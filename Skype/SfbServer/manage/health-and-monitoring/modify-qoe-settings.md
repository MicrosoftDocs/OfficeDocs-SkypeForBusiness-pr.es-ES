---
title: Modificar la configuración de calidad de la experiencia en Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
description: 'Resumen: Obtenga información sobre cómo especificar la retención de los datos de QoE en Skype para Business Server.'
ms.openlocfilehash: a456a2528b78242849f651209e70c98046ebe0c3
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21012669"
---
# <a name="modify-quality-of-experience-settings-in-skype-for-business-server"></a><span data-ttu-id="7f27b-103">Modificar la configuración de calidad de la experiencia en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="7f27b-103">Modify Quality of Experience settings in Skype for Business Server</span></span>
 
<span data-ttu-id="7f27b-104">**Resumen:** Obtenga información sobre cómo especificar la retención de los datos de QoE en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="7f27b-104">**Summary:** Learn how to specify retention of QoE data in Skype for Business Server.</span></span>
  
<span data-ttu-id="7f27b-p101">De forma predeterminada, los datos de calidad de la experiencia (QoE) se depuran una vez transcurridos 60 días. Puede usar la configuración de la página **Datos de calidad de la experiencia** para conservar los datos durante un periodo de tiempo mayor o menor. Si deshabilita QoE, los datos que se recopilaron antes de que se habilitara se someterán también a la depuración.</span><span class="sxs-lookup"><span data-stu-id="7f27b-p101">By default, Quality of Experience (QoE) data is purged after 60 days. You can use the settings on the **Quality of Experience Data** page to retain the data for a longer or shorter period of time. If you disable QoE, data that was captured before QoE was enabled will also be subject to purging.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7f27b-p102">Configure el registro detallado de llamadas (CDR) y QoE para que conserven los datos durante el mismo número de días. Cada llamada en los informes de detalles de llamadas (CDR), que se encuentra disponible en la página principal de los informes del servidor de supervisión, incluye la información del CDR y de la QoE. Si la duración de la depuración para los CDR y la QoE es diferente, es posible que algunas llamadas solo incluyan datos de CDR, mientras que otras solo incluirán datos de la QoE.</span><span class="sxs-lookup"><span data-stu-id="7f27b-p102">You should configure call detail recording (CDR) and QoE to retain data for the same number of days. Each call in the call detail reports (CDRs), available from the Monitoring Reports homepage, includes CDR and QoE information. If the purging duration for CDR and QoE is different, some calls may only include CDR data, while other may only include QoE data.</span></span> 
  
<span data-ttu-id="7f27b-111">El procedimiento siguiente describe cómo establecer la configuración de la depuración para los datos de la QoE.</span><span class="sxs-lookup"><span data-stu-id="7f27b-111">The following procedure describes how to configure purge settings for QoE data.</span></span> 
  
### <a name="to-specify-retention-of-qoe-data-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="7f27b-112">Para especificar la retención de los datos de QoE mediante el uso de Skype para el Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="7f27b-112">To specify retention of QoE data by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="7f27b-113">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como un miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="7f27b-113">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="7f27b-114">Para obtener información detallada, vea **Delegar permisos de instalación**.</span><span class="sxs-lookup"><span data-stu-id="7f27b-114">For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="7f27b-115">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="7f27b-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="7f27b-116">En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, luego, en **Datos sobre la calidad de la experiencia**.</span><span class="sxs-lookup"><span data-stu-id="7f27b-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>
    
4. <span data-ttu-id="7f27b-117">En la página **Datos sobre la calidad de la experiencia**, haga clic en el sitio apropiado de la tabla, haga clic en **Editar** y, luego, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="7f27b-117">On the **Quality of Experience Data** page, click the appropriate site from the table, click **Edit**, and then click **Show Details**.</span></span>
    
5. <span data-ttu-id="7f27b-118">Para activar la depuración, seleccione **Habilitar depuración de QoE**.</span><span class="sxs-lookup"><span data-stu-id="7f27b-118">To turn on purging, select **Enable Purging of QoE**.</span></span>
    
6. <span data-ttu-id="7f27b-119">En **Conservar QoE durante un máximo de (días)**, seleccione la cantidad máxima de días durante los que se necesitan conservar los datos de la QoE.</span><span class="sxs-lookup"><span data-stu-id="7f27b-119">In **Keep QoE for maximum duration (days)** select the maximum number of days that QoE data should be retained.</span></span>
    
7. <span data-ttu-id="7f27b-120">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="7f27b-120">Click **Commit**.</span></span>
    
## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="7f27b-121">Especificación de retención de la QoE mediante el uso de Cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7f27b-121">Specifying QoE Retention by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="7f27b-122">Puede crear la configuración de retención QoE mediante Windows PowerShell y el cmdlet **Set-CsQoEConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="7f27b-122">You can create QoE retention settings by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="7f27b-123">Se puede ejecutar este cmdlet, ya sea desde el Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7f27b-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="7f27b-124">Para obtener información detallada acerca del uso de Windows PowerShell remoto para conectarse a Skype para Business Server, vea el artículo del blog ["rápido iniciar: administración de Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="7f27b-124">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="7f27b-125">El proceso es el mismo en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="7f27b-125">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-specify-qoe-retention-for-a-specific-location"></a><span data-ttu-id="7f27b-126">Para especificar la retención de la QoE de una ubicación específica</span><span class="sxs-lookup"><span data-stu-id="7f27b-126">To specify QoE retention for a specific location</span></span>

- <span data-ttu-id="7f27b-127">Este comando permite habilitar la depuración de datos de la QoE en el sitio de Redmond, así como configurar el sitio de manera que mantenga los datos de la QoE durante 20 días.</span><span class="sxs-lookup"><span data-stu-id="7f27b-127">This command enables purging of QoE data for the Redmond site, and configures the site to maintain QoE data for 20 days.</span></span>
    
  ```
  Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20
  ```

### <a name="to-specify-qoe-retention-for-multiple-locations"></a><span data-ttu-id="7f27b-128">Para especificar la retención de la QoE de varias ubicaciones</span><span class="sxs-lookup"><span data-stu-id="7f27b-128">To specify QoE retention for multiple locations</span></span>

- <span data-ttu-id="7f27b-129">Este comando permite configurar la retención de todas las opciones de configuración de QoE que se usan en una organización.</span><span class="sxs-lookup"><span data-stu-id="7f27b-129">This command configures QoE retention for all the QoE configuration settings in use in an organization.</span></span>
    
  ```
  Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20 
  ```

<span data-ttu-id="7f27b-130">Para obtener más información, vea el tema de ayuda para el cmdlet [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="7f27b-130">For more information, see the help topic for the [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7f27b-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="7f27b-131">See also</span></span>

[<span data-ttu-id="7f27b-132">Implementación de la supervisión</span><span class="sxs-lookup"><span data-stu-id="7f27b-132">Deploying Monitoring</span></span>](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)