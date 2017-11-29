---
title: "IMetaDataAssemblyEmit::SetExportedTypeProps (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit.SetExportedTypeProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit::SetExportedTypeProps
helpviewer_keywords:
- SetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 1c090153-fd5f-46c7-9cff-39a78d992c8f
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c41cc2c6433139f1e1f355585e4af0a8f01c7c94
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyemitsetexportedtypeprops-method"></a><span data-ttu-id="467da-102">IMetaDataAssemblyEmit::SetExportedTypeProps (Método)</span><span class="sxs-lookup"><span data-stu-id="467da-102">IMetaDataAssemblyEmit::SetExportedTypeProps Method</span></span>
<span data-ttu-id="467da-103">Modifica la estructura de metadatos `ExportedType` especificada.</span><span class="sxs-lookup"><span data-stu-id="467da-103">Modifies the specified `ExportedType` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="467da-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="467da-104">Syntax</span></span>  
  
```  
HRESULT SetExportedTypeProps (  
    [in] mdExportedType   ct,   
    [in] mdToken          tkImplementation,  
    [in] mdTypeDef        tkTypeDef,  
    [in] DWORD            dwExportedTypeFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="467da-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="467da-105">Parameters</span></span>  
 `ct`  
 <span data-ttu-id="467da-106">[in] El token de metadatos que especifica el `ExportedType` estructura de metadatos que puede modificar.</span><span class="sxs-lookup"><span data-stu-id="467da-106">[in] The metadata token that specifies the `ExportedType` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="467da-107">[in] El token de tipo `File`, `AssemblyRef`, o `ExportedType`, que especifica cómo se implementa este tipo.</span><span class="sxs-lookup"><span data-stu-id="467da-107">[in] The token, of type `File`, `AssemblyRef`, or `ExportedType`, that specifies how this type is implemented.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="467da-108">[in] El `TypeDef` token al que hace referencia en el archivo de código.</span><span class="sxs-lookup"><span data-stu-id="467da-108">[in] The `TypeDef` token referenced in the code file.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="467da-109">[in] Una combinación bit a bit de valores que especifican los atributos del tipo.</span><span class="sxs-lookup"><span data-stu-id="467da-109">[in] A bitwise combination of values that specify attributes of the type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="467da-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="467da-110">Remarks</span></span>  
 <span data-ttu-id="467da-111">Para crear un `ExportedType` estructura de los metadatos, use la [IMetaDataAssemblyEmit:: DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="467da-111">To create an `ExportedType` metadata structure, use the [IMetaDataAssemblyEmit::DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="467da-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="467da-112">Requirements</span></span>  
 <span data-ttu-id="467da-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="467da-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="467da-114">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="467da-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="467da-115">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="467da-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="467da-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="467da-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="467da-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="467da-117">See Also</span></span>  
 [<span data-ttu-id="467da-118">IMetaDataAssemblyEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="467da-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)