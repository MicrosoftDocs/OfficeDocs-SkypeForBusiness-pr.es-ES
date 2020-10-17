---
title: 'Lync Server 2013: configuración de los equipos de Lync Server que se supervisarán'
description: 'Lync Server 2013: configurar los equipos de Lync Server que se supervisarán.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the Lync Server computers that will be monitored
ms:assetid: 9f1b2b91-d5af-42ad-a27d-b0815f762ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205118(v=OCS.15)
ms:contentKeyID: 48184927
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 742bd8a67eb42472e598c45619514e9407cb29cf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556836"
---
# <a name="configuring-the-lync-server-computers-that-will-be-monitored-in-lync-server-2013"></a>Configurar los equipos de Lync Server que se supervisarán en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-20_

Dado que Lync Server 2013 no usa el proceso de detección central que se usa en Microsoft Lync Server 2010, cada equipo de Lync Server 2013 que desee supervisar debe ser capaz de informar a sí mismo de su existencia al servidor de administración. Para hacerlo posible, debe instalar los archivos del agente Operations Manager en cada uno de los equipos que vaya a supervisar. Una vez instalados los archivos del agente, deberá configurar el equipo para que actúe como proxy de System Center. Tenga en cuenta que estos procedimientos deben realizarse después de haber instalado y configurado Lync Server en estos equipos.

</div>

<span> </span>

</div>

</div>

</div>

