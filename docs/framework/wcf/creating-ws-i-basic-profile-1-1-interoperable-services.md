---
title: Creación de servicios interoperables de WS-I Basic Profile 1.1
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- configuration [WCF], interoperable services
ms.assetid: 91b70a21-8f5c-4679-808c-2ed5fa6b2013
ms.openlocfilehash: f32308a17e2934b6884140307074f97e6b51f5f9
ms.sourcegitcommit: 296183dbe35077b5c5e5e74d5fbe7f399bc507ee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2018
ms.locfileid: "50982859"
---
# <a name="creating-ws-i-basic-profile-11-interoperable-services"></a>Creación de servicios interoperables de WS-I Basic Profile 1.1
Para configurar un punto de conexión de servicio WCF para interoperar con [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] clientes de servicios Web:  
  
-   Utilice el tipo <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> como tipo de enlace para su punto de conexión de servicio.  
  
-   No utilice devolución de llamada sino características de contrato de sesión o comportamientos de transacción en su punto de conexión de servicio  
  
 Puede habilitar opcionalmente el soporte para HTTPS y la autenticación del cliente del nivel de transporte en el enlace.  
  
 Las características siguientes de la clase <xref:System.ServiceModel.BasicHttpBinding> requieren la funcionalidad más allá de WS-I Basic Profile 1.1:  
  
-   Codificación de mensajes del Mecanismo de optimización de transmisión del mensajes (MTOM) controlada por la propiedad <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType>. Deje esta propiedad en su valor predeterminado, que es <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType> para no utilizar MTOM.  
  
-   La seguridad de mensaje que controla el valor <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> proporciona compatibilidad con WS-Security conforme a WS-I Basic Security Profile 1.0. Deje esta propiedad en su valor predeterminado, que es <xref:System.ServiceModel.SecurityMode.Transport?displayProperty=nameWithType>, para no usar WS-Security.  
  
 Para que esté disponible para los metadatos para un servicio WCF [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], utilice las herramientas de generación de cliente de servicio Web: [Web Services Description Language Tool (Wsdl.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7h3ystb6%28v=vs.100%29), [herramienta descubrimiento de servicios Web (Disco.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cy2a3ybs%28v=vs.100%29)y el `Add Web Reference` característica en Visual Studio; debe habilitar la publicación de metadatos. Para obtener más información, consulte [extremos de metadatos de publicación](../../../docs/framework/wcf/publishing-metadata-endpoints.md).  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Descripción  
 Ejemplo de código siguiente muestra cómo agregar un extremo de WCF es compatible con [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] los clientes en el código y, o bien, en un archivo de configuración de servicio Web.  
  
### <a name="code"></a>Código  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)]
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)]  
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]  
  
## <a name="see-also"></a>Vea también  
 [Interoperabilidad con servicios web ASP.NET](../../../docs/framework/wcf/feature-details/interop-with-aspnet-web-services.md)
