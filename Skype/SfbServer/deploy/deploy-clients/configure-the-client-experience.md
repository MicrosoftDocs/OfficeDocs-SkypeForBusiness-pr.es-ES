---
title: Configurar la experiencia del cliente con Skype para profesionales de 2015
ms.reviewer: ''
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66867a96-ff00-497d-889c-2e908cc384ce
description: 'Resumen: Lea este tema para obtener información sobre cómo configurar la experiencia del cliente de Skype para los usuarios empresariales.'
ms.openlocfilehash: b8d258236a5254aa1dab5e86edb9586ea514c689
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219603"
---
# <a name="configure-the-client-experience-with-skype-for-business-2015"></a><span data-ttu-id="e5af3-103">Configurar la experiencia del cliente con Skype para profesionales de 2015</span><span class="sxs-lookup"><span data-stu-id="e5af3-103">Configure the client experience with Skype for Business 2015</span></span>
 
<span data-ttu-id="e5af3-104">**Resumen:** Lea este tema para obtener información sobre cómo configurar la experiencia del cliente de Skype para los usuarios empresariales 2015.</span><span class="sxs-lookup"><span data-stu-id="e5af3-104">**Summary:** Read this topic to learn how to configure the client experience for Skype for Business 2015 users.</span></span>
  
<span data-ttu-id="e5af3-105">Skype para profesionales de 2015 proporciona una experiencia de usuario nuevo que se basa en la experiencia de producto de consumidor de Skype.</span><span class="sxs-lookup"><span data-stu-id="e5af3-105">Skype for Business 2015 provides a new user experience that is based on the Skype consumer product experience.</span></span> <span data-ttu-id="e5af3-106">Además de todas las características de Lync, Skype para la empresa proporciona nuevas características con controles simplificados y los iconos que ya conoce.</span><span class="sxs-lookup"><span data-stu-id="e5af3-106">In addition to all the features of Lync, Skype for Business provides new features with simplified controls and familiar icons.</span></span> <span data-ttu-id="e5af3-107">Para obtener información detallada acerca de la nueva experiencia del cliente, vea [Explore Skype para la empresa](https://go.microsoft.com/fwlink/?LinkId=529022).</span><span class="sxs-lookup"><span data-stu-id="e5af3-107">For detailed information about the new client experience, see [Explore Skype for Business](https://go.microsoft.com/fwlink/?LinkId=529022).</span></span>
  
<span data-ttu-id="e5af3-108">Skype para Business Server es compatible con el nuevo Skype para la experiencia del cliente empresarial, así como la experiencia del cliente Lync.</span><span class="sxs-lookup"><span data-stu-id="e5af3-108">Skype for Business Server supports the new Skype for Business client experience as well as the Lync client experience.</span></span> <span data-ttu-id="e5af3-109">Como administrador, puede elegir la experiencia de cliente preferida para sus usuarios.</span><span class="sxs-lookup"><span data-stu-id="e5af3-109">As an administrator, you can choose the preferred client experience for your users.</span></span> <span data-ttu-id="e5af3-110">Por ejemplo, es posible que desee implementar la experiencia del cliente Lync hasta que los usuarios de su organización están capacitados totalmente en la nueva Skype para que la experiencia empresarial.</span><span class="sxs-lookup"><span data-stu-id="e5af3-110">For example, you might want to deploy the Lync client experience until users in your organization are fully trained in the new Skype for Business experience.</span></span> <span data-ttu-id="e5af3-111">O bien, si no ha actualizado aún todos los usuarios a Skype para Business Server, es posible que desea que todos los usuarios tengan la misma experiencia de cliente hasta que todos se actualizan al nuevo servidor.</span><span class="sxs-lookup"><span data-stu-id="e5af3-111">Or, if you have not yet upgraded all users to Skype for Business Server, you might want all users to have the same client experience until all are upgraded to the new server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e5af3-112">Si su organización tiene ambos Skype para Business Server y a implementar Lync Server, la experiencia del cliente predeterminado variarán en función de las versiones de servidor y la configuración de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="e5af3-112">If your organization has both Skype for Business Server and Lync Server deployed, the default client experience will differ depending on server versions and UI settings.</span></span> <span data-ttu-id="e5af3-113">Cuando los usuarios iniciar Skype para la empresa por primera vez, siempre verán la Skype para la interfaz de usuario de negocio--incluso si ha seleccionado la experiencia del cliente Lync.</span><span class="sxs-lookup"><span data-stu-id="e5af3-113">When users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience.</span></span> <span data-ttu-id="e5af3-114">Después de varios minutos, se piden a los usuarios para cambiar al modo de Lync.</span><span class="sxs-lookup"><span data-stu-id="e5af3-114">After several minutes, users are asked to switch to Lync mode.</span></span> <span data-ttu-id="e5af3-115">Para más información, vea **Comportamiento del cliente en el primer inicio** más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="e5af3-115">For more information, see **First launch client behavior** later in this topic.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e5af3-116">La experiencia del cliente Lync 2013 no es una opción de Skype para versiones de cliente de 2016 empresarial o posterior.</span><span class="sxs-lookup"><span data-stu-id="e5af3-116">The Lync 2013 client experience is not an option for Skype for Business 2016 client versions or later.</span></span> <span data-ttu-id="e5af3-117">Antes de que intente configurar su entorno de cliente para usar el cliente de Lync 2013, compruebe la versión y asegúrese de que no empieza con el número 16; por ejemplo: 16.x.x.x.</span><span class="sxs-lookup"><span data-stu-id="e5af3-117">Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span> 
  
## <a name="configure-the-client-experience"></a><span data-ttu-id="e5af3-118">Configurar la experiencia del cliente</span><span class="sxs-lookup"><span data-stu-id="e5af3-118">Configure the client experience</span></span>

<span data-ttu-id="e5af3-119">Puede especificar la experiencia que tendrán los usuarios de su organización mediante el cmdlet **Set-CSClientPolicy** y el parámetro EnableSkypeUI:</span><span class="sxs-lookup"><span data-stu-id="e5af3-119">You can specify the client experience the users in your organization will see by using the **Set-CSClientPolicy** cmdlet with the EnableSkypeUI parameter:</span></span>
  
```
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

<span data-ttu-id="e5af3-120">donde XdsIdentity se refiere a la directiva Global o a una directiva de sitio.</span><span class="sxs-lookup"><span data-stu-id="e5af3-120">where XdsIdentity refers to the Global policy or a named site policy.</span></span>
  
<span data-ttu-id="e5af3-121">El comando siguiente selecciona la Skype para la experiencia del cliente empresarial para todos los usuarios de la organización afectada por la directiva Global (Recuerde, sitio o directivas específicas de usuario invalidación la directiva Global):</span><span class="sxs-lookup"><span data-stu-id="e5af3-121">The following command selects the Skype for Business client experience for all users in your organization affected by the Global policy (remember, site or user-specific policies override the Global policy):</span></span> 
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

<span data-ttu-id="e5af3-122">El comando siguiente selecciona la experiencia del cliente Lync para todos los usuarios de la organización afectada por la directiva Global:</span><span class="sxs-lookup"><span data-stu-id="e5af3-122">The next command selects the Lync client experience for all users in your organization affected by the Global policy:</span></span>
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

<span data-ttu-id="e5af3-123">El comando siguiente selecciona la Skype para la experiencia del cliente empresarial para todos los usuarios dentro del sitio de Redmond:</span><span class="sxs-lookup"><span data-stu-id="e5af3-123">The next command selects the Skype for Business client experience for all users within the Redmond site:</span></span>
  
```
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

<span data-ttu-id="e5af3-124">Si desea configurar la experiencia del cliente para usuarios específicos dentro de la organización, puede crear una nueva directiva de usuario mediante el cmdlet **New-CsClientPolicy** y, a continuación, asigne la directiva a usuarios específicos mediante la **Grant-CsClientPolicy** cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e5af3-124">If you want to configure the client experience for specific users within your organization, you can create a new user policy by using the **New-CsClientPolicy** cmdlet, and then assign the policy to specific users by using the **Grant-CsClientPolicy** cmdlet.</span></span>
  
<span data-ttu-id="e5af3-125">Por ejemplo, el siguiente comando crea una nueva directiva de cliente, SalesClientUI, que selecciona el Skype para la experiencia del cliente empresarial:</span><span class="sxs-lookup"><span data-stu-id="e5af3-125">For example, the following command creates a new client policy, SalesClientUI, that selects the Skype for Business client experience:</span></span>
  
```
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

<span data-ttu-id="e5af3-126">El siguiente comando asigna la directiva SalesClientUI a todos los miembros del departamento de Ventas:</span><span class="sxs-lookup"><span data-stu-id="e5af3-126">The next command assigns the policy, SalesClientUI, to all members of the Sales department:</span></span>
  
```
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a><span data-ttu-id="e5af3-127">Comportamientos del cliente en el primer inicio</span><span class="sxs-lookup"><span data-stu-id="e5af3-127">First launch client behaviors</span></span>

<span data-ttu-id="e5af3-128">De forma predeterminada, cuando los usuarios iniciar Skype para 2015 empresarial por primera vez, siempre verán la Skype para la interfaz de usuario de negocio--incluso si ha seleccionado la experiencia del cliente Lync estableciendo el valor del parámetro EnableSkypeUI en $False, tal como se describe anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e5af3-128">By default, when users launch Skype for Business 2015 for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the value of the EnableSkypeUI parameter to $False as described previously.</span></span> <span data-ttu-id="e5af3-129">Después de varios minutos, se les solicitará a los usuarios que cambien al modo Lync.</span><span class="sxs-lookup"><span data-stu-id="e5af3-129">After several minutes, users will then be asked to switch to Lync mode.</span></span>
  
<span data-ttu-id="e5af3-130">Si desea mostrar la interfaz de usuario de Lync cuando los usuarios inician el cliente Skype Empresarial por primera vez, siga estos pasos antes de que el cliente se inicie por primera vez después de la actualización:</span><span class="sxs-lookup"><span data-stu-id="e5af3-130">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>
  
1. <span data-ttu-id="e5af3-131">Confirme que el valor de `EnableSkypeUI` está establecido en $False en la directiva que está utilizando como se describió anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e5af3-131">Confirm that the value of  `EnableSkypeUI` is set to $False in the policy you are using as described previously.</span></span>
    
2. <span data-ttu-id="e5af3-p106">Actualice el registro del sistema en el equipo del usuario. Hágalo una sola vez antes de que los usuarios inicien el cliente Skype Empresarial por primera vez. Para obtener información sobre cómo crear un objeto de directiva de grupo para actualizar el registro en un equipo unido a un dominio, consulte la sección correspondiente en este mismo tema.</span><span class="sxs-lookup"><span data-stu-id="e5af3-p106">Update the system registry on the user's computer. You should do this before the first time users launch the Skype for Business client, and you should do this only once. For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="e5af3-135">En la clave **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]**, cree un valor **Binario**.</span><span class="sxs-lookup"><span data-stu-id="e5af3-135">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="e5af3-136">El **Nombre del valor** debe ser **EnableSkypeUI** y los **Datos del valor** deben configurarse como **00 00 00 00**.</span><span class="sxs-lookup"><span data-stu-id="e5af3-136">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="e5af3-137">La clave debería ser similar a esta:</span><span class="sxs-lookup"><span data-stu-id="e5af3-137">The key should look like the following:</span></span>
    
   <pre>
   [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
   "CanSharePptInCollab"=dword:00000001
   "CanShareOneNoteInCollab"=dword:00000001
   "CanAppShareInCollab"=dword:00000001
   "EnableSkypeUI"=hex:00,00,00,00
   </pre>

<span data-ttu-id="e5af3-138">La interfaz de usuario de Lync se mostrará ahora cuando los usuarios inicien el cliente Skype Empresarial por primera vez.</span><span class="sxs-lookup"><span data-stu-id="e5af3-138">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="e5af3-139">Tutorial sobre controlar cómo se muestra la pantalla de bienvenida</span><span class="sxs-lookup"><span data-stu-id="e5af3-139">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="e5af3-140">Cuando los usuarios abren la Skype para clientes empresariales, el comportamiento predeterminado es mostrar una pantalla de bienvenida que incluye la *mayoría de las personas formular a 7 sugerencias rápidas para*.</span><span class="sxs-lookup"><span data-stu-id="e5af3-140">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes  *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="e5af3-141">Puede desactivar la visualización de la pantalla de inicio de sesión, pero puede permitir que los usuarios sigan teniendo acceso al tutorial agregando el siguiente valor de registro en el equipo del cliente:</span><span class="sxs-lookup"><span data-stu-id="e5af3-141">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>
  
<span data-ttu-id="e5af3-p108">En la clave **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]**, cree un **valor DWORD (32 bits)**. Es preciso que el **Nombre del valor** sea **IsBasicTutorialSeenByUser** y que los **Datos del valor** se establezcan en **1**.</span><span class="sxs-lookup"><span data-stu-id="e5af3-p108">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** key, create a new **DWORD (32-bit) Value**. The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>
  
<span data-ttu-id="e5af3-144">La clave necesita ser similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="e5af3-144">The key should look like the following:</span></span>
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="e5af3-145">Desactivar el tutorial del cliente</span><span class="sxs-lookup"><span data-stu-id="e5af3-145">Turn off the client tutorial</span></span>

<span data-ttu-id="e5af3-146">Si no quiere que los usuarios obtengan acceso al tutorial, puede desactivar el tutorial del cliente con el siguiente valor del registro:</span><span class="sxs-lookup"><span data-stu-id="e5af3-146">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>
  
<span data-ttu-id="e5af3-p109">En la clave **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]**, cree un **valor DWORD (32 bits)**. Es preciso que el **Nombre del valor** sea **TutorialFeatureEnabled** y que los **Datos del valor** se establezcan en **0**.</span><span class="sxs-lookup"><span data-stu-id="e5af3-p109">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** key, create a new **DWORD (32-bit) Value**. The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>
  
