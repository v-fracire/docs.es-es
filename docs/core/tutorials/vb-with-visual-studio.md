---
title: Aplicación Hola mundo de .NET Core con Visual Basic en Visual Studio 2017
description: Obtenga información sobre cómo crear una sencilla aplicación de consola .NET Core con Visual Basic mediante Visual Studio 2017.
author: rpetrusha
ms.author: ronpet
ms.date: 08/07/2017
dev_langs:
- vb
ms.custom: vs-dotnet, seodec18
ms.openlocfilehash: 612de47c4d40d1272eb330a0343302109040f434
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53149386"
---
# <a name="build-a-net-core-visual-basic-hello-world-application-in-visual-studio-2017"></a>Compilación de una aplicación Hola mundo de .NET Core con Visual Basic en Visual Studio 2017

En este tema se proporciona una introducción detallada para compilar, depurar y publicar una sencilla aplicación de consola .NET Core con Visual Basic en Visual Studio 2017. Visual Studio 2017 proporciona un entorno de desarrollo completo para la compilación de aplicaciones .NET Core. Siempre que la aplicación no tenga dependencias específicas de la plataforma, la aplicación puede ejecutarse en cualquier plataforma que tenga como destino .NET Core y en cualquier sistema que tenga instalado .NET Core.

## <a name="prerequisites"></a>Requisitos previos

[Visual Studio de 2017](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada. Puede desarrollar su aplicación con .NET Core 2.0.

Para obtener más información, vea [Requisitos previos para .NET Core en Windows](../../core/windows-prerequisites.md).

## <a name="a-simple-hello-world-application"></a>Una aplicación Hola mundo sencilla

Comience creando una aplicación de consola "Hola mundo" sencilla. Siga estos pasos:

1. Inicie Visual Studio 2017. Seleccione **Archivo** > **Nuevo** > **Proyecto** de la barra de menús. En el cuadro de diálogo *Nuevo proyecto**, seleccione el nodo **Visual Basic** seguido del nodo **.NET Core**. Después, seleccione la plantilla del proyecto **Aplicación de consola (.NET Core)**. En el cuadro de texto **Nombre**, escriba "Hola mundo". Seleccione el botón **Aceptar**.

   ![Cuadro de diálogo Nuevo proyecto con la aplicación de consola seleccionada](./media/vb-with-visual-studio/new-project.png)
   
1. Visual Studio usa la plantilla para crear el proyecto. La plantilla de aplicación de consola de Visual Basic para .NET Core define automáticamente una clase, `Program`, con un único método, `Main`, que adopta una matriz <xref:System.String> como argumento. `Main` es el punto de entrada de la aplicación, el método que se llama automáticamente mediante el tiempo de ejecución cuando inicia la aplicación. Los argumentos de línea de comandos proporcionados cuando se inicia la aplicación están disponibles en la matriz *args*.

   ![Visual Studio y el nuevo proyecto Hola mundo](./media/vb-with-visual-studio/devenv.png)

   La plantilla crea una aplicación "Hola mundo" sencilla. Llama al método <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> para mostrar la cadena literal "Hola mundo" en la ventana de la consola. Al seleccionar el botón **HelloWorld** con la flecha verde en la barra de herramientas, puede ejecutar el programa en modo de depuración. Si lo hace, la ventana de la consola se mostrará durante poco tiempo antes de cerrarse. Esto ocurre porque el método `Main` finaliza y la aplicación termina en cuanto se ejecuta la única instrucción en el método `Main`.

1. Para que la aplicación se pause antes de que se cierre la ventana de la consola, agregue el siguiente código inmediatamente después de la llamada al método <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType>:

   ```vb
   Console.Write("Press any key to continue...")
   Console.ReadKey(true)
   ```
   Este código pide al usuario que presione cualquier tecla y, a continuación, detiene el programa hasta que se presiona una tecla.

1. En la barra de menús, seleccione **Compilar** > **Compilar solución**. De esta forma, el programa se compila en un lenguaje intermedio (IL) que se convierte en código binario mediante un compilador Just-In-Time (JIT).

1. Seleccione el botón **HelloWorld** con la flecha verde en la barra de herramientas para ejecutar el programa.

   ![Ventana de la consola que muestra Hola mundo Presione cualquier tecla para continuar](./media/with-visual-studio/helloworld1.png)

1. Presione cualquier tecla para cerrar la ventana de consola.

## <a name="enhancing-the-hello-world-application"></a>Mejorar la aplicación Hola mundo

Mejore su aplicación para pedir su nombre al usuario y mostrarlo junto con la fecha y la hora. Para modificar y probar el programa, haga lo siguiente:

1. Escriba el siguiente código de Visual Basic en la ventana de código inmediatamente después del corchete de apertura que sigue a la línea `Sub Main(args As String())` y antes del primer corchete de cierre:

   [!code-vb[GettingStarted#1](../../../samples/snippets/core/tutorials/vb-with-visual-studio/helloworld.vb#1)]

   Este código reemplaza las instrucciones <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>, <xref:System.Console.Write%2A?displayProperty=nameWithType> y <xref:System.Console.ReadKey%2A?displayProperty=nameWithType> existentes.

   ![Archivo del programa Visual Studio con el método Main actualizado](./media/vb-with-visual-studio/codewindow.png)

   Este código muestra "What is your name?" en la ventana de la consola y espera a que el usuario escriba una cadena seguida de la tecla Entrar. Almacena esta cadena en una variable denominada `name`. También recupera el valor de la propiedad <xref:System.DateTime.Now?displayProperty=nameWithType>, que contiene la hora local actual, y lo asigna a una variable denominada `currentDate`. Por último, usa una [cadena interpolada](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md) para mostrar estos valores en la ventana de la consola.

1. Compile el programa; para ello, seleccione **Generar** > **Compilar solución**.

1. Ejecute el programa en modo de depuración en Visual Studio; para ello, seleccione la flecha verde en la barra de herramientas, presione F5 o seleccione el elemento de menú **Depurar** > **Iniciar depuración**. Responda a la solicitud escribiendo un nombre y presionando la tecla Entrar.

   ![Ventana de la consola con el resultado del programa modificado](./media/with-visual-studio/helloworld2.png)

1. Presione cualquier tecla para cerrar la ventana de consola.

Ha creado y ejecutado la aplicación. Para desarrollar una aplicación profesional, realice algunos pasos adicionales para preparar el lanzamiento de la aplicación:

- Para obtener información sobre la depuración de la aplicación, vea [Depuración de la aplicación Hola a todos en C# con Visual Studio 2017](debugging-with-visual-studio.md).

- Para obtener información sobre el desarrollo y publicación de una versión de distribución de la aplicación, vea [Publicación de la aplicación Hola a todos en C# con Visual Studio 2017](publishing-with-visual-studio.md).

<!--
## Related topics

Instead of a console application, you can also build a class library with .NET Core and Visual Studio 2017. For a step-by-step introduction, see [Building a class library with C# and .NET Core in Visual Studio 2017](library-with-visual-studio.md).

You can also develop a .NET Core console app on Mac, Linux, and Windows by using [Visual Studio Code](https://code.visualstudio.com/), a downloadable code editor. For a step-by-step tutorial, see [Getting Started with Visual Studio Code](with-visual-studio-code.md). -->
