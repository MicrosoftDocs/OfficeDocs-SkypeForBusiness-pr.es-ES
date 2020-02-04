---
title: 'Lync Server 2013: procedimientos recomendados para su infraestructura básica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for your core infrastructure in Lync Server 2013
ms:assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518328(v=OCS.15)
ms:contentKeyID: 61071242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c6a8663bfae2411926fe08a497a5004def051ae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737580"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-your-core-infrastructure-in-lync-server-2013"></a>Procedimientos recomendados para su infraestructura básica en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-01-27_

Es probable que ya haya tomado las medidas para diseñar la tolerancia a errores en el sistema, con prácticas tales como garantizar la redundancia de hardware, protegerse contra la pérdida de energía, instalar de forma rutinaria actualizaciones de seguridad y medidas antivirus, y supervisar la actividad del servidor. Estas prácticas no solo benefician la infraestructura de Microsoft Lync Server 2013, sino también de toda la red. Si no ha implementado estos procedimientos, le recomendamos que lo haga antes de implementar Lync Server 2013.

Para ayudar a proteger los servidores de su implementación de Lync Server 2013 de daños accidentales o intencionados que pueden dar lugar a un tiempo de inactividad, tome las siguientes precauciones:

  - Mantenga sus servidores al día con las actualizaciones de seguridad. Suscribirse al servicio de notificaciones de seguridad de Microsoft le ayuda a recibir notificaciones inmediatas de versiones de boletines de seguridad para cualquier producto de Microsoft. Para suscribirse, vaya al sitio web de notificaciones de seguridad [http://go.microsoft.com/fwlink/p/?LinkId=145202](http://go.microsoft.com/fwlink/p/?linkid=145202)técnica de Microsoft en.

  - Asegúrese de que los derechos de acceso están configurados correctamente.

  - Mantenga los servidores en un entorno físico que evite el acceso no autorizado. Asegúrese de que el software antivirus adecuado esté instalado en todos los servidores. Mantenga el software actualizado con los últimos archivos de firma de virus. Use la característica de actualización automática de su aplicación antivirus para mantener actualizadas las firmas de virus.

  - Le recomendamos que deshabilite los servicios del sistema operativo Windows Server que no son necesarios en los equipos en los que instala Lync Server 2013.

  - Cifre los sistemas operativos y las unidades de disco en los que los datos se almacenan con un sistema de cifrado de volumen completo, a menos que pueda garantizar un control completo y constante de los servidores, el aislamiento físico total y la retirada correcta y segura de disco reemplazado o fallido discos.

  - Deshabilite todos los puertos de acceso directo a memoria (DMA) externos del servidor, a menos que pueda garantizar un control muy estricto sobre el acceso físico a los servidores. Los ataques basados en DMA, que se pueden iniciar con bastante facilidad, pueden exponer información muy confidencial, como las claves de cifrado privadas.

</div>

<span> </span>

</div>

</div>

</div>

