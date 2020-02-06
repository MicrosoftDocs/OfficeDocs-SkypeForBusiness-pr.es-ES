---
title: Eliminar una colección existente de opciones de configuración de CDR en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
description: 'Resumen: Aprenda a quitar las opciones de configuración de CDR en Skype empresarial Server.'
ms.openlocfilehash: d9e990018d97f8e631f3a95718a76aa83d7d619e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818030"
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="8bdde-103">Eliminar una colección existente de opciones de configuración de CDR en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="8bdde-103">Delete an existing collection of CDR configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="8bdde-104">**Resumen:** Obtenga información sobre cómo quitar la configuración de CDR en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="8bdde-104">**Summary:** Learn how to remove CDR configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="8bdde-p101">El registro detallado de llamadas (CDR) permite realizar un seguimiento del uso de aspectos como las sesiones de mensajería instantánea de punto a punto, llamadas telefónicas de voz sobre IP (VoIP) y llamadas de conferencia. Estos datos de uso contienen información sobre quién llamó a quién, cuándo se realizó la llamada y su duración.</span><span class="sxs-lookup"><span data-stu-id="8bdde-p101">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>
  
<span data-ttu-id="8bdde-107">Al instalar Skype empresarial Server, se crea una única colección global de parámetros de configuración de CDR.</span><span class="sxs-lookup"><span data-stu-id="8bdde-107">When you install Skype for Business Server, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="8bdde-108">Los administradores tienen la opción de crear conjuntos personalizados de configuraciones que se podrán aplicar a sitios individuales.</span><span class="sxs-lookup"><span data-stu-id="8bdde-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="8bdde-109">Por diseño, las opciones configuradas en el ámbito del sitio tienen precedencia sobre las opciones configuradas en el ámbito global.</span><span class="sxs-lookup"><span data-stu-id="8bdde-109">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="8bdde-110">Si elimina la configuración con ámbito en el sitio, el CDR se puede administrar en dicho sitio utilizando la configuración global.</span><span class="sxs-lookup"><span data-stu-id="8bdde-110">If you delete site-scoped settings, then CDR will be managed in that site by using the global settings.</span></span>
  
<span data-ttu-id="8bdde-111">Tenga en cuenta que también puede "eliminar" la configuración global.</span><span class="sxs-lookup"><span data-stu-id="8bdde-111">Note that you can also "delete" the global settings.</span></span> <span data-ttu-id="8bdde-112">Pero, esta no se quitará realmente.</span><span class="sxs-lookup"><span data-stu-id="8bdde-112">However, the global settings will not actually be removed.</span></span> <span data-ttu-id="8bdde-113">En su lugar, todas las propiedades de dicha colección se restablecerán a sus valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="8bdde-113">Instead, all the properties in that collection will be reset to their default values.</span></span> <span data-ttu-id="8bdde-114">Por ejemplo, la purga está habilitada de forma predeterminada en una colección de opciones de configuración de CDR.</span><span class="sxs-lookup"><span data-stu-id="8bdde-114">For example, by default purging is enabled in a collection of CDR configuration settings.</span></span> <span data-ttu-id="8bdde-115">Supongamos que modifica la colección global y la purga se deshabilita.</span><span class="sxs-lookup"><span data-stu-id="8bdde-115">Suppose you modify the global collection so that purging is disabled.</span></span> <span data-ttu-id="8bdde-116">Si más adelante elimina la configuración global, todas las propiedades se restablecerán a sus valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="8bdde-116">If you later delete the global settings, all the properties will be reset to their default values.</span></span> <span data-ttu-id="8bdde-117">En este caso, eso significa que la purga volverá a estar habilitada.</span><span class="sxs-lookup"><span data-stu-id="8bdde-117">In this case, that means that purging will once again be enabled.</span></span>
  
