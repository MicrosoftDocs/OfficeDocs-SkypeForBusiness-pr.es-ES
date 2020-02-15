---
title: 'Lync Server 2013: informes de QoE'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoE reports
ms:assetid: 49c827af-b8dd-4c6e-b0dc-b4bc6d60e9a3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720913(v=OCS.15)
ms:contentKeyID: 63969601
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 958c67b1b10b25e44805d2582ffe2e9fab575568
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045792"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="qoe-reports-in-lync-server-2013"></a>Informes de QoE en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-05-01_

<div>

## <a name="qoe-summarytrend-reports"></a>Informe de tendencias/Resumen de QoE

Los informes de Resumen/tendencias de QoE son útiles para encontrar los tiempos de uso máximo del día y para examinar la calidad de los medios en esas horas para asegurarse de que los recursos de red de la organización son suficientes. La organización también puede usar los numerosos filtros disponibles en el informe para aislar los números de rendimiento de determinadas ubicaciones, tipos de dispositivos y clientes, y servidores.

Los informes de tendencias y de Resumen de QoE constan de:

  - Informe de tendencias/Resumen de UC a UC

  - Informe de tendencias o Resumen de RTC

  - Informe de tendencias/Resumen de conferencia

</div>

<div>

## <a name="qoe-performance-reports"></a>Informes de rendimiento de QoE

Los informes de rendimiento de QoE proporcionan información detallada sobre los tres informes que se centran en el rendimiento de los servidores de mediación, los servidores de conferencia A/V y las ubicaciones de los extremos.

</div>

<div>

## <a name="mediation-server-performance-report"></a>Informe de rendimiento del servidor de mediación

El informe de rendimiento del servidor de mediación enumera las métricas logradas por una o más mediación durante el período de tiempo especificado. Las métricas de la sección del servidor de comunicaciones unificadas (UC) y la sección del servidor de mediación a la puerta de enlace de cada llamada se notifican por separado. Use este informe para comparar el volumen y el rendimiento de los diversos servidores de mediación de su organización.

Por cada servidor de mediación (y por cada pierna de llamada), el informe muestra lo siguiente:

  - Número de llamadas

  - Pérdida de paquetes

  - Tiempo de ida y vuelta

  - JIT

  - Puntuación de opinión media a la conversación (MOS)

  - Envío de MOS

  - Escuchar MOS

  - MOS de red

  - Degradación de MOS de red

  - Devolución de eco

  - Nivel de señal

</div>

<div>

## <a name="av-conferencing-server-performance-report"></a>Informe de rendimiento del servidor de conferencia A/V

El informe de rendimiento del servidor de conferencia A/V proporciona listas de métricas realizadas por uno o varios servidores de conferencia A/V durante el período de tiempo especificado. Este informe se puede usar para comparar el volumen y el rendimiento de los diversos servidores de conferencia A/V de la organización. La organización también puede aislar el informe para mostrar solo la experiencia de determinados tipos de clientes, como clientes de Lync o RTC.

Para cada servidor de conferencia A/V, el informe muestra lo siguiente:

  - Número de conferencias

  - Pérdida de paquetes

  - Tiempo de ida y vuelta

  - JIT

  - Puntuación de opinión media a la conversación (MOS)

  - Envío de MOS

  - Escuchar MOS

  - MOS de red

  - Degradación de MOS de red

  - Devolución de eco

  - Nivel de señal

</div>

<div>

## <a name="location-based-performance-report"></a>Informe de rendimiento basado en ubicación

El informe de rendimiento basado en ubicación proporciona una lista de ubicaciones de red y para cada ubicación muestra el número de llamadas en cada rango de calidad predeterminado. El objetivo de este informe es proporcionar información sobre la calidad de los medios de la mayor parte de las llamadas telefónicas de la organización en varias ubicaciones, de modo que pueda identificar las ubicaciones con un rendimiento deficiente y ver los diferentes grados de calidad de los medios en la organización. distintas ubicaciones.

Cuando se muestra el informe, aparecen diferentes tablas de métricas: una tabla para cada métrica a la que la organización decide informar. Puede elegir entre las siguientes métricas para este informe:

  - Puntuación de opinión media a la conversación (MOS)

  - MOS de red

  - Degradación de MOS de red

  - Envío de MOS

  - Escuchar MOS

  - Pérdida de paquetes

  - JIT

  - Latencia

</div>

</div>

<span> </span>

</div>

</div>

</div>

