---
title: Acessando atributos personalizados | Microsoft Docs
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
- custom attributes, accessibility
- attributes [.NET Framework], accessing
- reflection, custom attributes
ms.assetid: 1d8e3398-00d8-47d5-a084-214f9859d3d7
caps.latest.revision: 15
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: fbbc83b6aafdd5f2cbf554de66bc19f49d635aff
ms.contentlocale: pt-br
ms.lasthandoff: 06/02/2017

---
# <a name="accessing-custom-attributes"></a>Acessando atributos personalizados
Depois que os atributos tiverem sido associados aos elementos do programa, a reflexão poderá ser usada para consultar sua existência e seus valores. No .NET Framework versão 1.0 e 1.1, os atributos personalizados são examinados no contexto de execução. O .NET Framework versão 2.0 fornece um novo contexto de carregamento, o contexto somente para reflexão, que pode ser usado para examinar o código que não pode ser carregado para execução.  
  
## <a name="the-reflection-only-context"></a>O contexto somente para reflexão  
 O código carregado no contexto somente para reflexão não pode ser executado. Isso significa que instâncias de atributos personalizados não podem ser criadas porque isso exigiria a execução de seus construtores. Para carregar e examinar os atributos personalizados no contexto somente para reflexão, use a classe <xref:System.Reflection.CustomAttributeData>. Você pode obter as instâncias dessa classe usando a sobrecarga apropriada do método <xref:System.Reflection.CustomAttributeData.GetCustomAttributes%2A?displayProperty=fullName> estático. Consulte [Como carregar assemblies no contexto de somente para reflexão](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).  
  
## <a name="the-execution-context"></a>O contexto de execução  
 Os principais métodos de reflexão para consultar atributos no contexto de execução são <xref:System.Reflection.MemberInfo.GetCustomAttributes%2A?displayProperty=fullName> e <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=fullName>.  
  
 A acessibilidade de um atributo personalizado é verificada em relação ao assembly no qual ele está anexado. Isso é equivalente a verificar se um método em um tipo no assembly no qual o atributo personalizado está anexado pode chamar o construtor do atributo personalizado.  
  
 Métodos como <xref:System.Reflection.Assembly.GetCustomAttributes%28System.Boolean%29?displayProperty=fullName> verificam a visibilidade e a acessibilidade do argumento de tipo. Somente o código no assembly que contém o tipo definido pelo usuário pode recuperar um atributo personalizado desse tipo usando **GetCustomAttributes**.  
  
 O exemplo de C# a seguir é um padrão de design de atributo personalizado típico. Ele ilustra o modelo de reflexão do atributo personalizado em tempo de execução.  
  
```  
System.DLL  
public class DescriptionAttribute : Attribute  
{  
}  
  
System.Web.DLL  
internal class MyDescriptionAttribute : DescriptionAttribute  
{  
}  
  
public class LocalizationExtenderProvider  
{  
    [MyDescriptionAttribute(...)]  
    public CultureInfo GetLanguage(...)  
    {  
    }  
}  
```  
  
 Se o tempo de execução estiver tentando recuperar os atributos personalizados para o tipo de atributo personalizado público <xref:System.ComponentModel.DescriptionAttribute> anexado ao método **GetLanguage**, ele executará as seguintes ações:  
  
1.  O tempo de execução verifica se o argumento de tipo **DescriptionAttribute** para **Type.GetCustomAttributes**(Tipo *type*) é público e, portanto, está visível e acessível.  
  
2.  O tempo de execução verifica se o tipo definido pelo usuário **MyDescriptionAttribute** que é derivado de **DescriptionAttribute** está visível e acessível dentro do assembly **System.Web.DLL**, onde ele está anexado ao método **GetLanguage**().  
  
3.  O tempo de execução verifica se o construtor de **MyDescriptionAttribute** está visível e acessível dentro do assembly **System.Web.DLL**.  
  
4.  O tempo de execução chama o construtor de **MyDescriptionAttribute** com os parâmetros do atributo personalizado e retorna o novo objeto ao chamador.  
  
 O modelo de reflexão do atributo personalizado pode causar perda de instâncias de tipos definidos pelo usuário fora do assembly no qual o tipo é definido. Isso não é diferente dos membros na biblioteca do sistema do tempo de execução que retornam instâncias de tipos definidos pelo usuário, como <xref:System.Type.GetMethods%2A?displayProperty=fullName> que retorna uma matriz de objetos **RuntimeMethodInfo**. Para impedir que um cliente descubra informações sobre um tipo de atributo personalizado definido pelo usuário, defina os membros do tipo como confidenciais.  
  
 O exemplo a seguir demonstra a maneira básica de usar a reflexão para obter acesso a atributos personalizados.  
  
 [!code-cpp[CustomAttributeData#2](../../../samples/snippets/cpp/VS_Snippets_CLR/CustomAttributeData/CPP/source2.cpp#2)] [!code-csharp[CustomAttributeData#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CustomAttributeData/CS/source2.cs#2)] [!code-vb[CustomAttributeData#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CustomAttributeData/VB/source2.vb#2)]  
  
## <a name="see-also"></a>Consulte também  
 <xref:System.Reflection.MemberInfo.GetCustomAttributes%2A?displayProperty=fullName>   
 <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=fullName>   
 [Exibindo informações de tipo](../../../docs/framework/reflection-and-codedom/viewing-type-information.md)   
 [Considerações sobre segurança relacionadas à reflexão](../../../docs/framework/reflection-and-codedom/security-considerations-for-reflection.md)