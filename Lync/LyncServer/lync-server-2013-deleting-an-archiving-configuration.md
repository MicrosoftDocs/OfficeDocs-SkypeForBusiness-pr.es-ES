---
title: 'Lync Server 2013: eliminar una configuración de archivado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting an Archiving configuration
ms:assetid: a8744d39-5cf2-474c-9a99-a0f3a37f846f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205167(v=OCS.15)
ms:contentKeyID: 48185093
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a67d944de9b2c35c9ea2428603b39ddabbbcb26
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835587"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-an-archiving-configuration-in-lync-server-2013"></a><span data-ttu-id="0e3fa-102">Eliminar una configuración de archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e3fa-102">Deleting an Archiving configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e3fa-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="0e3fa-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="0e3fa-104">Puede eliminar una configuración de sitio o una configuración de grupo.</span><span class="sxs-lookup"><span data-stu-id="0e3fa-104">You can delete a site configuration or pool configuration.</span></span> <span data-ttu-id="0e3fa-105">No se puede quitar la configuración global.</span><span class="sxs-lookup"><span data-stu-id="0e3fa-105">The global configuration cannot be removed.</span></span> <span data-ttu-id="0e3fa-106">Si elimina la configuración global, esta se restablece automáticamente a sus valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="0e3fa-106">If you delete the global configuration, it is automatically reset to the default values.</span></span> <span data-ttu-id="0e3fa-107">Para obtener más información sobre cómo se implementan las configuraciones de archivado, incluidas las opciones que puede especificar y la jerarquía de las configuraciones de archivado, consulte [Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación de planeación, implementación documentación u operación.</span><span class="sxs-lookup"><span data-stu-id="0e3fa-107">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>

## <a name="to-delete-a-site-or-pool-configuration-for-archiving"></a><span data-ttu-id="0e3fa-108">Para eliminar una configuración de sitio o grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="0e3fa-108">To delete a site or pool configuration for archiving</span></span>

1.  <span data-ttu-id="0e3fa-109">Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="0e3fa-109">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0e3fa-110">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0e3fa-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0e3fa-111">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0e3fa-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0e3fa-112">En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.</span><span class="sxs-lookup"><span data-stu-id="0e3fa-112">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="0e3fa-113">En la lista de configuraciones de archivado, haga clic en la configuración de sitio o de grupo que desea eliminar y, luego, haga clic en **Editar** y en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="0e3fa-113">In the list of archiving configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="0e3fa-114">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="0e3fa-114">Click **Commit**.</span></span>

</div>

<div>

## <a name="removing-archiving-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="0e3fa-115">Quitar la configuración de archivado mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0e3fa-115">Removing Archiving Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="0e3fa-116">Los valores de configuración de archivado se pueden eliminar con Windows PowerShell y el cmdlet **Remove-CsArchivingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="0e3fa-116">Archiving configuration settings can be deleted by using Windows PowerShell and the **Remove-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="0e3fa-117">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0e3fa-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="0e3fa-118">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="0e3fa-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-archiving-configuration-settings"></a><span data-ttu-id="0e3fa-119">Para quitar una colección especificada de parámetros de configuración de archivado</span><span class="sxs-lookup"><span data-stu-id="0e3fa-119">To remove a specified collection of archiving configuration settings</span></span>

  - <span data-ttu-id="0e3fa-120">El siguiente comando quita los valores de configuración de archivado que se aplican al sitio de Redmond:</span><span class="sxs-lookup"><span data-stu-id="0e3fa-120">The following command removes the archiving configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsArchivingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-archiving-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="0e3fa-121">Para quitar todas las opciones de configuración de archivado aplicadas al ámbito del sitio</span><span class="sxs-lookup"><span data-stu-id="0e3fa-121">To remove all the archiving configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="0e3fa-122">Este comando quita todas las opciones de configuración de archivado aplicadas al ámbito de servicio:</span><span class="sxs-lookup"><span data-stu-id="0e3fa-122">This command removes all the archiving configuration settings applied to the service scope:</span></span>
    
        Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration

</div>

<div>

## <a name="to-remove-archiving-configuration-settings-based-on-a-specified-property-value"></a><span data-ttu-id="0e3fa-123">Para quitar los valores de configuración de archivado basados en un valor de propiedad especificado</span><span class="sxs-lookup"><span data-stu-id="0e3fa-123">To remove archiving configuration settings based on a specified property value</span></span>

  - <span data-ttu-id="0e3fa-124">Este comando quita todas las opciones de configuración de archivado donde se ha deshabilitado el archivado de Exchange:</span><span class="sxs-lookup"><span data-stu-id="0e3fa-124">This command removes all the archiving configuration settings where Exchange archiving has been disabled:</span></span>
    
        Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration

</div>

<span data-ttu-id="0e3fa-125">Para obtener más información, consulte el tema de ayuda para el cmdlet [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="0e3fa-125">For more information, see the help topic for the [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0e3fa-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="0e3fa-126">See Also</span></span>


[<span data-ttu-id="0e3fa-127">Cómo funciona el archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e3fa-127">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)  


[<span data-ttu-id="0e3fa-128">Administrar el archivado de comunicaciones internas y externas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e3fa-128">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

