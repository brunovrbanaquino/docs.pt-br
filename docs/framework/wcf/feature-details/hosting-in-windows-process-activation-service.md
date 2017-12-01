---
title: "Hospedagem no serviço de ativação do processo do Windows"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: hosting services [WCF], WAS
ms.assetid: d2b9d226-15b7-41fc-8c9a-cb651ac20ecd
caps.latest.revision: "16"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d7e8d8446f9cf4f95fecba6bfc18a5432f996f9f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="hosting-in-windows-process-activation-service"></a><span data-ttu-id="b539a-102">Hospedagem no serviço de ativação do processo do Windows</span><span class="sxs-lookup"><span data-stu-id="b539a-102">Hosting in Windows Process Activation Service</span></span>
<span data-ttu-id="b539a-103">O serviço de ativação de processos do Windows (WAS) gerencia a ativação e a vida útil dos processos de trabalho que contêm aplicativos que hospedam [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] serviços.</span><span class="sxs-lookup"><span data-stu-id="b539a-103">The Windows Process Activation Service (WAS) manages the activation and lifetime of the worker processes that contain applications that host [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] services.</span></span> <span data-ttu-id="b539a-104">O modelo de processo WAS generaliza o [!INCLUDE[iis601](../../../../includes/iis601-md.md)] modelo de processo para o servidor HTTP, removendo a dependência no HTTP.</span><span class="sxs-lookup"><span data-stu-id="b539a-104">The WAS process model generalizes the [!INCLUDE[iis601](../../../../includes/iis601-md.md)] process model for the HTTP server by removing the dependency on HTTP.</span></span> <span data-ttu-id="b539a-105">Isso permite que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services para usar HTTP e protocolos não HTTP, como o Net.TCP, em um ambiente de hospedagem que oferece suporte à ativação baseada em mensagem e oferece a capacidade de hospedar um grande número de aplicativos em determinado computador.</span><span class="sxs-lookup"><span data-stu-id="b539a-105">This allows [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services to use both HTTP and non-HTTP protocols, such as Net.TCP, in a hosting environment that supports message-based activation and offers the ability to host a large number of applications on a given machine.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="b539a-106">Criando um [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] consulte de serviço que executa no WAS do ambiente de hospedagem [como: hospedar um serviço WCF em WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md).</span><span class="sxs-lookup"><span data-stu-id="b539a-106"> building a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service that runs in the WAS hosting environment, see [How to: Host a WCF Service in WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md).</span></span>  
  
 <span data-ttu-id="b539a-107">O modelo de processo WAS oferece vários recursos que permitem que os aplicativos sejam hospedados em um modo que é mais robusto, mais gerenciáveis e que usa recursos de forma eficiente:</span><span class="sxs-lookup"><span data-stu-id="b539a-107">The WAS process model provides several features that enable applications to be hosted in a way that is more robust, more manageable, and that uses resources efficiently:</span></span>  
  
-   <span data-ttu-id="b539a-108">Ativação baseada em mensagem de aplicativos e aplicativos de processo de trabalho iniciados e interrompidos dinamicamente em resposta aos itens de trabalho de entrada que chegam usando HTTP e protocolos de rede não HTTP.</span><span class="sxs-lookup"><span data-stu-id="b539a-108">Message-based activation of applications and worker process applications start and stop dynamically in response to incoming work items that arrive using HTTP and non-HTTP network protocols.</span></span>  
  
-   <span data-ttu-id="b539a-109">Aplicativo robusto e reciclagem do processo de trabalho para manter a integridade de aplicativos em execução.</span><span class="sxs-lookup"><span data-stu-id="b539a-109">Robust application and worker process recycling to maintain the health of running applications.</span></span>  
  
-   <span data-ttu-id="b539a-110">Configuração de aplicativo centralizado e gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="b539a-110">Centralized application configuration and management.</span></span>  
  
-   <span data-ttu-id="b539a-111">Permite que aplicativos tirar proveito do modelo de processo do IIS sem a necessidade do volume de implantação de uma instalação completa do IIS.</span><span class="sxs-lookup"><span data-stu-id="b539a-111">Allows applications to take advantage of the IIS process model without requiring the deployment footprint of a full IIS installation.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="b539a-112">Recursos do WAS, consulte [IIS 7.0 Beta: administração da Web do IIS 7.0](../../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md).</span><span class="sxs-lookup"><span data-stu-id="b539a-112"> WAS features, see [IIS 7.0 Beta: IIS 7.0 Web Administration](../../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md).</span></span>  
  
 <span data-ttu-id="b539a-113">[Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkId=196496) funciona com [!INCLUDE[iisver](../../../../includes/iisver-md.md)] e o serviço de ativação de processos (WAS) do Windows para fornecer aplicativos avançados de ambiente para NET4 WCF e WF Serviços de hospedagem.</span><span class="sxs-lookup"><span data-stu-id="b539a-113">[Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkId=196496) works with [!INCLUDE[iisver](../../../../includes/iisver-md.md)] and Windows Process Activation Service (WAS) to provide a rich application hosting environment for NET4 WCF and WF services.</span></span> <span data-ttu-id="b539a-114">Esses benefícios incluem gerenciamento de ciclo de vida do processo, a reciclagem do processo, hospedagem compartilhada, proteção rápida contra falha, processo deixar arquivos órfãos, ativação sob demanda e monitoramento de integridade.</span><span class="sxs-lookup"><span data-stu-id="b539a-114">These benefits include process life-cycle management, process recycling, shared hosting, rapid failure protection, process orphaning, on-demand activation, and health monitoring.</span></span> <span data-ttu-id="b539a-115">Para obter informações detalhadas, consulte [recursos de hospedagem do AppFabric](http://go.microsoft.com/fwlink/?LinkId=196494) e [conceitos de hospedagem do AppFabric](http://go.microsoft.com/fwlink/?LinkId=196495).</span><span class="sxs-lookup"><span data-stu-id="b539a-115">For detailed information, see [AppFabric Hosting Features](http://go.microsoft.com/fwlink/?LinkId=196494) and [AppFabric Hosting Concepts](http://go.microsoft.com/fwlink/?LinkId=196495).</span></span>  
  
## <a name="elements-of-the-was-addressing-model"></a><span data-ttu-id="b539a-116">Elementos do WAS do modelo de endereçamento</span><span class="sxs-lookup"><span data-stu-id="b539a-116">Elements of the WAS Addressing Model</span></span>  
 <span data-ttu-id="b539a-117">Aplicativos têm endereços de identificador de recurso uniforme (URI), que são as unidades de código cujo ambiente de tempo de vida e execução são gerenciados pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="b539a-117">Applications have Uniform Resource Identifier (URI) addresses, which are the code units whose lifetime and execution environment are managed by the server.</span></span> <span data-ttu-id="b539a-118">Pode ser uma instância de servidor único do WAS base em vários aplicativos diferentes.</span><span class="sxs-lookup"><span data-stu-id="b539a-118">A single WAS server instance can be home to many different applications.</span></span> <span data-ttu-id="b539a-119">Organizam os servidores de aplicativos em grupos chamados *sites*.</span><span class="sxs-lookup"><span data-stu-id="b539a-119">Servers organize applications into groups called *sites*.</span></span> <span data-ttu-id="b539a-120">Em um site, aplicativos são organizados de forma hierárquica que reflete a estrutura dos URIs que servem como seus endereços externos.</span><span class="sxs-lookup"><span data-stu-id="b539a-120">Within a site, applications are arranged in a hierarchical manner that reflects the structure of the URIs that serve as their external addresses.</span></span>  
  
 <span data-ttu-id="b539a-121">Endereços de aplicativo têm duas partes: um prefixo URI base e um endereço específico do aplicativo, relativo (caminho) que fornecem o endereço externo para um aplicativo quando unidas.</span><span class="sxs-lookup"><span data-stu-id="b539a-121">Application addresses have two parts: a base URI prefix and an application-specific, relative address (path), which provide the external address for an application when joined together.</span></span> <span data-ttu-id="b539a-122">O prefixo URI base é construído com a associação do site e é usado para todos os aplicativos sob o site.</span><span class="sxs-lookup"><span data-stu-id="b539a-122">The base URI prefix is constructed from the site binding and is used for all the applications under the site.</span></span> <span data-ttu-id="b539a-123">Endereços de aplicativo, em seguida, são construídos colocando os fragmentos de caminho específico do aplicativo (como "/ applicationOne") e anexando-los para o prefixo URI base (por exemplo, "net.tcp://localhost") para chegar ao URI do aplicativo completo.</span><span class="sxs-lookup"><span data-stu-id="b539a-123">Application addresses are then constructed by taking application-specific path fragments (such as, "/applicationOne") and appending them to the base URI prefix (for example, "net.tcp://localhost") to arrive at the full application URI.</span></span>  
  
 <span data-ttu-id="b539a-124">A tabela a seguir ilustra vários cenários possíveis de endereçamento para sites do WAS com HTTP e associações de site não HTTP.</span><span class="sxs-lookup"><span data-stu-id="b539a-124">The following table illustrates several possible addressing scenarios for WAS sites with both HTTP and non-HTTP site bindings.</span></span>  
  
|<span data-ttu-id="b539a-125">Cenário</span><span class="sxs-lookup"><span data-stu-id="b539a-125">Scenario</span></span>|<span data-ttu-id="b539a-126">Associações de site</span><span class="sxs-lookup"><span data-stu-id="b539a-126">Site bindings</span></span>|<span data-ttu-id="b539a-127">Caminho do aplicativo</span><span class="sxs-lookup"><span data-stu-id="b539a-127">Application path</span></span>|<span data-ttu-id="b539a-128">URIs de aplicativo básico</span><span class="sxs-lookup"><span data-stu-id="b539a-128">Base application URIs</span></span>|  
|--------------|-------------------|----------------------|---------------------------|  
|<span data-ttu-id="b539a-129">HTTP apenas</span><span class="sxs-lookup"><span data-stu-id="b539a-129">HTTP Only</span></span>|<span data-ttu-id="b539a-130">http: *: 80:\*</span><span class="sxs-lookup"><span data-stu-id="b539a-130">http: *:80:\*</span></span>|<span data-ttu-id="b539a-131">/appTwo</span><span class="sxs-lookup"><span data-stu-id="b539a-131">/appTwo</span></span>|<span data-ttu-id="b539a-132">http://localhost/appTwo/</span><span class="sxs-lookup"><span data-stu-id="b539a-132">http://localhost/appTwo/</span></span>|  
|<span data-ttu-id="b539a-133">HTTP e não HTTP</span><span class="sxs-lookup"><span data-stu-id="b539a-133">Both HTTP and Non-HTTP</span></span>|<span data-ttu-id="b539a-134">http: *: 80:\*</span><span class="sxs-lookup"><span data-stu-id="b539a-134">http: *:80:\*</span></span><br /><br /> <span data-ttu-id="b539a-135">NET. TCP: 808:\*</span><span class="sxs-lookup"><span data-stu-id="b539a-135">net.tcp: 808:\*</span></span>|<span data-ttu-id="b539a-136">/appTwo</span><span class="sxs-lookup"><span data-stu-id="b539a-136">/appTwo</span></span>|<span data-ttu-id="b539a-137">http://localhost/appTwo/</span><span class="sxs-lookup"><span data-stu-id="b539a-137">http://localhost/appTwo/</span></span><br /><span data-ttu-id="b539a-138">NET.TCP://localhost/appTwo/</span><span class="sxs-lookup"><span data-stu-id="b539a-138">net.tcp://localhost/appTwo/</span></span>|  
|<span data-ttu-id="b539a-139">Diferente de HTTP apenas</span><span class="sxs-lookup"><span data-stu-id="b539a-139">Non-HTTP only</span></span>|<span data-ttu-id="b539a-140">NET. pipe: *</span><span class="sxs-lookup"><span data-stu-id="b539a-140">net.pipe: *</span></span>|<span data-ttu-id="b539a-141">/appThree</span><span class="sxs-lookup"><span data-stu-id="b539a-141">/appThree</span></span>|<span data-ttu-id="b539a-142">NET.pipe://appThree/</span><span class="sxs-lookup"><span data-stu-id="b539a-142">net.pipe://appThree/</span></span>|  
  
 <span data-ttu-id="b539a-143">Serviços e recursos em um aplicativo também podem ser resolvidos.</span><span class="sxs-lookup"><span data-stu-id="b539a-143">Services and resources within an application can also be addressed.</span></span> <span data-ttu-id="b539a-144">Dentro de um aplicativo, os recursos de aplicativo são endereçados relativo ao caminho base do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b539a-144">Within an application, application resources are addressed relative to the base application path.</span></span> <span data-ttu-id="b539a-145">Por exemplo, suponha que um site em um nome de máquina contoso.com tem associações de site para protocolos HTTP e Net.TCP.</span><span class="sxs-lookup"><span data-stu-id="b539a-145">For example, assume that a site on a machine name contoso.com has site bindings for both the HTTP and Net.TCP protocols.</span></span> <span data-ttu-id="b539a-146">Suponha também que o site contém um aplicativo localizado em /Billing, que expõe um serviço em GetOrders.svc.</span><span class="sxs-lookup"><span data-stu-id="b539a-146">Also assume that the site contains one application located at /Billing, which exposes a service at GetOrders.svc.</span></span> <span data-ttu-id="b539a-147">Em seguida, se o serviço GetOrders.svc exposto a um ponto de extremidade com um endereço relativo da SecureEndpoint, o ponto de extremidade de serviço deve ser exposto nos URIs a seguir:</span><span class="sxs-lookup"><span data-stu-id="b539a-147">Then, if the GetOrders.svc service exposed an endpoint with a relative address of SecureEndpoint, the service endpoint would be exposed at the following two URIs:</span></span>  
  
 <span data-ttu-id="b539a-148">http://contoso.com/Billing/GetOrders.svc/SecureEndpoint</span><span class="sxs-lookup"><span data-stu-id="b539a-148">http://contoso.com/Billing/GetOrders.svc/SecureEndpoint</span></span>  
<span data-ttu-id="b539a-149">NET.TCP://contoso.com/Billing/GetOrders.svc/SecureEndpoint</span><span class="sxs-lookup"><span data-stu-id="b539a-149">net.tcp://contoso.com/Billing/GetOrders.svc/SecureEndpoint</span></span>  
  
## <a name="the-was-runtime"></a><span data-ttu-id="b539a-150">O WAS em tempo de execução</span><span class="sxs-lookup"><span data-stu-id="b539a-150">The WAS Runtime</span></span>  
 <span data-ttu-id="b539a-151">Aplicativos são organizados em sites para fins de endereçamento e gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="b539a-151">Applications are organized into sites for the purposes of addressing and management.</span></span> <span data-ttu-id="b539a-152">Em tempo de execução aplicativos também são agrupados juntos em pools de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="b539a-152">At run time, applications are also grouped together into application pools.</span></span> <span data-ttu-id="b539a-153">Um pool de aplicativos pode hospedar vários aplicativos diferentes de vários sites diferentes.</span><span class="sxs-lookup"><span data-stu-id="b539a-153">An application pool can house many different applications from many different sites.</span></span> <span data-ttu-id="b539a-154">Todos os aplicativos dentro de um pool de aplicativos compartilham um conjunto comum de características de tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="b539a-154">All of the applications inside an application pool share a common set of run-time characteristics.</span></span> <span data-ttu-id="b539a-155">Por exemplo, todos executados sob a mesma versão do common language runtime (CLR) e todos eles compartilham uma identidade de processo comum.</span><span class="sxs-lookup"><span data-stu-id="b539a-155">For example, they all run under the same version of the common language runtime (CLR) and they all share a common process identity.</span></span> <span data-ttu-id="b539a-156">Cada pool de aplicativos corresponde a uma instância de um processo de trabalho (w3wp.exe).</span><span class="sxs-lookup"><span data-stu-id="b539a-156">Each application pool corresponds to an instance of a worker process (w3wp.exe).</span></span> <span data-ttu-id="b539a-157">Cada aplicativo gerenciado em execução dentro de um pool de aplicativo compartilhado é isolado de outros aplicativos por meio de um AppDomain do CLR.</span><span class="sxs-lookup"><span data-stu-id="b539a-157">Each managed application running inside of a shared application pool is isolated from other applications by means of a CLR AppDomain.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b539a-158">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b539a-158">See Also</span></span>  
 [<span data-ttu-id="b539a-159">ARQUITETURA de ativação</span><span class="sxs-lookup"><span data-stu-id="b539a-159">WAS Activation Architecture</span></span>](../../../../docs/framework/wcf/feature-details/was-activation-architecture.md)  
 [<span data-ttu-id="b539a-160">Configurando o WAS para utilização com o WCF</span><span class="sxs-lookup"><span data-stu-id="b539a-160">Configuring WAS for Use with WCF</span></span>](../../../../docs/framework/wcf/feature-details/configuring-the-wpa--service-for-use-with-wcf.md)  
 [<span data-ttu-id="b539a-161">Como: instalar e configurar os componentes de ativação do WCF</span><span class="sxs-lookup"><span data-stu-id="b539a-161">How to: Install and Configure WCF Activation Components</span></span>](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md)  
 [<span data-ttu-id="b539a-162">Como hospedar um serviço do WCF no WAS</span><span class="sxs-lookup"><span data-stu-id="b539a-162">How to: Host a WCF Service in WAS</span></span>](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md)  
 [<span data-ttu-id="b539a-163">Recursos de hospedagem do Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="b539a-163">Windows Server App Fabric Hosting Features</span></span>](http://go.microsoft.com/fwlink/?LinkId=201276)