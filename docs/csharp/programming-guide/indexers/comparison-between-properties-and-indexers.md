---
title: 'Comparación entre propiedades e indizadores: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], vs. indexers
- indexers [C#], vs. properties
ms.assetid: 3358a89f-44a0-4a4d-bf8c-07237a90af39
ms.openlocfilehash: 053eb7ee0fe9333f049e5b4f8a8e709e42aa2119
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53234466"
---
# <a name="comparison-between-properties-and-indexers-c-programming-guide"></a>Comparación entre propiedades e indizadores (Guía de programación de C#)
Los indexadores son como propiedades. Excepto por las diferencias que se muestran en la tabla siguiente, todas las reglas que se definen para los descriptores de acceso de propiedad se aplican también a los descriptores de acceso de indexador.  
  
|Propiedad.|Indexador|  
|--------------|-------------|  
|Permite que los métodos se llamen como si fueran miembros de datos públicos.|Permite que se pueda tener acceso a los elementos de una colección interna de un objeto mediante la notación de matriz en el propio objeto.|  
|Se ha tenido acceso mediante un nombre simple.|Se ha tenido acceso mediante un índice.|  
|Puede ser un miembro de instancia o estático.|Debe ser un miembro de instancia.|  
|Un descriptor de acceso [get](../../../csharp/language-reference/keywords/get.md) de una propiedad no tiene parámetros.|Un descriptor de acceso `get` de un indexador tiene la misma lista de parámetros formales que el indexador.|  
|Un descriptor de acceso [set](../../../csharp/language-reference/keywords/set.md) de una propiedad contiene el parámetro `value` implícito.|Un descriptor de acceso `set` de un indexador tiene la misma lista de parámetros formales que el indexador, y también para el parámetro [value](../../../csharp/language-reference/keywords/value.md).|  
|Admite la sintaxis abreviada con [Propiedades autoimplementadas](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).|No admite la sintaxis abreviada.|  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Indizadores](../../../csharp/programming-guide/indexers/index.md)  
- [Propiedades](../../../csharp/programming-guide/classes-and-structs/properties.md)
