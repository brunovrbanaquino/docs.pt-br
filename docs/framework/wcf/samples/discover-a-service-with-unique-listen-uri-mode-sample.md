---
title: "Descubra um serviço com exemplo de modo único de URI de escuta"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a6d35b2-0469-43c8-a0c9-63623e3d2733
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 48b49def3f8f009eeb4ffa0204e9c616b5acfec7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="discover-a-service-with-unique-listen-uri-mode-sample"></a><span data-ttu-id="049ea-102">Descubra um serviço com exemplo de modo único de URI de escuta</span><span class="sxs-lookup"><span data-stu-id="049ea-102">Discover a Service with Unique Listen Uri Mode Sample</span></span>
<span data-ttu-id="049ea-103">Este exemplo demonstra como descobrir um serviço que tem o <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> propriedade definida como <xref:System.ServiceModel.Description.ListenUriMode.Unique>.</span><span class="sxs-lookup"><span data-stu-id="049ea-103">This sample demonstrates how to discover a service that has the <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> property set to <xref:System.ServiceModel.Description.ListenUriMode.Unique>.</span></span> <span data-ttu-id="049ea-104">Quando o <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> está definida como <xref:System.ServiceModel.Description.ListenUriMode.Unique>, o ListenUri é garantido como sendo exclusivo definindo a porta a ser exclusivo ou o caminho ser exclusivo, acrescentando um GUID.</span><span class="sxs-lookup"><span data-stu-id="049ea-104">When the <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> property is set to <xref:System.ServiceModel.Description.ListenUriMode.Unique>, the ListenUri is ensured to be unique by either setting the port to be unique or for the path to be unique by appending a GUID.</span></span>  
  
### <a name="features-on-the-service"></a><span data-ttu-id="049ea-105">Recursos do serviço</span><span class="sxs-lookup"><span data-stu-id="049ea-105">Features on the Service</span></span>  
 <span data-ttu-id="049ea-106">O <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> está definida como <xref:System.ServiceModel.Description.ListenUriMode.Unique> para o ponto de extremidade TCP.</span><span class="sxs-lookup"><span data-stu-id="049ea-106">The <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> property is set to <xref:System.ServiceModel.Description.ListenUriMode.Unique> for the TCP endpoint.</span></span> <span data-ttu-id="049ea-107">O serviço é feito detectável em uma <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="049ea-107">The service is then made discoverable over a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> endpoint.</span></span>  
  
### <a name="features-on-the-client"></a><span data-ttu-id="049ea-108">Recursos no cliente</span><span class="sxs-lookup"><span data-stu-id="049ea-108">Features on the Client</span></span>  
 <span data-ttu-id="049ea-109">Esse cliente se conecta ao serviço usando o correto `Via.Uri` usando o <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> método.</span><span class="sxs-lookup"><span data-stu-id="049ea-109">This client connects to the service using the correct `Via.Uri` by using the <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> method.</span></span> <span data-ttu-id="049ea-110">O <xref:System.ServiceModel.Discovery.FindResponse> que é retornado do método é consultado para se ele contém um válido <xref:System.ServiceModel.Endpoint.ListenUri%2A> e se ele for diferente `Address.Uri`.</span><span class="sxs-lookup"><span data-stu-id="049ea-110">The <xref:System.ServiceModel.Discovery.FindResponse> that is returned from the method is then queried for whether it contains a valid <xref:System.ServiceModel.Endpoint.ListenUri%2A> and whether it is different than `Address.Uri`.</span></span> <span data-ttu-id="049ea-111">As informações apropriadas é então passadas para o `InvokeCalculatorService` método.</span><span class="sxs-lookup"><span data-stu-id="049ea-111">The appropriate information is then passed to the `InvokeCalculatorService` method.</span></span> <span data-ttu-id="049ea-112">No `InvokeCalculatorService` método, o <xref:System.ServiceModel.Endpoint.ListenUri%2A> foi passado pelo chamador, em seguida, um `ClientViaBehavior` com o nome correto `Via.Uri` é adicionado ao ponto de extremidade do cliente.</span><span class="sxs-lookup"><span data-stu-id="049ea-112">In the `InvokeCalculatorService` method, the <xref:System.ServiceModel.Endpoint.ListenUri%2A> was passed in by the caller, then a `ClientViaBehavior` with the correct `Via.Uri` is added to the client’s endpoint.</span></span>  
  
##### <a name="to-use-this-sample"></a><span data-ttu-id="049ea-113">Para usar este exemplo</span><span class="sxs-lookup"><span data-stu-id="049ea-113">To use this sample</span></span>  
  
1.  <span data-ttu-id="049ea-114">Usando [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], abra UniqueListenUriMode.sln.</span><span class="sxs-lookup"><span data-stu-id="049ea-114">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open UniqueListenUriMode.sln.</span></span>  
  
2.  <span data-ttu-id="049ea-115">Para criar a solução, pressione CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="049ea-115">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="049ea-116">Execute o aplicativo de serviço, que é gerado na pasta \service\bin\debug [diretório base de solução].</span><span class="sxs-lookup"><span data-stu-id="049ea-116">Run the service application, which is generated in the [solution base directory]\service\bin\debug folder.</span></span>  
  
4.  <span data-ttu-id="049ea-117">Execute o aplicativo cliente, que é gerado na pasta \Client\bin\debug [diretório base de solução].</span><span class="sxs-lookup"><span data-stu-id="049ea-117">Run the client application, which is generated in the [solution base directory]\Client\bin\debug folder.</span></span>  
  
     <span data-ttu-id="049ea-118">O cliente localiza o serviço em execução e grava os metadados publicados pelo ponto de extremidade do serviço no console.</span><span class="sxs-lookup"><span data-stu-id="049ea-118">The client locates the running service and writes to the console the metadata published by the service’s endpoint.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="049ea-119">Os exemplos podem já estar instalados no seu computador.</span><span class="sxs-lookup"><span data-stu-id="049ea-119">The samples may already be installed on your machine.</span></span> <span data-ttu-id="049ea-120">Verifique o seguinte diretório (padrão) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="049ea-120">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="049ea-121">Se este diretório não existir, vá para [Windows Communication Foundation (WCF) e exemplos do Windows Workflow Foundation (WF) para o .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para baixar todos os [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] exemplos.</span><span class="sxs-lookup"><span data-stu-id="049ea-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="049ea-122">Este exemplo está localizado no seguinte diretório.</span><span class="sxs-lookup"><span data-stu-id="049ea-122">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\UniqueListenUriMode`  
  
## <a name="see-also"></a><span data-ttu-id="049ea-123">Consulte também</span><span class="sxs-lookup"><span data-stu-id="049ea-123">See Also</span></span>