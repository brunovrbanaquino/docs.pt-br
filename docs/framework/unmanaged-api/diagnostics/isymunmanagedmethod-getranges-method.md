---
title: "Método ISymUnmanagedMethod::GetRanges"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedMethod.GetRanges
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetRanges
helpviewer_keywords:
- ISymUnmanagedMethod::GetRanges method [.NET Framework debugging]
- GetRanges method [.NET Framework debugging]
ms.assetid: a85283d8-379c-417a-9736-ddeeef9bcf50
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1e17b411e39e522006092d79380566484f8fab67
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedmethodgetranges-method"></a>Método ISymUnmanagedMethod::GetRanges
Fornecido uma posição em um documento, retorna uma matriz de pares deslocamentos de início e término que correspondem aos intervalos de Microsoft intermediate language (MSIL) que abrange a posição dentro desse método. A matriz é uma matriz de inteiros e tem o formato [início, end, início, fim]. O número de pares de intervalo é o comprimento da matriz dividido por 2.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
HRESULT GetRanges(  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32                line,  
    [in]  ULONG32                column,  
    [in]  ULONG32                cRanges,  
    [out] ULONG32                *pcRanges,  
    [out, size_is(cRanges),  
        length_is(*pcRanges)] ULONG32 ranges[]);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `document`  
 [in] O documento para o qual o deslocamento é solicitado.  
  
 `line`  
 [in] A linha do documento correspondente a intervalos.  
  
 `column`  
 [in] A coluna de documento correspondente a intervalos.  
  
 `cRanges`  
 [in] O tamanho do `ranges` matriz.  
  
 `pcRanges`  
 [out] Um ponteiro para um `ULONG32` que recebe o tamanho do buffer necessário para conter os intervalos.  
  
 `ranges`  
 [out] Um ponteiro para o buffer que recebe os intervalos.  
  
## <a name="return-value"></a>Valor de retorno  
 S_OK se o método for bem-sucedido; Caso contrário, E_FAIL ou algum outro código de erro.  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Consulte também  
 [Interface ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
