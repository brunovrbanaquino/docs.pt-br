---
title: Publicando pontos de extremidade de metadados
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 29cd8a60-dfb7-460c-bf5a-c2b31b782671
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7f4d7d99304df1622f482a827d67d389760bf76d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="publishing-metadata-endpoints"></a>Publicando pontos de extremidade de metadados
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)]Serviços de publicar metadados por um ou mais pontos de extremidade de metadados de publicação. Metadados de serviço de publicação disponibiliza os metadados usando protocolos padronizados, como solicitações de WS-MetadataExchange (MEX) e HTTP/GET. Pontos de extremidade de metadados são semelhantes aos outros pontos de extremidade de serviço que têm um endereço, uma ligação e um contrato e podem ser adicionadas a um host de serviço por meio de configuração ou em código. Para habilitar a publicação pontos de extremidade de metadados, você deve adicionar o <xref:System.ServiceModel.Description.ServiceMetadataBehavior> comportamento para o serviço de serviço.  
  
## <a name="in-this-section"></a>Nesta seção  
 [Como publicar metadados para um serviço usando um arquivo de configuração](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 Demonstra como configurar um [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] serviço para publicar metadados, de forma que os clientes podem recuperar os metadados usando um WS-MetadataExchange ou uma solicitação HTTP/GET usando o `?wsdl` cadeia de caracteres de consulta.  
  
 [Como publicar metadados para um serviço utilizando código](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 Demonstra como habilitar a publicação de metadados para um [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] no código de serviço para que os clientes podem recuperar os metadados usando um WS-MetadataExchange ou uma solicitação HTTP/GET usando o `?wsdl` cadeia de caracteres de consulta.  
  
## <a name="see-also"></a>Consulte também  
 [Publicando metadados](../../../docs/framework/wcf/feature-details/publishing-metadata.md)