<span data-ttu-id="e5af3-149">Lync</span><span class="sxs-lookup"><span data-stu-id="e5af3-149">Lync</span></span>
  
```
"TutorialFeatureEnabled"=dword:00000000
```

<span data-ttu-id="e5af3-150">Puede volver a activar el tutorial al configurar los **Datos del valor** en **1**.</span><span class="sxs-lookup"><span data-stu-id="e5af3-150">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>
  
## <a name="default-client-behaviors"></a><span data-ttu-id="e5af3-151">Comportamientos predeterminados de los clientes</span><span class="sxs-lookup"><span data-stu-id="e5af3-151">Default client behaviors</span></span>

<span data-ttu-id="e5af3-152">Si su organización tiene ambos Skype para Business Server y a implementar Lync Server, la experiencia del cliente variarán en función de las versiones de servidor y la UI de Skype configuración.</span><span class="sxs-lookup"><span data-stu-id="e5af3-152">If your organization has both Skype for Business Server and Lync Server deployed, the client experience will differ depending on server versions and the Skype UI setting.</span></span> <span data-ttu-id="e5af3-153">La tabla siguiente muestra la experiencia de cliente inicial en función de la versión del servidor y la configuración de la interfaz de usuario:</span><span class="sxs-lookup"><span data-stu-id="e5af3-153">The following table shows the initial client experience based on server version and the UI setting:</span></span>
  

