---
title: + (Concatenación de cadenas) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 580130fa-6c7c-4f76-a47d-d22c27ccadf6
ms.openlocfilehash: 8a1785d590c5f7fcc443856180d516bb40cfc28e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43500885"
---
# <a name="-string-concatenation-entity-sql"></a>+ (Concatenación de cadenas) (Entity SQL)
Concatena dos cadenas.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
expression + expression  
```  
  
## <a name="arguments"></a>Argumentos  
 `expression`  
 Cualquier expresión válida de los tipos de datos EDM.String. Ambas expresiones deben ser del mismo tipo de datos o una se debe poder convertir implícitamente en el tipo de datos de la otra.  
  
## <a name="result-types"></a>Tipos de resultado  
 El tipo de datos que resulta de la promoción de tipos implícita de dos argumentos. Para obtener más información acerca de la promoción de tipos implícita, vea [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).  
  
## <a name="example"></a>Ejemplo  
 La siguiente consulta de Entity SQL usa el operador +  para concatenar dos cadenas. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1.  Siga el procedimiento de [Cómo: ejecutar una consulta que muestra los resultados PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2.  Pase la consulta siguiente como argumento al método `ExecutePrimitiveTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#CONCAT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#concat)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [Tipos de modelo conceptual (CSDL)](https://msdn.microsoft.com/library/987b995f-e429-4569-9559-b4146744def4)
