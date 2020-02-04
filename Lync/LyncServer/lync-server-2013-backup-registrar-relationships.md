---
title: Relaciones del registrador de copia de seguridad en Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup Registrar relationships
ms:assetid: 7e078271-84b9-4666-989c-c4507a0cdf4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205033(v=OCS.15)
ms:contentKeyID: 48184631
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44111dbdec945e525b1ef54d910e1cf7f3b5a5d0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730350"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-registrar-relationships-in-lync-server-2013"></a>Relaciones del registrador de copia de seguridad en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-28_

Además de proporcionar la capacidad de recuperación ante desastres, dos grupos de servidores emparejados sirven como registradores de copia de seguridad entre sí. En Lync Server 2013, las relaciones de registro de copia de seguridad entre los grupos frontales siempre son de 1:1 y recíprocas. Esto significa que si P1 es la copia de seguridad de P2, P2 debe ser la copia de seguridad de P1, y ninguno puede ser la copia de seguridad de ningún otro grupo de servidores front-end. Este es un cambio de Lync Server 2010, en el que las relaciones de copia de seguridad del grupo de servidores front-end podrían ser varias a una.

A pesar de que las relaciones de copia de seguridad entre dos grupos front-end deben ser 1:1 y simétricas, cada grupo de servidores front-end también puede ser el registrador de copias de seguridad para cualquier serie de equipos de sucursales con supervivencia, al igual que en Lync Server 2010.

Tenga en cuenta que Lync Server 2013 no amplía la compatibilidad de recuperación ante desastres a los usuarios alojados en un dispositivo de sucursal con la supervivencia. Si un grupo de servidores front-end que funciona como la copia de seguridad de un equipo de sucursales con la supervivencia, deja de funcionar, los usuarios que hayan iniciado sesión en el dispositivo de sucursal con la supervivencia se clasificarán en el modo de resistencia, incluso después de que los usuarios alojados en el grupo frontal no realicen la copia de seguridad del grupo frontal.

</div>

<span> </span>

</div>

</div>

</div>