|<span data-ttu-id="e5af3-154">**Versión del servidor**</span><span class="sxs-lookup"><span data-stu-id="e5af3-154">**Server version**</span></span>|<span data-ttu-id="e5af3-155">**Configuración de EnableSkypeUI**</span><span class="sxs-lookup"><span data-stu-id="e5af3-155">**EnableSkypeUI setting**</span></span>|<span data-ttu-id="e5af3-156">**Experiencia del cliente**</span><span class="sxs-lookup"><span data-stu-id="e5af3-156">**Client experience**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e5af3-157">Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="e5af3-157">Skype for Business Server</span></span> |<span data-ttu-id="e5af3-158">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="e5af3-158">Default</span></span>  <br/> |<span data-ttu-id="e5af3-159">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="e5af3-159">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="e5af3-160">Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="e5af3-160">Skype for Business Server</span></span>  |<span data-ttu-id="e5af3-161">True</span><span class="sxs-lookup"><span data-stu-id="e5af3-161">True</span></span>  <br/> |<span data-ttu-id="e5af3-162">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="e5af3-162">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="e5af3-163">Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="e5af3-163">Skype for Business Server</span></span>  |<span data-ttu-id="e5af3-164">False</span><span class="sxs-lookup"><span data-stu-id="e5af3-164">False</span></span>  <br/> |<span data-ttu-id="e5af3-165">Usuario más frecuentes cambiar al modo de Lync (el usuario puede cambiar a Skype para la empresa más adelante si cambia la configuración de la interfaz de usuario en $true)</span><span class="sxs-lookup"><span data-stu-id="e5af3-165">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="e5af3-166">Lync Server 2010 o Lync Server 2013 (con correcciones correctos)</span><span class="sxs-lookup"><span data-stu-id="e5af3-166">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="e5af3-167">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="e5af3-167">Default</span></span>  <br/> |<span data-ttu-id="e5af3-168">Usuario más frecuentes cambiar al modo de Lync (el usuario puede cambiar a Skype para la empresa más adelante si cambia la configuración de la interfaz de usuario en $true)</span><span class="sxs-lookup"><span data-stu-id="e5af3-168">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="e5af3-169">Lync Server 2010 o Lync Server 2013 (con correcciones correctos)</span><span class="sxs-lookup"><span data-stu-id="e5af3-169">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="e5af3-170">True</span><span class="sxs-lookup"><span data-stu-id="e5af3-170">True</span></span>  <br/> |<span data-ttu-id="e5af3-171">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="e5af3-171">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="e5af3-172">Lync Server 2010 o Lync Server 2013 (con correcciones correctos)</span><span class="sxs-lookup"><span data-stu-id="e5af3-172">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="e5af3-173">False</span><span class="sxs-lookup"><span data-stu-id="e5af3-173">False</span></span>  <br/> |<span data-ttu-id="e5af3-174">Usuario más frecuentes cambiar al modo de Lync (el usuario puede cambiar a Skype para la empresa más adelante si cambia la configuración de la interfaz de usuario en $true)</span><span class="sxs-lookup"><span data-stu-id="e5af3-174">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="e5af3-175">Lync Server 2010 o Lync Server 2013 (sin revisiones)</span><span class="sxs-lookup"><span data-stu-id="e5af3-175">Lync Server 2010 or Lync Server 2013 (without patches)</span></span>  <br/> |<span data-ttu-id="e5af3-176">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="e5af3-176">Default</span></span>  <br/> |<span data-ttu-id="e5af3-177">Usuario más frecuentes cambiar al modo de Lync (el usuario no puede cambiar a Skype para la empresa más adelante)</span><span class="sxs-lookup"><span data-stu-id="e5af3-177">User asked to switch to Lync mode (user cannot switch to Skype for Business later)</span></span>  <br/> |
   
