---
title: Vinculación interna
ms.date: 11/04/2016
helpviewer_keywords:
- internal linkage
- linkage [C++], internal
ms.assetid: 80be7b51-c930-43db-94d6-4f09a64077bf
ms.openlocfilehash: 79601af27f847a3afe7e8bdaefa926cd45459847
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2019
ms.locfileid: "56150745"
---
# <a name="internal-linkage"></a>Vinculación interna

Si la declaración de un identificador de ámbito de archivo para un objeto o una función contiene el *storage-class-specifier* **static**, el identificador tiene vinculación interna. De lo contrario, el identificador tiene vinculación externa. Vea [Clases de almacenamiento](../c-language/c-storage-classes.md) si desea una descripción del elemento no terminal *storage-class-specifier*.

Dentro de una unidad de traducción, cada instancia de un identificador con vinculación interna denota el mismo identificador o función. Los identificadores vinculados internamente son exclusivos para una unidad de traducción.

## <a name="see-also"></a>Vea también

[Usar extern para especificar la vinculación](../cpp/using-extern-to-specify-linkage.md)
