---
title: _rotl8, _rotl16
ms.date: 11/04/2016
f1_keywords:
- _rotl8
- _rotl16
helpviewer_keywords:
- _rotl8 intrinsic
- _rotl16 intrinsic
ms.assetid: 8c519ab6-aef9-4f07-a387-daee8408368f
ms.openlocfilehash: 63a4b342db58b37070c9348ac9eff1044a54a28b
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/09/2018
ms.locfileid: "51327959"
---
# <a name="rotl8-rotl16"></a>_rotl8, _rotl16

**Específicos de Microsoft**

Girar los valores de entrada a la izquierda hacia el bit más significativo (MSB) según un número especificado de posiciones de bit.

## <a name="syntax"></a>Sintaxis

```
unsigned char _rotl8(
   unsigned char value,
   unsigned char shift
);
unsigned short _rotl16(
   unsigned short value,
   unsigned char shift
);
```

#### <a name="parameters"></a>Parámetros

*valor*<br/>
[in] El valor se va a girar.

*shift*<br/>
[in] El número de bits que se va a girar.

## <a name="return-value"></a>Valor devuelto

El valor girado.

## <a name="requirements"></a>Requisitos

|Función intrínseca|Arquitectura|
|---------------|------------------|
|`_rotl8`|x86, ARM, x64|
|`_rotl16`|x86, ARM, x64|

**Archivo de encabezado** \<intrin.h >

## <a name="remarks"></a>Comentarios

A diferencia de una operación de desplazamiento a la izquierda, al ejecutar un giro a la izquierda, los bits de valor superior que caen fuera del extremo superior se mueven a las posiciones de los bits menos significativos.

## <a name="example"></a>Ejemplo

```
// rotl.cpp
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(_rotl8, _rotl16)

int main()
{
    unsigned char c = 'A', c1, c2;

    for (int i = 0; i < 8; i++)
    {
       printf_s("Rotating 0x%x left by %d bits gives 0x%x\n", c,
               i, _rotl8(c, i));
    }

    unsigned short s = 0x12;
    int nBit = 10;

    printf_s("Rotating unsigned short 0x%x left by %d bits gives 0x%x\n",
            s, nBit, _rotl16(s, nBit));
}
```

```Output
Rotating 0x41 left by 0 bits gives 0x41
Rotating 0x41 left by 1 bits gives 0x82
Rotating 0x41 left by 2 bits gives 0x5
Rotating 0x41 left by 3 bits gives 0xa
Rotating 0x41 left by 4 bits gives 0x14
Rotating 0x41 left by 5 bits gives 0x28
Rotating 0x41 left by 6 bits gives 0x50
Rotating 0x41 left by 7 bits gives 0xa0
Rotating unsigned short 0x12 left by 10 bits gives 0x4800
```

**FIN de Específicos de Microsoft**

## <a name="see-also"></a>Vea también

[_rotr8, _rotr16](../intrinsics/rotr8-rotr16.md)<br/>
[Intrínsecos del controlador](../intrinsics/compiler-intrinsics.md)