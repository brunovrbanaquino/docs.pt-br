---
title: Como criar um cliente do Windows Communication Foundation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
caps.latest.revision: "64"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0d207a067fe6d654fdd8384f1955a25c69185320
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-windows-communication-foundation-client"></a><span data-ttu-id="28d7e-102">Como criar um cliente do Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="28d7e-102">How to: Create a Windows Communication Foundation Client</span></span>
<span data-ttu-id="28d7e-103">Esta é a quarta das seis tarefas necessárias para criar um aplicativo [!INCLUDE[indigo1](../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="28d7e-103">This is the fourth of six tasks required to create a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] application.</span></span> <span data-ttu-id="28d7e-104">Para obter uma visão geral de todos os seis das tarefas, consulte o [Tutorial de Introdução](../../../docs/framework/wcf/getting-started-tutorial.md) tópico.</span><span class="sxs-lookup"><span data-stu-id="28d7e-104">For an overview of all six of the tasks, see the [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md) topic.</span></span>  
  
 <span data-ttu-id="28d7e-105">Este tópico descreve como recuperar metadados de um serviço [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] e usá-los para criar um proxy [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] que possa acessar o serviço.</span><span class="sxs-lookup"><span data-stu-id="28d7e-105">This topic describes how to retrieve metadata from a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service and use it to create a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] proxy that can access the service.</span></span> <span data-ttu-id="28d7e-106">Essa tarefa é concluída usando a funcionalidade Adicionar Referência de Serviço fornecida pelo Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="28d7e-106">This task is completed by using the Add Service Reference functionality provided by Visual Studio .</span></span> <span data-ttu-id="28d7e-107">Essa ferramenta obtém os metadados do ponto de extremidade de MEX do serviço e gera um arquivo de código-fonte gerenciado para um proxy de cliente na linguagem escolhida (por padrão, C#).</span><span class="sxs-lookup"><span data-stu-id="28d7e-107">This tool obtains the metadata from the service’s MEX endpoint and generates a managed source code file for a client proxy in the language you have chosen (C# by default).</span></span> <span data-ttu-id="28d7e-108">Além de criar o proxy de cliente, a ferramenta também cria ou atualiza o arquivo de configuração do cliente, o que permite que o aplicativo cliente se conecte ao serviço em um de seus pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="28d7e-108">In addition to creating the client proxy, the tool also creates or updates the client configuration file which enables the client application to connect to the service at one of its endpoints.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="28d7e-109">Você também pode usar o [Ferramenta Utilitária de metadados ServiceModel (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) ferramenta para gerar a classe proxy e a configuração em vez de usar Adicionar referência de serviço dentro do Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="28d7e-109">You can also use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tool to generate the proxy class and configuration instead of using Add Service Reference inside of Visual Studio.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="28d7e-110">Ao chamar um serviço [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] de um projeto de biblioteca de classes no [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] você pode usar o recurso de Adicionar Referência de Serviço para gerar automaticamente um proxy e um arquivo de configuração associado.</span><span class="sxs-lookup"><span data-stu-id="28d7e-110">When calling a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service from a class library project in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] you can use the Add Service Reference feature to automatically generate a proxy and associated configuration file.</span></span>  <span data-ttu-id="28d7e-111">O arquivo de configuração não será usado pelo projeto de biblioteca de classes.</span><span class="sxs-lookup"><span data-stu-id="28d7e-111">The configuration file will not be used by the class library project.</span></span> <span data-ttu-id="28d7e-112">Você precisará adicionar as configurações no arquivo de configuração gerado para o arquivo app.config do executável que chamará a biblioteca de classes.</span><span class="sxs-lookup"><span data-stu-id="28d7e-112">You will need to add the settings in the generated configuration file to the app.config file for the executable that will call the class library.</span></span>  
  
 <span data-ttu-id="28d7e-113">O aplicativo cliente usa a classe proxy gerada para se comunicar com o serviço.</span><span class="sxs-lookup"><span data-stu-id="28d7e-113">The client application uses the generated proxy class to communicate with the service.</span></span> <span data-ttu-id="28d7e-114">Este procedimento é descrito em [como: usar um cliente](../../../docs/framework/wcf/how-to-use-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="28d7e-114">This procedure is described in [How to: Use a Client](../../../docs/framework/wcf/how-to-use-a-wcf-client.md).</span></span>  
  
### <a name="to-create-a-windows-communication-foundation-client"></a><span data-ttu-id="28d7e-115">Para criar um cliente do Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="28d7e-115">To create a Windows Communication Foundation client</span></span>  
  
1.  <span data-ttu-id="28d7e-116">Criar um novo projeto de aplicativo de console clicando na solução Introdução, selecionar, **adicionar**, **novo projeto**.</span><span class="sxs-lookup"><span data-stu-id="28d7e-116">Create a new console application project by right-clicking on the Getting Started solution, selecting, **Add**, **New Project**.</span></span> <span data-ttu-id="28d7e-117">No **adicionar novo projeto** caixa de diálogo no lado esquerdo da caixa de diálogo Selecionar **Windows** em **c#** ou **VB**.</span><span class="sxs-lookup"><span data-stu-id="28d7e-117">In the **Add New Project** dialog on the left hand side of the dialog select **Windows** under **C#** or **VB**.</span></span> <span data-ttu-id="28d7e-118">Na seção central da caixa de diálogo Selecionar **aplicativo de Console**.</span><span class="sxs-lookup"><span data-stu-id="28d7e-118">In the center section of the dialog select **Console Application**.</span></span> <span data-ttu-id="28d7e-119">Nomeie o projeto `GettingStartedClient`.</span><span class="sxs-lookup"><span data-stu-id="28d7e-119">Name the project `GettingStartedClient`.</span></span>  
  
2.  <span data-ttu-id="28d7e-120">Definir a estrutura de destino do projeto GettingStartedClient .NET Framework 4.5, clique com o botão direito em **GettingStartedClient** no Gerenciador de soluções e selecionando **propriedades**.</span><span class="sxs-lookup"><span data-stu-id="28d7e-120">Set the target framework of the GettingStartedClient project to .NET Framework 4.5 by right clicking on **GettingStartedClient** in the Solution Explorer and selecting **Properties**.</span></span> <span data-ttu-id="28d7e-121">Na caixa suspensa rotulada **Framework de destino** selecione **.NET Framework 4.5**.</span><span class="sxs-lookup"><span data-stu-id="28d7e-121">In the dropdown box labeled **Target Framework** select **.NET Framework 4.5**.</span></span> <span data-ttu-id="28d7e-122">Configuração da estrutura de destino para um projeto VB é um pouco diferente, a caixa de diálogo de propriedades de projeto GettingStartedClient, clique o **compilar** guia no lado esquerdo da tela e, em seguida, clique no **avançado Opções de compilação** botão no canto inferior esquerdo da caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="28d7e-122">Setting the target framework for a VB project is a little different, in the GettingStartedClient project properties dialog, click the **Compile** tab on the left-hand side of the screen, and then click the **Advanced Compile Options** button at the lower left-hand corner of the dialog.</span></span> <span data-ttu-id="28d7e-123">Em seguida, selecione **.NET Framework 4.5** na caixa suspensa rotulada **Framework de destino**.</span><span class="sxs-lookup"><span data-stu-id="28d7e-123">Then select **.NET Framework 4.5** in the dropdown box labeled **Target Framework**.</span></span>  
  
     <span data-ttu-id="28d7e-124">Definir a estrutura de destino fará com que o Visual Studio 2011 recarregar a solução, pressione **Okey** quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="28d7e-124">Setting the target framework will cause Visual Studio 2011 to reload the solution, press **OK** when prompted.</span></span>  
  
3.  <span data-ttu-id="28d7e-125">Adicione uma referência a System. ServiceModel para o projeto GettingStartedClient clicando com o **referência** pasta no projeto no Gerenciador de soluções e selecione GettingStartedClient **adicionar** Referência.</span><span class="sxs-lookup"><span data-stu-id="28d7e-125">Add a reference to System.ServiceModel to the GettingStartedClient project by right-clicking the **Reference** folder under the GettingStartedClient project in Solution Explorer and select **Add** Reference.</span></span> <span data-ttu-id="28d7e-126">No **adicionar referência** caixa de diálogo Selecionar **Framework** no lado esquerdo da caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="28d7e-126">In the **Add Reference** dialog select **Framework** on the left-hand side of the dialog.</span></span> <span data-ttu-id="28d7e-127">Na caixa de texto Pesquisar Assemblies, digite `System.ServiceModel`.</span><span class="sxs-lookup"><span data-stu-id="28d7e-127">In the Search Assemblies textbox, type in `System.ServiceModel`.</span></span> <span data-ttu-id="28d7e-128">Na seção central da caixa de diálogo Selecionar **System. ServiceModel**, clique no **adicionar** botão e, em seguida, clique no **fechar** botão.</span><span class="sxs-lookup"><span data-stu-id="28d7e-128">In the center section of the dialog select **System.ServiceModel**, click the **Add** button, and click the **Close** button.</span></span> <span data-ttu-id="28d7e-129">Salve a solução clicando o **Salvar tudo** botão abaixo do menu principal.</span><span class="sxs-lookup"><span data-stu-id="28d7e-129">Save the solution by clicking the **Save All** button below the main menu.</span></span>  
  
4.  <span data-ttu-id="28d7e-130">Em seguida, você adicionará uma referência de serviço para Calculator Service.</span><span class="sxs-lookup"><span data-stu-id="28d7e-130">Next you wlll add a service reference to the Calculator Service.</span></span> <span data-ttu-id="28d7e-131">Para poder fazer isso, você deve iniciar o aplicativo de controle GettingStartedHost.</span><span class="sxs-lookup"><span data-stu-id="28d7e-131">Before you can do that, you must start up the GettingStartedHost console application.</span></span> <span data-ttu-id="28d7e-132">Quando o host estiver em execução, você pode clique com botão direito na pasta de referências no projeto GettingStartedClient no Gerenciador de soluções e selecione Adicionar referência de serviço e digite a URL a seguir na caixa de endereço da caixa de diálogo Adicionar referência de serviço: HYPERLINK "http:/ / localhost:8000/ServiceModelSamples/serviço "ServiceModelSamples/http://localhost:8000/serviço e clique no **vá** botão.</span><span class="sxs-lookup"><span data-stu-id="28d7e-132">Once the host is running you can right click the References folder under the GettingStartedClient project in the Solution Explorer and select Add Service Reference and type in the following URL in the address box of the Add Service Reference dialog:  HYPERLINK "http://localhost:8000/ServiceModelSamples/Service" http://localhost:8000/ServiceModelSamples/Service and   click the **Go** button.</span></span> <span data-ttu-id="28d7e-133">O CalculatorService deve ser exibido na caixa de listagem Serviços, clique duas vezes em CalculatorService e ele será expandido e mostrará os contratos de serviço implementados pelo serviço.</span><span class="sxs-lookup"><span data-stu-id="28d7e-133">The CalculatorService should then be displayed in the Services list box, Double click CalculatorService and it will expand and show the service contracts implemented by the service.</span></span> <span data-ttu-id="28d7e-134">Deixe o namespace padrão como está e clique no **Okey** botão.</span><span class="sxs-lookup"><span data-stu-id="28d7e-134">Leave the default namespace as is and click the **OK** button.</span></span>  
  
     <span data-ttu-id="28d7e-135">Quando você adiciona uma referência a um serviço usando o Visual Studio, um novo item aparece no Gerenciador de Soluções sob a pasta Referências de Serviço no projeto GettingStartedClient.</span><span class="sxs-lookup"><span data-stu-id="28d7e-135">When you add a reference to a service using Visual Studio a new item will appear in the Solution Explorer under the Service References folder under the GettingStartedClient project.</span></span>  <span data-ttu-id="28d7e-136">Se você usar o [Ferramenta Utilitária de metadados ServiceModel (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) ferramenta serão gerados um arquivo de código fonte e o arquivo App. config.</span><span class="sxs-lookup"><span data-stu-id="28d7e-136">If you use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tool a source code file and app.config file will be generated.</span></span>  
  
     <span data-ttu-id="28d7e-137">Você também pode usar a ferramenta de linha de comando [Ferramenta Utilitária de metadados ServiceModel (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) com as opções apropriadas para criar o código de cliente.</span><span class="sxs-lookup"><span data-stu-id="28d7e-137">You can also use the command-line tool [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) with the appropriate switches to create the client code.</span></span> <span data-ttu-id="28d7e-138">O exemplo a seguir produz um arquivo de código e um arquivo de configuração para o serviço.</span><span class="sxs-lookup"><span data-stu-id="28d7e-138">The following example generates a code file and a configuration file for the service.</span></span> <span data-ttu-id="28d7e-139">O primeiro exemplo mostra como gerar o proxy no VB e o segundo mostra como gerar o proxy no C#:</span><span class="sxs-lookup"><span data-stu-id="28d7e-139">The first example shows how to generate the proxy in VB and the second shows how to generated the proxy in C#:</span></span>  
  
    ```  
    svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/ServiceModelSamples/service  
    ```  
  
    ```csharp  
    svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/ServiceModelSamples/service  
    ```  
  
 <span data-ttu-id="28d7e-140">Agora você criou o proxy que o aplicativo cliente usará para chamar o serviço de calculadora.</span><span class="sxs-lookup"><span data-stu-id="28d7e-140">You have now created the proxy that the client application will use to call the calculator service.</span></span> <span data-ttu-id="28d7e-141">Vá para o próximo tópico na série: [como: configurar um cliente](../../../docs/framework/wcf/how-to-configure-a-basic-wcf-client.md)</span><span class="sxs-lookup"><span data-stu-id="28d7e-141">Proceed to the next topic in the series: [How to: Configure a Client](../../../docs/framework/wcf/how-to-configure-a-basic-wcf-client.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28d7e-142">Consulte também</span><span class="sxs-lookup"><span data-stu-id="28d7e-142">See Also</span></span>  
 <span data-ttu-id="28d7e-143">[ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) [Ferramenta de utilitário de metadados ServiceModel (Svcutil.exe)]</span><span class="sxs-lookup"><span data-stu-id="28d7e-143">[ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)</span></span>  
 [<span data-ttu-id="28d7e-144">Introdução</span><span class="sxs-lookup"><span data-stu-id="28d7e-144">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [<span data-ttu-id="28d7e-145">Hospedagem interna</span><span class="sxs-lookup"><span data-stu-id="28d7e-145">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)  
 [<span data-ttu-id="28d7e-146">Como: publicar metadados para um serviço usando um arquivo de configuração</span><span class="sxs-lookup"><span data-stu-id="28d7e-146">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [<span data-ttu-id="28d7e-147">Como: usar o Svcutil.exe para baixar documentos de metadados</span><span class="sxs-lookup"><span data-stu-id="28d7e-147">How to: Use Svcutil.exe to Download Metadata Documents</span></span>](../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)