---
title: 'Lync Server 2013: funciones y características de movilidad'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobility features and capabilities
ms:assetid: 12517a88-2531-44a5-bea5-d8884aff53eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689983(v=OCS.15)
ms:contentKeyID: 48183457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c534aa912e2564f8a8934aafa75bc52b76600795
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217476"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mobility-features-and-capabilities-in-lync-server-2013"></a>Características y capacidades de movilidad en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-19_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

La característica de movilidad que se incluye en las actualizaciones acumulativas para Lync Server 2013: febrero de 2013 admite Lync 2010 para móviles y la funcionalidad de clientes móviles de Lync 2013. Al implementar el servicio de movilidad de Lync Server 2013, los usuarios pueden usar dispositivos móviles Apple iOS, Android y Windows Phone compatibles, o dispositivos móviles Nokia Symbian para realizar actividades como enviar y recibir mensajes instantáneos, ver contactos y ver la presencia. Asimismo, los dispositivos móviles admiten algunas características de Enterprise Voice, como hacer clic para unirse a una conferencia, Vía trabajo, conexión con un solo número, correo de voz y llamadas perdidas. Las nuevas características presentadas en las actualizaciones acumulativas para Lync Server 2013: febrero de 2013 incluyen la capacidad de voz sobre IP (VoIP) y el vídeo (H. 264) para los asistentes a la reunión.

La característica de movilidad que se ha incluido en las actualizaciones acumulativas para Lync Server 2013: febrero de 2013 admite la funcionalidad de cliente móvil de Lync 2013. Las actualizaciones acumulativas para Lync Server 2013: febrero 2013 instalar la API Web de comunicaciones unificadas, o UCWA. UCWA es el componente usado para clientes móviles de Lync 2013. En Lync Server 2013, MCX se usa para clientes móviles de Lync 2010. Actualizaciones acumulativas para Lync Server 2013: febrero de 2013 introduce UCWA como el nuevo punto de entrada para los servicios de movilidad. Lync Server 2013 implementa de forma concurrente el servicio de movilidad (MCX), que se ha incluido en las actualizaciones acumulativas para Lync Server 2010:2011 de noviembre y proporciona soporte técnico para Lync 2010 Mobile. Al implementar las actualizaciones acumulativas para Lync Server 2013: febrero de 2013, los usuarios pueden usar dispositivos móviles Apple iOS, Android y Windows Phone compatibles para realizar actividades como las siguientes:

<div>


> [!IMPORTANT]  
> Las características admitidas por el servicio de movilidad de las actualizaciones acumulativas para Lync Server 2010: el 2011 de noviembre se indican con (MCX). Las características enumeradas son compatibles con UCWA, que se incluyen en las actualizaciones acumulativas para Lync Server 2013: febrero de 2013.



</div>

  - Enviar y recibir mensajes instantáneos (MCX)

  - Ver presencia (MCX)

  - Ver contactos (MCX)

  - Haga clic para unirse a una conferencia (MCX)

  - Llamar a través del trabajo (MCX)

  - Alcance de un solo número (MCX)

  - Correo de voz (MCX)

  - Notificación de llamada perdida (MCX)

  - Voz sobre IP (VoIP)

  - Vídeo de asistente (H. 264)

<div>


> [!NOTE]  
> Lync 2010 Mobile proporcionó un cliente para dispositivos Nokia Symbian. Lync 2013 Mobile no tendrá un cliente para dispositivos basados en Nokia Symbian.



</div>

Los usuarios de Apple iPad tendrán acceso a funciones mejoradas. Después de unirse a una reunión mediante la devolución de llamada de audio, un usuario de iPad podrá ver las presentaciones cargadas de Microsoft PowerPoint en una reunión, compartir aplicaciones y escritorios, ver la lista de participantes de la reunión y recibir notificaciones de otros tipos de contenido. que se comparten en la reunión.

<div>


> [!TIP]  
> Con un número único alcance, un usuario recibe llamadas en un teléfono móvil que se marcaron en el número de trabajo. Con llamar a través del trabajo, el usuario realiza una llamada saliente desde el cliente móvil de Lync mediante un número de teléfono del trabajo en lugar del número de teléfono móvil. Con las llamadas salientes, el cliente envía una solicitud a MCX o UCWA (en función de la versión de Lync Mobile) para realizar la llamada. El servidor inicia la llamada y, a continuación, vuelve a llamar al usuario en el teléfono móvil. Cuando el usuario responde, el servidor completa la llamada al llamar a la otra parte. Mediante el uso de llamadas vía trabajo, los usuarios pueden mantener su identidad de trabajo durante una llamada, lo que significa que el destinatario de la llamada no ve el número de teléfono móvil del autor de la llamada, y el autor de la llamada evita los gastos de llamadas salientes.



</div>

<div>


> [!NOTE]  
> No todas las características funcionan exactamente igual en todos los dispositivos móviles. Para obtener más información sobre las características admitidas en los dispositivos móviles, consulte las <A href="https://go.microsoft.com/fwlink/p/?linkid=234777">https://go.microsoft.com/fwlink/p/?LinkId=234777</A>tablas de comparación de clientes móviles en. Para más detalles sobre los dispositivos compatibles y los dispositivos compatibles, consulte los temas de requisitos en <A href="lync-server-2013-planning-for-mobile-clients.md">Planning for Mobile clients in Lync Server 2013</A>.



</div>

Cuando se usa la característica detección automática de Lync Server 2013, las aplicaciones móviles pueden ubicar automáticamente los servicios Web de Lync Server 2013 sin que los usuarios tengan que escribir manualmente las direcciones URL en la configuración del dispositivo. También se admite la introducción manual de direcciones URL en la configuración de dispositivo móvil, principalmente con fines de solución de problemas.

<div>


> [!IMPORTANT]  
> MCX y UCWA son servicios complementarios que se implementan para admitir clientes móviles de Lync 2010 y Lync 2013. Lync 2013 Mobile no podrá iniciar sesión en implementaciones de Lync Server 2010. Lync 2010 Mobile y Lync 2013 Mobile podrán usar una implementación de Lync Server 2013 con las actualizaciones acumulativas para Lync Server 2013:2013 de febrero aplicado.



</div>

La característica de movilidad también admite las *notificaciones de inserción* en los dispositivos móviles que no son compatibles con las aplicaciones que se ejecutan en segundo plano. Las notificaciones de inserción son notificaciones que se envían a dispositivos móviles sobre un evento que se produce mientras una aplicación móvil está inactiva. Por ejemplo, una invitación de mensajería instantánea (mi) perdida puede dar como resultado una notificación de inserción.

MCX, UCWA, el servicio Detección automática y la compatibilidad con notificaciones de inserción se proporcionan en Lync Server 2013. Las características de cliente actualizadas, las capacidades y el uso de UCWA como punto de entrada de movilidad se incluyen en las actualizaciones acumulativas para Lync Server 2013: febrero de 2013.

</div>

<span> </span>

</div>

</div>

</div>

