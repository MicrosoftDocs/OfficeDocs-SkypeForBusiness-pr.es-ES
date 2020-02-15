---
title: 'Lync Server 2013: planear la apariencia de línea compartida'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Plan for Shared Line Appearance
ms:assetid: a35c83d8-f531-445b-a8d2-d5d8cec77c6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Mt712151(v=OCS.15)
ms:contentKeyID: 72522136
ms.date: 03/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fdb4f8ad407950f8d3180d030ede03a1e93cf0b3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050602"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="plan-for-shared-line-appearance-in-lync-server-2013"></a>Planeación de la apariencia de línea compartida en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-03-21_

Lea este tema para obtener información sobre cómo planear la apariencia de línea compartida (SLA) en Lync Server 2013, actualización acumulativa abril de 2016.

La apariencia de línea compartida es una característica de Lync Server 2013, actualización acumulativa de abril de 2016 para administrar varias llamadas en un número específico denominado número compartido. SLA puede configurar cualquier usuario de Lync habilitado para Enterprise Voice como un número compartido con varias líneas para responder a varias llamadas. En realidad, las llamadas no se reciben en el número compartido, sino que se reenvían a los usuarios que actúan como delegados para el número compartido. Cualquiera de los delegados puede recoger la llamada mientras el resto de los delegados reciben una notificación en su teléfono sobre quién ha seleccionado la llamada y qué línea se ha vuelto ocupada como resultado. Tanto el número de líneas como los delegados se pueden configurar para un número compartido en SLA. Además, las opciones avanzadas, como BusyOption (lo que sucede en una situación en la que todas las líneas están ocupadas) y MissedCallOption (el caso en que ninguno de los delegados selecciona una llamada), también se pueden configurar para un número compartido.

SLA solo se admite en los siguientes dispositivos telefónicos (no es compatible con los clientes de Lync en equipos, teléfonos móviles u otros dispositivos):

  - Polycom VVX300 con actualización de firmware 5.4.1

  - Polycom VVX400 con actualización de firmware 5.4.1

  - Polycom VVX500 con actualización de firmware 5.4.1

  - Polycom VVX600 con actualización de firmware 5.4.1

SLA es una nueva característica de Lync Server 2013, actualización acumulativa de abril de 2016.

Para obtener información sobre la implementación de SLA, consulte [deploy Shared line Appearance in Lync Server 2013](lync-server-2013-deploy-shared-line-appearance.md).

<div>

## <a name="feature-list"></a>Lista de características

La configuración de un grupo de SLA permite lo siguiente:

  - Todos los delegados del grupo pueden responder a las llamadas entrantes al mismo número compartido. Las llamadas pueden estar basadas en RTC o en SIP.

  - Los delegados pueden contener y seleccionar llamadas.

  - Los delegados pueden transferir llamadas a un número fuera del grupo de SLA.

  - Los delegados pueden ver cuántas llamadas hay actualmente en el número compartido y ver el estado de cada una de las llamadas.

  - Puede configurar un número máximo de llamadas simultáneas para el número compartido. También puede establecer cómo desea que se traten las llamadas adicionales después de que se alcance este máximo. Las llamadas excesivas pueden rechazarse con una señal de ocupado, desviarse a un número alternativo o reenviarse a un correo de voz.

  - Puede configurar el modo en que desea que se controlen las llamadas perdidas (llamadas que no se seleccionan después de un período de tiempo determinado). Si habilita el correo de voz para la identidad de grupo, las llamadas perdidas pasarán automáticamente a correo de voz. Si no tiene habilitado el correo de voz para la identidad de grupo (número compartido), puede elegir que las llamadas perdidas se rechacen con una señal de ocupado, se reenvíen a un número alternativo o se desconecten.

</div>

</div>

<span> </span>

</div>

</div>

</div>

