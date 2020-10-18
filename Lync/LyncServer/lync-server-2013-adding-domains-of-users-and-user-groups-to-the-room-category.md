---
title: 'Lync Server 2013: agregar dominios de usuarios y grupos de usuarios a la categoría de salón'
description: 'Lync Server 2013: agregar dominios de usuarios y grupos de usuarios a la categoría de salón.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding domains of users and user groups to the room category
ms:assetid: ee03f2cf-1c84-41c4-b524-d0729be33b8c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215884(v=OCS.15)
ms:contentKeyID: 48706013
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 196a795547d5caa6dfd1732c3d6b4630ef79438a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573526"
---
# <a name="adding-domains-of-users-and-user-groups-to-the-room-category-in-lync-server-2013"></a>Agregar dominios de usuarios y grupos de usuarios a la categoría de salón en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-07_

Para agregar grupos de usuarios más grandes a un salón de chat, vea [Configure Categories in Lync Server 2013](lync-server-2013-configure-categories.md) y [Manage Categories](manage-categories.md) en la documentación sobre implementación. Por ejemplo, este comando agrega todos los usuarios de la unidad organizativa NorthAmericaUsers en Active Directory al salón de chat Norteamérica:

    Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.litwareinc.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=litwareinc,DC=com"}

El comando agrega todos los miembros del grupo de distribución de Finanzas al mismo salón de chat:

    Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.litwareinc.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=litwareinc,DC=com"}

</div>

<span> </span>

</div>

</div>

</div>

