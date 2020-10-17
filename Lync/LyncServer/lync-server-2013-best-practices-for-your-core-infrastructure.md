---
title: 'Lync Server 2013: procedimientos recomendados para la infraestructura básica'
description: 'Lync Server 2013: procedimientos recomendados para la infraestructura básica.'
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
ms.openlocfilehash: d0ea7cb9c7685a3b6f7c04146ec5631bbac10fe6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552196"
---
# <a name="best-practices-for-your-core-infrastructure-in-lync-server-2013"></a>Procedimientos recomendados para la infraestructura básica en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-01-27_

Es probable que ya haya tomado las medidas necesarias para diseñar la tolerancia a errores en el sistema, mediante el uso de prácticas como garantizar la redundancia de hardware, la protección frente a interrupciones del suministro eléctrico, realizar instalaciones rutinarias de las actualizaciones de seguridad y las medidas contra virus, además de la supervisión de la actividad del servidor. Estas prácticas no solo benefician la infraestructura de Microsoft Lync Server 2013, sino también de toda la red. Si no ha implementado estos procedimientos, le recomendamos que lo haga antes de implementar Lync Server 2013.

Para ayudar a proteger los servidores de la implementación de Lync Server 2013 de daños accidentales o intencionados que puedan provocar un tiempo de inactividad, adopte las siguientes precauciones:

  - Mantenga los servidores actualizados con las actualizaciones de seguridad. Al suscribirse al Servicio de notificación de seguridad de Microsoft (Microsoft Security Notification Service), se garantiza que recibirá notificación inmediata de las nuevas versiones de los boletines de seguridad de los productos de Microsoft. Para suscribirse, vaya al sitio web de notificaciones de seguridad técnica de Microsoft en [https://go.microsoft.com/fwlink/p/?LinkId=145202](https://go.microsoft.com/fwlink/p/?linkid=145202) .

  - Asegúrese de que los derechos de acceso estén correctamente configurados.

  - Mantenga los servidores en un entorno físico que evite el acceso no autorizado. Asegúrese de que haya un software antivirus adecuado instalado en todos los servidores. Mantenga el software actualizado con los archivos de firma de virus más recientes. Utilice la función de actualización automática de la aplicación de antivirus para mantener las firmas de virus actualizadas.

  - Le recomendamos que deshabilite los servicios del sistema operativo Windows Server que no son necesarios en los equipos en los que se instala Lync Server 2013.

  - Cifre los sistemas operativos y las unidades de disco en los que se encuentren almacenados los datos mediante un sistema de cifrado de todo el volumen, a menos que pueda garantizar un control constante y completo de los servidores, aislamiento físico total y la retirada correcta y segura de las unidades de disco que se sustituyan o fallen.

  - Deshabilite todos los puertos de Acceso directo a memoria (DMA) del servidor, a menos que pueda garantizar un control muy estricto del acceso físico a los servidores. Los ataques basados en DMA, que pueden iniciarse de una forma muy sencilla, pueden exponer información muy confidencial, como es el caso de las claves de cifrado privadas.

</div>

<span> </span>

</div>

</div>

</div>

