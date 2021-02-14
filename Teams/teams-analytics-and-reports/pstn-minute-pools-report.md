---
title: Informe de grupos de minutos RTC de Microsoft Teams
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
description: Cómo usar el informe de grupos de minutos RTC de Teams en el centro de administración de Microsoft Teams para ver los minutos consumidos en la organización durante el mes actual.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8df0c1201f963a1c00742532f80089b523ca79aa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809350"
---
# <a name="microsoft-teams-pstn-minute-pools-report"></a>Informe de grupos de minutos RTC de Microsoft Teams

El informe de grupos de minutos RTC de Teams en el centro de administración de Microsoft Teams proporciona información general sobre la actividad de llamadas y audioconferencias de su organización al mostrarle el número de minutos consumidos durante el mes actual. Puede ver un desglose de la actividad, incluida la licencia usada para las llamadas, el total de minutos disponibles, los minutos usados y el uso de la licencia por ubicación.

## <a name="view-the-pstn-minute-pools-report"></a>Ver el informe de grupos de minutos RTC

En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, haga clic en **& informes de**  >  **uso.** En la **pestaña Ver informes,** **en** Informe, seleccione grupos de minutos RTC **y,** a continuación, haga clic en **Ejecutar informe.**

![Captura de pantalla del informe de grupos de minutos rtc de Teams en el centro de administración](../media/teams-reports-pstn-minute-pools-with-callouts.png "Captura de pantalla del informe de grupos de minutos RTC de Teams en el Centro de administración de Microsoft Teams con llamadas numeradas")

## <a name="interpret-the-report"></a>Interpretar el informe

|Globo |Descripción  |
|--------|-------------|
|**1**   |Cada informe tiene la fecha del momento en que se generó. Normalmente, el informe refleja una latencia de 24 a 48 horas desde el momento de actividad. |
|**2**   |Haga clic en una funcionalidad (licencia) para ver la actividad de esa capacidad. |
|**3**   |El eje X es el país o la región. El eje Y es número de minutos. <br>Mueva el puntero sobre una barra del gráfico para ver la actividad de esa ubicación de uso.  |
|**4**   |Puede filtrar lo que aparece en el gráfico haciendo clic en un elemento de la leyenda. Por ejemplo, haga clic en Usuarios no  **usados,** **Usuarios** nacionales, **Sin** datos o Internacional utilizado para ver solo la información relacionada con cada uno de ellos. |
|**5**   |La tabla proporciona un desglose de los grupos de minutos por capacidad y ubicación de uso. <ul><li>**País o región es** la ubicación de uso. </li><li>**La descripción de la** funcionalidad es la descripción de la licencia usada para la llamada.  Entre las descripciones de funcionalidad que puede ver en este informe se incluyen las siguientes: <ul><li>Plan de llamadas nacionales e internacionales (1200 minutos de llamadas nacionales)</li><li>Plan de llamadas nacionales e internacionales (3000 minutos de llamadas nacionales)</li><li>Plan de llamadas nacionales e internacionales (600 minutos internacionales)</li></ul></li><br><li>**El número** total de minutos es el número total de minutos disponibles para el mes.</li><li>**Minutos utilizados** es el número de minutos utilizados cada mes</li> <li>**Minutos disponibles** es el número de minutos restantes para el mes.</li><li>**La funcionalidad** es la licencia usada para la llamada. Las licencias que puede ver incluyen:<ul><li>**MCOPSTNPP-** Créditos de comunicaciones</li><li>**MCOPSTN1** - Plan de llamadas nacionales (3000 min para EE. UU. /1200 min en planes de la UE)</li><li>**MCOPSTN2** - Plan de llamadas internacionales</li><li>**MCOPSTN5** - Plan de llamadas nacionales (plan de llamadas de 120 min)</li><li>**MCOPSTN6** - Plan de llamadas nacionales (plan de llamadas de 240 minutos)</li><li>**MCOMEETADD** - Audioconferencia</li><li>**MCOMEETACPEA** - Audioconferencia de pago por minuto</li></ul></li> </ul> Para ver la información que quiera en la tabla, asegúrese de agregar las columnas a la tabla.|
|**6**   |Seleccione **Editar columnas** para agregar o quitar columnas en la tabla.|
|**7**   |Seleccione **Pantalla completa** para ver el informe en el modo de pantalla completa.|

## <a name="related-topics"></a>Temas relacionados

- [Análisis e informes de Teams](teams-reporting-reference.md)