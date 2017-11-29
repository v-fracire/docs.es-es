---
title: ICorDebugNativeFrame Interfaz1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame
helpviewer_keywords: ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 04819c58-7246-4b32-befb-680cf1dbc436
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 63d631dec00e63d6ee383cd36d79382a529d9ddb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugnativeframe-interface1"></a><span data-ttu-id="a3589-102">ICorDebugNativeFrame Interfaz1</span><span class="sxs-lookup"><span data-stu-id="a3589-102">ICorDebugNativeFrame Interface1</span></span>
<span data-ttu-id="a3589-103">Una implementación especializada de ICorDebugFrame que se utiliza para los marcos nativos.</span><span class="sxs-lookup"><span data-stu-id="a3589-103">A specialized implementation of ICorDebugFrame used for native frames.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a3589-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="a3589-104">Methods</span></span>  
  
|<span data-ttu-id="a3589-105">Método</span><span class="sxs-lookup"><span data-stu-id="a3589-105">Method</span></span>|<span data-ttu-id="a3589-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="a3589-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a3589-107">CanSetIP (método)</span><span class="sxs-lookup"><span data-stu-id="a3589-107">CanSetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-cansetip-method.md)|<span data-ttu-id="a3589-108">Obtiene un valor que indica si es seguro establecer el puntero de instrucción en la ubicación de desplazamiento especificada en el código nativo.</span><span class="sxs-lookup"><span data-stu-id="a3589-108">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location in native code.</span></span>|  
|[<span data-ttu-id="a3589-109">GetIP (método)</span><span class="sxs-lookup"><span data-stu-id="a3589-109">GetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getip-method.md)|<span data-ttu-id="a3589-110">Obtiene el desplazamiento del marco de pila en código nativo.</span><span class="sxs-lookup"><span data-stu-id="a3589-110">Gets the stack frame's offset into native code.</span></span>|  
|[<span data-ttu-id="a3589-111">GetLocalDoubleRegisterValue (método)</span><span class="sxs-lookup"><span data-stu-id="a3589-111">GetLocalDoubleRegisterValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocaldoubleregistervalue-method.md)|<span data-ttu-id="a3589-112">Obtiene un puntero a un valor de ICorDebugValue que representa el valor de un argumento o una variable local almacenada en dos registros de memoria de un marco nativo.</span><span class="sxs-lookup"><span data-stu-id="a3589-112">Gets a pointer to an ICorDebugValue that represents the value of an argument or local variable stored in two memory registers of a native frame.</span></span>|  
|[<span data-ttu-id="a3589-113">GetLocalMemoryRegisterValue (método)</span><span class="sxs-lookup"><span data-stu-id="a3589-113">GetLocalMemoryRegisterValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryregistervalue-method.md)|<span data-ttu-id="a3589-114">Obtiene un puntero a un `ICorDebugValue` que representa el valor de una variable local, de los cuales los bits inferiores se almacenan en el registro especificado y cuyos bits altos se almacenan en la dirección de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="a3589-114">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable, of which the low bits are stored in the specified register and the high bits are stored at the specified memory address.</span></span>|  
|[<span data-ttu-id="a3589-115">GetLocalMemoryValue (método)</span><span class="sxs-lookup"><span data-stu-id="a3589-115">GetLocalMemoryValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryvalue-method.md)|<span data-ttu-id="a3589-116">Obtiene un puntero a un `ICorDebugValue` que representa el valor de una variable local almacenada en la dirección de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="a3589-116">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable stored at the specified memory address.</span></span>|  
|[<span data-ttu-id="a3589-117">GetLocalRegisterMemoryValue (método)</span><span class="sxs-lookup"><span data-stu-id="a3589-117">GetLocalRegisterMemoryValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistermemoryvalue-method.md)|<span data-ttu-id="a3589-118">Obtiene un puntero a un `ICorDebugValue` que representa el valor de una variable local, de los cuales los bits superiores se almacenan en el registro especificado y los bits inferiores se almacenan en la dirección de memoria especificada</span><span class="sxs-lookup"><span data-stu-id="a3589-118">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable, of which the high bits are stored in the specified register and the low bits are stored at the specified memory address</span></span>|  
|[<span data-ttu-id="a3589-119">GetLocalRegisterValue (método)</span><span class="sxs-lookup"><span data-stu-id="a3589-119">GetLocalRegisterValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistervalue-method.md)|<span data-ttu-id="a3589-120">Obtiene un puntero a un `ICorDebugValue` que representa el valor de un argumento o una variable local almacenada en el registro nativo especificado.</span><span class="sxs-lookup"><span data-stu-id="a3589-120">Gets a pointer to an `ICorDebugValue` that represents the value of an argument or a local variable stored in the specified native register.</span></span>|  
|[<span data-ttu-id="a3589-121">GetRegisterSet (método)</span><span class="sxs-lookup"><span data-stu-id="a3589-121">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getregisterset-method.md)|<span data-ttu-id="a3589-122">Obtiene un puntero a un [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) que representa el conjunto de registros para este `ICorDebugNativeFrame`.</span><span class="sxs-lookup"><span data-stu-id="a3589-122">Gets a pointer to an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) that represents the register set for this `ICorDebugNativeFrame`.</span></span>|  
|[<span data-ttu-id="a3589-123">SetIP (método)</span><span class="sxs-lookup"><span data-stu-id="a3589-123">SetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md)|<span data-ttu-id="a3589-124">Establece el puntero de instrucción en la ubicación de desplazamiento especificada en el código nativo.</span><span class="sxs-lookup"><span data-stu-id="a3589-124">Sets the instruction pointer to the specified offset location in native code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3589-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a3589-125">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a3589-126">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="a3589-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3589-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a3589-127">Requirements</span></span>  
 <span data-ttu-id="a3589-128">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3589-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3589-129">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a3589-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a3589-130">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3589-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3589-131">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3589-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3589-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="a3589-132">See Also</span></span>  
 [<span data-ttu-id="a3589-133">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="a3589-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)