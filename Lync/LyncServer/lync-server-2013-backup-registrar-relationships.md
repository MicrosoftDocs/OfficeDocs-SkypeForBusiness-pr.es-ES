---
title: Relaciones de registrador de copia de seguridad 2013 de Lync Server
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
ms.openlocfilehash: 9ac47dcda07d7c0ca368cc572ccfafe2c6c95b2f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181373"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-registrar-relationships-in-lync-server-2013"></a>Relaciones de registrador de reserva en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-28_

Además de proporcionar la capacidad de recuperación ante desastres, dos grupos de servidores emparejados sirven como registradores de copia de seguridad entre sí. En Lync Server 2013, las relaciones de registrador de reserva entre grupos de servidores front-end son siempre 1:1 y recíprocas. Esto significa que, si P1 es la copia de seguridad de P2, entonces P2 deberá ser la copia de seguridad de P1, y ninguna de ellas podrá ser la copia de seguridad de ningún otro grupo de servidores front-end. Se trata de un cambio en Lync Server 2010, en el que las relaciones de copia de seguridad del grupo de servidores front-end podrían ser varias a una.

Aunque las relaciones de copia de seguridad entre dos grupos de servidores front-end deben ser 1:1 y simétricas, cada grupo de servidores front-end también puede ser el registrador de reserva de cualquier número de aplicaciones de sucursal con funciones de supervivencia, al igual que en Lync Server 2010.

Tenga en cuenta que Lync Server 2013 no amplía la compatibilidad con la recuperación ante desastres a los usuarios hospedados en una aplicación de sucursal con funciones de supervivencia. Si un grupo de servidores front-end que actúa como copia de seguridad de una aplicación de sucursal con funciones de supervivencia disminuye, los usuarios que iniciaron sesión en la sucursal con funciones de supervivencia entrarán en el modo de resistencia, incluso después de que los usuarios hospedados en el grupo de servidores front-end realicen una conmutación por error al grupo de servidores front-end

</div>

<span> </span>

</div>

</div>

</div>

