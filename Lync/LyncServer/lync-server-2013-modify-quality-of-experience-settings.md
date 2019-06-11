---
title: 'Lync Server 2013: modificar la configuración de la calidad de la experiencia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify Quality of Experience settings
ms:assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182563(v=OCS.15)
ms:contentKeyID: 48184996
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ce6041e6512714f10785cf2976727788e105f70
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826874"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-quality-of-experience-settings-in-lync-server-2013"></a><span data-ttu-id="80059-102">Modificar la configuración de la calidad de la experiencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="80059-102">Modify Quality of Experience settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80059-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="80059-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="80059-p101">De forma predeterminada, los datos de calidad de la experiencia (QoE) se depuran una vez transcurridos 60 días. Puede usar la configuración de la página **Datos de calidad de la experiencia** para conservar los datos durante un periodo de tiempo mayor o menor. Si deshabilita QoE, los datos que se recopilaron antes de que se habilitara se someterán también a la depuración.</span><span class="sxs-lookup"><span data-stu-id="80059-p101">By default, Quality of Experience (QoE) data is purged after 60 days. You can use the settings on the **Quality of Experience Data** page to retain the data for a longer or shorter period of time. If you disable QoE, data that was captured before QoE was enabled will also be subject to purging.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="80059-p102">Configure el registro detallado de llamadas (CDR) y QoE para que conserven los datos durante el mismo número de días. Cada llamada en los informes de detalles de llamadas (CDR), que se encuentra disponible en la página principal de los informes del servidor de supervisión, incluye la información del CDR y de la QoE. Si la duración de la depuración para los CDR y la QoE es diferente, es posible que algunas llamadas solo incluyan datos de CDR, mientras que otras solo incluirán datos de la QoE.</span><span class="sxs-lookup"><span data-stu-id="80059-p102">You should configure call detail recording (CDR) and QoE to retain data for the same number of days. Each call in the call detail reports (CDRs), available from the Monitoring Reports homepage, includes CDR and QoE information. If the purging duration for CDR and QoE is different, some calls may only include CDR data, while other may only include QoE data.</span></span>



</div>

<span data-ttu-id="80059-110">El procedimiento siguiente describe cómo establecer la configuración de la depuración para los datos de la QoE.</span><span class="sxs-lookup"><span data-stu-id="80059-110">The following procedure describes how to configure purge settings for QoE data.</span></span>

<div>

## <a name="to-specify-retention-of-qoe-data-by-using-lync-server-control-panel"></a><span data-ttu-id="80059-111">Para especificar la retención de datos de la calidad de la calidad mediante el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="80059-111">To specify retention of QoE data by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="80059-112">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="80059-112">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="80059-113">Para obtener más información, consulte [permisos de configuración de delegación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="80059-113">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="80059-114">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="80059-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="80059-115">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="80059-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="80059-116">En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, luego, en **Datos sobre la calidad de la experiencia**.</span><span class="sxs-lookup"><span data-stu-id="80059-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="80059-117">En la página **Datos sobre la calidad de la experiencia**, haga clic en el sitio apropiado de la tabla, haga clic en **Editar** y, luego, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="80059-117">On the **Quality of Experience Data** page, click the appropriate site from the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="80059-118">Para activar la depuración, seleccione **Habilitar depuración de QoE**.</span><span class="sxs-lookup"><span data-stu-id="80059-118">To turn on purging, select **Enable Purging of QoE**.</span></span>

6.  <span data-ttu-id="80059-119">En **Conservar QoE durante un máximo de (días)**, seleccione la cantidad máxima de días durante los que se necesitan conservar los datos de la QoE.</span><span class="sxs-lookup"><span data-stu-id="80059-119">In **Keep QoE for maximum duration (days)** select the maximum number of days that QoE data should be retained.</span></span>

7.  <span data-ttu-id="80059-120">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="80059-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="80059-121">Especificación de la retención de QoE mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="80059-121">Specifying QoE Retention by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="80059-122">Puede crear la configuración de retención de QoE mediante Windows PowerShell y el cmdlet **set-CsQoEConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="80059-122">You can create QoE retention settings by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="80059-123">Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="80059-123">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="80059-124">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="80059-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-specify-qoe-retention-for-a-specific-location"></a><span data-ttu-id="80059-125">Para especificar la retención de la QoE de una ubicación específica</span><span class="sxs-lookup"><span data-stu-id="80059-125">To specify QoE retention for a specific location</span></span>

  - <span data-ttu-id="80059-126">Este comando permite habilitar la depuración de datos de la QoE en el sitio de Redmond, así como configurar el sitio de manera que mantenga los datos de la QoE durante 20 días.</span><span class="sxs-lookup"><span data-stu-id="80059-126">This command enables purging of QoE data for the Redmond site, and configures the site to maintain QoE data for 20 days.</span></span>
    
        Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20

</div>

<div>

## <a name="to-specify-qoe-retention-for-multiple-locations"></a><span data-ttu-id="80059-127">Para especificar la retención de la QoE de varias ubicaciones</span><span class="sxs-lookup"><span data-stu-id="80059-127">To specify QoE retention for multiple locations</span></span>

  - <span data-ttu-id="80059-128">Este comando permite configurar la retención de todas las opciones de configuración de QoE que se usan en una organización.</span><span class="sxs-lookup"><span data-stu-id="80059-128">This command configures QoE retention for all the QoE configuration settings in use in an organization.</span></span>
    
        Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20 

</div>

<span data-ttu-id="80059-129">Para obtener más información, consulte el tema de ayuda para el cmdlet [set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="80059-129">For more information, see the help topic for the [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="80059-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="80059-130">See Also</span></span>


[<span data-ttu-id="80059-131">Implementación de la supervisión en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="80059-131">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