<span data-ttu-id="e5af3-178">En la tabla siguiente muestra la experiencia del cliente cuando el administrador cambia la configuración inicial para la experiencia de Skype UI:</span><span class="sxs-lookup"><span data-stu-id="e5af3-178">The next table shows the client experience when the administrator changes the initial setting for the Skype UI experience:</span></span>
  

|<span data-ttu-id="e5af3-179">**Versión del servidor**</span><span class="sxs-lookup"><span data-stu-id="e5af3-179">**Server version**</span></span>|<span data-ttu-id="e5af3-180">**Configuración de EnableSkypeUI**</span><span class="sxs-lookup"><span data-stu-id="e5af3-180">**EnableSkypeUI setting**</span></span>|<span data-ttu-id="e5af3-181">**La interfaz de usuario de cliente = Lync**</span><span class="sxs-lookup"><span data-stu-id="e5af3-181">**Client UI = Lync**</span></span>|<span data-ttu-id="e5af3-182">**IU del cliente = Skype Empresarial**</span><span class="sxs-lookup"><span data-stu-id="e5af3-182">**Client UI = Skype for Business**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e5af3-183">Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="e5af3-183">Skype for Business Server</span></span> |<span data-ttu-id="e5af3-184">True</span><span class="sxs-lookup"><span data-stu-id="e5af3-184">True</span></span>  <br/> |<span data-ttu-id="e5af3-185">Usuario que se le pida que cambie a Skype para la empresa</span><span class="sxs-lookup"><span data-stu-id="e5af3-185">User asked to switch to Skype for Business</span></span>  <br/> |<span data-ttu-id="e5af3-186">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="e5af3-186">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="e5af3-187">Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="e5af3-187">Skype for Business Server</span></span> |<span data-ttu-id="e5af3-188">False</span><span class="sxs-lookup"><span data-stu-id="e5af3-188">False</span></span>  <br/> |<span data-ttu-id="e5af3-189">Modo de Lync</span><span class="sxs-lookup"><span data-stu-id="e5af3-189">Lync mode</span></span>  <br/> |<span data-ttu-id="e5af3-190">Usuario más frecuentes cambiar al modo de Lync</span><span class="sxs-lookup"><span data-stu-id="e5af3-190">User asked to switch to Lync mode</span></span>  <br/> |
|<span data-ttu-id="e5af3-191">Lync Server 2010 o Lync Server 2013 (con correcciones correctos)</span><span class="sxs-lookup"><span data-stu-id="e5af3-191">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="e5af3-192">True</span><span class="sxs-lookup"><span data-stu-id="e5af3-192">True</span></span>  <br/> |<span data-ttu-id="e5af3-193">Usuario que se le pida que cambie a Skype para la empresa</span><span class="sxs-lookup"><span data-stu-id="e5af3-193">User asked to switch to Skype for Business</span></span>  <br/> |<span data-ttu-id="e5af3-194">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="e5af3-194">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="e5af3-195">Lync Server 2010 o Lync Server 2013 (con correcciones correctos)</span><span class="sxs-lookup"><span data-stu-id="e5af3-195">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="e5af3-196">False</span><span class="sxs-lookup"><span data-stu-id="e5af3-196">False</span></span>  <br/> |<span data-ttu-id="e5af3-197">Modo de Lync</span><span class="sxs-lookup"><span data-stu-id="e5af3-197">Lync mode</span></span>  <br/> |<span data-ttu-id="e5af3-198">Usuario más frecuentes cambiar al modo de Lync</span><span class="sxs-lookup"><span data-stu-id="e5af3-198">User asked to switch to Lync mode</span></span>  <br/> |
|<span data-ttu-id="e5af3-199">Lync Server 2010 o Lync Server 2013 (sin revisiones)</span><span class="sxs-lookup"><span data-stu-id="e5af3-199">Lync Server 2010 or Lync Server 2013 (without patches)</span></span>  <br/> |<span data-ttu-id="e5af3-200">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="e5af3-200">Default</span></span>  <br/> |<span data-ttu-id="e5af3-201">Modo de Lync (no se puede cambiar a Skype para la empresa)</span><span class="sxs-lookup"><span data-stu-id="e5af3-201">Lync mode (cannot switch to Skype for Business)</span></span>  <br/> |<span data-ttu-id="e5af3-202">Modo de Lync (no se puede cambiar a Skype para la empresa)</span><span class="sxs-lookup"><span data-stu-id="e5af3-202">Lync mode (cannot switch to Skype for Business)</span></span>  <br/> |
   
