---
title: Eventos (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- events [Visual Basic], about events
- events [Visual Basic]
ms.assetid: 8fb0353a-e41b-4e23-b78f-da65db832f70
ms.openlocfilehash: b69615a5cf05427a2bfde82af976cfafb41171b0
ms.sourcegitcommit: 869b5832b667915ac4a5dd8c86b1109ed26b6c08
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2018
ms.locfileid: "39332878"
---
# <a name="events-visual-basic"></a>Eventos (Visual Basic)
Aunque puede visualizar un proyecto de Visual Studio como una serie de procedimientos que se ejecutan en una secuencia, en realidad, la mayoría de los programas está dirigidos por eventos, lo que significa que el flujo de ejecución está determinado por elementos externos denominados *eventos*.  
  
 Un evento es una señal que comunica a una aplicación que ha sucedido algo importante. Por ejemplo, cuando un usuario hace clic en un control en un formulario, el formulario puede provocar un evento `Click` y llamar a un procedimiento que controla el evento. Los eventos también permiten que las tareas independientes se comuniquen. Por ejemplo, supongamos que la aplicación realiza una tarea de ordenación de manera independiente a la aplicación principal. Si un usuario cancela la ordenación, la aplicación puede enviar un evento de cancelación que indica al proceso de ordenación que se detenga.  
  
## <a name="event-terms-and-concepts"></a>Conceptos y términos de eventos  
 Esta sección describen los términos y conceptos que se usan con eventos en Visual Basic.  
  
### <a name="declaring-events"></a>Declarar eventos  
 Puede declarar eventos dentro de clases, estructuras, módulos e interfaces con la palabra clave `Event`, como en el ejemplo siguiente:  
  
 [!code-vb[VbVbalrEvents#24](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_1.vb)]  
  
### <a name="raising-events"></a>Generación de eventos  
 Un evento es como un mensaje que anuncia que ha sucedido algo importante. La acción de difundir el mensaje se denomina *generar* el evento. En Visual Basic, los eventos se producen con el `RaiseEvent` instrucción, como en el ejemplo siguiente:  
  
 [!code-vb[VbVbalrEvents#25](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_2.vb)]  
  
 Los eventos deben generarse dentro del ámbito de la clase, del módulo o de la estructura donde se declaran. Por ejemplo, una clase derivada no puede generar eventos heredados de una clase base.  
  
### <a name="event-senders"></a>Remitentes de eventos  
 Cualquier objeto capaz de generar un evento es un *remitente del evento*, lo que también se conoce como *origen del evento*. Los formularios, controles y objetos definidos por el usuario son ejemplos de remitentes de eventos.  
  
### <a name="event-handlers"></a>Controladores de eventos  
 Los *controladores de eventos* son procedimientos que se invocan cuando se produce un evento correspondiente. Puede utilizar cualquier subrutina válida con una firma coincidente como un controlador de eventos. Sin embargo, no se puede utilizar una función como un controlador de eventos, porque no devolverá un valor al origen del evento.  
  
 Visual Basic utiliza una convención de nomenclatura estándar para controladores de eventos que combina el nombre del remitente del evento, un carácter de subrayado y el nombre del evento. Por ejemplo, el evento `Click` de un botón con nombre `button1` se denominaría `Sub button1_Click`.  
  
> [!NOTE]
>  Se recomienda utilizar esta convención de nomenclatura al definir controladores de eventos para sus propios eventos, pero no es necesario; puede utilizar cualquier nombre de subrutina válido.  
  
## <a name="associating-events-with-event-handlers"></a>Asociación de eventos con controladores de eventos  
 Antes de poder utilizar un controlador de eventos, primero debe asociarlo con un evento mediante la utilización de la instrucción `Handles` o `AddHandler`.  
  
### <a name="withevents-and-the-handles-clause"></a>WithEvents y la cláusula Handles  
 La instrucción `WithEvents` y la cláusula `Handles` proporcionan una forma declarativa de especificar controladores de eventos. Un evento generado por un objeto declarado con la palabra clave `WithEvents` puede controlarse mediante cualquier procedimiento con una instrucción `Handles` para ese evento, tal como se muestra en el ejemplo siguiente:  
  
 [!code-vb[VbVbalrEvents#1](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_3.vb)]  
  
 La instrucción `WithEvents` y la cláusula `Handles` suelen ser la mejor opción para controladores de eventos, porque la sintaxis declarativa que utilizan hace que el control de eventos sea más fácil de codificar, leer y depurar. Sin embargo, tenga en cuenta las siguientes limitaciones en el uso de variables `WithEvents`:  
  
-   No puede usar una variable `WithEvents` como una variable de objeto. Es decir, no puede declararla como `Object`: debe especificar el nombre de clase al declarar la variable.  
  
-   Dado que los eventos compartidos no están asociados a instancias de clase, no puede usar `WithEvents` para controlar eventos compartidos de forma declarativa. De forma similar, no puede usar `WithEvents` o `Handles` para controlar eventos desde `Structure`. En ambos casos, puede usar la instrucción `AddHandler` para controlar dichos eventos.  
  
-   No puede crear matrices de las variables `WithEvents`.  
  
 Las variables `WithEvents` permiten que un único controlador de eventos controle uno o varios tipos de eventos, o bien que uno o varios controladores de eventos controlen el mismo tipo de eventos.  
  
 Aunque la cláusula `Handles` es la forma estándar de asociar un evento con un controlador de eventos, tiene la limitación de que solo puede asociar eventos con controladores de eventos en tiempo de compilación.  
  
 En algunos casos, como con eventos asociados con formularios o controles, Visual Basic automáticamente stubs de un controlador de eventos vacío y lo asocia con un evento. Por ejemplo, cuando hace doble clic en un botón de comando en un formulario en modo de diseño, Visual Basic crea un controlador de eventos vacío y un `WithEvents` variable para el botón de comando, como se muestra en el código siguiente:  
  
 [!code-vb[VbVbalrEvents#26](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_4.vb)]  
  
### <a name="addhandler-and-removehandler"></a>AddHandler y RemoveHandler  
 La instrucción `AddHandler` es similar a la cláusula `Handles` por el hecho de que ambas permiten especificar un controlador de eventos. Sin embargo, `AddHandler`, que se utiliza con `RemoveHandler`, aporta más flexibilidad que la cláusula `Handles`, ya que permite agregar, eliminar y cambiar de forma dinámica el controlador de eventos asociado con un evento. Si desea controlar eventos compartidos o eventos de una estructura, debe utilizar `AddHandler`.  
  
 `AddHandler` adopta dos argumentos: el nombre de un evento de un remitente de eventos como un control y una expresión que evalúa a un delegado. No es necesario especificar explícitamente la clase delegada al utilizar `AddHandler`, puesto que la instrucción `AddressOf` siempre devuelve una referencia al delegado. En el ejemplo siguiente se asocia un controlador de eventos a un evento generado por un objeto:  
  
 [!code-vb[VbVbalrEvents#28](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_5.vb)]  
  
 `RemoveHandler`, que desconecta un evento de un controlador de eventos, utiliza la misma sintaxis que `AddHandler`. Por ejemplo:  
  
 [!code-vb[VbVbalrEvents#29](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_6.vb)]  
  
 En el ejemplo siguiente, un controlador de eventos está asociado a un evento, y se genera el evento. El controlador de eventos detecta el evento y muestra un mensaje.  
  
 A continuación, se quita el primer controlador de eventos y se asocia otro diferente al evento. Cuando se vuelve a generar el evento, se muestra un mensaje diferente.  
  
 Por último, se quita el segundo controlador de eventos, y el evento se genera por tercera vez. Dado que ya no hay ningún controlador de eventos asociado al evento, no se realiza ninguna acción.  
  
 [!code-vb[VbVbalrEvents#38](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_7.vb)]  
  
## <a name="handling-events-inherited-from-a-base-class"></a>Control de eventos heredados de una clase base  
 *Clases derivadas*: clases que heredan características de una clase base, que pueden controlar eventos generados por su clase base con la instrucción `Handles``MyBase`.  
  
#### <a name="to-handle-events-from-a-base-class"></a>Para controlar eventos de una clase base  
  
-   Declare un controlador de eventos en la clase derivada; para ello, agregue una instrucción `Handles MyBase.`*eventname* a la línea de declaración del procedimiento del controlador de eventos, donde *eventname* es el nombre del evento de la clase base que se va a controlar. Por ejemplo:  
  
     [!code-vb[VbVbalrEvents#12](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_8.vb)]  
  
## <a name="related-sections"></a>Secciones relacionadas  
  
|Title|Descripción|  
|-----------|-----------------|  
|[Tutorial: Declarar y provocar eventos](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)|Proporciona una descripción detallada de cómo declarar y generar eventos para una clase.|  
|[Tutorial: Controlar eventos](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)|Muestra cómo escribir un procedimiento de controlador de eventos.|  
|[Declarar eventos personalizados para evitar bloqueos](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)|Muestra cómo definir un evento personalizado que permite invocar a sus controladores de eventos de forma asincrónica.|  
|[Declarar eventos personalizados para conservar memoria](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)|Muestra cómo definir un evento personalizado que utiliza la memoria solo cuando se controla el evento.|  
|[Solucionar problemas de controladores de eventos heredados en Visual Basic](../../../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)|Enumera los problemas habituales que se producen con los controladores de eventos en componentes heredados.|  
|[Eventos](../../../../standard/events/index.md)|Proporciona una descripción general del modelo de eventos de [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].|  
|[Crear controladores de eventos en Windows Forms](../../../../framework/winforms/creating-event-handlers-in-windows-forms.md)|Describe cómo trabajar con eventos asociados a objetos de Windows Forms.|  
|[Delegados](../../../../visual-basic/programming-guide/language-features/delegates/index.md)|Proporciona información general sobre delegados en Visual Basic.|
