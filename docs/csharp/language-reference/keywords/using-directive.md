---
title: 'Directiva using: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- using directive [C#]
ms.assetid: b42b8e61-5e7e-439c-bb71-370094b44ae8
ms.openlocfilehash: b58467953096c26d13f4c837f13548876e645f08
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53240325"
---
# <a name="using-directive-c-reference"></a>using (Directiva, Referencia de C#)
La directiva `using` tiene tres usos:  
  
-   Permitir el uso de tipos en un espacio de nombres de manera que no tenga que calificar el uso de un tipo en dicho espacio de nombres:  
  
    ```csharp  
    using System.Text;  
    ```  
  
-   Permitirle acceder a los miembros estáticos y a los tipos anidados de un tipo sin tener que calificar el acceso con el nombre del tipo. 
  
    ```csharp  
    using static System.Math;  
    ```  
     
    Para obtener más información, vea [using static (Directiva)](using-static.md).

-   Para crear un alias para un espacio de nombre o un tipo. Esto se conoce como *alias using (Directiva)*.  
  
    ```csharp  
    using Project = PC.MyCompany.Project;  
    ```  
  
 La palabra clave `using` también se usa para crear *instrucciones using*, que ayudan a garantizar que los objetos <xref:System.IDisposable>, como archivos y fuentes, se tratan correctamente. Consulte [using (Instrucción)](../../../csharp/language-reference/keywords/using-statement.md) para obtener más información.  
  
## <a name="using-static-type"></a>Usar el tipo estático  
 Puede acceder a los miembros estáticos de un tipo sin tener que calificar el acceso con el nombre del tipo:  
  
```csharp  
using static System.Console;   
using static System.Math;  
class Program   
{   
    static void Main()   
    {   
        WriteLine(Sqrt(3*3 + 4*4));   
    }   
}  
```  
  
## <a name="remarks"></a>Comentarios  
 El ámbito de una directiva `using` se limita al archivo en el que aparece.
 
 La directiva `using` puede aparecer:
- Al principio de un archivo de código fuente, antes de las definiciones de espacio de nombres o tipo.
- En cualquier espacio de nombres, pero antes de cualquier espacio de nombres o tipos declarados en este espacio de nombres.

De lo contrario, se generará el error de compilador [CS1529](../../misc/cs1529.md).
  
 Cree una directiva de alias `using` para facilitar la calificación de un identificador como espacio de nombres o tipo. En cualquier directiva `using`, hay que usar el espacio de nombres o el tipo con cualificación completa, independientemente de las directivas `using` que los precedan. No se puede usar ningún alias `using` en la declaración de una directiva `using`. Por ejemplo, el código siguiente genera un error de compilador:
 ```csharp
 using s = System.Text;
 using s.RegularExpressions; 
 ```
  
 Cree una directiva `using` para usar los tipos de un espacio de nombres sin tener que especificarlo. Una directiva `using` no proporciona acceso a los espacios de nombres que están anidados en el espacio de nombres especificado.  
  
 Los espacios de nombres se dividen en dos categorías: definidos por el sistema y definidos por el usuario. Los espacios de nombres definidos por el usuario son espacios de nombres definidos en el código. Para obtener una lista de los espacios de nombres definidos por el sistema, vea [Explorador de API de .NET](https://docs.microsoft.com/dotnet/api/).  
  
 Para obtener ejemplos de cómo hacer referencia a métodos en otros ensamblados, vea [Crear y usar ensamblados desde la línea de comandos (C#)](../../programming-guide/concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md).  
  
## <a name="example-1"></a>Ejemplo 1  
  
 En el ejemplo siguiente se muestra cómo definir y usar un alias `using` para un espacio de nombres:  
  
 [!code-csharp[csrefKeywordsNamespace#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-directive_1.cs)]  
  
 Una directiva de alias using no puede tener un tipo genérico abierto en el lado derecho. Por ejemplo, no puede crear un alias using para List\<T>, pero puede crear uno para List\<int>.  
  
## <a name="example-2"></a>Ejemplo 2  
  
 En el ejemplo siguiente se muestra cómo definir una directiva `using` y un alias `using` para una clase:  
  
 [!code-csharp[csrefKeywordsNamespace#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-directive_2.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../../../csharp/language-reference/index.md)  
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Utilizar espacios de nombres](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
- [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)  
- [Palabras clave del espacio de nombres](../../../csharp/language-reference/keywords/namespace-keywords.md)  
- [Espacios de nombres](../../../csharp/programming-guide/namespaces/index.md)  
- [using (instrucción)](../../../csharp/language-reference/keywords/using-statement.md)
