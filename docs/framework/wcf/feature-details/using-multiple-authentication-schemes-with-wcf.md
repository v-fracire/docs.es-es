---
title: "Usar m&#250;ltiples esquemas de autenticaci&#243;n con WCF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f32a56a0-e2b2-46bf-a302-29e1275917f9
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Usar m&#250;ltiples esquemas de autenticaci&#243;n con WCF
WCF permite ahora especificar varios esquemas de autenticación en un único extremo.  Además los servicios hospedados en web pueden heredar sus valores de autenticación directamente de IIS.  Los servicios autohospedados pueden especificar los esquemas de autenticación que se pueden usar.  Para obtener más información sobre cómo establecer la configuración de autenticación en IIS, vea [Autenticación en IIS](http://go.microsoft.com/fwlink/?LinkId=232458)  
  
## Servicios hospedados en IIS  
 Para los servicios hospedados en IIS, establezca los esquemas de autenticación que desea usa en IIS.  A continuación, en el archivo web.config del servicio, en la configuración de enlace especifique el tipo clientCredential como “InheritedFromHost” como se muestra en el fragmento XML siguiente:  
  
```xml  
<bindings>  
      <basicHttpBinding>  
        <binding name="secureBinding">  
          <security mode="Transport">  
            <transport clientCredentialType="InheritedFromHost" />  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
```  
  
 Puede especificar que solo quiere usar un subconjunto de esquemas de autenticación con el servicio mediante el ServiceAuthenticationBehavior o el elemento \<serviceAuthenticationManager\>.  Al configurar esto en el código, use ServiceAuthenticationBehavior como se muestra en el fragmento de código siguiente.  
  
```csharp  
// ...  
ServiceAuthenticationBehavior sab = null;  
sab = serviceHost.Description.Behaviors.Find<ServiceAuthenticationBehavior>();  
  
if (sab == null)  
{  
    sab = new ServiceAuthenticationBehavior();  
    sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
    serviceHost.Description.Behaviors.Add(sab);  
}  
else  
{  
     sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
}  
// ...  
  
```  
  
 Al configurar esto en un archivo de configuración, use el elemento \<serviceAuthenticationManager\> como se muestra en el fragmento XML siguiente.  
  
```xml  
<behaviors>  
      <serviceBehaviors>  
        <behavior name="limitedAuthBehavior">  
          <serviceAuthenticationManager authenticationSchemes="Negotiate, Digest, Basic"/>  
          <!-- ... -->  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
```  
  
 Esto garantizará que solo se considere un subconjunto de los esquemas de autenticación enumerados aquí para aplicar en el extremo de servicio, según cuál se haya seleccionado en IIS.  Esto significa que un desarrollador puede excluir la autenticación básica de la lista omitiéndola de la lista de serviceAuthenticationManager e incluso si está habilitada en IIS, no se aplicará en el extremo de servicio.  
  
## Servicios WCF autohospedados  
 Los servicios autohospedados se configuran de manera ligeramente diferente puesto que no hay configuración de IIS para heredar.  Aquí se usa el elemento \<serviceAuthenticationManager\> o ServiceAuthenticationBehavior para especificar los valores de autenticación que se heredarán.  En el código tiene el siguiente aspecto:  
  
```csharp  
// ...  
ServiceAuthenticationBehavior sab = null;  
sab = serviceHost.Description.Behaviors.Find<ServiceAuthenticationBehavior>();  
  
if (sab == null)  
{  
    sab = new ServiceAuthenticationBehavior();  
    sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
    serviceHost.Description.Behaviors.Add(sab);  
}  
else  
{  
     sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
}  
// ...  
  
```  
  
 En la configuración, tiene el siguiente aspecto:  
  
```xml  
<behaviors>  
      <serviceBehaviors>  
        <behavior name="limitedAuthBehavior">  
          <serviceAuthenticationManager authenticationSchemes="Negotiate, Digest, Basic"/>  
          <!-- ... -->  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
```  
  
 A continuación puede especificar InheritFromHost en la configuración de enlace como se muestra en el fragmento XML siguiente.  
  
```xml  
<bindings>  
      <basicHttpBinding>  
        <binding name="secureBinding">  
          <security mode="Transport">  
            <transport clientCredentialType="InheritedFromHost" />  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
```  
  
 Opcionalmente, puede especificar los esquemas de autenticación en un enlace personalizado, estableciendo los esquemas de autenticación en el elemento de enlace de transporte HTTP, como se muestra en el siguiente fragmento de código de configuración.  
  
```xml  
<binding name="multipleBinding">  
      <textMessageEncoding/>  
      <httpTransport authenticationScheme="Negotiate, Ntlm, Digest, Basic" />  
    </binding>  
  
```  
  
## Vea también  
 [Enlaces y seguridad](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)   
 [Extremos: direcciones, enlaces y contratos](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)   
 [Configuración de enlaces proporcionados por el sistema](../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Capacidades de seguridad con enlaces personalizados](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)   
 [Enlaces](../../../../docs/framework/wcf/feature-details/bindings.md)   
 [Enlaces](../../../../docs/framework/wcf/feature-details/bindings.md)   
 [Enlaces personalizados](../../../../docs/framework/wcf/extending/custom-bindings.md)