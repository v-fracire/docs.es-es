---
title: 'Cómo: Leer y escribir en un archivo de datos recién creado'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- streams, reading and writing data
- BinaryReader class, examples
- I/O [.NET Framework], reading data
- I/O [.NET Framework], writing data
- BinaryWriter class, examples
ms.assetid: e209d949-31e8-44ea-8e38-87f9093f3093
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 65c56a11531f705b7e047e435ec575969d39a616
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2018
ms.locfileid: "45592911"
---
# <a name="how-to-read-and-write-to-a-newly-created-data-file"></a>Cómo: Leer y escribir en un archivo de datos recién creado
Las clases <xref:System.IO.BinaryWriter> y <xref:System.IO.BinaryReader?displayProperty=nameWithType> se usan para escribir y leer datos, en lugar de cadenas de caracteres. En el ejemplo de código siguiente se muestra cómo se escriben y se leen datos de una nueva secuencia de archivos vacía denominada `Test.data`. Después de crear el archivo de datos en el directorio actual, se crean los objetos <xref:System.IO.BinaryWriter> y <xref:System.IO.BinaryReader> asociados, y se usa el objeto <xref:System.IO.BinaryWriter> para escribir los enteros de 0 a 10 en `Test.data`, que deja el puntero de archivo al final del archivo. Después de volver a establecer el puntero de archivo en el origen, el objeto <xref:System.IO.BinaryReader> lee el contenido especificado.  
  
## <a name="example"></a>Ejemplo  
 [!code-cpp[System.IO.BinaryReaderWriter#7](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/CPP/source6.cpp#7)]
 [!code-csharp[System.IO.BinaryReaderWriter#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/CS/source6.cs#7)]
 [!code-vb[System.IO.BinaryReaderWriter#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/VB/source6.vb#7)]  
  
## <a name="robust-programming"></a>Programación sólida  
 Si `Test.data` ya existe en el directorio actual, se genera una excepción <xref:System.IO.IOException>. Use la opción de modo de archivo <xref:System.IO.FileMode.Create?displayProperty=nameWithType> al inicializar la secuencia de archivo para crear siempre un archivo nuevo sin generar una excepción.  
  
## <a name="see-also"></a>Vea también

- <xref:System.IO.BinaryReader>  
- <xref:System.IO.BinaryWriter>  
- <xref:System.IO.FileStream>  
- <xref:System.IO.FileStream.Seek%2A?displayProperty=nameWithType>  
- <xref:System.IO.SeekOrigin>  
- [Enumerar directorios y archivos](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
- [Cómo: Abrir y anexar a un archivo de registro](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
- [Cómo: Leer texto de un archivo](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
- [Cómo: Escribir texto en un archivo](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
- [Cómo: Leer caracteres de una cadena](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
- [Cómo: Escribir caracteres en una cadena](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
- [E/S de archivos y secuencias](../../../docs/standard/io/index.md)
