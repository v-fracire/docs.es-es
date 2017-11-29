---
title: "ISymUnmanagedReader2::GetMethodByVersionPreRemap (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader2.GetMethodByVersionPreRemap
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader2::GetMethodByVersionPreRemap
helpviewer_keywords:
- GetMethodByVersionPreRemap method [.NET Framework debugging]
- ISymUnmanagedReader2::GetMethodByVersionPreRemap method [.NET Framework debugging]
ms.assetid: 0d144ed4-bdb0-4cac-960c-cb90f4dca173
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 69a203424320a176cd285c23d98111e71709042a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreader2getmethodbyversionpreremap-method"></a><span data-ttu-id="172ba-102">ISymUnmanagedReader2::GetMethodByVersionPreRemap (Método)</span><span class="sxs-lookup"><span data-stu-id="172ba-102">ISymUnmanagedReader2::GetMethodByVersionPreRemap Method</span></span>
<span data-ttu-id="172ba-103">Obtiene un método del lector de símbolos, dado un token de método y un número de versión de editar y continuar.</span><span class="sxs-lookup"><span data-stu-id="172ba-103">Gets a symbol reader method, given a method token and an edit-and-continue version number.</span></span> <span data-ttu-id="172ba-104">Números de versión empiezan en 1 y se incrementan cada vez que se cambia el método como resultado de una operación de editar y continuar.</span><span class="sxs-lookup"><span data-stu-id="172ba-104">Version numbers start at 1 and are incremented each time the method is changed as a result of an edit-and-continue operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="172ba-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="172ba-105">Syntax</span></span>  
  
```  
HRESULT GetMethodByVersionPreRemap(  
    [in]  mdMethodDef token,  
    [in]  int version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="172ba-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="172ba-106">Parameters</span></span>  
 `token`  
 <span data-ttu-id="172ba-107">[in] El token de metadatos del método.</span><span class="sxs-lookup"><span data-stu-id="172ba-107">[in] The method metadata token.</span></span>  
  
 `version`  
 <span data-ttu-id="172ba-108">[in] La versión del método.</span><span class="sxs-lookup"><span data-stu-id="172ba-108">[in] The method version.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="172ba-109">[out] Un puntero para el valor devuelto [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="172ba-109">[out] A pointer to the returned [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="172ba-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="172ba-110">Return Value</span></span>  
 <span data-ttu-id="172ba-111">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="172ba-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="172ba-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="172ba-112">Requirements</span></span>  
 <span data-ttu-id="172ba-113">**Encabezado:** CorSym.idl.</span><span class="sxs-lookup"><span data-stu-id="172ba-113">**Header:** CorSym.idl.</span></span> <span data-ttu-id="172ba-114">CorSym.h</span><span class="sxs-lookup"><span data-stu-id="172ba-114">CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="172ba-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="172ba-115">See Also</span></span>  
 [<span data-ttu-id="172ba-116">ISymUnmanagedReader2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="172ba-116">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)