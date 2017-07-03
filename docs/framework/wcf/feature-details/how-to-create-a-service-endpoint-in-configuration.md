---
title: "C&#243;mo crear un extremo de servicio en configuraci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "2016-06-16"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f474e25d-2a27-4f31-84c5-395c442b8e70
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# C&#243;mo crear un extremo de servicio en configuraci&#243;n
Los extremos proporcionan a los clientes acceso a la funcionalidad que ofrece un servicio de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]. Puede definir uno o más extremos para un servicio usando una combinación de direcciones de extremo relativas y absolutas; si no se define ninguno, el tiempo de ejecución proporciona varios de forma predeterminada. En este tema se muestra cómo agregar extremos mediante un archivo de configuración que contiene tanto direcciones absolutas como relativas.  
  
## Ejemplo  
 La siguiente configuración de servicio especifica una dirección base y cinco extremos.  
  
```xml  
<configuration>  
  
  <appSettings>  
    <!-- use appSetting to configure base address provided by host -->  
    <add key="baseAddress" value="http://localhost:8000/servicemodelsamples/service" />  
  </appSettings>  
  
  <system.serviceModel>  
    <services>  
    <!-- This section is optional with the default configuration introduced  
         in .NET Framework 4. -->  
      <service  
          name="Microsoft.ServiceModel.Samples.CalculatorService">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
          </baseAddresses>  
        </host>  
        <endpoint address=""  
                  binding="wsHttpBinding"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <endpoint address="/test"  
                  binding="wsHttpBinding"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <endpoint address="http://localhost:8001/hello/servicemodelsamples"  
                  binding="wsHttpBinding"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <endpoint address="net.tcp://localhost:9000/servicemodelsamples/service"  
                  binding="netTcpBinding"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <!-- the mex endpoint is another relative address exposed at   
             http://localhost:8000/ServiceModelSamples/service/mex -->  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  
  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  
  </system.serviceModel>  
  
</configuration>  
  
```  
  
## Ejemplo  
 La dirección base se especifica utilizando el elemento `add`, bajo service\/host\/baseAddresses, como se muestra en el siguiente ejemplo.  
  
```xml  
<service   
    name="Microsoft.ServiceModel.Samples.CalculatorService">  
  <host>  
    <baseAddresses>  
      <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
    </baseAddresses>  
  </host>  
```  
  
## Ejemplo  
 La primera definición de extremo mostrada en el siguiente ejemplo especifica una dirección relativa, que significa que la dirección del extremo es una combinación de la dirección base y la dirección relativa siguiendo las reglas de composición de identificadores uniformes de recursos \(URI\). La dirección relativa está vacía \(""\), por lo que la dirección del extremo es igual a la dirección base. La dirección del punto de conexión real es http:\/\/localhost:8000\/servicemodelsamples\/service.  
  
```xml  
<endpoint address=""   
    binding="wsHttpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## Ejemplo  
 La segunda definición de extremo también especifica una dirección relativa, como se muestra en el siguiente ejemplo de configuración. La dirección relativa, "test", se anexa a la dirección base. La dirección del extremo real es http:\/\/localhost:8000\/servicemodelsamples\/service\/test.  
  
```xml  
<endpoint address="/test"  
    binding="wsHttpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## Ejemplo  
 La tercera definición de extremo especifica una dirección absoluta, como se muestra en el siguiente ejemplo de configuración. La dirección base no desempeña ningún papel en la dirección. La dirección del extremo real es http:\/\/localhost:8001\/hello\/servicemodelsamples.  
  
```xml  
<endpoint address="http://localhost:8001/hello/servicemodelsamples"  
    binding="wsHttpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## Ejemplo  
 La cuarta dirección del extremo especifica una dirección absoluta y un TCP de transporte diferente. La dirección base no desempeña ningún papel en la dirección. La dirección del punto de conexión real es net.tcp:\/\/localhost:9000\/servicemodelsamples\/service.  
  
```xml  
<endpoint address="net.tcp://localhost:9000/servicemodelsamples/service"  
    binding="netTcpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## Ejemplo  
 Para usar los puntos de conexión predeterminados proporcionados por el tiempo de ejecución, no especifique ningún punto de conexión de servicio en el código ni en el archivo de configuración. En este ejemplo, el tiempo de ejecución crea los puntos de conexión predeterminados al abrir el servicio.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] los puntos de conexión, enlaces y comportamientos predeterminados, consulte [Configuración simplificada](../../../../docs/framework/wcf/simplified-configuration.md) y [Configuración simplificada de los servicios de WCF](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
```xml  
<configuration>  
  
  <appSettings>  
    <!-- use appSetting to configure base address provided by host -->  
    <add key="baseAddress" value="http://localhost:8000/servicemodelsamples/service" />  
  </appSettings>  
  
  <system.serviceModel>  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  
  </system.serviceModel>  
  
</configuration>  
```