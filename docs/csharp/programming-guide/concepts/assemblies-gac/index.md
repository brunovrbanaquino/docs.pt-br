---
title: Assemblies e o cache de assembly global (C#) | Microsoft Docs
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 149f5ca5-5b34-4746-9542-1ae43b2d0256
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 3305034e916f10d863b2194681342df246f2acc1
ms.lasthandoff: 03/13/2017

---
# <a name="assemblies-and-the-global-assembly-cache-c"></a>Assemblies e o cache de assembly global (C#)
Os assemblies formam a unidade fundamental de implantação, controle de versão, reutilização, escopo de ativação e permissões de segurança para um aplicativo baseado em .NET Framework. Os assemblies tomam a forma de um arquivo executável (.exe) ou de biblioteca de link dinâmico (.dll) e são os blocos de construção do .NET Framework. Eles oferecem ao Common Language Runtime as informações de que ele precisa para estar ciente das implementações de tipo. Você pode pensar em um assembly como uma coleção de tipos e recursos que formam uma unidade lógica de funcionalidade e são criados para trabalharem juntos.  
  
 Os assemblies podem conter um ou mais módulos. Por exemplo, projetos maiores podem ser planejados de forma que vários desenvolvedores individuais trabalhem em módulos separados, todos juntos para criar um único assembly. Para obter mais informações sobre os módulos, consulte o tópico [Como compilar um Assembly de vários arquivos](https://msdn.microsoft.com/library/226t7yxe).  
  
 Os assemblies têm as seguintes propriedades:  
  
-   Assemblies são implementados como arquivos .dll ou .exe.  
  
-   Você pode compartilhar um assembly entre aplicativos colocando-o no cache de assembly global. Os assemblies devem ter nome forte antes de serem colocados no cache de assembly global. Para obter mais informações, consulte [Assemblies com nome forte](https://msdn.microsoft.com/library/wd40t7ad).  
  
-   Os assemblies serão carregados na memória somente se forem necessários. Se não forem usados, eles não serão carregados. Isso significa que os assemblies podem ser uma maneira eficiente de gerenciar recursos em projetos grandes.  
  
-   Você pode obter informações programaticamente sobre um assembly usando reflexão. Para obter mais informações, consulte [Reflexão (C#)](../../../../csharp/programming-guide/concepts/reflection.md).  
  
-   Se você deseja carregar um assembly apenas para inspecioná-lo, use um método como <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A>.  
  
## <a name="assembly-manifest"></a>Manifesto de um assembly  
 Dentro de todo assembly está um *manifesto do assembly*. Semelhante a um sumário, o manifesto do assembly contém o seguinte:  
  
-   A identidade do assembly (seu nome e versão).  
  
-   Uma tabela de arquivo que descreve todos os outros arquivos que compõem o assembly, por exemplo, quaisquer outros assemblies que você criou que seu arquivo .dll ou .exe depende, ou até mesmo arquivos bitmap ou Leiame.  
  
-   Um *lista de referências de assembly*, que é uma lista de todas as dependências externas, .dlls ou outros arquivos que seu aplicativo precisa e que podem ter sido criados por outra pessoa. As referências de assembly contêm referências a objetos globais e privados. Os objetos globais residem no cache de assembly global, uma área disponível para outros aplicativos. Objetos privados devem estar em um diretório no mesmo nível ou abaixo do diretório no qual seu aplicativo está instalado.  
  
 Como os assemblies contêm informações sobre conteúdo, controle de versão e dependências, os aplicativos criados com o C# não dependem de valores do Registro do Windows para funcionar corretamente. Os assemblies reduzem conflitos de .dll e tornam seus aplicativos mais confiáveis e mais fáceis de implantar. Em muitos casos, você pode instalar um aplicativo baseado em .NET simplesmente copiando seus arquivos para o computador de destino.  
  
 Para obter mais informações, consulte [Manifesto do assembly](https://msdn.microsoft.com/library/1w45z383).  
  
## <a name="adding-a-reference-to-an-assembly"></a>Adicionando uma referência a um assembly  
 Para usar um assembly, você deve adicionar uma referência a ele. Em seguida, use a [diretiva using](../../../../csharp/language-reference/keywords/using-directive.md) para escolher o namespace dos itens que você deseja usar. Quando um assembly é referenciado e importado, todas as classes acessíveis, propriedades, métodos e outros membros de seus namespaces estão disponíveis para o seu aplicativo como se seus códigos fossem parte de seu arquivo de origem.  
  
 No C#, você também pode usar duas versões do mesmo assembly em um único aplicativo. Para obter mais informações, consulte [alias externo](../../../../csharp/language-reference/keywords/extern-alias.md).  
  
## <a name="creating-an-assembly"></a>Criando um assembly  
 Compile o aplicativo clicando em **Compilar** no menu **Compilar** ou compile da linha de comando usando o compilador de linha de comando. Para obter detalhes sobre como compilar assemblies da linha de comando, consulte [Compilando da linha de comando com csc.exe](../../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  
  
> [!NOTE]
>  Para criar um assembly no Visual Studio, no menu **Compilar**, escolha **Compilar**.  
  
## <a name="see-also"></a>Consulte também  
 [Guia de programação em C#](../../../../csharp/programming-guide/index.md)   
 [Assemblies no Common Language Runtime](https://msdn.microsoft.com/library/k3677y81)   
 [Assemblies amigáveis (C#)](friend-assemblies.md)   
 [Como compartilhar um assembly com outros aplicativos (C#)](how-to-share-an-assembly-with-other-applications.md)   
 [Como carregar e descarregar assemblies (C#)](how-to-load-and-unload-assemblies.md)   
 [Como determinar se um arquivo é um assembly (C#)](how-to-determine-if-a-file-is-an-assembly.md)   
 [Como criar e usar assemblies usando a linha de comando (C#)](how-to-create-and-use-assemblies-using-the-command-line.md)   
 [Passo a passo: inserindo tipos de assemblies gerenciados no Visual Studio (C#)](walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md)   
 [Passo a passo: inserindo informações de tipo dos Microsoft Office Assemblies no Visual Studio (C#)](walkthrough-embedding-type-information-from-microsoft-office-assemblies.md)