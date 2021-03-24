---
title: Configurar la experiencia del cliente con Skype Empresarial 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 66867a96-ff00-497d-889c-2e908cc384ce
description: 'Summary: Read this topic to learn how to configure the client experience for Skype for Business users.'
ms.openlocfilehash: 1816ff9af6c8c6e28ca72420f843d224587b2c70
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096014"
---
# <a name="configure-the-client-experience-with-skype-for-business-2015"></a><span data-ttu-id="5abca-103">Configurar la experiencia del cliente con Skype Empresarial 2015</span><span class="sxs-lookup"><span data-stu-id="5abca-103">Configure the client experience with Skype for Business 2015</span></span>
 
<span data-ttu-id="5abca-104">**Resumen:** Lea este tema para obtener información sobre cómo configurar la experiencia de cliente para los usuarios de Skype Empresarial 2015.</span><span class="sxs-lookup"><span data-stu-id="5abca-104">**Summary:** Read this topic to learn how to configure the client experience for Skype for Business 2015 users.</span></span>
  
<span data-ttu-id="5abca-105">Skype Empresarial 2015 proporciona una nueva experiencia de usuario basada en la experiencia del producto de consumidor de Skype.</span><span class="sxs-lookup"><span data-stu-id="5abca-105">Skype for Business 2015 provides a new user experience that is based on the Skype consumer product experience.</span></span> <span data-ttu-id="5abca-106">Además de todas las características de Lync, Skype Empresarial proporciona nuevas características con controles simplificados e iconos conocidos.</span><span class="sxs-lookup"><span data-stu-id="5abca-106">In addition to all the features of Lync, Skype for Business provides new features with simplified controls and familiar icons.</span></span> <span data-ttu-id="5abca-107">Para obtener información detallada sobre la nueva experiencia del cliente, vea [Explorar Skype Empresarial](https://go.microsoft.com/fwlink/?LinkId=529022).</span><span class="sxs-lookup"><span data-stu-id="5abca-107">For detailed information about the new client experience, see [Explore Skype for Business](https://go.microsoft.com/fwlink/?LinkId=529022).</span></span>
  
<span data-ttu-id="5abca-108">Skype Empresarial Server admite la nueva experiencia de cliente de Skype Empresarial, así como la experiencia de cliente de Lync.</span><span class="sxs-lookup"><span data-stu-id="5abca-108">Skype for Business Server supports the new Skype for Business client experience as well as the Lync client experience.</span></span> <span data-ttu-id="5abca-109">Como administrador, puede elegir la experiencia de cliente preferida para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="5abca-109">As an administrator, you can choose the preferred client experience for your users.</span></span> <span data-ttu-id="5abca-110">Por ejemplo, es posible que desee implementar la experiencia de cliente de Lync hasta que los usuarios de su organización estén totalmente formados en la nueva experiencia de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="5abca-110">For example, you might want to deploy the Lync client experience until users in your organization are fully trained in the new Skype for Business experience.</span></span> <span data-ttu-id="5abca-111">O bien, si aún no ha actualizado todos los usuarios a Skype Empresarial Server, es posible que desee que todos los usuarios tengan la misma experiencia de cliente hasta que todos se actualicen al nuevo servidor.</span><span class="sxs-lookup"><span data-stu-id="5abca-111">Or, if you have not yet upgraded all users to Skype for Business Server, you might want all users to have the same client experience until all are upgraded to the new server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5abca-112">Si su organización tiene implementados Skype Empresarial Server y Lync Server, la experiencia del cliente predeterminada variará en función de las versiones del servidor y la configuración de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="5abca-112">If your organization has both Skype for Business Server and Lync Server deployed, the default client experience will differ depending on server versions and UI settings.</span></span> <span data-ttu-id="5abca-113">Cuando los usuarios inicien Skype Empresarial por primera vez, siempre verán la interfaz de usuario de Skype Empresarial, incluso si ha seleccionado la experiencia de cliente de Lync.</span><span class="sxs-lookup"><span data-stu-id="5abca-113">When users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience.</span></span> <span data-ttu-id="5abca-114">Después de varios minutos, se pide a los usuarios que cambien al modo Lync.</span><span class="sxs-lookup"><span data-stu-id="5abca-114">After several minutes, users are asked to switch to Lync mode.</span></span> <span data-ttu-id="5abca-115">Para obtener más información, vea **First launch client behavior** later in this topic.</span><span class="sxs-lookup"><span data-stu-id="5abca-115">For more information, see **First launch client behavior** later in this topic.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5abca-116">La experiencia de cliente de Lync 2013 no es una opción para las versiones de cliente de Skype Empresarial 2016 o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="5abca-116">The Lync 2013 client experience is not an option for Skype for Business 2016 client versions or later.</span></span> <span data-ttu-id="5abca-117">Antes de intentar configurar el entorno de cliente para que use el cliente de Lync 2013, compruebe la versión del cliente para asegurarse de que no comienza con el número 16; por ejemplo: 16.x.x.x.</span><span class="sxs-lookup"><span data-stu-id="5abca-117">Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span> 
  
## <a name="configure-the-client-experience"></a><span data-ttu-id="5abca-118">Configurar la experiencia del cliente</span><span class="sxs-lookup"><span data-stu-id="5abca-118">Configure the client experience</span></span>

<span data-ttu-id="5abca-119">Puede especificar la experiencia del cliente que verán los usuarios de su organización mediante el cmdlet **Set-CSClientPolicy** con el parámetro EnableSkypeUI:</span><span class="sxs-lookup"><span data-stu-id="5abca-119">You can specify the client experience the users in your organization will see by using the **Set-CSClientPolicy** cmdlet with the EnableSkypeUI parameter:</span></span>
  
```powershell
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

<span data-ttu-id="5abca-120">donde XdsIdentity hace referencia a la directiva global o a una directiva de sitio con nombre.</span><span class="sxs-lookup"><span data-stu-id="5abca-120">where XdsIdentity refers to the Global policy or a named site policy.</span></span>
  
<span data-ttu-id="5abca-121">El siguiente comando selecciona la experiencia de cliente de Skype Empresarial para todos los usuarios de la organización afectados por la directiva global (recuerde que las directivas específicas del sitio o del usuario invalidan la directiva global):</span><span class="sxs-lookup"><span data-stu-id="5abca-121">The following command selects the Skype for Business client experience for all users in your organization affected by the Global policy (remember, site or user-specific policies override the Global policy):</span></span> 
  
```powershell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

<span data-ttu-id="5abca-122">El siguiente comando selecciona la experiencia de cliente de Lync para todos los usuarios de la organización afectados por la directiva global:</span><span class="sxs-lookup"><span data-stu-id="5abca-122">The next command selects the Lync client experience for all users in your organization affected by the Global policy:</span></span>
  
```powershell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

<span data-ttu-id="5abca-123">El siguiente comando selecciona la experiencia del cliente de Skype Empresarial para todos los usuarios del sitio redmond:</span><span class="sxs-lookup"><span data-stu-id="5abca-123">The next command selects the Skype for Business client experience for all users within the Redmond site:</span></span>
  
```powershell
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

<span data-ttu-id="5abca-124">Si desea configurar la experiencia de cliente para usuarios específicos de la organización, puede crear una nueva directiva de usuario mediante el cmdlet **New-CsClientPolicy** y, a continuación, asignar la directiva a usuarios específicos mediante el cmdlet **Grant-CsClientPolicy.**</span><span class="sxs-lookup"><span data-stu-id="5abca-124">If you want to configure the client experience for specific users within your organization, you can create a new user policy by using the **New-CsClientPolicy** cmdlet, and then assign the policy to specific users by using the **Grant-CsClientPolicy** cmdlet.</span></span>
  
<span data-ttu-id="5abca-125">Por ejemplo, el siguiente comando crea una nueva directiva de cliente, SalesClientUI, que selecciona la experiencia de cliente de Skype Empresarial:</span><span class="sxs-lookup"><span data-stu-id="5abca-125">For example, the following command creates a new client policy, SalesClientUI, that selects the Skype for Business client experience:</span></span>
  
```powershell
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

<span data-ttu-id="5abca-126">El siguiente comando asigna la directiva, SalesClientUI, a todos los miembros del departamento de ventas:</span><span class="sxs-lookup"><span data-stu-id="5abca-126">The next command assigns the policy, SalesClientUI, to all members of the Sales department:</span></span>
  
```powershell
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a><span data-ttu-id="5abca-127">Comportamientos de cliente de primer inicio</span><span class="sxs-lookup"><span data-stu-id="5abca-127">First launch client behaviors</span></span>

<span data-ttu-id="5abca-128">De forma predeterminada, cuando los usuarios inician Skype Empresarial 2015 por primera vez, siempre verán la interfaz de usuario de Skype Empresarial, incluso si ha seleccionado la experiencia de cliente de Lync estableciendo el valor del parámetro EnableSkypeUI en $False como se describió anteriormente.</span><span class="sxs-lookup"><span data-stu-id="5abca-128">By default, when users launch Skype for Business 2015 for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the value of the EnableSkypeUI parameter to $False as described previously.</span></span> <span data-ttu-id="5abca-129">Después de varios minutos, se pedirá a los usuarios que cambien al modo Lync.</span><span class="sxs-lookup"><span data-stu-id="5abca-129">After several minutes, users will then be asked to switch to Lync mode.</span></span>
  
<span data-ttu-id="5abca-130">Si desea mostrar la interfaz de usuario de Lync cuando los usuarios inician el cliente de Skype Empresarial por primera vez, siga estos pasos antes de que el cliente se inicie por primera vez después de actualizarse:</span><span class="sxs-lookup"><span data-stu-id="5abca-130">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>
  
1. <span data-ttu-id="5abca-131">Confirme que el valor de está establecido en $False en la directiva que está usando como  `EnableSkypeUI` se describió anteriormente.</span><span class="sxs-lookup"><span data-stu-id="5abca-131">Confirm that the value of  `EnableSkypeUI` is set to $False in the policy you are using as described previously.</span></span>
    
2. <span data-ttu-id="5abca-132">Actualice el Registro del sistema en el equipo del usuario.</span><span class="sxs-lookup"><span data-stu-id="5abca-132">Update the system registry on the user's computer.</span></span> <span data-ttu-id="5abca-133">Debe hacerlo antes de que la primera vez que los usuarios inicien el cliente de Skype Empresarial y solo debe hacerlo una vez.</span><span class="sxs-lookup"><span data-stu-id="5abca-133">You should do this before the first time users launch the Skype for Business client, and you should do this only once.</span></span> <span data-ttu-id="5abca-134">Para obtener información sobre cómo crear un objeto de directiva de grupo para actualizar el Registro en un equipo unido a un dominio, vea la sección más adelante en el tema.</span><span class="sxs-lookup"><span data-stu-id="5abca-134">For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="5abca-135">En la **clave [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync],** cree un nuevo **valor Binario.**</span><span class="sxs-lookup"><span data-stu-id="5abca-135">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="5abca-136">El **nombre del valor** debe ser **EnableSkypeUI** y los datos **value** deben establecerse en **00 00 00 00**.</span><span class="sxs-lookup"><span data-stu-id="5abca-136">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="5abca-137">La clave debe tener el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="5abca-137">The key should look like the following:</span></span>
    
   <pre>
   [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
   "CanSharePptInCollab"=dword:00000001
   "CanShareOneNoteInCollab"=dword:00000001
   "CanAppShareInCollab"=dword:00000001
   "EnableSkypeUI"=hex:00,00,00,00
   </pre>

<span data-ttu-id="5abca-138">La interfaz de usuario de Lync se mostrará ahora cuando los usuarios inicien el cliente de Skype Empresarial por primera vez.</span><span class="sxs-lookup"><span data-stu-id="5abca-138">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="5abca-139">Controlar la presentación del tutorial de pantalla de bienvenida</span><span class="sxs-lookup"><span data-stu-id="5abca-139">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="5abca-140">Cuando los usuarios abren el cliente de Skype Empresarial, el comportamiento predeterminado es mostrar una pantalla de bienvenida que incluye 7 sugerencias rápidas que la mayoría de las  *personas piden*.</span><span class="sxs-lookup"><span data-stu-id="5abca-140">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes  *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="5abca-141">Puedes desactivar la presentación de la pantalla de bienvenida pero permitir que los usuarios accedan al tutorial agregando el siguiente valor del Registro en el equipo cliente:</span><span class="sxs-lookup"><span data-stu-id="5abca-141">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>
  
<span data-ttu-id="5abca-142">En la **clave [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync],** cree un nuevo **valor DWORD (32 bits).**</span><span class="sxs-lookup"><span data-stu-id="5abca-142">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="5abca-143">El **nombre del valor** debe ser **IsBasicTutorialSeenByUser** y los **datos value** deben establecerse en **1**.</span><span class="sxs-lookup"><span data-stu-id="5abca-143">The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>
  
<span data-ttu-id="5abca-144">La clave debe tener el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="5abca-144">The key should look like the following:</span></span>
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="5abca-145">Desactivar el tutorial de cliente</span><span class="sxs-lookup"><span data-stu-id="5abca-145">Turn off the client tutorial</span></span>

<span data-ttu-id="5abca-146">Si no desea que los usuarios puedan acceder al tutorial, puede desactivar el tutorial de cliente con el siguiente valor del Registro:</span><span class="sxs-lookup"><span data-stu-id="5abca-146">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>
  
<span data-ttu-id="5abca-147">En la **clave [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync],** cree un nuevo **valor DWORD (32 bits).**</span><span class="sxs-lookup"><span data-stu-id="5abca-147">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="5abca-148">El **nombre del valor** debe ser **TutorialFeatureEnabled** y los **datos value** deben establecerse en **0**.</span><span class="sxs-lookup"><span data-stu-id="5abca-148">The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>
  
<span data-ttu-id="5abca-149">Lync</span><span class="sxs-lookup"><span data-stu-id="5abca-149">Lync</span></span>
  
```console
"TutorialFeatureEnabled"=dword:00000000
```

<span data-ttu-id="5abca-150">Puede volver a activar el tutorial estableciendo los **datos de valor** en **1**.</span><span class="sxs-lookup"><span data-stu-id="5abca-150">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>
  
## <a name="default-client-behaviors"></a><span data-ttu-id="5abca-151">Comportamientos de cliente predeterminados</span><span class="sxs-lookup"><span data-stu-id="5abca-151">Default client behaviors</span></span>

<span data-ttu-id="5abca-152">Si su organización tiene implementados Skype Empresarial Server y Lync Server, la experiencia del cliente variará según las versiones del servidor y la configuración de la interfaz de usuario de Skype.</span><span class="sxs-lookup"><span data-stu-id="5abca-152">If your organization has both Skype for Business Server and Lync Server deployed, the client experience will differ depending on server versions and the Skype UI setting.</span></span> <span data-ttu-id="5abca-153">En la tabla siguiente se muestra la experiencia de cliente inicial basada en la versión del servidor y la configuración de la interfaz de usuario:</span><span class="sxs-lookup"><span data-stu-id="5abca-153">The following table shows the initial client experience based on server version and the UI setting:</span></span>
  

|<span data-ttu-id="5abca-154">**Versión del servidor**</span><span class="sxs-lookup"><span data-stu-id="5abca-154">**Server version**</span></span>|<span data-ttu-id="5abca-155">**Configuración de EnableSkypeUI**</span><span class="sxs-lookup"><span data-stu-id="5abca-155">**EnableSkypeUI setting**</span></span>|<span data-ttu-id="5abca-156">**Experiencia del cliente**</span><span class="sxs-lookup"><span data-stu-id="5abca-156">**Client experience**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5abca-157">Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="5abca-157">Skype for Business Server</span></span> |<span data-ttu-id="5abca-158">Predeterminado</span><span class="sxs-lookup"><span data-stu-id="5abca-158">Default</span></span>  <br/> |<span data-ttu-id="5abca-159">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="5abca-159">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="5abca-160">Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="5abca-160">Skype for Business Server</span></span>  |<span data-ttu-id="5abca-161">Verdadero</span><span class="sxs-lookup"><span data-stu-id="5abca-161">True</span></span>  <br/> |<span data-ttu-id="5abca-162">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="5abca-162">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="5abca-163">Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="5abca-163">Skype for Business Server</span></span>  |<span data-ttu-id="5abca-164">False</span><span class="sxs-lookup"><span data-stu-id="5abca-164">False</span></span>  <br/> |<span data-ttu-id="5abca-165">El usuario solicitó cambiar al modo Lync (el usuario puede cambiar a Skype Empresarial más adelante si cambia la configuración de la interfaz de usuario a $true)</span><span class="sxs-lookup"><span data-stu-id="5abca-165">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="5abca-166">Lync Server 2010 o Lync Server 2013 (con revisiones correctas)</span><span class="sxs-lookup"><span data-stu-id="5abca-166">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="5abca-167">Predeterminado</span><span class="sxs-lookup"><span data-stu-id="5abca-167">Default</span></span>  <br/> |<span data-ttu-id="5abca-168">El usuario solicitó cambiar al modo Lync (el usuario puede cambiar a Skype Empresarial más adelante si cambia la configuración de la interfaz de usuario a $true)</span><span class="sxs-lookup"><span data-stu-id="5abca-168">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="5abca-169">Lync Server 2010 o Lync Server 2013 (con revisiones correctas)</span><span class="sxs-lookup"><span data-stu-id="5abca-169">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="5abca-170">Verdadero</span><span class="sxs-lookup"><span data-stu-id="5abca-170">True</span></span>  <br/> |<span data-ttu-id="5abca-171">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="5abca-171">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="5abca-172">Lync Server 2010 o Lync Server 2013 (con revisiones correctas)</span><span class="sxs-lookup"><span data-stu-id="5abca-172">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="5abca-173">False</span><span class="sxs-lookup"><span data-stu-id="5abca-173">False</span></span>  <br/> |<span data-ttu-id="5abca-174">El usuario solicitó cambiar al modo Lync (el usuario puede cambiar a Skype Empresarial más adelante si cambia la configuración de la interfaz de usuario a $true)</span><span class="sxs-lookup"><span data-stu-id="5abca-174">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="5abca-175">Lync Server 2010 o Lync Server 2013 (sin revisiones)</span><span class="sxs-lookup"><span data-stu-id="5abca-175">Lync Server 2010 or Lync Server 2013 (without patches)</span></span>  <br/> |<span data-ttu-id="5abca-176">Predeterminado</span><span class="sxs-lookup"><span data-stu-id="5abca-176">Default</span></span>  <br/> |<span data-ttu-id="5abca-177">Usuario solicitado para cambiar al modo Lync (el usuario no puede cambiar a Skype Empresarial más adelante)</span><span class="sxs-lookup"><span data-stu-id="5abca-177">User asked to switch to Lync mode (user cannot switch to Skype for Business later)</span></span>  <br/> |
   
<span data-ttu-id="5abca-178">En la siguiente tabla se muestra la experiencia del cliente cuando el administrador cambia la configuración inicial de la experiencia de la interfaz de usuario de Skype:</span><span class="sxs-lookup"><span data-stu-id="5abca-178">The next table shows the client experience when the administrator changes the initial setting for the Skype UI experience:</span></span>
  

|<span data-ttu-id="5abca-179">**Versión del servidor**</span><span class="sxs-lookup"><span data-stu-id="5abca-179">**Server version**</span></span>|<span data-ttu-id="5abca-180">**Configuración de EnableSkypeUI**</span><span class="sxs-lookup"><span data-stu-id="5abca-180">**EnableSkypeUI setting**</span></span>|<span data-ttu-id="5abca-181">**Interfaz de usuario de cliente = Lync**</span><span class="sxs-lookup"><span data-stu-id="5abca-181">**Client UI = Lync**</span></span>|<span data-ttu-id="5abca-182">**Interfaz de usuario de cliente = Skype Empresarial**</span><span class="sxs-lookup"><span data-stu-id="5abca-182">**Client UI = Skype for Business**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5abca-183">Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="5abca-183">Skype for Business Server</span></span> |<span data-ttu-id="5abca-184">Verdadero</span><span class="sxs-lookup"><span data-stu-id="5abca-184">True</span></span>  <br/> |<span data-ttu-id="5abca-185">Usuario solicitado para cambiar a Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="5abca-185">User asked to switch to Skype for Business</span></span>  <br/> |<span data-ttu-id="5abca-186">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="5abca-186">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="5abca-187">Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="5abca-187">Skype for Business Server</span></span> |<span data-ttu-id="5abca-188">False</span><span class="sxs-lookup"><span data-stu-id="5abca-188">False</span></span>  <br/> |<span data-ttu-id="5abca-189">Modo Lync</span><span class="sxs-lookup"><span data-stu-id="5abca-189">Lync mode</span></span>  <br/> |<span data-ttu-id="5abca-190">Usuario solicitado para cambiar al modo Lync</span><span class="sxs-lookup"><span data-stu-id="5abca-190">User asked to switch to Lync mode</span></span>  <br/> |
|<span data-ttu-id="5abca-191">Lync Server 2010 o Lync Server 2013 (con revisiones correctas)</span><span class="sxs-lookup"><span data-stu-id="5abca-191">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="5abca-192">Verdadero</span><span class="sxs-lookup"><span data-stu-id="5abca-192">True</span></span>  <br/> |<span data-ttu-id="5abca-193">Usuario solicitado para cambiar a Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="5abca-193">User asked to switch to Skype for Business</span></span>  <br/> |<span data-ttu-id="5abca-194">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="5abca-194">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="5abca-195">Lync Server 2010 o Lync Server 2013 (con revisiones correctas)</span><span class="sxs-lookup"><span data-stu-id="5abca-195">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="5abca-196">False</span><span class="sxs-lookup"><span data-stu-id="5abca-196">False</span></span>  <br/> |<span data-ttu-id="5abca-197">Modo Lync</span><span class="sxs-lookup"><span data-stu-id="5abca-197">Lync mode</span></span>  <br/> |<span data-ttu-id="5abca-198">Usuario solicitado para cambiar al modo Lync</span><span class="sxs-lookup"><span data-stu-id="5abca-198">User asked to switch to Lync mode</span></span>  <br/> |
|<span data-ttu-id="5abca-199">Lync Server 2010 o Lync Server 2013 (sin revisiones)</span><span class="sxs-lookup"><span data-stu-id="5abca-199">Lync Server 2010 or Lync Server 2013 (without patches)</span></span>  <br/> |<span data-ttu-id="5abca-200">Predeterminado</span><span class="sxs-lookup"><span data-stu-id="5abca-200">Default</span></span>  <br/> |<span data-ttu-id="5abca-201">Modo Lync (no se puede cambiar a Skype Empresarial)</span><span class="sxs-lookup"><span data-stu-id="5abca-201">Lync mode (cannot switch to Skype for Business)</span></span>  <br/> |<span data-ttu-id="5abca-202">Modo Lync (no se puede cambiar a Skype Empresarial)</span><span class="sxs-lookup"><span data-stu-id="5abca-202">Lync mode (cannot switch to Skype for Business)</span></span>  <br/> |
   
<span data-ttu-id="5abca-203">Las versiones de revisión necesarias para administrar la configuración del cliente de Skype Empresarial son:</span><span class="sxs-lookup"><span data-stu-id="5abca-203">The patch versions required to manage the configuration of the Skype for Business client are:</span></span>
  
- <span data-ttu-id="5abca-204">Lync Server 2010: actualización acumulativa de febrero de 2015 (4.0.7577.710) para Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="5abca-204">Lync Server 2010 - February 2015 Cumulative Update (4.0.7577.710) for Lync Server 2010.</span></span> <span data-ttu-id="5abca-205">Para obtener información, vea [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)</span><span class="sxs-lookup"><span data-stu-id="5abca-205">For information, see [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)</span></span>
    
- <span data-ttu-id="5abca-206">Lync Server 2013: actualización acumulativa de diciembre de 2014 (5.0.8308.857) para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5abca-206">Lync Server 2013 - December 2014 Cumulative Update (5.0.8308.857) for Lync Server 2013.</span></span> <span data-ttu-id="5abca-207">Para obtener información, vea [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).</span><span class="sxs-lookup"><span data-stu-id="5abca-207">For information, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).</span></span>
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="5abca-208">Crear un objeto de directiva de grupo para modificar el Registro en un equipo unido a un dominio</span><span class="sxs-lookup"><span data-stu-id="5abca-208">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="5abca-209">La actualización del Registro para mostrar la experiencia del cliente lync la primera vez que un usuario inicia el cliente de Skype Empresarial 2015 debe realizarse solo una vez.</span><span class="sxs-lookup"><span data-stu-id="5abca-209">The registry update to display the Lync client experience the first time a user launches the Skype for Business 2015 client should be done only once.</span></span> <span data-ttu-id="5abca-210">Si usa un objeto de directiva de grupo (GPO) para actualizar el Registro, debe definir el objeto para crear un nuevo valor en lugar de actualizar los datos value.</span><span class="sxs-lookup"><span data-stu-id="5abca-210">If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data.</span></span> <span data-ttu-id="5abca-211">Cuando se aplica el GPO, si el nuevo valor no existe, el GPO lo creará y establecerá los datos value en 0.</span><span class="sxs-lookup"><span data-stu-id="5abca-211">When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span> 
  
<span data-ttu-id="5abca-212">En el siguiente procedimiento se describe cómo modificar el Registro para que se muestre la experiencia del cliente lync la primera vez que un usuario inicia el cliente de Skype Empresarial 2015.</span><span class="sxs-lookup"><span data-stu-id="5abca-212">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business 2015 client.</span></span> <span data-ttu-id="5abca-213">También puede usar este procedimiento para actualizar el Registro para deshabilitar el tutorial de pantalla de bienvenida como se describió anteriormente.</span><span class="sxs-lookup"><span data-stu-id="5abca-213">You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>
  
### <a name="to-create-the-gpo"></a><span data-ttu-id="5abca-214">Para crear el GPO</span><span class="sxs-lookup"><span data-stu-id="5abca-214">To create the GPO</span></span>

1. <span data-ttu-id="5abca-215">Inicie la consola **de administración de directivas de grupo**.</span><span class="sxs-lookup"><span data-stu-id="5abca-215">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="5abca-216">Para obtener información sobre cómo usar la Consola de administración de directivas de grupo, vea [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn265969(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="5abca-216">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn265969(v=ws.11)).</span></span>
    
2. <span data-ttu-id="5abca-217">Haga clic con el botón secundario **en el nodo Objetos de directiva de** grupo y seleccione **Nuevo** en el menú.</span><span class="sxs-lookup"><span data-stu-id="5abca-217">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>
    
3. <span data-ttu-id="5abca-218">En el cuadro de diálogo Nuevo **GPO,** escriba un nombre para el GPO, por ejemplo, MakeLyncDefaultUI y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5abca-218">In the **New GPO** dialog, enter a name for the GPO, for example,MakeLyncDefaultUI, and then click **OK**.</span></span>
    
4. <span data-ttu-id="5abca-219">Haga clic con el botón secundario en el nuevo GPO que acaba de crear y, a continuación, **seleccione Editar** en el menú.</span><span class="sxs-lookup"><span data-stu-id="5abca-219">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>
    
5. <span data-ttu-id="5abca-220">En el **Editor de administración de directivas de** grupo, expanda Configuración **de** usuario, **Expanda** Preferencias, Expanda Configuración de **Windows** y, a continuación, seleccione **el nodo** Registro.</span><span class="sxs-lookup"><span data-stu-id="5abca-220">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>
    
6. <span data-ttu-id="5abca-221">Haga clic con el botón secundario en **el nodo Registro** y, a continuación, seleccione Nuevo **elemento** del  >  **Registro**.</span><span class="sxs-lookup"><span data-stu-id="5abca-221">Right-click on the **Registry** node, and then select **New** > **Registry Item**.</span></span>
    
7. <span data-ttu-id="5abca-222">En el **cuadro de diálogo Nuevas propiedades del** Registro, actualice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5abca-222">On the **New Registry Properties** dialog, update the following:</span></span>
    
   |<span data-ttu-id="5abca-223">**Field**</span><span class="sxs-lookup"><span data-stu-id="5abca-223">**Field**</span></span>|<span data-ttu-id="5abca-224">**Valor para seleccionar o escribir**</span><span class="sxs-lookup"><span data-stu-id="5abca-224">**Value to select or enter**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="5abca-225">**Acción**</span><span class="sxs-lookup"><span data-stu-id="5abca-225">**Action**</span></span> <br/> |<span data-ttu-id="5abca-226">**Create**</span><span class="sxs-lookup"><span data-stu-id="5abca-226">**Create**</span></span> <br/> |
   |<span data-ttu-id="5abca-227">**Subárbol**</span><span class="sxs-lookup"><span data-stu-id="5abca-227">**Hive**</span></span> <br/> | <span data-ttu-id="5abca-228">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="5abca-228">HKEY_CURRENT_USER</span></span> <br/> |
   |<span data-ttu-id="5abca-229">**Ruta de acceso clave**</span><span class="sxs-lookup"><span data-stu-id="5abca-229">**Key Path**</span></span> <br/> |<span data-ttu-id="5abca-230">Software\Microsoft\Office\Lync</span><span class="sxs-lookup"><span data-stu-id="5abca-230">Software\Microsoft\Office\Lync</span></span>  <br/> |
   |<span data-ttu-id="5abca-231">**Nombre del valor**</span><span class="sxs-lookup"><span data-stu-id="5abca-231">**Value name**</span></span> <br/> |<span data-ttu-id="5abca-232">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="5abca-232">EnableSkypeUI</span></span>  <br/> |
   |<span data-ttu-id="5abca-233">**Tipo de valor**</span><span class="sxs-lookup"><span data-stu-id="5abca-233">**Value type**</span></span> <br/> |<span data-ttu-id="5abca-234">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="5abca-234">REG_BINARY</span></span>  <br/> |
   |<span data-ttu-id="5abca-235">**Value data**</span><span class="sxs-lookup"><span data-stu-id="5abca-235">**Value data**</span></span> <br/> |<span data-ttu-id="5abca-236">00000000</span><span class="sxs-lookup"><span data-stu-id="5abca-236">00000000</span></span>  <br/> |
   
8. <span data-ttu-id="5abca-237">Haga **clic en** Aceptar para guardar los cambios y, a continuación, cierre el GPO.</span><span class="sxs-lookup"><span data-stu-id="5abca-237">Click **OK** to save your changes, and then close the GPO.</span></span>
    
<span data-ttu-id="5abca-238">A continuación, deberá vincular el GPO que creó al grupo de usuarios a los que desea asignar la directiva, como una OU.</span><span class="sxs-lookup"><span data-stu-id="5abca-238">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>
  
### <a name="to-use-the-gpo-to-assign-the-policy"></a><span data-ttu-id="5abca-239">Para usar el GPO para asignar la directiva</span><span class="sxs-lookup"><span data-stu-id="5abca-239">To use the GPO to assign the policy</span></span>

1. <span data-ttu-id="5abca-240">En la Consola de administración de directivas de grupo, haga clic con el botón secundario en la OU a la que desea asignar la directiva y, a continuación, seleccione **Vincular a un GPO existente.**</span><span class="sxs-lookup"><span data-stu-id="5abca-240">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>
    
2. <span data-ttu-id="5abca-241">En el cuadro de diálogo Seleccionar **GPO,** seleccione el GPO que creó y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5abca-241">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>
    
3. <span data-ttu-id="5abca-242">En el equipo del usuario de destino, abra un símbolo del sistema y escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="5abca-242">On the target user's computer, open a command prompt and type the following command:</span></span>
       
```console
gpupdate /target:user
```

    
    The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.
    
4. <span data-ttu-id="5abca-243">En el símbolo del sistema, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="5abca-243">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="5abca-244">**gpresult /r**</span><span class="sxs-lookup"><span data-stu-id="5abca-244">**gpresult /r**</span></span>
    
    <span data-ttu-id="5abca-245">Debería ver "Objetos de directiva de grupo asignados" con el nombre del GPO que creó que se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="5abca-245">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>
    
<span data-ttu-id="5abca-246">También puede comprobar que el GPO ha actualizado correctamente el Registro en el equipo de un usuario examinando el Registro.</span><span class="sxs-lookup"><span data-stu-id="5abca-246">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry.</span></span> <span data-ttu-id="5abca-247">Abra el Editor del Registro y vaya a **la clave [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync].**</span><span class="sxs-lookup"><span data-stu-id="5abca-247">Open Registry Editor and navigate to the **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** key.</span></span> <span data-ttu-id="5abca-248">Si el GPO actualizó correctamente el Registro, verá un valor denominado EnableSkypeUI con un valor de 0.</span><span class="sxs-lookup"><span data-stu-id="5abca-248">If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>
