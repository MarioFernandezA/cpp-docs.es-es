---
title: Abrir carpeta de los proyectos de Visual C++ | Documentos de Microsoft
ms.custom: 
ms.date: 08/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: Open Folder Projects in Visual C++
ms.assetid: abd1985e-3717-4338-9e80-869db5435175
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 72106bd363987d39fb11c9ec1a6d3fd0ceb5665d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="open-folder-projects-in-visual-c"></a>Abrir carpeta de los proyectos en Visual C++
Visual Studio de 2017 presenta la característica de "Abrir carpeta", que le permite abrir una carpeta de archivos de origen e inmediatamente comenzar a codificar con compatibilidad con IntelliSense, exploración, refactorización, depuración y así sucesivamente. No se ha cargado ningún archivo .sln o .vcxproj; Si es necesario, puede especificar las tareas personalizadas así como crear y los parámetros de inicio a través de los archivos .json simple. Con la tecnología de carpeta abierta, Visual C++ ahora puede admitir no solo malas recopilaciones de archivos, sino también a prácticamente cualquier sistema de compilación, incluidos CMake, Ninja, QMake (para los proyectos de Qt), gyp, SCons, Gradle, Buck, creación y mucho más. 

Para usar la carpeta abierta, en el menú principal seleccione *archivo | Abra | Carpeta* o presione *Ctrl + Mayús + Alt + O*. El Explorador de soluciones muestra inmediatamente todos los archivos en la carpeta. Puede hacer clic en cualquier archivo comience a editarlo. En segundo plano, Visual Studio inicia la indización de los archivos para habilitar IntelliSense, navegación y características de refactorización. Como editar, crear, mover o eliminar archivos, Visual Studio realiza automáticamente un seguimiento de los cambios y actualiza continuamente su índice de IntelliSense. 
  
## <a name="cmake-projects"></a>Proyectos de CMake
CMake está integrado en el IDE de Visual Studio como CMake Tools para Visual C++, un componente de la carga de trabajo de escritorio de C++. Para obtener más información, consulte [Herramientas de CMake para Visual C++](cmake-tools-for-visual-cpp.md).
 
