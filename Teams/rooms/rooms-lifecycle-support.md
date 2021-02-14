---
title: Compatibilidad con versiones
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: Obtenga información sobre el soporte técnico de ciclo de vida de Microsoft Teams Rooms, incluida la estructura de soporte dinámico y sus fases.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 584f4661a39d21f916b2097c242f71b996c568e6
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662455"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Compatibilidad con la versión de la aplicación Salas de Microsoft Teams
 
La aplicación Salas de Microsoft Teams recibe actualizaciones varias veces al año. Cada actualización admitida durante doce (12) meses desde su fecha de lanzamiento de disponibilidad general (GA). Se proporciona soporte técnico para los doce (12) meses completos. Sin embargo, la estructura de soporte es dinámica, con dos fases distintas que dependen de la disponibilidad de la versión más reciente:

- **Fase de mantenimiento y actualizaciones críticas** \- Al ejecutar la última versión de la aplicación Salas de Microsoft Teams, recibirá actualizaciones periódicas que contienen actualizaciones de *seguridad y* mantenimiento.

- **Fase solo de actualizaciones de seguridad** \- Cuando se publica una nueva versión de la aplicación Salas de Microsoft  Teams, las versiones anteriores de la aplicación tienen un nivel de soporte reducido con actualizaciones de seguridad solo para el resto del ciclo de vida de doce (12) meses.

> [!NOTE]
> La última versión siempre está en la fase de mantenimiento y actualizaciones críticas. Cuando se produce un defecto de código que garantiza una actualización crítica, también debe tener instalada la versión más reciente para recibir una corrección. El resto de las versiones compatibles solo serán aptas para recibir actualizaciones de seguridad.

Todo el soporte finaliza después de que el ciclo de vida de doce (12) meses de una versión haya expirado o si desde entonces se han publicado más de dos actualizaciones. A continuación, los clientes deben actualizar a una versión compatible.

Todas las versiones se muestran en las notas [de la versión de salas de Microsoft Teams.](rooms-release-note.md)

## <a name="windows-10-release-support"></a>Soporte técnico para versiones de Windows 10

Salas de Microsoft Teams requiere las SKU de Windows 10 IoT Enterprise o Windows 10 Enterprise en las Semi-Annual de mantenimiento del Canal local. Estas otras ediciones de Windows 10 no son compatibles:

- Ediciones de la rama de mantenimiento a largo plazo (LTSB) de Windows 10 Enterprise y el Canal de mantenimiento a largo plazo (LTSC)
- Ediciones LtSB/LTSC de Windows 10 Internet of Things (IoT) Enterprise
- cualquier otra edición de Windows, como Windows 10 Pro u Home edition

Una actualización de características de Windows 10 no se ofrece ni se actualiza inmediatamente en los dispositivos de Microsoft Teams Rooms. Un retraso intencionado de hasta seis meses después de la fecha de disponibilidad general publicada en la página de información de la versión [de Windows 10.](https://docs.microsoft.com/windows/release-information/) El tiempo de retraso se usa para validar la compatibilidad de la versión de Windows 10 para la aplicación Salas de Microsoft Teams, el hardware del dispositivo y periféricos de vídeo de audio certificados. La validación comienza y continúa durante el desarrollo activo de cada versión principal de Windows 10. Se necesita más tiempo para validar que todos los fabricantes de dispositivos han creado imágenes actualizadas para sus dispositivos y para que Microsoft Teams certifique y pruebe esas imágenes. Durante el período de validación, la aplicación Microsoft Teams Room usa directivas de grupo de  [Windows Update](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) para empresas para retrasar las actualizaciones de características de Windows 10. Después de encontrar y resolver los problemas de compatibilidad, el bloque se levanta mediante la actualización de directivas de grupo a través de una nueva versión de aplicación en la Tienda Windows. Los dispositivos que ejecutan la aplicación Microsoft Teams Rooms se actualizan automáticamente a una versión apropiada de Windows 10 durante el reinicio del mantenimiento nocturno. Una versión de MSI está disponible para los clientes que deseen administrar las actualizaciones manualmente.  

> [!IMPORTANT]
> Durante el período de validación,  los dispositivos de Salas de Microsoft Teams no deben actualizarse a la siguiente versión de Windows 10 por ningún medio. Esto incluye la invalidación de las directivas de grupo en su lugar, o el uso de System Center u otros servicios de administración de dispositivos de terceros. Cualquiera de estos puede causar problemas para la aplicación Microsoft Teams Room o puede dejar dispositivos inutilizables.  

En la tabla siguiente se muestran las versiones recomendadas y compatibles de Windows 10 que se han comprobado que son compatibles con salas de Microsoft Teams. Todas las fechas se muestran en formato ISO 8601: YYYY-MM-DD.

|Versión  |Fecha de disponibilidad   |Estado del soporte de salas de Microsoft Teams   |Versión de aplicación Salas mínima de Microsoft Teams | Compilación del sistema operativo recomendada  |
|:---  |:---       |:---                                  |:---     |:---     |
| 20H2 |2020-10-20 |En validación, <br/>No compatible todavía|&#x2014; |19042.572 |
| 2004 |2020-05-27 |Omitido, <br/> No recomendado|&#x2014; |19041.264 |
| 1909 |2019-11-12 |Compatible, <br/>Recomendado |4.5.33.0 |18363.418  |
| 1903 |2019-05-21 |Compatible  |4.2.4.0 |18362.356 |
| 1809 |2019-03-28 |No compatible, <br/>Problemas de compatibilidad conocidos &#x2780;|&#x2014; |&#x2014; |
| 1803 |2018-07-10 |No compatible                             |&#x2014;  |&#x2014; |
| 1709 |2018-01-18 |No se admite                         |&#x2014; |&#x2014; |
| 1703 |2017-07-11 |No compatible                         |&#x2014; |&#x2014; |

&#x2780; no se recomienda usar la versión 1809 de Windows 10 debido a los problemas de compatibilidad encontrados con la aplicación Salas de Microsoft Teams. Este problema específico provoca que la aplicación Salas de Microsoft Teams no se inicie tras el reinicio nocturno. Este problema se solucionó en la versión 1903 de Windows 10.  

&#x2781; no se recomienda usar la versión 2004 de Windows 10 debido a los problemas de compatibilidad de la aplicación Salas de Microsoft Teams. Este problema específico provoca que la aplicación Microsoft Teams Rooms no se inicie tras el reinicio nocturno. 

Cuando use una versión compatible de Windows 10, siempre recibirá las últimas actualizaciones de aplicaciones para la aplicación Salas de Microsoft Teams.  

## <a name="related-topics"></a>Temas relacionados

[Ayuda de Salas de Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Notas de la versión de salas de Microsoft Teams](rooms-release-note.md)

[Plan para Salas de Microsoft Teams](rooms-plan.md)
