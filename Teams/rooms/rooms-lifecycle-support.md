---
title: compatibilidad con la versión de la aplicación Salas de Microsoft Teams
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
description: Obtén información sobre el soporte técnico del ciclo de vida para Salas de Microsoft Teams, incluida la estructura dinámica de soporte técnico y sus fases.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c0353dc1a52dbc16d42d7c7e2f974675bb5098aa
ms.sourcegitcommit: cd4464fe9bf0f38ed4c3ca058a51bcd29578eef9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2022
ms.locfileid: "65316516"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>compatibilidad con la versión de la aplicación Salas de Microsoft Teams
 
La aplicación Salas de Microsoft Teams obtiene actualizaciones a través de la tienda Windows. Microsoft Teams aplicación Room usa un ciclo de vida de producto perenne y solo se admite la versión actual y la siguiente versión más reciente de la aplicación en un momento dado. La aplicación sala de Microsoft Teams agrupa una versión específica de la aplicación de escritorio de Teams que se ha modificado para su uso en el salón. La aplicación de escritorio Teams se actualiza cada dos semanas. Más información sobre el [proceso de actualización de Teams](../teams-client-update.md). Esto significa que Salas de Teams versión actual-1 de la aplicación puede tener hasta seis Teams actualizaciones de la aplicación de escritorio, por lo que se recomienda mantener la aplicación Teams Room actualizada a la última versión de la aplicación Salas de Teams en todo momento. 

La estructura de soporte para Salas de Teams es dinámica y depende de la disponibilidad de la última versión. Cuando se produce un defecto de código en una versión de la aplicación que no es la más reciente, debe instalar la versión más reciente para recibir una corrección.

Todas las versiones se muestran en la [Salas de Microsoft Teams notas de la versión](rooms-release-note.md).

> [!IMPORTANT]
> Al instalar un nuevo dispositivo que venía con una versión anterior de la aplicación de sala de Teams, se recomienda [actualizar manualmente la aplicación](manual-update.md) después de configurar la cuenta, antes de descargar las actualizaciones de Windows. Esto garantiza que la versión correcta del sistema operativo y las actualizaciones de Windows estén instaladas en el dispositivo.  

## <a name="windows-10-release-support"></a>Windows 10 compatibilidad con versiones

Salas de Microsoft Teams requiere la Windows 10 IoT Enterprise o Windows 10 Enterprise SKU en las opciones de servicio del Canal Semi-Annual. Estas otras ediciones de Windows 10 no son compatibles:

- Windows 10 Enterprise ediciones de la Rama de mantenimiento a largo plazo (LTSB) o del Canal de mantenimiento a largo plazo (LTSC)
- Windows 10 ediciones de Internet de las cosas (IoT) Enterprise LTSB/LTSC
- cualquier otra edición de Windows, como Windows 10 Pro o Home

Las nuevas actualizaciones de características de Windows 10 no se ofrecen inmediatamente en Salas de Microsoft Teams dispositivos. Hay un retraso intencionado de hasta seis meses o más después de la fecha de disponibilidad general publicada en la página [Windows 10 información de lanzamiento](/windows/release-information/). Esta vez se usa para validar la compatibilidad de versiones de Windows 10 para la aplicación de Salas de Microsoft Teams, el hardware del dispositivo y los periféricos de vídeo de audio certificados. La validación comienza y continúa durante el desarrollo activo de cada versión principal de Windows 10. Se necesita más tiempo para validar que todos los fabricantes de dispositivos han creado imágenes actualizadas para sus dispositivos y para que Microsoft certifique y pruebe esas imágenes. Durante el período de validación, la aplicación Sala de Microsoft Teams usa [Windows Update directivas de grupo de Empresarial para](/windows/deployment/update/waas-manage-updates-wufb) retrasar Windows 10 actualizaciones de características. Una vez encontrados y resueltos los problemas de compatibilidad, el bloque se levanta mediante la actualización de directivas de grupo mediante una nueva versión de la aplicación en Windows store. Los dispositivos que ejecutan la aplicación Salas de Microsoft Teams se actualizan automáticamente a una versión de Windows 10 adecuada durante el reinicio de mantenimiento nocturno. Una versión msi está disponible para los clientes que necesitan administrar manualmente las actualizaciones.  

> [!IMPORTANT]
> Durante el período de validación, **Salas de Microsoft Teams dispositivos no** deben actualizarse a la siguiente versión de Windows 10 por ningún medio. Esto incluye la invalidación de las directivas de grupo en su lugar o el uso de System Center u otros servicios de administración de dispositivos de terceros. Cualquiera de estos problemas puede causar problemas para la aplicación Microsoft Teams Room o puede dejar dispositivos inutilizables.  

En la tabla siguiente se muestran las versiones recomendadas y compatibles de Windows 10 comprobadas para admitir Salas de Microsoft Teams. Todas las fechas se muestran en formato ISO 8601: AAAA-MM-DD.

| Versión | Fecha de disponibilidad | Salas de Microsoft Teams estado de soporte técnico                    | Salas de Microsoft Teams versión mínima de la aplicación | Compilación de SO recomendada |
|:--------|:------------------|:--------------------------------------------------------|:--------------------------------------------------|:---------------------|
| 21H2    | 2021-11-16        | Apoyado<br>Recomendado                               | 4.12.126.0                                        | 19044.1288           |
| 21H1    | 2021-05-18        | No compatible                                           | &#x2014;                                          | &#x2014;             |
| 20H2    | 2020-10-20        | Compatible                                               | 4.10.10.0                                         | 19042.631            |
| 2004    | 2020-05-27        | Saltamos <br/> No recomendado &#x2780;                 | &#x2014;                                          | &#x2014;             |
| 1909    | 2019-11-12        | Compatible                                               | 4.5.33.0                                          | 18363.418            |
| 1903    | 2019-05-21        | No compatible                                           | &#x2014;                                          | &#x2014;             |
| 1809    | 2019-03-28        | No compatible, <br/>Problemas de compatibilidad conocidos &#x2781; | &#x2014;                                          | &#x2014;             |
| 1803    | 2018-07-10        | No compatible                                           | &#x2014;                                          | &#x2014;             |
| 1709    | 2018-01-18        | No se admite                                           | &#x2014;                                          | &#x2014;             |
| 1703    | 2017-07-11        | No compatible                                           | &#x2014;                                          | &#x2014;             |

&#x2780; Windows 10 versión 2004 no se recomienda debido a problemas de compatibilidad encontrados con la aplicación Salas de Microsoft Teams. Este problema específico hace que la aplicación Salas de Microsoft Teams no se inicie después del reinicio nocturno. 

&#x2781; Windows 10 versión 1809 no se recomienda debido a los problemas de compatibilidad encontrados con la aplicación Salas de Microsoft Teams. Este problema específico hace que la aplicación Salas de Microsoft Teams no se inicie después del reinicio nocturno. Este problema se solucionó en Windows 10 versión 1903.  

Cuando uses una versión compatible de Windows 10, siempre obtendrás las últimas actualizaciones de aplicaciones para la aplicación Salas de Microsoft Teams.  


## <a name="related-topics"></a>Temas relacionados

[Ayuda de Salas de Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Salas de Microsoft Teams notas de la versión](rooms-release-note.md)

[Plan para Salas de Microsoft Teams](rooms-plan.md)
