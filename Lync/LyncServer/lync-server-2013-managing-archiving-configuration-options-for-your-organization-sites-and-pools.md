---
title: 'Lync Server 2013: administración de las opciones de configuración de archivado para la organización, los sitios y los grupos de servidores'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Archiving configuration options for your organization, sites, and pools
ms:assetid: 377a6f80-5f2b-4bc1-b507-e930a461fb1d
ms:mtpsurl: https://technet.microsoft.com/library/JJ204802(v=OCS.15)
ms:contentKeyID: 48183830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fd9b777f3c7dbfc008f0b985a9c1512aaeb52d2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498367"
---
# <a name="managing-archiving-configuration-options-in-lync-server-2013-for-your-organization-sites-and-pools"></a><span data-ttu-id="9e1e1-102">Administración de las opciones de configuración de archivado en Lync Server 2013 para la organización, los sitios y los grupos de servidores</span><span class="sxs-lookup"><span data-stu-id="9e1e1-102">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e1e1-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="9e1e1-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="9e1e1-104">En el panel de control de Lync Server 2013, se usan configuraciones de archivado para especificar cómo se implementa el archivado.</span><span class="sxs-lookup"><span data-stu-id="9e1e1-104">In Lync Server 2013 Control Panel, you use Archiving configurations to specify how archiving is implemented.</span></span> <span data-ttu-id="9e1e1-105">Esto incluye las siguientes configuraciones de archivado:</span><span class="sxs-lookup"><span data-stu-id="9e1e1-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="9e1e1-106">Una configuración global que se crea de forma predeterminada al implementar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9e1e1-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="9e1e1-107">Unas configuraciones en el nivel de sitio y de grupo que se pueden crear y usar para especificar cómo se implementa el archivado en sitios o grupos determinados.</span><span class="sxs-lookup"><span data-stu-id="9e1e1-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="9e1e1-108">Las configuraciones de archivado se instalan inicialmente al implementar el archivado, pero podrá cambiar, agregar y eliminar las configuraciones después de la implementación.</span><span class="sxs-lookup"><span data-stu-id="9e1e1-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="9e1e1-109">En el panel de control de Lync Server 2013, puede usar la página **configuración de archivado** del grupo **archivado y supervisión** para administrar las configuraciones en el nivel global, el nivel de sitio y el nivel de grupo.</span><span class="sxs-lookup"><span data-stu-id="9e1e1-109">In Lync Server 2013 Control Panel, you can use the **Archiving Configuration** page of the **Archiving and Monitoring** group to manage configurations at the global level, site level, and pool level.</span></span> <span data-ttu-id="9e1e1-110">Para obtener información detallada sobre cómo se implementan las configuraciones de archivado, incluidas las opciones que se pueden especificar y la jerarquía de las configuraciones de archivado, vea [how archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación sobre Planeación, la documentación sobre la implementación o las operaciones.</span><span class="sxs-lookup"><span data-stu-id="9e1e1-110">For details about how Archiving configurations are implemented, including which options you can specify, and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9e1e1-111">Para usar el archivado, debe configurar las directivas de archivado para especificar si desea habilitar el archivado para las comunicaciones internas, para las comunicaciones externas o para todos los usuarios hospedados en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9e1e1-111">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for all users homed on Lync Server 2013.</span></span> <span data-ttu-id="9e1e1-112">De forma predeterminada, el archivado no está habilitado ni para la comunicación interna ni para la externa.</span><span class="sxs-lookup"><span data-stu-id="9e1e1-112">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="9e1e1-113">Si usa la integración de Microsoft Exchange, debe habilitar y configurar Exchange 2013 para que admita el archivado para todos los usuarios hospedados en Exchange 2013 cuyos buzones se hayan puesto en retención de In-Place.</span><span class="sxs-lookup"><span data-stu-id="9e1e1-113">If you use Microsoft Exchange integration, you must enable and configure Exchange 2013 to support archiving for all users homed on Exchange 2013 who have had their mailboxes put on In-Place Hold.</span></span><BR><span data-ttu-id="9e1e1-114">Antes de habilitar el archivado, especifique la configuración de archivado adecuada para su implementación y, de forma opcional, para determinas grupos y sitios, tal como se describe en esta sección.</span><span class="sxs-lookup"><span data-stu-id="9e1e1-114">Prior to enabling Archiving, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="9e1e1-115">Para obtener más información sobre cómo habilitar el archivado, consulte <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">configuración y asignación de directivas de archivado en Lync Server 2013</A> en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="9e1e1-115">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="9e1e1-116">**Para ver la información de configuración de archivado con los cmdlets de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="9e1e1-116">**To view archiving configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="9e1e1-117">Puede ver la información de configuración de archivado con Windows PowerShell y el cmdlet **Get-CsArchivingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="9e1e1-117">You can view Archiving configuration information by using Windows PowerShell and the **Get-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="9e1e1-118">Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9e1e1-118">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9e1e1-119">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="9e1e1-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="9e1e1-120">En el shell de administración de Lync Server, use el siguiente comando para ver información sobre todas las opciones de configuración de archivado:</span><span class="sxs-lookup"><span data-stu-id="9e1e1-120">In the Lync Server Management Shell, use the following command to view information about all of your archiving configuration settings:</span></span>
    
        Get-CsArchivingConfiguration

