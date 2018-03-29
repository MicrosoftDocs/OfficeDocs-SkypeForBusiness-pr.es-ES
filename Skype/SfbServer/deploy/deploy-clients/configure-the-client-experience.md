---
title: Configurar la experiencia del cliente con Skype Empresarial
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66867a96-ff00-497d-889c-2e908cc384ce
description: 'Resumen: Leer este tema para aprender a configurar la experiencia del cliente de Skype para usuarios de negocios.'
ms.openlocfilehash: 9c1bc182c383ea7d806ce779f3d727e7925a59d4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-the-client-experience-with-skype-for-business"></a><span data-ttu-id="4afa0-103">Configurar la experiencia del cliente con Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="4afa0-103">Configure the client experience with Skype for Business</span></span>
 
<span data-ttu-id="4afa0-104">**Resumen:** Lea este tema para aprender a configurar la experiencia del cliente de Skype para usuarios de negocios.</span><span class="sxs-lookup"><span data-stu-id="4afa0-104">**Summary:** Read this topic to learn how to configure the client experience for Skype for Business users.</span></span>
  
<span data-ttu-id="4afa0-105">Skype para empresas proporciona una nueva experiencia de usuario que se basa en la experiencia de producto del consumidor de Skype.</span><span class="sxs-lookup"><span data-stu-id="4afa0-105">Skype for Business provides a new user experience that is based on the Skype consumer product experience.</span></span> <span data-ttu-id="4afa0-106">Además de todas las características de Lync, Skype para empresas proporciona nuevas características con controles simplificados y los iconos que ya conoce.</span><span class="sxs-lookup"><span data-stu-id="4afa0-106">In addition to all the features of Lync, Skype for Business provides new features with simplified controls and familiar icons.</span></span> <span data-ttu-id="4afa0-107">Para obtener información detallada acerca de la nueva experiencia de cliente, consulte [Lync es ahora Skype para Business & #x 2014; consulte Novedades](https://go.microsoft.com/fwlink/?LinkId=529022).</span><span class="sxs-lookup"><span data-stu-id="4afa0-107">For detailed information about the new client experience, see [Lync is now Skype for Business &#x2014; see what's new](https://go.microsoft.com/fwlink/?LinkId=529022).</span></span>
  
<span data-ttu-id="4afa0-108">Skype para Business Server es compatible con el nuevo Skype para la experiencia del cliente de negocios, así como la experiencia del cliente Lync.</span><span class="sxs-lookup"><span data-stu-id="4afa0-108">Skype for Business Server supports the new Skype for Business client experience as well as the Lync client experience.</span></span> <span data-ttu-id="4afa0-109">Como administrador, puede elegir la experiencia de cliente preferida para sus usuarios.</span><span class="sxs-lookup"><span data-stu-id="4afa0-109">As an administrator, you can choose the preferred client experience for your users.</span></span> <span data-ttu-id="4afa0-110">Por ejemplo, que desea implementar la experiencia del cliente Lync hasta que los usuarios de su organización están plenamente capacitados en el nuevo Skype para la experiencia del negocio.</span><span class="sxs-lookup"><span data-stu-id="4afa0-110">For example, you might want to deploy the Lync client experience until users in your organization are fully trained in the new Skype for Business experience.</span></span> <span data-ttu-id="4afa0-111">O, si aún no ha actualizado los todos los usuarios a Skype para Business Server, todos los usuarios tengan la misma experiencia de cliente hasta que todos se actualicen al nuevo servidor.</span><span class="sxs-lookup"><span data-stu-id="4afa0-111">Or, if you have not yet upgraded all users to Skype for Business Server, you might want all users to have the same client experience until all are upgraded to the new server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4afa0-112">Si su organización tiene ambos Skype para Business Server e implementar Lync Server, la experiencia de cliente predeterminada variarán en función de las versiones de servidor y configuración de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="4afa0-112">If your organization has both Skype for Business Server and Lync Server deployed, the default client experience will differ depending on server versions and UI settings.</span></span> <span data-ttu-id="4afa0-113">Cuando los usuarios iniciar Skype para el negocio por primera vez, siempre verán la Skype para la interfaz de usuario de negocio--incluso si ha seleccionado la experiencia del cliente Lync.</span><span class="sxs-lookup"><span data-stu-id="4afa0-113">When users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience.</span></span> <span data-ttu-id="4afa0-114">Después de varios minutos, se solicita a los usuarios para cambiar al modo de Lync.</span><span class="sxs-lookup"><span data-stu-id="4afa0-114">After several minutes, users are asked to switch to Lync mode.</span></span> <span data-ttu-id="4afa0-115">Para más información, vea **Comportamiento del cliente en el primer inicio** más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="4afa0-115">For more information, see **First launch client behavior** later in this topic.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4afa0-116">La experiencia del cliente Lync 2013 no es una opción de Skype para versiones de cliente de empresa 2016.</span><span class="sxs-lookup"><span data-stu-id="4afa0-116">The Lync 2013 client experience is not an option for Skype for Business 2016 client versions.</span></span> <span data-ttu-id="4afa0-117">Antes de que intente configurar su entorno de cliente para usar el cliente de Lync 2013, compruebe la versión y asegúrese de que no empieza con el número 16; por ejemplo: 16.x.x.x.</span><span class="sxs-lookup"><span data-stu-id="4afa0-117">Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span> 
  
## <a name="configure-the-client-experience"></a><span data-ttu-id="4afa0-118">Configurar la experiencia del cliente</span><span class="sxs-lookup"><span data-stu-id="4afa0-118">Configure the client experience</span></span>

<span data-ttu-id="4afa0-119">Puede especificar la experiencia que tendrán los usuarios de su organización mediante el cmdlet **Set-CSClientPolicy** y el parámetro EnableSkypeUI:</span><span class="sxs-lookup"><span data-stu-id="4afa0-119">You can specify the client experience the users in your organization will see by using the **Set-CSClientPolicy** cmdlet with the EnableSkypeUI parameter:</span></span>
  
```
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

<span data-ttu-id="4afa0-120">donde XdsIdentity se refiere a la directiva Global o a una directiva de sitio.</span><span class="sxs-lookup"><span data-stu-id="4afa0-120">where XdsIdentity refers to the Global policy or a named site policy.</span></span>
  
<span data-ttu-id="4afa0-121">El comando siguiente selecciona el Skype para la experiencia del cliente empresarial para todos los usuarios de la organización afectada por la directiva Global (Recuerde, sitio o directivas específicas de usuario reemplaza la directiva Global):</span><span class="sxs-lookup"><span data-stu-id="4afa0-121">The following command selects the Skype for Business client experience for all users in your organization affected by the Global policy (remember, site or user-specific policies override the Global policy):</span></span> 
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

<span data-ttu-id="4afa0-122">El comando siguiente selecciona la experiencia del cliente Lync para todos los usuarios de la organización afectada por la directiva Global:</span><span class="sxs-lookup"><span data-stu-id="4afa0-122">The next command selects the Lync client experience for all users in your organization affected by the Global policy:</span></span>
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

<span data-ttu-id="4afa0-123">El comando siguiente selecciona el Skype para la experiencia del cliente empresarial para todos los usuarios en el sitio de Redmond:</span><span class="sxs-lookup"><span data-stu-id="4afa0-123">The next command selects the Skype for Business client experience for all users within the Redmond site:</span></span>
  
```
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

<span data-ttu-id="4afa0-124">Si desea configurar la experiencia del cliente para usuarios específicos dentro de su organización, puede crear una nueva directiva de usuario mediante el cmdlet **New-CsClientPolicy** y después asigne la directiva a usuarios específicos mediante el uso de la **Concesión CsClientPolicy** cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4afa0-124">If you want to configure the client experience for specific users within your organization, you can create a new user policy by using the **New-CsClientPolicy** cmdlet, and then assign the policy to specific users by using the **Grant-CsClientPolicy** cmdlet.</span></span>
  
<span data-ttu-id="4afa0-125">Por ejemplo, el siguiente comando crea una nueva directiva de cliente, SalesClientUI, que selecciona el Skype para la experiencia del cliente empresarial:</span><span class="sxs-lookup"><span data-stu-id="4afa0-125">For example, the following command creates a new client policy, SalesClientUI, that selects the Skype for Business client experience:</span></span>
  
```
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

<span data-ttu-id="4afa0-126">El siguiente comando asigna la directiva SalesClientUI a todos los miembros del departamento de Ventas:</span><span class="sxs-lookup"><span data-stu-id="4afa0-126">The next command assigns the policy, SalesClientUI, to all members of the Sales department:</span></span>
  
```
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a><span data-ttu-id="4afa0-127">Comportamientos del cliente en el primer inicio</span><span class="sxs-lookup"><span data-stu-id="4afa0-127">First launch client behaviors</span></span>

<span data-ttu-id="4afa0-128">De forma predeterminada, cuando los usuarios iniciar Skype para el negocio por primera vez, siempre verán la Skype para la interfaz de usuario de negocio--incluso si ha seleccionado la experiencia del cliente Lync estableciendo el valor del parámetro EnableSkypeUI en $False, como se describió anteriormente .</span><span class="sxs-lookup"><span data-stu-id="4afa0-128">By default, when users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the value of the EnableSkypeUI parameter to $False as described previously.</span></span> <span data-ttu-id="4afa0-129">Después de varios minutos, se les solicitará a los usuarios que cambien al modo Lync.</span><span class="sxs-lookup"><span data-stu-id="4afa0-129">After several minutes, users will then be asked to switch to Lync mode.</span></span>
  
<span data-ttu-id="4afa0-130">Si desea mostrar la interfaz de usuario de Lync cuando los usuarios inician el cliente Skype Empresarial por primera vez, siga estos pasos antes de que el cliente se inicie por primera vez después de la actualización:</span><span class="sxs-lookup"><span data-stu-id="4afa0-130">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>
  
1. <span data-ttu-id="4afa0-131">Confirme que el valor de `EnableSkypeUI` se establece en $False en la directiva que se está utilizando como se describió anteriormente.</span><span class="sxs-lookup"><span data-stu-id="4afa0-131">Confirm that the value of  `EnableSkypeUI` is set to $False in the policy you are using as described previously.</span></span>
    
2. <span data-ttu-id="4afa0-p106">Actualice el registro del sistema en el equipo del usuario. Hágalo una sola vez antes de que los usuarios inicien el cliente Skype Empresarial por primera vez. Para obtener información sobre cómo crear un objeto de directiva de grupo para actualizar el registro en un equipo unido a un dominio, consulte la sección correspondiente en este mismo tema.</span><span class="sxs-lookup"><span data-stu-id="4afa0-p106">Update the system registry on the user's computer. You should do this before the first time users launch the Skype for Business client, and you should do this only once. For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="4afa0-135">En la clave **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]**, cree un valor **Binario**.</span><span class="sxs-lookup"><span data-stu-id="4afa0-135">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="4afa0-136">El **Nombre del valor** debe ser **EnableSkypeUI** y los **Datos del valor** deben configurarse como **00 00 00 00**.</span><span class="sxs-lookup"><span data-stu-id="4afa0-136">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="4afa0-137">La clave debería ser similar a esta:</span><span class="sxs-lookup"><span data-stu-id="4afa0-137">The key should look like the following:</span></span>
    
  ```
  [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
"CanSharePptInCollab"=dword:00000001
"CanShareOneNoteInCollab"=dword:00000001
"CanAppShareInCollab"=dword:00000001
"EnableSkypeUI"=hex:00,00,00,00
  ```

<span data-ttu-id="4afa0-138">La interfaz de usuario de Lync se mostrará ahora cuando los usuarios inicien el cliente Skype Empresarial por primera vez.</span><span class="sxs-lookup"><span data-stu-id="4afa0-138">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="4afa0-139">Controlar la visualización del tutorial de la pantalla de inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="4afa0-139">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="4afa0-p107">Cuando los usuarios abren el cliente Skype Empresarial, el comportamiento predeterminado consiste en mostrar una pantalla de inicio de sesión que incluye  *7 consejos rápidos que la mayoría de las personas solicitan*  . Puede desactivar la visualización de la pantalla de inicio de sesión, pero puede permitir que los usuarios sigan teniendo acceso al tutorial agregando el siguiente valor de registro en el equipo del cliente:</span><span class="sxs-lookup"><span data-stu-id="4afa0-p107">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes  *7 Quick tips most people ask for*  . You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>
  
<span data-ttu-id="4afa0-p108">En la clave **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]**, cree un **valor DWORD (32 bits)**. Es preciso que el **Nombre del valor** sea **IsBasicTutorialSeenByUser** y que los **Datos del valor** se establezcan en **1**.</span><span class="sxs-lookup"><span data-stu-id="4afa0-p108">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** key, create a new **DWORD (32-bit) Value**. The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>
  
