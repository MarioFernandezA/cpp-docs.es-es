---
title: /U, /u (Anular la definición de símbolos)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.UndefinePreprocessorDefinitions
- VC.Project.VCCLWCECompilerTool.UndefinePreprocessorDefinitions
- VC.Project.VCCLCompilerTool.UndefineAllPreprocessorDefinitions
- /u
- VC.Project.VCCLWCECompilerTool.UndefineAllPreprocessorDefinitions
helpviewer_keywords:
- -U compiler option [C++]
- Undefine Symbols compiler option
- /U compiler option [C++]
- U compiler option [C++]
ms.assetid: 7bc0474f-6d1f-419b-807d-0d8816763b2a
ms.openlocfilehash: 1ccda218a2bccc261653016ad6a47d419ddacfd9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50624450"
---
# <a name="u-u-undefine-symbols"></a>/U, /u (Anular la definición de símbolos)

El **/U** opción del compilador anula la definición del símbolo de preprocesador especificado. El **/u** los símbolos específicos de Microsoft que define el compilador anula la definición de opción del compilador.

## <a name="syntax"></a>Sintaxis

```
/U[ ]symbol
/u
```

## <a name="arguments"></a>Argumentos

*Símbolo*<br/>
El símbolo de preprocesador para anular la definición.

## <a name="remarks"></a>Comentarios

Ni el **/U** o **/u** opción puede anular la definición de un símbolo creado mediante el uso de la **#define** directiva.

El **/U** opción puede anular la definición de un símbolo que se definió anteriormente mediante la **/D** opción.

De forma predeterminada, el compilador define los siguientes símbolos específicos de Microsoft.

|Símbolo|Función|
|------------|--------------|
|_CHAR_UNSIGNED|Tipo de carácter predeterminado es sin signo. Definida cuando la [/j](../../build/reference/j-default-char-type-is-unsigned.md) se especifica la opción.|
|_CPPRTTI|Definida para el código compilado con la [/GR](../../build/reference/gr-enable-run-time-type-information.md) opción.|
|_CPPUNWIND|Definida para el código compilado con la [/EHsc](../../build/reference/eh-exception-handling-model.md) opción.|
|_DLL|Definida cuando la [/MD](../../build/reference/md-mt-ld-use-run-time-library.md) se especifica la opción.|
|_M_IX86|De forma predeterminada, definida en 600 para x86 destinos.|
|_MSC_VER|Para obtener más información, consulta [Predefined Macros](../../preprocessor/predefined-macros.md).|
|_WIN32|Definida para aplicaciones WIN32. Siempre definido.|
|_MT|Definida cuando la [/MD o/MT](../../build/reference/md-mt-ld-use-run-time-library.md) se especifica la opción.|

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio

1. Abra el cuadro de diálogo **Páginas de propiedades** del proyecto. Para obtener más información, vea [Trabajar con propiedades del proyecto](../../ide/working-with-project-properties.md).

1. Haga clic en la carpeta **C/C++** .

1. Haga clic en el **avanzadas** página de propiedades.

1. Modificar el **Anular definiciones del preprocesador** o **anular todas las definiciones del preprocesador** propiedades.

### <a name="to-set-this-compiler-option-programmatically"></a>Para establecer esta opción del compilador mediante programación

- Vea <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UndefineAllPreprocessorDefinitions%2A> o <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UndefinePreprocessorDefinitions%2A>.

## <a name="see-also"></a>Vea también

[Opciones del compilador](../../build/reference/compiler-options.md)<br/>
[Establecer las opciones del compilador](../../build/reference/setting-compiler-options.md)<br/>
[/J (El tipo de carácter predeterminado no tiene signo)](../../build/reference/j-default-char-type-is-unsigned.md)<br/>
[/GR (Habilitar la información de tipo en tiempo de ejecución)](../../build/reference/gr-enable-run-time-type-information.md)<br/>
[/EH (Modelo de control de excepciones)](../../build/reference/eh-exception-handling-model.md)<br/>
[/MD, /MT, /LD (Usar la biblioteca en tiempo de ejecución)](../../build/reference/md-mt-ld-use-run-time-library.md)