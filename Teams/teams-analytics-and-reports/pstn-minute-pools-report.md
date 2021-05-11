---
title: Microsoft Teams Informe de grupos de minutos RTC
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
MS.collection:
- M365-voice
description: Cómo usar el informe Teams grupos de minutos RTC en el centro de administración de Microsoft Teams para ver los minutos consumidos en su organización durante el mes actual.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4d28e33ae820407ffe8c9561cae8c79863532417
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2021
ms.locfileid: "52305994"
---
# <a name="microsoft-teams-pstn-minute-pools-report"></a>Microsoft Teams Informe de grupos de minutos RTC

El informe Teams grupos de minutos RTC en el Centro de administración de Microsoft Teams le proporciona información general sobre la actividad de las audioconferencias y las llamadas en su organización mostrando el número de minutos consumidos durante el mes actual. Puede ver un desglose de la actividad, incluida la licencia usada para llamadas, el total de minutos disponibles, los minutos usados y el uso de licencias por ubicación.

## <a name="view-the-pstn-minute-pools-report"></a>Ver el informe de grupos de minutos RTC

En el panel de navegación izquierdo del centro Microsoft Teams administración, haga clic **en Análisis & informes de**  >  **uso.** En la pestaña **Ver informes,** **en** Informe, seleccione Grupos de minutos **RTC** y, a continuación, haga clic en **Ejecutar informe.**

![Captura de pantalla del Teams de minutos RTC en el centro de administración](../media/teams-reports-pstn-minute-pools-with-callouts.png "Captura de pantalla del Teams de minutos RTC en el centro de Microsoft Teams con llamadas numeradas")

## <a name="interpret-the-report"></a>Interpretar el informe

|Globo |Descripción  |
|--------|-------------|
|**1**   |Cada informe tiene una fecha para cuándo se generó. Normalmente, el informe refleja una latencia de 24 a 48 horas desde el momento de actividad. |
|**2**   |Haga clic en una capacidad (licencia) para ver la actividad de esa capacidad. |
|**3**   |El eje X es país o región. El eje Y es número de minutos. <br>Mantenga el puntero sobre una barra del gráfico para ver la actividad de esa ubicación de uso.  |
|**4**   |Puede filtrar lo que aparece en el gráfico haciendo clic en un elemento de la leyenda. Por ejemplo, haga clic **en Sin** usar  , **Usuarios nacionales**, **Sin** datos o Internacional usado para ver solo la información relacionada con cada uno de ellos. |
|**5**   |La tabla le proporciona un desglose de los grupos de minutos por capacidad y ubicación de uso. <ul><li>**País o región es** la ubicación de uso. </li><li>**Descripción de la capacidad** es la descripción de la licencia usada para la llamada.  Las descripciones de funcionalidad que puede ver en este informe incluyen: <ul><li>Plan de llamadas nacionales e internacionales (1.200 minutos nacionales)</li><li>Plan de llamadas nacionales e internacionales (3000 minutos nacionales)</li><li>Plan de llamadas nacionales e internacionales (600 minutos internacionales)</li></ul></li><br><li>**Minutos totales** es el número total de minutos disponibles para el mes.</li><li>**Minutos usados** es el número de minutos usados cada mes</li> <li>**Minutos disponibles** es el número de minutos restantes para el mes.</li><li>**La funcionalidad** es la licencia que se usa para la llamada. Las licencias que puede ver incluyen:<ul><li>**MCOPSTN1** - Plan de llamadas nacionales (3000 min ee. UU. / 1200 min planes de la UE)</li><li>**MCOPSTN2** - Plan de llamadas internacionales</li><li>**MCOPSTN5** - Plan de llamadas nacionales (plan de llamadas de 120 minutos)</li><li>**MCOPSTN6** - Plan de llamadas nacionales (plan de llamadas de 240 minutos)</li><li>**MCOMEETADD-** Audioconferencia</li></ul></li> </ul> Para ver la información que quiera en la tabla, asegúrese de agregar las columnas a la tabla.|
|**6**   |Seleccione **Editar columnas** para agregar o quitar columnas en la tabla.|
|**7**   |Seleccione **Pantalla completa** para ver el informe en modo de pantalla completa.|

## <a name="related-topics"></a>Temas relacionados

- [Análisis e informes de Teams](teams-reporting-reference.md)
