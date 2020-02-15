---
title: 'Lync Server 2013: información general sobre el enrutamiento basado en ubicación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Location-Based Routing
ms:assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994032(v=OCS.15)
ms:contentKeyID: 51803941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7bc7320ffd8bb4d12483a882b588205d26e7e164
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051012"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-in-lync-server-2013"></a>Información general sobre el enrutamiento basado en ubicación en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

El enrutamiento basado en ubicación presenta un nuevo conjunto de reglas que modifica el enrutamiento de las llamadas RTC nacionales e internacionales para evitar la omisión de peaje. El enrutamiento basado en ubicación proporciona la flexibilidad necesaria para establecer el ámbito de estas reglas a regiones específicas, puertas de enlace específicas o a un conjunto específico de usuarios únicamente.

Los siguientes escenarios ilustran los principales tipos de restricciones que el enrutamiento basado en ubicación puede exigir:

  - Llamadas de salida: el enrutamiento basado en ubicación puede aplicar llamadas salientes a salidas de una puerta de enlace RTC que se encuentra en la misma región en la que el autor de la llamada impide el desvío de llamadas RTC, lo que impide que se produzcan llamadas de salida de una puerta de enlace RTC situada en una región distinta a la autor.

  - Llamadas de entrada: el enrutamiento basado en ubicación puede evitar llamadas RTC entrantes para llamar a los puntos de conexión de Lync si el enrutamiento de la puerta de enlace RTC la llamada entrante no se encuentra en la misma región que el usuario de Lync llamado.

  - Regiones desconocidas: el enrutamiento basado en ubicación restringe las llamadas RTC entrantes y salientes a los usuarios que se encuentran en ubicaciones sin determinar (por ejemplo, los usuarios remotos que se conectan desde Internet o que se encuentran en regiones desconocidas).

  - Regiones internacionales: el enrutamiento basado en ubicación fuerza el enrutamiento de las llamadas salientes a través de puertas de enlace RTC internacionales Si no se encuentra una puerta de enlace local a la ubicación del usuario.

<div>

## <a name="see-also"></a>Vea también


[Planeación del enrutamiento basado en ubicación en Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

