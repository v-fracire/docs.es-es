---
title: SqlDependency en una aplicación ASP.NET
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ff226ce3-f6b5-47a1-8d22-dc78b67e07f5
ms.openlocfilehash: 5465238e4b9deaa13c76cb35122fcaded7acd7f7
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43864844"
---
# <a name="sqldependency-in-an-aspnet-application"></a>SqlDependency en una aplicación ASP.NET
En el ejemplo de esta sección se muestra cómo utilizar <xref:System.Data.SqlClient.SqlDependency> de forma indirecta aprovechando el objeto <xref:System.Web.Caching.SqlCacheDependency> de ASP:NET. El objeto <xref:System.Web.Caching.SqlCacheDependency> utiliza <xref:System.Data.SqlClient.SqlDependency> para escuchar notificaciones y de actualizar correctamente la caché.  
  
> [!NOTE]
>  El código de ejemplo se da por supuesto que ha habilitado las notificaciones de consulta mediante la ejecución de las secuencias de comandos en [habilitar las notificaciones de consulta](../../../../../docs/framework/data/adonet/sql/enabling-query-notifications.md).  
  
## <a name="about-the-sample-application"></a>Acerca de la aplicación de ejemplo  
 La aplicación de ejemplo usa una única página Web de ASP.NET para mostrar información de producto desde la **AdventureWorks** base de datos de SQL Server en un <xref:System.Web.UI.WebControls.GridView> control. Cuando se carga la página, el código escribe la hora actual en un control <xref:System.Web.UI.WebControls.Label>. A continuación, se define un objeto <xref:System.Web.Caching.SqlCacheDependency> y se establecen las propiedades del objeto <xref:System.Web.Caching.Cache> para almacenar los datos de la caché durante tres minutos como máximo. Entonces el código se conecta a la base de datos y recupera los datos. Cuando la página está cargada y la aplicación se está ejecutando, ASP.NET recuperará datos de la caché, lo cual podrá comprobar si observa que la hora de la página no cambia. Si los datos que se supervisan cambian, ASP.NET invalida la caché y vuelve a llenar el control `GridView` con datos nuevos, actualizando la hora que se muestra en el control `Label`.  
  
## <a name="creating-the-sample-application"></a>Crear la aplicación de ejemplo  
 Para crear y ejecutar la aplicación de ejemplo, siga estos pasos:  
  
1.  Cree un nuevo sitio web ASP.NET.  
  
2.  Agregue un control <xref:System.Web.UI.WebControls.Label> y <xref:System.Web.UI.WebControls.GridView> a la página Default.aspx.  
  
3.  Abra el módulo de clase de la página y agregue las siguientes directivas:  
  
    ```vb  
    Option Strict On  
    Option Explicit On  
  
    Imports System.Data.SqlClient  
    ```  
  
    ```csharp  
    using System.Data.SqlClient;  
    using System.Web.Caching;  
    ```  
  
4.  Agregue el siguiente código al evento `Page_Load` de la página:  
  
     [!code-csharp[DataWorks SqlDependency.AspNet#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/CS/Default.aspx.cs#1)]
     [!code-vb[DataWorks SqlDependency.AspNet#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/VB/Default.aspx.vb#1)]  
  
5.  Agregue dos métodos auxiliares: `GetConnectionString` y `GetSQL`. La cadena de conexión definida utiliza seguridad integrada. Deberá comprobar que la cuenta que está usando tiene los permisos de base de datos necesarios y que la base de datos de ejemplo, **AdventureWorks**, tiene habilitadas las notificaciones. Para obtener más información, consulte [especial consideraciones al usar notificaciones de consulta](https://msdn.microsoft.com/library/a83c8dc8-4fb9-4ffd-a2a5-c07cf4a203c7).  
  
     [!code-csharp[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/CS/Default.aspx.cs#2)]
     [!code-vb[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/VB/Default.aspx.vb#2)]  
  
### <a name="testing-the-application"></a>Probar la aplicación  
 La aplicación almacena en caché los datos mostrados en el formulario web y los actualiza cada tres minutos si no hay ninguna actividad Si se produce un cambio en la base de datos, la caché se actualiza inmediatamente. Ejecute la aplicación desde Visual Studio, que carga la página en el explorador. La hora de actualización de la caché que se muestra indica la hora de la última actualización. Espere tres minutos y, a continuación, actualice la página, lo que dará lugar a un evento postback de datos. Observe que la hora que se muestra en la página ha cambiado. Si actualiza la página sin esperar los tres minutos, la hora mostrada será la misma.  
  
 A continuación, actualice los datos de la base de datos mediante un comando UPDATE deTransact-SQL y actualice la página. La hora que se muestra indica ahora que la caché se ha actualizado con los datos nuevos de la base de datos. Tenga en cuenta que, aunque la caché está actualizada, la hora que se muestra en la página no cambia hasta que se produce un evento postback de datos.  
  
## <a name="see-also"></a>Vea también  
 [Notificaciones de consulta en SQL Server](../../../../../docs/framework/data/adonet/sql/query-notifications-in-sql-server.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
