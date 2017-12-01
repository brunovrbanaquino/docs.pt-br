---
title: "Usando o escopo de edição"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 79306f9e-318b-4687-9863-8b93d1841716
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6aec54cef13bcd99fb65a6305e086fe577b6bc13
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="using-editing-scope"></a><span data-ttu-id="9122a-102">Usando o escopo de edição</span><span class="sxs-lookup"><span data-stu-id="9122a-102">Using Editing Scope</span></span>
<span data-ttu-id="9122a-103">Este exemplo demonstra como em lotes um conjunto de alterações de modo que eles possam ser desfeitos em uma única unidade atômica.</span><span class="sxs-lookup"><span data-stu-id="9122a-103">This sample demonstrates how to batch a set of changes so that they can be undone in a single atomic unit.</span></span> <span data-ttu-id="9122a-104">Por padrão, as ações executadas por um autor do designer de atividade automaticamente são integradas desfazer/refazem o sistema.</span><span class="sxs-lookup"><span data-stu-id="9122a-104">By default, the actions taken by an activity designer author are automatically integrated into the Undo/Redo system.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="9122a-105">Demonstra</span><span class="sxs-lookup"><span data-stu-id="9122a-105">Demonstrates</span></span>  
 <span data-ttu-id="9122a-106">Edite o escopo e desfaz e refaz.</span><span class="sxs-lookup"><span data-stu-id="9122a-106">Editing scope and Undo and Redo.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="9122a-107">Discussão</span><span class="sxs-lookup"><span data-stu-id="9122a-107">Discussion</span></span>  
 <span data-ttu-id="9122a-108">Este exemplo demonstra como em lotes um conjunto de alterações na árvore de <xref:System.Activities.Presentation.Model.ModelItem> em uma única unidade de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9122a-108">This sample demonstrates how to batch a set of changes to the <xref:System.Activities.Presentation.Model.ModelItem> tree within a single unit of work.</span></span> <span data-ttu-id="9122a-109">Observe que ao associar aos valores de <xref:System.Activities.Presentation.Model.ModelItem> diretamente de um designer de WPF, as alterações serão aplicadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="9122a-109">Note that when binding to <xref:System.Activities.Presentation.Model.ModelItem> values directly from a WPF designer, changes are applied automatically.</span></span> <span data-ttu-id="9122a-110">Este exemplo demonstra o que deve ser feito quando várias alterações a ser agrupadas estão sendo feitas com o código obrigatório, em vez de uma única alteração.</span><span class="sxs-lookup"><span data-stu-id="9122a-110">This sample demonstrates what must be done when multiple changes to be batched are being made through imperative code, rather than a single change.</span></span>  
  
 <span data-ttu-id="9122a-111">Nesse exemplo, três atividades são adicionadas.</span><span class="sxs-lookup"><span data-stu-id="9122a-111">In this sample, three activities are added.</span></span> <span data-ttu-id="9122a-112">Quando editar começa, <xref:System.Activities.Presentation.Model.ModelItem.BeginEdit%2A> é chamado uma instância de <xref:System.Activities.Presentation.Model.ModelItem>.</span><span class="sxs-lookup"><span data-stu-id="9122a-112">When editing begins, <xref:System.Activities.Presentation.Model.ModelItem.BeginEdit%2A> is called on an instance of <xref:System.Activities.Presentation.Model.ModelItem>.</span></span> <span data-ttu-id="9122a-113">As alterações feitas na árvore de <xref:System.Activities.Presentation.Model.ModelItem> dentro desse escopo de edição são agrupadas.</span><span class="sxs-lookup"><span data-stu-id="9122a-113">Changes made to the <xref:System.Activities.Presentation.Model.ModelItem> tree within this editing scope are batched.</span></span> <span data-ttu-id="9122a-114">O comando de <xref:System.Activities.Presentation.Model.ModelItem.BeginEdit%2A> retorna <xref:System.Activities.Presentation.Model.EditingScope>, que podem ser usados para controlar essa instância.</span><span class="sxs-lookup"><span data-stu-id="9122a-114">The <xref:System.Activities.Presentation.Model.ModelItem.BeginEdit%2A> command returns an <xref:System.Activities.Presentation.Model.EditingScope>, which can be used to control this instance.</span></span> <span data-ttu-id="9122a-115"><xref:System.Activities.Presentation.Model.EditingScope.OnComplete%2A> ou <xref:System.Activities.Presentation.Model.EditingScope.OnRevert%2A> podem ser chamados a confirmação ou reverter o escopo de edição.</span><span class="sxs-lookup"><span data-stu-id="9122a-115">Either <xref:System.Activities.Presentation.Model.EditingScope.OnComplete%2A> or <xref:System.Activities.Presentation.Model.EditingScope.OnRevert%2A> can be called to either commit or revert the editing scope.</span></span>  
  
 <span data-ttu-id="9122a-116">Você também pode aninhar objetos de <xref:System.Activities.Presentation.Model.EditingScope> , que permite vários conjuntos de alterações ser controlado como parte de um escopo maior de edição e pode ser controlado individualmente.</span><span class="sxs-lookup"><span data-stu-id="9122a-116">You can also nest <xref:System.Activities.Presentation.Model.EditingScope> objects, which allows for multiple sets of changes to be tracked as part of a larger editing scope and can be controlled individually.</span></span> <span data-ttu-id="9122a-117">Um cenário que pode usar esse recurso seria quando as alterações de várias caixas de diálogo devem ser adicionadas ou revertido separada, com as alterações que estão sendo tratados como uma única operação atômica.</span><span class="sxs-lookup"><span data-stu-id="9122a-117">A scenario that may use this feature would be when changes from multiple dialogs must be committed or reverted separately, with all changes being treated as a single atomic operation.</span></span> <span data-ttu-id="9122a-118">Nesse exemplo, os escopos de edição são empilhados usando <xref:System.Collections.ObjectModel.ObservableCollection%601> de tipo <xref:System.Activities.Presentation.Model.ModelEditingScope>.</span><span class="sxs-lookup"><span data-stu-id="9122a-118">In this sample, the editing scopes are stacked using an <xref:System.Collections.ObjectModel.ObservableCollection%601> of type <xref:System.Activities.Presentation.Model.ModelEditingScope>.</span></span> <span data-ttu-id="9122a-119"><xref:System.Collections.ObjectModel.ObservableCollection%601> é utilizado para que a profundidade de aninhamento pode ser observada na superfície de designer.</span><span class="sxs-lookup"><span data-stu-id="9122a-119">The <xref:System.Collections.ObjectModel.ObservableCollection%601> is used so that the depth of the nesting can be observed on the designer surface.</span></span>  
  
