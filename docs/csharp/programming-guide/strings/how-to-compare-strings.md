---
title: "Como comparar cadeias de caracteres (Guia de Programação em C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- strings [C#], comparison
- comparing strings [C#]
ms.assetid: e1268e28-ee98-4695-98e9-92280f1c33c0
caps.latest.revision: "23"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4837fa57c962cba841ffcc83c5bd4475a4faff0c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-compare-strings-c-programming-guide"></a>Como comparar cadeias de caracteres (Guia de Programação em C#)

Quando compara cadeias de caracteres, você está produzindo um resultado que diz que uma cadeia de caracteres é maior ou menor que outra ou que as duas cadeias de caracteres são iguais. As regras segundo as quais o resultado é determinado são diferentes dependendo de você estar executando uma *comparação ordinal* ou uma *comparação sensível à cultura*. É importante usar o tipo correto de comparação para a tarefa específica.

 Use comparações ordinais básicas quando precisar comparar ou classificar os valores de duas cadeias de caracteres sem considerar convenções linguísticas. Uma comparação ordinal básica (`System.StringComparison.Ordinal`) diferencia maiúsculas de minúsculas, o que significa que as duas cadeias de caracteres devem corresponder em cada caractere: "and" não é igual a "And" ou "AND". Uma variação usada com frequência é `System.StringComparison.OrdinalIgnoreCase`, o que corresponde a "and", "And" e "AND". `StringComparison.OrdinalIgnoreCase` frequentemente é usado para comparar nomes de arquivo, nomes de caminho, caminhos de rede e qualquer outra cadeia de caracteres cujo valor não é alterado com base na localidade do computador do usuário. Para obter mais informações, consulte <xref:System.StringComparison?displayProperty=nameWithType>.

 Comparações sensíveis à cultura normalmente são usadas para comparar e classificar cadeias de caracteres que são inseridas por usuários finais, porque os caracteres e as convenções de classificação dessas cadeias de caracteres podem variar dependendo da localidade do computador do usuário. Até mesmo cadeias de caracteres que contêm caracteres idênticos podem ser classificadas de formas diferentes dependendo da cultura do thread atual.

> [!NOTE]
> Quando comparar cadeias de caracteres, você deve usar os métodos que especificam explicitamente o tipo de comparação que pretende executar. Isso torna o código mais legível e fácil de manter. Sempre que possível, use as sobrecargas dos métodos das classes <xref:System.String?displayProperty=nameWithType> e <xref:System.Array?displayProperty=nameWithType> que utilizam um parâmetro de enumeração <xref:System.StringComparison>, para que você possa especificar que tipo de comparação executar. É melhor evitar o uso dos operadores `==` e `!=` para comparar cadeias de caracteres. Além disso, evite usar os métodos de instância <xref:System.String.CompareTo%2A?displayProperty=nameWithType> porque nenhuma das sobrecargas utiliza um <xref:System.StringComparison>.

## <a name="example"></a>Exemplo

O exemplo a seguir mostra como comparar corretamente cadeias de caracteres cujos valores não serão alterados com base na localidade do computador do usuário. Além disso, ele também demonstra o recurso de *centralização da cadeia de caracteres* do C#. Quando um programa declara duas ou mais variáveis de cadeia de caracteres idênticas, o compilador armazena todas no mesmo local. Chamando o método <xref:System.Object.ReferenceEquals%2A>, você pode ver que as duas cadeias de caracteres na verdade se referem ao mesmo objeto na memória. Use o método <xref:System.String.Copy%2A?displayProperty=nameWithType> para evitar a centralização, conforme mostrado no exemplo.

[!code-csharp[csProgGuideStrings#11](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#11)]

## <a name="example"></a>Exemplo

O exemplo a seguir mostra como comparar cadeias de caracteres da maneira preferencial usando métodos <xref:System.String?displayProperty=nameWithType> que usam uma enumeração <xref:System.StringComparison>. Observe que os métodos de instância <xref:System.String.CompareTo%2A?displayProperty=nameWithType> não são usados aqui porque nenhuma das sobrecargas utiliza um <xref:System.StringComparison>.

[!code-csharp[csProgGuideStrings#31](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#31)]

## <a name="example"></a>Exemplo

O exemplo a seguir mostra como classificar e pesquisar cadeias de caracteres em uma matriz de maneira sensível à cultura usando os métodos <xref:System.Array> estáticos que usam um parâmetro <xref:System.StringComparer?displayProperty=nameWithType>.

[!code-csharp[csProgGuideStrings#32](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#32)]

Classes de coleção como <xref:System.Collections.Hashtable?displayProperty=nameWithType>, <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> e <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> têm construtores que usam um parâmetro <xref:System.StringComparer?displayProperty=nameWithType> quando o tipo dos elementos ou chaves é `string`. Em geral, você deve usar esses construtores sempre que possível e especificar `Ordinal` ou `OrdinalIgnoreCase`.

## <a name="see-also"></a>Consulte também
 <xref:System.Globalization.CultureInfo?displayProperty=nameWithType>  
 <xref:System.StringComparer?displayProperty=nameWithType>  
 [Cadeias de Caracteres](../../../csharp/programming-guide/strings/index.md)  
 [Comparação de cadeias de caracteres](../../../standard/base-types/comparing.md)  
 [Globalizando e localizando aplicativos](/visualstudio/ide/globalizing-and-localizing-applications)