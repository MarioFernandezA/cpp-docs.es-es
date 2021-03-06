---
title: Fecha y hora
ms.date: 11/04/2016
helpviewer_keywords:
- time, MFC programming
- time
- MFC, date and time
- dates, MFC
ms.assetid: ecf56dc5-d418-4603-ad3e-af7e205a6403
ms.openlocfilehash: dcb5ef9f21987e11608cfa29e77b24e96153e6b3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50459454"
---
# <a name="date-and-time"></a>Fecha y hora

MFC admite varias maneras de trabajar con fechas y horas. Se incluyen los siguientes:

- Clases en tiempo de uso general. El [CTime](../atl-mfc-shared/reference/ctime-class.md) y [CTimeSpan](../atl-mfc-shared/reference/ctimespan-class.md) clases encapsulan gran parte de la funcionalidad asociada a la biblioteca en tiempo de ANSI estándar, que se declara en el tiempo. H.

- Compatibilidad con el reloj del sistema. Con la versión 3.0 de MFC, se agregó compatibilidad a `CTime` para Win32 `SYSTEMTIME` y `FILETIME` tipos de datos.

- Compatibilidad con la automatización [tipo de datos DATE](../atl-mfc-shared/date-type.md). Admite la fecha, hora y los valores de fecha y hora. El [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md) y [COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md) clases encapsulan esta funcionalidad. Funcionan con el [COleVariant](../mfc/reference/colevariant-class.md) con compatibilidad de automatización de la clase.

## <a name="what-do-you-want-to-know-more-about"></a>¿Qué desea saber más sobre

- [Fecha y hora: Compatibilidad con SYSTEMTIME](../atl-mfc-shared/date-and-time-systemtime-support.md)

- [Fecha y hora: Compatibilidad de automatización](../atl-mfc-shared/date-and-time-automation-support.md)

- [Fecha y hora: Compatibilidad con bases de datos](../atl-mfc-shared/date-and-time-database-support.md)

## <a name="see-also"></a>Vea también

[Conceptos](../mfc/mfc-concepts.md)<br/>
[Temas generales de MFC](../mfc/general-mfc-topics.md)

