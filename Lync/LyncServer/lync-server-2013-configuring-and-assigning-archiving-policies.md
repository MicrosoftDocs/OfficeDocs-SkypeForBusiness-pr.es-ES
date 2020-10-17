---
title: 'Lync Server 2013: configuración y asignación de directivas de archivado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring and assigning Archiving policies
ms:assetid: acd18ea8-c7f1-4178-871a-cd3b75bdaa8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205175(v=OCS.15)
ms:contentKeyID: 48185121
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af6a253de4d35b3505b5ffa8be42fae297221641
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517577"
---
# <a name="configuring-and-assigning-archiving-policies-in-lync-server-2013"></a><span data-ttu-id="56da4-102">Configuración y asignación de directivas de archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56da4-102">Configuring and assigning Archiving policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56da4-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="56da4-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="56da4-104">En Lync Server 2013, las directivas se usan para habilitar y deshabilitar el archivado de comunicaciones internas y comunicaciones externas para los usuarios hospedados en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="56da4-104">In Lync Server 2013, you use policies to enable and disable archiving for internal communications and external communications for users who are homed on Lync Server 2013.</span></span> <span data-ttu-id="56da4-105">Esto incluye las siguientes directivas de archivado:</span><span class="sxs-lookup"><span data-stu-id="56da4-105">This includes the following Archiving policies:</span></span>

  - <span data-ttu-id="56da4-106">Una directiva global que se crea de forma predeterminada al implementar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="56da4-106">A global policy that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="56da4-107">Directivas opcionales de nivel de sitio y de usuario que puede crear y usar para especificar cómo se implementa el archivado para sitios o usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="56da4-107">Optional site-level and user-level policies that you can create and use to specify how archiving is implemented for specific sites or users.</span></span>

<span data-ttu-id="56da4-108">Las directivas de archivado se configuran inicialmente al implementar el archivado, pero es posible cambiar, agregar y eliminar directivas después de la implementación.</span><span class="sxs-lookup"><span data-stu-id="56da4-108">You initially set up Archiving policies when you deploy Archiving, but you can change, add, and delete policies after deployment.</span></span> <span data-ttu-id="56da4-109">En el panel de control de Lync Server 2013, puede usar la página **Directiva de archivado** del grupo **archivado y supervisión** para administrar las directivas en el nivel global, en el nivel de sitio y en el nivel de usuario.</span><span class="sxs-lookup"><span data-stu-id="56da4-109">In Lync Server 2013 Control Panel, you can use the **Archiving Policy** page of the **Archiving and Monitoring** group to manage policies at the global level, site level, and user level.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="56da4-110">Para controlar la implementación del archivado, debe especificar opciones en las configuraciones de archivado, por ejemplo, si se deben archivar las sesiones de MI o de conferencia, el uso del modo crítico y las opciones de depuración.</span><span class="sxs-lookup"><span data-stu-id="56da4-110">To control the implementation of Archiving, you must specify options in Archiving configurations, such as whether to archive IM or conferencing, the use of critical mode, and purging options.</span></span> <span data-ttu-id="56da4-111">De manera predeterminada, no hay opciones habilitadas en la configuración de archivado global ni ninguna otra configuración de archivado de nivel de grupo.</span><span class="sxs-lookup"><span data-stu-id="56da4-111">By default no options are enabled in the global Archiving configuration or any site or pool Archiving configuration.</span></span> <span data-ttu-id="56da4-112">Debe especificar todas las opciones correspondientes en las configuraciones de archivado antes de habilitar el archivado para las comunicaciones internas o externas en las directivas de archivado.</span><span class="sxs-lookup"><span data-stu-id="56da4-112">You should specify all appropriate options in the Archiving configurations before enabling Archiving for internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="56da4-113">Para obtener más información, consulte <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">administrar las opciones de configuración de archivado en Lync Server 2013 para la organización, los sitios y los grupos</A> de servidores en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="56da4-113">For details, see <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</A> in the Operations documentation.</span></span><BR><span data-ttu-id="56da4-114">Si integra el almacenamiento de Lync Server con el almacenamiento de Exchange 2013, las directivas de usuario de Exchange tienen prioridad sobre las directivas de archivado de Lync Server 2013, pero solo para los usuarios hospedados en Exchange 2013 cuyos buzones se han puesto en In-Place retención.</span><span class="sxs-lookup"><span data-stu-id="56da4-114">If you integrate your Lync Server storage with Exchange 2013 storage, the Exchange user policies take precedence over the Lync Server 2013 archiving policies but only for those users who are homed on Exchange 2013 who have had their mailboxes put on In-Place Hold.</span></span>



</div>

<span data-ttu-id="56da4-115">Para obtener más información sobre cómo se implementan las directivas, incluida la jerarquía de directivas, consulte [how archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación referente a la planeación, la implementación o las operaciones.</span><span class="sxs-lookup"><span data-stu-id="56da4-115">For details about how policies are implemented, including the hierarchy of policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span> <span data-ttu-id="56da4-116">Para obtener más información sobre cómo administrar directivas tras la implementación, consulte [Administración del archivado de comunicaciones internas y externas en Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) en la documentación referente a las operaciones.</span><span class="sxs-lookup"><span data-stu-id="56da4-116">For details about how to manage policies after deployment, see [Managing the Archiving of internal and external communications in Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) in the Operations documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="56da4-117">En esta sección</span><span class="sxs-lookup"><span data-stu-id="56da4-117">In This Section</span></span>

  - [<span data-ttu-id="56da4-118">Configuración de la directiva global para el archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56da4-118">Configuring the global policy for Archiving in Lync Server 2013</span></span>](lync-server-2013-configuring-the-global-policy-for-archiving.md)

  - [<span data-ttu-id="56da4-119">Configuración de directivas de sitio para archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56da4-119">Setting up site policies for Archiving in Lync Server 2013</span></span>](lync-server-2013-setting-up-site-policies-for-archiving.md)

  - [<span data-ttu-id="56da4-120">Configuración de directivas de archivado para usuarios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56da4-120">Setting up Archiving policies for users in Lync Server 2013</span></span>](lync-server-2013-setting-up-archiving-policies-for-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

