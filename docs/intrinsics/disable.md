---
title: _disable
ms.date: 11/04/2016
f1_keywords:
- _disable_cpp
- _disable
helpviewer_keywords:
- _disable intrinsic
- rsm instruction
- disable intrinsic
ms.assetid: 52da3df9-815c-4524-9839-6d1742cff5c6
ms.openlocfilehash: 64e7031ab578632322dfd5c73eb81e0750c1e0b5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50587816"
---
# <a name="disable"></a>_disable

**Específicos de Microsoft**

Deshabilita las interrupciones.

## <a name="syntax"></a>Sintaxis

```
void _disable(void);
```

## <a name="requirements"></a>Requisitos

|Función intrínseca|Arquitectura|
|---------------|------------------|
|`_disable`|x86, ARM, x64|

**Archivo de encabezado** \<intrin.h >

## <a name="remarks"></a>Comentarios

`_disable` indica al procesador que debe borrar la marca de la interrupción. En sistemas x86, esta función genera la instrucción Borrar marca de interrupción (`cli`).

Esta función solo está disponible en modo kernel. Si se utiliza en modo de usuario, se produce una excepción de Instrucción privilegiada en tiempo de ejecución.

En las plataformas ARM, esta rutina solo está disponible como intrínseco.

**FIN de Específicos de Microsoft**

## <a name="see-also"></a>Vea también

[Intrínsecos del controlador](../intrinsics/compiler-intrinsics.md)