---
title: Error del compilador C2530
ms.date: 11/04/2016
f1_keywords:
- C2530
helpviewer_keywords:
- C2530
ms.assetid: b790a312-48df-4a6a-9e27-be2c5f32f16c
ms.openlocfilehash: 2c8164cad25d68ee61ff9fed7170482d5dfc9505
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50474794"
---
# <a name="compiler-error-c2530"></a>Error del compilador C2530

'identifier': se deben inicializar referencias

Debe inicializar una referencia cuando se declara, a menos que ya se haya declarado:

- Con la palabra clave [extern](../../cpp/using-extern-to-specify-linkage.md).

- Como miembro de una clase, estructura o unión (y se inicializa en el constructor).

- Como un parámetro en una definición o declaración de función.

- Como el tipo de valor devuelto de una función.

El ejemplo siguiente genera C2530:

```
// C2530.cpp
int main() {
   int i = 0;
   int &j;   // C2530
   int &k = i;   // OK
}
```