---
title: Particular (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Private
helpviewer_keywords:
- Private keyword [Visual Basic]
- Private keyword [Visual Basic], syntax
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 07450c2a5443bf6bc147cad2cfc779072bfc363b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="private-visual-basic"></a>Particular (Visual Basic)
Especifica que um ou mais elementos de programação declarados são acessíveis somente de dentro de seu contexto de declaração, inclusive em todos os tipos contidos.  
  
## <a name="remarks"></a>Comentários  
 Se um elemento de programação representa funcionalidade proprietária, ou contém dados confidenciais, você geralmente deseja limitar o acesso a ele estritamente possível. Obtém o limite máximo, permitindo que somente o módulo, classe ou estrutura que o define para acessá-lo. Para limitar o acesso a um elemento dessa maneira, você pode declará-la com `Private`.  
  
## <a name="rules"></a>Regras  
  
-   **Contexto de declaração.** Você pode usar `Private` apenas no nível de módulo. Isso significa que o contexto da declaração para um `Private` elemento deve ser um módulo, classe ou estrutura e não pode ser um arquivo de origem, namespace, interface ou procedimento.  
  
## <a name="behavior"></a>Comportamento  
  
-   **Nível de acesso.** Todo código em um contexto de declaração pode acessar seus `Private` elementos. Isso inclui o código dentro de um tipo contido, como uma classe aninhada ou uma expressão de atribuição em uma enumeração. Nenhum código fora do contexto de declaração pode acessar seus `Private` elementos.  
  
-   **Modificadores de acesso.** As palavras-chave que especificam o nível de acesso são chamadas *modificadores de acesso*. Para uma comparação entre os modificadores de acesso, consulte [acessar níveis no Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 O `Private` modificador pode ser usado nesses contextos:  
  
 [Instrução Class](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Instrução Const](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [Instrução Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Instrução Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [Instrução Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Instrução Enum](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [Instrução Event](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Instrução Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Instrução Interface](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [Instrução Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Instrução Structure](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Instrução Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Consulte também  
 [Público](../../../visual-basic/language-reference/modifiers/public.md)  
 [Protegido](../../../visual-basic/language-reference/modifiers/protected.md)  
 [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
 [Níveis de acesso no Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [Procedimentos](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [Estruturas](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Objetos e Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
