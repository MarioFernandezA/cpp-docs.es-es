---
title: Error del compilador C2821
ms.date: 11/04/2016
f1_keywords:
- C2821
helpviewer_keywords:
- C2821
ms.assetid: e8d71988-a968-4484-94db-e8c3bad74a4a
ms.openlocfilehash: 5c725d9648a7800c68a2fbff20e594a400c296c8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50632558"
---
# <a name="compiler-error-c2821"></a>Error del compilador C2821

primer parámetro formal para 'operator new' debe ser 'unsigned int'

El primer parámetro formal de la [new (operador)](../../standard-library/new-operators.md#op_new) deben tener un signo `int`.

## <a name="example"></a>Ejemplo

El ejemplo siguiente genera C2821:

```cpp
// C2821.cpp
// compile with: /c
void * operator new( /* unsigned int,*/ void * );   // C2821
void * operator new( unsigned int, void * );
```