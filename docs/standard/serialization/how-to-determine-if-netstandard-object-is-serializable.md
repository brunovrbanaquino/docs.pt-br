---
title: "Como: determinar se um objeto .NET padrão é serializável"
description: "Mostra como determinar se um tipo .NET padrão pode ser serializado em tempo de execução."
ms.custom: 
ms.date: 10/20/2017
ms.prod: .net
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 8246e825202b3eb02db5d11f1fe55b4a0d14a4ea
ms.sourcegitcommit: 099aa20d9b6450d1b7452d782a55771a6ad8ff35
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2018
---
# <a name="how-to-determine-if-a-net-standard-object-is-serializable"></a>Como: determinar se um objeto .NET padrão é serializável

O padrão do .NET é uma especificação que define os tipos e membros que devem estar presentes em implementações específicas do .NET que estão em conformidade com essa versão do padrão. No entanto, o padrão do .NET não define se um tipo é serializável. Os tipos definidos na biblioteca .NET padrão não são marcados com o <xref:System.SerializableAttribute> atributo. Em vez disso, implementações específicas do .NET, como o .NET Framework e o .NET Core serão livres para determinar se um determinado tipo é serializável. 

Se você desenvolveu uma biblioteca que tem como destino padrão do .NET, a biblioteca pode ser consumida por qualquer implementação do .NET que oferece suporte ao padrão do .NET. Isso significa que você não pode saber com antecedência se um tipo específico é serializável; Você somente pode determinar se é serializável em tempo de execução.

Você pode determinar se um objeto é serializado em tempo de execução por recuperar o valor da <xref:System.Type.IsSerializable> propriedade de um <xref:System.Type> objeto que representa o tipo do objeto. O exemplo a seguir fornece uma implementação. Define uma `IsSerializable(Object)` método de extensão que indica se qualquer <xref:System.Object> instância pode ser serializada.

[!code-csharp[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#2)]
[!code-vb[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/library.vb#2)]

Você pode passar qualquer objeto para o método para determinar se ele pode ser serializado e desserializado na implementação atual do .NET, como mostra o exemplo a seguir:

[!code-csharp[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#1)]
[!code-vb[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/program.vb#1)]

# <a name="see-also"></a>Consulte também

[Serialização binária](binary-serialization.md)   
<xref:System.SerializableAttribute?displayProperty=nameWithType>    
<xref:System.Type.IsSerializable?displayProperty=nameWithType>   