<span data-ttu-id="4afa0-144">La clave debería ser similar a esta:</span><span class="sxs-lookup"><span data-stu-id="4afa0-144">The key should look like the following:</span></span>
  
```
"IsBasicTutorialSeenByUser"=dword:00000001
```

### <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="4afa0-145">Desactivar el tutorial del cliente</span><span class="sxs-lookup"><span data-stu-id="4afa0-145">Turn off the client tutorial</span></span>

<span data-ttu-id="4afa0-146">Si no desea que los usuarios puedan tener acceso al tutorial, puede desactivar el tutorial del cliente con el siguiente valor de registro:</span><span class="sxs-lookup"><span data-stu-id="4afa0-146">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>
  
<span data-ttu-id="4afa0-p109">En la clave **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]**, cree un **valor DWORD (32 bits)**. Es preciso que el **Nombre del valor** sea **TutorialFeatureEnabled** y que los **Datos del valor** se establezcan en **0**.</span><span class="sxs-lookup"><span data-stu-id="4afa0-p109">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** key, create a new **DWORD (32-bit) Value**. The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>
  
<span data-ttu-id="4afa0-149">Lync</span><span class="sxs-lookup"><span data-stu-id="4afa0-149">Lync</span></span>
  
```
"TutorialFeatureEnabled"=dword:00000000
```

