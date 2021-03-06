---
title: ¿Qué es un flujo?
ms.date: 11/04/2016
helpviewer_keywords:
- reading data [C++], iostream programming
- data [C++], reading
- streams [C++], in iostream classes
- streams [C++]
ms.assetid: a7e661e9-6cd1-4543-a9a4-c58ee9fd32f3
ms.openlocfilehash: 9b8821861baed53880a00695204a4555994dccb3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50637091"
---
# <a name="what-a-stream-is"></a>¿Qué es un flujo?

Al igual que C, C++ no tiene capacidad integrada de entrada y salida. Pero todos los compiladores de C++ incluyen un paquete sistemático de E/S orientado a objetos, conocido como las clases iostream. La secuencia es el concepto central de las clases iostream. Puede pensar en un objeto de secuencia como en un archivo inteligente que actúa como origen y destino de bytes. Las características de una secuencia se determinan por su clase y por operadores de inserción y extracción personalizados.

A través de los controladores de dispositivo, el sistema operativo de disco se ocupa del teclado, la pantalla, la impresora y los puertos de comunicación como archivos extendidos. Las clases iostream interactúan con estos archivos extendidos. Las clases integradas admiten la lectura y escritura en la memoria con una sintaxis idéntica a la de E/S de disco, lo que facilita la derivación de las clases de secuencia.

## <a name="in-this-section"></a>En esta sección

[Alternativas de entrada/salida](../standard-library/input-output-alternatives.md)

## <a name="see-also"></a>Vea también

[Programación con iostream](../standard-library/iostream-programming.md)<br/>
