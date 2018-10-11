---
title: importar (atributo de COM de C++) | Microsoft Docs
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.import
dev_langs:
- C++
helpviewer_keywords:
- import attribute
ms.assetid: ebf07cae-39fb-4047-8b57-54af0a9a83de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a0509f6c1292ee7bb2e1ba97d1f75c626f3b0761
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "48792426"
---
# <a name="import"></a>importación

Especifica otro archivo .idl, .odl o encabezado que contiene las definiciones que desea hacer referencia desde la principal IDL.

## <a name="syntax"></a>Sintaxis

```cpp
[ import(
   idl_file
) ];
```

### <a name="parameters"></a>Parámetros

*idl_file*<br/>
El nombre de un archivo .idl que desea importar en la biblioteca de tipos del proyecto actual.

## <a name="remarks"></a>Comentarios

El **importar** hace que el atributo de C++ un `#import` instrucción colocarse debajo el `import "docobj.idl"` instrucción en el archivo .idl generado. El **importar** atributo tiene la misma funcionalidad que el [importar](/windows/desktop/Midl/import) atributo MIDL.

El **importar** atributo sólo coloca el archivo especificado en el archivo .idl que se generará el proyecto; el **importar** atributo no le permite llamar a construcciones en el archivo especificado desde el código fuente en el proyecto.  Para llamar a construcciones en el archivo especificado desde el código fuente en el proyecto, utilice [#import](../../preprocessor/hash-import-directive-cpp.md) y `embedded_idl` atributo, o bien puede incluir el archivo .h el *idl_file*, si existe un archivo .h.

## <a name="example"></a>Ejemplo

El código siguiente:

```cpp
// cpp_attr_ref_import.cpp
// compile with: /LD
[module(name="MyLib")];
[import(import.idl)];
```

genera el código siguiente en el archivo .idl generado:

```
import "docobj.idl";
import "import.idl";

[ uuid(EED3644C-8488-3ECD-BA97-147DB3CDB499), version(1.0) ]
library MyLib {
   importlib("stdole2.tlb");
   importlib("olepro32.dll");
...
```

## <a name="requirements"></a>Requisitos

### <a name="attribute-context"></a>Contexto de atributo

|||
|-|-|
|**Se aplica a**|En cualquier lugar|
|**Reiterativo**|No|
|**Atributos requeridos**|Ninguna|
|**Atributos no válidos**|Ninguna|

Para obtener más información, consulte [contextos de atributo](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Vea también

[Atributos IDL](idl-attributes.md)<br/>
[Atributos independientes](stand-alone-attributes.md)<br/>
[importidl](importidl.md)<br/>
[importlib](importlib.md)<br/>
[include](include-cpp.md)<br/>
[includelib](includelib-cpp.md)  