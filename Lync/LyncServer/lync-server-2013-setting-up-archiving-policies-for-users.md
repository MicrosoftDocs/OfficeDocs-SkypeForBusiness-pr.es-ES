---
title: 'Lync Server 2013: configuración de directivas de archivado para usuarios'
description: 'Lync Server 2013: configuración de directivas de archivado para usuarios.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Archiving policies for users
ms:assetid: 1bbb45df-0590-4c66-9d65-d25526f57790
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204722(v=OCS.15)
ms:contentKeyID: 48183549
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c18a15c1a0611f49a6fd9a4983f3ce87104332e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559526"
---
# <a name="setting-up-archiving-policies-for-users-in-lync-server-2013"></a><span data-ttu-id="77f7e-103">Configuración de directivas de archivado para usuarios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77f7e-103">Setting up Archiving policies for users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77f7e-104">_**Última modificación del tema:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="77f7e-104">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="77f7e-105">Puede habilitar o deshabilitar el archivado para usuarios específicos creando y configurando una directiva de archivado para los usuarios y, a continuación, aplicando la Directiva a usuarios o grupos de usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="77f7e-105">You can enable or disable Archiving for specific users by creating and configuring an Archiving policy for users, and then applying the policy to specific users or user groups.</span></span> <span data-ttu-id="77f7e-106">Las directivas de usuario invalidan la directiva global o las directivas de sitio.</span><span class="sxs-lookup"><span data-stu-id="77f7e-106">User policies override any global policy or site policies.</span></span> <span data-ttu-id="77f7e-107">Las directivas de archivado solo se aplican si no se usa la integración de Microsoft Exchange o si se usa la integración de Microsoft Exchange, pero hay algunos usuarios que no están hospedados en Exchange 2013 y que sus buzones se colocan en In-Place retención.</span><span class="sxs-lookup"><span data-stu-id="77f7e-107">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span>

<span data-ttu-id="77f7e-108">Para obtener más información sobre cómo funcionan las directivas de archivado, incluida la jerarquía de las directivas globales, de sitio y de usuario, consulte [how archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning Documentation, Deployment Documentation o Operations Documentation.</span><span class="sxs-lookup"><span data-stu-id="77f7e-108">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="77f7e-109">Si habilita la integración de Microsoft Exchange para su implementación, las directivas de Exchange In-Place retenciones controlan si el archivado está habilitado para los usuarios que están hospedados en Exchange 2013 y que sus buzones se colocan en In-Place suspensión.</span><span class="sxs-lookup"><span data-stu-id="77f7e-109">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="77f7e-110">Para obtener más información, consulte <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">configuración de directivas para archivar en Lync Server 2013 al usar la integración de Exchange Server</A> en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="77f7e-110">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="77f7e-111">Debe especificar las opciones correctas en la configuración del archivado antes de habilitar el archivado de las comunicaciones internas o externas en las directivas de archivado.</span><span class="sxs-lookup"><span data-stu-id="77f7e-111">You should specify all appropriate options in the Archiving configurations before enabling Archiving of internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="77f7e-112">Para obtener más información, consulte <A href="lync-server-2013-configuring-archiving-options.md">Configuring archiving Options in Lync Server 2013</A> en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="77f7e-112">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="77f7e-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="77f7e-113">In This Section</span></span>

  - [<span data-ttu-id="77f7e-114">Configuración de directivas de usuario para archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77f7e-114">Setting up user policies for Archiving in Lync Server 2013</span></span>](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md)

  - [<span data-ttu-id="77f7e-115">Configuración de directivas para el archivado en Lync Server 2013 al usar la integración de Exchange Server</span><span class="sxs-lookup"><span data-stu-id="77f7e-115">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</span></span>](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

