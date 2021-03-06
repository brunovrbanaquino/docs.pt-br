---
title: "Chamando uma propriedade ou um método usando o nome de uma cadeia de caracteres (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- passing operators [Visual Basic]
- strings [Visual Basic], passing new operators as
- objects [Visual Basic], setting properties
- setting properties, object properties at run time
- method calls [Visual Basic], strings
- methods [Visual Basic], calling with string names
- calling methods [Visual Basic], string names
- properties [Visual Basic], setting at run time
- CallByName function
ms.assetid: 79a7b8b4-b8c7-4ad8-aca8-12a9a2b32f03
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c5974257fb82fe83c66a480225da200c14338898
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="calling-a-property-or-method-using-a-string-name-visual-basic"></a>Chamando uma propriedade ou um método usando o nome de uma cadeia de caracteres (Visual Basic)
Na maioria dos casos, você pode descobrir as propriedades e métodos de um objeto em tempo de design e escrever código para lidar com eles. No entanto, em alguns casos você talvez não saiba sobre as propriedades e métodos de um objeto com antecedência, ou você pode apenas querer a flexibilidade de habilitação de um usuário final especificar propriedades ou executar métodos em tempo de execução.  
  
## <a name="callbyname-function"></a>Função CallByName  
 Considere, por exemplo, um aplicativo cliente que avalia as expressões inseridas pelo usuário, passando um operador para um componente COM. Suponha que você está constantemente adicionando novas funções ao componente que exigem novos operadores. Quando você usa técnicas de acesso a objeto padrão, você deve recompilar e redistribuir o aplicativo cliente antes que ele poderia usar os novos operadores. Para evitar isso, você pode usar o `CallByName` função para passar os novos operadores como cadeias de caracteres, sem alterar o aplicativo.  
  
 O `CallByName` função permite que você use uma cadeia de caracteres para especificar uma propriedade ou método em tempo de execução. A assinatura para o `CallByName` função tem esta aparência:  
  
 *Resultado* = `CallByName`(*objeto*, *ProcedureName*, *CallType*, *argumentos*())  
  
 O primeiro argumento, *objeto*, obtém o nome do objeto que você deseja agir. O *ProcedureName* argumento tem uma cadeia de caracteres que contém o nome do procedimento de propriedade ou método a ser invocado. O *CallType* argumento leva uma constante que representa o tipo de procedimento para chamar: um método (`Microsoft.VisualBasic.CallType.Method`), uma propriedade de leitura (`Microsoft.VisualBasic.CallType.Get`), ou um conjunto de propriedades (`Microsoft.VisualBasic.CallType.Set`). O *argumentos* argumento, que é opcional, leva uma matriz do tipo `Object` que contém quaisquer argumentos para o procedimento.  
  
 Você pode usar `CallByName` com classes em sua solução atual, mas geralmente é usado para acessar objetos COM ou objetos de [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assemblies.  
  
 Suponha que você adicionar uma referência a um assembly que contém uma classe denominada `MathClass`, que tem uma nova função chamada `SquareRoot`, conforme mostrado no código a seguir:  
  
 [!code-vb[VbVbalrOOP#53](../../../../visual-basic/misc/codesnippet/VisualBasic/calling-a-property-or-method-using-a-string-name_1.vb)]  
  
 Seu aplicativo pode usar controles de caixa de texto para controlar qual método será chamado e seus argumentos. Por exemplo, se `TextBox1` contém a expressão a ser avaliada, e `TextBox2` é usado para inserir o nome da função, você pode usar o seguinte código para chamar o `SquareRoot` função na expressão em `TextBox1`:  
  
 [!code-vb[VbVbalrOOP#54](../../../../visual-basic/misc/codesnippet/VisualBasic/calling-a-property-or-method-using-a-string-name_2.vb)]  
  
 Se você inserir "64" `TextBox1`, "SquareRoot" no `TextBox2`e, em seguida, chame o `CallMath` procedimento, a raiz quadrada do número em `TextBox1` é avaliada. O código de exemplo invoca o `SquareRoot` função (que utiliza uma cadeia de caracteres que contém a expressão a ser avaliada como um argumento necessário) e retorna "8" `TextBox1` (a raiz quadrada de 64). Obviamente, se o usuário insere uma cadeia de caracteres inválida em `TextBox2`, se a cadeia de caracteres contém o nome de uma propriedade em vez de um método, ou se o método tinha um argumento adicional necessário, ocorrerá um erro de tempo de execução. Você precisa adicionar o código de tratamento de erros robusto ao usar `CallByName` para prever essas ou quaisquer outros erros.  
  
> [!NOTE]
>  Enquanto o `CallByName` função pode ser útil em alguns casos, você deve avaliar sua utilidade contra as implicações de desempenho — usando `CallByName` chamar um procedimento é um pouco mais lenta do que uma chamada de associação tardia. Se você estiver chamando uma função que é chamada repetidamente, tais como dentro de um loop, `CallByName` pode ter um grave efeito no desempenho.  
  
## <a name="see-also"></a>Consulte também  
 <xref:Microsoft.VisualBasic.Interaction.CallByName%2A>  
 [Determinando o Tipo de Objeto](../../../../visual-basic/programming-guide/language-features/early-late-binding/determining-object-type.md)
