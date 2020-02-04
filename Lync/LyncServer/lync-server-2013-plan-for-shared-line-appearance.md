---
title: 'Lync Server 2013: planear la apariencia de las líneas compartidas'
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
ms.openlocfilehash: 755bff84b8902e346135139d1c8c5b26c55605c1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755170"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="plan-for-shared-line-appearance-in-lync-server-2013"></a>Planear la apariencia de líneas compartidas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-03-21_

Lea este tema para obtener información sobre cómo planear la apariencia de línea compartida (SLA) en Lync Server 2013, actualización acumulativa de abril de 2016.

La apariencia de línea compartida es una característica de Lync Server 2013, actualización acumulativa de abril de 2016 para administrar varias llamadas en un número específico denominado número compartido. SLA puede configurar cualquier usuario de Lync habilitado para telefonía IP como un número compartido con varias líneas para responder a varias llamadas. En realidad, las llamadas no se reciben en el número compartido, sino que se desvían a usuarios que actúan como delegados para el número compartido. Cualquiera de estos delegados puede responder a la llamada mientras el resto de los delegados recibe una notificación en su teléfono sobre el usuario que respondió a la llamada y la línea que está ocupada como resultado. El número de líneas y los delegados se pueden configurar para un número compartido en SLA. Además, también se pueden configurar otras opciones avanzadas para un número compartido, como BusyOption (que se produce cuando todas las líneas están ocupadas) y MissedCallOption (si ninguno de los delegados responde a una llamada).

El SLA solo se admite en los siguientes dispositivos telefónicos (no es compatible con los clientes de Lync en equipos, teléfonos móviles u otros dispositivos):

  - Polycom VVX300 con actualización de firmware 5.4.1

  - Polycom VVX400 con actualización de firmware 5.4.1

  - Polycom VVX500 con actualización de firmware 5.4.1

  - Polycom VVX600 con actualización de firmware 5.4.1

SLA es una característica nueva de Lync Server 2013, actualización acumulativa de abril de 2016.

Para obtener más información sobre cómo implementar un SLA, consulte [implementar la apariencia de línea compartida en Lync Server 2013](lync-server-2013-deploy-shared-line-appearance.md).

<div>

## <a name="feature-list"></a>Lista de características

Configurar un grupo de SLA permite lo siguiente:

  - Todos los delegados del grupo pueden responder a llamadas entrantes al mismo número compartido. Las llamadas pueden estar basadas en RTC o en SIP.

  - Los delegados pueden responder llamadas y ponerlas en espera.

  - Los delegados pueden transferir llamadas a un número fuera del grupo de SLA.

  - Los delegados pueden ver cuántas llamadas están actualmente en el número compartido, así como ver el estado de esas llamadas.

  - Puede configurar un número máximo de llamadas simultáneas para el número compartido. Además, puede configurar cómo quiere administrar las llamadas adicionales cuando se alcanza el número máximo. Las llamadas que superen el límite se pueden rechazar con una señal de línea ocupada, desviar a un número alternativo o desviarlas al correo de voz.

  - Puede configurar cómo quiere administrar las llamadas perdidas (llamadas que no se responden después de un tiempo específico). Si habilita el correo de voz para la identidad de grupo, las llamadas perdidas se desvían automáticamente al correo de voz. Si no tiene habilitado el correo de voz para la identidad de grupo (número compartido), puede elegir que las llamadas perdidas se rechacen con una señal de línea ocupada, se desvíen a un número alternativo o se desconecten.

</div>

</div>

<span> </span>

</div>

</div>

</div>

