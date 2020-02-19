---
title: 'Lync Server 2013: eliminar una configuración de archivado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting an Archiving configuration
ms:assetid: a8744d39-5cf2-474c-9a99-a0f3a37f846f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205167(v=OCS.15)
ms:contentKeyID: 48185093
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 709e336f1ac627e658f4f4ba678af6e85a549bf3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138221"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-an-archiving-configuration-in-lync-server-2013"></a><span data-ttu-id="0a9bd-102">Eliminación de una configuración de archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a9bd-102">Deleting an Archiving configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a9bd-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="0a9bd-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="0a9bd-104">Puede eliminar una configuración de sitio o de grupo.</span><span class="sxs-lookup"><span data-stu-id="0a9bd-104">You can delete a site configuration or pool configuration.</span></span> <span data-ttu-id="0a9bd-105">La configuración global no se puede quitar.</span><span class="sxs-lookup"><span data-stu-id="0a9bd-105">The global configuration cannot be removed.</span></span> <span data-ttu-id="0a9bd-106">Si elimina la configuración global, esta se restablece automáticamente a los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="0a9bd-106">If you delete the global configuration, it is automatically reset to the default values.</span></span> <span data-ttu-id="0a9bd-107">Para obtener más información sobre cómo se implementan las configuraciones de archivado, incluidas las opciones que puede especificar y la jerarquía de las configuraciones de archivado, consulte [how archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación sobre Planeación, la documentación sobre la implementación o las operaciones.</span><span class="sxs-lookup"><span data-stu-id="0a9bd-107">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>

## <a name="to-delete-a-site-or-pool-configuration-for-archiving"></a><span data-ttu-id="0a9bd-108">Para eliminar una configuración de sitio o de grupo para archivado</span><span class="sxs-lookup"><span data-stu-id="0a9bd-108">To delete a site or pool configuration for archiving</span></span>

1.  <span data-ttu-id="0a9bd-109">Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="0a9bd-109">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0a9bd-110">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0a9bd-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0a9bd-111">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0a9bd-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0a9bd-112">En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, a continuación, haga clic en **Configuración de archivado**.</span><span class="sxs-lookup"><span data-stu-id="0a9bd-112">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="0a9bd-113">En la lista de configuraciones de archivado, haga clic en la configuración de sitio o de grupo que desea eliminar y, después, haga clic en **Editar** y en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="0a9bd-113">In the list of archiving configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="0a9bd-114">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="0a9bd-114">Click **Commit**.</span></span>

</div>

<div>

## <a name="removing-archiving-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="0a9bd-115">Quitar las opciones de configuración de archivado con los cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0a9bd-115">Removing Archiving Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="0a9bd-116">Las opciones de configuración de archivado se pueden eliminar con Windows PowerShell y el cmdlet **Remove-CsArchivingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="0a9bd-116">Archiving configuration settings can be deleted by using Windows PowerShell and the **Remove-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="0a9bd-117">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0a9bd-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="0a9bd-118">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="0a9bd-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-archiving-configuration-settings"></a><span data-ttu-id="0a9bd-119">Para quitar una colección especificada de opciones de configuración de archivado</span><span class="sxs-lookup"><span data-stu-id="0a9bd-119">To remove a specified collection of archiving configuration settings</span></span>

  - <span data-ttu-id="0a9bd-120">El siguiente comando quita las opciones de configuración de archivado aplicadas al sitio Redmond:</span><span class="sxs-lookup"><span data-stu-id="0a9bd-120">The following command removes the archiving configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsArchivingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-archiving-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="0a9bd-121">Para quitar todas las opciones de configuración de archivado aplicadas al ámbito de sitio</span><span class="sxs-lookup"><span data-stu-id="0a9bd-121">To remove all the archiving configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="0a9bd-122">Este comando quita todas las opciones de configuración de archivado aplicadas al ámbito de servicio:</span><span class="sxs-lookup"><span data-stu-id="0a9bd-122">This command removes all the archiving configuration settings applied to the service scope:</span></span>
    
        Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration

</div>

<div>

## <a name="to-remove-archiving-configuration-settings-based-on-a-specified-property-value"></a><span data-ttu-id="0a9bd-123">Para quitar las opciones de configuración de archivado en función de un valor de propiedad especificado</span><span class="sxs-lookup"><span data-stu-id="0a9bd-123">To remove archiving configuration settings based on a specified property value</span></span>

  - <span data-ttu-id="0a9bd-124">Este comando quita todas las opciones de configuración de archivado en las que se deshabilitó el archivado de Exchange:</span><span class="sxs-lookup"><span data-stu-id="0a9bd-124">This command removes all the archiving configuration settings where Exchange archiving has been disabled:</span></span>
    
        Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration

</div>

<span data-ttu-id="0a9bd-125">Para obtener más información, consulte el tema de ayuda del cmdlet [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="0a9bd-125">For more information, see the help topic for the [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0a9bd-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="0a9bd-126">See Also</span></span>


[<span data-ttu-id="0a9bd-127">Cómo funciona el archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a9bd-127">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)  


[<span data-ttu-id="0a9bd-128">Administración del archivado de comunicaciones internas y externas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a9bd-128">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

