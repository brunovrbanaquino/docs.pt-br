---
title: "Como: Executar ações quando um bloco de fluxo de dados recebe dados"
ms.date: 03/30/2017
ms.prod: .net
ms.technology: dotnet-standard
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- TPL dataflow library, receiving data
ms.assetid: fc2585dc-965e-4632-ace7-73dd02684ed3
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 4aee0462e641e755830b63d3d708bf51b22cd797
ms.sourcegitcommit: 6a9030eb5bd0f00e1d144f81958adb195cfb1f6f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-perform-action-when-a-dataflow-block-receives-data"></a>Como: Executar ações quando um bloco de fluxo de dados recebe dados
Os tipos de *Blocos de fluxo de dados de execução* chamam um representante fornecido pelo usuário ao receber dados. As classes <xref:System.Threading.Tasks.Dataflow.ActionBlock%601?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602?displayProperty=nameWithType> e <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602?displayProperty=nameWithType> são tipos de blocos de fluxo de dados de execução. Você pode usar a palavra-chave `delegate` (`Sub` em [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), <xref:System.Action%601>, <xref:System.Func%602> ou uma expressão lambda ao fornecer uma função de trabalho a um bloco de fluxo de dados de execução. Este documento descreve como usar <xref:System.Func%602> e as expressões lambda para executar a ação em blocos de execução.  

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="example"></a>Exemplo  
 O exemplo a seguir usa o fluxo de dados para ler um arquivo do disco e calcula o número de bytes no arquivo que são iguais a zero. Ele usa <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> para ler o arquivo e calcula o número de zero bytes e <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> para imprimir o número de zero bytes no console. O objeto <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> especifica um objeto <xref:System.Func%602> para executar o trabalho quando os blocos recebem dados. O objeto <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> usa uma expressão lambda para imprimir no console o número de zero bytes que são lidos.  
  
 [!code-csharp[TPLDataflow_ExecutionBlocks#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_executionblocks/cs/dataflowexecutionblocks.cs#1)]
 [!code-vb[TPLDataflow_ExecutionBlocks#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_executionblocks/vb/dataflowexecutionblocks.vb#1)]  
  
 Embora você possa fornecer uma expressão lambda para um objeto <xref:System.Threading.Tasks.Dataflow.TransformBlock%602>, este exemplo usa <xref:System.Func%602> para habilitar outro código para usar o método `CountBytes`. O objeto <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> usa uma expressão lambda porque o trabalho a ser executado é específico dessa tarefa e provavelmente não será útil para outro código. Para obter mais informações sobre como as expressões lambda funcionam na Biblioteca de paralelismo de tarefas, confira [Expressões lambda no PLINQ e TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).  
  
 A seção Resumo de tipos de representantes no documento [Fluxo de dados](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md) resume os tipos de representantes que você pode oferecer aos objetos <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> e <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602>. A tabela também especifica se o tipo de representante opera de forma síncrona ou assíncrona.  
  
## <a name="compiling-the-code"></a>Compilando o código  
 Copie o código de exemplo e cole-o em um projeto do Visual Studio, ou cole-o em um arquivo chamado `DataflowExecutionBlocks.cs` (`DataflowExecutionBlocks.vb` para [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) e execute o seguinte comando em uma janela do Prompt de comando do Visual Studio.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowExecutionBlocks.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowExecutionBlocks.vb**  
  
## <a name="robust-programming"></a>Programação robusta  
 Este exemplo fornece um representante do tipo <xref:System.Func%602> ao objeto <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> para executar a tarefa do bloco de fluxo de dados de forma síncrona. Para habilitar o bloco de fluxo de dados para se comportar de forma assíncrona, forneça um representante do tipo <xref:System.Func%601> ao bloco de fluxo de dados. Quando um bloco de fluxo de dados se comporta de forma assíncrona, a tarefa do bloco de fluxo de dados só será concluída quando o objeto <xref:System.Threading.Tasks.Task%601>retornado for concluído. O exemplo a seguir modifica o método `CountBytes` e usa os operadores [async](~/docs/csharp/language-reference/keywords/async.md) e [await](~/docs/csharp/language-reference/keywords/await.md) ([Async](~/docs/visual-basic/language-reference/modifiers/async.md) e [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) em [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) para calcular de forma assíncrona o número total de bytes que tem valor zero no arquivo fornecido. O método <xref:System.IO.FileStream.ReadAsync%2A> executa operações de leitura de arquivo de forma assíncrona.  
  
 [!code-csharp[TPLDataflow_ExecutionBlocks#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_executionblocks/cs/dataflowexecutionblocks.cs#2)]
 [!code-vb[TPLDataflow_ExecutionBlocks#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_executionblocks/vb/dataflowexecutionblocks.vb#2)]  
  
 Você também pode usar expressões lambda assíncronas para executar a ação em um bloco de fluxo de dados de execução. O exemplo a seguir modifica o objeto <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> usado no exemplo anterior para que ele use uma expressão lambda para executar o trabalho de forma assíncrona.  
  
 [!code-csharp[TPLDataflow_ExecutionBlocks#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_executionblocks/cs/dataflowexecutionblocks.cs#3)]
 [!code-vb[TPLDataflow_ExecutionBlocks#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_executionblocks/vb/dataflowexecutionblocks.vb#3)]  
  
## <a name="see-also"></a>Consulte também  
 [Fluxo de dados](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
