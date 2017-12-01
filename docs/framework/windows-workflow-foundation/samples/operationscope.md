---
title: OperationScope
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 56206a21-1e63-422d-b92a-e5d8b713e707
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b90ab7e38f40cb515166d4d08e0316ffb9061be3
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2017
---
# <a name="operationscope"></a><span data-ttu-id="cc3c9-102">OperationScope</span><span class="sxs-lookup"><span data-stu-id="cc3c9-102">OperationScope</span></span>
<span data-ttu-id="cc3c9-103">Este exemplo demonstra como as atividades, <xref:System.ServiceModel.Activities.Receive> e <xref:System.ServiceModel.Activities.SendReply> de mensagens podem ser usados para expor uma atividade personalizado existente como uma operação em um serviço de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="cc3c9-103">This sample demonstrates how the messaging activities, <xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply> can be used to expose an existing custom activity as an operation in a workflow service.</span></span> <span data-ttu-id="cc3c9-104">Este exemplo inclui uma nova atividade personalizado chamada `OperationScope`.</span><span class="sxs-lookup"><span data-stu-id="cc3c9-104">This sample includes a new custom activity called an `OperationScope`.</span></span> <span data-ttu-id="cc3c9-105">Se destina a tornar o desenvolvimento de um serviço de fluxo de trabalho permitir que os usuários criarem o corpo das operações separadamente como atividades personalizados e então facilmente expostos como as operações de serviço usando a atividade de `OperationScope` .</span><span class="sxs-lookup"><span data-stu-id="cc3c9-105">It is intended to ease the development of a workflow service by allowing users to author the body of their operations separately as custom activities and then easily exposing them as service operations using the `OperationScope` activity.</span></span> <span data-ttu-id="cc3c9-106">Por exemplo, uma atividade personalizado de `Add` que aceita dois argumentos e retornos de `in` um argumento de `out` pode ser exposta como uma operação de `Add` no serviço de fluxo de trabalho soltando na `OperationScope`.</span><span class="sxs-lookup"><span data-stu-id="cc3c9-106">For example, a custom `Add` activity that takes two `in` arguments and returns one `out` argument could be exposed as an `Add` operation on the workflow service by dropping it into an `OperationScope`.</span></span>  
  
 <span data-ttu-id="cc3c9-107">O escopo inspecionando a atividade fornecida como o corpo.</span><span class="sxs-lookup"><span data-stu-id="cc3c9-107">The scope works by inspecting the activity provided as its body.</span></span> <span data-ttu-id="cc3c9-108">Todos os argumentos desatados de `in` são considerados para ser entradas de mensagens de entrada.</span><span class="sxs-lookup"><span data-stu-id="cc3c9-108">Any unbound `in` arguments are assumed to be inputs from the incoming message.</span></span> <span data-ttu-id="cc3c9-109">Todos os argumentos de `out` , independentemente se estão associados, são considerados para ser saída na mensagem subsequente de resposta.</span><span class="sxs-lookup"><span data-stu-id="cc3c9-109">All `out` arguments, regardless of whether they are bound, are assumed to be outputs in the subsequent reply message.</span></span> <span data-ttu-id="cc3c9-110">O nome da operação expõe é tirado de nome para exibição de atividade de `OperationScope` .</span><span class="sxs-lookup"><span data-stu-id="cc3c9-110">The exposed operation’s name is taken from the display name of the `OperationScope` activity.</span></span> <span data-ttu-id="cc3c9-111">O resultado final é que a atividade de corpo está envolvida em <xref:System.ServiceModel.Activities.Receive> e em <xref:System.ServiceModel.Activities.SendReply> com os parâmetros de mensagens associadas a atividade de argumentos.</span><span class="sxs-lookup"><span data-stu-id="cc3c9-111">The end result is that the body activity is wrapped in a <xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply> with the parameters from the messages bound to the arguments of the activity.</span></span>  
  
 <span data-ttu-id="cc3c9-112">Este exemplo exibe um serviço de fluxo de trabalho usando pontos de extremidade HTTP.</span><span class="sxs-lookup"><span data-stu-id="cc3c9-112">This sample exposes a workflow service using HTTP endpoints.</span></span> <span data-ttu-id="cc3c9-113">Para executar, o URL apropriado ACLs deve ser adicionado.</span><span class="sxs-lookup"><span data-stu-id="cc3c9-113">To run, proper URL ACLs must be added.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="cc3c9-114">[Configurando HTTP e HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353).</span><span class="sxs-lookup"><span data-stu-id="cc3c9-114"> [Configuring HTTP and HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353).</span></span> <span data-ttu-id="cc3c9-115">Executando o seguinte comando em um prompt elevado adiciona as ACLs corretas (certifique-se de que seu nome de usuário e domínio são substituídos por domínio %\\% UserName %).</span><span class="sxs-lookup"><span data-stu-id="cc3c9-115">Executing the following command at an elevated prompt adds the appropriate ACLs (ensure that your Domain and Username are substituted for %DOMAIN%\\%UserName%).</span></span>  
  
 <span data-ttu-id="cc3c9-116">**Netsh http adicionar url urlacl = http: / / +: 8000 / usuário = % domínio %\\% UserName %**</span><span class="sxs-lookup"><span data-stu-id="cc3c9-116">**netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\\%UserName%**</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="cc3c9-117">Para executar a amostra</span><span class="sxs-lookup"><span data-stu-id="cc3c9-117">To run the sample</span></span>  
  
