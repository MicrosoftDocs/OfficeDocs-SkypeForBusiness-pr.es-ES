---
title: Crear opciones de configuración de calidad de la experiencia en Skype Empresarial Server
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
ms.assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
description: 'Resumen: obtenga información sobre la configuración de calidad de la experiencia (QoE) en Skype Empresarial Server.'
ms.openlocfilehash: d1d0b299b5cf0bbaf3627b7c90f90e7e1d958d10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817000"
---
# <a name="create-quality-of-experience-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="327b0-103">Crear opciones de configuración de calidad de la experiencia en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="327b0-103">Create Quality of Experience configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="327b0-104">**Resumen:** Obtenga información sobre la configuración de calidad de la experiencia (QoE) en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="327b0-104">**Summary:** Learn about Quality of Experience (QoE) settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="327b0-p101">Las métricas de calidad de la experiencia (QoE) realizan un seguimiento de la calidad de las llamadas de audio y vídeo que se han efectuado en la organización, incluido el número de paquetes de red perdidos, el ruido de fondo y la cantidad de "vibración" (diferencias en el retraso de paquetes). Esta información se almacena en una base de datos independiente de otras estadísticas, como los registros de detalles de llamadas, lo que permite activar y desactivar las métricas QoE de manera independiente de otros datos registrados.</span><span class="sxs-lookup"><span data-stu-id="327b0-p101">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>
  
<span data-ttu-id="327b0-107">Al instalar Skype Empresarial Server, se crea una colección única y global de opciones de configuración de QoE.</span><span class="sxs-lookup"><span data-stu-id="327b0-107">When you install Skype for Business Server, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="327b0-108">Los administradores pueden también crear una configuración personalizada en el ámbito de sitio.</span><span class="sxs-lookup"><span data-stu-id="327b0-108">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="327b0-109">Cuando se usa esta configuración en el ámbito del sitio, predomina sobre la configuración global.</span><span class="sxs-lookup"><span data-stu-id="327b0-109">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="327b0-110">Por ejemplo, si crea configuraciones de ámbito de sitio para el sitio Redmond, dicha configuración (en lugar de la configuración global) se usará para administrar QoE en Redmond.</span><span class="sxs-lookup"><span data-stu-id="327b0-110">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage QoE in Redmond.</span></span>
  
