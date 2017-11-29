---
title: "Como desabilitar botões em uma coluna de botão no controle DataGridView dos Windows Forms"
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
helpviewer_keywords:
- data grids [Windows Forms], disabling buttons
- buttons [Windows Forms], disabling in button columns
- DataGridView control [Windows Forms], disabling button cells
ms.assetid: 5c344d01-013a-4a6b-8f8d-62ec9321d81e
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3c6f28ac69e2799a25f75c3093d9c8f1ef01bc48
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-disable-buttons-in-a-button-column-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="7a858-102">Como desabilitar botões em uma coluna de botão no controle DataGridView dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7a858-102">How to: Disable Buttons in a Button Column in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="7a858-103">O <xref:System.Windows.Forms.DataGridView> controle inclui o <xref:System.Windows.Forms.DataGridViewButtonCell> classe para exibir células com uma interface de usuário (UI) como um botão.</span><span class="sxs-lookup"><span data-stu-id="7a858-103">The <xref:System.Windows.Forms.DataGridView> control includes the <xref:System.Windows.Forms.DataGridViewButtonCell> class for displaying cells with a user interface (UI) like a button.</span></span> <span data-ttu-id="7a858-104">No entanto, <xref:System.Windows.Forms.DataGridViewButtonCell> não fornece uma maneira de desabilitar a aparência do botão exibido pela célula.</span><span class="sxs-lookup"><span data-stu-id="7a858-104">However, <xref:System.Windows.Forms.DataGridViewButtonCell> does not provide a way to disable the appearance of the button displayed by the cell.</span></span>  
  
 <span data-ttu-id="7a858-105">O exemplo de código a seguir demonstra como personalizar o <xref:System.Windows.Forms.DataGridViewButtonCell> classe para exibir botões que podem aparecer desabilitado.</span><span class="sxs-lookup"><span data-stu-id="7a858-105">The following code example demonstrates how to customize the <xref:System.Windows.Forms.DataGridViewButtonCell> class to display buttons that can appear disabled.</span></span> <span data-ttu-id="7a858-106">O exemplo define um novo tipo de célula, `DataGridViewDisableButtonCell`, que deriva de <xref:System.Windows.Forms.DataGridViewButtonCell>.</span><span class="sxs-lookup"><span data-stu-id="7a858-106">The example defines a new cell type, `DataGridViewDisableButtonCell`, that derives from <xref:System.Windows.Forms.DataGridViewButtonCell>.</span></span> <span data-ttu-id="7a858-107">Esse tipo de célula fornece uma nova propriedade `Enabled` que pode ser definida como `false` para desenhar um botão desabilitado na célula.</span><span class="sxs-lookup"><span data-stu-id="7a858-107">This cell type provides a new `Enabled` property that can be set to `false` to draw a disabled button in the cell.</span></span> <span data-ttu-id="7a858-108">O exemplo também define um novo tipo de coluna, `DataGridViewDisableButtonColumn`, que exibe objetos `DataGridViewDisableButtonCell`.</span><span class="sxs-lookup"><span data-stu-id="7a858-108">The example also defines a new column type, `DataGridViewDisableButtonColumn`, that displays `DataGridViewDisableButtonCell` objects.</span></span> <span data-ttu-id="7a858-109">Para demonstrar essa nova célula e a coluna de tipo, o valor atual de cada <xref:System.Windows.Forms.DataGridViewCheckBoxCell> no pai <xref:System.Windows.Forms.DataGridView> determina se o `Enabled` propriedade o `DataGridViewDisableButtonCell` na mesma linha é `true` ou `false`.</span><span class="sxs-lookup"><span data-stu-id="7a858-109">To demonstrate this new cell and column type, the current value of each <xref:System.Windows.Forms.DataGridViewCheckBoxCell> in the parent <xref:System.Windows.Forms.DataGridView> determines whether the `Enabled` property of the `DataGridViewDisableButtonCell` in the same row is `true` or `false`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7a858-110">Quando você deriva de <xref:System.Windows.Forms.DataGridViewCell> ou <xref:System.Windows.Forms.DataGridViewColumn> e adicionar novas propriedades para a classe derivada, certifique-se de substituir o `Clone` método para copiar as novas propriedades durante operações de clonagem.</span><span class="sxs-lookup"><span data-stu-id="7a858-110">When you derive from <xref:System.Windows.Forms.DataGridViewCell> or <xref:System.Windows.Forms.DataGridViewColumn> and add new properties to the derived class, be sure to override the `Clone` method to copy the new properties during cloning operations.</span></span> <span data-ttu-id="7a858-111">Você também deve chamar o método `Clone` da classe base para que as propriedades da classe base sejam copiadas para a nova célula ou coluna.</span><span class="sxs-lookup"><span data-stu-id="7a858-111">You should also call the base class's `Clone` method so that the properties of the base class are copied to the new cell or column.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a858-112">Exemplo</span><span class="sxs-lookup"><span data-stu-id="7a858-112">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridView.DisabledButtons#0](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DisabledButtons/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.DisabledButtons#0](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DisabledButtons/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7a858-113">Compilando o código</span><span class="sxs-lookup"><span data-stu-id="7a858-113">Compiling the Code</span></span>  
 <span data-ttu-id="7a858-114">Este exemplo requer:</span><span class="sxs-lookup"><span data-stu-id="7a858-114">This example requires:</span></span>  
  
-   <span data-ttu-id="7a858-115">Referências aos assemblies System, System.Drawing, System.Windows.Forms e System.Windows.Forms.VisualStyles.</span><span class="sxs-lookup"><span data-stu-id="7a858-115">References to the System, System.Drawing, System.Windows.Forms and System.Windows.Forms.VisualStyles assemblies.</span></span>  
  
 <span data-ttu-id="7a858-116">Para obter informações sobre como criar este exemplo da linha de comando para [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] ou [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], consulte [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) (Compilação da linha de comando) ou [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) (Compilação da linha de comando com csc.exe).</span><span class="sxs-lookup"><span data-stu-id="7a858-116">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="7a858-117">Também é possível compilar este exemplo em [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] colando o código em um novo projeto.</span><span class="sxs-lookup"><span data-stu-id="7a858-117">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="7a858-118">Consulte também [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)) (Como compilar e executar um exemplo completo de código dos Windows Forms usando o Visual Studio).</span><span class="sxs-lookup"><span data-stu-id="7a858-118">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a858-119">Consulte também</span><span class="sxs-lookup"><span data-stu-id="7a858-119">See Also</span></span>  
 [<span data-ttu-id="7a858-120">Personalizando o controle DataGridView dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7a858-120">Customizing the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="7a858-121">Arquitetura de controle DataGridView</span><span class="sxs-lookup"><span data-stu-id="7a858-121">DataGridView Control Architecture</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-architecture-windows-forms.md)  
 [<span data-ttu-id="7a858-122">Tipos de coluna no controle DataGridView dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7a858-122">Column Types in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)