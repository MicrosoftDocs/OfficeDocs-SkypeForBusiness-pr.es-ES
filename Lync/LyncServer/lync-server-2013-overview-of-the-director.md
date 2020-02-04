---
title: 'Lync Server 2013: Información general sobre el director'
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
ms.openlocfilehash: 51ee90020be9d23384c5ed90ca1f8095156eaf56
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755444"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-director-in-lync-server-2013"></a>Información general sobre el director en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-08_

Un director es un servidor que ejecuta Lync Server 2013 que autentica solicitudes de usuario, pero no aloja cuentas de usuario. De manera opcional, puede implementar un director en los dos escenarios siguientes:

  - Si habilita el acceso de usuarios externos mediante la implementación de servidores perimetrales, también debe implementar un director. En este escenario, el director autentica a los usuarios externos y, a continuación, pasa su tráfico a los servidores internos. Cuando se usa un director para autenticar usuarios externos, libera servidores de grupo de servidores front-end de la sobrecarga de realizar la autenticación de estos usuarios. También ayuda a aislar grupos internos de aplicaciones para el usuario contra tráfico malintencionado, como ataques de denegación de servicio. Si la red se inunda con tráfico externo no válido en tal ataque, este tráfico finaliza en el director.

  - Si implementa varios grupos front-end en un sitio central agregando un director a ese sitio, podrá optimizar las solicitudes de autenticación y mejorar el rendimiento. En este escenario, todas las solicitudes se dirigen al Director, que a su vez las enruta al grupo de servidores front-end correcto.

</div>

<span> </span>

</div>

</div>

</div>

