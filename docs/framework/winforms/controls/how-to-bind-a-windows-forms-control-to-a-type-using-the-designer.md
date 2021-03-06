---
title: Como associar um controle dos Windows Forms a um tipo usando o designer
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [Windows Forms], binding to a type
- BindingSource component [Windows Forms], binding to a type
- types [Windows Forms], binding controls to
ms.assetid: 5ab984b5-c2d0-4638-a572-1c84013e8746
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ee932e7cb4a3333ac56242e281ec64d3016746f9
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-bind-a-windows-forms-control-to-a-type-using-the-designer"></a>Como associar um controle dos Windows Forms a um tipo usando o designer
Quando estiver compilando controles que interagem com os dados, pode ser necessário associar um controle a um tipo, em vez de um objeto. Geralmente é necessário associar um controle a um tipo no tempo de design, quando os dados podem não estar disponíveis, mas ainda é recomendável fazer com que os controles associados a dados exibam dados da interface pública de um tipo. Os procedimentos a seguir demonstram como criar um novo <xref:System.Windows.Forms.BindingSource> que é associado a um tipo e como associar uma das propriedades do tipo para o <xref:System.Windows.Forms.TextBox.Text%2A> propriedade de um <xref:System.Windows.Forms.TextBox>.  
  
### <a name="to-bind-the-bindingsource-to-a-type"></a>Associar o BindingSource a um tipo  
  
1.  Criar um projeto do Windows Forms.  
  
     Para obter mais informações, consulte [Como criar um projeto de aplicativos do Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Em **Design** exibir, arraste um <xref:System.Windows.Forms.BindingSource> componente para o formulário.  
  
3.  No **propriedades** janela, clique na seta para a <xref:System.Windows.Forms.BindingSource.DataSource%2A> propriedade.  
  
4.  No **Editor de tipo de interface do usuário de DataSource**, clique em **Adicionar fonte de dados do projeto**.  
  
5.  Na página **Escolher um tipo de fonte de dados**, selecione **Objeto** e clique em **Avançar**.  
  
6.  Selecione o tipo para associar a:  
  
    -   Se o tipo ao qual você deseja associar está no projeto atual ou o assembly que contém o tipo já foi adicionado como uma referência, expanda os nós para localizar o tipo desejado e, em seguida, selecione-o.  
  
         -ou-  
  
    -   Se o tipo ao qual você deseja associar está em outro assembly, e não na lista de referências atual, clique em **Adicionar referência** e, em seguida, na guia **Projetos**. Selecione o projeto que contém o objeto comercial que você deseja e clique em **OK**. Este projeto será exibido na lista de assemblies, portanto é possível expandir os nós para encontrar o tipo desejado e, em seguida, selecioná-lo.  
  
        > [!NOTE]
        >  Se você desejar associar a um tipo em uma estrutura ou assembly Microsoft, desmarque a caixa de seleção **Ocultar assemblies que começam com Microsoft ou System**.  
  
7.  Clique em **Avançar**e em **Concluir**.  
  
### <a name="to-bind-the-control-to-the-bindingsource"></a>Associar o controle ao BindingSource  
  
1.  Adicionar uma <xref:System.Windows.Forms.TextBox> ao formulário.  
  
2.  Na janela **Propriedades**, expanda o nó **(DataBindings)**.  
  
3.  Clique na seta ao lado de <xref:System.Windows.Forms.TextBox.Text%2A> propriedade.  
  
4.  No **Editor de tipo de interface de usuário de fonte de dados**, expanda o nó para o <xref:System.Windows.Forms.BindingSource> adicionado anteriormente e selecione a propriedade do tipo associado que deseja associar ao <xref:System.Windows.Forms.TextBox.Text%2A> propriedade do <xref:System.Windows.Forms.TextBox>.  
  
## <a name="see-also"></a>Consulte também  
 [Componente BindingSource](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [Como associar um controle do Windows Forms a um tipo](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)  
 [Associar controles a dados no Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