1.  <span data-ttu-id="cc3c9-118">Abra a solução de OperationScope.sln em [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc3c9-118">Open the OperationScope.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="cc3c9-119">Definir vários projetos de inicialização, clicando duas vezes a solução no Gerenciador de soluções e selecionando **definir projetos de inicialização**.</span><span class="sxs-lookup"><span data-stu-id="cc3c9-119">Set multiple start-up projects by right-clicking the solution in Solution Explorer and selecting **Set Startup Projects**.</span></span> <span data-ttu-id="cc3c9-120">Adicione o cenário e o Scenario_Client (nessa ordem) como vários projetos inicialização.</span><span class="sxs-lookup"><span data-stu-id="cc3c9-120">Add Scenario and Scenario_Client (in that order) as multiple start-up projects.</span></span>  
  
3.  <span data-ttu-id="cc3c9-121">Pressione CTRL+SHIFT+B para criar a solução.</span><span class="sxs-lookup"><span data-stu-id="cc3c9-121">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="cc3c9-122">Essa etapa é necessária para exibir o fluxo de trabalho BankService.xaml devido à atividade personalizado `OperationScope`.</span><span class="sxs-lookup"><span data-stu-id="cc3c9-122">This step is required to view the BankService.xaml workflow due to the custom activity `OperationScope`.</span></span>  
  
4.  <span data-ttu-id="cc3c9-123">Pressione CTRL+F5 para executar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="cc3c9-123">Press CTRL+F5 to run the application.</span></span> <span data-ttu-id="cc3c9-124">O console de Scenario_Client solicitará entrada e saída correspondentes são considerados no console de cenário.</span><span class="sxs-lookup"><span data-stu-id="cc3c9-124">The Scenario_Client console prompts you for inputs and the corresponding output is seen in the Scenario console.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cc3c9-125">Os exemplos podem já estar instalados no seu computador.</span><span class="sxs-lookup"><span data-stu-id="cc3c9-125">The samples may already be installed on your machine.</span></span> <span data-ttu-id="cc3c9-126">Verifique o seguinte diretório (padrão) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="cc3c9-126">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="cc3c9-127">Se este diretório não existir, vá para [Windows Communication Foundation (WCF) e exemplos do Windows Workflow Foundation (WF) para o .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para baixar todos os [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] exemplos.</span><span class="sxs-lookup"><span data-stu-id="cc3c9-127">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="cc3c9-128">Este exemplo está localizado no seguinte diretório.</span><span class="sxs-lookup"><span data-stu-id="cc3c9-128">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\OperationScope`