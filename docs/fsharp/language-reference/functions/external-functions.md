---
title: "Funções externas (F#)"
description: "Saiba mais sobre o suporte de linguagem F # para chamar funções em código nativo."
keywords: "visual f#, f#, programação funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: c26b6124-ceaa-471c-9dc9-861b4dfa332a
ms.openlocfilehash: 69b73983a91bc6c7cc38fa34484a3c89fc01858f
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2017
---
# <a name="external-functions"></a>Funções externas

Este tópico descreve o suporte da linguagem F # para chamar funções em código nativo.

## <a name="syntax"></a>Sintaxe

```fsharp
[<DllImport( arguments )>]
extern declaration
```

## <a name="remarks"></a>Comentários

Na sintaxe anterior, *argumentos* representa os argumentos fornecidos para o `System.Runtime.InteropServices.DllImportAttribute` atributo. O primeiro argumento é uma cadeia de caracteres que representa o nome da DLL que contém essa função, sem a extensão. dll. Argumentos adicionais podem ser fornecidos para qualquer uma das propriedades públicas do `System.Runtime.InteropServices.DllImportAttribute` classe, como a convenção de chamada.

Suponha que você tem um DLL do C++ que contém a seguinte função exportada nativo.

```cpp
#include <stdio.h>
extern "C" void __declspec(dllexport) HelloWorld()
{
    printf("Hello world, invoked by F#!\n");
}
```

Você pode chamar essa função do F # usando o código a seguir.

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

Interoperabilidade com código nativo é conhecida como *invocação de plataforma* e é um recurso do CLR. Para obter mais informações, consulte [interoperação com código não gerenciado](../../../../docs/framework/interop/index.md). As informações nesta seção são aplicáveis a F #.


## <a name="see-also"></a>Consulte também

[Funções](index.md)
