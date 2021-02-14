---
title: Especificar la retención de datos de CDR en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
description: 'Resumen: obtenga información sobre cómo administrar los datos del registro detallado de llamadas (CDR) para Skype Empresarial Server.'
ms.openlocfilehash: 01b4765a9fa98a898255c1374115e17c4966e797
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814220"
---
# <a name="specify-retention-of-cdr-data-in-skype-for-business-server"></a><span data-ttu-id="144b3-103">Especificar la retención de datos de CDR en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="144b3-103">Specify retention of CDR data in Skype for Business Server</span></span>
 
<span data-ttu-id="144b3-104">**Resumen:** Obtenga información sobre cómo administrar los datos del registro detallado de llamadas (CDR) para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="144b3-104">**Summary:** Learn how to manage call detail recording (CDR) data for Skype for Business Server.</span></span>
  
<span data-ttu-id="144b3-p101">De forma predeterminada, los datos del registro detallado de llamadas (CDR) se purgan una vez transcurridos 60 días. Puede usar la configuración de la página **Registro detallado de llamadas** para conservar los datos durante un periodo de tiempo mayor o menor. Si deshabilita CDR, los datos que se recopilaron antes de habilitarlo también se someterán a la purga.</span><span class="sxs-lookup"><span data-stu-id="144b3-p101">By default, call detail recording (CDR) data is purged after 60 days. You can use the settings on the **Call Detail Recording** page to retain the data for a longer or shorter period of time. If you disable CDR, data that was captured before CDR was enabled will also be subject to purging.</span></span>
  
> [!NOTE]
> <span data-ttu-id="144b3-p102">Configure CDR y la calidad de la experiencia (QoE) para que conserven los datos durante el mismo número de días. Cada llamada de CDR, que se encuentra disponible en la página web Informes del Servidor de supervisión, incluye la información de QoE y CDR. Si la duración de la purga es diferente para CDR y QoE, es posible que algunas llamadas solo incluyan datos de CDR y otras solo de QoE.</span><span class="sxs-lookup"><span data-stu-id="144b3-p102">You should configure CDR and Quality of Experience (QoE) to retain data for the same number of days. Each call in the call detail reports (CDRs), available from the Monitoring Server Reports webpage, includes CDR and QoE information. If the purging duration for CDR and QoE is different, some calls might only include CDR data, while other may only include QoE data.</span></span> 
  
<span data-ttu-id="144b3-111">Use los procedimientos siguientes para configurar la purga de los datos de CDR.</span><span class="sxs-lookup"><span data-stu-id="144b3-111">Use the following procedures to configure purge settings for CDR data.</span></span> 
  
### <a name="to-specify-retention-of-cdr-data"></a><span data-ttu-id="144b3-112">Para especificar la retención de los datos de CDR:</span><span class="sxs-lookup"><span data-stu-id="144b3-112">To specify retention of CDR data</span></span>

1. <span data-ttu-id="144b3-113">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes) o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que implementó Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="144b3-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="144b3-114">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="144b3-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="144b3-115">En la barra de navegación de la izquierda, haga clic en **Supervisión y archivado** y en **Registro de detallado de llamadas**.</span><span class="sxs-lookup"><span data-stu-id="144b3-115">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>
    
4. <span data-ttu-id="144b3-116">En la página **Registro detallado de llamadas**, haga clic en el sitio apropiado de la tabla, en **Editar** y en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="144b3-116">On the **Call Detail Recording** page, click the appropriate site in the table, click **Edit**, and then click **Show Details**.</span></span>
    
5. <span data-ttu-id="144b3-117">Para activar la purga, seleccione **Habilitar depuración de registros de detalles de llamadas (CDR)**.</span><span class="sxs-lookup"><span data-stu-id="144b3-117">To turn on purging, select **Enable purging of CDRs**.</span></span>
    
6. <span data-ttu-id="144b3-118">En **Conservar registros de detalles de llamadas durante un máximo de (días):**, seleccione el número máximo de días que desea retener los registros detallados de llamadas.</span><span class="sxs-lookup"><span data-stu-id="144b3-118">In **Keep CDRs for maximum duration (days):** select the maximum number of days that call detail recordings should be retained.</span></span>
    
7. <span data-ttu-id="144b3-119">En **Conservar los datos de los informes de errores durante el período de duración máximo (días):**, seleccione el número máximo de días que desea retener los registros de error.</span><span class="sxs-lookup"><span data-stu-id="144b3-119">In **Keep error report data for maximum duration (days):** select the maximum number of days that error reports should be retained.</span></span>
    
8. <span data-ttu-id="144b3-120">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="144b3-120">Click **Commit**.</span></span>
    
## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="144b3-121">Especificación de la retención de CDR mediante Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="144b3-121">Specifying CDR retention by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="144b3-122">Puede definir la configuración de retención de CDR con Windows PowerShell y el cmdlet Set-CsCdrConfiguration.</span><span class="sxs-lookup"><span data-stu-id="144b3-122">You can create CDR retention settings by using Windows PowerShell and the Set-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="144b3-123">Puede ejecutar este cmdlet desde el Shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="144b3-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="144b3-124">Para obtener más información sobre el uso de Windows PowerShell remoto para conectarse a Skype Empresarial Server, consulte el artículo del blog "Inicio rápido: administración de [Microsoft Lync Server 2010 con PowerShell remoto".](https://go.microsoft.com/fwlink/p/?linkId=255876)</span><span class="sxs-lookup"><span data-stu-id="144b3-124">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="144b3-125">El proceso es el mismo en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="144b3-125">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-specify-cdr-retention-for-a-specific-location"></a><span data-ttu-id="144b3-126">Para especificar la retención de CDR para una ubicación determinada:</span><span class="sxs-lookup"><span data-stu-id="144b3-126">To specify CDR retention for a specific location</span></span>

- <span data-ttu-id="144b3-127">Este comando habilita la purga de los datos de CDR para el sitio de Redmond y configura el sitio para conservar los datos de CDR y de los registros de errores durante 20 días.</span><span class="sxs-lookup"><span data-stu-id="144b3-127">This command enables purging of CDR data for the Redmond site, and configures the site to maintain both CDR data and error reports data for 20 days.</span></span>
    
  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

### <a name="to-specify-cdr-retention-for-multiple-locations"></a><span data-ttu-id="144b3-128">Para especificar la retención de CDR para varias ubicaciones:</span><span class="sxs-lookup"><span data-stu-id="144b3-128">To specify CDR retention for multiple locations</span></span>

- <span data-ttu-id="144b3-129">Este comando configura la retención de CDR para todos los valores de configuración de CDR que se usan en una organización.</span><span class="sxs-lookup"><span data-stu-id="144b3-129">This command configures CDR retention for all the CDR configuration settings in use in an organization.</span></span>
    
  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

<span data-ttu-id="144b3-130">Para obtener más información, consulte el tema de ayuda del cmdlet [Set-CsCdrConfiguration.](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="144b3-130">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="144b3-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="144b3-131">See also</span></span>

[<span data-ttu-id="144b3-132">Registro detallado de llamadas (CDR) en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="144b3-132">Call detail recording (CDR) in Skype for Business Server</span></span>](call-detail-recording-cdr.md)
