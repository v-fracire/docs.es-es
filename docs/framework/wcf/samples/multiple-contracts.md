---
title: Contratos múltiples
ms.date: 03/30/2017
ms.assetid: 2bef319b-fe9c-4d49-ac6c-dfb23eb35099
ms.openlocfilehash: 040ab9b80e9567139ca4588e3ddf83b8f43f2d76
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43864818"
---
# <a name="multiple-contracts"></a>Contratos múltiples
El ejemplo de contratos múltiples muestra cómo implementar más de un contrato en un servicio y cómo configurar los puntos de conexión para comunicarse con cada uno de los contratos implementados. En este ejemplo se basa en el [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md). El servicio se ha modificado para definir dos contratos: `ICalculator` y `ICalculatorSession`.  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 La clase de servicio implementa los contratos `ICalculator` e `ICalculatorSession`. Dado que uno de los contratos requiere una sesión, el servicio utiliza el modo de instancia <xref:System.ServiceModel.InstanceContextMode.PerSession> para mantener el estado en toda la duración de la sesión.  
  
 La configuración de servicio se ha modificado para definir dos extremos para exponer cada contrato. El extremo `ICalculator` se expone en la dirección base utilizando `basicHttpBinding`. El extremo `ICalculatorSession` se expone en la dirección base/sesión utilizando `wsHttpBinding` con el atributo `bindingConfiguration` establecido en `BindingWithSession`, tal y como se muestra en la configuración de ejemplo siguiente.  
  
```xml  
<service   
    name="Microsoft.ServiceModel.Samples.CalculatorService"  
    behaviorConfiguration="CalculatorServiceBehavior">  
  <!-- ICalculator endpoint is exposed using BasicBinding at the base  
       address provided by host:   
       http://localhost/servicemodelsamples/service.svc  -->  
  <endpoint address=""  
            binding="basicHttpBinding"  
            contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  <!-- ICalculatorSession endpoint is exposed using BindingWithSession  
       at {baseaddress}/session:  
       http://localhost/servicemodelsamples/service.svc/session -->  
  <endpoint address="session"  
            binding="wsHttpBinding"  
            bindingConfiguration="BindingWithSession"   
           contract="Microsoft.ServiceModel.Samples.ICalculatorSession" />  
  ...  
</service>  
```  
  
 El código de cliente generado incluye ahora una clase de cliente para el contrato original `ICalculator` y el nuevo contrato `ICalculatorSession`. Se han modificado la configuración de cliente y el código para comunicarse con cada contrato en el punto de conexión de servicio adecuado.  
  
 El cliente es una aplicación de consola de Windows (.exe). El servicio está hospedado por Internet Information Services (IIS).  
  
 La ventana de la consola del cliente muestra las operaciones enviadas a cada uno de los puntos de conexión, primero el punto de conexión básico, seguido por el punto de conexión seguro.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de que ha realizado la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\MultipleContracts`  
  
## <a name="see-also"></a>Vea también
