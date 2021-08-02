---
title: Salas de Microsoft Teams versión de la aplicación
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
description: Obtenga información sobre el soporte para el ciclo de Salas de Microsoft Teams, incluida la estructura de soporte dinámico y sus fases.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c34f448eeaadbf946ab708378caa835a94836ccc
ms.sourcegitcommit: ad215c120d7e550a7aebf2e1bb620c69039e5d8d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2021
ms.locfileid: "53679735"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Salas de Microsoft Teams versión de la aplicación
 
La Salas de Microsoft Teams aplicación obtiene actualizaciones varias veces al año. Cada actualización es compatible durante doce (12) meses desde su fecha de publicación de disponibilidad general (GA). Se proporciona soporte técnico durante los doce (12) meses completos. Sin embargo, la estructura de soporte es dinámica, con dos fases distintas que dependen de la disponibilidad de la versión más reciente:

- **Fase De mantenimiento** y actualizaciones críticas: cuando ejecuta la última versión de la aplicación Salas de Microsoft Teams, recibe actualizaciones periódicas que contienen actualizaciones de seguridad *y* mantenimiento.

- Solo fase actualizaciones de **seguridad:** cuando se publica una nueva versión de la aplicación Salas de Microsoft Teams, las versiones anteriores de la aplicación tienen un nivel de soporte técnico reducido con actualizaciones de seguridad solo para el resto del ciclo de vida de doce (12) meses. 

> [!NOTE]
> La versión más reciente siempre está en la fase mantenimiento y actualizaciones críticas. Cuando se produce un defecto de código que justifica una actualización crítica, también debe tener instalada la versión más reciente para recibir una corrección. Todas las demás versiones compatibles solo podrán recibir actualizaciones de seguridad.

Todo el soporte técnico finaliza después de que el ciclo de vida de doce (12) meses de una versión haya expirado o si se han publicado más de dos actualizaciones desde entonces. A continuación, los clientes deben actualizar a una versión compatible.

Todas las versiones se muestran en las [Salas de Microsoft Teams de la versión.](rooms-release-note.md)

## <a name="windows-10-release-support"></a>Windows 10 soporte técnico para la versión de lanzamiento

Salas de Microsoft Teams requiere las Windows 10 IoT Enterprise o Windows 10 Enterprise SKU en Semi-Annual de mantenimiento del canal. Estas otras Windows 10 ediciones anteriores no son compatibles:

- Windows 10 Enterprise Ediciones de la Rama de mantenimiento a largo plazo (LTSB) /Canal de mantenimiento a largo plazo (LTSC)
- Windows 10 Internet de las cosas (IoT) Enterprise ediciones LTSB /LTSC
- cualquier otra edición de Windows como Windows 10 Pro o Edición principal

Las Windows 10 nuevas características no se ofrecen en Salas de Microsoft Teams dispositivos inmediatamente. Un retraso intencionado de hasta seis meses después de la fecha de disponibilidad general publicada en la [Windows 10 información de la versión.](/windows/release-information/) El tiempo de retraso se usa para validar la compatibilidad Windows 10 versión de la aplicación Salas de Microsoft Teams, el hardware del dispositivo y los periféricos certificados de audio y vídeo. La validación comienza y continúa durante el desarrollo activo de cada versión principal de Windows 10. Se necesita tiempo adicional para validar que todos los fabricantes de dispositivos han creado imágenes actualizadas para sus dispositivos y para Microsoft Teams certificar y probar esas imágenes. Durante el período de validación, la aplicación Microsoft Teams Room usa Windows [de](/windows/deployment/update/waas-manage-updates-wufb) grupo Actualizar para empresas para retrasar las Windows 10 características. Una vez que se encuentran y se resuelven los problemas de compatibilidad, el bloque se levanta mediante la actualización de directivas de grupo a través de una nueva versión de la aplicación en Windows store. Los dispositivos que ejecutan Salas de Microsoft Teams aplicación se actualizan automáticamente a una versión Windows 10 durante el reinicio de mantenimiento nocturno. Una versión msi está disponible para los clientes que deseen administrar manualmente las actualizaciones.  

> [!IMPORTANT]
> Durante el período de validación, Salas de Microsoft Teams dispositivos no **deben** actualizarse a la siguiente versión de Windows 10 por ningún medio. Esto incluye reemplazar las directivas de grupo existentes o usar System Center servicios de administración de dispositivos de terceros. Cualquiera de estas opciones puede causar problemas en la aplicación Microsoft Teams Room o puede dejar los dispositivos inutilizables.  

En la tabla siguiente se muestran las versiones recomendadas y compatibles Windows 10 que se comprueban para admitir Salas de Microsoft Teams. Todas las fechas se muestran en formato ISO 8601: AYYY-MM-DD.

|Versión  |Fecha de disponibilidad   |Salas de Microsoft Teams de soporte técnico   |Salas de Microsoft Teams Versión mínima de la aplicación | Compilación recomendada del sistema operativo  |
|:---  |:---       |:---                                  |:---     |:---     |
| 20H2 |2020-10-20 |Compatible, <br/>Recomendado|4.8.31.0 |19042.631 |
| 2004 |2020-05-27 |Omitido, <br/> No recomendado &#x2780;|&#x2014; |&#x2014; |
| 1909 |2019-11-12 |Compatible |4.5.33.0 |18363.418  |
| 1903 |2019-05-21 |No compatible  |&#x2014; |&#x2014; |
| 1809 |2019-03-28 |No compatible, <br/>Problemas de compatibilidad conocidos &#x2781;|&#x2014; |&#x2014; |
| 1803 |2018-07-10 |No compatible                             |&#x2014;  |&#x2014; |
| 1709 |2018-01-18 |No se admite                         |&#x2014; |&#x2014; |
| 1703 |2017-07-11 |No compatible                         |&#x2014; |&#x2014; |

&#x2780; Windows 10 versión 2004 no se recomienda debido a problemas de compatibilidad encontrados con la Salas de Microsoft Teams aplicación. Este problema específico hace que Salas de Microsoft Teams aplicación no se inicie después del reinicio nocturno. 

&#x2781; Windows 10 versión 1809 no se recomienda debido a problemas de compatibilidad encontrados con la Salas de Microsoft Teams aplicación. Este problema específico hace que Salas de Microsoft Teams aplicación no se inicie después del reinicio nocturno. Este problema se solucionó en Windows 10 versión 1903.  

Cuando use una versión compatible de Windows 10, siempre recibirá las últimas actualizaciones de la aplicación para Salas de Microsoft Teams aplicación.  

> [!IMPORTANT]
> La Windows 10 20H2 aún no está disponible para los siguientes dispositivos Salas de Teams debido a problemas de compatibilidad. Los OEM de dispositivos están trabajando para resolver estos problemas lo antes posible. Windows 10 20H2 no se ofrecerán en estos dispositivos. No actualice manualmente estos dispositivos a 20H2 anulando los objetos de directiva de grupo (GPO) o la administración de dispositivos móviles (MDM). 
> 
> Los dispositivos con problemas de compatibilidad son:
> 
> - Crestron UC-Engine (la versión/fecha del BIOS contiene "KYSKLI", que indica un BIOS de Skull Canyon) 

## <a name="related-topics"></a>Temas relacionados

[Ayuda de Salas de Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Salas de Microsoft Teams notas de la versión](rooms-release-note.md)

[Plan para Salas de Microsoft Teams](rooms-plan.md)