<span data-ttu-id="e5af3-203">Las versiones de revisión necesarias para administrar la configuración de la Skype para clientes empresariales son:</span><span class="sxs-lookup"><span data-stu-id="e5af3-203">The patch versions required to manage the configuration of the Skype for Business client are:</span></span>
  
- <span data-ttu-id="e5af3-204">Lync Server 2010 - actualización acumulativa de febrero de 2015 (4.0.7577.710) para Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e5af3-204">Lync Server 2010 - February 2015 Cumulative Update (4.0.7577.710) for Lync Server 2010.</span></span> <span data-ttu-id="e5af3-205">Para obtener información, vea [actualizaciones de Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)</span><span class="sxs-lookup"><span data-stu-id="e5af3-205">For information, see [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)</span></span>
    
- <span data-ttu-id="e5af3-206">Lync Server 2013 - actualización acumulativa de diciembre de 2014 (5.0.8308.857) para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e5af3-206">Lync Server 2013 - December 2014 Cumulative Update (5.0.8308.857) for Lync Server 2013.</span></span> <span data-ttu-id="e5af3-207">Para obtener información, vea [actualizaciones de Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).</span><span class="sxs-lookup"><span data-stu-id="e5af3-207">For information, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).</span></span>
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="e5af3-208">Crear un objeto de directiva de grupo para modificar el registro en un equipo unido a un dominio</span><span class="sxs-lookup"><span data-stu-id="e5af3-208">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="e5af3-209">La actualización del registro para mostrar la experiencia del cliente Lync la primera vez que un usuario inicia la Skype para cliente empresarial 2015 debe realizarse sólo una vez.</span><span class="sxs-lookup"><span data-stu-id="e5af3-209">The registry update to display the Lync client experience the first time a user launches the Skype for Business 2015 client should be done only once.</span></span> <span data-ttu-id="e5af3-210">Si utiliza un objeto de directiva de grupo (GPO) para actualizar el registro, es necesario que defina el objeto para crear un nuevo valor en lugar de actualizar los datos de valor.</span><span class="sxs-lookup"><span data-stu-id="e5af3-210">If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data.</span></span> <span data-ttu-id="e5af3-211">Cuando se aplica el GPO, si el nuevo valor no existe, el GPO lo creará y establecerá los datos del valor en 0.</span><span class="sxs-lookup"><span data-stu-id="e5af3-211">When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span> 
  
