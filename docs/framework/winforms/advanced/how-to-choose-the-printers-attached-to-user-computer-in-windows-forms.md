---
title: 'Como: escolher as impressoras conectadas ao computador de um usuário no Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- printing [Windows Forms], choosing printers
- printers [Windows Forms], choosing
ms.assetid: 63c1172b-2931-4ac0-953f-37f629494bbf
ms.openlocfilehash: efd65ff6417b1a63a7f87917c4d9a95dedc464ad
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62004439"
---
# <a name="how-to-choose-the-printers-attached-to-a-users-computer-in-windows-forms"></a>Como: escolher as impressoras conectadas ao computador de um usuário no Windows Forms
Geralmente, os usuários escolhem uma impressora diferente da impressora padrão para imprimir. Você pode habilitar os usuários escolham uma impressora dentre as instaladas no momento usando o <xref:System.Windows.Forms.PrintDialog> componente. Por meio de <xref:System.Windows.Forms.PrintDialog> componente, o <xref:System.Windows.Forms.DialogResult> da <xref:System.Windows.Forms.PrintDialog> componente é capturado e usado para selecionar a impressora.  
  
 No procedimento a seguir, um arquivo de texto é selecionado para ser impresso na impressora padrão. O <xref:System.Windows.Forms.PrintDialog> classe é então instanciada.  
  
### <a name="to-choose-a-printer-and-then-print-a-file"></a>Para escolher uma impressora e imprimir um arquivo  
  
1. Selecione a impressora a ser usada com o <xref:System.Windows.Forms.PrintDialog> componente.  
  
     No exemplo de código a seguir, há dois eventos que estão sendo manipulados. No primeiro, um <xref:System.Windows.Forms.Button> do controle <xref:System.Windows.Forms.Control.Click> evento, o <xref:System.Windows.Forms.PrintDialog> classe é instanciada e a impressora selecionada pelo usuário é capturada no <xref:System.Windows.Forms.DialogResult> propriedade.  
  
     No segundo evento, o <xref:System.Drawing.Printing.PrintDocument.PrintPage> eventos do <xref:System.Drawing.Printing.PrintDocument> componente, um documento de exemplo é impresso na impressora especificada.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles Button1.Click  
       Dim PrintDialog1 As New PrintDialog()  
       PrintDialog1.Document = PrintDocument1  
       Dim result As DialogResult = PrintDialog1.ShowDialog()  
  
       If (result = DialogResult.OK) Then  
         PrintDocument1.Print()  
       End If   
  
    End Sub  
  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillRectangle(Brushes.Red, New Rectangle(500, 500, 500, 500))          
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       PrintDialog printDialog1 = new PrintDialog();  
       printDialog1.Document = printDocument1;  
       DialogResult result = printDialog1.ShowDialog();  
       if (result == DialogResult.OK)  
       {  
          printDocument1.Print();  
       }  
    }  
  
    private void printDocument1_PrintPage(object sender,   
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Red,   
         new Rectangle(500, 500, 500, 500));  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          PrintDialog ^ printDialog1 = gcnew PrintDialog();  
          printDialog1->Document = printDocument1;  
          System::Windows::Forms::DialogResult result =   
             printDialog1->ShowDialog();  
          if (result == DialogResult::OK)  
          {  
             printDocument1->Print();  
          }  
       }  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Red,  
             Rectangle(500, 500, 500, 500));  
       }  
    ```  
  
     (Visual c# e [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) coloque o seguinte código no construtor do formulário para registrar o manipulador de eventos.  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>Consulte também

- [Suporte à impressão nos Windows Forms](windows-forms-print-support.md)
