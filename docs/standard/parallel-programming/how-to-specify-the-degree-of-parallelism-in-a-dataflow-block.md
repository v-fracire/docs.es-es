---
title: "How to: Specify the Degree of Parallelism in a Dataflow Block | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "dataflow block, specifying parallelism in TPL"
  - "Task Parallel Library, dataflows"
  - "TPL dataflow library, specifying parallelism"
ms.assetid: e4088541-ee05-40db-95f5-147cfe62fde7
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# How to: Specify the Degree of Parallelism in a Dataflow Block
En este documento se describe cómo establecer la propiedad <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions.MaxDegreeOfParallelism%2A?displayProperty=fullName> para que un bloque de flujo de datos de ejecución pueda procesar más de un mensaje al mismo tiempo.  Esto resulta útil cuando tiene un bloque de flujo de datos que realiza un cálculo de ejecución prolongada y se puede beneficiar del procesamiento de mensajes en paralelo.  En el ejemplo se usa la clase <xref:System.Threading.Tasks.Dataflow.ActionBlock%601?displayProperty=fullName> para llevar a cabo varias operaciones de flujo de datos simultáneamente; sin embargo, puede especificar el grado máximo de paralelismo en cualquiera de los tipos de bloque de ejecución predefinidos que la biblioteca de flujo de datos TPL proporciona, <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602?displayProperty=fullName> y <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602?displayProperty=fullName>.  
  
> [!TIP]
>  La biblioteca de flujos de datos TPL \(el espacio de nombres <xref:System.Threading.Tasks.Dataflow?displayProperty=fullName>\) no se distribuye con [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].  Para instalar el espacio de nombres <xref:System.Threading.Tasks.Dataflow>, abra el proyecto en [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], elija **Administrar paquetes NuGet** en el menú Proyecto, y busque en línea el paquete `Microsoft.Tpl.Dataflow`.  
  
## Ejemplo  
 En el ejemplo siguiente se realizan dos cálculos de flujo de datos y se imprime el tiempo transcurrido que se necesita para cada cálculo.  El primer cálculo especifica un grado máximo de paralelismo de 1, que es el valor predeterminado.  Un grado máximo de paralelismo de 1 hace que el bloque de flujo de datos procese los mensajes en serie.  El segundo cálculo es similar al primero, excepto que especifica un grado máximo de paralelismo igual al número de procesadores disponibles.  Esto permite que el bloque de flujo de datos realice varias operaciones en paralelo.  
  
 [!code-csharp[TPLDataflow_DegreeOfParallelism#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_degreeofparallelism/cs/dataflowdegreeofparallelism.cs#1)]
 [!code-vb[TPLDataflow_DegreeOfParallelism#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_degreeofparallelism/vb/dataflowdegreeofparallelism.vb#1)]  
  
## Compilar el código  
 Copie el código de ejemplo y péguelo en un proyecto de Visual Studio o péguelo en un archivo llamado `DataflowDegreeOfParallelism.cs` \(`DataflowDegreeOfParallelism.vb` en [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\) y, después, ejecute el siguiente comando en una ventana del símbolo del sistema de Visual Studio.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe \/r:System.Threading.Tasks.Dataflow.dll DataflowDegreeOfParallelism.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe \/r:System.Threading.Tasks.Dataflow.dll DataflowDegreeOfParallelism.vb**  
  
## Programación eficaz  
 De forma predeterminada, cada bloque de flujo de datos predefinido propaga los mensajes en el orden con que se reciben.  Aunque cuando se especifica un grado máximo de paralelismo mayor que 1 se procesan simultáneamente varios mensajes, se siguen propagando en el orden con que se reciben.  
  
 Dado que la propiedad <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions.MaxDegreeOfParallelism%2A> representa el grado máximo de paralelismo, el bloque de flujo de datos puede ejecutarse con un menor grado de paralelismo que el especificado.  El bloque de flujo de datos puede usar un grado de paralelismo menor para cumplir los requisitos funcionales o porque hay una falta de recursos del sistema.  Un bloque de flujo de datos nunca elige un grado de paralelismo mayor que el especificado.  
  
## Vea también  
 [Flujo de datos](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)