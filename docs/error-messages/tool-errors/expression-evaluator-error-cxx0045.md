---
title: Error del evaluador de expresiones CXX0045
ms.date: 11/04/2016
f1_keywords:
- CXX0045
helpviewer_keywords:
- CXX0045
- CAN0045
ms.assetid: 32181bc8-e79c-4ad7-a82f-47c62ec06d7d
ms.openlocfilehash: 04ce1d8332a92c6221bf91e122e753f709911036
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50488093"
---
# <a name="expression-evaluator-error-cxx0045"></a>Error del evaluador de expresiones CXX0045

no es una función

Se proporcionó una lista de argumentos para un símbolo en el programa que no es el nombre de una función.

## <a name="example"></a>Ejemplo

```
queue( alpha, beta )
```

Cuando `queue` no es una función.

Este error es idéntico a CAN0045.