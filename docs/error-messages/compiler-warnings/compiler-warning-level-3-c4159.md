---
title: Compilador advertencia (nivel 3) C4159
ms.date: 11/04/2016
f1_keywords:
- C4159
helpviewer_keywords:
- C4159
ms.assetid: e2cf964e-f4b8-4b2c-9569-1abb94307232
ms.openlocfilehash: e898af8f109ed23bd1784df7b39c174bbed675f2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50552287"
---
# <a name="compiler-warning-level-3-c4159"></a>Compilador advertencia (nivel 3) C4159

> #<a name="pragma-pragmapop--has-popped-previously-pushed-identifier-identifier"></a>pragma pragma(pop,...): ha sacado de identificador insertado anteriormente '*identificador*'

## <a name="remarks"></a>Comentarios

El código fuente contiene un **inserción** seguido de la instrucción con un identificador para una pragma un **pop** instrucción sin identificador. Como resultado, *identificador* usa extraído y posteriores de *identificador* puede provocar un comportamiento inesperado.

## <a name="example"></a>Ejemplo

Para evitar esta advertencia, indique un identificador en el **pop** instrucción. Por ejemplo:

```cpp
// C4159.cpp
// compile with: /W3
#pragma pack(push, f)
#pragma pack(pop)   // C4159

// using the identifier resolves the warning
// #pragma pack(pop, f)

int main()
{
}
```