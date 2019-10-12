---
title: Compatibilidad con versiones
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
ms.date: 4/17/2018
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection: M365-voice
localization_priority: Normal
description: En este artículo se describe la compatibilidad del ciclo de vida de las salas de Microsoft Teams.
ms.openlocfilehash: 89706c2459c8f27c71017cc4f2b19395afaf5ead
ms.sourcegitcommit: e84becc101232b8017aab519378480c5dbebbb48
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/11/2019
ms.locfileid: "37468470"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Compatibilidad de versiones de la aplicación salas de Microsoft Teams
 
La aplicación salas de Microsoft Teams recibe actualizaciones varias veces por año. Cada actualización admitida por doce (12) meses a partir de la fecha de publicación de disponibilidad general (GA). Se proporciona soporte técnico para los doce (12) meses completos. Sin embargo, la estructura de soporte es dinámica, con dos fases distintas que dependen de la disponibilidad de la última versión:

- \- **Fase de mantenimiento y actualizaciones críticas** cuando ejecuta la versión más reciente de la aplicación salas de Microsoft Teams, recibe actualizaciones periódicas que contienen actualizaciones *de seguridad y mantenimiento de servicios* .

- **Fase** \- actualizaciones de seguridad solo cuando se publica una nueva versión de la aplicación salas de Microsoft Teams, las versiones anteriores de la aplicación tienen un nivel de compatibilidad reducido con *las actualizaciones de seguridad solo* durante el resto del ciclo de vida de doce (12) meses.

> [!NOTE]
> La versión más reciente siempre está en la fase de mantenimiento y actualizaciones críticas. Cuando encuentre un defecto de código que garantice una actualización crítica, también debe tener instalada la última versión para recibir una corrección. Todas las demás versiones admitidas solo podrán recibir actualizaciones de seguridad.

Toda la asistencia finaliza después del ciclo de vida de doce (12) meses para una versión vencida o si se han publicado más de dos actualizaciones desde entonces. Después, los clientes deben actualizar a una versión compatible.

Todas las versiones se enumeran en las notas de la [versión de Microsoft Teams Rooms](srs2-release-note.md).

## <a name="windows-10-release-support"></a>Soporte técnico para Windows 10

Las salas de Microsoft Teams requieren las SKU de Windows 10 IoT Enterprise o Windows 10 Enterprise en opciones de mantenimiento del canal semianual. Estas otras ediciones de Windows 10 no son compatibles:

- Ediciones de la sucursal de mantenimiento a largo plazo (LTSB) de Windows 10 Enterprise y del canal de mantenimiento a largo plazo (LTSC)
- Windows 10 Internet of Things (IoT) Enterprise LTSB/LTSC Edition
- cualquier otra edición de Windows, como Windows 10 Pro o Home Edition

Una actualización de características de Windows 10 no se ofrece ni actualiza inmediatamente en los dispositivos de las salas de Microsoft Teams. Un retraso intencionado de hasta seis meses después de la fecha de disponibilidad general Publicada en la página de información de la [versión de Windows 10](https://docs.microsoft.com/windows/release-information/) . El tiempo de retraso se usa para validar la compatibilidad de la versión de Windows 10 para la aplicación salas de Microsoft Teams, hardware de dispositivo y periféricos de video de audio certificados. La validación comienza y continúa durante el desarrollo activo de cada versión principal de Windows 10. Se necesita más tiempo para validar que todos los fabricantes de dispositivos han creado imágenes actualizadas para sus dispositivos y Microsoft Teams para certificar y probar dichas imágenes. Durante el período de validación, la aplicación de Microsoft Team Room usa [las directivas de grupo de Windows Update para empresas](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) para retrasar las actualizaciones de características de Windows 10. Después de encontrar y resolver cualquier problema de compatibilidad, el bloque se eleva mediante la actualización de directivas de grupo a través de una nueva versión de la aplicación en la tienda Windows. Los dispositivos que ejecutan la aplicación salas de Microsoft Teams se actualizan automáticamente a una versión de Windows 10 adecuada durante el reinicio de mantenimiento nocturno. Una versión de MSI está disponible para los clientes que desean administrar las actualizaciones de forma manual.  

Durante el período de validación, los dispositivos de salas de Microsoft Teams Rooms **no** se actualizarán de ninguna manera a la siguiente versión de Windows 10. Esto incluye la invalidación de las directivas de grupo vigentes o el uso de System Center u otros servicios de administración de dispositivos de terceros. Cualquiera de estas causas puede causar problemas en la aplicación de Microsoft Teams Room o puede dejar los dispositivos inutilizables.  

En la tabla siguiente se muestran las versiones recomendadas y compatibles de Windows 10 que se han verificado para que sean compatibles con salas de Microsoft Teams. Todas las fechas aparecen en formato ISO 8601: AAAA-MM-DD.

|Versión  |Fecha de disponibilidad   |Estado de soporte técnico de salas de Microsoft Teams   |Versión mínima de la aplicación salas de Microsoft Teams | Compilación recomendada de sistema operativo  |
|:---  |:---       |:---                |:---    |:--- |
| 1903 |2019-05-21 |Posible <br/>Recomendado |4.2.4.0 |18362,356 |
| 1809 |2019-03-28 |Omitidos <br/>No se recomienda &#x2780; |&#x2014; |&#x2014; |
| 1803 |2018-07-10 |Compatible           |4.1.22.0 |17134,191 |
| 1709 |2018-01-18 |No compatible       |&#x2014; |&#x2014;|
| 1703 |2017-07-11 |No compatible       |&#x2014; |&#x2014;|
||||| |

Si usa una versión compatible de Windows 10, siempre obtendrá las actualizaciones de aplicaciones más recientes para la aplicación salas de Microsoft Teams.  

&#x2780; la versión de Windows 10 1809 no se recomienda debido a problemas de compatibilidad con la aplicación salas de Microsoft Teams. Este problema específico hace que la aplicación salas de Microsoft Teams no se inicie tras el reinicio nocturno. Este problema se ha solucionado en la versión de Windows 10 1903.  

## <a name="see-also"></a>Vea también

[Ayuda de Salas de Microsoft Teams](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Notas de la versión de Microsoft Teams Rooms](srs2-release-note.md)

[Plan para salas de Microsoft Teams](skype-room-systems-v2-0.md)
