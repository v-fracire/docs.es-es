---
title: Aserciones (F#)
description: Aprenda a usar la expresión 'assert' como una característica de depuración para probar expresiones en el F# lenguaje de programación.
ms.date: 05/16/2016
ms.openlocfilehash: fbaf038f08cfc74e6cb262c110322dc586813c0c
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53127256"
---
# <a name="assertions"></a>Aserciones

El `assert` expresión es una característica de depuración que puede usar para probar una expresión. En caso de error en modo de depuración, una aserción genera un cuadro de diálogo de error del sistema.

## <a name="syntax"></a>Sintaxis

```fsharp
assert condition
```

## <a name="remarks"></a>Comentarios

El `assert` expresión tiene el tipo `bool -> unit`.

En la sintaxis anterior, *condición* representa una expresión booleana que se va a probar. Si la expresión se evalúa como `true`, la ejecución continúa sin ninguna variación. Si se evalúa como `false`, se genera un cuadro de diálogo de error del sistema. El cuadro de diálogo de error tiene un título que contiene la cadena **error de aserción**. El cuadro de diálogo contiene un seguimiento de pila que indica dónde se produjo el error de aserción.

Comprobación de aserción está habilitada sólo cuando se compila en modo de depuración; es decir, si la constante `DEBUG` está definido. En el sistema del proyecto, de forma predeterminada, el `DEBUG` constante se define en la configuración de depuración pero no en la configuración de lanzamiento.

No se puede detectar el error de aserción utilizando F# control de excepciones.

> [!NOTE]
> El `assert` función se resuelve en <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.

## <a name="example"></a>Ejemplo

El ejemplo de código siguiente muestra el uso de la `assert` expresión.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
