---
title: 'Cómo: Enlazar un objeto DataView a un control DataGridView de Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2b73d60a-6049-446a-85a7-3e5a68b183e2
ms.openlocfilehash: 98b3afcded257bc11dc3bca7d9a9310dc1a7cc89
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32765027"
---
# <a name="how-to-bind-a-dataview-object-to-a-windows-forms-datagridview-control"></a>Cómo: Enlazar un objeto DataView a un control DataGridView de Windows Forms
El control <xref:System.Windows.Forms.DataGridView> proporciona una forma eficaz y flexible de mostrar datos en formato de tabla. El control <xref:System.Windows.Forms.DataGridView> admite el modelo de enlace de datos de Windows Forms estándar, por lo que se enlazará a <xref:System.Data.DataView> y a otros orígenes de datos. Sin embargo, en la mayoría de las situaciones se enlazará a un componente <xref:System.Windows.Forms.BindingSource> que administrará los detalles de la interacción con el origen de datos.  
  
 Para obtener más información sobre la <xref:System.Windows.Forms.DataGridView> control, vea [información general del Control DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md).  
  
### <a name="to-connect-a-datagridview-control-to-a-dataview"></a>Para conectar un control DataGridView a DataView  
  
1.  Implemente un método que controle los detalles de recuperación de datos desde una base de datos. En el ejemplo de código siguiente se implementa un método `GetData` que inicializa un componente <xref:System.Data.SqlClient.SqlDataAdapter> y lo utiliza para rellenar un <xref:System.Data.DataSet>. Asegúrese de establecer la variable `connectionString` en un valor que sea adecuado para la base de datos. Necesitará tener acceso a un servidor que tenga la base de datos de ejemplo AdventureWorks de SQL Server instalada.  
  
     [!code-csharp[DP DataViewWinForms Sample#LDVSample1GetData](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/CS/Form1.cs#ldvsample1getdata)]
     [!code-vb[DP DataViewWinForms Sample#LDVSample1GetData](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/VB/Form1.vb#ldvsample1getdata)]  
  
2.  En el controlador de eventos <xref:System.Windows.Forms.Form.Load> del formulario, enlace el control <xref:System.Windows.Forms.DataGridView> al componente <xref:System.Windows.Forms.BindingSource> y llame al método `GetData` para recuperar los datos de la base de datos. <xref:System.Data.DataView> se crea a partir de una consulta [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] en <xref:System.Data.DataTable> Contact y luego se enlaza al componente <xref:System.Windows.Forms.BindingSource>.  
  
     [!code-csharp[DP DataViewWinForms Sample#LDVSample1FormLoad](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/CS/Form1.cs#ldvsample1formload)]
     [!code-vb[DP DataViewWinForms Sample#LDVSample1FormLoad](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/VB/Form1.vb#ldvsample1formload)]  
  
## <a name="see-also"></a>Vea también  
 [Enlace de datos y LINQ to DataSet](../../../../docs/framework/data/adonet/data-binding-and-linq-to-dataset.md)
