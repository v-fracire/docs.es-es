---
title: HttpTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 088a7bce-6bb2-4839-ad74-f68d4b1aa0f9
ms.openlocfilehash: 34ad4b8534d082d7f5248d42d70ca5bd0647a5dc
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/19/2018
ms.locfileid: "49454322"
---
# <a name="httptransportbindingelement"></a>HttpTransportBindingElement
HttpTransportBindingElement  
  
## <a name="syntax"></a>Sintaxis  
  
```csharp
class HttpTransportBindingElement : TransportBindingElement  
{  
  boolean AllowCookies;  
  string AuthenticationScheme;  
  boolean BypassProxyOnLocal;  
  string HostNameComparisonMode;  
  boolean KeepAliveEnabled;  
  sint32 MaxBufferSize;  
  string ProxyAddress;  
  string ProxyAuthenticationScheme;  
  string Realm;  
  string TransferMode;  
  boolean UnsafeConnectionNtlmAuthentication;  
  boolean UseDefaultWebProxy;  
};  
```  
  
## <a name="methods"></a>Métodos  
 La clase HttpTransportBindingElement no define ningún método.  
  
## <a name="properties"></a>Propiedades  
 La clase HttpTransportBindingElement tiene las propiedades siguientes:  
  
### <a name="allowcookies"></a>AllowCookies  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Un valor que indica si el cliente acepta las cookies y las propaga en solicitudes futuras.  
  
### <a name="authenticationscheme"></a>AuthenticationScheme  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El esquema de autenticación usado para autenticar las solicitudes del cliente que está procesando un agente de escucha HTTP.  
  
### <a name="bypassproxyonlocal"></a>BypassProxyOnLocal  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Un valor que indica si se omiten servidores proxy para direcciones locales.  
  
### <a name="hostnamecomparisonmode"></a>HostNameComparisonMode  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Un valor que indica si el nombre del host se usa para alcanzar el servicio al coincidir con el URI.  
  
### <a name="keepaliveenabled"></a>KeepAliveEnabled  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Cuando se habilita, las conexiones HTTP se mantienen vivas sin tener en cuenta el nivel de actividad.  
  
### <a name="maxbuffersize"></a>MaxBufferSize  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El tamaño máximo del grupo de búferes.  
  
### <a name="proxyaddress"></a>ProxyAddress  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Un URI que contiene la dirección del proxy que utilizar para las solicitudes HTTP.  
  
### <a name="proxyauthenticationscheme"></a>ProxyAuthenticationScheme  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El esquema de autenticación usado para autenticar las solicitudes del cliente que un proxy HTTP está procesando.  
  
### <a name="realm"></a>Dominio kerberos  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El dominio kerberos de autenticación.  
  
### <a name="transfermode"></a>TransferMode  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Un valor que especifica si los mensajes se almacenan en búfer, se transmiten o si son una solicitud o una respuesta.  
  
### <a name="unsafeconnectionntlmauthentication"></a>UnsafeConnectionNtlmAuthentication  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Un valor que indica si la conexión compartida no segura está habilitada en el servidor.  
  
### <a name="usedefaultwebproxy"></a>UseDefaultWebProxy  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Un valor que indica si se utiliza la configuración de proxy del equipo en lugar de la configuración específica del usuario.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>
