---
title: Advertencia del compilador (nivel 4) C4296
ms.date: 11/04/2016
f1_keywords:
- C4296
helpviewer_keywords:
- C4296
ms.assetid: 9d99aafe-f6bd-4ee0-b8d0-98ce5712274d
ms.openlocfilehash: 74a2df69120436d0bb3a0a02809a1523a3766445
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50624654"
---
# <a name="compiler-warning-level-4-c4296"></a>Advertencia del compilador (nivel 4) C4296

'operator': expresión siempre es false

Se utilizó una variable sin signo en una operación de comparación con cero.

De forma predeterminada, esta advertencia está desactivada. Vea [Advertencias del compilador desactivadas de forma predeterminada](../../preprocessor/compiler-warnings-that-are-off-by-default.md) para más información.

El ejemplo siguiente genera C4296:

```
// C4296.cpp
// compile with: /W4
#pragma warning(default : 4296)
int main()
{
   unsigned int u = 9;
   if (u < 0)    // C4296
      u++;
   if (u >= 0)   // C4296
      u++;
}
```