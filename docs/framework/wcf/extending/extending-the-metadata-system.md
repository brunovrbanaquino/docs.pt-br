---
title: Estendendo o sistema de metadados
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- extending metadata [WCF]
ms.assetid: 8c6b3b00-61b8-4589-8fa5-546cc33719bf
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: aca7a7aba7ef4a40100e9858561d197916b71544
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="extending-the-metadata-system"></a>Estendendo o sistema de metadados
O [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] sistema de metadados é um grupo de interfaces e classes que representam os metadados necessários para implementar aplicativos baseados em serviço. Modificar ou estender as classes de ou implementar e configurar as interfaces para exportar e importar metadados personalizados, como extensões WSDL Web Services Description Language () ou asserções de WS-PolicyAttachments personalizadas.  
  
## <a name="in-this-section"></a>Nesta seção  
 [Exportando metadados personalizados para uma extensão do WCF](../../../../docs/framework/wcf/extending/exporting-custom-metadata-for-a-wcf-extension.md)  
 Descreve como implementar e usar o <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> interface incorporar declarações de política personalizada em documentos WSDL.  
  
 [Importando metadados personalizados para uma extensão do WCF](../../../../docs/framework/wcf/extending/importing-custom-metadata-for-a-wcf-extension.md)  
 Descreve como implementar e usar o <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> interface para ler e responder às declarações de política personalizada em documentos WSDL.  
  
 [Publicando e recuperando metadados através de uma associação personalizada](../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 Descreve como a troca de metadados sobre associações personalizadas.