<span data-ttu-id="4afa0-150">Puede volver a activar el tutorial al configurar los **Datos del valor** en **1**.</span><span class="sxs-lookup"><span data-stu-id="4afa0-150">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>
  
## <a name="default-client-behaviors"></a><span data-ttu-id="4afa0-151">Comportamientos predeterminados de los clientes</span><span class="sxs-lookup"><span data-stu-id="4afa0-151">Default client behaviors</span></span>

<span data-ttu-id="4afa0-152">Si su organización tiene ambos Skype para Business Server e implementar Lync Server, la experiencia del cliente variarán en función de las versiones de servidor y la UI de Skype configuración.</span><span class="sxs-lookup"><span data-stu-id="4afa0-152">If your organization has both Skype for Business Server and Lync Server deployed, the client experience will differ depending on server versions and the Skype UI setting.</span></span> <span data-ttu-id="4afa0-153">La tabla siguiente muestra la experiencia de cliente inicial en función de la versión del servidor y la configuración de la interfaz de usuario:</span><span class="sxs-lookup"><span data-stu-id="4afa0-153">The following table shows the initial client experience based on server version and the UI setting:</span></span>
  

|<span data-ttu-id="4afa0-154">**Versión del servidor**</span><span class="sxs-lookup"><span data-stu-id="4afa0-154">**Server version**</span></span>|<span data-ttu-id="4afa0-155">**Configuración de EnableSkypeUI**</span><span class="sxs-lookup"><span data-stu-id="4afa0-155">**EnableSkypeUI setting**</span></span>|<span data-ttu-id="4afa0-156">**Experiencia del cliente**</span><span class="sxs-lookup"><span data-stu-id="4afa0-156">**Client experience**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4afa0-157">Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="4afa0-157">Skype for Business Server 2015</span></span>  <br/> |<span data-ttu-id="4afa0-158">Predeterminado</span><span class="sxs-lookup"><span data-stu-id="4afa0-158">Default</span></span>  <br/> |<span data-ttu-id="4afa0-159">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="4afa0-159">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="4afa0-160">Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="4afa0-160">Skype for Business Server 2015</span></span>  <br/> |<span data-ttu-id="4afa0-161">Verdadero</span><span class="sxs-lookup"><span data-stu-id="4afa0-161">True</span></span>  <br/> |<span data-ttu-id="4afa0-162">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="4afa0-162">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="4afa0-163">Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="4afa0-163">Skype for Business Server 2015</span></span>  <br/> |<span data-ttu-id="4afa0-164">Falso</span><span class="sxs-lookup"><span data-stu-id="4afa0-164">False</span></span>  <br/> |<span data-ttu-id="4afa0-165">Pregunta de usuario cambiar al modo de Lync (usuario puede pasar a Skype para empresas más tarde si cambia la configuración de la interfaz de usuario en $true)</span><span class="sxs-lookup"><span data-stu-id="4afa0-165">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="4afa0-166">Lync Server 2010 o Lync Server 2013 (con correcciones correctos)</span><span class="sxs-lookup"><span data-stu-id="4afa0-166">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="4afa0-167">Predeterminado</span><span class="sxs-lookup"><span data-stu-id="4afa0-167">Default</span></span>  <br/> |<span data-ttu-id="4afa0-168">Pregunta de usuario cambiar al modo de Lync (usuario puede pasar a Skype para empresas más tarde si cambia la configuración de la interfaz de usuario en $true)</span><span class="sxs-lookup"><span data-stu-id="4afa0-168">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="4afa0-169">Lync Server 2010 o Lync Server 2013 (con correcciones correctos)</span><span class="sxs-lookup"><span data-stu-id="4afa0-169">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="4afa0-170">Verdadero</span><span class="sxs-lookup"><span data-stu-id="4afa0-170">True</span></span>  <br/> |<span data-ttu-id="4afa0-171">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="4afa0-171">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="4afa0-172">Lync Server 2010 o Lync Server 2013 (con correcciones correctos)</span><span class="sxs-lookup"><span data-stu-id="4afa0-172">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="4afa0-173">Falso</span><span class="sxs-lookup"><span data-stu-id="4afa0-173">False</span></span>  <br/> |<span data-ttu-id="4afa0-174">Pregunta de usuario cambiar al modo de Lync (usuario puede pasar a Skype para empresas más tarde si cambia la configuración de la interfaz de usuario en $true)</span><span class="sxs-lookup"><span data-stu-id="4afa0-174">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="4afa0-175">Lync Server 2010 o Lync Server 2013 (sin revisiones)</span><span class="sxs-lookup"><span data-stu-id="4afa0-175">Lync Server 2010 or Lync Server 2013 (without patches)</span></span>  <br/> |<span data-ttu-id="4afa0-176">Predeterminado</span><span class="sxs-lookup"><span data-stu-id="4afa0-176">Default</span></span>  <br/> |<span data-ttu-id="4afa0-177">Pregunta de usuario cambiar al modo de Lync (el usuario no puede cambiar a Skype para empresas más adelante)</span><span class="sxs-lookup"><span data-stu-id="4afa0-177">User asked to switch to Lync mode (user cannot switch to Skype for Business later)</span></span>  <br/> |
   