<span data-ttu-id="e5af3-212">El siguiente procedimiento describe cómo modificar el registro para que la experiencia del cliente Lync se muestra la primera vez que un usuario inicia la Skype para cliente empresarial 2015.</span><span class="sxs-lookup"><span data-stu-id="e5af3-212">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business 2015 client.</span></span> <span data-ttu-id="e5af3-213">También puede usar este procedimiento para actualizar el registro para deshabilitar el tutorial de la pantalla de inicio de sesión como se ha descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e5af3-213">You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>
  
### <a name="to-create-the-gpo"></a><span data-ttu-id="e5af3-214">Para crear el GPO</span><span class="sxs-lookup"><span data-stu-id="e5af3-214">To create the GPO</span></span>

1. <span data-ttu-id="e5af3-215">Inicie la **Consola de administración de directivas de grupo**.</span><span class="sxs-lookup"><span data-stu-id="e5af3-215">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="e5af3-216">Para obtener información acerca de cómo usar la consola de administración de directivas de grupo, consulte [Consola de administración de directivas de grupo](https://go.microsoft.com/fwlink/?LinkId=532759).</span><span class="sxs-lookup"><span data-stu-id="e5af3-216">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](https://go.microsoft.com/fwlink/?LinkId=532759).</span></span>
    
2. <span data-ttu-id="e5af3-217">Haga clic con el botón derecho en el nodo **Objetos de directiva de grupo** y seleccione **Nuevo** en el menú.</span><span class="sxs-lookup"><span data-stu-id="e5af3-217">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>
    
3. <span data-ttu-id="e5af3-218">En el diálogo **Nuevo GPO**, escriba un nombre para el GPO, por ejemplo, MakeLyncDefaultUIy haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e5af3-218">In the **New GPO** dialog, enter a name for the GPO, for example,MakeLyncDefaultUI, and then click **OK**.</span></span>
    
4. <span data-ttu-id="e5af3-219">Haga clic con el botón derecho en el GPO nuevo que acaba de crear y seleccione **Editar** en el menú.</span><span class="sxs-lookup"><span data-stu-id="e5af3-219">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>
    
5. <span data-ttu-id="e5af3-220">En el **Editor de administración de directivas de grupo**, expanda **Configuración de usuario**, expanda **Preferencias**, expanda **Configuración de Windows** y seleccione el nodo **Registro**.</span><span class="sxs-lookup"><span data-stu-id="e5af3-220">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>
    
6. <span data-ttu-id="e5af3-221">Haga clic con el botón derecho en el nodo **Registro** y seleccione **Nuevo** > **Elemento de registro**.</span><span class="sxs-lookup"><span data-stu-id="e5af3-221">Right-click on the **Registry** node, and then select **New** > **Registry Item**.</span></span>
    
7. <span data-ttu-id="e5af3-222">En el diálogo **Nuevas propiedades de registro**, actualice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e5af3-222">On the **New Registry Properties** dialog, update the following:</span></span>
    
   |<span data-ttu-id="e5af3-223">**Campo**</span><span class="sxs-lookup"><span data-stu-id="e5af3-223">**Field**</span></span>|<span data-ttu-id="e5af3-224">**Valor para seleccionar o introducir**</span><span class="sxs-lookup"><span data-stu-id="e5af3-224">**Value to select or enter**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="e5af3-225">**Acción**</span><span class="sxs-lookup"><span data-stu-id="e5af3-225">**Action**</span></span> <br/> |<span data-ttu-id="e5af3-226">**Creación**</span><span class="sxs-lookup"><span data-stu-id="e5af3-226">**Create**</span></span> <br/> |
   |<span data-ttu-id="e5af3-227">**Subárbol**</span><span class="sxs-lookup"><span data-stu-id="e5af3-227">**Hive**</span></span> <br/> | <span data-ttu-id="e5af3-228">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="e5af3-228">HKEY_CURRENT_USER</span></span> <br/> |
   |<span data-ttu-id="e5af3-229">**Ruta de acceso a la clave**</span><span class="sxs-lookup"><span data-stu-id="e5af3-229">**Key Path**</span></span> <br/> |<span data-ttu-id="e5af3-230">Software\Microsoft\Office\Lync</span><span class="sxs-lookup"><span data-stu-id="e5af3-230">Software\Microsoft\Office\Lync</span></span>  <br/> |
   |<span data-ttu-id="e5af3-231">**Nombre del valor**</span><span class="sxs-lookup"><span data-stu-id="e5af3-231">**Value name**</span></span> <br/> |<span data-ttu-id="e5af3-232">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="e5af3-232">EnableSkypeUI</span></span>  <br/> |
   |<span data-ttu-id="e5af3-233">**Tipo de valor**</span><span class="sxs-lookup"><span data-stu-id="e5af3-233">**Value type**</span></span> <br/> |<span data-ttu-id="e5af3-234">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="e5af3-234">REG_BINARY</span></span>  <br/> |
   |<span data-ttu-id="e5af3-235">**Datos del valor**</span><span class="sxs-lookup"><span data-stu-id="e5af3-235">**Value data**</span></span> <br/> |<span data-ttu-id="e5af3-236">00000000</span><span class="sxs-lookup"><span data-stu-id="e5af3-236">00000000</span></span>  <br/> |
   
8. <span data-ttu-id="e5af3-237">Haga clic en **Aceptar** para guardar los cambios y cierre el GPO.</span><span class="sxs-lookup"><span data-stu-id="e5af3-237">Click **OK** to save your changes, and then close the GPO.</span></span>
    
<span data-ttu-id="e5af3-238">A continuación, es preciso que vincule el GPO que creó con el grupo de usuarios al que desea asignar la directiva, como una UO.</span><span class="sxs-lookup"><span data-stu-id="e5af3-238">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>
  
### <a name="to-use-the-gpo-to-assign-the-policy"></a><span data-ttu-id="e5af3-239">Para usar el GPO a fin de asignar la directiva</span><span class="sxs-lookup"><span data-stu-id="e5af3-239">To use the GPO to assign the policy</span></span>

1. <span data-ttu-id="e5af3-240">En la Consola de administración de directivas de grupo, haga clic con el botón secundario en la UO a la que desea asignar la directiva y, luego, seleccione **Vincular con un GPO existente**.</span><span class="sxs-lookup"><span data-stu-id="e5af3-240">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>
    
2. <span data-ttu-id="e5af3-241">En el diálogo **Seleccionar GPO**, seleccione el GPO que ha creado y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e5af3-241">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>
    
3. <span data-ttu-id="e5af3-242">En el equipo del usuario de destino, abra un símbolo del sistema y escriba el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="e5af3-242">On the target user's computer, open a command prompt and type the following command:</span></span>
       
```
gpupdate /target:user
```

    
    The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.
    
4. <span data-ttu-id="e5af3-243">En el símbolo del sistema, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="e5af3-243">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="e5af3-244">**gpresult /r**</span><span class="sxs-lookup"><span data-stu-id="e5af3-244">**gpresult /r**</span></span>
    
    <span data-ttu-id="e5af3-245">Junto con el nombre del GPO que creó verá abajo "Objetos de directiva de grupo asignados".</span><span class="sxs-lookup"><span data-stu-id="e5af3-245">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>
    
<span data-ttu-id="e5af3-p115">Asimismo, puede comprobar si el GPO ha actualizado correctamente el registro en el equipo de un usuario al examinar el registro. Para ello, abra el Editor del Registro y diríjase a la clave **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]**. Si el GPO ha actualizado correctamente el registro, verá el valor denominado EnableSkypeUI con un valor de 0.</span><span class="sxs-lookup"><span data-stu-id="e5af3-p115">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry. Open Registry Editor and navigate to the **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** key. If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>
  

