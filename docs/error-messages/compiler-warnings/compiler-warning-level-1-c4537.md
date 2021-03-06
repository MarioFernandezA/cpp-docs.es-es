---
title: Advertencia del compilador (nivel 1) C4537
ms.date: 08/27/2018
f1_keywords:
- C4537
helpviewer_keywords:
- C4537
ms.assetid: 9454493c-d419-475e-8f35-9c00233c9329
ms.openlocfilehash: 2f97be4e1aaa5143df685cb95935d350e6f02534
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50441328"
---
# <a name="compiler-warning-level-1-c4537"></a>Advertencia del compilador (nivel 1) C4537

> '*objeto*': '*operador*' aplicado al tipo no definido por el usuario

## <a name="remarks"></a>Comentarios

Se pasó una referencia donde se esperaba un objeto (tipo definido por el usuario). Una referencia no es un objeto, pero no es capaz de hacer la distinción entre código ensamblador alineado. El compilador genera código como si *objeto* fuera una instancia.

## <a name="example"></a>Ejemplo

El ejemplo siguiente genera C4537 y muestra cómo corregirlo:

```cpp
// C4537.cpp
// compile with: /W1 /c
// processor: x86
struct S {
    int member;
};

void f1(S &s) {
    __asm mov eax, s.member;   // C4537
    // try the following code instead
    // or, make the declaration "void f1(S s)"
    /*
    mov eax, s
    mov eax, [eax]s.member
    */
}
```