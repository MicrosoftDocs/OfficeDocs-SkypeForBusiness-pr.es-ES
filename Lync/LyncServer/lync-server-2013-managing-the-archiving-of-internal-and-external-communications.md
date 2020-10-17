---
title: Administración del archivado de comunicaciones internas y externas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing the Archiving of internal and external communications
ms:assetid: 6c2cf941-3204-4f1a-a7e0-416c828056d9
ms:mtpsurl: https://technet.microsoft.com/library/JJ204977(v=OCS.15)
ms:contentKeyID: 48184417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14df9a4472d920e5b583e4d2abe2deeb3fba0c98
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525037"
---
# <a name="managing-the-archiving-of-internal-and-external-communications-in-lync-server-2013"></a><span data-ttu-id="f1bf7-102">Administración del archivado de comunicaciones internas y externas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1bf7-102">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1bf7-103">_**Última modificación del tema:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="f1bf7-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="f1bf7-104">En Lync Server 2013, las directivas de archivado se usan para habilitar y deshabilitar el archivado de comunicaciones internas y externas si no se usa la integración de Microsoft Exchange o si hay usuarios que no están hospedados en Exchange 2013 con sus buzones colocados en In-Place retención.</span><span class="sxs-lookup"><span data-stu-id="f1bf7-104">In Lync Server 2013, you use Archiving policies to enable and disable archiving for internal communications and external communications if you do not use Microsoft Exchange integration or you have users who are not homed on Exchange 2013 with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="f1bf7-105">Esto incluye las siguientes directivas de archivado:</span><span class="sxs-lookup"><span data-stu-id="f1bf7-105">This includes the following Archiving policies:</span></span>

  - <span data-ttu-id="f1bf7-106">Una directiva global que se crea de forma predeterminada al implementar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f1bf7-106">A global policy that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="f1bf7-107">Directivas opcionales de nivel de sitio y de usuario que puede crear y usar para especificar cómo se implementa el archivado para sitios o usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="f1bf7-107">Optional site-level and user-level policies that you can create and use to specify how archiving is implemented for specific sites or users.</span></span>

<span data-ttu-id="f1bf7-108">Las directivas de archivado se configuran inicialmente al implementar el archivado, pero es posible cambiar, agregar y eliminar directivas después de la implementación.</span><span class="sxs-lookup"><span data-stu-id="f1bf7-108">You initially set up Archiving policies when you deploy Archiving, but you can change, add, and delete policies after deployment.</span></span> <span data-ttu-id="f1bf7-109">En el panel de control de Lync Server 2013, puede usar la página **Directiva de archivado** del grupo **archivado y supervisión** para administrar las directivas en el nivel global, en el nivel de sitio y en el nivel de usuario.</span><span class="sxs-lookup"><span data-stu-id="f1bf7-109">In Lync Server 2013 Control Panel, you can use the **Archiving Policy** page of the **Archiving and Monitoring** group to manage policies at the global level, site level, and user level.</span></span> <span data-ttu-id="f1bf7-110">Si integra el almacenamiento de Lync Server con el almacenamiento de Exchange 2013, las directivas de usuario de Exchange tienen prioridad sobre las directivas de archivado de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f1bf7-110">If you integrate your Lync Server storage with Exchange 2013 storage, the Exchange user policies take precedence over the Lync Server 2013 archiving policies.</span></span>

<span data-ttu-id="f1bf7-111">Para obtener más información sobre cómo se implementan las directivas, incluida la jerarquía de directivas, consulte [how archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación referente a la planeación, la implementación o las operaciones.</span><span class="sxs-lookup"><span data-stu-id="f1bf7-111">For details about how policies are implemented, including the hierarchy of policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="f1bf7-112">Para controlar la implementación del archivado, debe especificar opciones en las configuraciones de archivado, por ejemplo, si se deben archivar las sesiones de MI o de conferencia, el uso del modo crítico y las opciones de depuración.</span><span class="sxs-lookup"><span data-stu-id="f1bf7-112">To control the implementation of Archiving, you must specify options in Archiving configurations, such as whether to archive IM or conferencing, the use of critical mode, and purging options.</span></span> <span data-ttu-id="f1bf7-113">De manera predeterminada, no hay opciones habilitadas en la configuración de archivado global ni ninguna otra configuración de archivado de nivel de grupo.</span><span class="sxs-lookup"><span data-stu-id="f1bf7-113">By default no options are enabled in the global Archiving configuration or any site or pool Archiving configuration.</span></span> <span data-ttu-id="f1bf7-114">Debe especificar todas las opciones correspondientes en las configuraciones de archivado antes de habilitar el archivado para las comunicaciones internas o externas en las directivas de archivado.</span><span class="sxs-lookup"><span data-stu-id="f1bf7-114">You should specify all appropriate options in the Archiving configurations before enabling Archiving for internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="f1bf7-115">Para obtener más información, consulte <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">administrar las opciones de configuración de archivado en Lync Server 2013 para la organización, los sitios y los grupos</A> de servidores en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="f1bf7-115">For details, see <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</A> in the Operations documentation.</span></span><BR><span data-ttu-id="f1bf7-116">Si habilita la integración de Microsoft Exchange para su implementación, las directivas de Exchange controlan si el archivado está habilitado para los usuarios hospedados en Exchange 2013 y para los que se colocan sus buzones de In-Place.</span><span class="sxs-lookup"><span data-stu-id="f1bf7-116">If you enable Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="f1bf7-117">Para obtener más información, consulte <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">configuración de directivas para archivar en Lync Server 2013 al usar la integración de Exchange Server</A> en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="f1bf7-117">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f1bf7-118">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f1bf7-118">In This Section</span></span>

  - [<span data-ttu-id="f1bf7-119">Crear una directiva de archivado en Lync Server 2013 para habilitar o deshabilitar el archivado de comunicaciones internas o externas para sitios o usuarios específicos</span><span class="sxs-lookup"><span data-stu-id="f1bf7-119">Creating an Archiving policy in Lync Server 2013 to enable or disable Archiving of internal or external communications for specific sites or users</span></span>](lync-server-2013-create-archiving-policy-sites-users.md)

  - [<span data-ttu-id="f1bf7-120">Cambiar una directiva de archivado en Lync Server 2013 para habilitar o deshabilitar el archivado de comunicaciones internas o externas para la organización, los sitios o los usuarios</span><span class="sxs-lookup"><span data-stu-id="f1bf7-120">Changing an Archiving policy in Lync Server 2013 to enable or disable Archiving of internal or external communications for your organization, sites, or users</span></span>](lync-server-2013-change-archiving-policy-org-sites-users.md)

  - [<span data-ttu-id="f1bf7-121">Aplicar una directiva de archivado a los usuarios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1bf7-121">Applying an Archiving policy to users in Lync Server 2013</span></span>](lync-server-2013-applying-an-archiving-policy-to-users.md)

  - [<span data-ttu-id="f1bf7-122">Configuración de directivas para el archivado en Lync Server 2013 al usar la integración de Exchange Server</span><span class="sxs-lookup"><span data-stu-id="f1bf7-122">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</span></span>](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

  - [<span data-ttu-id="f1bf7-123">Eliminación de una directiva de archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1bf7-123">Deleting an Archiving policy in Lync Server 2013</span></span>](lync-server-2013-deleting-an-archiving-policy.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

