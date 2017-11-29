---
title: "Función PutInstanceWmi (referencia de API no administrada)"
description: "La función PutInstanceWmi crea o actualiza una instancia de una clase existente."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: PutInstanceWmi
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: PutInstanceWmi
helpviewer_keywords: PutInstanceWmi function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b7a4ffce4789fb59d84778d02b41910c974216bd
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="putinstancewmi-function"></a><span data-ttu-id="7160f-103">PutInstanceWmi (función)</span><span class="sxs-lookup"><span data-stu-id="7160f-103">PutInstanceWmi function</span></span>
<span data-ttu-id="7160f-104">Crea o actualiza una instancia de una clase existente.</span><span class="sxs-lookup"><span data-stu-id="7160f-104">Creates or updates an instance of an existing class.</span></span> <span data-ttu-id="7160f-105">La instancia se escribe en el repositorio de WMI.</span><span class="sxs-lookup"><span data-stu-id="7160f-105">The instance is written to the WMI repository.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="7160f-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7160f-106">Syntax</span></span>  
  
```  
HRESULT PutInstanceWmi (
   [in] IWbemClassObject*    pInst,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
); 
```  

## <a name="parameters"></a><span data-ttu-id="7160f-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7160f-107">Parameters</span></span>

`pInst`    
<span data-ttu-id="7160f-108">[in] Un puntero a la instancia sea escritos.</span><span class="sxs-lookup"><span data-stu-id="7160f-108">[in] A pointer to the instance to be writen.</span></span>

`lFlags`   
<span data-ttu-id="7160f-109">[in] Una combinación de indicadores que afectan al comportamiento de esta función.</span><span class="sxs-lookup"><span data-stu-id="7160f-109">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="7160f-110">Los valores siguientes se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="7160f-110">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span> 

|<span data-ttu-id="7160f-111">Constante</span><span class="sxs-lookup"><span data-stu-id="7160f-111">Constant</span></span>  |<span data-ttu-id="7160f-112">Valor</span><span class="sxs-lookup"><span data-stu-id="7160f-112">Value</span></span>  |<span data-ttu-id="7160f-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="7160f-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="7160f-114">0 x 20000</span><span class="sxs-lookup"><span data-stu-id="7160f-114">0x20000</span></span> | <span data-ttu-id="7160f-115">Si se establece, WMI no almacena los calificadores con el **modificado** flavor.</span><span class="sxs-lookup"><span data-stu-id="7160f-115">If set, WMI does not store any qualifiers with the **Amended** flavor.</span></span> </br> <span data-ttu-id="7160f-116">Si no conjunto, se supone que no se localiza este objeto y todos los calificadores son storedwith esta instancia.</span><span class="sxs-lookup"><span data-stu-id="7160f-116">If not set, it is assumed that this object is not localized, and all qualifiers are storedwith this instance.</span></span> |
| `WBEM_FLAG_CREATE_OR_UPDATE` | <span data-ttu-id="7160f-117">0</span><span class="sxs-lookup"><span data-stu-id="7160f-117">0</span></span> | <span data-ttu-id="7160f-118">Crear la instancia si no existe, o sobrescribirlo si ya existe.</span><span class="sxs-lookup"><span data-stu-id="7160f-118">Create the instance if it does not exist, or overwrite it if it exists already.</span></span> |
| `WBEM_FLAG_UPDATE_ONLY` | <span data-ttu-id="7160f-119">1</span><span class="sxs-lookup"><span data-stu-id="7160f-119">1</span></span> | <span data-ttu-id="7160f-120">Actualizar la instancia.</span><span class="sxs-lookup"><span data-stu-id="7160f-120">Update the instance.</span></span> <span data-ttu-id="7160f-121">Debe existir la instancia de la llamada se realice correctamente.</span><span class="sxs-lookup"><span data-stu-id="7160f-121">The instance must exist for the call to be successful.</span></span> |
| `WBEM_FLAG_CREATE_ONLY` | <span data-ttu-id="7160f-122">2</span><span class="sxs-lookup"><span data-stu-id="7160f-122">2</span></span> | <span data-ttu-id="7160f-123">Crear la instancia.</span><span class="sxs-lookup"><span data-stu-id="7160f-123">Create the instance.</span></span> <span data-ttu-id="7160f-124">Se produce un error en la llamada si la instancia ya existe.</span><span class="sxs-lookup"><span data-stu-id="7160f-124">The call fails if the instance already exists.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="7160f-125">0 x 10</span><span class="sxs-lookup"><span data-stu-id="7160f-125">0x10</span></span> | <span data-ttu-id="7160f-126">La marca hace una llamada semisincrónica.</span><span class="sxs-lookup"><span data-stu-id="7160f-126">The flag causes a semisynchronous call.</span></span> |

