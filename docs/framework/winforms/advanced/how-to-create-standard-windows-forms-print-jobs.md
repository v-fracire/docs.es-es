---
title: 'Cómo: Crear trabajos de impresión estándar de formularios Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- printing [Windows Forms]
- printing [Windows Forms], creating print jobs
- printing [Visual Basic], in Windows applications
ms.assetid: 03342b90-9cfe-40b2-838b-b479a13c5dea
ms.openlocfilehash: b580268a6af3f56f240a1c511c3d473a4a5ddc15
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33522338"
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a>Cómo: Crear trabajos de impresión estándar de formularios Windows Forms
La base de la impresión en formularios Windows Forms es el <xref:System.Drawing.Printing.PrintDocument> componente, más específicamente, el <xref:System.Drawing.Printing.PrintDocument.PrintPage> eventos. Al escribir código para controlar la <xref:System.Drawing.Printing.PrintDocument.PrintPage> evento, puede especificar lo que desea imprimir y cómo imprimirlo.  
  
### <a name="to-create-a-print-job"></a>Para crear un trabajo de impresión  
  
1.  Agregar un <xref:System.Drawing.Printing.PrintDocument> al formulario.  
  
2.  Escriba código para controlar el evento <xref:System.Drawing.Printing.PrintDocument.PrintPage>.  
  
     Tendrá que codificar su propia lógica de impresión. Además, tendrá que especificar el material para su impresión.  
  
     En el ejemplo de código siguiente, se crea un gráfico de ejemplo en la forma de un rectángulo rojo en el <xref:System.Drawing.Printing.PrintDocument.PrintPage> controlador de eventos para que actúe como material para ser impreso.  
  
    ```vb  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillRectangle(Brushes.Red, New Rectangle(500, 500, 500, 500))  
    End Sub  
    ```  
  
    ```csharp  
    private void printDocument1_PrintPage(object sender,   
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Red,   
         new Rectangle(500, 500, 500, 500));  
    }  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Red,  
             Rectangle(500, 500, 500, 500));  
       }  
    ```  
  
     (Visual C# y [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
    ```  
  
    ```cpp  
    printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    ```  
  
     También puede escribir código para el <xref:System.Drawing.Printing.PrintDocument.BeginPrint> y <xref:System.Drawing.Printing.PrintDocument.EndPrint> eventos, quizá para incluir un entero que representa el número total de páginas para imprimir que cada página se imprime.  
  
    > [!NOTE]
    >  Puede agregar un <xref:System.Windows.Forms.PrintDialog> componente al formulario para proporcionar una interfaz de usuario limpia y eficiente (UI) a los usuarios. Establecer el <xref:System.Windows.Forms.PrintDialog.Document%2A> propiedad de la <xref:System.Windows.Forms.PrintDialog> habilita el componente establecer propiedades relacionadas con la impresión del documento que está trabajando con en el formulario. Para obtener más información sobre la <xref:System.Windows.Forms.PrintDialog> componente, vea [PrintDialog (componente)](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md).  
  
     Para obtener más información sobre las características de Windows Forms, trabajos de impresión, incluido cómo crear un trabajo de impresión mediante programación, vea <xref:System.Drawing.Printing.PrintPageEventArgs>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Drawing.Printing.PrintDocument>  
 [Windows Forms Print Support](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md) (Funcionalidad para imprimir en Windows Forms)
