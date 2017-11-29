---
title: "Enumeração CorSymAddrKind"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorSymAddrKind
api_location: mscoree.dll
api_type: COM
f1_keywords: CorSymAddrKind
helpviewer_keywords: CorSymAddrKind enumeration [.NET Framework debugging]
ms.assetid: 3ef841c2-cade-42ee-ba34-2ef91d6d0879
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 56bb55d9c9f85ae8f8112f16dcf552295699826d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="corsymaddrkind-enumeration"></a><span data-ttu-id="20067-102">Enumeração CorSymAddrKind</span><span class="sxs-lookup"><span data-stu-id="20067-102">CorSymAddrKind Enumeration</span></span>
<span data-ttu-id="20067-103">Indica o tipo de endereço de memória.</span><span class="sxs-lookup"><span data-stu-id="20067-103">Indicates the type of memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20067-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="20067-104">Syntax</span></span>  
  
```  
typedef enum CorSymAddrKind  
{  
    ADDR_IL_OFFSET          = 1,  
    ADDR_NATIVE_RVA         = 2,  
    ADDR_NATIVE_REGISTER    = 3,  
    ADDR_NATIVE_REGREL      = 4,  
    ADDR_NATIVE_OFFSET      = 5,  
    ADDR_NATIVE_REGREG      = 6,  
    ADDR_NATIVE_REGSTK      = 7,  
    ADDR_NATIVE_STKREG      = 8,  
    ADDR_BITFIELD           = 9,  
    ADDR_NATIVE_ISECTOFFSET = 10  
} CorSymAddrKind;  
```  
  
## <a name="members"></a><span data-ttu-id="20067-105">Membros</span><span class="sxs-lookup"><span data-stu-id="20067-105">Members</span></span>  
  
|<span data-ttu-id="20067-106">Membro</span><span class="sxs-lookup"><span data-stu-id="20067-106">Member</span></span>|<span data-ttu-id="20067-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="20067-107">Description</span></span>|  
|------------|-----------------|  
|`ADDR_IL_OFFSET`|<span data-ttu-id="20067-108">Indica um Microsoft intermediate language (MSIL) local variável ou parâmetro de índice.</span><span class="sxs-lookup"><span data-stu-id="20067-108">Indicates a Microsoft intermediate language (MSIL) local variable or parameter index.</span></span>|  
|`ADDR_NATIVE_RVA`|<span data-ttu-id="20067-109">Indica um endereço virtual relativo em um módulo.</span><span class="sxs-lookup"><span data-stu-id="20067-109">Indicates a relative virtual address into a module.</span></span>|  
|`ADDR_NATIVE_REGISTER`|<span data-ttu-id="20067-110">Indica um registro de CPU.</span><span class="sxs-lookup"><span data-stu-id="20067-110">Indicates a CPU register.</span></span>|  
|`ADDR_NATIVE_REGREL`|<span data-ttu-id="20067-111">Indica que o primeiro endereço é um registro e o segundo endereço é um deslocamento.</span><span class="sxs-lookup"><span data-stu-id="20067-111">Indicates that the first address is a register and the second address is an offset.</span></span>|  
|`ADDR_NATIVE_OFFSET`|<span data-ttu-id="20067-112">Indica um deslocamento de um endereço base.</span><span class="sxs-lookup"><span data-stu-id="20067-112">Indicates an offset from a base address.</span></span>|  
|`ADDR_NATIVE_REGREG`|<span data-ttu-id="20067-113">Indica que o primeiro endereço é a parte baixa de um registro, e o segundo endereço é a parte alta.</span><span class="sxs-lookup"><span data-stu-id="20067-113">Indicates that the first address is the low portion of a register, and the second address is the high portion.</span></span>|  
|`ADDR_NATIVE_REGSTK`|<span data-ttu-id="20067-114">Indica que o primeiro endereço é a parte baixa de um registro, o segundo é a parte alta e a terceira é um deslocamento.</span><span class="sxs-lookup"><span data-stu-id="20067-114">Indicates that the first address is the low portion of a register, the second is the high portion, and the third is an offset.</span></span>|  
|`ADDR_NATIVE_STKREG`|<span data-ttu-id="20067-115">Indica que o primeiro endereço é um registro, o segundo é um deslocamento e o terceiro é a parte alta do registro.</span><span class="sxs-lookup"><span data-stu-id="20067-115">Indicates that the first address is a register, the second is an offset, and the third is the high portion of the register.</span></span>|  
|`ADDR_BITFIELD`|<span data-ttu-id="20067-116">Indica que o primeiro endereço é o início de um campo e o segundo endereço é o tamanho do campo.</span><span class="sxs-lookup"><span data-stu-id="20067-116">Indicates that the first address is the start of a field and the second address is the field length.</span></span>|  
|`ADDR_NATIVE_ISECTOFFSET`|<span data-ttu-id="20067-117">Indica que o primeiro endereço é a seção e o segundo endereço é um deslocamento.</span><span class="sxs-lookup"><span data-stu-id="20067-117">Indicates that the first address is the section and the second address is an offset.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="20067-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="20067-118">Requirements</span></span>  
 <span data-ttu-id="20067-119">**Cabeçalho:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="20067-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20067-120">Consulte também</span><span class="sxs-lookup"><span data-stu-id="20067-120">See Also</span></span>  
 [<span data-ttu-id="20067-121">Enumerações de armazenamento de símbolo de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="20067-121">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)