---
title: Error del compilador C2437
ms.date: 11/04/2016
f1_keywords:
- C2437
helpviewer_keywords:
- C2437
ms.assetid: 2d2b3c6c-856a-4b27-ae10-64813b3e5483
ms.openlocfilehash: 93b642d9bfbb5a8d938e3dfba6e3ad5fe8b3cbb0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50460676"
---
# <a name="compiler-error-c2437"></a>Error del compilador C2437

'identifier': ya inicializado

Un objeto se puede inicializar una sola vez.

El ejemplo siguiente genera C2437:

```
// C2437.cpp
// compile with: /c
class A {
public:
   A(int i) {}
};

class B : A {
   B() : A(1), A(2) {}   // C2437
   B() : A(1) {}   // OK
};
```