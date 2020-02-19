---
title: 'Lync Server 2013: agregar dominios de usuarios y grupos de usuarios a la categoría de salón'
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
ms.openlocfilehash: f9e918d5c1f888d508220279426d6d6125f1416f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137871"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="adding-domains-of-users-and-user-groups-to-the-room-category-in-lync-server-2013"></a><span data-ttu-id="fba35-102">Agregar dominios de usuarios y grupos de usuarios a la categoría de salón en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fba35-102">Adding domains of users and user groups to the room category in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fba35-103">_**Última modificación del tema:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="fba35-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="fba35-104">Para agregar grupos de usuarios más grandes a un salón de chat, vea [Configure Categories in Lync Server 2013](lync-server-2013-configure-categories.md) y [Manage Categories](manage-categories.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="fba35-104">To add larger groups of users to a chat room, see [Configure categories in Lync Server 2013](lync-server-2013-configure-categories.md) and [Manage categories](manage-categories.md) in the Deployment documentation.</span></span> <span data-ttu-id="fba35-105">Por ejemplo, este comando agrega todos los usuarios de la unidad organizativa NorthAmericaUsers en Active Directory al salón de chat Norteamérica:</span><span class="sxs-lookup"><span data-stu-id="fba35-105">For example, this command adds all the users from the NorthAmericaUsers OU in active Directory to the NorthAmerica chat room:</span></span>

    Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.litwareinc.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=litwareinc,DC=com"}

<span data-ttu-id="fba35-106">El comando agrega todos los miembros del grupo de distribución de Finanzas al mismo salón de chat:</span><span class="sxs-lookup"><span data-stu-id="fba35-106">His command adds all the members from the Finance distribution group to the same chat room:</span></span>

    Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.litwareinc.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=litwareinc,DC=com"}

</div>

<span> </span>

</div>

</div>

</div>