<span data-ttu-id="4afa0-178">La tabla siguiente muestra la experiencia del cliente cuando el administrador cambia la configuración inicial de la experiencia de Skype UI:</span><span class="sxs-lookup"><span data-stu-id="4afa0-178">The next table shows the client experience when the administrator changes the initial setting for the Skype UI experience:</span></span>
  

|<span data-ttu-id="4afa0-179">**Versión del servidor**</span><span class="sxs-lookup"><span data-stu-id="4afa0-179">**Server version**</span></span>|<span data-ttu-id="4afa0-180">**Configuración de EnableSkypeUI**</span><span class="sxs-lookup"><span data-stu-id="4afa0-180">**EnableSkypeUI setting**</span></span>|<span data-ttu-id="4afa0-181">**IU de cliente = Lync**</span><span class="sxs-lookup"><span data-stu-id="4afa0-181">**Client UI = Lync**</span></span>|<span data-ttu-id="4afa0-182">**IU de cliente = Skype para empresas**</span><span class="sxs-lookup"><span data-stu-id="4afa0-182">**Client UI = Skype for Business**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4afa0-183">Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="4afa0-183">Skype for Business Server 2015</span></span>  <br/> |<span data-ttu-id="4afa0-184">Verdadero</span><span class="sxs-lookup"><span data-stu-id="4afa0-184">True</span></span>  <br/> |<span data-ttu-id="4afa0-185">Pregunta de usuario cambiar a Skype para empresas</span><span class="sxs-lookup"><span data-stu-id="4afa0-185">User asked to switch to Skype for Business</span></span>  <br/> |<span data-ttu-id="4afa0-186">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="4afa0-186">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="4afa0-187">Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="4afa0-187">Skype for Business Server 2015</span></span>  <br/> |<span data-ttu-id="4afa0-188">Falso</span><span class="sxs-lookup"><span data-stu-id="4afa0-188">False</span></span>  <br/> |<span data-ttu-id="4afa0-189">Modo de Lync</span><span class="sxs-lookup"><span data-stu-id="4afa0-189">Lync mode</span></span>  <br/> |<span data-ttu-id="4afa0-190">Pregunta de usuario cambiar al modo de Lync</span><span class="sxs-lookup"><span data-stu-id="4afa0-190">User asked to switch to Lync mode</span></span>  <br/> |
|<span data-ttu-id="4afa0-191">Lync Server 2010 o Lync Server 2013 (con correcciones correctos)</span><span class="sxs-lookup"><span data-stu-id="4afa0-191">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="4afa0-192">Verdadero</span><span class="sxs-lookup"><span data-stu-id="4afa0-192">True</span></span>  <br/> |<span data-ttu-id="4afa0-193">Pregunta de usuario cambiar a Skype para empresas</span><span class="sxs-lookup"><span data-stu-id="4afa0-193">User asked to switch to Skype for Business</span></span>  <br/> |<span data-ttu-id="4afa0-194">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="4afa0-194">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="4afa0-195">Lync Server 2010 o Lync Server 2013 (con correcciones correctos)</span><span class="sxs-lookup"><span data-stu-id="4afa0-195">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="4afa0-196">Falso</span><span class="sxs-lookup"><span data-stu-id="4afa0-196">False</span></span>  <br/> |<span data-ttu-id="4afa0-197">Modo de Lync</span><span class="sxs-lookup"><span data-stu-id="4afa0-197">Lync mode</span></span>  <br/> |<span data-ttu-id="4afa0-198">Pregunta de usuario cambiar al modo de Lync</span><span class="sxs-lookup"><span data-stu-id="4afa0-198">User asked to switch to Lync mode</span></span>  <br/> |
|<span data-ttu-id="4afa0-199">Lync Server 2010 o Lync Server 2013 (sin revisiones)</span><span class="sxs-lookup"><span data-stu-id="4afa0-199">Lync Server 2010 or Lync Server 2013 (without patches)</span></span>  <br/> |<span data-ttu-id="4afa0-200">Predeterminado</span><span class="sxs-lookup"><span data-stu-id="4afa0-200">Default</span></span>  <br/> |<span data-ttu-id="4afa0-201">Modo de Lync (no puede cambiar a Skype para empresas)</span><span class="sxs-lookup"><span data-stu-id="4afa0-201">Lync mode (cannot switch to Skype for Business)</span></span>  <br/> |<span data-ttu-id="4afa0-202">Modo de Lync (no puede cambiar a Skype para empresas)</span><span class="sxs-lookup"><span data-stu-id="4afa0-202">Lync mode (cannot switch to Skype for Business)</span></span>  <br/> |
   