## <a name="qmake-projects-that-target-the-qt-framework"></a>QMake proyectos que tienen como destino el marco de trabajo de Qt
Puede usar herramientas CMake para Visual C++ para destino Qt para compilar proyectos Qt, o puede usar la extensión Qt de Visual Studio. Nota: A partir de agosto de 2017 el [compatibilidad de extensión de Visual Studio Qt para Visual Studio de 2017](https://download.qt.io/development_releases/vsaddin/) está disponible como una versión beta.

## <a name="gyp-cons-scons-buck-etc"></a>gyp, inconvenientes, SCons, Buck, etcetera
Puede usar cualquier sistema de compilación en Visual C++ y seguir disfrutando de las ventajas del IDE de Visual C++ y depurador. Cuando se abre la carpeta raíz del proyecto, Visual C++ utiliza la heurística para indizar los archivos de origen IntelliSense y la exploración. Puede proporcionar sugerencias acerca de la estructura del código al editar el archivo CppProperties.json. De forma similar, puede configurar el programa de compilación editando el archivo launch.vs.json. 

## <a name="configuring-open-folder-projects"></a>Configurar los proyectos de la carpeta abierta
Puede personalizar un proyecto de la carpeta abierta a través de tres archivos JSON:
|||
|-|-|
|CppProperties.json|Especifique la información de configuración personalizada para la exploración. Crear este archivo, si es necesario, en la carpeta raíz del proyecto.|
|Launch.VS.JSON|Especifique los argumentos de línea de comandos. Se accede a través de la **el Explorador de soluciones** elemento de menú contextual **iniciar configuración y depuración**.|
|Tasks.VS.JSON|Especificar los comandos de compilación personalizada y los modificadores del compilador. Se accede a través de la **el Explorador de soluciones** elemento de menú contextual **configurar tareas**.|

### <a name="configure-intellisense-with-cpppropertiesjson"></a>Configurar IntelliSense con CppProperties.json
IntelliSense y el comportamiento de la búsqueda en parte depende de la configuración de compilación activa, que define #include rutas de acceso, los modificadores del compilador y otros parámetros. De forma predeterminada, Visual Studio proporciona configuraciones Debug y Release. Para algunos proyectos, debe crear una configuración personalizada en orden para IntelliSense y las características de exploración para comprender totalmente el código. Para definir una nueva configuración, cree un archivo denominado CppProperties.json en la carpeta raíz. A continuación se muestra un ejemplo:

```json
{
  "configurations": [
    {
      "name": "Windows x64",
      "includePath": [ "include" ],
      "defines": [ "_DEBUG" ],
      "compilerSwitches": "/std:c++17",
      "intelliSenseMode": "msvc-x64",
      "forcedInclude": [ "pch.h" ],
      "undefines": []
    }
  ]
}
```
Una configuración puede tener cualquiera de las siguientes propiedades:

|||  
|-|-| 
|`name`|el nombre de configuración que aparece en la lista desplegable de configuración de C++|
|`includePath`|la lista de carpetas que se deben especificar en la ruta de acceso de inclusión (se asigna a/i para la mayoría de los compiladores)|
|`defines`|la lista de macros que debe estar definido (se asigna a /D para la mayoría de los compiladores)|
|`compilerSwitches`|uno o varios conmutadores adicionales que pueden influir en el comportamiento de IntelliSense|
|`forcedInclude`|encabezado que se incluirá automáticamente en cada unidad de compilación (se asigna a /FI para MSVC o - incluir para clang)|
|`undefines`|la lista de macros como no definido (se asigna a /U para MSVC)|
|`intelliSenseMode`|el motor de IntelliSense para usarse. Puede especificar las variantes específicas de la arquitectura para MSVC, gcc o Clang:
- MSVC-x86 (valor predeterminado)
- MSVC x64
- MSVC arm
- Windows-clang-x86
- Windows-clang-x64
- Windows-clang-arm
- Linux x64
- Linux x86
- Arm de Linux
- gccarm

Expansión de variables de entorno de admite y CppProperties.json para incluir las rutas de acceso y otros valores de propiedad. La sintaxis es `${env.FOODIR}` para expandir una variable de entorno `%FOODIR%`.

También tienen acceso a las siguientes macros integradas dentro de este archivo:
|||
|-|-|
|`${workspaceRoot}`| la ruta de acceso completa a la carpeta de área de trabajo|
|`${projectRoot}`| la ruta de acceso completa a la carpeta donde se colocan los CppProperties.json|
|`${vsInstallDir}`| la ruta de acceso completa a la carpeta donde está instalada la instancia en ejecución de VS de 2017|

Por ejemplo, si el proyecto tiene una carpeta de inclusión y también incluye windows.h y otros encabezados comunes de Windows SDK, puede que desee actualizar su CppProperties.json archivo de configuración con estos incluye:

```json
{
  "configurations": [
    {
      "name": "Windows",
      "includePath": [
        // local include folder
        "${workspaceRoot}\\include",
        // Windows SDK and CRT headers
        "${env.WindowsSdkDir}include\\${env.WindowsSDKVersion}\\ucrt",
        "${env.NETFXSDKDir}\\include\\um",
        "${env.WindowsSdkDir}include\\${env.WindowsSDKVersion}\\um",
        "${env.WindowsSdkDir}include\\${env.WindowsSDKVersion}\\shared",
        "${env.VCToolsInstallDir}include"
      ]
    }
  ]
}
```

**Nota:** `%WindowsSdkDir%` y `%VCToolsInstallDir%` no se establecen como variables de entorno globales, así que asegúrese de iniciar devenv.exe un "Developer desde línea de comandos para VS 2017" que define estas variables.

Para solucionar problemas de IntelliSense errores causados por falta incluyen rutas de acceso, abra la **lista de errores** y filtrar sus resultados a "Sólo IntelliSense" y el código de error E1696 "no puede abrir el archivo de código fuente...". 

Puede crear cualquier número de configuraciones en CppProperties.json. Cada una aparecerá en la lista desplegable de configuración:

```json
{
  "configurations": [
    {
      "name": "Windows",
      ...
    },
    {
      "name": "with EXTERNAL_CODECS",
      ...
    }
  ]
}
```
### <a name="define-tasks-with-tasksvsjson"></a>Definir las tareas con tasks.vs.json
Puede automatizar scripts de compilación ni ninguna otra operación externos en los archivos en el área de trabajo actual mediante la ejecución de ellos como tareas directamente en el IDE. Puede configurar una nueva tarea, haga doble clic en un archivo o carpeta y seleccione **configurar tareas**. 

![Abrir carpeta configurar tareas](media/open-folder-config-tasks.png)

Esto crea (o abre) el `tasks.vs.json` archivo en la carpeta de VS que Visual Studio crea en la carpeta raíz del proyecto. Puede definir cualquier tarea arbitrario en este archivo y, a continuación, invocarlo desde el **el Explorador de soluciones** menú contextual. En el ejemplo siguiente se muestra un archivo tasks.vs.json que define una sola tarea. `taskName`define el nombre que aparece en el menú contextual. `appliesTo`define qué archivos se pueden realizar el comando en. El `command` propiedad hace referencia a la variable de entorno COMSPEC, que identifica la ruta de acceso de la consola (cmd.exe en Windows). El `args` propiedad especifica la línea de comandos que se debe invocar. El `${file}` macro recupera el archivo seleccionado en **el Explorador de soluciones**. En el ejemplo siguiente se muestra el nombre de archivo del archivo .cpp seleccionada actualmente.

```json
{
  "version": "0.2.1",
  "tasks": [
    {
      "taskName": "Echo filename",
      "appliesTo": "*.cpp",
      "type": "command",
      "command": "${env.COMSPEC}",
      "args": ["echo ${file}"]
    }
  ]
}
```
Después de guardar tasks.vs.json, puede haga clic en cualquier archivo .cpp en la carpeta, elija **eco filename** desde el menú contextual y vea el nombre de archivo que se muestra en la ventana de salida.

#### <a name="appliesto"></a>appliesTo
Puede crear tareas para cualquier archivo o carpeta especificando su nombre en el `appliesTo` campo, por ejemplo `"appliesTo" : "hello.cpp"`. Las máscaras de archivo siguientes se pueden usar como valores:
|||
|-|-|
|`"*"`| tarea está disponible para todos los archivos y carpetas en el área de trabajo|
|`"*/"`| tarea está disponible para todas las carpetas en el área de trabajo|
|`"*.cpp"`| tarea está disponible para todos los archivos con la extensión .cpp en el área de trabajo|
|`"/*.cpp"`| tarea está disponible para todos los archivos con la extensión .cpp en la raíz del área de trabajo|
|`"src/*/"`| tarea está disponible para todas las subcarpetas de la carpeta "src"|
|`"makefile"`| tarea está disponible para todos los archivos MAKE en el área de trabajo|
|`"/makefile"`| tarea solo está disponible para el archivo MAKE en la raíz del área de trabajo|

#### <a name="output"></a>salida
Use la `output` propiedad para especificar el archivo ejecutable que se iniciará cuando se presiona **F5**. Por ejemplo:

```json
      "output": "${workspaceRoot}\\bin\\hellomake.exe" 
```

#### <a name="macros-for-tasksvsjson"></a>Macros para tasks.vs.json

|||
|-|-|
|`${env.<VARIABLE>}`| Especifica las variables de entorno (por ejemplo, ${env. Ruta de acceso} ${env.COMSPEC} y así sucesivamente) que se establece para el símbolo del sistema para desarrolladores. Para obtener más información, consulte [símbolo del sistema para desarrolladores de Visual Studio](/dotnet/framework/tools/developer-command-prompt-for-vs).|
|`${workspaceRoot}`| la ruta de acceso completa a la carpeta de área de trabajo (por ejemplo, "C:\sources\hello")|
|`${file}`| la ruta de acceso completa del archivo o carpeta seleccionado para ejecutar esta tarea (por ejemplo, "C:\sources\hello\src\hello.cpp")|
|`${relativeFile}`| la ruta de acceso relativa al archivo o carpeta (por ejemplo, "src\hello.cpp")|
|`${fileBasename}`| el nombre del archivo sin la ruta de acceso o la extensión (por ejemplo, "Hola")|
|`${fileDirname}`| la ruta de acceso completa al archivo, sin incluir el nombre de archivo (por ejemplo, "C:\sources\hello\src")|
|`${fileExtname}`| la extensión del archivo seleccionado (por ejemplo, ".cpp")|

#### <a name="custom-macros"></a>Macros personalizadas
Para definir una macro personalizada en tasks.vs.json, agregue un par de nombre: valor antes de los bloques de tarea. En el ejemplo siguiente se define una macro denominada `outDir` que se consume en la `args` propiedad:

```json
{
"version": "0.2.1",
  "outDir": "${workspaceRoot}\\bin",
  "tasks": [
    {
      "taskName": "List outputs",
      "*",
      "type": "command",
      "command": "${env.COMSPEC}",
      "args": [
        "dir ${outDir}"
      ]
    }
  ]
```

### <a name="configure-debugging-parameters-with-launchvsjson"></a>Configurar parámetros de depuración con launch.vs.json
Para personalizar los argumentos de línea de comandos del programa, haga doble clic en el archivo ejecutable en **el Explorador de soluciones** y seleccione **iniciar configuración y depuración**. Se abrirá otra `launch.vs.json` archivo, o si no existe ninguno, creará un nuevo archivo rellenada previamente con la información acerca del programa que seleccionó. 

Para especificar argumentos adicionales, agregue simplemente en el `args` matriz JSON como se muestra en el ejemplo siguiente:

```json
{
  "version": "0.2.1",
  "defaults": {},
  "configurations": [
    {
      "type": "default",
      "project": "CPP\\7zip\\Bundles\\Alone\\O\\7za.exe",
      "name": "7za.exe list content of helloworld.zip",
      "args": [ "l", "d:\\sources\\helloworld.zip" ]
    }
  ]
}
```

Al guardar este archivo, la nueva configuración aparece en la lista desplegable destino de depuración y puede seleccionarlo para iniciar al depurador. Puede crear muchas configuraciones de depuración como sea necesario, para cualquier número de ejecutables. Si presiona **F5** ahora, el depurador se inicie y se alcanza cualquier punto de interrupción ya establecido. Todas las ventanas de depurador familiar y su funcionalidad ahora están disponibles.

## <a name="see-also"></a>Vea también
[IDE y herramientas para desarrollo de Visual C++](ide-and-tools-for-visual-cpp-development.md)