`pCtx`  
<span data-ttu-id="7160f-127">[in] Normalmente, este valor es `null`.</span><span class="sxs-lookup"><span data-stu-id="7160f-127">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="7160f-128">En caso contrario, es un puntero a un [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) instancia que se puede usar el proveedor que proporciona las clases solicitadas.</span><span class="sxs-lookup"><span data-stu-id="7160f-128">Otherwise, it is a pointer to an [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) instance that can be used by the provider that is providing the requested classes.</span></span> 

`ppCallResult`  
<span data-ttu-id="7160f-129">[out] Si `null`, este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="7160f-129">[out] If `null`, this parameter is unused.</span></span> <span data-ttu-id="7160f-130">Si `lFlags` contiene `WBEM_FLAG_RETURN_IMMEDIATELY`, la función devuelve inmediatamente con `WBEM_S_NO_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="7160f-130">If `lFlags` contains `WBEM_FLAG_RETURN_IMMEDIATELY`, the function returns immediately with `WBEM_S_NO_ERROR`.</span></span> <span data-ttu-id="7160f-131">El `ppCallResult` parámetro recibe un puntero a una nueva [IWbemCallResult](https://msdn.microsoft.com/library/aa391425(v=vs.85).aspx) objeto.</span><span class="sxs-lookup"><span data-stu-id="7160f-131">The `ppCallResult` parameter receives a pointer to a new [IWbemCallResult](https://msdn.microsoft.com/library/aa391425(v=vs.85).aspx) object.</span></span>

## <a name="return-value"></a><span data-ttu-id="7160f-132">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7160f-132">Return value</span></span>

<span data-ttu-id="7160f-133">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="7160f-133">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="7160f-134">Constante</span><span class="sxs-lookup"><span data-stu-id="7160f-134">Constant</span></span>  |<span data-ttu-id="7160f-135">Valor</span><span class="sxs-lookup"><span data-stu-id="7160f-135">Value</span></span>  |<span data-ttu-id="7160f-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="7160f-136">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="7160f-137">0x80041003</span><span class="sxs-lookup"><span data-stu-id="7160f-137">0x80041003</span></span> | <span data-ttu-id="7160f-138">El usuario no tiene permiso para actualizar una instancia de la clase especificada.</span><span class="sxs-lookup"><span data-stu-id="7160f-138">The user does not have permission to update an instance of the specified class.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="7160f-139">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="7160f-139">0x80041001</span></span> | <span data-ttu-id="7160f-140">Se ha producido un error no especificado.</span><span class="sxs-lookup"><span data-stu-id="7160f-140">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="7160f-141">0 x 80041010</span><span class="sxs-lookup"><span data-stu-id="7160f-141">0x80041010</span></span> | <span data-ttu-id="7160f-142">La clase compatible con esta instancia no es válida.</span><span class="sxs-lookup"><span data-stu-id="7160f-142">The class supporting this instance is not valid.</span></span> |
| `WBEM_E_ILLEGAL_NULL` | <span data-ttu-id="7160f-143">0x80041028</span><span class="sxs-lookup"><span data-stu-id="7160f-143">0x80041028</span></span> | <span data-ttu-id="7160f-144">un `null` no se especificó para una propiedad que no puede ser `null`, como uno que esté marcada con un **indexado** o **Not_Null** calificador.</span><span class="sxs-lookup"><span data-stu-id="7160f-144">a `null` was specified for a property that cannot be `null`, such as one that is marked by an **Indexed** or **Not_Null** qualifier.</span></span> |
| `WBEM_E_INVALID_OBJECT` | <span data-ttu-id="7160f-145">0x8004100f</span><span class="sxs-lookup"><span data-stu-id="7160f-145">0x8004100f</span></span> | <span data-ttu-id="7160f-146">La instancia especificada no es válida.</span><span class="sxs-lookup"><span data-stu-id="7160f-146">The specified instance is not valid.</span></span> <span data-ttu-id="7160f-147">(Por ejemplo, al llamar a `PutInstanceWmi` con una clase devuelve este valor.)</span><span class="sxs-lookup"><span data-stu-id="7160f-147">(For example, calling `PutInstanceWmi` with a class returns this value.)</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="7160f-148">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="7160f-148">0x80041008</span></span> | <span data-ttu-id="7160f-149">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="7160f-149">A parameter is not valid.</span></span> |
| `WBEM_E_ALREADY_EXISTS` | <span data-ttu-id="7160f-150">0x80041019</span><span class="sxs-lookup"><span data-stu-id="7160f-150">0x80041019</span></span> | <span data-ttu-id="7160f-151">El `WBEM_FLAG_CREATE_ONLY` se especificó la marca, pero la instancia ya existe.</span><span class="sxs-lookup"><span data-stu-id="7160f-151">The `WBEM_FLAG_CREATE_ONLY` flag was specified, but the instance already exists.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="7160f-152">0x80041002</span><span class="sxs-lookup"><span data-stu-id="7160f-152">0x80041002</span></span> | <span data-ttu-id="7160f-153">`WBEM_FLAG_UPDATE_ONLY`no se especificó en `lFlags`, pero la instancia no existe.</span><span class="sxs-lookup"><span data-stu-id="7160f-153">`WBEM_FLAG_UPDATE_ONLY` was specified in `lFlags`, but the instance does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="7160f-154">0 x 80041006</span><span class="sxs-lookup"><span data-stu-id="7160f-154">0x80041006</span></span> | <span data-ttu-id="7160f-155">No hay suficiente memoria disponible para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="7160f-155">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="7160f-156">0x80041033</span><span class="sxs-lookup"><span data-stu-id="7160f-156">0x80041033</span></span> | <span data-ttu-id="7160f-157">WMI se ha detenido probablemente y reiniciar.</span><span class="sxs-lookup"><span data-stu-id="7160f-157">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="7160f-158">Llame a [ConnectServerWmi](connectserverwmi.md) nuevo.</span><span class="sxs-lookup"><span data-stu-id="7160f-158">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="7160f-159">0x80041015</span><span class="sxs-lookup"><span data-stu-id="7160f-159">0x80041015</span></span> | <span data-ttu-id="7160f-160">Error en el vínculo de procedimiento remoto (RPC) de la llamada entre el proceso actual y WMI.</span><span class="sxs-lookup"><span data-stu-id="7160f-160">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="7160f-161">0</span><span class="sxs-lookup"><span data-stu-id="7160f-161">0</span></span> | <span data-ttu-id="7160f-162">La llamada de función tuvo éxito.</span><span class="sxs-lookup"><span data-stu-id="7160f-162">The function call was successful.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="7160f-163">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7160f-163">Remarks</span></span>

<span data-ttu-id="7160f-164">Esta función contiene una llamada a la [IWbemServices::PutInstance](https://msdn.microsoft.com/library/aa392115(v=vs.85).aspx) método.</span><span class="sxs-lookup"><span data-stu-id="7160f-164">This function wraps a call to the [IWbemServices::PutInstance](https://msdn.microsoft.com/library/aa392115(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="7160f-165">El `PutInstanceWmi` función admite la creación de instancias y la actualización de instancias de clases existentes solo.</span><span class="sxs-lookup"><span data-stu-id="7160f-165">The `PutInstanceWmi` function supports creating instances and updating instances of existing classes only.</span></span>  <span data-ttu-id="7160f-166">Función de la configuración `pCtx` parámetro se establece, se actualizan algunas o todas las propiedades de la instancia.</span><span class="sxs-lookup"><span data-stu-id="7160f-166">Depending on how the `pCtx` parameter is set, either some or all of the properties of the instance are updated.</span></span> 

<span data-ttu-id="7160f-167">Cuando la instancia que señala `pInst` pertenece a una subclase, administración de Windows llama todos los proveedores responsables de las clases de la que deriva la subclase.</span><span class="sxs-lookup"><span data-stu-id="7160f-167">When the instance pointed to by `pInst` belongs to a subclass, Windows Management calls all the providers responsible for the classes from which the subclass derives.</span></span> <span data-ttu-id="7160f-168">Todos estos proveedores deben ejecutarse correctamente para la versión original `PutInstanceWmi` solicitud se realice correctamente.</span><span class="sxs-lookup"><span data-stu-id="7160f-168">All of these providers must succeed for the original `PutInstanceWmi` request to succeed.</span></span> <span data-ttu-id="7160f-169">El proveedor de compatibilidad de la clase de nivel superior en la jerarquía se llama en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="7160f-169">The provider supporting the topmost class in the hierarchy is called first.</span></span> <span data-ttu-id="7160f-170">El orden de llamada continúa con la subclase de la clase de nivel superior y continúa de arriba a abajo hasta que alcance de administración de Windows del proveedor para la clase propietaria de la instancia que señala `pInst`.</span><span class="sxs-lookup"><span data-stu-id="7160f-170">The calling order continues with the subclass of the topmost class and proceeds from top to bottom until Windows Management reaches the provider for the class owning the instance pointed to by `pInst`.</span></span>
<span data-ttu-id="7160f-171">Administración de Windows no llama a los proveedores para cualquiera de las clases secundarias de una instancia.</span><span class="sxs-lookup"><span data-stu-id="7160f-171">Windows Management does not call the providers for any of the child classes of an instance.</span></span> 

<span data-ttu-id="7160f-172">Cuando una aplicación debe actualizar una instancia que pertenece a una jerarquía de clases, el `pInst` parámetro debe apuntar a la instancia que contiene las propiedades que se pueden modificar.</span><span class="sxs-lookup"><span data-stu-id="7160f-172">When an application must update an instance that belongs to a class hierarchy, the `pInst` parameter must point to the instance containing the properties to be modified.</span></span> <span data-ttu-id="7160f-173">Es decir, considere la posibilidad de una instancia de destino pertenece a **ClassB**.</span><span class="sxs-lookup"><span data-stu-id="7160f-173">That is, consider a target instance that belongs to **ClassB**.</span></span> <span data-ttu-id="7160f-174">El **ClassB** deriva instancia **ClassA**, y **ClassA** define la propiedad **PropA**.</span><span class="sxs-lookup"><span data-stu-id="7160f-174">The **ClassB** instance derives from **ClassA**, and **ClassA** defines the property **PropA**.</span></span> <span data-ttu-id="7160f-175">Si una aplicación desea volver a realizar un cambio en el valor de **PropA** en el **ClassB** instancia, se debe establecer `pInst` a esa instancia en lugar de una instancia de **ClassA** .</span><span class="sxs-lookup"><span data-stu-id="7160f-175">If an application wants to make a change to the value of **PropA** in the **ClassB** instance, it must set `pInst` to that instance rather than an instance of **ClassA**.</span></span>

<span data-ttu-id="7160f-176">Al llamar a `PutInstanceWmi` no se permite en una instancia de una clase abstracta.</span><span class="sxs-lookup"><span data-stu-id="7160f-176">Calling `PutInstanceWmi` on an instance of an abstract class is not allowed.</span></span>

<span data-ttu-id="7160f-177">Si se produce un error en la llamada de función, puede obtener información de error adicional mediante una llamada a la [GetErrorInfo](geterrorinfo.md) función.</span><span class="sxs-lookup"><span data-stu-id="7160f-177">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="7160f-178">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7160f-178">Requirements</span></span>  
 <span data-ttu-id="7160f-179">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7160f-179">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7160f-180">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="7160f-180">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="7160f-181">**Versiones de .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7160f-181">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7160f-182">Vea también</span><span class="sxs-lookup"><span data-stu-id="7160f-182">See also</span></span>  
[<span data-ttu-id="7160f-183">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="7160f-183">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)