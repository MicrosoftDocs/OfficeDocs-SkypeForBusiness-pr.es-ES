---
title: 'Lync Server 2013: eliminar una colección existente de opciones de configuración de CDR'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing collection of CDR configuration settings
ms:assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688128(v=OCS.15)
ms:contentKeyID: 49733726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28d15f224d7e3aa4b43b20925a4efd4007a0c6c3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835627"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="0f913-102">Eliminar una colección existente de opciones de configuración de CDR en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f913-102">Delete an existing collection of CDR configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f913-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="0f913-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="0f913-p101">El registro detallado de llamadas (CDR) permite realizar un seguimiento del uso de aspectos como las sesiones de mensajería instantánea de punto a punto, llamadas telefónicas de voz sobre IP (VoIP) y llamadas de conferencia. Estos datos de uso contienen información sobre quién llamó a quién, cuándo se realizó la llamada y su duración.</span><span class="sxs-lookup"><span data-stu-id="0f913-p101">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>

<span data-ttu-id="0f913-106">Al instalar Microsoft Lync Server 2013, se crea una única colección global de opciones de configuración de CDR.</span><span class="sxs-lookup"><span data-stu-id="0f913-106">When you install Microsoft Lync Server 2013, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="0f913-107">Los administradores tienen la opción de crear conjuntos personalizados de configuraciones que se podrán aplicar a sitios individuales.</span><span class="sxs-lookup"><span data-stu-id="0f913-107">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="0f913-108">Por diseño, las opciones configuradas en el ámbito del sitio tienen precedencia sobre las opciones configuradas en el ámbito global.</span><span class="sxs-lookup"><span data-stu-id="0f913-108">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="0f913-109">Si elimina la configuración con ámbito en el sitio, el CDR se puede administrar en dicho sitio utilizando la configuración global.</span><span class="sxs-lookup"><span data-stu-id="0f913-109">If you delete site-scoped settings, then CDR will be managed in that site by using the global settings.</span></span>

<span data-ttu-id="0f913-p103">Recuerde que también puede "eliminar" la configuración global. Pero, esta no se quitará realmente. En su lugar, todas las propiedades de dicha colección se restablecerán a sus valores predeterminados. Por ejemplo, la purga está habilitada de forma predeterminada en una colección de opciones de configuración de CDR. Supongamos que modifica la colección global y la purga se deshabilita. Si más adelante elimina la configuración global, todas las propiedades se restablecerán a sus valores predeterminados. En este caso, eso significa que la purga volverá a estar habilitada.</span><span class="sxs-lookup"><span data-stu-id="0f913-p103">Note that you can also “delete” the global settings. However, the global settings will not actually be removed. Instead, all the properties in that collection will be reset to their default values. For example, by default purging is enabled in a collection of CDR configuration settings. Suppose you modify the global collection so that purging is disabled. If you later delete the global settings, all the properties will be reset to their default values. In this case, that means that purging will once again be enabled.</span></span>

<span data-ttu-id="0f913-117">Puede quitar las opciones de configuración de CDR con el panel de control de Lync Server o el cmdlet [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="0f913-117">You can remove CDR configuration settings by using the Lync Server Control Panel or the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) cmdlet.</span></span>

<div>

## <a name="to-remove-cdr-configuration-settings-with-lync-server-control-panel"></a><span data-ttu-id="0f913-118">Para quitar la configuración de CDR con el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="0f913-118">To remove CDR configuration settings with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="0f913-119">En el panel de control de Lync Server, haga clic en **supervisión y archivado**.</span><span class="sxs-lookup"><span data-stu-id="0f913-119">In Lync Server Control Panel, click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="0f913-p104">En la pestaña **Registro detallado de llamadas**, seleccione la colección o colecciones de opciones de CDR que se van a quitar. Para seleccionar varias colecciones, haga clic en la primera colección, mantenga presionada la tecla Control y haga clic en otras colecciones.</span><span class="sxs-lookup"><span data-stu-id="0f913-p104">On the **Call Detail Recording** tab, select the collection (or collections) of CDR settings to be removed. To select multiple collections, click the first collection, hold down the Ctrl key, and click additional collections.</span></span>

3.  <span data-ttu-id="0f913-122">Haga clic en **Editar** y después en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="0f913-122">Click **Edit**, and then click **Delete**.</span></span>

4.  <span data-ttu-id="0f913-123">En el cuadro de diálogo panel de control de Lync Server, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0f913-123">In the Lync Server Control Panel dialog box, click **OK**.</span></span>

</div>

<div>

## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="0f913-124">Quitar las opciones de configuración de CDR con cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0f913-124">Removing CDR Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="0f913-125">Puede eliminar la configuración de la configuración de la llamada registrar detalles mediante Windows PowerShell y el cmdlet **Remove-CsCdrConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="0f913-125">You can delete call detail recording configuration settings by using Windows PowerShell and the **Remove-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="0f913-126">Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0f913-126">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="0f913-127">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="0f913-127">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a><span data-ttu-id="0f913-128">Para quitar una colección especificada de opciones de configuración de CDR</span><span class="sxs-lookup"><span data-stu-id="0f913-128">To remove a specified collection of CDR configuration settings</span></span>

  - <span data-ttu-id="0f913-129">Este comando quita las opciones de configuración de CDR que se aplican al sitio Redmond:</span><span class="sxs-lookup"><span data-stu-id="0f913-129">This command removes the CDR configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="0f913-130">Para quitar todas las opciones de configuración de CDR que se aplican al ámbito del sitio</span><span class="sxs-lookup"><span data-stu-id="0f913-130">To remove all the CDR configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="0f913-131">Este comando quita todas las opciones de configuración de CDR que se aplican al ámbito del sitio:</span><span class="sxs-lookup"><span data-stu-id="0f913-131">This command removes all the CDR configuration settings applied to the site scope:</span></span>
    
        Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-that-disable-call-detail-recording"></a><span data-ttu-id="0f913-132">Para quitar todas las opciones de configuración de CDR que deshabilitan el registro detallado de llamadas</span><span class="sxs-lookup"><span data-stu-id="0f913-132">To remove all the CDR configuration settings that disable call detail recording</span></span>

  - <span data-ttu-id="0f913-133">Este comando quita todas las opciones de configuración de CDR en las que se ha deshabilitado el registro detallado de llamadas:</span><span class="sxs-lookup"><span data-stu-id="0f913-133">This command removes all the CDR configuration settings where Call Detail recording has been disabled:</span></span>
    
        Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration

</div>

<span data-ttu-id="0f913-134">Para obtener más información, consulte el tema de ayuda para el cmdlet [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="0f913-134">For more information, see the help topic for the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

