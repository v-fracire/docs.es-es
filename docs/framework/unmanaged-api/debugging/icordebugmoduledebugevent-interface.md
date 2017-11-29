---
title: ICorDebugModuleDebugEvent (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 41950c52-1ac8-4212-b814-c77e20879f91
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dced93ab39529ec57fb6fb99603a197fb957be8d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmoduledebugevent-interface"></a><span data-ttu-id="f7e6c-102">ICorDebugModuleDebugEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f7e6c-102">ICorDebugModuleDebugEvent Interface</span></span>
<span data-ttu-id="f7e6c-103">Extiende la [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interfaz para admitir eventos de nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="f7e6c-103">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support module-level events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f7e6c-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="f7e6c-104">Methods</span></span>  
  
|<span data-ttu-id="f7e6c-105">Método</span><span class="sxs-lookup"><span data-stu-id="f7e6c-105">Method</span></span>|<span data-ttu-id="f7e6c-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="f7e6c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f7e6c-107">GetModule (método)</span><span class="sxs-lookup"><span data-stu-id="f7e6c-107">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-getmodule-method.md)|<span data-ttu-id="f7e6c-108">Obtiene el módulo combinado que se acaba de cargar o descargar.</span><span class="sxs-lookup"><span data-stu-id="f7e6c-108">Gets the merged module that was just loaded or unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f7e6c-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f7e6c-109">Remarks</span></span>  
 <span data-ttu-id="f7e6c-110">El [MODULE_LOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) y [MODULE_UNLOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) tipos de evento implementan esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="f7e6c-110">The [MODULE_LOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) and [MODULE_UNLOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) event types implement this interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f7e6c-111">La interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f7e6c-111">The interface is available with .NET Native only.</span></span> <span data-ttu-id="f7e6c-112">Al intentar llamar a `QueryInterface` para recuperar un puntero a interfaz, devuelve `E_NOINTERFACE` para escenarios de ICorDebug fuera de .NET nativo.</span><span class="sxs-lookup"><span data-stu-id="f7e6c-112">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7e6c-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f7e6c-113">Requirements</span></span>  
 <span data-ttu-id="f7e6c-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7e6c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7e6c-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f7e6c-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f7e6c-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7e6c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f7e6c-117">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7e6c-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7e6c-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7e6c-118">See Also</span></span>  
 [<span data-ttu-id="f7e6c-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="f7e6c-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="f7e6c-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="f7e6c-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)