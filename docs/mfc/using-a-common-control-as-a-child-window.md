---
title: Usar un control común como ventana secundaria
ms.date: 11/04/2016
helpviewer_keywords:
- controls [MFC], using as child windows
- windows [MFC], common controls as
- child windows [MFC], common controls as
- common controls [MFC], child windows
- Windows common controls [MFC], child windows
ms.assetid: 608f7d47-7854-4fce-bde9-856c51e76753
ms.openlocfilehash: 690b48cf50e95265aaf5bdd454e2881b8f5fab3f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50655135"
---
# <a name="using-a-common-control-as-a-child-window"></a>Usar un control común como ventana secundaria

Cualquiera de los controles comunes de Windows puede utilizarse como una ventana secundaria de cualquier otra ventana. El siguiente procedimiento describe cómo crear un control común de forma dinámica y, a continuación, trabajar con ellos.

### <a name="to-use-a-common-control-as-a-child-window"></a>Para utilizar un control común como ventana secundaria

1. Definir el control en la clase relacionada o controlador.

1. Use la invalidación del control de la [CWnd:: Create](../mfc/reference/cwnd-class.md#create) método para crear el control de Windows.

1. Una vez creado el control (tan pronto como el `OnCreate` controlador si subclase del control), puede manipular el control mediante sus funciones miembro. Vea las descripciones de los controles individuales en [controles](../mfc/controls-mfc.md) para obtener más información sobre los métodos.

1. Cuando haya terminado con el control, utilice [CWnd:: DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow) para destruir el control.

## <a name="see-also"></a>Vea también

[Creación y uso de controles](../mfc/making-and-using-controls.md)<br/>
[Controles](../mfc/controls-mfc.md)

