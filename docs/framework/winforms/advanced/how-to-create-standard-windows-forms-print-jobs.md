---
title: "Como criar trabalhos de impressão padrão do Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- printing [Windows Forms]
- printing [Windows Forms], creating print jobs
- printing [Visual Basic], in Windows applications
ms.assetid: 03342b90-9cfe-40b2-838b-b479a13c5dea
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c2b0ce30f76fe7f8cbdc156c4a8ff5abffafae10
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a><span data-ttu-id="9f836-102">Como criar trabalhos de impressão padrão do Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9f836-102">How to: Create Standard Windows Forms Print Jobs</span></span>
<span data-ttu-id="9f836-103">É a base de impressão no Windows Forms a <xref:System.Drawing.Printing.PrintDocument> componente — mais especificamente, o <xref:System.Drawing.Printing.PrintDocument.PrintPage> evento.</span><span class="sxs-lookup"><span data-stu-id="9f836-103">The foundation of printing in Windows Forms is the <xref:System.Drawing.Printing.PrintDocument> component—more specifically, the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span> <span data-ttu-id="9f836-104">Escrevendo código para manipular o <xref:System.Drawing.Printing.PrintDocument.PrintPage> eventos, você pode especificar o que imprimir e como imprimi-lo.</span><span class="sxs-lookup"><span data-stu-id="9f836-104">By writing code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event, you can specify what to print and how to print it.</span></span>  
  
### <a name="to-create-a-print-job"></a><span data-ttu-id="9f836-105">Para criar um trabalho de impressão</span><span class="sxs-lookup"><span data-stu-id="9f836-105">To create a print job</span></span>  
  
1.  <span data-ttu-id="9f836-106">Adicionar um <xref:System.Drawing.Printing.PrintDocument> componente para seu formulário.</span><span class="sxs-lookup"><span data-stu-id="9f836-106">Add a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2.  <span data-ttu-id="9f836-107">Escreva código para manipular o <xref:System.Drawing.Printing.PrintDocument.PrintPage> evento.</span><span class="sxs-lookup"><span data-stu-id="9f836-107">Write code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>  
  
     <span data-ttu-id="9f836-108">Você terá de codificar sua própria lógica de impressão.</span><span class="sxs-lookup"><span data-stu-id="9f836-108">You will have to code your own printing logic.</span></span> <span data-ttu-id="9f836-109">Além disso, precisará especificar o material a ser impresso.</span><span class="sxs-lookup"><span data-stu-id="9f836-109">Additionally, you will have to specify the material to be printed.</span></span>  
  
     <span data-ttu-id="9f836-110">No exemplo de código a seguir, uma amostra de gráfico na forma de um retângulo vermelho criado no <xref:System.Drawing.Printing.PrintDocument.PrintPage> manipulador de eventos para atuar como material a ser impresso.</span><span class="sxs-lookup"><span data-stu-id="9f836-110">In the following code example, a sample graphic in the shape of a red rectangle is created in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler to act as material to be printed.</span></span>  
  
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
  
     <span data-ttu-id="9f836-111">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] e [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Coloque o seguinte código no construtor do formulário para registrar o manipulador de eventos.</span><span class="sxs-lookup"><span data-stu-id="9f836-111">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
     <span data-ttu-id="9f836-112">Você também deseja escrever código para o <xref:System.Drawing.Printing.PrintDocument.BeginPrint> e <xref:System.Drawing.Printing.PrintDocument.EndPrint> eventos, talvez incluindo um inteiro que representa o número total de páginas para imprimir que é reduzido à medida que cada página impressa.</span><span class="sxs-lookup"><span data-stu-id="9f836-112">You may also want to write code for the <xref:System.Drawing.Printing.PrintDocument.BeginPrint> and <xref:System.Drawing.Printing.PrintDocument.EndPrint> events, perhaps including an integer representing the total number of pages to print that is decremented as each page prints.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9f836-113">Você pode adicionar um <xref:System.Windows.Forms.PrintDialog> componente ao formulário para fornecer uma interface de usuário normal e eficiente (UI) para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="9f836-113">You can add a <xref:System.Windows.Forms.PrintDialog> component to your form to provide a clean and efficient user interface (UI) to your users.</span></span> <span data-ttu-id="9f836-114">Definindo o <xref:System.Windows.Forms.PrintDialog.Document%2A> propriedade o <xref:System.Windows.Forms.PrintDialog> permite que o componente para definir as propriedades relacionadas ao imprimir documentos que você está trabalhando com do formulário.</span><span class="sxs-lookup"><span data-stu-id="9f836-114">Setting the <xref:System.Windows.Forms.PrintDialog.Document%2A> property of the <xref:System.Windows.Forms.PrintDialog> component enables you to set properties related to the print document you are working with on your form.</span></span> <span data-ttu-id="9f836-115">Para obter mais informações sobre o <xref:System.Windows.Forms.PrintDialog> componente, consulte [componente PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="9f836-115">For more information about the <xref:System.Windows.Forms.PrintDialog> component, see [PrintDialog Component](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md).</span></span>  
  
     <span data-ttu-id="9f836-116">Para obter mais informações sobre as especificações de Windows Forms trabalhos de impressão, incluindo como criar um trabalho de impressão programaticamente, consulte <xref:System.Drawing.Printing.PrintPageEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="9f836-116">For more information about the specifics of Windows Forms print jobs, including how to create a print job programmatically, see <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f836-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="9f836-117">See Also</span></span>  
 <xref:System.Drawing.Printing.PrintDocument>  
 [<span data-ttu-id="9f836-118">Suporte à impressão nos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9f836-118">Windows Forms Print Support</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)