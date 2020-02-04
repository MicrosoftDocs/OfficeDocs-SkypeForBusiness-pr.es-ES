---
title: 'Lync Server 2013: administración de las opciones de configuración de archivado para su organización, sitios y grupos'
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
ms.openlocfilehash: 59db9765b9e9ee0b453268ea9c22d897f10ba662
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765611"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-archiving-configuration-options-in-lync-server-2013-for-your-organization-sites-and-pools"></a><span data-ttu-id="465e9-102">Administrar las opciones de configuración de archivado en Lync Server 2013 para su organización, sitios y grupos</span><span class="sxs-lookup"><span data-stu-id="465e9-102">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="465e9-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="465e9-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="465e9-104">En el panel de control de Lync Server 2013, se usan configuraciones de archivado para especificar cómo se implementa el archivado.</span><span class="sxs-lookup"><span data-stu-id="465e9-104">In Lync Server 2013 Control Panel, you use Archiving configurations to specify how archiving is implemented.</span></span> <span data-ttu-id="465e9-105">Esto incluye las siguientes configuraciones de archivado:</span><span class="sxs-lookup"><span data-stu-id="465e9-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="465e9-106">Una configuración global que se crea de forma predeterminada al implementar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="465e9-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="465e9-107">Configuraciones de nivel de sitio y de grupo opcionales que puede crear y usar para especificar cómo se implementa el archivado para grupos o sitios específicos.</span><span class="sxs-lookup"><span data-stu-id="465e9-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="465e9-108">Inicialmente, debe configurar las configuraciones de archivado al implementar el archivado, pero puede cambiar, agregar y eliminar configuraciones después de la implementación.</span><span class="sxs-lookup"><span data-stu-id="465e9-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="465e9-109">En el panel de control de Lync Server 2013, puede usar la página **configuración de archivado** del grupo **archivado y supervisión** para administrar las configuraciones a nivel global, nivel de sitio y nivel de grupo.</span><span class="sxs-lookup"><span data-stu-id="465e9-109">In Lync Server 2013 Control Panel, you can use the **Archiving Configuration** page of the **Archiving and Monitoring** group to manage configurations at the global level, site level, and pool level.</span></span> <span data-ttu-id="465e9-110">Para obtener detalles sobre cómo se implementan las configuraciones de archivado, incluidas las opciones que puede especificar y la jerarquía de las configuraciones de archivado, consulte [Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación de planeación, la documentación de implementación o la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="465e9-110">For details about how Archiving configurations are implemented, including which options you can specify, and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="465e9-111">Para usar el archivado, debe configurar las directivas de archivado para especificar si desea habilitar el archivado de las comunicaciones internas, de las comunicaciones externas o de ambos para todos los usuarios alojados en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="465e9-111">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for all users homed on Lync Server 2013.</span></span> <span data-ttu-id="465e9-112">De forma predeterminada, el archivado no está habilitado para las comunicaciones internas o externas.</span><span class="sxs-lookup"><span data-stu-id="465e9-112">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="465e9-113">Si usa la integración de Microsoft Exchange, debe habilitar y configurar Exchange 2013 para que admita el archivado de todos los usuarios alojados en Exchange 2013 que hayan puesto sus buzones en conservación local.</span><span class="sxs-lookup"><span data-stu-id="465e9-113">If you use Microsoft Exchange integration, you must enable and configure Exchange 2013 to support archiving for all users homed on Exchange 2013 who have had their mailboxes put on In-Place Hold.</span></span><BR><span data-ttu-id="465e9-114">Antes de habilitar el archivado, debe especificar las configuraciones de archivado apropiadas para su implementación y, opcionalmente, para determinados sitios y grupos, tal y como se describe en esta sección.</span><span class="sxs-lookup"><span data-stu-id="465e9-114">Prior to enabling Archiving, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="465e9-115">Para obtener más información sobre cómo habilitar el archivado, vea <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">configurar y asignar directivas de archivado en Lync Server 2013</A> en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="465e9-115">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="465e9-116">**Para ver la información de configuración de archivado mediante cmdlets de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="465e9-116">**To view archiving configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="465e9-117">Puede ver la información de configuración de archivado mediante Windows PowerShell y el cmdlet **Get-CsArchivingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="465e9-117">You can view Archiving configuration information by using Windows PowerShell and the **Get-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="465e9-118">Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="465e9-118">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="465e9-119">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="465e9-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="465e9-120">En el shell de administración de Lync Server, use el siguiente comando para ver información sobre todas las opciones de configuración de archivado:</span><span class="sxs-lookup"><span data-stu-id="465e9-120">In the Lync Server Management Shell, use the following command to view information about all of your archiving configuration settings:</span></span>
    
        Get-CsArchivingConfiguration

<div>

## <a name="in-this-section"></a><span data-ttu-id="465e9-121">En esta sección</span><span class="sxs-lookup"><span data-stu-id="465e9-121">In This Section</span></span>

  - [<span data-ttu-id="465e9-122">Creación de una configuración de archivado en Lync Server 2013 para administrar el archivado de sitios o grupos específicos</span><span class="sxs-lookup"><span data-stu-id="465e9-122">Creating an Archiving configuration in Lync Server 2013 to manage Archiving for specific sites or pools</span></span>](lync-server-2013-creating-an-archiving-configuration-to-manage-archiving-for-specific-sites-or-pools.md)

  - [<span data-ttu-id="465e9-123">Habilitar o deshabilitar el archivado de sesiones de mensajería instantánea o de conferencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="465e9-123">Enabling or disabling Archiving of IM or conferencing sessions in Lync Server 2013</span></span>](lync-server-2013-enabling-or-disabling-archiving-of-im-or-conferencing-sessions.md)

  - [<span data-ttu-id="465e9-124">Habilitar o deshabilitar la purga de datos archivados en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="465e9-124">Enabling or disabling the purging of archived data in Lync Server 2013</span></span>](lync-server-2013-enabling-or-disabling-the-purging-of-archived-data.md)

  - [<span data-ttu-id="465e9-125">Habilitar o deshabilitar el modo crítico en Lync Server 2013 para bloquear o permitir sesiones de mensajería instantánea y Web si se produce un error de archivado</span><span class="sxs-lookup"><span data-stu-id="465e9-125">Enabling or disabling critical mode in Lync Server 2013 to block or allow IM and web conferencing sessions if Archiving fails</span></span>](lync-server-2013-enable-disable-critical-mode.md)

  - [<span data-ttu-id="465e9-126">Habilitar o deshabilitar el envío de una renuncia de archivado a socios federados en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="465e9-126">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [<span data-ttu-id="465e9-127">Habilitar o deshabilitar la integración de Lync Server 2013 con almacenamiento de Exchange</span><span class="sxs-lookup"><span data-stu-id="465e9-127">Enabling or disabling integration of Lync Server 2013 with Exchange storage</span></span>](lync-server-2013-enabling-or-disabling-integration-with-exchange-storage.md)

  - [<span data-ttu-id="465e9-128">Eliminar una configuración de archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="465e9-128">Deleting an Archiving configuration in Lync Server 2013</span></span>](lync-server-2013-deleting-an-archiving-configuration.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="465e9-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="465e9-129">See Also</span></span>


[<span data-ttu-id="465e9-130">Administración de archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="465e9-130">Managing Lync Server 2013 Archiving</span></span>](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