<span data-ttu-id="4afa0-203">Las versiones de revisión necesarias para administrar la configuración de la Skype para Business client son:</span><span class="sxs-lookup"><span data-stu-id="4afa0-203">The patch versions required to manage the configuration of the Skype for Business client are:</span></span>
  
- <span data-ttu-id="4afa0-204">Lync Server 2010 - actualización acumulativa de febrero de 2015 (4.0.7577.710) de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="4afa0-204">Lync Server 2010 - February 2015 Cumulative Update (4.0.7577.710) for Lync Server 2010.</span></span> <span data-ttu-id="4afa0-205">Para obtener información, vea [versiones de Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)</span><span class="sxs-lookup"><span data-stu-id="4afa0-205">For information, see [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)</span></span>
    
- <span data-ttu-id="4afa0-206">Lync Server 2013 - actualización acumulativa de diciembre de 2014 (5.0.8308.857) para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4afa0-206">Lync Server 2013 - December 2014 Cumulative Update (5.0.8308.857) for Lync Server 2013.</span></span> <span data-ttu-id="4afa0-207">Para obtener información, vea [versiones de Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).</span><span class="sxs-lookup"><span data-stu-id="4afa0-207">For information, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).</span></span>
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="4afa0-208">Crear un objeto de directiva de grupo para modificar el registro en un equipo unido a un dominio</span><span class="sxs-lookup"><span data-stu-id="4afa0-208">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="4afa0-p113">La actualización del registro para visualizar la experiencia de cliente Lync la primera vez que el usuario inicia el cliente Skype Empresarial debe realizarse solo una vez. Si utiliza un objeto de directiva de grupo (GPO) para actualizar el registro, es necesario que defina el objeto para crear un nuevo valor en lugar de actualizar los datos de valor. Cuando se aplica el GPO, si el nuevo valor no existe, el GPO lo creará y establecerá los datos del valor en 0.</span><span class="sxs-lookup"><span data-stu-id="4afa0-p113">The registry update to display the Lync client experience the first time a user launches the Skype for Business client should be done only once. If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data. When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span> 
  
