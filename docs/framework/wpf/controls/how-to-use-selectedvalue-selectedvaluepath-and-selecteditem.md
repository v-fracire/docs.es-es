---
title: 'Cómo: Usar SelectedValue, SelectedValuePath y SelectedItem'
ms.date: 03/30/2017
helpviewer_keywords:
- TreeView control [WPF], SelectedValue properties
- Control class [WPF], SelectedItem properties
- Control class [WPF], TreeView properties
- Control class [WPF], SelectedValue properties
- TreeView control [WPF], SelectedItem properties
- SelectedValue [WPF], SelectedValuePath properties
- TreeView control [WPF], SelectedValuePath properties
- Control class [WPF], SelectedValuePath properties
- SelectedValue [WPF], SelectedItem properties
ms.assetid: 2fc92ad4-f02c-4f89-bbe9-d4978a7af0db
ms.openlocfilehash: 93720c0e1ac96a55fafa36479968cc3492cb0d84
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33554799"
---
# <a name="how-to-use-selectedvalue-selectedvaluepath-and-selecteditem"></a>Cómo: Usar SelectedValue, SelectedValuePath y SelectedItem
Este ejemplo muestra cómo utilizar el <xref:System.Windows.Controls.TreeView.SelectedValue%2A> y <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> propiedades para especificar un valor para el <xref:System.Windows.Controls.TreeView.SelectedItem%2A> de un <xref:System.Windows.Controls.TreeView>.  
  
## <a name="example"></a>Ejemplo  
 El <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> propiedad proporciona una manera de especificar un <xref:System.Windows.Controls.TreeView.SelectedValue%2A> para el <xref:System.Windows.Controls.TreeView.SelectedItem%2A> en un <xref:System.Windows.Controls.TreeView>. El <xref:System.Windows.Controls.TreeView.SelectedItem%2A> representa un objeto en el <xref:System.Windows.Controls.ItemsControl.Items%2A> colección y <xref:System.Windows.Controls.TreeView> muestra el valor de una propiedad única del elemento seleccionado. El <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> propiedad especifica la ruta de acceso a la propiedad que se usa para determinar el valor de la <xref:System.Windows.Controls.TreeView.SelectedValue%2A> propiedad. Los ejemplos de este tema muestran este concepto.  
  
 El ejemplo siguiente muestra un <xref:System.Windows.Data.XmlDataProvider> que contiene información del empleado.  
  
 [!code-xaml[TreeViewSelectedValue#XMLDataProvider](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#xmldataprovider)]  
  
 En el ejemplo siguiente se define un <xref:System.Windows.HierarchicalDataTemplate> que muestra la `EmployeeName` y `EmployeeWorkDay` de la `Employee`. Tenga en cuenta que la <xref:System.Windows.HierarchicalDataTemplate> no especifica la `EmployeeNumber` como parte de la plantilla.  
  
 [!code-xaml[TreeViewSelectedValue#HierarchicalDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#hierarchicaldatatemplate)]  
  
 El siguiente ejemplo se muestra un <xref:System.Windows.Controls.TreeView> que usa definida previamente <xref:System.Windows.HierarchicalDataTemplate> y que establece la <xref:System.Windows.Controls.TreeView.SelectedValue%2A> propiedad a la `EmployeeNumber`. Cuando se selecciona un `EmployeeName` en el <xref:System.Windows.Controls.TreeView>, el <xref:System.Windows.Controls.TreeView.SelectedItem%2A> propiedad devuelve el `EmployeeInfo` elemento de datos que corresponde a la seleccionada `EmployeeName`. Sin embargo, dado que la <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> de este <xref:System.Windows.Controls.TreeView> está establecido en `EmployeeNumber`, el <xref:System.Windows.Controls.TreeView.SelectedValue%2A> está establecido en el `EmployeeNumber`.  
  
 [!code-xaml[TreeViewSelectedValue#SelectedValuePath](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#selectedvaluepath)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.TreeView>  
 <xref:System.Windows.Controls.TreeViewItem>  
 [Introducción a TreeView](../../../../docs/framework/wpf/controls/treeview-overview.md)  
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/treeview-how-to-topics.md)
