---
title: Consideraciones sobre la coexistencia
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Coexistence considerations
ms:assetid: 9d1a3c0f-492a-4e37-bc2f-63509e328785
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205131(v=OCS.15)
ms:contentKeyID: 48184990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e53c57b90a85024ed5375129ce23c6ff0060edc4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727990"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="coexistence-considerations"></a>Consideraciones sobre la coexistencia

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-06_

Después de la migración, solo existirá un servidor Lync Server 2013, el grupo de servidores de chat persistente y podrá dar de baja la implementación heredada.

Antes de que se complete la migración y antes de haber desactivado la implementación del servidor de chat de grupo actual, es posible que tenga alguna de las siguientes implementaciones:

  - Lync Server 2013, grupo de servidores de chat persistente, que debe estar alojado en un grupo de servidores de Lync Server 2013.

  - Lync Server 2010, grupo de chats grupales, que se debe alojar en un grupo de servidores de Lync Server 2010.

  - Grupo de chats grupales de Office Communications Server 2007 R2, que debe estar alojado en un grupo de Office Communications Server 2007 R2.

Estas implementaciones pueden existir en paralelo. Sin embargo, las categorías, salas y complementos de una implementación no interactúan con los de la implementación correspondiente.

Con la configuración manual, un cliente heredado (cliente de chat grupal) puede conectarse a un grupo a la vez para Office Communications Server 2007 R2, Lync Server 2010, chat grupal o Lync Server 2013.

Lync 2013 (cliente) solo puede interactuar con Lync Server 2013, grupo de servidores de chat persistente y no con grupos de servidores de chat heredados. Para usar el chat persistente en una 2013 (cliente) de Lync, el usuario debe estar alojado en Lync 2013 y habilitado por directiva.

</div>

<span> </span>

</div>

</div>

</div>

