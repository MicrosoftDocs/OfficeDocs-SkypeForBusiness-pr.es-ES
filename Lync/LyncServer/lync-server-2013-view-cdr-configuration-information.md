---
title: 'Lync Server 2013: ver la información de configuración de CDR'
description: 'Lync Server 2013: ver la información de configuración de CDR.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View CDR configuration information
ms:assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688096(v=OCS.15)
ms:contentKeyID: 49733695
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 687ee05701c022e1d7ecfe2cd8be5190949c51d0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551316"
---
# <a name="view-cdr-configuration-information-in-lync-server-2013"></a><span data-ttu-id="ffc54-103">Ver la información de configuración de CDR en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ffc54-103">View CDR configuration information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ffc54-104">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="ffc54-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="ffc54-p101">El registro detallado de llamadas (CDR) permite realizar un seguimiento del uso de aspectos como las sesiones de mensajería instantánea de punto a punto, llamadas telefónicas de voz sobre IP (VoIP) y llamadas en conferencia. Estos datos de uso abarcan información sobre quién llamó a quién, cuándo se llamó y la duración de la llamada.</span><span class="sxs-lookup"><span data-stu-id="ffc54-p101">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>

<span data-ttu-id="ffc54-107">Al instalar Microsoft Lync Server 2013, se creará una única colección global de opciones de configuración de CDR.</span><span class="sxs-lookup"><span data-stu-id="ffc54-107">When you install Microsoft Lync Server 2013, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="ffc54-108">Los administradores también tienen la opción de crear colecciones de opciones de configuración personalizadas que se pueden aplicar a sitios individuales.</span><span class="sxs-lookup"><span data-stu-id="ffc54-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="ffc54-109">Puede ver las opciones de configuración de CDR que se usan en la organización mediante el panel de control de Lync Server o el cmdlet [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="ffc54-109">You can view the CDR configuration settings in use in your organization by using Lync Server Control Panel or the [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) cmdlet.</span></span>

<div>

## <a name="to-view-cdr-configuration-information-by-using-lync-server-control-panel"></a><span data-ttu-id="ffc54-110">Para ver la información de configuración de CDR mediante el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="ffc54-110">To view CDR configuration information by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="ffc54-111">En el panel de control de Lync Server, haga clic en **supervisión y archivado**.</span><span class="sxs-lookup"><span data-stu-id="ffc54-111">In Lync Server Control Panel click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="ffc54-p103">En la pestaña **Registro detallado de llamadas**, se mostrará una lista de todas las opciones de configuración de CDR. En cada colección de opciones verá la colección **Nombre**, con independencia de si se habilitó CDR (la propiedad **CDR**) y el purgado (la propiedad **Purgado de CDR**). Para ver información detallada sobre una colección en concreto, haga doble clic sobre la colección o selecciónela, haga clic en **Editar** y, luego, en **Mostrar detalles**. Tenga en cuenta que solo puede ver información detallada de una única colección de opciones de configuración al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="ffc54-p103">A list of all your CDR configuration settings will be displayed in the **Call Detail Recording** tab; for each collection of settings you will see the collection **Name**; whether or not CDR has been enabled (the **CDR** property); and whether or not purging has been enabled (the **CDR purging** property). To see detailed information about a collection, double-click the collection, or select the appropriate collection, click **Edit**, and then click **Show Details**. Note that you can only view detailed information for a single collection of CDR configuration settings at a time.</span></span>

</div>

<div>

## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ffc54-115">Ver la información de configuración de CDR mediante los cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ffc54-115">Viewing CDR Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="ffc54-116">Puede ver las opciones de configuración de CDR con Windows PowerShell y el cmdlet Get-CsCdrConfiguration.</span><span class="sxs-lookup"><span data-stu-id="ffc54-116">You can view CDR configuration settings by using Windows PowerShell and the Get-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="ffc54-117">Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ffc54-117">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="ffc54-118">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="ffc54-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-cdr-configuration-information"></a><span data-ttu-id="ffc54-119">Para ver la información de configuración de CDR</span><span class="sxs-lookup"><span data-stu-id="ffc54-119">To view CDR configuration information</span></span>

  - <span data-ttu-id="ffc54-120">Para ver información sobre todas las opciones de configuración de CDR, escriba el siguiente comando en el shell de administración de Lync Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="ffc54-120">To view information about all your CDR configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsCdrConfiguration
    
    <span data-ttu-id="ffc54-121">Devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="ffc54-121">That will return information similar to this:</span></span>
    
        Identity               : Global
        EnableCDR              : True
        EnablePurging          : True
        KeepCallDetailForDays  : 90
        KeepErrorReportForDays : 60
        PurgeHourOfDay         : 2

</div>

<span data-ttu-id="ffc54-122">Para obtener más información, consulte el tema de ayuda para el cmdlet [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="ffc54-122">For more information, see the help topic for the [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