## <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="9122a-120">Para configurar, compilar, e executar o exemplo</span><span class="sxs-lookup"><span data-stu-id="9122a-120">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="9122a-121">Compilar e executar o exemplo, e depois use os botões à esquerda para alterar o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9122a-121">Build and run the sample, and then use the buttons on the left to modify the workflow.</span></span>  
  
2.  <span data-ttu-id="9122a-122">Clique em **abrir Editar escopo**.</span><span class="sxs-lookup"><span data-stu-id="9122a-122">Click **Open Editing Scope**.</span></span>  
  
    1.  <span data-ttu-id="9122a-123">Este comando chama <xref:System.Activities.Presentation.Model.ModelItem.BeginEdit%2A> que cria um escopo e envia de edição ele na pilha de edição.</span><span class="sxs-lookup"><span data-stu-id="9122a-123">This command calls <xref:System.Activities.Presentation.Model.ModelItem.BeginEdit%2A> that creates an editing scope and pushes it onto the editing stack.</span></span>  
  
    2.  <span data-ttu-id="9122a-124">Três atividades são adicionadas a <xref:System.Activities.Presentation.Model.ModelItem>selecionado.</span><span class="sxs-lookup"><span data-stu-id="9122a-124">Three activities are then added to the selected <xref:System.Activities.Presentation.Model.ModelItem>.</span></span> <span data-ttu-id="9122a-125">Observe que se o escopo de edição não tivesse sido aberto com <xref:System.Activities.Presentation.Model.ModelItem.BeginEdit%2A>, três novas atividades apareceriam na tela de designer.</span><span class="sxs-lookup"><span data-stu-id="9122a-125">Note that if the editing scope had not been opened with <xref:System.Activities.Presentation.Model.ModelItem.BeginEdit%2A>, three new activities would appear on the designer canvas.</span></span> <span data-ttu-id="9122a-126">Porque esta operação ainda está pendente dentro de <xref:System.Activities.Presentation.Model.EditingScope>, o designer não é atualizada ainda.</span><span class="sxs-lookup"><span data-stu-id="9122a-126">Because this operation is still pending within the <xref:System.Activities.Presentation.Model.EditingScope>, the designer is not yet updated.</span></span>  
  
3.  <span data-ttu-id="9122a-127">Pressione **escopo de edição fechar** para confirmar o escopo de edição.</span><span class="sxs-lookup"><span data-stu-id="9122a-127">Press **Close Editing Scope** to commit the editing scope.</span></span> <span data-ttu-id="9122a-128">Três atividades aparecem no designer.</span><span class="sxs-lookup"><span data-stu-id="9122a-128">Three activities appear in the designer.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9122a-129">Os exemplos podem já estar instalados no seu computador.</span><span class="sxs-lookup"><span data-stu-id="9122a-129">The samples may already be installed on your machine.</span></span> <span data-ttu-id="9122a-130">Verifique o seguinte diretório (padrão) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="9122a-130">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="9122a-131">Se este diretório não existir, vá para [Windows Communication Foundation (WCF) e exemplos do Windows Workflow Foundation (WF) para o .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para baixar todos os [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] exemplos.</span><span class="sxs-lookup"><span data-stu-id="9122a-131">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9122a-132">Este exemplo está localizado no seguinte diretório.</span><span class="sxs-lookup"><span data-stu-id="9122a-132">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\UsingEditingScope`