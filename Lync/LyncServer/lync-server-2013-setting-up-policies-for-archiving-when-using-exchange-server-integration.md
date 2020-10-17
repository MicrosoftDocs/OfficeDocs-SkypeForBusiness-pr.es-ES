---
title: Configuración de directivas para el archivado al usar la integración de Exchange Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up policies for Archiving when using Exchange Server integration
ms:assetid: 8b9b2bad-a4b3-42e1-85a7-04022e9442ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205063(v=OCS.15)
ms:contentKeyID: 48184742
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a63392507579a64aede11adb2bf327d0d6d56aa
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521867"
---
# <a name="setting-up-policies-for-archiving-in-lync-server-2013-when-using-exchange-server-integration"></a><span data-ttu-id="26a31-102">Configuración de directivas para el archivado en Lync Server 2013 al usar la integración de Exchange Server</span><span class="sxs-lookup"><span data-stu-id="26a31-102">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26a31-103">_**Última modificación del tema:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="26a31-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="26a31-104">Si los usuarios hospedados en Exchange 2013 tienen buzones colocados en In-Place Hold, las directivas de retención de Exchange In-Place controlan el archivado para esos usuarios.</span><span class="sxs-lookup"><span data-stu-id="26a31-104">If users homed on Exchange 2013 have their mailboxes put on In-Place Hold, Exchange In-Place Hold policies control archiving for those users.</span></span> <span data-ttu-id="26a31-105">Si usa la integración de Microsoft Exchange para su implementación, las directivas de Exchange 2013 invalidan las directivas de archivado de Lync Server para los usuarios hospedados en Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="26a31-105">If you use Microsoft Exchange integration for your deployment, Exchange 2013 policies override Lync Server Archiving policies for users who are homed on Exchange 2013.</span></span> <span data-ttu-id="26a31-106">Para obtener información acerca de cómo configurar las directivas de archivado de Exchange, consulte la documentación de Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="26a31-106">For information about configuring Exchange Archiving policies, see the Exchange 2013 documentation.</span></span> <span data-ttu-id="26a31-107">Para obtener información detallada sobre cómo configurar las directivas de usuario para los usuarios hospedados en Lync Server 2013, consulte [configuración de directivas de usuario para archivado en Lync server 2013](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="26a31-107">For details about setting up user policies for users homed on Lync Server 2013, see [Setting up user policies for Archiving in Lync Server 2013](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md) in the Deployment documentation.</span></span> <span data-ttu-id="26a31-108">Para obtener más información sobre cómo funcionan las directivas, consulte [how archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación sobre Planeación, la documentación sobre la implementación o las operaciones.</span><span class="sxs-lookup"><span data-stu-id="26a31-108">For details about how policies work, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="26a31-109">Si implementa Exchange 2013 y Lync Server 2013 en el mismo bosque, las directivas de Exchange 2013 In-Place retener controlan el archivado.</span><span class="sxs-lookup"><span data-stu-id="26a31-109">If you deploy Exchange 2013 and Lync Server 2013 in the same forest, your Exchange 2013 In-Place Hold policies control archiving.</span></span> <span data-ttu-id="26a31-110">Si implementa Exchange 2013 y Lync Server 2013 en bosques independientes, vea "implementación de Lync Server y Microsoft Exchange en bosques diferentes" en la <A href="lync-server-2013-deployment-checklist-for-archiving.md">lista de comprobación de la implementación para el archivado en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="26a31-110">If you deploy Exchange 2013 and Lync Server 2013 in separate forests, see “Deploying Lync Server and Microsoft Exchange in Different Forests” in <A href="lync-server-2013-deployment-checklist-for-archiving.md">Deployment checklist for Archiving in Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