<span data-ttu-id="4afa0-p114">El procedimiento siguiente describe cómo modificar el registro de manera que la experiencia de cliente Lync se muestre la primera vez que el usuario inicie Skype Empresarial. También puede utilizar este procedimiento para actualizar el registro para desactivar el tutorial de la pantalla de inicio de sesión como se ha descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="4afa0-p114">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business. You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>
  
### <a name="to-create-the-gpo"></a><span data-ttu-id="4afa0-214">Para crear el GPO</span><span class="sxs-lookup"><span data-stu-id="4afa0-214">To create the GPO</span></span>

1. <span data-ttu-id="4afa0-215">Inicie la **Consola de administración de directivas de grupo**.</span><span class="sxs-lookup"><span data-stu-id="4afa0-215">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="4afa0-216">Para obtener información acerca de cómo usar la consola de administración de directivas de grupo, consulte [Consola de administración de directivas de grupo](https://go.microsoft.com/fwlink/?LinkId=532759).</span><span class="sxs-lookup"><span data-stu-id="4afa0-216">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](https://go.microsoft.com/fwlink/?LinkId=532759).</span></span>
    
2. <span data-ttu-id="4afa0-217">Haga clic con el botón derecho en el nodo **Objetos de directiva de grupo** y seleccione **Nuevo** en el menú.</span><span class="sxs-lookup"><span data-stu-id="4afa0-217">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>
    
3. <span data-ttu-id="4afa0-218">En el diálogo **Nuevo GPO**, escriba un nombre para el GPO, por ejemplo, MakeLyncDefaultUIy haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4afa0-218">In the **New GPO** dialog, enter a name for the GPO, for example,MakeLyncDefaultUI, and then click **OK**.</span></span>
    
4. <span data-ttu-id="4afa0-219">Haga clic con el botón derecho en el GPO nuevo que acaba de crear y seleccione **Editar** en el menú.</span><span class="sxs-lookup"><span data-stu-id="4afa0-219">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>
    
5. <span data-ttu-id="4afa0-220">En el **Editor de administración de directivas de grupo**, expanda **Configuración de usuario**, expanda **Preferencias**, expanda **Configuración de Windows** y seleccione el nodo **Registro**.</span><span class="sxs-lookup"><span data-stu-id="4afa0-220">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>
    
6. <span data-ttu-id="4afa0-221">Haga clic con el botón derecho en el nodo **Registro** y seleccione **Nuevo** > **Elemento de registro**.</span><span class="sxs-lookup"><span data-stu-id="4afa0-221">Right-click on the **Registry** node, and then select **New** > **Registry Item**.</span></span>
    
7. <span data-ttu-id="4afa0-222">En el diálogo **Nuevas propiedades de registro**, actualice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4afa0-222">On the **New Registry Properties** dialog, update the following:</span></span>
    
   |<span data-ttu-id="4afa0-223">**Campo**</span><span class="sxs-lookup"><span data-stu-id="4afa0-223">**Field**</span></span>|<span data-ttu-id="4afa0-224">**Valor para seleccionar o introducir**</span><span class="sxs-lookup"><span data-stu-id="4afa0-224">**Value to select or enter**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="4afa0-225">**Acción**</span><span class="sxs-lookup"><span data-stu-id="4afa0-225">**Action**</span></span> <br/> |<span data-ttu-id="4afa0-226">**Creación**</span><span class="sxs-lookup"><span data-stu-id="4afa0-226">**Create**</span></span> <br/> |
   |<span data-ttu-id="4afa0-227">**Subárbol**</span><span class="sxs-lookup"><span data-stu-id="4afa0-227">**Hive**</span></span> <br/> | <span data-ttu-id="4afa0-228">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="4afa0-228">HKEY_CURRENT_USER</span></span> <br/> |
   |<span data-ttu-id="4afa0-229">**Ruta de acceso a la clave**</span><span class="sxs-lookup"><span data-stu-id="4afa0-229">**Key Path**</span></span> <br/> |<span data-ttu-id="4afa0-230">Software\Microsoft\Office\Lync</span><span class="sxs-lookup"><span data-stu-id="4afa0-230">Software\Microsoft\Office\Lync</span></span>  <br/> |
   |<span data-ttu-id="4afa0-231">**Nombre del valor**</span><span class="sxs-lookup"><span data-stu-id="4afa0-231">**Value name**</span></span> <br/> |<span data-ttu-id="4afa0-232">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="4afa0-232">EnableSkypeUI</span></span>  <br/> |
   |<span data-ttu-id="4afa0-233">**Tipo de valor**</span><span class="sxs-lookup"><span data-stu-id="4afa0-233">**Value type**</span></span> <br/> |<span data-ttu-id="4afa0-234">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="4afa0-234">REG_BINARY</span></span>  <br/> |
   |<span data-ttu-id="4afa0-235">**Datos del valor**</span><span class="sxs-lookup"><span data-stu-id="4afa0-235">**Value data**</span></span> <br/> |<span data-ttu-id="4afa0-236">00000000</span><span class="sxs-lookup"><span data-stu-id="4afa0-236">00000000</span></span>  <br/> |
   
8. <span data-ttu-id="4afa0-237">Haga clic en **Aceptar** para guardar los cambios y cierre el GPO.</span><span class="sxs-lookup"><span data-stu-id="4afa0-237">Click **OK** to save your changes, and then close the GPO.</span></span>
    
<span data-ttu-id="4afa0-238">A continuación, tendrá que vincular el GPO que ha creado al grupo de usuarios al que desea asignar la política, como una UO.</span><span class="sxs-lookup"><span data-stu-id="4afa0-238">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>
  
### <a name="to-use-the-gpo-to-assign-the-policy"></a><span data-ttu-id="4afa0-239">Utilizar el GPO para asignar la directiva</span><span class="sxs-lookup"><span data-stu-id="4afa0-239">To use the GPO to assign the policy</span></span>

1. <span data-ttu-id="4afa0-240">En la consola de administración de directivas de grupo, haga clic con el botón derecho en la UO a la que desea asignar la directiva y seleccione **Vincular a un GPO existente**.</span><span class="sxs-lookup"><span data-stu-id="4afa0-240">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>
    
2. <span data-ttu-id="4afa0-241">En el diálogo **Seleccionar GPO**, seleccione el GPO que ha creado y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4afa0-241">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>
    
3. <span data-ttu-id="4afa0-242">En el equipo del usuario de destino, abra un símbolo del sistema y escriba el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="4afa0-242">On the target user's computer, open a command prompt and type the following command:</span></span>
    
    <span data-ttu-id="4afa0-243">**gpupdate /target:usuario**</span><span class="sxs-lookup"><span data-stu-id="4afa0-243">**gpupdate /target:user**</span></span>
    
    <span data-ttu-id="4afa0-p115">El mensaje "Actualizando directiva..." se muestra mientras se aplica el GPO. Cuando se ha completado, aparece el mensaje "La actualización de la directiva de usuario ha concluido satisfactoriamente".</span><span class="sxs-lookup"><span data-stu-id="4afa0-p115">The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.</span></span>
    
4. <span data-ttu-id="4afa0-246">En el símbolo del sistema, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="4afa0-246">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="4afa0-247">**gpresult /r**</span><span class="sxs-lookup"><span data-stu-id="4afa0-247">**gpresult /r**</span></span>
    
    <span data-ttu-id="4afa0-248">Junto con el nombre del GPO que creó verá abajo "Objetos de directiva de grupo asignados".</span><span class="sxs-lookup"><span data-stu-id="4afa0-248">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>
    
<span data-ttu-id="4afa0-p116">Asimismo, puede comprobar si el GPO ha actualizado correctamente el registro en el equipo de un usuario al examinar el registro. Para ello, abra el Editor del Registro y diríjase a la clave **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]**. Si el GPO ha actualizado correctamente el registro, verá el valor denominado EnableSkypeUI con un valor de 0.</span><span class="sxs-lookup"><span data-stu-id="4afa0-p116">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry. Open Registry Editor and navigate to the **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** key. If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>
  

