---
title: Informe de grupos de minutos RTC de Microsoft Teams
author: LanaChin
ms.author: v-lanac
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
description: Aprenda a usar el informe de grupos de minutos RTC de Teams en el centro de administración de Microsoft Teams para ver el número de minutos consumidos durante el mes actual de su organización.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0fa9b8f4a676c1e937fed02eabc0e7cd4acd5325
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827328"
---
# <a name="microsoft-teams-pstn-minute-pools-report"></a>Informe de grupos de minutos RTC de Microsoft Teams

El informe grupos de grupos de minutos RTC en el centro de administración de Microsoft Teams le ofrece información general sobre la actividad de llamadas y videollamadas de su organización mostrándole la cantidad de minutos consumidos durante el mes en curso. Puede ver un desglose de actividad como la licencia que se usa para las llamadas, los minutos totales disponibles, los minutos usados y el uso de licencias por ubicación.

## <a name="view-the-report"></a>Ver el informe

En el centro de navegación izquierdo del centro de administración de Microsoft Teams, haga clic en > **informes de uso**de **informes &**. En la pestaña **ver informes** , en **Informe**, seleccione **grupos de minutos RTC**y, a continuación, haga clic en **Ejecutar Informe**.

![Captura de pantalla del informe de grupos de minutos RTC de Teams en el centro de administración](../media/teams-reports-pstn-minute-pools-with-callouts.png "Captura de pantalla del informe de grupos de minutos RTC de Teams en el centro de administración de Microsoft Teams con llamadas numeradas")

## <a name="interpret-the-report"></a>Interpretar el informe

|Globo |Descripción  |
|--------|-------------|
|**1**   |Cada informe tiene una fecha en la que se generó. Normalmente, el informe refleja una latencia de 24 a 48 horas desde el momento de actividad. |
|**2**   |Haga clic en una capacidad (licencia) para ver la actividad de esa capacidad. |
|**3**   |El eje X es país o región. El eje Y es el número de minutos. <br>Desplace el puntero sobre una barra del gráfico para ver la actividad de esa ubicación de uso.  |
|**4**   |Puede filtrar lo que aparece en el gráfico haciendo clic en un elemento de la leyenda. Por ejemplo, haga clic en no **usado**, **usuarios nacionales**, **sin datos**o en **uso internacional** para ver solo la información relacionada con cada uno de ellos. |
|**5**   |La tabla ofrece un desglose de los grupos de minutos por capacidad y ubicación de uso. <ul><li>**País o región** es la ubicación de uso. </li><li>**Descripción** de la funcionalidad es la descripción de la licencia que se usa para la llamada.  Las descripciones de las funciones que puede ver en este informe son: <ul><li>Plan de llamadas nacionales e internacionales (1200 minutos nacionales)</li><li>Plan de llamadas nacionales e internacionales (3000 minutos nacionales)</li><li>Plan de llamadas nacionales e internacionales (600 minutos internacionales)</li></ul></li><br><li>**Minutos totales** es el número total de minutos disponibles para el mes.</li><li>**Minutos usados** es el número de minutos que se usan cada mes</li> <li>Los **minutos disponibles** son la cantidad de minutos que quedan para el mes.</li><li>**Capacidad** es la licencia que se usa para la llamada. Entre las licencias que puede ver se incluyen las siguientes:<ul><li>**MCOPSTNPP** -créditos de comunicaciones</li><li>Plan de llamadas **MCOPSTN1** -nacionales (3000 min Estados unidos/1200 mín. planes de la UE)</li><li>Plan de llamadas **MCOPSTN2** -International</li><li>Plan de llamadas **MCOPSTN5** -nacionales (120)</li><li>Plan de llamadas **MCOPSTN6** -nacionales (240)</li><li>**MCOMEETADD** : audioconferencia</li><li>Videoconferencias por minuto de **MCOMEETACPEA**</li></ul></li> </ul> Para ver la información que quiera en la tabla, asegúrese de agregar las columnas a la tabla.|
|**6**   |Seleccione **Editar columnas** para agregar o quitar columnas en la tabla.|
|**7**   |Seleccione **pantalla completa** para ver el informe en modo de pantalla completa.|

## <a name="related-topics"></a>Temas relacionados

- [Análisis e informes de Teams](teams-reporting-reference.md)