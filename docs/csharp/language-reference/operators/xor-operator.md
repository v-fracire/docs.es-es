---
title: 'Operador ^: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ^_CSharpKeyword
helpviewer_keywords:
- ^ operator [C#]
- bitwise exclusive OR operator [C#]
ms.assetid: b09bc815-570f-4db6-a637-5b4ed99d014a
ms.openlocfilehash: f6f09f197502af1bc38bcdef97dd1db0ad9c7c08
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236952"
---
# <a name="-operator-c-reference"></a>Operador ^ (Referencia de C#)
Los operadores binarios `^` están predefinidos para los tipos enteros y `bool`. Para los tipos enteros, `^` calcula OR exclusiva bit a bit de sus operandos. Para operandos `bool`, `^` calcula OR exclusiva lógica de sus operandos; es decir, el resultado es `true` si y solo si exactamente uno de sus operandos es `true`.  
  
## <a name="remarks"></a>Comentarios  
 Los tipos definidos por el usuario pueden sobrecargar el operador `^` (vea [operator](../../../csharp/language-reference/keywords/operator.md)). Las operaciones de tipos enteros suelen estar permitidas en la enumeración.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csRefOperators#30](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-operator_1.cs)]  
  
 El cálculo de `0xf8 ^ 0x3f` en el ejemplo anterior realiza una operación OR exclusiva bit a bit de los siguientes dos valores binarios, que corresponden a los valores hexadecimales F8 y 3F:  
  
 `1111 1000`  
  
 `0011 1111`  
  
 El resultado de la OR exclusiva es `1100 0111`, que es C7 en hexadecimal.  
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../../../csharp/language-reference/index.md)  
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Operadores de C#](../../../csharp/language-reference/operators/index.md)