<span data-ttu-id="8bdde-118">Puede quitar la configuración de CDR con el panel de control de Skype empresarial Server o el cmdlet [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="8bdde-118">You can remove CDR configuration settings by using the Skype for Business Server Control Panel or the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-remove-cdr-configuration-settings-with-skype-for-business-server-control-panel"></a><span data-ttu-id="8bdde-119">Para quitar la configuración de CDR con el panel de control de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="8bdde-119">To remove CDR configuration settings with Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="8bdde-120">En el panel de control de Skype empresarial Server, haga clic en **supervisión y archivado**.</span><span class="sxs-lookup"><span data-stu-id="8bdde-120">In Skype for Business Server Control Panel, click **Monitoring and Archiving**.</span></span> 
    
2. <span data-ttu-id="8bdde-p104">En la pestaña **Registro detallado de llamadas**, seleccione la colección o colecciones de opciones de CDR que se van a quitar. Para seleccionar varias colecciones, haga clic en la primera colección, mantenga presionada la tecla Control y haga clic en otras colecciones.</span><span class="sxs-lookup"><span data-stu-id="8bdde-p104">On the **Call Detail Recording** tab, select the collection (or collections) of CDR settings to be removed. To select multiple collections, click the first collection, hold down the Ctrl key, and click additional collections.</span></span>
    
3. <span data-ttu-id="8bdde-123">Haga clic en **Editar** y después en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="8bdde-123">Click **Edit**, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="8bdde-124">En el cuadro de diálogo panel de control de Skype empresarial Server, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8bdde-124">In the Skype for Business Server Control Panel dialog box, click **OK**.</span></span>
    
## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="8bdde-125">Quitar las opciones de configuración de CDR con cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8bdde-125">Removing CDR configuration settings by using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="8bdde-126">Puede eliminar la configuración de la configuración de la llamada registrar detalles mediante Windows PowerShell y el cmdlet **Remove-CsCdrConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="8bdde-126">You can delete call detail recording configuration settings by using Windows PowerShell and the **Remove-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="8bdde-127">Puede ejecutar este cmdlet desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8bdde-127">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="8bdde-128">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Skype empresarial Server, consulte el artículo del blog ["Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="8bdde-128">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="8bdde-129">El proceso es el mismo en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="8bdde-129">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a><span data-ttu-id="8bdde-130">Para quitar una colección especificada de opciones de configuración de CDR</span><span class="sxs-lookup"><span data-stu-id="8bdde-130">To remove a specified collection of CDR configuration settings</span></span>

 <span data-ttu-id="8bdde-131">Este comando quita las opciones de configuración de CDR que se aplican al sitio Redmond:</span><span class="sxs-lookup"><span data-stu-id="8bdde-131">This command removes the CDR configuration settings applied to the Redmond site:</span></span>
    
  ```PowerShell
  Remove-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="8bdde-132">Para quitar todas las opciones de configuración de CDR que se aplican al ámbito del sitio</span><span class="sxs-lookup"><span data-stu-id="8bdde-132">To remove all the CDR configuration settings applied to the site scope</span></span>

 <span data-ttu-id="8bdde-133">Este comando quita todas las opciones de configuración de CDR que se aplican al ámbito del sitio:</span><span class="sxs-lookup"><span data-stu-id="8bdde-133">This command removes all the CDR configuration settings applied to the site scope:</span></span>
    
  ```PowerShell
  Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration
  ```PowerShell

### To remove all the CDR configuration settings that disable call detail recording

 This command removes all the CDR configuration settings where Call Detail recording has been disabled:
    
  ```PowerShell
  Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration
  ```

<span data-ttu-id="8bdde-134">Para obtener más información, consulte el tema de ayuda para el cmdlet [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="8bdde-134">For more information, see the help topic for the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8bdde-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="8bdde-135">See also</span></span>

[<span data-ttu-id="8bdde-136">Purgar manualmente las bases de datos de grabación de detalles de llamadas y de calidad de la experiencia en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="8bdde-136">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server</span></span>](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

