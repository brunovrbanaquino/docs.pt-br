---
title: "Enumeração CorDeclSecurity"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDeclSecurity
api_location: mscoree.dll
api_type: COM
f1_keywords: CorDeclSecurity
helpviewer_keywords: CorDeclSecurity enumeration [.NET Framework metadata]
ms.assetid: 864f1267-d267-4696-8df7-1f83f8444d6f
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e5ba8de0a8db315e5c06586ad2248cfea241653b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="cordeclsecurity-enumeration"></a><span data-ttu-id="529e3-102">Enumeração CorDeclSecurity</span><span class="sxs-lookup"><span data-stu-id="529e3-102">CorDeclSecurity Enumeration</span></span>
<span data-ttu-id="529e3-103">Especifica as ações de segurança que podem ser executadas usando a segurança declarativa.</span><span class="sxs-lookup"><span data-stu-id="529e3-103">Specifies the security actions that can be performed using declarative security.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="529e3-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="529e3-104">Syntax</span></span>  
  
```  
typedef enum CorDeclSecurity {  
  
    dclActionMask               =   0x001f,  
    dclActionNil                =   0x0000,  
    dclRequest                  =   0x0001,  
    dclDemand                   =   0x0002,  
    dclAssert                   =   0x0003,  
    dclDeny                     =   0x0004,  
    dclPermitOnly               =   0x0005,  
    dclLinktimeCheck            =   0x0006,  
    dclInheritanceCheck         =   0x0007,  
    dclRequestMinimum           =   0x0008,  
    dclRequestOptional          =   0x0009,  
    dclRequestRefuse            =   0x000a,  
    dclPrejitGrant              =   0x000b,  
    dclPrejitDenied             =   0x000c,  
    dclNonCasDemand             =   0x000d,  
    dclNonCasLinkDemand         =   0x000e,  
    dclNonCasInheritance        =   0x000f,  
    dclLinkDemandChoice         =   0x0010,  
    dclInheritanceDemandChoice  =   0x0011,  
    dclDemandChoice             =   0x0012,  
    dclMaximumValue             =   0x0012  
  
} CorDeclSecurity;  
```  
  
## <a name="members"></a><span data-ttu-id="529e3-105">Membros</span><span class="sxs-lookup"><span data-stu-id="529e3-105">Members</span></span>  
  
