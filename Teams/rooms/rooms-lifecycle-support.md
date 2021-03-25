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
description: Obtenga información sobre la compatibilidad con el ciclo de vida de salas de Microsoft Teams, incluida la estructura de soporte dinámico y sus fases.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e22bf9759920a5b4233fab9a6f6169f3a1153f0d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117448"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Compatibilidad con la versión de la aplicación Salas de Microsoft Teams
 
La aplicación Salas de Microsoft Teams recibe actualizaciones varias veces al año. Cada actualización admitida durante doce (12) meses desde su fecha de publicación de disponibilidad general (GA). Se proporciona soporte técnico durante los doce (12) meses completos. Sin embargo, la estructura de soporte es dinámica, con dos fases distintas que dependen de la disponibilidad de la versión más reciente:

- **Fase de mantenimiento y actualizaciones críticas** \- Al ejecutar la versión más reciente de la aplicación Salas de Microsoft Teams, recibirá actualizaciones periódicas que contienen actualizaciones de seguridad *y* mantenimiento.

- **Fase Solo actualizaciones de seguridad** \- Cuando se publica una nueva versión de la aplicación Salas de Microsoft  Teams, las versiones anteriores de la aplicación tienen un nivel de soporte técnico reducido con actualizaciones de seguridad solo para el resto del ciclo de vida de doce (12) meses.

> [!NOTE]
> La versión más reciente siempre está en la fase mantenimiento y actualizaciones críticas. Cuando se produce un defecto de código que justifica una actualización crítica, también debe tener instalada la versión más reciente para recibir una corrección. Todas las demás versiones compatibles solo podrán recibir actualizaciones de seguridad.

Todo el soporte técnico finaliza después de que el ciclo de vida de doce (12) meses de una versión haya expirado o si se han publicado más de dos actualizaciones desde entonces. A continuación, los clientes deben actualizar a una versión compatible.

Todas las versiones se muestran en las notas de la versión [salas de Microsoft Teams.](rooms-release-note.md)

## <a name="windows-10-release-support"></a>Compatibilidad con la versión de Windows 10

Microsoft Teams Rooms requiere las SKU de Windows 10 IoT Enterprise o Windows 10 Enterprise en Semi-Annual de mantenimiento del canal. Estas otras ediciones de Windows 10 no son compatibles:

- Ediciones de Windows 10 Enterprise Long-Term Servicing Branch (LTSB) / Long Term Servicing Channel (LTSC)
- Ediciones de Windows 10 Internet of Things (IoT) Enterprise LTSB /LTSC
- cualquier otra edición de Windows como Windows 10 Pro o Home edition

Una actualización de características de Windows 10 no se ofrece ni se actualiza inmediatamente en dispositivos microsoft Teams Rooms. Un retraso intencionado de hasta seis meses después de la fecha de disponibilidad general publicada en la página de información de la versión [de Windows 10.](/windows/release-information/) El tiempo de retraso se usa para validar la compatibilidad de la versión de Windows 10 para la aplicación Salas de Microsoft Teams, el hardware del dispositivo y los periféricos certificados de audio y vídeo. La validación comienza y continúa durante el desarrollo activo de cada versión principal de Windows 10. Se necesita tiempo adicional para validar que todos los fabricantes de dispositivos han creado imágenes actualizadas para sus dispositivos y para que Microsoft Teams certifique y pruebe esas imágenes. Durante el período de validación, la aplicación Salón de Microsoft Teams usa directivas de grupo de  [Windows Update para](/windows/deployment/update/waas-manage-updates-wufb) empresas para retrasar las actualizaciones de características de Windows 10. Una vez que se encuentran y resuelven los problemas de compatibilidad, el bloque se levanta mediante la actualización de directivas de grupo a través de una nueva versión de la aplicación en la Tienda Windows. Los dispositivos que ejecutan la aplicación Salas de Microsoft Teams se actualizan automáticamente a una versión adecuada de Windows 10 durante el reinicio de mantenimiento nocturno. Una versión msi está disponible para los clientes que deseen administrar manualmente las actualizaciones.  

> [!IMPORTANT]
> Durante el período de validación, los dispositivos salas de Microsoft Teams **no** se deben actualizar a la próxima versión de Windows 10 por ningún medio. Esto incluye reemplazar las directivas de grupo existentes o usar system center u otros servicios de administración de dispositivos de terceros. Cualquiera de estas opciones puede causar problemas para la aplicación Salón de Microsoft Teams o puede dejar los dispositivos inutilizables.  

En la tabla siguiente se muestran las versiones recomendadas y compatibles de Windows 10 que se han comprobado para admitir Salas de Microsoft Teams. Todas las fechas se muestran en formato ISO 8601: AYYY-MM-DD.

|Versión  |Fecha de disponibilidad   |Estado de soporte técnico de Salas de Microsoft Teams   |Versión de la aplicación Salas mínimas de Microsoft Teams | Compilación recomendada del sistema operativo  |
|:---  |:---       |:---                                  |:---     |:---     |
| 20H2 |2020-10-20 |En validación, <br/>Aún no se admite|&#x2014; |19042.572 |
| 2004 |2020-05-27 |Omitido, <br/> No recomendado|&#x2014; |19041.264 |
| 1909 |2019-11-12 |Compatible, <br/>Recomendado |4.5.33.0 |18363.418  |
| 1903 |2019-05-21 |Compatible  |4.2.4.0 |18362.356 |
| 1809 |2019-03-28 |No compatible, <br/>Problemas de compatibilidad conocidos &#x2780;|&#x2014; |&#x2014; |
| 1803 |2018-07-10 |No compatible                             |&#x2014;  |&#x2014; |
| 1709 |2018-01-18 |No se admite                         |&#x2014; |&#x2014; |
| 1703 |2017-07-11 |No compatible                         |&#x2014; |&#x2014; |

&#x2780; versión 1809 de Windows 10 no se recomienda debido a problemas de compatibilidad encontrados con la aplicación Salas de Microsoft Teams. Este problema específico hace que la aplicación Salas de Microsoft Teams no se inicie después del reinicio nocturno. Este problema se solucionó en la versión 1903 de Windows 10.  

&#x2781; versión 2004 de Windows 10 no se recomienda debido a problemas de compatibilidad encontrados con la aplicación Salas de Microsoft Teams. Este problema específico hace que la aplicación Salas de Microsoft Teams no se inicie después del reinicio nocturno. 

Cuando use una versión compatible de Windows 10, siempre recibirá las últimas actualizaciones de aplicaciones para la aplicación Salas de Microsoft Teams.  

## <a name="related-topics"></a>Temas relacionados

[Ayuda de Salas de Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Notas de la versión de Salas de Microsoft Teams](rooms-release-note.md)

[Plan para Salas de Microsoft Teams](rooms-plan.md)