---
title: 'Lync Server 2013: especificación de la retención de datos de CDR'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Specifying retention of CDR data
ms:assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182581(v=OCS.15)
ms:contentKeyID: 48185299
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 32eee413b25da3231d5633e89571bbc08deb1f38
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764456"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="specifying-retention-of-cdr-data-in-lync-server-2013"></a><span data-ttu-id="9ee4c-102">Especificación de la retención de datos de CDR en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9ee4c-102">Specifying retention of CDR data in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ee4c-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="9ee4c-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="9ee4c-p101">De forma predeterminada, los datos del registro detallado de llamadas (CDR) se purgan una vez transcurridos 60 días. Puede usar la configuración de la página **Registro detallado de llamadas** para conservar los datos durante un periodo de tiempo mayor o menor. Si deshabilita CDR, los datos que se recopilaron antes de habilitarlo también se someterán a la purga.</span><span class="sxs-lookup"><span data-stu-id="9ee4c-p101">By default, call detail recording (CDR) data is purged after 60 days. You can use the settings on the **Call Detail Recording** page to retain the data for a longer or shorter period of time. If you disable CDR, data that was captured before CDR was enabled will also be subject to purging.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9ee4c-p102">Configure CDR y la calidad de la experiencia (QoE) para que conserven los datos durante el mismo número de días. Cada llamada de CDR, que se encuentra disponible en la página web Informes del Servidor de supervisión, incluye la información de QoE y CDR. Si la duración de la purga es diferente para CDR y QoE, es posible que algunas llamadas solo incluyan datos de CDR y otras solo de QoE.</span><span class="sxs-lookup"><span data-stu-id="9ee4c-p102">You should configure CDR and Quality of Experience (QoE) to retain data for the same number of days. Each call in the call detail reports (CDRs), available from the Monitoring Server Reports webpage, includes CDR and QoE information. If the purging duration for CDR and QoE is different, some calls might only include CDR data, while other may only include QoE data.</span></span>



</div>

<span data-ttu-id="9ee4c-110">Use los procedimientos siguientes para configurar la purga de los datos de CDR.</span><span class="sxs-lookup"><span data-stu-id="9ee4c-110">Use the following procedures to configure purge settings for CDR data.</span></span>

<div>

## <a name="to-specify-retention-of-cdr-data"></a><span data-ttu-id="9ee4c-111">Para especificar la retención de los datos de CDR</span><span class="sxs-lookup"><span data-stu-id="9ee4c-111">To specify retention of CDR data</span></span>

1.  <span data-ttu-id="9ee4c-112">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que haya implementado Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9ee4c-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="9ee4c-113">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9ee4c-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9ee4c-114">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9ee4c-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9ee4c-115">En la barra de navegación de la izquierda, haga clic en **Supervisión y archivado** y en **Registro de detallado de llamadas**.</span><span class="sxs-lookup"><span data-stu-id="9ee4c-115">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4.  <span data-ttu-id="9ee4c-116">En la página **Registro detallado de llamadas**, haga clic en el sitio apropiado de la tabla, en **Editar** y en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="9ee4c-116">On the **Call Detail Recording** page, click the appropriate site in the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="9ee4c-117">Para activar la purga, seleccione **Habilitar depuración de registros de detalles de llamadas (CDR)**.</span><span class="sxs-lookup"><span data-stu-id="9ee4c-117">To turn on purging, select **Enable purging of CDRs**.</span></span>

6.  <span data-ttu-id="9ee4c-118">En **Conservar registros de detalles de llamadas durante un máximo de (días):**, seleccione el número máximo de días que desea retener los registros detallados de llamadas.</span><span class="sxs-lookup"><span data-stu-id="9ee4c-118">In **Keep CDRs for maximum duration (days):** select the maximum number of days that call detail recordings should be retained.</span></span>

7.  <span data-ttu-id="9ee4c-119">En **Conservar los datos de los informes de errores durante el período de duración máximo (días):**, seleccione el número máximo de días que desea retener los registros de error.</span><span class="sxs-lookup"><span data-stu-id="9ee4c-119">In **Keep error report data for maximum duration (days):** select the maximum number of days that error reports should be retained.</span></span>

8.  <span data-ttu-id="9ee4c-120">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="9ee4c-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9ee4c-121">Especificar la retención de CDR mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9ee4c-121">Specifying CDR Retention by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="9ee4c-122">Puede crear la configuración de retención de CDR con Windows PowerShell y el cmdlet Set-CsCdrConfiguration.</span><span class="sxs-lookup"><span data-stu-id="9ee4c-122">You can create CDR retention settings by using Windows PowerShell and the Set-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="9ee4c-123">Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9ee4c-123">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9ee4c-124">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="9ee4c-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-specify-cdr-retention-for-a-specific-location"></a><span data-ttu-id="9ee4c-125">Para especificar la retención de CDR para una ubicación determinada:</span><span class="sxs-lookup"><span data-stu-id="9ee4c-125">To specify CDR retention for a specific location</span></span>

  - <span data-ttu-id="9ee4c-126">Este comando habilita la purga de los datos de CDR para el sitio de Redmond y configura el sitio para conservar los datos de CDR y de los registros de errores durante 20 días.</span><span class="sxs-lookup"><span data-stu-id="9ee4c-126">This command enables purging of CDR data for the Redmond site, and configures the site to maintain both CDR data and error reports data for 20 days.</span></span>
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20

</div>

<div>

## <a name="to-specify-cdr-retention-for-multiple-locations"></a><span data-ttu-id="9ee4c-127">Para especificar la retención de CDR para varias ubicaciones:</span><span class="sxs-lookup"><span data-stu-id="9ee4c-127">To specify CDR retention for multiple locations</span></span>

  - <span data-ttu-id="9ee4c-128">Este comando configura la retención de CDR para todos los valores de configuración de CDR que se usan en una organización.</span><span class="sxs-lookup"><span data-stu-id="9ee4c-128">This command configures CDR retention for all the CDR configuration settings in use in an organization.</span></span>
    
        Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20

</div>

<span data-ttu-id="9ee4c-129">Para obtener más información, consulte el tema de ayuda para el cmdlet [set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="9ee4c-129">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9ee4c-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ee4c-130">See Also</span></span>


[<span data-ttu-id="9ee4c-131">Grabación de detalles de llamadas (CDR) en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9ee4c-131">Call detail recording (CDR) in Lync Server 2013</span></span>](lync-server-2013-call-detail-recording-cdr.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

