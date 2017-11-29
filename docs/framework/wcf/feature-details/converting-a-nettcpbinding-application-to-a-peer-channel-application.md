---
title: Convertendo um aplicativo NetTcpBinding em um aplicativo de canal par
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d4137292-a923-4b8f-8594-42276f2d3ce2
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 532171dfeba965ae30dc92f31448cf38964fc695
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="converting-a-nettcpbinding-application-to-a-peer-channel-application"></a><span data-ttu-id="4c1e9-102">Convertendo um aplicativo NetTcpBinding em um aplicativo de canal par</span><span class="sxs-lookup"><span data-stu-id="4c1e9-102">Converting a NetTcpBinding Application to a Peer Channel Application</span></span>
<span data-ttu-id="4c1e9-103">Você pode criar conexões entre os clientes que usam o [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] usando associações que descrevem os parâmetros de conexão.</span><span class="sxs-lookup"><span data-stu-id="4c1e9-103">You can create connections between clients using the [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] by using bindings that describe the parameters of the connection.</span></span> <span data-ttu-id="4c1e9-104">Convertendo um [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] aplicativo para usar conexões ponto a ponto requer uma associação que dá suporte a essa tecnologia ao fazer conexões de cliente.</span><span class="sxs-lookup"><span data-stu-id="4c1e9-104">Converting a [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] application to use peer-to-peer connections requires a binding that supports this technology when making client connections.</span></span> <span data-ttu-id="4c1e9-105">Canal par fornece uma associação chamada <xref:System.ServiceModel.NetPeerTcpBinding>, que pode ser usado de maneira semelhante para o <xref:System.ServiceModel.NetTcpBinding>.</span><span class="sxs-lookup"><span data-stu-id="4c1e9-105">Peer Channel provides a binding called <xref:System.ServiceModel.NetPeerTcpBinding>, which you can use in a similar way to the <xref:System.ServiceModel.NetTcpBinding>.</span></span> <span data-ttu-id="4c1e9-106">Principais diferenças incluem especificar um serviço de resolução e definir as configurações de segurança.</span><span class="sxs-lookup"><span data-stu-id="4c1e9-106">Key differences include specifying a resolver service and defining security settings.</span></span>  
  
 <span data-ttu-id="4c1e9-107">Se um aplicativo está usando o resolvedor padrão e as configurações de segurança, convertendo um aplicativo baseado em cliente/servidor normal para usar o canal par envolve a alteração do nome da associação de "NetTcpBinding" para "NetPeerTcpBinding" do aplicativo arquivo de configuração, você não precisa alterar a base de código do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="4c1e9-107">If an application is using the default resolver and security settings, converting a normal client/server-based application to use Peer Channel entails changing the name of the binding from "NetTcpBinding" to "NetPeerTcpBinding" in the application’s configuration file—you do not have to change the application code base.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c1e9-108">Consulte também</span><span class="sxs-lookup"><span data-stu-id="4c1e9-108">See Also</span></span>  
 [<span data-ttu-id="4c1e9-109">Criando um aplicativo de canal par</span><span class="sxs-lookup"><span data-stu-id="4c1e9-109">Building a Peer Channel Application</span></span>](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md)  
 <span data-ttu-id="4c1e9-110">[System-Provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md) (Associações fornecidas pelo sistema)</span><span class="sxs-lookup"><span data-stu-id="4c1e9-110">[System-Provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md)</span></span>