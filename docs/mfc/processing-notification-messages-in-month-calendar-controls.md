---
title: Procesar mensajes de notificación en los controles de calendario mensual
ms.date: 11/04/2016
helpviewer_keywords:
- CMonthCalCtrl class [MFC], notifications
- CMonthCalCtrl class [MFC], day states
- month calendar controls [MFC], notification messages
- notifications [MFC], for CMonthCalCtrl
- notifications [MFC], month calendar control
ms.assetid: 607c3e90-0756-493b-9503-ce835a50c7ab
ms.openlocfilehash: 3dbf50080bea59c4df4a9c92a135a65b093f7674
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50511935"
---
# <a name="processing-notification-messages-in-month-calendar-controls"></a>Procesar mensajes de notificación en los controles de calendario mensual

Cuando los usuarios interactúan con el control de calendario mensual (selección de fechas o ver un mes distinto), el control (`CMonthCalCtrl`) envía mensajes de notificación a su ventana primaria, normalmente un objeto de vista o cuadro de diálogo. Controle estos mensajes si desea hacer algo en respuesta. Por ejemplo, cuando el usuario selecciona un nuevo mes para ver, podría proporcionar un conjunto de fechas que se debe enfatizar.

Use la ventana Propiedades para agregar controladores de notificación a la clase primaria para aquellos mensajes que desee implementar.

En la lista siguiente describe las distintas notificaciones enviadas por el control de calendario mensual.

- MCN_GETDAYSTATE solicita información acerca de los días que deben mostrarse en negrita. Para obtener información sobre cómo controlar esta notificación, consulte [establecer el estado de día de un Control de calendario mensual](../mfc/setting-the-day-state-of-a-month-calendar-control.md).

- MCN_SELCHANGE Notifica a la principal que ha cambiado la fecha seleccionada o un rango de la fecha.

- MCN_SELECT notifica al elemento primario que se ha realizado una selección de fecha de forma explícita.

## <a name="see-also"></a>Vea también

[Uso de CMonthCalCtrl](../mfc/using-cmonthcalctrl.md)<br/>
[Controles](../mfc/controls-mfc.md)

