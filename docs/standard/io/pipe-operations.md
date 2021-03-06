---
title: "Operações de pipe no .NET Framework"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipes [.NET Framework]
- pipe operations [.NET Framework]
- interprocess communication [.NET Framework], pipes
- I/O [.NET Framework], pipes
ms.assetid: 7b964ebd-7a4f-4d28-8194-7841f9e4c702
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 68c1ad34952ee4d20dbf56aa8ca437a3f99db751
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/23/2017
---
# <a name="pipe-operations-in-the-net-framework"></a>Operações de pipe no .NET Framework
Os pipes fornecem um meio de comunicação entre processos. Existem dois tipos de pipes:  
  
-   Pipes anônimos.  
  
     Os pipes anônimos fornecem comunicação entre processos em um computador local. Os pipes anônimos exigem menos sobrecarga do que os pipes nomeados mas oferecem serviços limitados. Os pipes anônimos são unidirecionais e não podem ser usados em uma rede. Eles oferecem suporte a apenas uma única instância de servidor. Os pipes anônimos são úteis para a comunicação entre threads ou entre processos pai e filho em que os identificadores de pipe podem ser facilmente passados para o processo filho quando ele é criado.  
  
     No .NET Framework, você implementa pipes anônimos usando as classes <xref:System.IO.Pipes.AnonymousPipeServerStream> e <xref:System.IO.Pipes.AnonymousPipeClientStream>.  
  
     Veja [Como usar pipes anônimos para a comunicação entre processos locais](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md).  
  
-   Pipes nomeados.  
  
     Os pipes nomeados fornecem a comunicação entre processos entre um servidor de pipe e um ou mais clientes pipe. Os pipes nomeados podem ser unidirecionais ou bidirecionais. Eles oferecem suporte à comunicação baseada em mensagens e permitem que vários clientes se conectem simultaneamente ao processo do servidor usando o mesmo nome de pipe. Os pipes nomeados também oferecem suporte à representação, que permite aos processos de conexão usar suas próprias permissões em servidores remotos.  
  
     No .NET Framework, você implementa pipes nomeados usando as classes <xref:System.IO.Pipes.NamedPipeServerStream> e <xref:System.IO.Pipes.NamedPipeClientStream>.  
  
     Veja [Como usar pipes nomeados para comunicação entre processos na rede](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md).  
  
## <a name="see-also"></a>Consulte também  
 [E/S de arquivo e de fluxo](../../../docs/standard/io/index.md)  
 [Como usar pipes anônimos para comunicação entre processos locais](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md)  
 [Como usar pipes nomeados para comunicação entre processos na rede](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md)
