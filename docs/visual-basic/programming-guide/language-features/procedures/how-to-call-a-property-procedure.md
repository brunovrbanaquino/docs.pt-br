---
title: Como chamar um procedimento de propriedade (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], property procedures
- procedure calls [Visual Basic], property procedures
ms.assetid: 96bc4d74-d9c3-4b7a-954d-58ac8553cd94
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cf9080e3c2b23302257499f13e734231f3614495
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-a-property-procedure-visual-basic"></a>Como chamar um procedimento de propriedade (Visual Basic)
Para chamar um procedimento de propriedade, armazenar um valor na propriedade ou recuperar seu valor. Você acessa uma propriedade da mesma maneira que você acessa uma variável.  
  
 A propriedade `Set` procedimento armazena um valor e seu `Get` procedimento recupera o valor. No entanto, você não explicitamente chamar esses procedimentos por nome. Você usar a propriedade em uma instrução de atribuição ou uma expressão, exatamente como você poderia armazenar ou recuperar o valor de uma variável. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]faz as chamadas aos procedimentos da propriedade.  
  
### <a name="to-call-a-propertys-get-procedure"></a>Para chamar um procedimento da propriedade Get  
  
1.  Use o nome da propriedade em uma expressão da mesma maneira que você usaria um nome de variável. Você pode usar uma propriedade em qualquer lugar você pode usar uma variável ou constante.  
  
     -ou-  
  
     Use o nome de propriedade seguido de igual (`=`) entrar em uma instrução de atribuição.  
  
     O exemplo a seguir lê o valor de <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> property, implicitamente chamando seu `Get` procedimento.  
  
     [!code-vb[VbVbalrDateProperties#4](./codesnippet/VisualBasic/how-to-call-a-property-procedure_1.vb)]  
  
2.  Se a propriedade utiliza argumentos, siga o nome da propriedade com parênteses para incluir a lista de argumentos. Se não houver nenhum argumento, opcionalmente, você pode omitir os parênteses.  
  
3.  Coloque os argumentos na lista de argumentos dentro dos parênteses, separados por vírgulas. Certifique-se de que fornecer os argumentos na mesma ordem que a propriedade define os parâmetros correspondentes.  
  
 O valor da propriedade participa na expressão apenas como uma variável ou constante seria, ou ele é armazenado na variável ou propriedade no lado esquerdo da instrução de atribuição.  
  
### <a name="to-call-a-propertys-set-procedure"></a>Para chamar uma propriedade do procedimento Set  
  
1.  Use o nome da propriedade no lado esquerdo de uma instrução de atribuição.  
  
     O exemplo a seguir define o valor de <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> property, implicitamente chamando o `Set` procedimento.  
  
     [!code-vb[VbVbcnProcedures#11](./codesnippet/VisualBasic/how-to-call-a-property-procedure_2.vb)]  
  
2.  Se a propriedade utiliza argumentos, siga o nome da propriedade com parênteses para incluir a lista de argumentos. Se não houver nenhum argumento, opcionalmente, você pode omitir os parênteses.  
  
3.  Coloque os argumentos na lista de argumentos dentro dos parênteses, separados por vírgulas. Certifique-se de que fornecer os argumentos na mesma ordem que a propriedade define os parâmetros correspondentes.  
  
 O valor gerado no lado direito da instrução de atribuição é armazenado na propriedade.  
  
## <a name="see-also"></a>Consulte também  
 [Procedimentos de Propriedade](./property-procedures.md)  
 [Parâmetros e Argumentos de Procedimento](./procedure-parameters-and-arguments.md)  
 [Instrução Property](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [Diferenças entre propriedades e variáveis no Visual Basic](./differences-between-properties-and-variables.md)  
 [Como criar uma propriedade](./how-to-create-a-property.md)  
 [Como declarar uma propriedade com níveis de acesso mistos](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [Como: declarar e chamar uma propriedade padrão no Visual Basic](./how-to-declare-and-call-a-default-property.md)  
 [Como inserir um valor em uma propriedade](./how-to-put-a-value-in-a-property.md)  
 Como obter um valor de uma propriedade (Visual Basic)[Como obter um valor de uma propriedade](./how-to-get-a-value-from-a-property.md)  
 [Instrução Get](../../../../visual-basic/language-reference/statements/get-statement.md)  
 [Instrução Set](../../../../visual-basic/language-reference/statements/set-statement.md)
