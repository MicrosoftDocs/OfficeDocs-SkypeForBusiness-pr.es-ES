---
title: Eliminar la calidad de la configuración de la experiencia en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
description: 'Resumen: Aprenda a eliminar la configuración de la calidad de la experiencia (QoE) en Skype empresarial Server.'
ms.openlocfilehash: 4b521afd85a97550b27f320b9e49c5439e431681
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305804"
---
# <a name="delete-quality-of-experience-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="043f2-103">Eliminar la calidad de la configuración de la experiencia en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="043f2-103">Delete Quality of Experience configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="043f2-104">**Resumen:** Aprenda a eliminar la configuración de la calidad de la experiencia (QoE) en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="043f2-104">**Summary:** Learn how to delete Quality of Experience (QoE) settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="043f2-p101">Las métricas de calidad de la experiencia (QoE) realizan un seguimiento de la calidad de las llamadas de audio y vídeo que se han efectuado en la organización, incluido la cantidad de paquetes de red perdidos, el ruido de fondo y la cantidad de "vibración" (diferencias en el retraso de paquetes). Esta información se almacena en una base de datos independiente de otras estadísticas, como los registros de detalles de llamadas, lo que permite activar y desactivar las métricas QoE de manera independiente de otros datos registrados.</span><span class="sxs-lookup"><span data-stu-id="043f2-p101">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>
  
<span data-ttu-id="043f2-107">Al instalar Skype empresarial Server, se crea una única colección global de parámetros de configuración de QoE para usted.</span><span class="sxs-lookup"><span data-stu-id="043f2-107">When you install Skype for Business Server, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="043f2-108">Los administradores tienen la opción de crear conjuntos personalizados de configuraciones que se podrán aplicar a sitios individuales.</span><span class="sxs-lookup"><span data-stu-id="043f2-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="043f2-109">De forma predeterminada, las opciones configuradas en el ámbito de sitio tienen prioridad sobre las opciones de ámbito global.</span><span class="sxs-lookup"><span data-stu-id="043f2-109">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="043f2-110">Si se elimina la configuración de sitio, la QoE se gestionará en ese sitio por medio de la configuración global.</span><span class="sxs-lookup"><span data-stu-id="043f2-110">If you delete site-scoped settings, then QoE will be managed in that site by using the global settings.</span></span>
  
<span data-ttu-id="043f2-111">Tenga en cuenta que también puede "eliminar" la configuración global.</span><span class="sxs-lookup"><span data-stu-id="043f2-111">Note that you can also "delete" the global settings.</span></span> <span data-ttu-id="043f2-112">Pero, esta no se quitará realmente.</span><span class="sxs-lookup"><span data-stu-id="043f2-112">However, the global settings will not actually be removed.</span></span> <span data-ttu-id="043f2-113">En su lugar, todas las propiedades de dicha colección se restablecerán a sus valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="043f2-113">Instead, all the properties in that collection will be reset to their default values.</span></span> <span data-ttu-id="043f2-114">Por ejemplo, de forma predeterminada, la purga está habilitada en una colección de parámetros de configuración de QoE.</span><span class="sxs-lookup"><span data-stu-id="043f2-114">For example, by default purging is enabled in a collection of QoE configuration settings.</span></span> <span data-ttu-id="043f2-115">Supongamos que modifica la colección global y la purga se deshabilita.</span><span class="sxs-lookup"><span data-stu-id="043f2-115">Suppose you modify the global collection so that purging is disabled.</span></span> <span data-ttu-id="043f2-116">Si más adelante elimina la configuración global, todas las propiedades se restablecerán a sus valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="043f2-116">If you later delete the global settings, all the properties will be reset to their default values.</span></span> <span data-ttu-id="043f2-117">En este caso, eso significa que la purga volverá a estar habilitada.</span><span class="sxs-lookup"><span data-stu-id="043f2-117">In this case, that means that purging will once again be enabled.</span></span>
  
<span data-ttu-id="043f2-118">Puede quitar las opciones de configuración de la calidad de servicio con el panel de control de Skype empresarial o mediante el cmdlet [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="043f2-118">You can remove QoE configuration settings by using the Skype for Business Server Control Panel or by using the [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-delete-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="043f2-119">Para eliminar la configuración de QoE con el panel de control de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="043f2-119">To delete QoE configuration settings by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="043f2-p104">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para más información, consulte **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="043f2-p104">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role. For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="043f2-122">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="043f2-122">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="043f2-123">En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, luego, en **Datos sobre la calidad de la experiencia**.</span><span class="sxs-lookup"><span data-stu-id="043f2-123">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>
    
4. <span data-ttu-id="043f2-124">En la página **Datos de calidad de la experiencia**, haga clic en la directiva que desee, haga clic en **Editar** y, luego, en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="043f2-124">On the **Quality of Experience Data** page, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="043f2-125">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="043f2-125">Click **OK**.</span></span>
    
## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="043f2-126">Quitar las opciones de configuración de QoE mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="043f2-126">Removing QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="043f2-127">Puede eliminar la configuración de la configuración de la calidad de usuario mediante Windows PowerShell y el cmdlet **Remove-CsQoEConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="043f2-127">You can delete QoE configuration settings by using Windows PowerShell and the **Remove-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="043f2-128">Puede ejecutar este cmdlet desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="043f2-128">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="043f2-129">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Skype empresarial Server, consulte el artículo del blog ["Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="043f2-129">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="043f2-130">El proceso es el mismo en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="043f2-130">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a><span data-ttu-id="043f2-131">Para quitar un conjunto concreto de configuraciones de QoE</span><span class="sxs-lookup"><span data-stu-id="043f2-131">To remove a specified collection of QoE configuration settings</span></span>

 <span data-ttu-id="043f2-132">Este comando quita la configuración de QoE aplicada al sitio Redmond:</span><span class="sxs-lookup"><span data-stu-id="043f2-132">This command removes the QoE configuration settings applied to the Redmond site:</span></span>
    
  ```
  Remove-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="043f2-133">Para quitar todas las opciones de configuración de QoE aplicadas al ámbito de sitio</span><span class="sxs-lookup"><span data-stu-id="043f2-133">To remove all of the QoE configuration settings applied to the site scope</span></span>

 <span data-ttu-id="043f2-134">Este comando quita todas las opciones de configuración de QoE aplicadas al ámbito de sitio:</span><span class="sxs-lookup"><span data-stu-id="043f2-134">This command removes all the QoE configuration settings applied to the site scope:</span></span>
    
  ```
  Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="043f2-135">Para quitar todas las opciones de configuración de QoE en las que se ha deshabilitado la supervisión de QoE</span><span class="sxs-lookup"><span data-stu-id="043f2-135">To remove all of the QoE configuration settings where QoE monitoring is disabled</span></span>

 <span data-ttu-id="043f2-136">Este comando quita todas las opciones de configuración de QoE donde se ha deshabilitado la supervisión de QoE:</span><span class="sxs-lookup"><span data-stu-id="043f2-136">This command removes all the QoE configuration settings where QoE monitoring has been disabled:</span></span>
    
  ```
  Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration
  ```

<span data-ttu-id="043f2-137">Para obtener más información, consulte [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="043f2-137">For details, see [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="043f2-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="043f2-138">See also</span></span>

[<span data-ttu-id="043f2-139">Purgar manualmente las bases de datos de grabación de detalles de llamadas y de calidad de la experiencia en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="043f2-139">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server</span></span>](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

