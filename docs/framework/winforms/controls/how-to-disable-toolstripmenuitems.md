---
title: Como desabilitar ToolStripMenuItems
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
- ToolStripMenuItems [Windows Forms], enabling
- ToolStripMenuItems [Windows Forms], disabling
- menu items [Windows Forms], disabling
- disabling menu items
- menu items [Windows Forms], enabling
- menus [Windows Forms], disabling menu items
ms.assetid: bcc1da84-50fd-41d2-8475-103b581d5654
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e3307da3e0810ea775c799a4b065e1f7484b5779
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-disable-toolstripmenuitems"></a><span data-ttu-id="9c4be-102">Como desabilitar ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="9c4be-102">How to: Disable ToolStripMenuItems</span></span>
<span data-ttu-id="9c4be-103">Você pode limitar ou ampliar os comandos que um usuário pode fazer ao habilitar e desabilitar itens de menu em resposta a atividades do usuário.</span><span class="sxs-lookup"><span data-stu-id="9c4be-103">You can limit or broaden the commands a user may make by enabling and disabling menu items in response to user activities.</span></span> <span data-ttu-id="9c4be-104">Itens de menu são habilitados por padrão, quando eles são criados, mas isso pode ser ajustado por meio de <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> propriedade.</span><span class="sxs-lookup"><span data-stu-id="9c4be-104">Menu items are enabled by default when they are created, but this can be adjusted through the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property.</span></span> <span data-ttu-id="9c4be-105">Você pode manipular essa propriedade em tempo de design na janela **Propriedades** ou programaticamente configurando ela no código.</span><span class="sxs-lookup"><span data-stu-id="9c4be-105">You can manipulate this property at design time in the **Properties** window or programmatically by setting it in code.</span></span>  
  
### <a name="to-disable-a-menu-item-programmatically"></a><span data-ttu-id="9c4be-106">Para desabilitar um item de menu programaticamente</span><span class="sxs-lookup"><span data-stu-id="9c4be-106">To disable a menu item programmatically</span></span>  
  
-   <span data-ttu-id="9c4be-107">Dentro do método onde você define as propriedades do item de menu, adicione código para definir o <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> propriedade `false`.</span><span class="sxs-lookup"><span data-stu-id="9c4be-107">Within the method where you set the properties of the menu item, add code to set the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property to `false`.</span></span>  
  
    ```vb  
    MenuItem1.Enabled = False  
    ```  
  
    ```csharp  
    menuItem1.Enabled = false;  
    ```  
  
    ```cpp  
    menuItem1->Enabled = false;  
    ```  
  
    > [!TIP]
    >  <span data-ttu-id="9c4be-108">Desabilitar o item de menu de nível superior ou primeiro em um menu oculta todos os itens de menu contidos no menu, mas não desabilitá-las.</span><span class="sxs-lookup"><span data-stu-id="9c4be-108">Disabling the first or top-level menu item in a menu hides all the menu items contained within the menu, but does not disable them.</span></span> <span data-ttu-id="9c4be-109">Da mesma forma, a desabilitação de um item de menu que tem itens de submenu oculta os itens de submenu, mas não desabilitá-las.</span><span class="sxs-lookup"><span data-stu-id="9c4be-109">Likewise, disabling a menu item that has submenu items hides the submenu items, but does not disable them.</span></span> <span data-ttu-id="9c4be-110">Se todos os comandos em um determinado menu estiverem indisponíveis para o usuário, ocultar e desabilitar todo o menu será considerado uma boa prática de programação, pois isso apresenta uma interface do usuário mais enxuta.</span><span class="sxs-lookup"><span data-stu-id="9c4be-110">If all the commands on a given menu are unavailable to the user, it is considered good programming practice to both hide and disable the entire menu, as this presents a clean user interface.</span></span> <span data-ttu-id="9c4be-111">Você deve ocultar e desabilitar o menu e desative a cada item e o item de submenu no menu, porque ocultando sozinho não impede o acesso a um comando de menu por meio de uma tecla de atalho.</span><span class="sxs-lookup"><span data-stu-id="9c4be-111">You should hide and disable the menu, and disable every item and submenu item in the menu, because hiding alone does not prevent access to a menu command via a shortcut key.</span></span> <span data-ttu-id="9c4be-112">Definir o <xref:System.Windows.Forms.ToolStripItem.Visible%2A> propriedade de um item de menu de nível superior para `false` para ocultar o menu inteiro.</span><span class="sxs-lookup"><span data-stu-id="9c4be-112">Set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of a top-level menu item to `false` to hide the entire menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c4be-113">Consulte também</span><span class="sxs-lookup"><span data-stu-id="9c4be-113">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [<span data-ttu-id="9c4be-114">Como ocultar ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="9c4be-114">How to: Hide ToolStripMenuItems</span></span>](../../../../docs/framework/winforms/controls/how-to-hide-toolstripmenuitems.md)  
 [<span data-ttu-id="9c4be-115">Visão geral do controle MenuStrip</span><span class="sxs-lookup"><span data-stu-id="9c4be-115">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)