---
title: Error del compilador C3772
ms.date: 11/04/2016
f1_keywords:
- C3772
helpviewer_keywords:
- C3772
ms.assetid: 63e938d4-088d-41cc-a562-5881a05b5710
ms.openlocfilehash: 9a72cb9ee5d1d839f6ca5d113c25795f83dab811
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50595681"
---
# <a name="compiler-error-c3772"></a>Error del compilador C3772

"name": declaración de plantilla friend no válida

No es válida para declarar un elemento friend de una especialización de plantilla de clase. No puede declarar una especialización parcial o explícita de una plantilla de clase y declarar en la misma instrucción un elemento friend de esa especialización. El marcador *name* identifica la declaración no válida.

### <a name="to-correct-this-error"></a>Para corregir este error

- No declare un elemento friend de una especialización de plantilla de clase.

- Si es adecuado para la aplicación, declare un elemento friend de la plantilla de clase o declare un elemento friend de una especialización parcial o explícita determinada.

## <a name="example"></a>Ejemplo

En el ejemplo de código siguiente se produce un error, porque se declara un elemento friend de una especialización parcial de una plantilla de clase.

```cpp
// c3772.cpp
// compile with: /c

// A class template.
    template<class T> class A {};

// A partial specialization of the class template.
    template<class T> class A<T*> {};

// An explicit specialization.
    template<> class A<char>;

class X {
// Invalid declaration of a friend of a partial specialization.
    template<class T> friend class A<T*>; // C3772

// Instead, if it is appropriate for your application, declare a
// friend of the class template. Consequently, all specializations
// of the class template are friends:
//    template<class T> friend class A;
// Or declare a friend of a particular partial specialization:
//    friend class A<int*>;
// Or declare a friend of a particular explicit specialization:
//    friend class A<char>;
};
```

## <a name="see-also"></a>Vea también

[Templates](../../cpp/templates-cpp.md) (Plantillas [C++])<br/>
[Especialización de plantilla](../../cpp/template-specialization-cpp.md)