<span data-ttu-id="327b0-111">Las opciones de configuración de QoE se pueden crear mediante el Panel de control de Skype Empresarial Server o el cmdlet [New-CsQoEConfiguration.](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="327b0-111">QoE configuration settings can be created by using either Skype for Business Server Control Panel or the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="327b0-112">Si usa el Panel de control de Skype Empresarial Server para crear una nueva configuración, estarán disponibles las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="327b0-112">If you are using Skype for Business Server Control Panel to create new settings the following options will be available to you:</span></span>
  
|<span data-ttu-id="327b0-113">**Configuración de la interfaz de usuario**</span><span class="sxs-lookup"><span data-stu-id="327b0-113">**UI setting**</span></span>|<span data-ttu-id="327b0-114">**Parámetro de PowerShell**</span><span class="sxs-lookup"><span data-stu-id="327b0-114">**PowerShell parameter**</span></span>|<span data-ttu-id="327b0-115">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="327b0-115">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="327b0-116">Nombre</span><span class="sxs-lookup"><span data-stu-id="327b0-116">Name</span></span>  <br/> |<span data-ttu-id="327b0-117">Identidad</span><span class="sxs-lookup"><span data-stu-id="327b0-117">Identity</span></span>  <br/> |<span data-ttu-id="327b0-118">Identificador único de la configuración que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="327b0-118">Unique identifier for the settings to be created.</span></span> <span data-ttu-id="327b0-119">Las opciones de configuración de QoE solo se pueden crear en el ámbito del sitio.</span><span class="sxs-lookup"><span data-stu-id="327b0-119">QoE configuration settings can only be created at the site scope.</span></span>  <br/> |
|<span data-ttu-id="327b0-120">Habilitar la supervisión de datos de QoE</span><span class="sxs-lookup"><span data-stu-id="327b0-120">Enable monitoring of QoE data</span></span>  <br/> |<span data-ttu-id="327b0-121">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="327b0-121">EnableQoE</span></span>  <br/> |<span data-ttu-id="327b0-122">Especifica si los registros QoE se recopilarán y guardarán en la base de datos de supervisión.</span><span class="sxs-lookup"><span data-stu-id="327b0-122">Specifies whether QoE records will be collected and saved to the monitoring database.</span></span>  <br/> |
|<span data-ttu-id="327b0-123">Habilitar la purga de datos de QoE</span><span class="sxs-lookup"><span data-stu-id="327b0-123">Enable purging of QoE data</span></span>  <br/> |<span data-ttu-id="327b0-124">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="327b0-124">EnablePurging</span></span>  <br/> |<span data-ttu-id="327b0-125">Especifica si los registros se purgarán después de que transcurra la duración definida en los datos de **Keep QoE** para una propiedad de duración máxima (días).</span><span class="sxs-lookup"><span data-stu-id="327b0-125">Specifies whether records will be purged after the duration defined in the **Keep QoE data for a maximum duration (days)** property has elapsed.</span></span> <br/> |
|<span data-ttu-id="327b0-126">Conservar los datos de QoE durante un máximo de (días)</span><span class="sxs-lookup"><span data-stu-id="327b0-126">Keep QoE data for maximum duration (days)</span></span>  <br/> |<span data-ttu-id="327b0-127">KeepQoEDataForDays</span><span class="sxs-lookup"><span data-stu-id="327b0-127">KeepQoEDataForDays</span></span>  <br/> |<span data-ttu-id="327b0-128">Número de días que se almacenarán los datos de QoE antes de ser purgados de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="327b0-128">Number of days QoE data will be stored before being purged from the database.</span></span> <span data-ttu-id="327b0-129">Este valor se omite si la purga está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="327b0-129">This value is ignored if purging is disabled.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="327b0-130">El cmdlet New-CsQoEConfiguration incluye opciones adicionales no disponibles en el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="327b0-130">The New-CsQoEConfiguration cmdlet includes additional options not available in Skype for Business Server Control Panel.</span></span> <span data-ttu-id="327b0-131">Para obtener más información, consulte el tema de ayuda [New-CsQoEConfiguration.](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="327b0-131">For more information, see the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) help topic.</span></span>
  
### <a name="to-create-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="327b0-132">Para crear opciones de configuración de QoE mediante el Panel de control de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="327b0-132">To create QoE configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="327b0-p107">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins, o como miembro del rol CsVoiceAdministrator, CsServerAdministrator, o CsAdministrator. Para obtener información detallada, consulte **Delegación de permisos de instalación**.</span><span class="sxs-lookup"><span data-stu-id="327b0-p107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role. For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="327b0-135">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="327b0-135">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="327b0-136">En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, a continuación, en **Datos sobre la calidad de la experiencia**.</span><span class="sxs-lookup"><span data-stu-id="327b0-136">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>
    
4. <span data-ttu-id="327b0-137">En la **página Datos de calidad de** la experiencia, haga clic en **Nuevo.**</span><span class="sxs-lookup"><span data-stu-id="327b0-137">On the **Quality of Experience Data** page, click **New**.</span></span>
    
5. <span data-ttu-id="327b0-138">En **Seleccionar un sitio,** haga clic en el sitio al que se va a aplicar la directiva y haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="327b0-138">In **Select a Site**, click the site to which the policy is to be applied, and click **OK**.</span></span>
    
6. <span data-ttu-id="327b0-139">En **Nueva configuración de calidad de la experiencia,** haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="327b0-139">In **New Quality of Experience Setting**, do the following:</span></span>
    
   - <span data-ttu-id="327b0-140">Seleccione **Habilitar supervisión de datos de QoE** para activar la supervisión.</span><span class="sxs-lookup"><span data-stu-id="327b0-140">Select **Enable monitoring of QoE data** to turn on monitoring.</span></span>
    
   - <span data-ttu-id="327b0-141">Seleccione **Habilitar purgado de datos de QoE** para activar la depuración.</span><span class="sxs-lookup"><span data-stu-id="327b0-141">Select **Enable purging of QoE data** to turn on purging.</span></span>
    
   - <span data-ttu-id="327b0-142">En **Conservar QoE durante un máximo de (días),** seleccione el número máximo de días que deben conservarse los registros de QoE.</span><span class="sxs-lookup"><span data-stu-id="327b0-142">In **Keep QoE for maximum duration (days)**, select the maximum number of days that QoE records should be retained.</span></span>
    
7. <span data-ttu-id="327b0-143">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="327b0-143">Click **Commit**.</span></span>
    
## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="327b0-144">Creación de opciones de configuración de QoE mediante Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="327b0-144">Creating QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="327b0-145">Puede crear opciones de configuración de QoE con Windows PowerShell y el cmdlet New-CsQoEConfiguration configuración.</span><span class="sxs-lookup"><span data-stu-id="327b0-145">You can create QoE configuration settings by using Windows PowerShell and the New-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="327b0-146">Puede ejecutar este cmdlet desde el Shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="327b0-146">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="327b0-147">Para obtener más información sobre el uso de Windows PowerShell remoto para conectarse a Skype Empresarial Server, consulte el artículo del blog "Inicio rápido: administración de [Microsoft Lync Server 2010 con PowerShell remoto".](https://go.microsoft.com/fwlink/p/?linkId=255876)</span><span class="sxs-lookup"><span data-stu-id="327b0-147">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="327b0-148">El proceso es el mismo en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="327b0-148">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="327b0-149">Para crear una nueva recopilación de opciones de configuración de QoE</span><span class="sxs-lookup"><span data-stu-id="327b0-149">To create a new collection of QoE configuration settings</span></span>

 <span data-ttu-id="327b0-150">Este comando crea una nueva recopilación de opciones de configuración de QoE aplicadas al sitio Redmond:</span><span class="sxs-lookup"><span data-stu-id="327b0-150">This command creates a new collection of QoE configuration settings applied to the Redmond site:</span></span>
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="327b0-151">Para crear una nueva recopilación de opciones de configuración de QoE en las que la supervisión de QoE está deshabilitada</span><span class="sxs-lookup"><span data-stu-id="327b0-151">To create a new collection of QoE configuration settings where QoE monitoring is disabled</span></span>

 <span data-ttu-id="327b0-152">Dado que, en el comando anterior, no se especificaron parámetros (además del parámetro de identidad obligatorio), la nueva colección de valores de configuración usará los valores predeterminados para todas sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="327b0-152">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span> <span data-ttu-id="327b0-153">Para crear una configuración que use otros valores de propiedad, basta con incluir el parámetro y el valor correspondiente adecuados.</span><span class="sxs-lookup"><span data-stu-id="327b0-153">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="327b0-154">Por ejemplo, para crear una colección de opciones de configuración de calidad de la experiencia que, de forma predeterminada, permita deshabilitar la grabación de QoE, use un comando como este:</span><span class="sxs-lookup"><span data-stu-id="327b0-154">For example, to create a collection of Quality of Experience configuration settings that, by default, allow disable QoE recording use a command like this:</span></span>
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="327b0-155">Para especificar varios valores de propiedad al crear una nueva colección de opciones de configuración de QoE</span><span class="sxs-lookup"><span data-stu-id="327b0-155">To specify multiple property values when creating a new collection of QoE configuration settings</span></span>

 <span data-ttu-id="327b0-156">Puede incluir varios parámetros para varios valores de propiedad.</span><span class="sxs-lookup"><span data-stu-id="327b0-156">You can multiple property values by including multiple parameters.</span></span> <span data-ttu-id="327b0-157">Por ejemplo, este comando configura las nuevas opciones para conservar los datos de QoE durante 30 días y purgar los datos antiguos a las 3:00 a.m.:</span><span class="sxs-lookup"><span data-stu-id="327b0-157">For example, this command configures the new settings to keep QoE data for 30 days and to purge old data at 3:00 AM:</span></span>
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3
  ```

<span data-ttu-id="327b0-158">Para obtener más información, consulte el tema de ayuda del cmdlet [New-CsQoEConfiguration.](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="327b0-158">For more information, see the help topic for the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) cmdlet.</span></span>
  

