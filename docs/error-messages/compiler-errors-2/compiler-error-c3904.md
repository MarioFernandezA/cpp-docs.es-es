---
title: Error del compilador C3904
ms.date: 11/04/2016
f1_keywords:
- C3904
helpviewer_keywords:
- C3904
ms.assetid: 08297605-e4f2-4c6c-b637-011f1fd40631
ms.openlocfilehash: 8c7f4a2861825a35d676328b5e283a5e4087d85b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50519787"
---
# <a name="compiler-error-c3904"></a>Error del compilador C3904

'property_accessor': debe especificar número parámetros

Compruebe el número de parámetros en su `get` y `set` métodos con dimensiones de la propiedad.

- El número de parámetros para el `get` método debe ser igual al número de dimensiones de la propiedad o debe ser cero para las propiedades no indizadas.

- El número de parámetros de la `set` método debe ser uno más que el número de dimensiones de la propiedad.

Para obtener más información, consulta [property](../../windows/property-cpp-component-extensions.md).

## <a name="example"></a>Ejemplo

El ejemplo siguiente genera C3904.

```
// C3904.cpp
// compile with: /clr /c
ref class X {
   property int P {
      // set
      void set();   // C3904
      // try the following line instead
      // void set(int);

      // get
      int get(int, int);   // C3904
      // try the following line instead
      // int get();
   };
};
```

## <a name="example"></a>Ejemplo

El ejemplo siguiente genera C3904.

```
// C3904b.cpp
// compile with: /clr /c
ref struct X {
   property int Q[double, double, float, float, void*, int] {
      // set
      void set(double, void*);   // C3904
      // try the following line instead
      // void set(double, double, float, float, void*, int, int);

      // get
      int get();   // C3904
      // try the following line instead
      // int get(double, double, float, float, void*, int);
   }
};
```