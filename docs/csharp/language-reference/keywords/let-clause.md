---
title: "Cláusula let (Referência de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- let_CSharpKeyword
- let
helpviewer_keywords:
- let keyword [C#]
- let clause [C#]
ms.assetid: 13c9c1a4-ce57-48ef-8e1b-4c2a59b99fb4
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 077c5178946b85d0fb85aa8da94966e4c5821736
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="let-clause-c-reference"></a>Cláusula let (Referência de C#)
Em uma expressão de consulta, às vezes é útil armazenar o resultado de uma subexpressão para usá-lo em cláusulas subsequentes. É possível fazer isso com a palavra-chave `let`, que cria uma nova variável de intervalo e a inicializa com o resultado da expressão fornecida. Depois de inicializado com um valor, a variável de intervalo não pode ser usada para armazenar outro valor. No entanto, se a variável de intervalo mantiver um tipo passível de consulta, ela poderá ser consultada.  
  
## <a name="example"></a>Exemplo  
 No exemplo a seguir, `let` é usado de duas maneiras:  
  
1.  Para criar um tipo enumerável que pode ser pesquisado por si só.  
  
2.  Para permitir que a consulta chame `ToLower` apenas uma vez na variável de intervalo `word`. Sem usar `let`, seria necessário chamar `ToLower` em cada predicado na cláusula `where`.  
  
 [!code-csharp[cscsrefQueryKeywords#28](../../../csharp/language-reference/keywords/codesnippet/CSharp/let-clause_1.cs)]  
  
## <a name="see-also"></a>Consulte também  
 [Referência de C#](../../../csharp/language-reference/index.md)  
 [Palavras-chave de Consulta (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md)  
 [Expressões de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [Introdução a LINQ em C#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [Como manipular exceções em expressões de consultas](../../../csharp/programming-guide/linq-query-expressions/how-to-handle-exceptions-in-query-expressions.md)
