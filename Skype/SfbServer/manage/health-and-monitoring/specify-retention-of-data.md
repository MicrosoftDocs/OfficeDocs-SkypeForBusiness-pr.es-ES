---
title: Especificar la retención de datos de CDR en Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
description: 'Resumen: Obtenga información sobre cómo administrar los detalles de llamadas (CDR) datos de Skype para Business Server.'
ms.openlocfilehash: 72fbb679a260462086930fc0457b5c748447cc29
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878748"
---
# <a name="specify-retention-of-cdr-data-in-skype-for-business-server"></a><span data-ttu-id="62d3d-103">Especificar la retención de datos de CDR en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="62d3d-103">Specify retention of CDR data in Skype for Business Server</span></span>
 
<span data-ttu-id="62d3d-104">**Resumen:** Obtenga información sobre cómo administrar los detalles de llamadas (CDR) datos de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="62d3d-104">**Summary:** Learn how to manage call detail recording (CDR) data for Skype for Business Server.</span></span>
  
<span data-ttu-id="62d3d-p101">De forma predeterminada, los datos del registro detallado de llamadas (CDR) se purgan una vez transcurridos 60 días. Puede usar la configuración de la página **Registro detallado de llamadas** para conservar los datos durante un periodo de tiempo mayor o menor. Si deshabilita CDR, los datos que se recopilaron antes de habilitarlo también se someterán a la purga.</span><span class="sxs-lookup"><span data-stu-id="62d3d-p101">By default, call detail recording (CDR) data is purged after 60 days. You can use the settings on the **Call Detail Recording** page to retain the data for a longer or shorter period of time. If you disable CDR, data that was captured before CDR was enabled will also be subject to purging.</span></span>
  
> [!NOTE]
> <span data-ttu-id="62d3d-p102">Configure CDR y la calidad de la experiencia (QoE) para que conserven los datos durante el mismo número de días. Cada llamada de CDR, que se encuentra disponible en la página web Informes del Servidor de supervisión, incluye la información de QoE y CDR. Si la duración de la purga es diferente para CDR y QoE, es posible que algunas llamadas solo incluyan datos de CDR y otras solo de QoE.</span><span class="sxs-lookup"><span data-stu-id="62d3d-p102">You should configure CDR and Quality of Experience (QoE) to retain data for the same number of days. Each call in the call detail reports (CDRs), available from the Monitoring Server Reports webpage, includes CDR and QoE information. If the purging duration for CDR and QoE is different, some calls might only include CDR data, while other may only include QoE data.</span></span> 
  
<span data-ttu-id="62d3d-111">Use los procedimientos siguientes para configurar la purga de los datos de CDR.</span><span class="sxs-lookup"><span data-stu-id="62d3d-111">Use the following procedures to configure purge settings for CDR data.</span></span> 
  
### <a name="to-specify-retention-of-cdr-data"></a><span data-ttu-id="62d3d-112">Para especificar la retención de los datos de CDR</span><span class="sxs-lookup"><span data-stu-id="62d3d-112">To specify retention of CDR data</span></span>

1. <span data-ttu-id="62d3d-113">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tiene derechos de usuario equivalentes), o asignados a la función CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que implementa Skype para Business Server .</span><span class="sxs-lookup"><span data-stu-id="62d3d-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="62d3d-114">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="62d3d-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="62d3d-115">En la barra de navegación de la izquierda, haga clic en **Supervisión y archivado** y en **Registro de detallado de llamadas**.</span><span class="sxs-lookup"><span data-stu-id="62d3d-115">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>
    
4. <span data-ttu-id="62d3d-116">En la página **Registro detallado de llamadas**, haga clic en el sitio apropiado de la tabla, en **Editar** y en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="62d3d-116">On the **Call Detail Recording** page, click the appropriate site in the table, click **Edit**, and then click **Show Details**.</span></span>
    
5. <span data-ttu-id="62d3d-117">Para activar la purga, seleccione **Habilitar depuración de registros de detalles de llamadas (CDR)**.</span><span class="sxs-lookup"><span data-stu-id="62d3d-117">To turn on purging, select **Enable purging of CDRs**.</span></span>
    
6. <span data-ttu-id="62d3d-118">En **Conservar registros de detalles de llamadas durante un máximo de (días):**, seleccione el número máximo de días que desea retener los registros detallados de llamadas.</span><span class="sxs-lookup"><span data-stu-id="62d3d-118">In **Keep CDRs for maximum duration (days):** select the maximum number of days that call detail recordings should be retained.</span></span>
    
7. <span data-ttu-id="62d3d-119">En **Conservar los datos de los informes de errores durante el período de duración máximo (días):**, seleccione el número máximo de días que desea retener los registros de error.</span><span class="sxs-lookup"><span data-stu-id="62d3d-119">In **Keep error report data for maximum duration (days):** select the maximum number of days that error reports should be retained.</span></span>
    
8. <span data-ttu-id="62d3d-120">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="62d3d-120">Click **Commit**.</span></span>
    
## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="62d3d-121">Especificación de retención de CDR mediante el uso de cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="62d3d-121">Specifying CDR retention by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="62d3d-122">Puede crear la configuración de retención de CDR mediante el uso de Windows PowerShell y el cmdlet Set-CsCdrConfiguration.</span><span class="sxs-lookup"><span data-stu-id="62d3d-122">You can create CDR retention settings by using Windows PowerShell and the Set-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="62d3d-123">Se puede ejecutar este cmdlet, ya sea desde el Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="62d3d-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="62d3d-124">Para obtener información detallada acerca del uso de Windows PowerShell remoto para conectarse a Skype para Business Server, vea el artículo del blog ["rápido iniciar: administración de Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="62d3d-124">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="62d3d-125">El proceso es el mismo en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="62d3d-125">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-specify-cdr-retention-for-a-specific-location"></a><span data-ttu-id="62d3d-126">Para especificar la retención de CDR para una ubicación determinada:</span><span class="sxs-lookup"><span data-stu-id="62d3d-126">To specify CDR retention for a specific location</span></span>

- <span data-ttu-id="62d3d-127">Este comando habilita la purga de los datos de CDR para el sitio de Redmond y configura el sitio para conservar los datos de CDR y de los registros de errores durante 20 días.</span><span class="sxs-lookup"><span data-stu-id="62d3d-127">This command enables purging of CDR data for the Redmond site, and configures the site to maintain both CDR data and error reports data for 20 days.</span></span>
    
  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

### <a name="to-specify-cdr-retention-for-multiple-locations"></a><span data-ttu-id="62d3d-128">Para especificar la retención de CDR para varias ubicaciones:</span><span class="sxs-lookup"><span data-stu-id="62d3d-128">To specify CDR retention for multiple locations</span></span>

- <span data-ttu-id="62d3d-129">Este comando configura la retención de CDR para todos los valores de configuración de CDR que se usan en una organización.</span><span class="sxs-lookup"><span data-stu-id="62d3d-129">This command configures CDR retention for all the CDR configuration settings in use in an organization.</span></span>
    
  ```
  Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

<span data-ttu-id="62d3d-130">Para obtener más información, vea el tema de ayuda para el cmdlet [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="62d3d-130">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="62d3d-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="62d3d-131">See also</span></span>

[<span data-ttu-id="62d3d-132">Detalles de llamadas (CDR) en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="62d3d-132">Call detail recording (CDR) in Skype for Business Server</span></span>](call-detail-recording-cdr.md)
