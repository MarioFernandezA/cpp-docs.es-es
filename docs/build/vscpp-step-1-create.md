﻿---
title: Cree un proyecto de aplicación de consola de C++
description: Crear una aplicación de consola Hola a todos en Visual C++
ms.custom: mvc
ms.date: 12/12/2017
ms.topic: tutorial
ms.devlang: cpp
ms.assetid: 45138d70-719d-42dc-90d7-1d0ca31a2f54
ms.openlocfilehash: 5722dcc06f5141818910e44a6160d12bcd4eaecd
ms.sourcegitcommit: beeb77b2976e997debc55b1af35024cc62e62799
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2018
ms.locfileid: "52977763"
---
# <a name="create-a-c-console-app-project"></a>Cree un proyecto de aplicación de consola de C++

El punto de partida habitual para un programador de C++ es un "Hello, world!", aplicación que se ejecuta en la línea de comandos. Eso es lo que creará en Visual Studio en este paso.

## <a name="prerequisites"></a>Requisitos previos

- Tenga Visual Studio con el entorno de desarrollo para escritorio de C++ instalado y ejecutándose en el equipo. Si aún no está instalado, consulte [soporte de instalación de C++ en Visual Studio 2017](../build/vscpp-step-0-installation.md).

## <a name="create-your-app-project"></a>Crear el proyecto de aplicación

Visual Studio usa *proyectos* para organizar el código de una aplicación y *soluciones* para organizar los proyectos. Un proyecto contiene todas las opciones, las configuraciones y reglas utilizadas para compilar sus aplicaciones y administra la relación entre todos los archivos del proyecto y todos los archivos externos. Para crear la aplicación, en primer lugar, creará un nuevo proyecto y solución.

1. En Visual Studio, abra el menú **archivo**  y elija **nuevo > proyecto** para abrir el cuadro de diálogo **nuevo proyecto**.

   ![Abra el cuadro de diálogo nuevo proyecto](../build/media/vscpp-file-new-project.gif "abrir el cuadro de diálogo nuevo proyecto")

1. En el cuadro de diálogo **nuevo proyecto** , seleccione **instalado**, y **Visual C++** si aún no está seleccionada, a continuación, elija la plantilla **proyecto vacío** . En el **nombre** , introduzca *HelloWorld*. Elija **Aceptar** para crear el proyecto.

   ![Asigne un nombre y crear el nuevo proyecto](../build/media/vscpp-concierge-project-name-callouts.png "nombre y crear el nuevo proyecto")

Visual Studio crea un proyecto nuevo y vacío, listo para especializar para el tipo de aplicación que quiera crear y agregar los archivos de código fuente. Hará esto a continuación.

