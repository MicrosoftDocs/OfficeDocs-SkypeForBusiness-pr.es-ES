---
title: Consideraciones sobre la coexistencia
description: Consideraciones sobre la coexistencia.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
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
ms.openlocfilehash: fd1f9525b37bdee3249e0e47352fdea1bc7f012f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547036"
---
# <a name="coexistence-considerations"></a>Consideraciones sobre la coexistencia

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-06_

Después de la migración, solo existirá un grupo de servidores de chat persistente y Lync Server 2013 y podrá retirar su implementación heredada.

Antes de que se complete la migración y antes de que haya retirado la implementación actual del servidor de chat de grupo, puede tener alguna de las siguientes implementaciones:

  - Lync Server 2013, grupo de servidores de chat persistente, que debe estar alojado en un grupo de servidores de Lync Server 2013.

  - Lync Server 2010, grupo de chats en grupo, que debe estar alojado en un grupo de servidores de Lync Server 2010.

  - Grupo de servidores de chat en grupo de Office Communications Server 2007 R2, que debe estar alojado en un grupo de servidores de Office Communications Server 2007 R2.

Estas implementaciones pueden existir simultáneamente. Ahora bien, las categorías, salones y complementos de una implementación no interactúan con las de la implementación que la acompaña.

Mediante la configuración manual, un cliente heredado (cliente de chat en grupo) puede conectarse a un grupo de servidores a la vez para Office Communications Server 2007 R2, Lync Server 2010, chat en grupo o Lync Server 2013.

Lync 2013 (cliente) solo puede interactuar con el grupo de servidores de chat persistente de Lync Server 2013 y no con grupos de servidores de chat de grupo heredados. Para usar chat persistente en un equipo con Lync 2013 (cliente), el usuario debe estar alojado en Lync 2013 y habilitado por la Directiva.

</div>

<span> </span>

</div>

</div>

</div>

