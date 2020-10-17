---
title: 'Lync Server 2013: configuración de directivas de usuario para archivado en Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up user policies for Archiving in Lync Server
ms:assetid: 22d6cc76-6b5c-4a8c-bb8a-7996450ec085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204742(v=OCS.15)
ms:contentKeyID: 48183626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee2074aa9608dad4adcfe85845e7b2e045276f59
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497517"
---
# <a name="setting-up-user-policies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="d2757-102">Configuración de directivas de usuario para archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2757-102">Setting up user policies for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2757-103">_**Última modificación del tema:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="d2757-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="d2757-104">La habilitación o deshabilitación del archivado para usuarios específicos hospedados en Lync Server 2013 requiere la creación y configuración de una o varias directivas de usuario y, a continuación, la aplicación de la directiva correspondiente a usuarios o grupos de usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="d2757-104">Enabling or disabling Archiving for specific users homed on Lync Server 2013 requires creating and configuring one or more user policies, and then applying the appropriate policy to specific users or user groups.</span></span> <span data-ttu-id="d2757-105">Las directivas de usuario invalidan las directivas globales y de sitio, pero solo para los usuarios hospedados en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d2757-105">User policies override site and global policies, but only for users homed on Lync Server 2013.</span></span>

<span data-ttu-id="d2757-106">Los usuarios siempre se hospedan en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d2757-106">Users are always homed in Lync Server.</span></span> <span data-ttu-id="d2757-107">Si la integración de Microsoft Exchange está habilitada, los usuarios cuyos buzones estén en Microsoft Exchange Server 2013 no necesitan tener las directivas de archivado en Lync Server administradas.</span><span class="sxs-lookup"><span data-stu-id="d2757-107">If Microsoft Exchange integration is enabled, users whose mailboxes are in Microsoft Exchange Server 2013 don’t need to have their Archiving policies in Lync Server managed.</span></span> <span data-ttu-id="d2757-108">Los usuarios con archivado se administrarán con Exchange In-Place Hold.</span><span class="sxs-lookup"><span data-stu-id="d2757-108">These users with Archiving will be managed by Exchange In-Place Hold.</span></span>

<span data-ttu-id="d2757-109">Para obtener más información sobre cómo funcionan las directivas de archivado, incluida la jerarquía de las directivas globales, de sitio y de usuario, consulte [how archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación referente a la planeación, la documentación sobre la implementación o las operaciones.</span><span class="sxs-lookup"><span data-stu-id="d2757-109">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d2757-110">Si habilitó la integración de Microsoft Exchange para su implementación, las directivas de Exchange In-Place retenciones controlan si el archivado está habilitado para los usuarios hospedados en Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="d2757-110">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013.</span></span> <span data-ttu-id="d2757-111">El archivado para estos usuarios requiere que tengan sus buzones colocados en conservación local.</span><span class="sxs-lookup"><span data-stu-id="d2757-111">Archiving for these users requires that they have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="d2757-112">Para obtener más información, consulte <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">configuración de directivas para archivar en Lync Server 2013 al usar la integración de Exchange Server</A> en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="d2757-112">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="d2757-113">Antes de habilitar el archivado, debe especificar todas las opciones adecuadas en las configuraciones de archivado.</span><span class="sxs-lookup"><span data-stu-id="d2757-113">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="d2757-114">Para obtener más información, consulte <A href="lync-server-2013-configuring-archiving-options.md">Configuring archiving Options in Lync Server 2013</A> en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="d2757-114">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d2757-115">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d2757-115">In This Section</span></span>

  - [<span data-ttu-id="d2757-116">Creación y configuración de directivas de usuario para archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2757-116">Creating and configuring user policies for Archiving in Lync Server 2013</span></span>](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md)

  - [<span data-ttu-id="d2757-117">Aplicar una directiva de archivado de Lync Server a un usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2757-117">Applying a Lync Server Archiving policy to a user in Lync Server 2013</span></span>](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

