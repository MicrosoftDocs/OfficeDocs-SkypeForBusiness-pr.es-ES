---
title: Crear una configuración de la calidad de la experiencia de configuración en Skype empresarial Server
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
ms.assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
description: 'Resumen: Obtenga información sobre la configuración de la calidad de la experiencia (QoE) en Skype empresarial Server.'
ms.openlocfilehash: 5366937f1faa01e6533b51677122713ee9e839fa
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818040"
---
# <a name="create-quality-of-experience-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="de6cb-103">Crear una configuración de la calidad de la experiencia de configuración en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="de6cb-103">Create Quality of Experience configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="de6cb-104">**Resumen:** Obtenga más información sobre la configuración de la calidad de la experiencia (QoE) en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="de6cb-104">**Summary:** Learn about Quality of Experience (QoE) settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="de6cb-p101">Las métricas de calidad de la experiencia (QoE) realizan un seguimiento de la calidad de las llamadas de audio y vídeo que se han efectuado en la organización, incluido la cantidad de paquetes de red perdidos, el ruido de fondo y la cantidad de "vibración" (diferencias en el retraso de paquetes). Esta información se almacena en una base de datos independiente de otras estadísticas, como los registros de detalles de llamadas, lo que permite activar y desactivar las métricas QoE de manera independiente de otros datos registrados.</span><span class="sxs-lookup"><span data-stu-id="de6cb-p101">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>
  
<span data-ttu-id="de6cb-107">Al instalar Skype empresarial Server, se crea una única colección global de parámetros de configuración de QoE para usted.</span><span class="sxs-lookup"><span data-stu-id="de6cb-107">When you install Skype for Business Server, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="de6cb-108">Los administradores también tienen la posibilidad de crear opciones personalizadas en el ámbito del sitio.</span><span class="sxs-lookup"><span data-stu-id="de6cb-108">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="de6cb-109">Cuando estas opciones de ámbito de sitio se usan, tienen prioridad frente a la configuración global.</span><span class="sxs-lookup"><span data-stu-id="de6cb-109">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="de6cb-110">Así, por ejemplo, si crea opciones de ámbito de sitio para el sitio de Redmond, serán las opciones que se usen (y no la configuración global) para administrar la calidad de la experiencia en Redmond.</span><span class="sxs-lookup"><span data-stu-id="de6cb-110">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage QoE in Redmond.</span></span>
  
