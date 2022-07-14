---
title: Informe de grupos de minutos de RTC de Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
MS.collection:
- M365-voice
description: Cómo usar el informe grupos de minutos RTC de Teams en el Centro de administración de Microsoft Teams para ver los minutos consumidos en su organización durante el mes actual.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3aafc45cebab24f5524a4d3120dd0c03083d0c6c
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2022
ms.locfileid: "66794358"
---
# <a name="microsoft-teams-pstn-minute-pools-report"></a>Informe de grupos de minutos de RTC de Microsoft Teams

El informe grupos de minutos de RTC de Teams en el Centro de administración de Microsoft Teams le ofrece información general sobre la actividad de llamadas y audioconferencias en su organización, mostrándole el número de minutos consumidos durante el mes actual. Puede ver un desglose de la actividad, incluida la licencia usada para las llamadas, el total de minutos disponibles, los minutos usados y el uso de licencias por ubicación.

## <a name="view-the-pstn-minute-pools-report"></a>Ver el informe de grupos de minutos de RTC

En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, haga clic en **Análisis & informes** > **de uso**. En la pestaña **Ver informes** , en **Informe**, seleccione Grupos de **minutos RTC y SMS(versión preliminar)** y, a continuación, haga clic en **Ejecutar informe**.

![Captura de pantalla del informe de grupos de minutos rtc de Teams en el centro de administración.](../media/teams-reports-pstn-minute-pools-with-callouts.png "Captura de pantalla del informe de grupos de minutos RTC de Teams en el Centro de administración de Microsoft Teams con llamadas numeradas")

## <a name="interpret-the-report"></a>Interpretar el informe

|Globo |Descripción  |
|--------|-------------|
|**1**   |Cada informe tiene una fecha en la que se generó. Normalmente, el informe refleja una latencia de 24 a 48 horas desde el momento de actividad. |
|**2**   |Haga clic en una funcionalidad (licencia) para ver la actividad de esa funcionalidad. |
|**3**   |El eje X es el país o la región. El eje Y es número de minutos. <br>Mueva el puntero sobre una barra del gráfico para ver la actividad de esa ubicación de uso.  |
|**4**   |Puede filtrar lo que aparece en el gráfico haciendo clic en un elemento de la leyenda. Por ejemplo, haga clic en **Sin usar**, **Usuarios nacionales**, **Sin datos** o **Internacional usados** para ver solo la información relacionada con cada uno de ellos. |
|**5**   |La tabla ofrece un desglose de los grupos de minutos por capacidad y ubicación de uso. <ul><li>**País o región** es la ubicación de uso. </li><li>**Descripción de la funcionalidad** es la descripción de la licencia que se usa para la llamada.  Las descripciones de funcionalidad que puede ver en este informe incluyen: <ul><li>Plan de llamadas nacionales e internacionales (1200 minutos nacionales)</li><li>Plan de llamadas nacionales e internacionales (3000 minutos nacionales)</li><li>Plan de llamadas nacionales e internacionales (600 minutos internacionales)</li></ul></li><br><li>**Minutos totales** es el número total de minutos disponibles para el mes.</li><li>**Minutos utilizados** es el número de minutos usados cada mes</li> <li>**Minutos disponibles** es el número de minutos restantes para el mes.</li><li>**Funcionalidad** es la licencia que se usa para la llamada. Las licencias que puede ver incluyen:<ul><li>**MCOPSTN1** - Plan de llamadas nacionales (planes de 3000 min EE. UU. / 1200 min de la UE)</li><li>**MCOPSTN2** - Plan de llamadas internacionales</li><li>**MCOPSTN5** - Plan de llamadas nacionales (plan de llamadas de 120 minutos)</li><li>**MCOPSTN6** - Plan de llamadas nacionales (plan de llamadas de 240 minutos)</li><li>**MCOMEETADD** : Audioconferencia</li></ul></li> </ul> Para ver la información que quiera en la tabla, asegúrese de agregar las columnas a la tabla.|
|**6**   |Seleccione **Editar columnas** para agregar o quitar columnas en la tabla.|
|**7**   |Seleccione **Pantalla completa** para ver el informe en modo de pantalla completa.|

## <a name="related-topics"></a>Temas relacionados

- [Análisis e informes de Teams](teams-reporting-reference.md)