|<span data-ttu-id="529e3-106">Membro</span><span class="sxs-lookup"><span data-stu-id="529e3-106">Member</span></span>|<span data-ttu-id="529e3-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="529e3-107">Description</span></span>|  
|------------|-----------------|  
|`dclActionMask`|<span data-ttu-id="529e3-108">Reservado.</span><span class="sxs-lookup"><span data-stu-id="529e3-108">Reserved.</span></span>|  
|`dclActionNil`|<span data-ttu-id="529e3-109">Reservado.</span><span class="sxs-lookup"><span data-stu-id="529e3-109">Reserved.</span></span>|  
|`dclRequest`|<span data-ttu-id="529e3-110">Reservado.</span><span class="sxs-lookup"><span data-stu-id="529e3-110">Reserved.</span></span>|  
|`dclDemand`|<span data-ttu-id="529e3-111">Todos os chamadores na pilha de chamadas deverão ter a permissão especificada pelo objeto de permissão atual.</span><span class="sxs-lookup"><span data-stu-id="529e3-111">All callers higher in the call stack are required to have been granted the permission specified by the current permission object.</span></span>|  
|`dclAssert`|<span data-ttu-id="529e3-112">O código de chamada pode acessar o recurso identificado pelo objeto de permissão atual, mesmo que os chamadores mais acima na pilha não recebeu permissão para acessar o recurso</span><span class="sxs-lookup"><span data-stu-id="529e3-112">The calling code can access the resource identified by the current permission object, even if callers higher in the stack have not been granted permission to access the resource</span></span>|  
|`dclDeny`|<span data-ttu-id="529e3-113">A capacidade de acessar o recurso especificado pelo objeto atual da permissão é negada a chamadores, mesmo se eles têm permissão para acessá-lo.</span><span class="sxs-lookup"><span data-stu-id="529e3-113">The ability to access the resource specified by the current permission object is denied to callers, even if they have been granted permission to access it.</span></span>|  
|`dclPermitOnly`|<span data-ttu-id="529e3-114">Somente os recursos especificados por esse objeto de permissão poderão ser acessados, mesmo que o código tenha recebido permissão para acessar outros recursos.</span><span class="sxs-lookup"><span data-stu-id="529e3-114">Only the resources specified by this permission object can be accessed, even if the code has been granted permission to access other resources.</span></span>|  
|`dclLinktimeCheck`|<span data-ttu-id="529e3-115">O chamador imediato é necessário ter a permissão especificada para um determinado período de tempo.</span><span class="sxs-lookup"><span data-stu-id="529e3-115">The immediate caller is required to have been granted the specified permission for a given period of time.</span></span>|  
|`dclInheritanceCheck`|<span data-ttu-id="529e3-116">A classe derivada herdar de outra classe ou substituindo um método é necessária para ter a permissão especificada.</span><span class="sxs-lookup"><span data-stu-id="529e3-116">The derived class inheriting another class or overriding a method is required to have been granted the specified permission.</span></span>|  
|`dclRequestMinimum`|<span data-ttu-id="529e3-117">O chamador pode solicitar para as permissões mínimas necessárias para a execução de código.</span><span class="sxs-lookup"><span data-stu-id="529e3-117">The caller can request for the minimum permissions required for code to run.</span></span> <span data-ttu-id="529e3-118">Esta ação só pode ser usada no escopo do assembly.</span><span class="sxs-lookup"><span data-stu-id="529e3-118">This action can only be used within the scope of the assembly.</span></span>|  
|`dclRequestOptional`|<span data-ttu-id="529e3-119">O chamador pode solicitar permissões adicionais que são opcionais (não é necessário para executar).</span><span class="sxs-lookup"><span data-stu-id="529e3-119">The caller can request for additional permissions that are optional (not required to run).</span></span> <span data-ttu-id="529e3-120">Essa solicitação implicitamente recusa todas as outras permissões não especificamente solicitadas.</span><span class="sxs-lookup"><span data-stu-id="529e3-120">This request implicitly refuses all other permissions not specifically requested.</span></span> <span data-ttu-id="529e3-121">Esta ação só pode ser usada no escopo do assembly.</span><span class="sxs-lookup"><span data-stu-id="529e3-121">This action can only be used within the scope of the assembly.</span></span>|  
|`dclRequestRefuse`|<span data-ttu-id="529e3-122">Solicitação do chamador para permissões que pode ser usado de forma incorreta não será concedida.</span><span class="sxs-lookup"><span data-stu-id="529e3-122">The caller's request for permissions that might be misused will not be granted.</span></span> <span data-ttu-id="529e3-123">Esta ação só pode ser usada no escopo do assembly.</span><span class="sxs-lookup"><span data-stu-id="529e3-123">This action can only be used within the scope of the assembly.</span></span>|  
|`dclPrejitGrant`|<span data-ttu-id="529e3-124">Reservado.</span><span class="sxs-lookup"><span data-stu-id="529e3-124">Reserved.</span></span>|  
|`dclPrejitDenied`|<span data-ttu-id="529e3-125">Reservado.</span><span class="sxs-lookup"><span data-stu-id="529e3-125">Reserved.</span></span>|  
|`dclNonCasDemand`|<span data-ttu-id="529e3-126">Reservado.</span><span class="sxs-lookup"><span data-stu-id="529e3-126">Reserved.</span></span>|  
|`dclNonCasLinkDemand`|<span data-ttu-id="529e3-127">O chamador imediato deverá ter recebido a permissão especificada.</span><span class="sxs-lookup"><span data-stu-id="529e3-127">The immediate caller is required to have been granted the specified permission.</span></span>|  
|`dclNonCasInheritance`|<span data-ttu-id="529e3-128">Reservado.</span><span class="sxs-lookup"><span data-stu-id="529e3-128">Reserved.</span></span>|  
|`dclLinkDemandChoice`|<span data-ttu-id="529e3-129">Reservado.</span><span class="sxs-lookup"><span data-stu-id="529e3-129">Reserved.</span></span>|  
|`dclInheritanceDemandChoice`|<span data-ttu-id="529e3-130">Reservado.</span><span class="sxs-lookup"><span data-stu-id="529e3-130">Reserved.</span></span>|  
|`dclDemandChoice`|<span data-ttu-id="529e3-131">Reservado.</span><span class="sxs-lookup"><span data-stu-id="529e3-131">Reserved.</span></span>|  
|`dclMaximumValue`|<span data-ttu-id="529e3-132">Reservado.</span><span class="sxs-lookup"><span data-stu-id="529e3-132">Reserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="529e3-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="529e3-133">Requirements</span></span>  
 <span data-ttu-id="529e3-134">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="529e3-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="529e3-135">**Cabeçalho:** Corhdr</span><span class="sxs-lookup"><span data-stu-id="529e3-135">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="529e3-136">**Versões do .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="529e3-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="529e3-137">Consulte também</span><span class="sxs-lookup"><span data-stu-id="529e3-137">See Also</span></span>  
 [<span data-ttu-id="529e3-138">Enumerações de metadados</span><span class="sxs-lookup"><span data-stu-id="529e3-138">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)