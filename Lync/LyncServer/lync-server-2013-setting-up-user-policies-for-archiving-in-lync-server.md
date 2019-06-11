---
title: 'Lync Server 2013: configuración de directivas de usuario para archivar en Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up user policies for Archiving in Lync Server
ms:assetid: 22d6cc76-6b5c-4a8c-bb8a-7996450ec085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204742(v=OCS.15)
ms:contentKeyID: 48183626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3921956949f38390277328495398970203993377
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850636"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-user-policies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="33232-102">Configurar directivas de usuario para archivar en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33232-102">Setting up user policies for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33232-103">_**Última modificación del tema:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="33232-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="33232-104">Habilitar o deshabilitar el archivado para usuarios específicos alojados en Lync Server 2013 requiere la creación y configuración de una o más directivas de usuario y, después, la aplicación de la directiva correspondiente a usuarios específicos o grupos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="33232-104">Enabling or disabling Archiving for specific users homed on Lync Server 2013 requires creating and configuring one or more user policies, and then applying the appropriate policy to specific users or user groups.</span></span> <span data-ttu-id="33232-105">Las directivas de usuario invalidan las directivas globales y de sitio, pero solo para usuarios alojados en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="33232-105">User policies override site and global policies, but only for users homed on Lync Server 2013.</span></span>

<span data-ttu-id="33232-106">Los usuarios siempre se encuentran alojados en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="33232-106">Users are always homed in Lync Server.</span></span> <span data-ttu-id="33232-107">Si la integración de Microsoft Exchange está habilitada, los usuarios cuyos buzones estén en Microsoft Exchange Server 2013 no necesitan tener las directivas de archivado en Lync Server administrado.</span><span class="sxs-lookup"><span data-stu-id="33232-107">If Microsoft Exchange integration is enabled, users whose mailboxes are in Microsoft Exchange Server 2013 don’t need to have their Archiving policies in Lync Server managed.</span></span> <span data-ttu-id="33232-108">Estos usuarios con archivado serán administrados por la conservación local de Exchange.</span><span class="sxs-lookup"><span data-stu-id="33232-108">These users with Archiving will be managed by Exchange In-Place Hold.</span></span>

<span data-ttu-id="33232-109">Para obtener detalles sobre cómo funcionan las directivas de archivado, incluida la jerarquía para las directivas globales, de sitio y de usuario, consulte [Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación de planeación, la documentación de implementación o la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="33232-109">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="33232-110">Si habilitó la integración de Microsoft Exchange para su implementación, las directivas de retención local de Exchange controlan si el archivado está habilitado para los usuarios alojados en Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="33232-110">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013.</span></span> <span data-ttu-id="33232-111">El archivado de estos usuarios requiere que sus buzones se coloquen en la retención local.</span><span class="sxs-lookup"><span data-stu-id="33232-111">Archiving for these users requires that they have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="33232-112">Para obtener más información, consulte <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">configurar directivas para archivar en Lync Server 2013 al usar la integración de Exchange Server</A> en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="33232-112">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="33232-113">Debe especificar todas las opciones apropiadas en las configuraciones de archivado antes de habilitar el archivado.</span><span class="sxs-lookup"><span data-stu-id="33232-113">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="33232-114">Para obtener información detallada, vea <A href="lync-server-2013-configuring-archiving-options.md">configuración de las opciones de archivado en Lync Server 2013</A> en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="33232-114">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="33232-115">En esta sección</span><span class="sxs-lookup"><span data-stu-id="33232-115">In This Section</span></span>

  - [<span data-ttu-id="33232-116">Crear y configurar directivas de usuario para archivar en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33232-116">Creating and configuring user policies for Archiving in Lync Server 2013</span></span>](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md)

  - [<span data-ttu-id="33232-117">Aplicar una directiva de archivado de Lync Server a un usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33232-117">Applying a Lync Server Archiving policy to a user in Lync Server 2013</span></span>](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