<div>

## <a name="in-this-section"></a><span data-ttu-id="9e1e1-121">En esta sección</span><span class="sxs-lookup"><span data-stu-id="9e1e1-121">In This Section</span></span>

  - [<span data-ttu-id="9e1e1-122">Crear una configuración de archivado en Lync Server 2013 para administrar el archivado de sitios o grupos de servidores específicos</span><span class="sxs-lookup"><span data-stu-id="9e1e1-122">Creating an Archiving configuration in Lync Server 2013 to manage Archiving for specific sites or pools</span></span>](lync-server-2013-creating-an-archiving-configuration-to-manage-archiving-for-specific-sites-or-pools.md)

  - [<span data-ttu-id="9e1e1-123">Habilitar o deshabilitar el archivado de sesiones de mensajería instantánea o de conferencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e1e1-123">Enabling or disabling Archiving of IM or conferencing sessions in Lync Server 2013</span></span>](lync-server-2013-enabling-or-disabling-archiving-of-im-or-conferencing-sessions.md)

  - [<span data-ttu-id="9e1e1-124">Habilitación o deshabilitación de la purga de datos archivados en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e1e1-124">Enabling or disabling the purging of archived data in Lync Server 2013</span></span>](lync-server-2013-enabling-or-disabling-the-purging-of-archived-data.md)

  - [<span data-ttu-id="9e1e1-125">Habilitación o deshabilitación del modo crítico en Lync Server 2013 para bloquear o permitir sesiones de mensajería instantánea y de conferencias web si se produce un error de archivado</span><span class="sxs-lookup"><span data-stu-id="9e1e1-125">Enabling or disabling critical mode in Lync Server 2013 to block or allow IM and web conferencing sessions if Archiving fails</span></span>](lync-server-2013-enable-disable-critical-mode.md)

  - [<span data-ttu-id="9e1e1-126">Habilitar o deshabilitar el envío de una declinación de responsabilidades de archivado a socios federados en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e1e1-126">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [<span data-ttu-id="9e1e1-127">Habilitación o deshabilitación de la integración de Lync Server 2013 con almacenamiento de Exchange</span><span class="sxs-lookup"><span data-stu-id="9e1e1-127">Enabling or disabling integration of Lync Server 2013 with Exchange storage</span></span>](lync-server-2013-enabling-or-disabling-integration-with-exchange-storage.md)

  - [<span data-ttu-id="9e1e1-128">Eliminación de una configuración de archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e1e1-128">Deleting an Archiving configuration in Lync Server 2013</span></span>](lync-server-2013-deleting-an-archiving-configuration.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9e1e1-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9e1e1-129">See Also</span></span>


[<span data-ttu-id="9e1e1-130">Administración de archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e1e1-130">Managing Lync Server 2013 Archiving</span></span>](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

