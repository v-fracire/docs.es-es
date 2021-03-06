---
title: 'Expresiones lambda: la palabra clave fun (F#)'
description: Obtenga información sobre cómo usar la palabra clave "diversión" de F# para definir una expresión lambda, que es una función anónima.
ms.date: 05/16/2016
ms.openlocfilehash: a37757f6b7328cd348bbf13f058a6dbc881769cf
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2018
ms.locfileid: "47231026"
---
# <a name="lambda-expressions-the-fun-keyword-f"></a>Expresiones lambda: la palabra clave fun (F#)

El `fun` palabra clave se usa para definir una expresión lambda, es decir, una función anónima.

## <a name="syntax"></a>Sintaxis

```fsharp
fun parameter-list -> expression
```

## <a name="remarks"></a>Comentarios

El *lista de parámetros* normalmente consta de los nombres y, opcionalmente, tipos de parámetros. Por lo general, el *lista de parámetros* puede estar formada por los patrones de F#. Para obtener una lista completa de patrones posibles, consulte [coincidencia de patrones](../pattern-matching.md). Listas de parámetros válidos incluyen los ejemplos siguientes.

```fsharp
// Lambda expressions with parameter lists.
fun a b c -> ...
fun (a: int) b c -> ...
fun (a : int) (b : string) (c:float) -> ...

// A lambda expression with a tuple pattern.
fun (a, b) -> …

// A lambda expression with a list pattern.
fun head :: tail -> …
```

El *expresión* es el cuerpo de la función, la última expresión que genera un valor devuelto. Ejemplos de expresiones lambda válidas incluyen lo siguiente:

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet301.fs)]

## <a name="using-lambda-expressions"></a>Uso de expresiones lambda

Las expresiones lambda son especialmente útiles cuando desea realizar operaciones en una lista o en otra colección y desea evitar el trabajo adicional de definir una función. Muchas funciones de biblioteca de F# toman valores de función como argumentos, y puede ser especialmente útil usar una expresión lambda en esos casos. El código siguiente aplica una expresión lambda a elementos de una lista. En este caso, la función anónima suma 1 a cada elemento de una lista.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet302.fs)]

## <a name="see-also"></a>Vea también

- [Funciones](index.md)
