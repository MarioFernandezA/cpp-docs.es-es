---
title: setbuf
ms.date: 11/04/2016
apiname:
- setbuf
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- setbuf
helpviewer_keywords:
- setbuf function
- stream buffering
ms.assetid: 13beda22-7b56-455d-8a6c-f2eb636885b9
ms.openlocfilehash: 3b5fbccd304d406131b0c4f7d16a289f80484642
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50440501"
---
# <a name="setbuf"></a>setbuf

Controla el almacenamiento en búfer de la secuencia. Esta función está en desuso; use [setvbuf](setvbuf.md) en su lugar.

## <a name="syntax"></a>Sintaxis

```C
void setbuf(
   FILE *stream,
   char *buffer
);
```

### <a name="parameters"></a>Parámetros

*secuencia*<br/>
Puntero a la estructura **FILE**.

*buffer*<br/>
Búfer asignado por el usuario.

## <a name="remarks"></a>Comentarios

El **setbuf** funcionar los controles para el almacenamiento en búfer *secuencia*. El *secuencia* argumento debe hacer referencia a un archivo abierto que no leído o escrito. Si el *búfer* argumento es **NULL**, la secuencia es no almacenado en búfer. Si no, el búfer debe apuntar a una matriz de caracteres de longitud **BUFSIZ**, donde **BUFSIZ** es el tamaño del búfer como se define en STDIO. H. Para el almacenamiento en búfer de E/S se usa el búfer especificado por el usuario, y no el búfer predeterminado asignado por el sistema para la secuencia especificada. El **stderr** secuencia es no almacenado en búfer de forma predeterminada, pero puede usar **setbuf** para asignar búferes a **stderr**.

**setbuf** ha sido reemplazado por [setvbuf](setvbuf.md), que es la rutina preferida para el nuevo código. **setbuf** se conserva por compatibilidad con el código existente.

## <a name="requirements"></a>Requisitos

|Rutina|Encabezado necesario|
|-------------|---------------------|
|**setbuf**|\<stdio.h>|

Para obtener información adicional sobre compatibilidad, consulte [Compatibilidad](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Ejemplo

```C
// crt_setbuf.c
// compile with: /W3
// This program first opens files named DATA1 and
// DATA2. Then it uses setbuf to give DATA1 a user-assigned
// buffer and to change DATA2 so that it has no buffer.

#include <stdio.h>

int main( void )
{
   char buf[BUFSIZ];
   FILE *stream1, *stream2;

   fopen_s( &stream1, "data1", "a" );
   fopen_s( &stream2, "data2", "w" );

   if( (stream1 != NULL) && (stream2 != NULL) )
   {
      // "stream1" uses user-assigned buffer:
      setbuf( stream1, buf ); // C4996
      // Note: setbuf is deprecated; consider using setvbuf instead
      printf( "stream1 set to user-defined buffer at: %Fp\n", buf );

      // "stream2" is unbuffered
      setbuf( stream2, NULL ); // C4996
      printf( "stream2 buffering disabled\n" );
      _fcloseall();
   }
}
```

```Output
stream1 set to user-defined buffer at: 0012FCDC
stream2 buffering disabled
```

## <a name="see-also"></a>Vea también

[E/S de secuencia](../../c-runtime-library/stream-i-o.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[fflush](fflush.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[setvbuf](setvbuf.md)<br/>