<span data-ttu-id="de6cb-111">Las opciones de configuración de QoE se pueden crear con el panel de control de Skype empresarial Server o el cmdlet [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="de6cb-111">QoE configuration settings can be created by using either Skype for Business Server Control Panel or the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="de6cb-112">Si está usando el panel de control de Skype empresarial Server para crear nuevos ajustes, las siguientes opciones estarán disponibles:</span><span class="sxs-lookup"><span data-stu-id="de6cb-112">If you are using Skype for Business Server Control Panel to create new settings the following options will be available to you:</span></span>
  
|<span data-ttu-id="de6cb-113">**Valor de interfaz de usuario**</span><span class="sxs-lookup"><span data-stu-id="de6cb-113">**UI setting**</span></span>|<span data-ttu-id="de6cb-114">**Parámetro de PowerShell**</span><span class="sxs-lookup"><span data-stu-id="de6cb-114">**PowerShell parameter**</span></span>|<span data-ttu-id="de6cb-115">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="de6cb-115">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="de6cb-116">Nombre</span><span class="sxs-lookup"><span data-stu-id="de6cb-116">Name</span></span>  <br/> |<span data-ttu-id="de6cb-117">Identidad</span><span class="sxs-lookup"><span data-stu-id="de6cb-117">Identity</span></span>  <br/> |<span data-ttu-id="de6cb-p104">Identificador único de la opción que se va a crear. La opción de configuración de QoE solo se puede crear en el ámbito del sitio.</span><span class="sxs-lookup"><span data-stu-id="de6cb-p104">Unique identifier for the settings to be created. QoE configuration settings can only be created at the site scope.</span></span>  <br/> |
|<span data-ttu-id="de6cb-120">Habilitar supervisión de datos de calidad de la experiencia (QoE)</span><span class="sxs-lookup"><span data-stu-id="de6cb-120">Enable monitoring of QoE data</span></span>  <br/> |<span data-ttu-id="de6cb-121">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="de6cb-121">EnableQoE</span></span>  <br/> |<span data-ttu-id="de6cb-122">Especifica si los registros QoE se recopilarán y guardarán en la base de datos de supervisión.</span><span class="sxs-lookup"><span data-stu-id="de6cb-122">Specifies whether QoE records will be collected and saved to the monitoring database.</span></span>  <br/> |
|<span data-ttu-id="de6cb-123">Habilitar purgado de datos de calidad de la experiencia (QoE)</span><span class="sxs-lookup"><span data-stu-id="de6cb-123">Enable purging of QoE data</span></span>  <br/> |<span data-ttu-id="de6cb-124">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="de6cb-124">EnablePurging</span></span>  <br/> |<span data-ttu-id="de6cb-125">Especifica si los registros se van a purgar una vez transcurrida la duración definida en la propiedad **Conservar datos de QoE durante el período de duración máximo (días)**.</span><span class="sxs-lookup"><span data-stu-id="de6cb-125">Specifies whether records will be purged after the duration defined in the **Keep QoE data for a maximum duration (days)** property has elapsed.</span></span> <br/> |
|<span data-ttu-id="de6cb-126">Conservar datos de calidad de la experiencia (QoE) durante un máximo de (días)</span><span class="sxs-lookup"><span data-stu-id="de6cb-126">Keep QoE data for maximum duration (days)</span></span>  <br/> |<span data-ttu-id="de6cb-127">KeepQoEDataForDays</span><span class="sxs-lookup"><span data-stu-id="de6cb-127">KeepQoEDataForDays</span></span>  <br/> |<span data-ttu-id="de6cb-p105">Cantidad de días en que los datos de QoE se almacenarán antes de que se purguen de la base de datos. Este valor se ignora si el purgado está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="de6cb-p105">Number of days QoE data will be stored before being purged from the database. This value is ignored if purging is disabled.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="de6cb-130">El cmdlet New-CsQoEConfiguration incluye opciones adicionales que no están disponibles en el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="de6cb-130">The New-CsQoEConfiguration cmdlet includes additional options not available in Skype for Business Server Control Panel.</span></span> <span data-ttu-id="de6cb-131">Para obtener más información, vea el tema [de ayuda nuevo-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="de6cb-131">For more information, see the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) help topic.</span></span>
  
### <a name="to-create-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="de6cb-132">Para crear parámetros de configuración de QoE con el panel de control de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="de6cb-132">To create QoE configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="de6cb-p107">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para más información, consulte **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="de6cb-p107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role. For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="de6cb-135">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="de6cb-135">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="de6cb-136">En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, luego, en **Datos sobre la calidad de la experiencia**.</span><span class="sxs-lookup"><span data-stu-id="de6cb-136">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>
    
4. <span data-ttu-id="de6cb-137">En la página **Datos de calidad de la experiencia**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="de6cb-137">On the **Quality of Experience Data** page, click **New**.</span></span>
    
5. <span data-ttu-id="de6cb-138">En **Seleccionar un sitio**, haga clic en el sitio al que va a aplicar la directiva y, luego, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="de6cb-138">In **Select a Site**, click the site to which the policy is to be applied, and click **OK**.</span></span>
    
6. <span data-ttu-id="de6cb-139">En **Nueva configuración de calidad de la experiencia**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="de6cb-139">In **New Quality of Experience Setting**, do the following:</span></span>
    
   - <span data-ttu-id="de6cb-140">Seleccione **Habilitar supervisión de datos de calidad de la experiencia (QoE)** para activar la supervisión.</span><span class="sxs-lookup"><span data-stu-id="de6cb-140">Select **Enable monitoring of QoE data** to turn on monitoring.</span></span>
    
   - <span data-ttu-id="de6cb-141">Seleccione **Habilitar purgado de datos de calidad de la experiencia (QoE)** para activar el purgado.</span><span class="sxs-lookup"><span data-stu-id="de6cb-141">Select **Enable purging of QoE data** to turn on purging.</span></span>
    
   - <span data-ttu-id="de6cb-142">En **Conservar datos de calidad de la experiencia (QoE) durante un máximo de (días)**, seleccione la cantidad máxima de días durante la que se tienen que conservar los registros de QoE.</span><span class="sxs-lookup"><span data-stu-id="de6cb-142">In **Keep QoE for maximum duration (days)**, select the maximum number of days that QoE records should be retained.</span></span>
    
7. <span data-ttu-id="de6cb-143">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="de6cb-143">Click **Commit**.</span></span>
    
## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="de6cb-144">Creación de parámetros de configuración de QoE con cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="de6cb-144">Creating QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="de6cb-145">Puede crear parámetros de configuración de QoE mediante Windows PowerShell y el cmdlet New-CsQoEConfiguration.</span><span class="sxs-lookup"><span data-stu-id="de6cb-145">You can create QoE configuration settings by using Windows PowerShell and the New-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="de6cb-146">Puede ejecutar este cmdlet desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="de6cb-146">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="de6cb-147">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Skype empresarial Server, consulte el artículo del blog ["Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="de6cb-147">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="de6cb-148">El proceso es el mismo en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="de6cb-148">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="de6cb-149">Para crear una colección de opciones de configuración de QoE</span><span class="sxs-lookup"><span data-stu-id="de6cb-149">To create a new collection of QoE configuration settings</span></span>

 <span data-ttu-id="de6cb-150">Con este comando se crea una colección de opciones de configuración de QoE para usarla en el sitio de Redmond:</span><span class="sxs-lookup"><span data-stu-id="de6cb-150">This command creates a new collection of QoE configuration settings applied to the Redmond site:</span></span>
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="de6cb-151">Para crear una colección de opciones de configuración de QoE cuando la supervisión de QoE está deshabilitada</span><span class="sxs-lookup"><span data-stu-id="de6cb-151">To create a new collection of QoE configuration settings where QoE monitoring is disabled</span></span>

 <span data-ttu-id="de6cb-p109">Dado que en el comando anterior no se ha especificado ningún parámetro (aparte del obligado Identity), la nueva colección de opciones de configuración usará los valores predeterminados en todas sus propiedades. Para crear opciones que usen otros valores de propiedad, bastará con incluir el parámetro y los valores que sean adecuados. Por ejemplo, use un comando como el siguiente para crear una colección de opciones de configuración de calidad de la experiencia que permita deshabilitar el registro de QoE de forma predeterminada:</span><span class="sxs-lookup"><span data-stu-id="de6cb-p109">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties. To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of Quality of Experience configuration settings that, by default, allow disable QoE recording use a command like this:</span></span>
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="de6cb-155">Para especificar varios valores de propiedad al crear una colección de opciones de configuración de QoE</span><span class="sxs-lookup"><span data-stu-id="de6cb-155">To specify multiple property values when creating a new collection of QoE configuration settings</span></span>

 <span data-ttu-id="de6cb-p110">Si desea especificar varios valores de propiedad, es preciso incluir varios parámetros. Por ejemplo, con este comando se configuran nuevas opciones que permiten conservar los datos de QoE durante 30 días y purgar los datos antiguos a las 3:00 AM:</span><span class="sxs-lookup"><span data-stu-id="de6cb-p110">You can multiple property values by including multiple parameters. For example, this command configures the new settings to keep QoE data for 30 days and to purge old data at 3:00 AM:</span></span>
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3
  ```

<span data-ttu-id="de6cb-158">Para obtener más información, vea el tema de ayuda sobre el cmdlet [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="de6cb-158">For more information, see the help topic for the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) cmdlet.</span></span>
  

