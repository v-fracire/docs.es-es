---
title: 'var: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- var
- var_CSharpKeyword
helpviewer_keywords:
- var keyword [C#]
ms.assetid: 0777850a-2691-4e3e-927f-0c850f5efe15
ms.openlocfilehash: f0e8b0e416cb32a57a83224ab6627c9ad520ec80
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53240221"
---
# <a name="var-c-reference"></a>var (Referencia de C#)
A partir de Visual C# 3.0, las variables que se declaran en el ámbito de método pueden tener un "tipo" `var` implícito. Una variable local con tipo implícito es fuertemente tipada exactamente igual que si hubiera declarado el tipo, solo que en este caso es el compilador el que lo determina. Las dos declaraciones siguientes de `i` tienen una función equivalente:  
  
```csharp  
var i = 10; // Implicitly typed. 
int i = 10; // Explicitly typed. 
```  
  
 Para obtener más información, vea [Implicitly typed local variables](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) (Variables locales con tipo implícito) y [Type relationships in LINQ query operations](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md) (Relaciones entre tipos en las operaciones de consulta de LINQ).  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se muestran dos expresiones de consulta. En la primera expresión, el uso de `var` se permite pero no es necesario, ya que el tipo del resultado de la consulta se puede indicar explícitamente como `IEnumerable<string>`. En cambio, en la segunda expresión, `var` permite que el resultado sea una colección de tipos anónimos y solo el compilador puede tener acceso al nombre de ese tipo. El uso de `var` elimina la necesidad de crear una nueva clase para el resultado. Tenga en cuenta que, en el ejemplo 2, la variable de iteración `foreach` `item` también debe tener tipo implícito.  
  
 [!code-csharp[csrefKeywordsTypes#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/var_1.cs)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../../../csharp/language-reference/index.md)  
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Variables locales con asignación implícita de tipos](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)
