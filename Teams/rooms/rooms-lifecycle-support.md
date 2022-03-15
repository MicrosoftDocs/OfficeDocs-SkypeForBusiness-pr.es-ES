---
title: Salas de Microsoft Teams versión de la aplicación
ms.author: czawideh
author: cazawideh
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Obtenga información sobre el soporte del ciclo de Salas de Microsoft Teams, incluida la estructura de soporte dinámico y sus fases.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b2f1ad2ce3be71667588288b82ca93646ff776a5
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503677"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Salas de Microsoft Teams versión de la aplicación
 
La Salas de Microsoft Teams obtiene actualizaciones a través de la Windows tienda. Microsoft Teams aplicación Room usa un ciclo de vida de producto permanente y solo la versión actual y la siguiente más reciente de la aplicación son compatibles en un momento determinado. La Microsoft Teams room incluye una versión específica de la Teams de escritorio que se modifica para el uso del salón. La Teams aplicación de escritorio se actualiza cada dos semanas. Obtenga más información sobre el [proceso Teams actualización.](../teams-client-update.md) Esto significa que Salas de Teams la versión actual de la aplicación 1 puede tener hasta seis actualizaciones de aplicaciones de escritorio de Teams detrás, por lo que se recomienda mantener la aplicación de sala de Teams actualizada Teams la última versión de la aplicación Salas de Teams en todo momento. 

La estructura de soporte para Salas de Teams es dinámica y depende de la disponibilidad de la última versión. Cuando se produce un defecto de código en una versión de la aplicación que no es la más reciente, debe instalar la versión más reciente para recibir una corrección.

Todas las versiones se muestran en las [Salas de Microsoft Teams de la versión.](rooms-release-note.md)

> [!IMPORTANT]
> Al instalar un nuevo dispositivo que venía con una versión anterior de la aplicación de salón de Teams, se recomienda actualizar manualmente la [](manual-update.md) aplicación después de configurar la cuenta, antes de descargar cualquier Windows actualizaciones. Esto garantiza la versión correcta del sistema operativo y Windows actualizaciones se instalan en el dispositivo.  

## <a name="windows-10-release-support"></a>Windows 10 de lanzamiento

Salas de Microsoft Teams requiere las Windows 10 IoT Enterprise o Windows 10 Enterprise SKU en Semi-Annual de mantenimiento del canal. Estas otras Windows 10 ediciones anteriores no son compatibles:

- Windows 10 Enterprise ediciones de la rama de mantenimiento a largo plazo (LTSB) /Canal de mantenimiento a largo plazo (LTSC)
- Windows 10 internet de las cosas (IoT) Enterprise ediciones LTSB /LTSC
- cualquier otra edición de Windows como Windows 10 Pro o Edición de inicio

Las Windows 10 nuevas características no se ofrecen en Salas de Microsoft Teams dispositivos inmediatamente. Hay un retraso intencionado de hasta seis meses o más después de la fecha de disponibilidad general publicada en la Windows 10 [información de la versión](/windows/release-information/). Esta vez se usa para validar la Windows 10 versión para la aplicación Salas de Microsoft Teams, el hardware del dispositivo y los periféricos certificados de audio y vídeo. La validación comienza y continúa durante el desarrollo activo de cada versión principal de Windows 10. Se necesita tiempo adicional para validar que todos los fabricantes de dispositivos han creado imágenes actualizadas para sus dispositivos y para que Microsoft certifique y pruebe esas imágenes. Durante el período de validación, la aplicación Microsoft Teams Room usa [Windows de](/windows/deployment/update/waas-manage-updates-wufb) grupo Actualizar para empresas para retrasar Windows 10 actualizaciones de características. Una vez que se encuentran y resuelven los problemas de compatibilidad, el bloque se levanta mediante la actualización de directivas de grupo a través de una nueva versión de la aplicación en Windows store. Los dispositivos que ejecutan Salas de Microsoft Teams aplicación se actualizan automáticamente a una versión Windows 10 durante el reinicio de mantenimiento nocturno. Una versión msi está disponible para los clientes que necesitan administrar manualmente las actualizaciones.  

> [!IMPORTANT]
> Durante el período de validación, Salas de Microsoft Teams dispositivos no **deben** actualizarse a la próxima versión de Windows 10 por ningún medio. Esto incluye reemplazar las directivas de grupo existentes o usar System Center servicios de administración de dispositivos de terceros. Cualquiera de estos problemas puede causar problemas en la aplicación Microsoft Teams Room o puede dejar los dispositivos inutilizables.  

En la tabla siguiente se muestran las versiones recomendadas y compatibles Windows 10 que se comprueban para admitir Salas de Microsoft Teams. Todas las fechas se muestran en formato ISO 8601: AYYY-MM-DD.

|Versión  |Fecha de disponibilidad   |Salas de Microsoft Teams de soporte técnico   |Salas de Microsoft Teams versión mínima de la aplicación | Compilación recomendada del sistema operativo  |
|:---  |:---       |:---                                  |:---     |:---     |
| 21H1 |2021-05-18 |No compatible                         |&#x2014; |&#x2014; |
| 20H2 |2020-10-20 |Compatible, <br/>Recomendado|4.10.10.0 |19042.631 |
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


## <a name="related-topics"></a>Temas relacionados

[Ayuda de Salas de Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Salas de Microsoft Teams notas de la versión](rooms-release-note.md)

[Plan para Salas de Microsoft Teams](rooms-plan.md)
