---
title: "get (Referência de C#)"
ms.date: 03/10/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- get_CSharpKeyword
- get
helpviewer_keywords: get keyword [C#]
ms.assetid: a52de048-fbe0-41b0-82ec-8e4ac04d3a71
caps.latest.revision: "11"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a2e8426e5c5be16be0114b5ccc66f30793ce7dda
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="get-c-reference"></a>get (Referência de C#)

A palavra-chave `get` define um método do *acessador* em uma propriedade ou um indexador que retorna o valor da propriedade ou o elemento do indexador. Para obter mais informações, consulte [Propriedades](../../../csharp/programming-guide/classes-and-structs/properties.md), [Propriedades autoimplementadas](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md) e [Indexadores](../../../csharp/programming-guide/indexers/index.md).  
  
O exemplo a seguir define um acessador `get` e um acessador `set` para uma propriedade chamada `Seconds`. Ela usa um campo particular chamado `_seconds` para dar suporte ao valor da propriedade.  
 
 [!code-csharp[get#1](../../../../samples/snippets/csharp/language-reference/keywords/get/get-1.cs)]  
  
Geralmente, o acessador `get` consiste em uma única instrução que retorna um valor, como no exemplo anterior. A partir do C# 7, você pode implementar o acessador `get` como um membro apto para expressão. O exemplo a seguir implementa os acessadores `get` e `set` como membros aptos para expressão.

 [!code-csharp[get#3](../../../../samples/snippets/csharp/language-reference/keywords/get/get-3.cs)]   
 
Para casos simples em que os acessadores `get` e `set` de uma propriedade não realizam nenhuma outra operação, a não ser a configuração ou a recuperação de um valor em um campo de suporte particular, você pode tirar proveito do suporte do compilador do C# para propriedades autoimplementadas. O exemplo a seguir implementa `Hours` como uma propriedade autoimplementada. 
  
 [!code-csharp[get#2](../../../../samples/snippets/csharp/language-reference/keywords/get/get-2.cs)]  
  
## <a name="c-language-specification"></a>Especificação da Linguagem C#

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Consulte também  
 [Referência de C#](../../../csharp/language-reference/index.md)  
 [Guia de Programação em C#](../../../csharp/programming-guide/index.md)  
 [Palavras-chave C#](../../../csharp/language-reference/keywords/index.md) [propriedades](../../../csharp/programming-guide/classes-and-structs/properties.md)
