---
title: Nombres seguros (Referencia de la API no administrada)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- strong naming [.NET Framework], using the unmanaged API
- native API reference [.NET Framework], strong naming
- unmanaged API reference [.NET Framework], strong naming
ms.assetid: 428c68b6-a7b4-44be-b280-75905f46612c
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 86d741a16a0293892d0d6d90f1763d744ed3675d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="strong-naming-unmanaged-api-reference"></a><span data-ttu-id="c9ca7-102">Nombres seguros (Referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="c9ca7-102">Strong Naming (Unmanaged API Reference)</span></span>
<span data-ttu-id="c9ca7-103">La API de nombres seguros permite a un cliente administrar la firma de ensamblados con nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="c9ca7-103">The strong naming API enables a client to administer strong name signing for assemblies.</span></span>  
  
 <span data-ttu-id="c9ca7-104">Al firmar un ensamblado con un nombre seguro, se agrega un cifrado mediante clave pública al archivo que contiene el manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c9ca7-104">Signing an assembly with a strong name adds a public key encryption to the file containing the assembly manifest.</span></span> <span data-ttu-id="c9ca7-105">Firmar con nombres seguros ayuda a comprobar la exclusividad del nombre, impide la simulación de nombres y no proporciona una identidad única a los llamadores cuando se resuelve una referencia.</span><span class="sxs-lookup"><span data-stu-id="c9ca7-105">Strong name signing helps verify name uniqueness, prevents name spoofing, and provides callers with a unique identity when a reference is resolved.</span></span> <span data-ttu-id="c9ca7-106">Sin embargo, ningún nivel de confianza está asociado con un nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="c9ca7-106">However, no level of trust is associated with a strong name.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c9ca7-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c9ca7-107">In This Section</span></span>  
 [<span data-ttu-id="c9ca7-108">Las funciones estáticas globales de nombres seguros</span><span class="sxs-lookup"><span data-stu-id="c9ca7-108">Strong Naming Global Static Functions</span></span>](http://msdn.microsoft.com/en-us/efa715df-e8cc-48f2-9ec4-26586f0dc8d0)  
 <span data-ttu-id="c9ca7-109">Describe las funciones estáticas globales no administradas que utiliza la API de nombres seguros.</span><span class="sxs-lookup"><span data-stu-id="c9ca7-109">Describes the unmanaged global static functions that the strong naming API uses.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c9ca7-110">Todas estas funciones han quedado en desuso a partir de la [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9ca7-110">All of these functions have been deprecated starting with the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="c9ca7-111">Para alternativas sugeridas, consulte el [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="c9ca7-111">For suggested alternatives, see the [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) interface.</span></span>  
  
 [<span data-ttu-id="c9ca7-112">GetHashFromAssemblyFile (función)</span><span class="sxs-lookup"><span data-stu-id="c9ca7-112">GetHashFromAssemblyFile Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromassemblyfile-function.md)  
 <span data-ttu-id="c9ca7-113">Obtiene un valor hash del archivo de ensamblado especificado, utilizando el algoritmo hash especificado.</span><span class="sxs-lookup"><span data-stu-id="c9ca7-113">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span> <span data-ttu-id="c9ca7-114">En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9ca7-114">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c9ca7-115">GetHashFromAssemblyFileW (función)</span><span class="sxs-lookup"><span data-stu-id="c9ca7-115">GetHashFromAssemblyFileW Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromassemblyfilew-function.md)  
 <span data-ttu-id="c9ca7-116">Obtiene un valor hash del archivo de ensamblado especificado como una cadena Unicode, mediante el algoritmo hash especificado.</span><span class="sxs-lookup"><span data-stu-id="c9ca7-116">Gets a hash of the assembly file specified as a Unicode string, using the specified hash algorithm.</span></span> <span data-ttu-id="c9ca7-117">En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9ca7-117">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c9ca7-118">GetHashFromBlob (función)</span><span class="sxs-lookup"><span data-stu-id="c9ca7-118">GetHashFromBlob Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromblob-function.md)  
 <span data-ttu-id="c9ca7-119">Obtiene un valor hash del ensamblado en la dirección de memoria especificada, utilizando el algoritmo hash especificado.</span><span class="sxs-lookup"><span data-stu-id="c9ca7-119">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span> <span data-ttu-id="c9ca7-120">En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9ca7-120">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c9ca7-121">GetHashFromFile (función)</span><span class="sxs-lookup"><span data-stu-id="c9ca7-121">GetHashFromFile Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfile-function.md)  
 <span data-ttu-id="c9ca7-122">Genera un hash sobre el contenido del archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="c9ca7-122">Generates a hash over the contents of the specified file.</span></span>  <span data-ttu-id="c9ca7-123">En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9ca7-123">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c9ca7-124">GetHashFromFileW (función)</span><span class="sxs-lookup"><span data-stu-id="c9ca7-124">GetHashFromFileW Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfilew-function.md)  
 <span data-ttu-id="c9ca7-125">Genera un hash sobre el contenido del archivo especificado por una cadena Unicode.</span><span class="sxs-lookup"><span data-stu-id="c9ca7-125">Generates a hash over the contents of the file specified by a Unicode string.</span></span> <span data-ttu-id="c9ca7-126">En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9ca7-126">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c9ca7-127">GetHashFromHandle (función)</span><span class="sxs-lookup"><span data-stu-id="c9ca7-127">GetHashFromHandle Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromhandle-function.md)  
 <span data-ttu-id="c9ca7-128">Genera un hash sobre el contenido del archivo con el identificador de archivo especificado, utilizando el algoritmo hash especificado.</span><span class="sxs-lookup"><span data-stu-id="c9ca7-128">Generates a hash over the contents of the file with the specified file handle, using the specified hash algorithm.</span></span>  <span data-ttu-id="c9ca7-129">En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9ca7-129">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c9ca7-130">StrongNameCompareAssemblies (función)</span><span class="sxs-lookup"><span data-stu-id="c9ca7-130">StrongNameCompareAssemblies Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamecompareassemblies-function.md)  
 <span data-ttu-id="c9ca7-131">Determina si dos ensamblados difieren solo en sus firmas de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="c9ca7-131">Determines whether two assemblies differ only by their strong name signatures.</span></span> <span data-ttu-id="c9ca7-132">En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9ca7-132">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c9ca7-133">StrongNameErrorInfo (función)</span><span class="sxs-lookup"><span data-stu-id="c9ca7-133">StrongNameErrorInfo Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)  
 <span data-ttu-id="c9ca7-134">Obtiene el último código de error que se genera mediante una de las funciones de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="c9ca7-134">Gets the last error code that was raised by one of the strong name functions.</span></span>  
  
 [<span data-ttu-id="c9ca7-135">StrongNameFreeBuffer (función)</span><span class="sxs-lookup"><span data-stu-id="c9ca7-135">StrongNameFreeBuffer Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md)  
 <span data-ttu-id="c9ca7-136">Libera la memoria que se asignó con una llamada anterior a una función de nombre seguro como [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md), o [StrongNameSignatureGeneration ](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md).</span><span class="sxs-lookup"><span data-stu-id="c9ca7-136">Frees memory that was allocated with a previous call to a strong name function such as [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md), or [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md).</span></span>   <span data-ttu-id="c9ca7-137">En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9ca7-137">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c9ca7-138">StrongNameGetBlob (función)</span><span class="sxs-lookup"><span data-stu-id="c9ca7-138">StrongNameGetBlob Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetblob-function.md)  
 <span data-ttu-id="c9ca7-139">Llena el búfer especificado con la representación binaria del archivo ejecutable en la dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="c9ca7-139">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span> <span data-ttu-id="c9ca7-140">En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9ca7-140">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c9ca7-141">StrongNameGetBlobFromImage (función)</span><span class="sxs-lookup"><span data-stu-id="c9ca7-141">StrongNameGetBlobFromImage Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetblobfromimage-function.md)  
 <span data-ttu-id="c9ca7-142">Obtiene una representación binaria de la imagen de ensamblado en la dirección de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="c9ca7-142">Gets a binary representation of the assembly image at the specified memory address.</span></span> <span data-ttu-id="c9ca7-143">En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9ca7-143">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c9ca7-144">StrongNameGetPublicKey (función)</span><span class="sxs-lookup"><span data-stu-id="c9ca7-144">StrongNameGetPublicKey Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)  
 <span data-ttu-id="c9ca7-145">Obtiene la clave pública de un par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="c9ca7-145">Gets the public key from a private/public key pair.</span></span> <span data-ttu-id="c9ca7-146">En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9ca7-146">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c9ca7-147">StrongNameHashSize (función)</span><span class="sxs-lookup"><span data-stu-id="c9ca7-147">StrongNameHashSize Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamehashsize-function.md)  
 <span data-ttu-id="c9ca7-148">Obtiene el tamaño de búfer requerido para un hash mediante el algoritmo hash especificado.</span><span class="sxs-lookup"><span data-stu-id="c9ca7-148">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  <span data-ttu-id="c9ca7-149">En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9ca7-149">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c9ca7-150">StrongNameKeyDelete (función)</span><span class="sxs-lookup"><span data-stu-id="c9ca7-150">StrongNameKeyDelete Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeydelete-function.md)  
 <span data-ttu-id="c9ca7-151">Elimina el contenedor de claves especificado.</span><span class="sxs-lookup"><span data-stu-id="c9ca7-151">Deletes the specified key container.</span></span> <span data-ttu-id="c9ca7-152">En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9ca7-152">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c9ca7-153">StrongNameKeyGen (función)</span><span class="sxs-lookup"><span data-stu-id="c9ca7-153">StrongNameKeyGen Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeygen-function.md)  
 <span data-ttu-id="c9ca7-154">Crea un nuevo par de claves pública y privada para su uso de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="c9ca7-154">Creates a new public/private key pair for strong name use.</span></span>  <span data-ttu-id="c9ca7-155">En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9ca7-155">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c9ca7-156">StrongNameKeyGenEx (función)</span><span class="sxs-lookup"><span data-stu-id="c9ca7-156">StrongNameKeyGenEx Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeygenex-function.md)  
 <span data-ttu-id="c9ca7-157">Genera un nuevo par de claves pública/privada con el tamaño de clave especificado para su uso de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="c9ca7-157">Generates a new public/private key pair with the specified key size for strong name use.</span></span> <span data-ttu-id="c9ca7-158">En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9ca7-158">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c9ca7-159">StrongNameKeyInstall (función)</span><span class="sxs-lookup"><span data-stu-id="c9ca7-159">StrongNameKeyInstall Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeyinstall-function.md)  
 <span data-ttu-id="c9ca7-160">Importa un par de claves pública/privada en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="c9ca7-160">Imports a public/private key pair into a container.</span></span>  <span data-ttu-id="c9ca7-161">En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9ca7-161">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c9ca7-162">StrongNameSignatureGeneration (función)</span><span class="sxs-lookup"><span data-stu-id="c9ca7-162">StrongNameSignatureGeneration Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)  
 <span data-ttu-id="c9ca7-163">Genera una firma de nombre seguro para el ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="c9ca7-163">Generates a strong name signature for the specified assembly.</span></span>   <span data-ttu-id="c9ca7-164">En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9ca7-164">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c9ca7-165">StrongNameSignatureGenerationEx (función)</span><span class="sxs-lookup"><span data-stu-id="c9ca7-165">StrongNameSignatureGenerationEx Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegenerationex-function.md)  
 <span data-ttu-id="c9ca7-166">Genera una firma de nombre seguro para el ensamblado especificado, en función de las marcas especificadas.</span><span class="sxs-lookup"><span data-stu-id="c9ca7-166">Generates a strong name signature for the specified assembly, based on the specified flags.</span></span>    <span data-ttu-id="c9ca7-167">En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9ca7-167">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c9ca7-168">StrongNameSignatureSize (función)</span><span class="sxs-lookup"><span data-stu-id="c9ca7-168">StrongNameSignatureSize Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md)  
 <span data-ttu-id="c9ca7-169">Devuelve el tamaño de la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="c9ca7-169">Returns the size of the strong name signature.</span></span> <span data-ttu-id="c9ca7-170">En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9ca7-170">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c9ca7-171">StrongNameSignatureVerification (función)</span><span class="sxs-lookup"><span data-stu-id="c9ca7-171">StrongNameSignatureVerification Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md)  
 <span data-ttu-id="c9ca7-172">Obtiene un valor que indica si el manifiesto del ensamblado en la ruta de acceso proporcionada contiene una firma de nombre seguro, que se comprueba según los marcadores especificados.</span><span class="sxs-lookup"><span data-stu-id="c9ca7-172">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature, which is verified according to the specified flags.</span></span> <span data-ttu-id="c9ca7-173">En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9ca7-173">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c9ca7-174">StrongNameSignatureVerificationEx (función)</span><span class="sxs-lookup"><span data-stu-id="c9ca7-174">StrongNameSignatureVerificationEx Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverificationex-function.md)  
 <span data-ttu-id="c9ca7-175">Obtiene un valor que indica si el manifiesto del ensamblado en la ruta de acceso proporcionada contiene una firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="c9ca7-175">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  <span data-ttu-id="c9ca7-176">En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9ca7-176">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c9ca7-177">StrongNameSignatureVerificationFromImage (función)</span><span class="sxs-lookup"><span data-stu-id="c9ca7-177">StrongNameSignatureVerificationFromImage Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverificationfromimage-function.md)  
 <span data-ttu-id="c9ca7-178">Comprueba que un ensamblado que ya se ha asignado a la memoria es válido para la clave pública asociada.</span><span class="sxs-lookup"><span data-stu-id="c9ca7-178">Verifies that an assembly that has already been mapped to memory is valid for the associated public key.</span></span> <span data-ttu-id="c9ca7-179">En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9ca7-179">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c9ca7-180">StrongNameTokenFromAssembly (función)</span><span class="sxs-lookup"><span data-stu-id="c9ca7-180">StrongNameTokenFromAssembly Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md)  
 <span data-ttu-id="c9ca7-181">Crea un token de nombre seguro del archivo de ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="c9ca7-181">Creates a strong name token from the specified assembly file.</span></span>  <span data-ttu-id="c9ca7-182">En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9ca7-182">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c9ca7-183">StrongNameTokenFromAssemblyEx (función)</span><span class="sxs-lookup"><span data-stu-id="c9ca7-183">StrongNameTokenFromAssemblyEx Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassemblyex-function.md)  
 <span data-ttu-id="c9ca7-184">Crea un token de nombre seguro del archivo de ensamblado especificado y devuelve la clave pública.</span><span class="sxs-lookup"><span data-stu-id="c9ca7-184">Creates a strong name token from the specified assembly file, and returns the public key.</span></span> <span data-ttu-id="c9ca7-185">En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9ca7-185">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c9ca7-186">StrongNameTokenFromPublicKey (función)</span><span class="sxs-lookup"><span data-stu-id="c9ca7-186">StrongNameTokenFromPublicKey Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md)  
 <span data-ttu-id="c9ca7-187">Obtiene un token que representa una clave pública.</span><span class="sxs-lookup"><span data-stu-id="c9ca7-187">Gets a token representing a public key.</span></span> <span data-ttu-id="c9ca7-188">En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9ca7-188">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c9ca7-189">Estructura de nombres seguros</span><span class="sxs-lookup"><span data-stu-id="c9ca7-189">Strong Naming Structure</span></span>](http://msdn.microsoft.com/en-us/4b041a2f-fd12-4b91-aacd-bc3b34a5124d)  
 <span data-ttu-id="c9ca7-190">Describe la estructura no administrada que utiliza la API de asignación de nombres seguros para administrar la firma de ensamblados con nombre seguro...</span><span class="sxs-lookup"><span data-stu-id="c9ca7-190">Describes the unmanaged structure that the strong naming API uses  to administer strong name signing for assemblies..</span></span>  
  
 [<span data-ttu-id="c9ca7-191">PublicKeyBlob (estructura)</span><span class="sxs-lookup"><span data-stu-id="c9ca7-191">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)  
 <span data-ttu-id="c9ca7-192">Representa la clave pública de un par de claves pública/privada en formato binario.</span><span class="sxs-lookup"><span data-stu-id="c9ca7-192">Represents the public key of a public/private key pair in binary format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9ca7-193">Vea también</span><span class="sxs-lookup"><span data-stu-id="c9ca7-193">See Also</span></span>  
 [<span data-ttu-id="c9ca7-194">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c9ca7-194">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)  
 [<span data-ttu-id="c9ca7-195">Referencia de API no administrada</span><span class="sxs-lookup"><span data-stu-id="c9ca7-195">Unmanaged API Reference</span></span>](../../../../docs/framework/unmanaged-api/index.md)