[He tenido un problema.](#create-your-app-project-issues)

## <a name="make-your-project-a-console-app"></a>Convertir el proyecto en una aplicación de consola

Visual Studio puede crear todo tipo de aplicaciones y componentes de Windows y otras plataformas. La plantilla **proyecto vacío**  no es específica acerca de qué tipo de aplicación crea. Para crear un *aplicación de consola*, una que se ejecuta en una ventana de símbolo del sistema o de consola, debe indicar a Visual Studio que compile su aplicación para utilizar el subsistema de consola.

1. En Visual Studio, abra el menú **proyecto**  y elija **propiedades** para abrir el cuadro de diálogo **páginas de propiedades HelloWorld** .

1. En el cuadro de diálogo **páginas de propiedades** , en **propiedades de configuración**, seleccione **vinculador > sistema**, a continuación, seleccione el cuadro de edición situado junto a la propiedad **subsistema**. En el menú desplegable que aparece, seleccione **consola (/ SUBSYSTEM: CONSOLE)**  Elija **Aceptar** para guardar los cambios.

   ![Abra el cuadro de diálogo páginas de propiedades](../build/media/vscpp-properties-linker-subsystem.gif "abrir el cuadro de diálogo páginas de propiedades")

Ahora Visual Studio sabe como compilar el proyecto para que se ejecute en una ventana de consola. A continuación, Agregará un archivo de código fuente y escribirá el código de la aplicación.

[He tenido un problema.](#make-your-project-a-console-app-issues)

## <a name="add-a-source-code-file"></a>Agregar un archivo de código fuente

1. En **el Explorador de soluciones**, seleccione el proyecto HelloWorld. En la barra de menús, elija **Proyecto** > **Agregar nuevo elemento** para abrir el cuadro de diálogo **Agregar nuevo elemento**.

1. En el cuadro de diálogo **Agregar nuevo elemento** , y seleccione **Visual C++** en **instalado** si no está ya seleccionado. En el panel central, seleccione **archivo C++ (.cpp)**. Cambiar el **nombre** a *HelloWorld.cpp*. Elija **agregar** para cerrar el cuadro de diálogo y crear el archivo.

   ![Agregar un archivo de código fuente para HelloWorld.cpp](../build/media/vscpp-add-new-item.gif "agregar un archivo de código fuente para HelloWorld.cpp")

Visual studio crea un archivo de código fuente nuevo y lo abre en una ventana del editor, lista para escribir el código fuente.

[He tenido un problema.](#add-a-source-code-file-issues)

## <a name="add-code-to-the-source-file"></a>Agregue código al archivo de origen

1. Copie este código en la ventana del editor HelloWorld.cpp.

   ```cpp
   #include <iostream>

   int main()
   {
       std::cout << "Hello, world!" << std::endl;
       return 0;
   }
   ```

   En la ventana del editor, el código debe tener el siguiente aspecto:

   ![Hola código del mundo en el editor](../build/media/vscpp-hello-world-editor.png "código Hello World en el editor")

Cuando el código tiene este aspecto en el editor, está listo para continuar con el paso siguiente y compilar la aplicación.

[He tenido un problema.](#add-a-source-code-file-issues)

## <a name="next-steps"></a>Pasos siguientes

> [!div class="nextstepaction"]
> [Compilar y ejecutar un proyecto de C++](vscpp-step-2-build.md)

## <a name="troubleshooting-guide"></a>Guía de solución de problemas

Consulte aquí para encontrar soluciones a los problemas más comunes al crear su primer proyecto de C++.

### <a name="create-your-app-project-issues"></a>Problemas al crear la aplicación  del proyecto

Si el diálogo **nuevo proyecto** no muestra una entrada para **Visual C++**  en el cuadro **instalado**, probablemente su copia de Visual Studio no tiene el entorno de trabajo  **Desktop development with C++**  instalado. Puede ejecutar el instalador directamente desde el cuadro de diálogo **nuevo proyecto** . Elija el vínculo **abrir Visual Studio Installer** para iniciar el programa de instalación de nuevo. Si el diálogo  **User Account Control** solicita permisos, elija **Sí**. En el programa de instalación, asegúrese de que el **desarrollo de escritorio con C++/Desktop development with C++** este activado y elija **Aceptar** para actualizar la instalación de Visual Studio.

Si ya existe otro proyecto con el mismo nombre, elija otro nombre para el proyecto, o elimine el proyecto existente y vuelva a intentarlo. Para eliminar un proyecto existente, elimine la carpeta de solución (la carpeta que contiene el archivo helloworld.sln) en el Explorador de archivos.

[Volver atrás](#create-your-app-project).

### <a name="make-your-project-a-console-app-issues"></a>Problemas al convertir el proyecto en una aplicación de consola

Si no ve **vinculador** en las **propiedades de configuración**, elija **cancelar** para cerrar el cuadro de diálogo **páginas de propiedades** , a continuación, Asegúrese de que el proyecto **HelloWorld**  está seleccionado en **el Explorador de soluciones**, no la solución u otro archivo o carpeta, antes de que vuelva a intentarlo.

El control de la lista desplegable no aparece en el cuadro de edición de propiedad **subsistema** hasta que haya seleccionado la propiedad. Puede seleccionar mediante el puntero, o puede presionar Tab para desplazarse por los controles de cuadro de diálogo hasta que **subsistema** este resaltado. Elija el control dropdown o presione ALT+flecha abajo para abrirlo.

[Volver](#make-your-project-a-console-app)

### <a name="add-a-source-code-file-issues"></a>Problemas al agregar un archivo de código fuente

Está bien si asigna a el archivo de código fuente un nombre diferente. Sin embargo, no agregue más de un archivo de código fuente que contenga el mismo código a su proyecto.

Si agrega el tipo de archivo incorrecto al proyecto, por ejemplo, un archivo de encabezado, elimínelo y vuelva a intentarlo. Para eliminar el archivo, selecciónelo en **el Explorador de soluciones** y presione la tecla SUPR.

[Volver atrás](#add-a-source-code-file).

### <a name="add-code-to-the-source-file-issues"></a>Problemas al agregar contenido a un archivo de código fuente

Si accidentalmente ha cerrado la ventana del editor del archivo de código fuente, para abrirla de nuevo, haga doble clic en HelloWorld.cpp en la ventana de **Explorador de soluciones** .

Si aparece un subrayado ondulado rojo bajo cualquier elemento en el editor de código fuente, compruebe que el código coincide con el ejemplo de ortografía, puntuación y case. Case es una palabra reservada en código C++.

[Volver atrás](#add-code-to-the-source-file).

<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />
