---
title: 'Funciones de Azure: aplicaciones sin servidor'
description: Las funciones de Azure proporcionan funcionalidades sin servidor en varios idiomas (C#, en JavaScript, Java) y plataformas para proporcionar controlado por eventos instantánea escalar código.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: f08ba20b485197acd3bb5cdfe5699cd6be991d7c
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2018
ms.locfileid: "49370193"
---
# <a name="azure-functions"></a><span data-ttu-id="b9754-103">Comprobación de</span><span class="sxs-lookup"><span data-stu-id="b9754-103">Azure Functions</span></span>

<span data-ttu-id="b9754-104">Azure functions proporciona una experiencia de proceso sin servidor.</span><span class="sxs-lookup"><span data-stu-id="b9754-104">Azure functions provide a serverless compute experience.</span></span> <span data-ttu-id="b9754-105">Invoca una función de un *desencadenador* (por ejemplo, el acceso a un punto de conexión HTTP o un temporizador) y ejecuta un bloque de código o la lógica empresarial.</span><span class="sxs-lookup"><span data-stu-id="b9754-105">A function is invoked by a *trigger* (such as access to an HTTP endpoint or a timer) and executes a block of code or business logic.</span></span> <span data-ttu-id="b9754-106">Las funciones también soporte técnico especializado *enlaces* que se conectan a recursos como almacenamiento y colas.</span><span class="sxs-lookup"><span data-stu-id="b9754-106">Functions also support specialized *bindings* that connect to resources like storage and queues.</span></span>

![Logotipo de Azure functions](./media/azure-functions-logo.png)

<span data-ttu-id="b9754-108">Hay dos versiones de framework de Azure Functions.</span><span class="sxs-lookup"><span data-stu-id="b9754-108">There are two versions of the Azure Functions framework.</span></span> <span data-ttu-id="b9754-109">La versión heredada es compatible con la versión completa de .NET Framework y el nuevo tiempo de ejecución es compatible con aplicaciones de .NET Core multiplataforma.</span><span class="sxs-lookup"><span data-stu-id="b9754-109">The legacy version supports the full .NET Framework and the new runtime supports cross-platform .NET Core applications.</span></span> <span data-ttu-id="b9754-110">Compatibilidad para idiomas adicionales además de C#, como JavaScript, F # y Java.</span><span class="sxs-lookup"><span data-stu-id="b9754-110">Additional languages besides C# such as JavaScript, F#, and Java are supported.</span></span> <span data-ttu-id="b9754-111">Las funciones creadas en el portal proporcionan una sintaxis de scripting enriquecida.</span><span class="sxs-lookup"><span data-stu-id="b9754-111">Functions created in the portal provide a rich scripting syntax.</span></span> <span data-ttu-id="b9754-112">Las funciones que se crean como proyectos independientes pueden implementarse con capacidades y compatibilidad de plataforma completa.</span><span class="sxs-lookup"><span data-stu-id="b9754-112">Functions created as standalone projects can be deployed with full platform support and capabilities.</span></span>

<span data-ttu-id="b9754-113">Para obtener más información, consulte [documentación de Azure Functions](https://docs.microsoft.com/azure/azure-functions).</span><span class="sxs-lookup"><span data-stu-id="b9754-113">For more information, see [Azure Functions documentation](https://docs.microsoft.com/azure/azure-functions).</span></span>

## <a name="functions-v1-vs-v2"></a><span data-ttu-id="b9754-114">Funciones v1 y v2</span><span class="sxs-lookup"><span data-stu-id="b9754-114">Functions v1 vs. v2</span></span>

<span data-ttu-id="b9754-115">Hay dos versiones del runtime de Azure Functions: 1.x y 2.x.</span><span class="sxs-lookup"><span data-stu-id="b9754-115">There are two versions of the Azure Functions runtime: 1.x and 2.x.</span></span> <span data-ttu-id="b9754-116">Versión 1.x está disponible con carácter general (GA).</span><span class="sxs-lookup"><span data-stu-id="b9754-116">Version 1.x is generally available (GA).</span></span> <span data-ttu-id="b9754-117">Admite el desarrollo de .NET desde el portal o las máquinas Windows y usa .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b9754-117">It supports .NET development from the portal or Windows machines and uses the .NET Framework.</span></span> <span data-ttu-id="b9754-118">1.x es compatible con C#, JavaScript y F #, con compatibilidad experimental con Python, PHP, TypeScript, Batch, Bash y PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b9754-118">1.x supports C#, JavaScript, and F#, with experimental support for Python, PHP, TypeScript, Batch, Bash, and PowerShell.</span></span>

<span data-ttu-id="b9754-119">Versión 2.x está en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="b9754-119">Version 2.x is in preview.</span></span> <span data-ttu-id="b9754-120">Aprovecha .NET Core y admite el desarrollo multiplataforma en máquinas Linux, macOS y Windows.</span><span class="sxs-lookup"><span data-stu-id="b9754-120">It leverages .NET Core and supports cross-platform development on Windows, macOS, and Linux machines.</span></span> <span data-ttu-id="b9754-121">2.x agrega soporte de primera clase para Java pero todavía no directamente admite cualquiera de los lenguajes experimentales.</span><span class="sxs-lookup"><span data-stu-id="b9754-121">2.x adds first-class support for Java but doesn't yet directly support any of the experimental languages.</span></span> <span data-ttu-id="b9754-122">Versión 2.x usa un nuevo modelo de extensibilidad de enlace que permite a las extensiones de terceros a la plataforma, crear versiones independientes de los enlaces, y una más simplificado de entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b9754-122">Version 2.x uses a new binding extensibility model that enables third-party extensions to the platform, independent versioning of bindings, and a more streamlined execution environment.</span></span>

> <span data-ttu-id="b9754-123">**Hay un problema conocido en la versión 1.x con [compatibilidad de redireccionamiento de enlace](https://github.com/Azure/azure-functions-host/issues/992).**</span><span class="sxs-lookup"><span data-stu-id="b9754-123">**There is a known issue in 1.x with [binding redirect support](https://github.com/Azure/azure-functions-host/issues/992).**</span></span> <span data-ttu-id="b9754-124">El problema es específico para el desarrollo de. NET.</span><span class="sxs-lookup"><span data-stu-id="b9754-124">The issue is specific to .NET development.</span></span> <span data-ttu-id="b9754-125">Los proyectos con dependencias en las bibliotecas que son una versión diferente de las bibliotecas incluidas en el tiempo de ejecución se ven afectados.</span><span class="sxs-lookup"><span data-stu-id="b9754-125">Projects with dependencies on libraries that are a different version from the libraries included in the runtime are impacted.</span></span> <span data-ttu-id="b9754-126">El equipo de funciones se ha comprometido a progresar concreta en el problema.</span><span class="sxs-lookup"><span data-stu-id="b9754-126">The functions team has committed to making concrete progress on the problem.</span></span> <span data-ttu-id="b9754-127">El equipo abordará redirecciones de enlace en 2.x antes de que entre en disponibilidad general.</span><span class="sxs-lookup"><span data-stu-id="b9754-127">The team will address binding redirects in 2.x before it goes into general availability.</span></span> <span data-ttu-id="b9754-128">La instrucción del equipo oficial con correcciones sugeridas y soluciones alternativas está disponible aquí: [resolución de ensamblado en Azure Functions](https://github.com/Azure/azure-functions-host/wiki/Assembly-Resolution-in-Azure-Functions).</span><span class="sxs-lookup"><span data-stu-id="b9754-128">The official team statement with suggested fixes and workarounds is available here: [Assembly resolution in Azure Functions](https://github.com/Azure/azure-functions-host/wiki/Assembly-Resolution-in-Azure-Functions).</span></span>

<span data-ttu-id="b9754-129">Para obtener más información, consulte [comparación entre 1.x y 2.x](https://docs.microsoft.com/azure/azure-functions/functions-versions).</span><span class="sxs-lookup"><span data-stu-id="b9754-129">For more information, see [Compare 1.x and 2.x](https://docs.microsoft.com/azure/azure-functions/functions-versions).</span></span>

## <a name="programming-language-support"></a><span data-ttu-id="b9754-130">Compatibilidad con lenguajes de programación</span><span class="sxs-lookup"><span data-stu-id="b9754-130">Programming language support</span></span>

<span data-ttu-id="b9754-131">Se admiten los siguientes idiomas ya sea en general (GA), disponibilidad de una vista previa, o en fase experimental.</span><span class="sxs-lookup"><span data-stu-id="b9754-131">The following languages are supported either in general availability (GA), preview, or experimental.</span></span>

|<span data-ttu-id="b9754-132">Lenguaje</span><span class="sxs-lookup"><span data-stu-id="b9754-132">Language</span></span>      |<span data-ttu-id="b9754-133">1.x</span><span class="sxs-lookup"><span data-stu-id="b9754-133">1.x</span></span>         |<span data-ttu-id="b9754-134">2.x</span><span class="sxs-lookup"><span data-stu-id="b9754-134">2.x</span></span>      |
|--------------|------------|---------|
|<span data-ttu-id="b9754-135">**C#**</span><span class="sxs-lookup"><span data-stu-id="b9754-135">**C#**</span></span>        |<span data-ttu-id="b9754-136">DISPONIBILIDAD GENERAL</span><span class="sxs-lookup"><span data-stu-id="b9754-136">GA</span></span>          |<span data-ttu-id="b9754-137">Vista previa</span><span class="sxs-lookup"><span data-stu-id="b9754-137">Preview</span></span>  |
|<span data-ttu-id="b9754-138">**JavaScript**</span><span class="sxs-lookup"><span data-stu-id="b9754-138">**JavaScript**</span></span>|<span data-ttu-id="b9754-139">DISPONIBILIDAD GENERAL</span><span class="sxs-lookup"><span data-stu-id="b9754-139">GA</span></span>          |<span data-ttu-id="b9754-140">Vista previa</span><span class="sxs-lookup"><span data-stu-id="b9754-140">Preview</span></span>  |
|<span data-ttu-id="b9754-141">**F#**</span><span class="sxs-lookup"><span data-stu-id="b9754-141">**F#**</span></span>        |<span data-ttu-id="b9754-142">DISPONIBILIDAD GENERAL</span><span class="sxs-lookup"><span data-stu-id="b9754-142">GA</span></span>          |         |
|<span data-ttu-id="b9754-143">**Java**</span><span class="sxs-lookup"><span data-stu-id="b9754-143">**Java**</span></span>      |            |<span data-ttu-id="b9754-144">Vista previa</span><span class="sxs-lookup"><span data-stu-id="b9754-144">Preview</span></span>  |
|<span data-ttu-id="b9754-145">**Python**</span><span class="sxs-lookup"><span data-stu-id="b9754-145">**Python**</span></span>    |<span data-ttu-id="b9754-146">Habilitación de características</span><span class="sxs-lookup"><span data-stu-id="b9754-146">Experimental</span></span>|         |
|<span data-ttu-id="b9754-147">**PHP**</span><span class="sxs-lookup"><span data-stu-id="b9754-147">**PHP**</span></span>       |<span data-ttu-id="b9754-148">Habilitación de características</span><span class="sxs-lookup"><span data-stu-id="b9754-148">Experimental</span></span>|         |
|<span data-ttu-id="b9754-149">**TypeScript**</span><span class="sxs-lookup"><span data-stu-id="b9754-149">**TypeScript**</span></span>|<span data-ttu-id="b9754-150">Habilitación de características</span><span class="sxs-lookup"><span data-stu-id="b9754-150">Experimental</span></span>|         |
|<span data-ttu-id="b9754-151">**Batch**</span><span class="sxs-lookup"><span data-stu-id="b9754-151">**Batch**</span></span>     |<span data-ttu-id="b9754-152">Habilitación de características</span><span class="sxs-lookup"><span data-stu-id="b9754-152">Experimental</span></span>|         |
|<span data-ttu-id="b9754-153">**Bash**</span><span class="sxs-lookup"><span data-stu-id="b9754-153">**Bash**</span></span>      |<span data-ttu-id="b9754-154">Habilitación de características</span><span class="sxs-lookup"><span data-stu-id="b9754-154">Experimental</span></span>|         |
|<span data-ttu-id="b9754-155">**PowerShell**</span><span class="sxs-lookup"><span data-stu-id="b9754-155">**PowerShell**</span></span>|<span data-ttu-id="b9754-156">Habilitación de características</span><span class="sxs-lookup"><span data-stu-id="b9754-156">Experimental</span></span>|         |

<span data-ttu-id="b9754-157">Para obtener más información, consulte [idiomas admitidos](https://docs.microsoft.com/azure/azure-functions/supported-languages).</span><span class="sxs-lookup"><span data-stu-id="b9754-157">For more information, see [Supported languages](https://docs.microsoft.com/azure/azure-functions/supported-languages).</span></span>

## <a name="app-service-plans"></a><span data-ttu-id="b9754-158">Planes de App service</span><span class="sxs-lookup"><span data-stu-id="b9754-158">App service plans</span></span>

<span data-ttu-id="b9754-159">Las funciones están respaldadas por un *plan de app service*.</span><span class="sxs-lookup"><span data-stu-id="b9754-159">Functions are backed by an *app service plan*.</span></span> <span data-ttu-id="b9754-160">El plan define los recursos utilizados por la aplicación de functions.</span><span class="sxs-lookup"><span data-stu-id="b9754-160">The plan defines the resources used by the functions app.</span></span> <span data-ttu-id="b9754-161">Puede asignar los planes a una región, determinar el tamaño y el número de máquinas virtuales que se usará y elegir un plan de tarifa.</span><span class="sxs-lookup"><span data-stu-id="b9754-161">You can assign plans to a region, determine the size and number of virtual machines that will be used, and pick a pricing tier.</span></span> <span data-ttu-id="b9754-162">Un enfoque sin servidor es true, las aplicaciones de función pueden usar el **consumo** plan.</span><span class="sxs-lookup"><span data-stu-id="b9754-162">For a true serverless approach, function apps may use the **consumption** plan.</span></span> <span data-ttu-id="b9754-163">El plan de consumo escalará el back-end automáticamente según la carga.</span><span class="sxs-lookup"><span data-stu-id="b9754-163">The consumption plan will scale the back end automatically based on load.</span></span>

<span data-ttu-id="b9754-164">Para obtener más información, consulte [planes de App service](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview).</span><span class="sxs-lookup"><span data-stu-id="b9754-164">For more information, see [App service plans](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview).</span></span>

## <a name="create-your-first-function"></a><span data-ttu-id="b9754-165">Cree su primera función</span><span class="sxs-lookup"><span data-stu-id="b9754-165">Create your first function</span></span>

<span data-ttu-id="b9754-166">Hay tres formas comunes de creación de aplicaciones de función.</span><span class="sxs-lookup"><span data-stu-id="b9754-166">There are three common ways you can create function apps.</span></span>

* <span data-ttu-id="b9754-167">Funciones de script en el portal.</span><span class="sxs-lookup"><span data-stu-id="b9754-167">Script functions in the portal.</span></span>
* <span data-ttu-id="b9754-168">Cree los recursos necesarios con la interfaz de línea de comandos (CLI) de Azure.</span><span class="sxs-lookup"><span data-stu-id="b9754-168">Create the necessary resources using the Azure Command Line Interface (CLI).</span></span>
* <span data-ttu-id="b9754-169">Crear funciones localmente mediante su IDE favorito y publicarlos en Azure.</span><span class="sxs-lookup"><span data-stu-id="b9754-169">Build functions locally using your favorite IDE and publish them to Azure.</span></span>

<span data-ttu-id="b9754-170">Para obtener más información sobre cómo crear una función con secuencias de comandos en el portal, consulte [crear su primera función en Azure portal](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function).</span><span class="sxs-lookup"><span data-stu-id="b9754-170">For more information on creating a scripted function in the portal, see [Create your first function in the Azure portal](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function).</span></span>

<span data-ttu-id="b9754-171">Para compilar desde la CLI de Azure, consulte [crear su primera función mediante la CLI de Azure](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli).</span><span class="sxs-lookup"><span data-stu-id="b9754-171">To build from the Azure CLI, see [Create your first function using the Azure CLI](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli).</span></span>

<span data-ttu-id="b9754-172">Para crear una función desde Visual Studio, consulte [crear su primera función mediante Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="b9754-172">To create a function from Visual Studio, see [Create your first function using Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio).</span></span>

## <a name="understand-triggers-and-bindings"></a><span data-ttu-id="b9754-173">Comprender los desencadenadores y enlaces</span><span class="sxs-lookup"><span data-stu-id="b9754-173">Understand triggers and bindings</span></span>

<span data-ttu-id="b9754-174">Las funciones se invocan mediante un *desencadenador* y puede tener exactamente uno.</span><span class="sxs-lookup"><span data-stu-id="b9754-174">Functions are invoked by a *trigger* and can have exactly one.</span></span> <span data-ttu-id="b9754-175">Además de invocar la función, determinados desencadenadores también sirven como los enlaces.</span><span class="sxs-lookup"><span data-stu-id="b9754-175">In addition to invoking the function, certain triggers also serve as bindings.</span></span> <span data-ttu-id="b9754-176">También puede definir varios enlaces además el desencadenador.</span><span class="sxs-lookup"><span data-stu-id="b9754-176">You may also define multiple bindings in addition to the trigger.</span></span> <span data-ttu-id="b9754-177">*Enlaces* proporcionan una forma declarativa para conectar datos a su código.</span><span class="sxs-lookup"><span data-stu-id="b9754-177">*Bindings* provide a declarative way to connect data to your code.</span></span> <span data-ttu-id="b9754-178">Se pueden pasar en (entrada) o recibir datos (output).</span><span class="sxs-lookup"><span data-stu-id="b9754-178">They can be passed in (input) or receive data (output).</span></span> <span data-ttu-id="b9754-179">Hacen funciones facilita el trabajo con desencadenadores y enlaces.</span><span class="sxs-lookup"><span data-stu-id="b9754-179">Triggers and bindings make functions easy to work with.</span></span> <span data-ttu-id="b9754-180">Enlaces de quitar la sobrecarga de la creación manual de base de datos o archivo del sistema conexiones.</span><span class="sxs-lookup"><span data-stu-id="b9754-180">Bindings remove the overhead of manually creating database or file system connections.</span></span> <span data-ttu-id="b9754-181">Toda la información necesaria para los enlaces está contenida en un especial *functions.json* de archivos para las secuencias de comandos o declarados con atributos en el código.</span><span class="sxs-lookup"><span data-stu-id="b9754-181">All of the information needed for the bindings is contained in a special *functions.json* file for scripts or declared with attributes in code.</span></span>

<span data-ttu-id="b9754-182">Algunos desencadenadores comunes incluyen:</span><span class="sxs-lookup"><span data-stu-id="b9754-182">Some common triggers include:</span></span>

* <span data-ttu-id="b9754-183">Almacenamiento de blobs: invocar la función cuando se carga o se puede cambiar en el almacenamiento de un archivo o carpeta.</span><span class="sxs-lookup"><span data-stu-id="b9754-183">Blob Storage: invoke your function when a file or folder is uploaded or changed in storage.</span></span>
* <span data-ttu-id="b9754-184">HTTP: invocar la función como una API de REST.</span><span class="sxs-lookup"><span data-stu-id="b9754-184">HTTP: invoke your function like a REST API.</span></span>
* <span data-ttu-id="b9754-185">Cola: invocar la función cuando existen elementos en una cola.</span><span class="sxs-lookup"><span data-stu-id="b9754-185">Queue: invoke your function when items exist in a queue.</span></span>
* <span data-ttu-id="b9754-186">Temporizador: invocar la función a un ritmo normal.</span><span class="sxs-lookup"><span data-stu-id="b9754-186">Timer: invoke your function on a regular cadence.</span></span>

<span data-ttu-id="b9754-187">Ejemplos de enlaces:</span><span class="sxs-lookup"><span data-stu-id="b9754-187">Examples of bindings include:</span></span>

* <span data-ttu-id="b9754-188">COSMOS DB: conectar fácilmente a la base de datos para cargar o guardar archivos.</span><span class="sxs-lookup"><span data-stu-id="b9754-188">CosmosDB: easily connect to the database to load or save files.</span></span>
* <span data-ttu-id="b9754-189">Almacenamiento de tabla: trabajar con almacenamiento de pares clave-valor de la aplicación de función.</span><span class="sxs-lookup"><span data-stu-id="b9754-189">Table Storage: work with key/value storage from your function app.</span></span>
* <span data-ttu-id="b9754-190">Almacenamiento en cola: fácilmente recuperar elementos de una cola o colocar los nuevos elementos en la cola.</span><span class="sxs-lookup"><span data-stu-id="b9754-190">Queue Storage: easily retrieve items from a queue, or place new items on the queue.</span></span>

<span data-ttu-id="b9754-191">En el siguiente ejemplo *functions.json* archivo define un desencadenador y un enlace:</span><span class="sxs-lookup"><span data-stu-id="b9754-191">The following example *functions.json* file defines a trigger and a binding:</span></span>

```json
{
  "bindings": [
    {
      "name": "myBlob",
      "type": "blobTrigger",
      "direction": "in",
      "path": "images/{name}",
      "connection": "AzureWebJobsStorage"
    },
    {
      "name": "$return",
      "type": "queue",
      "direction": "out",
      "queueName": "images",
      "connection": "AzureWebJobsStorage"
    }
  ],
  "disabled": false
}
```

<span data-ttu-id="b9754-192">En este ejemplo, la función se desencadena por un cambio en el almacenamiento de blobs en el `images` contenedor.</span><span class="sxs-lookup"><span data-stu-id="b9754-192">In this example, the function is triggered by a change to blob storage in the `images` container.</span></span> <span data-ttu-id="b9754-193">La información del archivo se pasa, por lo que el desencadenador también actúa como un enlace.</span><span class="sxs-lookup"><span data-stu-id="b9754-193">The information for the file is passed in, so the trigger also acts as a binding.</span></span> <span data-ttu-id="b9754-194">Existe otro enlace para introducir la información en una cola denominada `images`.</span><span class="sxs-lookup"><span data-stu-id="b9754-194">Another binding exists to put information onto a queue named `images`.</span></span>

<span data-ttu-id="b9754-195">Este es el script de C# para la función:</span><span class="sxs-lookup"><span data-stu-id="b9754-195">Here is the C# script for the function:</span></span>

```csharp
public static string Run(Stream myBlob, string name, TraceWriter log)
{
    log.Info($"C# Blob trigger function Processed blob\n Name:{name} \n Size: {myBlob.Length} Bytes");
    return name;
}
```

<span data-ttu-id="b9754-196">El ejemplo es una función simple que toma el nombre del archivo que se modificó o carga en el almacenamiento de blobs y lo coloca en una cola para su posterior procesamiento.</span><span class="sxs-lookup"><span data-stu-id="b9754-196">The example is a simple function that takes the name of the file that was modified or uploaded to blob storage, and places it on a queue for later processing.</span></span>

<span data-ttu-id="b9754-197">Para obtener una lista completa de los desencadenadores y enlaces, vea [conceptos de enlaces y desencadenadores de Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings).</span><span class="sxs-lookup"><span data-stu-id="b9754-197">For a full list of triggers and bindings, see [Azure Functions triggers and bindings concepts](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings).</span></span>

## <a name="proxies"></a><span data-ttu-id="b9754-198">Servidores proxy</span><span class="sxs-lookup"><span data-stu-id="b9754-198">Proxies</span></span>

<span data-ttu-id="b9754-199">Los proxies proporcionan funcionalidad de redirección para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b9754-199">Proxies provide redirect functionality for your application.</span></span> <span data-ttu-id="b9754-200">Los proxies exponen un punto de conexión y asignan ese extremo a otro recurso.</span><span class="sxs-lookup"><span data-stu-id="b9754-200">Proxies expose an endpoint and map that endpoint to another resource.</span></span> <span data-ttu-id="b9754-201">Con los servidores proxy, puede:</span><span class="sxs-lookup"><span data-stu-id="b9754-201">With proxies, you can:</span></span>

* <span data-ttu-id="b9754-202">Volver a enrutar una solicitud entrante a otro punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="b9754-202">Reroute an incoming request to another endpoint.</span></span>
* <span data-ttu-id="b9754-203">Modifique la solicitud entrante antes de pasarlo a lo largo.</span><span class="sxs-lookup"><span data-stu-id="b9754-203">Modify the incoming request before it's passed along.</span></span>
* <span data-ttu-id="b9754-204">Modificar o proporcionar una respuesta.</span><span class="sxs-lookup"><span data-stu-id="b9754-204">Modify or provide a response.</span></span>

<span data-ttu-id="b9754-205">Los servidores proxy se utilizan para escenarios como:</span><span class="sxs-lookup"><span data-stu-id="b9754-205">Proxies are used for scenarios such as:</span></span>

* <span data-ttu-id="b9754-206">Simplificar, lo que reduce o cambiar la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="b9754-206">Simplifying, shortening, or changing the URL.</span></span>
* <span data-ttu-id="b9754-207">Proporcionar un prefijo de API coherente a varios servicios de back-end.</span><span class="sxs-lookup"><span data-stu-id="b9754-207">Providing a consistent API prefix to multiple back-end services.</span></span>
* <span data-ttu-id="b9754-208">Una respuesta a un punto de conexión que se desarrolla la simulación.</span><span class="sxs-lookup"><span data-stu-id="b9754-208">Mocking a response to an endpoint being developed.</span></span>
* <span data-ttu-id="b9754-209">Proporcionar una respuesta estática a un extremo conocido.</span><span class="sxs-lookup"><span data-stu-id="b9754-209">Providing a static response to a well-known endpoint.</span></span>
* <span data-ttu-id="b9754-210">Mantener un punto de conexión de API coherente mientras se mueve o se migró el back-end.</span><span class="sxs-lookup"><span data-stu-id="b9754-210">Keeping an API endpoint consistent while the back end is moved or migrated.</span></span>

<span data-ttu-id="b9754-211">Los servidores proxy se almacenan como definiciones de JSON.</span><span class="sxs-lookup"><span data-stu-id="b9754-211">Proxies are stored as JSON definitions.</span></span> <span data-ttu-id="b9754-212">A continuación, se muestra un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b9754-212">Here is an example:</span></span>

```json
{
  "$schema": "http://json.schemastore.org/proxies",
  "proxies": {
    "Domain Redirect": {
      "matchCondition": {
        "route": "/{shortUrl}"
      },
      "backendUri": "http://%WEBSITE_HOSTNAME%/api/UrlRedirect/{shortUrl}"
    },
    "Root": {
      "matchCondition": {
        "route": "/"
      },
      "responseOverrides": {
        "response.statusCode": "301",
        "response.statusReason": "Moved Permanently",
        "response.headers.location": "https://docs.microsoft.com/"
      }
    }
  }
}
```

<span data-ttu-id="b9754-213">El `Domain Redirect` proxy toma una ruta abreviada y lo asigna al recurso de función más largo.</span><span class="sxs-lookup"><span data-stu-id="b9754-213">The `Domain Redirect` proxy takes a shortened route and maps it to the longer function resource.</span></span> <span data-ttu-id="b9754-214">La transformación es similar:</span><span class="sxs-lookup"><span data-stu-id="b9754-214">The transformation looks like:</span></span>

`https://--shorturl--/123` -> `https://--longurl--.azurewebsites.net/api/UrlRedirect/123`

<span data-ttu-id="b9754-215">El `Root` proxy toma todo lo envía a la dirección URL raíz (`https://--shorturl--/`) y lo redirige a la documentación del sitio.</span><span class="sxs-lookup"><span data-stu-id="b9754-215">The `Root` proxy takes anything sent to the root URL (`https://--shorturl--/`) and redirects it to the documentation site.</span></span>

<span data-ttu-id="b9754-216">Se muestra un ejemplo del uso de los servidores proxy en el vídeo [Azure: traiga su aplicación a la nube con Azure Functions sin servidor](https://channel9.msdn.com/events/Connect/2017/E102).</span><span class="sxs-lookup"><span data-stu-id="b9754-216">An example of using proxies is shown in the video [Azure: Bring your app to the cloud with serverless Azure Functions](https://channel9.msdn.com/events/Connect/2017/E102).</span></span> <span data-ttu-id="b9754-217">En tiempo real, se migra una aplicación de ASP.NET Core que se ejecutan en el servidor SQL Server local a la nube de Azure.</span><span class="sxs-lookup"><span data-stu-id="b9754-217">In real time, an ASP.NET Core application running on local SQL Server is migrated to the Azure Cloud.</span></span> <span data-ttu-id="b9754-218">Los servidores proxy se utilizan para ayudar a refactorizar un proyecto de API Web tradicional para usar las funciones.</span><span class="sxs-lookup"><span data-stu-id="b9754-218">Proxies are used to help refactor a traditional Web API project to use functions.</span></span>

<span data-ttu-id="b9754-219">Para obtener más información acerca de los servidores proxy, consulte [trabajar con Azure Functions Proxies](https://docs.microsoft.com/azure/azure-functions/functions-proxies).</span><span class="sxs-lookup"><span data-stu-id="b9754-219">For more information about Proxies, see [Work with Azure Functions Proxies](https://docs.microsoft.com/azure/azure-functions/functions-proxies).</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="b9754-220">[Anterior](azure-serverless-platform.md)
[Siguiente](application-insights.md)</span><span class="sxs-lookup"><span data-stu-id="b9754-220">[Previous](azure-serverless-platform.md)
[Next](application-insights.md)</span></span>