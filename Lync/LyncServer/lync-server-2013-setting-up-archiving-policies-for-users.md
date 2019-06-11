---
title: 'Lync Server 2013: configuración de directivas de archivado para usuarios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up Archiving policies for users
ms:assetid: 1bbb45df-0590-4c66-9d65-d25526f57790
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204722(v=OCS.15)
ms:contentKeyID: 48183549
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55a56ff5c44d10d112762bb06662e9266dbc270b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821869"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-archiving-policies-for-users-in-lync-server-2013"></a><span data-ttu-id="a80b4-102">Configuración de directivas de archivado para usuarios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a80b4-102">Setting up Archiving policies for users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a80b4-103">_**Última modificación del tema:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="a80b4-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="a80b4-104">Puede habilitar o deshabilitar el archivado para usuarios específicos creando y configurando una directiva de archivado para los usuarios y, a continuación, aplicando la Directiva a determinados usuarios o grupos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="a80b4-104">You can enable or disable Archiving for specific users by creating and configuring an Archiving policy for users, and then applying the policy to specific users or user groups.</span></span> <span data-ttu-id="a80b4-105">Las directivas de usuario invalidan las directivas de sitio o las directivas globales.</span><span class="sxs-lookup"><span data-stu-id="a80b4-105">User policies override any global policy or site policies.</span></span> <span data-ttu-id="a80b4-106">Las directivas de archivado solo se aplican si no usa la integración de Microsoft Exchange o si usa la integración de Microsoft Exchange, pero tiene algunos usuarios que no están alojados en Exchange 2013 y tienen sus buzones en conservación local.</span><span class="sxs-lookup"><span data-stu-id="a80b4-106">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span>

<span data-ttu-id="a80b4-107">Para obtener detalles sobre cómo funcionan las directivas de archivado, incluida la jerarquía para las directivas globales, de sitio y de usuario, consulte Cómo funciona el archivado en la documentación de planeamiento, la documentación de implementación o la documentación de operaciones [de Lync Server 2013](lync-server-2013-how-archiving-works.md) .</span><span class="sxs-lookup"><span data-stu-id="a80b4-107">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a80b4-108">Si habilita la integración de Microsoft Exchange para su implementación, las directivas de retención local de Exchange controlan si el archivado está habilitado para los usuarios alojados en Exchange 2013 y si sus buzones se colocan en conservación local.</span><span class="sxs-lookup"><span data-stu-id="a80b4-108">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="a80b4-109">Para obtener más información, consulte <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">configurar directivas para archivar en Lync Server 2013 al usar la integración de Exchange Server</A> en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="a80b4-109">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="a80b4-110">Es necesario que especifique todas las opciones adecuadas en las configuraciones de archivado antes de habilitar el archivado de las comunicaciones internas o externas en las directivas de archivado.</span><span class="sxs-lookup"><span data-stu-id="a80b4-110">You should specify all appropriate options in the Archiving configurations before enabling Archiving of internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="a80b4-111">Para obtener información detallada, vea <A href="lync-server-2013-configuring-archiving-options.md">configuración de las opciones de archivado en Lync Server 2013</A> en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="a80b4-111">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a80b4-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a80b4-112">In This Section</span></span>

  - [<span data-ttu-id="a80b4-113">Configurar directivas de usuario para archivar en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a80b4-113">Setting up user policies for Archiving in Lync Server 2013</span></span>](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md)

  - [<span data-ttu-id="a80b4-114">Configurar directivas para archivar en Lync Server 2013 al usar la integración de Exchange Server</span><span class="sxs-lookup"><span data-stu-id="a80b4-114">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</span></span>](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

