---
title: 'Lync Server 2013: información general del Director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Director
ms:assetid: cf9919b3-e16b-47c5-be1d-2c4bc64f44ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398879(v=OCS.15)
ms:contentKeyID: 48185393
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb187711174785833716b2d14ffe7979cedcbc96
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520827"
---
# <a name="overview-of-the-director-in-lync-server-2013"></a>Información general sobre el Director en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-08_

Un director es un servidor que ejecuta Lync Server 2013 y que autentica solicitudes de usuario, pero no aloja ninguna cuenta de usuario. Opcionalmente, puede implementar un director en los dos escenarios siguientes:

  - Si habilita el acceso de usuarios externos mediante la implementación de servidores perimetrales, también debe implementar un director. En este escenario, el director autentica a los usuarios externos y, a continuación, pasa su tráfico a los servidores internos. Cuando se usa un director para autenticar usuarios externos, libera los servidores del grupo de servidores front-end de la sobrecarga de realizar la autenticación de estos usuarios. También ayuda a aislar los grupos de servidores front-end internos del tráfico malintencionado, como los ataques por denegación de servicio. Si la red está saturada con tráfico externo no válido, este tráfico llega al director.

  - Si implementa varios grupos de servidores front-end en un sitio central, agregando un director a ese sitio podrá simplificar las solicitudes de autenticación y mejorar el rendimiento. En este escenario, todas las solicitudes van primero al Director, que, a continuación, las enruta al grupo de servidores front-end correcto.

</div>

<span> </span>

</div>

</div>

</div>

