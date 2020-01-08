---
title: Cambiar de la interfaz de usuario del cliente de Lync a la de Skype Empresarial
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: a2394a4c-7522-484c-a047-7b3289742be0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: None
ms.custom:
- Setup
description: 'Learn how to switch between Skype for Business and Lync client user interfaces using PowerShell in Office 365 '
ms.openlocfilehash: 0f24879c136c98db1a856765cb164d376417ad5a
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "40962888"
---
# <a name="switching-between-the-skype-for-business-and-the-lync-client-user-interfaces"></a><span data-ttu-id="114ed-103">Cambiar de la interfaz de usuario del cliente de Lync a la de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="114ed-103">Switching between the Skype for Business and the Lync client user interfaces</span></span>

<span data-ttu-id="114ed-104">Para las organizaciones de Skype empresarial online, puede usar PowerShell remoto en Office 365 para permitir que los usuarios de Skype empresarial usen el cliente de Skype empresarial o la interfaz de usuario del cliente de Skype empresarial (Lync).</span><span class="sxs-lookup"><span data-stu-id="114ed-104">For Skype for Business Online organizations, you can use the Remote PowerShell in Office 365 to enable your Skype for Business users to use the Skype for Business client or the Skype for Business (Lync) client user interface.</span></span> <span data-ttu-id="114ed-105">La configuración predeterminada es que los usuarios usen la interfaz de usuario del cliente de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="114ed-105">The default setting is for users to use the Skype for Business client user interface.</span></span> <span data-ttu-id="114ed-106">Si prefiere usar la experiencia del cliente de Lync, puede administrar el primer inicio de cliente para mostrar la interfaz de usuario de Lync siguiendo los pasos que se describen más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="114ed-106">If you'd prefer to use the Lync client experience, you can manage the first launch client behavior to display the Lync user interface by following the steps later in this topic.</span></span>
  
> [!NOTE]
> <span data-ttu-id="114ed-p102">La experiencia de cliente con Lync 2013 no está disponible en las versiones de cliente de Skype Empresarial 2016. Antes de que intente configurar su entorno de cliente para usar el cliente de Lync 2013, compruebe la versión y asegúrese de que no empieza con el número 16; por ejemplo: 16.x.x.x.</span><span class="sxs-lookup"><span data-stu-id="114ed-p102">The Lync 2013 client experience isn't an option for Skype for Business 2016 client versions. Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span> 
  
> [!TIP]
> <span data-ttu-id="114ed-109">Si desea cambiar fácilmente la interfaz de usuario y no desea realizar los pasos manuales, consulte el centro de [descarga de Microsoft](https://go.microsoft.com/fwlink/?LinkId=532431) para obtener un script de PowerShell que lo hace más fácil.</span><span class="sxs-lookup"><span data-stu-id="114ed-109">If you want to easily switch the user interface and don't want to do the manual steps, see the [Microsoft Download Center](https://go.microsoft.com/fwlink/?LinkId=532431) for a PowerShell script to make it easier.</span></span>
  
## <a name="switching-the-skype-for-business-user-interface-for-users"></a><span data-ttu-id="114ed-110">Cambio de la interfaz de usuario de Skype Empresarial para los usuarios</span><span class="sxs-lookup"><span data-stu-id="114ed-110">Switching the Skype for Business user interface for users</span></span>

<span data-ttu-id="114ed-p103">El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta a Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688). Para otra información, consulte [Cómo configurar el equipo para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=534539).</span><span class="sxs-lookup"><span data-stu-id="114ed-p103">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). For other information, see [Configuring your computer for Skype for Business Online management](https://go.microsoft.com/fwlink/?LinkId=534539).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="114ed-p104">La configuración de la directiva  _Global_ para cambiar la interfaz de usuario no se aplicará a un usuario que ya tenga aplicada una directiva personalizada. Para poder cambiar la interfaz de usuario, tendrá que ejecutar lo siguiente para cada usuario que tenga aplicada una directiva personalizada:</span><span class="sxs-lookup"><span data-stu-id="114ed-p104">The  _Global_ policy setting for switching the user interface won't be applied to a user that already has a custom policy applied. To be able to change the user interface, you will need to run the following for each user that has a custom policy applied:</span></span>
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

> [!CAUTION]
> <span data-ttu-id="114ed-116">La directiva  _ClientPolicyEnableSkypeUI_ sustituirá a la configuración de la directiva personalizada existente para el usuario.</span><span class="sxs-lookup"><span data-stu-id="114ed-116">The  _ClientPolicyEnableSkypeUI_ policy will replace the existing custom policy setting for the user.</span></span>
  
<span data-ttu-id="114ed-117">Para habilitar que todos los usuarios de su organización utilicen el cliente de Skype Empresarial, abra el PowerShell remoto y escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="114ed-117">To enable all of the users in your organization to use the Skype for Business client, open the Remote PowerShell and type the following:</span></span>
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

<span data-ttu-id="114ed-118">Si configura la directiva de forma correcta, verá:</span><span class="sxs-lookup"><span data-stu-id="114ed-118">If you set the policy right, you will see:</span></span>
  
![PowerShell: SkypeUIEnabled](../images/b6b9d2e1-1a37-46df-9757-f81c6054e93b.png)
  
<span data-ttu-id="114ed-120">Para habilitar que todos los usuarios de su organización utilicen el cliente de Skype Empresarial (Lync), abra el PowerShell remoto y escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="114ed-120">To enable all of the users in your organization to use the Skype for Business (Lync) client, open the Remote PowerShell and type the following:</span></span> 
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

<span data-ttu-id="114ed-121">Si configura la directiva de forma correcta, verá:</span><span class="sxs-lookup"><span data-stu-id="114ed-121">If you set the policy right, you will see:</span></span>
  
![PowerShell: SkypeUIDisabled](../images/f14ec3ce-4eb8-4a11-826e-6029043ed054.png)
  
<span data-ttu-id="114ed-123">Para permitir que solo un usuario de su organización utilice el cliente de Skype Empresarial, abra el PowerShell remoto y escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="114ed-123">To allow a single user in your organization to use the Skype for Business client, open the Remote PowerShell and type the following:</span></span>
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

<span data-ttu-id="114ed-124">Si configura la directiva de forma correcta, verá:</span><span class="sxs-lookup"><span data-stu-id="114ed-124">If you set the policy right, you will see:</span></span>
  
![Skype Empresarial Online - Activar IU](../images/596aef69-41dc-4e1e-b689-2b7009ae58a1.png)
  
<span data-ttu-id="114ed-126">Para permitir que solo un usuario de su organización utilice el cliente de Skype Empresarial (Lync), abra el PowerShell remoto y escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="114ed-126">To allow a single user in your organization to use the Skype for Business (Lync) client, open the Remote PowerShell and type the following:</span></span>
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI -Identity <username>
```

<span data-ttu-id="114ed-127">Si configura la directiva de forma correcta, verá:</span><span class="sxs-lookup"><span data-stu-id="114ed-127">If you set the policy right, you will see:</span></span>
  
![Skype Empresarial Online - IU deshabilitada](../images/61c645e0-67fc-4e03-803c-b7028a47dae3.png)
  
<span data-ttu-id="114ed-129">Para permitir que varios usuarios de su organización utilicen el cliente de Skype Empresarial, abra el PowerShell remoto y escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="114ed-129">To allow multiple users in your organization to use the Skype for Business client, open the Remote PowerShell and type the following:</span></span>
  

```PowerShell
$users = @("sip:bob@contoso.com","sip:fred@contoso.com") 

$users | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

<span data-ttu-id="114ed-130">Para permitir que varios usuarios de su organización utilicen el cliente de Skype Empresarial (Lync), abra el PowerShell remoto y escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="114ed-130">To allow multiple users in your organization to use the Skype for Business (Lync) client, open the Remote PowerShell and type the following:</span></span>
  
```PowerShell
$users = @("sip:bob@contoso.com","sip:fred@contoso.com")

$users | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

<span data-ttu-id="114ed-131">Para permitir que un grupo de usuarios de su organización utilice el cliente de Skype Empresarial, abra el PowerShell remoto y escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="114ed-131">To allow a group of users in your organization to use the Skype for Business client, open the Remote PowerShell and type the following:</span></span>
  
```PowerShell
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

<span data-ttu-id="114ed-132">Para permitir que un grupo de usuarios de su organización utilice el cliente de Skype Empresarial (Lync), abra el PowerShell remoto y escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="114ed-132">To allow a group of users in your organization to use the Skype for Business (Lync) client, open the Remote PowerShell and type the following:</span></span>
  
```PowerShell
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

> [!NOTE]
>  <span data-ttu-id="114ed-p105">El nombre del usuario es el nombre de la cuenta del usuario a la cual se asignará la directiva. El nombre de la cuenta del usuario se puede introducir en uno de los siguientes formatos:>  Dirección SIP del usuario>  Nombre principal de usuario (UPN) del usuario>  Dominio\\nombre de usuario del usuario>  Nombre para mostrar de Active Directory del usuario</span><span class="sxs-lookup"><span data-stu-id="114ed-p105">The user's name is the name of the user's account that the policy should be assigned to. The user's account name can be entered in one of the following formats:>  SIP address of the user>  User Principal name (UPN) of the user>  Domain\\username of the user>  Active Directory display name of the user</span></span>
  
[<span data-ttu-id="114ed-135">Uso de Windows PowerShell para administrar Lync Online</span><span class="sxs-lookup"><span data-stu-id="114ed-135">Using Windows PowerShell to manage Lync Online</span></span>](https://go.microsoft.com/fwlink/?LinkID=525453)
  
## <a name="skype-for-business-online-policy-settings"></a><span data-ttu-id="114ed-136">Configuración de directivas de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="114ed-136">Skype for Business Online policy settings</span></span>

<span data-ttu-id="114ed-137">Esta tabla muestra la experiencia de usuario cuando la directiva se aplica primero a los usuarios:</span><span class="sxs-lookup"><span data-stu-id="114ed-137">This table shows the user experience when the policy is first applied to users:</span></span>
  
|<span data-ttu-id="114ed-138">**Configuración de la directiva de administrador**</span><span class="sxs-lookup"><span data-stu-id="114ed-138">**Admin policy setting**</span></span>|<span data-ttu-id="114ed-139">**Interfaz de usuario que se muestra**</span><span class="sxs-lookup"><span data-stu-id="114ed-139">**User interface displayed**</span></span>|
|:-----|:-----|
|<span data-ttu-id="114ed-140">La directiva no está configurada.</span><span class="sxs-lookup"><span data-stu-id="114ed-140">The policy isn't set.</span></span> |<span data-ttu-id="114ed-141">El usuario continuará utilizando la interfaz de usuario del cliente de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="114ed-141">The user will continue using the Skype for Business client user interface.</span></span>|
|`Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI`<br/>|<span data-ttu-id="114ed-142">El usuario continuará utilizando la interfaz de usuario del cliente de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="114ed-142">The user will continue using the Skype for Business client user interface.</span></span>|
|`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`<br/>|<span data-ttu-id="114ed-143">Se le pedirá al usuario que cambie a la interfaz de usuario del cliente de Skype empresarial (Lync).</span><span class="sxs-lookup"><span data-stu-id="114ed-143">The user will be asked to switch to the Skype for Business (Lync) client user interface.</span></span> <span data-ttu-id="114ed-144">Pueden realizar el cambio más tarde.</span><span class="sxs-lookup"><span data-stu-id="114ed-144">They can switch later.</span></span>|
|`Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>`|<span data-ttu-id="114ed-145">El usuario usará la interfaz de usuario del cliente de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="114ed-145">The user will be using the Skype for Business client user interface.</span></span> |
`Grant-CsClientPolicy-PolicyName ClientPolicyDisableSkypeUI -Identity <username>`|<span data-ttu-id="114ed-146">Se le pedirá al usuario que cambie a la interfaz de usuario del cliente de Skype empresarial (Lync).</span><span class="sxs-lookup"><span data-stu-id="114ed-146">The user will be asked to switch to the Skype for Business (Lync) client user interface.</span></span> <span data-ttu-id="114ed-147">Un administrador puede cambiar la configuración en el futuro, por lo que cambiará la interfaz de usuario del cliente de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="114ed-147">An admin can change the setting in the future that will switch them to the Skype for Business client user interface.</span></span> |
   
<span data-ttu-id="114ed-148">Esta tabla muestra la experiencia de usuario cuando se cambia la directiva:</span><span class="sxs-lookup"><span data-stu-id="114ed-148">This table shows the user experience when the policy is changed:</span></span>
  
|<span data-ttu-id="114ed-149">**Configuración de la directiva de administrador**</span><span class="sxs-lookup"><span data-stu-id="114ed-149">**Admin policy setting**</span></span>|<span data-ttu-id="114ed-150">**Interfaz de usuario de Skype Empresarial (Lync)**</span><span class="sxs-lookup"><span data-stu-id="114ed-150">**Skype for Business (Lync) user interface**</span></span>|<span data-ttu-id="114ed-151">**Interfaz de usuario de Skype Empresarial**</span><span class="sxs-lookup"><span data-stu-id="114ed-151">**Skype for Business user interface**</span></span>|
|:-----|:-----|:-----|
|`Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI`|<span data-ttu-id="114ed-152">Se le pedirá al usuario que cambie a la interfaz de usuario del cliente de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="114ed-152">The user will be asked to switch to the Skype for Business client user interface.</span></span>  <br/> |<span data-ttu-id="114ed-153">El usuario seguirá usando la interfaz de usuario del cliente de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="114ed-153">The user will continue to use the Skype for Business client user interface.</span></span>  <br/> |
|`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`|<span data-ttu-id="114ed-154">El usuario seguirá usando la interfaz de Skype empresarial (Lync).</span><span class="sxs-lookup"><span data-stu-id="114ed-154">The user will continue to use the Skype for Business (Lync) interface.</span></span>  <br/> |<span data-ttu-id="114ed-155">Se le pedirá al usuario que cambie a la interfaz de usuario del cliente de Skype empresarial (Lync).</span><span class="sxs-lookup"><span data-stu-id="114ed-155">The user will be asked to switch to the Skype for Business (Lync) client user interface.</span></span>  <br/> |
|<span data-ttu-id="114ed-156">La directiva no está configurada.</span><span class="sxs-lookup"><span data-stu-id="114ed-156">The policy isn't set.</span></span>  <br/> |<span data-ttu-id="114ed-157">Los usuarios nunca verán la interfaz de usuario del cliente de Skype empresarial (Lync) si no se establece la Directiva.</span><span class="sxs-lookup"><span data-stu-id="114ed-157">Users will never see the Skype for Business (Lync) client user interface if the policy is not set.</span></span> <span data-ttu-id="114ed-158">Siempre utilizarán la interfaz de usuario del cliente de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="114ed-158">They will always use the Skype for Business client user interface.</span></span>  <br/> |<span data-ttu-id="114ed-159">El usuario seguirá usando la interfaz de usuario del cliente de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="114ed-159">The user will continue to use the Skype for Business client user interface.</span></span>  <br/> |
   
<span data-ttu-id="114ed-p109">Esta tabla muestra todas las directivas personalizadas disponibles en línea. Hay nuevas políticas creadas para dar flexibilidad a los administradores para que conserven la antigua directiva personalizada al cambiar entre las marcas EnableSkypeUI. Use los cmdlets de arriba para conceder una de las siguientes directivas a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="114ed-p109">This table shows all the Online custom policies available. There are new policies created to give admins flexibility in retaining the old custom policy while switching between the EnableSkypeUI flags. Please use the cmdlets from above to grant one of the below policies to your users.</span></span>
  
|<span data-ttu-id="114ed-163">**Nombre de la directiva**</span><span class="sxs-lookup"><span data-stu-id="114ed-163">**Policy name**</span></span>|<span data-ttu-id="114ed-164">**EnableSkypeUI**</span><span class="sxs-lookup"><span data-stu-id="114ed-164">**EnableSkypeUI**</span></span>|
|:-----|:-----|
`ClientPolicyDefaultPhoto`||
`ClientPolicyDefaultPhotoDisableSkypeUI` |<span data-ttu-id="114ed-165">Falso</span><span class="sxs-lookup"><span data-stu-id="114ed-165">False</span></span>|
`ClientPolicyNoIMURL`||
`ClientPolicyNoIMURLDisableSkypeUI` |<span data-ttu-id="114ed-166">Falso</span><span class="sxs-lookup"><span data-stu-id="114ed-166">False</span></span>|
`ClientPolicyNoIMURLPhoto`||
`ClientPolicyNoIMURLPhotoDisableSkypeUI` |<span data-ttu-id="114ed-167">Falso</span><span class="sxs-lookup"><span data-stu-id="114ed-167">False</span></span>|
`ClientPolicyNoSaveIMNoArchivingI`||
`ClientPolicyNoSaveIMNoArchivingDisableSkypeUI` |<span data-ttu-id="114ed-168">Falso</span><span class="sxs-lookup"><span data-stu-id="114ed-168">False</span></span>|
`ClientPolicyNoSaveIMNoArchivingNoIMURL`||
`ClientPolicyNoSaveIMNoArchivingNoIMURLDisableSkypeUI` |<span data-ttu-id="114ed-169">Falso</span><span class="sxs-lookup"><span data-stu-id="114ed-169">False</span></span>|
`ClientPolicyNoSaveIMNoArchivingNoIMURLPhoto` ||
`ClientPolicyNoSaveIMNoArchivingNoIMURLPhotoDisableSkypeUI`|<span data-ttu-id="114ed-170">Falso</span><span class="sxs-lookup"><span data-stu-id="114ed-170">False</span></span>|
`ClientPolicyNoSaveIMNoArchivingPhoto`||
`ClientPolicyNoSaveIMNoArchivingPhotoDisableSkypeUI` |<span data-ttu-id="114ed-171">Falso</span><span class="sxs-lookup"><span data-stu-id="114ed-171">False</span></span>|

   
<span data-ttu-id="114ed-172">To get started with Windows PowerShell, see these topics:</span><span class="sxs-lookup"><span data-stu-id="114ed-172">To get started with Windows PowerShell, see these topics:</span></span>
  
- [<span data-ttu-id="114ed-173">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="114ed-173">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- [<span data-ttu-id="114ed-174">Las mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="114ed-174">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
## <a name="first-launch-client-behaviors"></a><span data-ttu-id="114ed-175">Comportamientos del cliente en el primer inicio</span><span class="sxs-lookup"><span data-stu-id="114ed-175">First launch client behaviors</span></span>

<span data-ttu-id="114ed-176">De forma predeterminada, cuando los usuarios inician Skype empresarial por primera vez, siempre verán la interfaz de usuario de Skype empresarial, aunque haya seleccionado la experiencia del cliente de Lync con la configuración de cliente de Lync (`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`) tal y como se ha descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="114ed-176">By default, when users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the client policy to the Lync client experience (`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`) as described previously.</span></span> <span data-ttu-id="114ed-177">Después de varios minutos, se les solicitará a los usuarios que cambien al modo Lync.</span><span class="sxs-lookup"><span data-stu-id="114ed-177">After several minutes, users will then be asked to switch to Lync mode.</span></span>
  
<span data-ttu-id="114ed-178">Si desea mostrar la interfaz de usuario de Lync cuando los usuarios inician el cliente Skype Empresarial por primera vez, siga estos pasos antes de que el cliente se inicie por primera vez después de la actualización:</span><span class="sxs-lookup"><span data-stu-id="114ed-178">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>
  
1. <span data-ttu-id="114ed-179">Siga los pasos descritos anteriormente en este tema y confirme que la directiva de cliente está configurada para deshabilitar la interfaz de usuario de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="114ed-179">Follow the steps earlier in this topic and confirm that the client policy is set to disable the Skype for Business user interface.</span></span>
    
2. <span data-ttu-id="114ed-p111">Actualice el registro del sistema en el equipo del usuario. Hágalo una sola vez antes de que los usuarios inicien el cliente Skype Empresarial por primera vez. Para obtener información sobre cómo crear un objeto de directiva de grupo para actualizar el registro en un equipo unido a un dominio, consulte la sección correspondiente en este mismo tema.</span><span class="sxs-lookup"><span data-stu-id="114ed-p111">Update the system registry on the user's computer. You should do this before the first time users launch the Skype for Business client, and you should do this only once. For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="114ed-183">En la clave **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]**, cree un nuevo valor **Binario**.</span><span class="sxs-lookup"><span data-stu-id="114ed-183">In the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="114ed-184">El **Nombre del valor** debe ser **EnableSkypeUI** y los **Datos del valor** deben configurarse como **00 00 00 00**.</span><span class="sxs-lookup"><span data-stu-id="114ed-184">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="114ed-185">La clave debería ser similar a esta:</span><span class="sxs-lookup"><span data-stu-id="114ed-185">The key should look like the following:</span></span>
    
    <span data-ttu-id="114ed-186">[Software\\\\de HKEY_CURRENT_USER\\Microsoft\\Office Lync]</span><span class="sxs-lookup"><span data-stu-id="114ed-186">[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]</span></span>
    
    <span data-ttu-id="114ed-187">"CanSharePptInCollab" = dword: 00000001</span><span class="sxs-lookup"><span data-stu-id="114ed-187">"CanSharePptInCollab"=dword:00000001</span></span>
    
    <span data-ttu-id="114ed-188">"CanShareOneNoteInCollab" = dword: 00000001</span><span class="sxs-lookup"><span data-stu-id="114ed-188">"CanShareOneNoteInCollab"=dword:00000001</span></span>
    
    <span data-ttu-id="114ed-189">"CanAppShareInCollab" = dword: 00000001</span><span class="sxs-lookup"><span data-stu-id="114ed-189">"CanAppShareInCollab"=dword:00000001</span></span>
    
    <span data-ttu-id="114ed-190">"EnableSkypeUI" = hex: 00, 00, 00, 00</span><span class="sxs-lookup"><span data-stu-id="114ed-190">"EnableSkypeUI"=hex:00,00,00,00</span></span>
    
<span data-ttu-id="114ed-191">La interfaz de usuario de Lync se mostrará ahora cuando los usuarios inicien el cliente Skype Empresarial por primera vez.</span><span class="sxs-lookup"><span data-stu-id="114ed-191">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="114ed-192">Tutorial sobre controlar cómo se muestra la pantalla de bienvenida</span><span class="sxs-lookup"><span data-stu-id="114ed-192">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="114ed-193">Cuando los usuarios abren el cliente de Skype empresarial, el comportamiento predeterminado es mostrar una pantalla de bienvenida que incluye *7 consejos rápidos que la mayoría de las personas solicitan*.</span><span class="sxs-lookup"><span data-stu-id="114ed-193">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="114ed-194">Puede desactivar la visualización de la pantalla de inicio de sesión, pero puede permitir que los usuarios sigan teniendo acceso al tutorial agregando el siguiente valor de registro en el equipo del cliente:</span><span class="sxs-lookup"><span data-stu-id="114ed-194">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>
  
<span data-ttu-id="114ed-p113">En la clave **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0 \\Lync]**, cree un nuevo **valor DWORD (32 bits)**. El **Nombre del valor** debe ser **IsBasicTutorialSeenByUser**y los **Datos del valor** deben configurarse como **1**.</span><span class="sxs-lookup"><span data-stu-id="114ed-p113">In the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]** key, create a new **DWORD (32-bit) Value**. The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>
  
<span data-ttu-id="114ed-197">La clave debería ser similar a esta:</span><span class="sxs-lookup"><span data-stu-id="114ed-197">The key should look like the following:</span></span>
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="114ed-198">Desactivar el tutorial del cliente</span><span class="sxs-lookup"><span data-stu-id="114ed-198">Turn off the client tutorial</span></span>

<span data-ttu-id="114ed-199">Si no desea que los usuarios puedan tener acceso al tutorial, puede desactivar el tutorial del cliente con el siguiente valor de registro:</span><span class="sxs-lookup"><span data-stu-id="114ed-199">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>
  
<span data-ttu-id="114ed-p114">En la clave **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0 \\Lync]**, cree un nuevo **valor DWORD (32 bits)**. El **Nombre del valor** debe ser **TutorialFeatureEnabled**y los **Datos del valor** deben configurarse como **0**.</span><span class="sxs-lookup"><span data-stu-id="114ed-p114">In the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]** key, create a new **DWORD (32-bit) Value**. The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>
  
```PowerShell
"TutorialFeatureEnabled"=dword:00000000
```

<span data-ttu-id="114ed-202">Puede volver a activar el tutorial configurando los **Datos del valor** como **1**.</span><span class="sxs-lookup"><span data-stu-id="114ed-202">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>
  
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="114ed-203">Crear un objeto de directiva de grupo para modificar el registro en un equipo unido a un dominio</span><span class="sxs-lookup"><span data-stu-id="114ed-203">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="114ed-p115">La actualización del registro para visualizar la experiencia de cliente Lync la primera vez que el usuario inicia el cliente Skype Empresarial debe realizarse solo una vez. Si utiliza un objeto de directiva de grupo (GPO) para actualizar el registro, es necesario que defina el objeto para crear un nuevo valor en lugar de actualizar los datos de valor. Cuando se aplica el GPO, si el nuevo valor no existe, el GPO lo creará y establecerá los datos del valor en 0.</span><span class="sxs-lookup"><span data-stu-id="114ed-p115">The registry update to display the Lync client experience the first time a user launches the Skype for Business client should be done only once. If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data. When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span>
  
<span data-ttu-id="114ed-p116">El procedimiento siguiente describe cómo modificar el registro de manera que la experiencia de cliente Lync se muestre la primera vez que el usuario inicie Skype Empresarial. También puede utilizar este procedimiento para actualizar el registro para desactivar el tutorial de la pantalla de inicio de sesión como se ha descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="114ed-p116">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business. You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>
  
 <span data-ttu-id="114ed-209">**Para crear el GPO**</span><span class="sxs-lookup"><span data-stu-id="114ed-209">**To create the GPO**</span></span>
  
1. <span data-ttu-id="114ed-210">Inicie la **Consola de administración de directivas de grupo**.</span><span class="sxs-lookup"><span data-stu-id="114ed-210">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="114ed-211">Para obtener información acerca de cómo usar la consola de administración de directivas de grupo, consulte [Consola de administración de directivas de grupo](https://go.microsoft.com/fwlink/?LinkId=532759).</span><span class="sxs-lookup"><span data-stu-id="114ed-211">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](https://go.microsoft.com/fwlink/?LinkId=532759).</span></span>
    
2. <span data-ttu-id="114ed-212">Haga clic con el botón derecho en el nodo **Objetos de directiva de grupo** y seleccione **Nuevo** en el menú.</span><span class="sxs-lookup"><span data-stu-id="114ed-212">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>
    
3. <span data-ttu-id="114ed-213">En el diálogo **Nuevo GPO**, escriba un nombre para el GPO, por ejemplo, MakeLyncDefaultUIy haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="114ed-213">In the **New GPO** dialog, enter a name for the GPO, for example,MakeLyncDefaultUI, and then click **OK**.</span></span>
    
4. <span data-ttu-id="114ed-214">Haga clic con el botón derecho en el GPO nuevo que acaba de crear y seleccione **Editar** en el menú.</span><span class="sxs-lookup"><span data-stu-id="114ed-214">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>
    
5. <span data-ttu-id="114ed-215">En el **Editor de administración de directivas de grupo**, expanda **Configuración de usuario**, expanda **Preferencias**, expanda **Configuración de Windows** y seleccione el nodo **Registro**.</span><span class="sxs-lookup"><span data-stu-id="114ed-215">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>
    
6. <span data-ttu-id="114ed-216">Haga clic con el botón derecho en el nodo **Registro** y seleccione **Nuevo** > **Elemento de registro**.</span><span class="sxs-lookup"><span data-stu-id="114ed-216">Right-click on the **Registry** node, and then select **New** > **Registry Item**.</span></span>
    
7. <span data-ttu-id="114ed-217">En el diálogo **Nuevas propiedades de registro**, actualice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="114ed-217">On the **New Registry Properties** dialog, update the following:</span></span>
    
|<span data-ttu-id="114ed-218">**Campo**</span><span class="sxs-lookup"><span data-stu-id="114ed-218">**Field**</span></span>|<span data-ttu-id="114ed-219">**Valor para seleccionar o introducir**</span><span class="sxs-lookup"><span data-stu-id="114ed-219">**Value to select or enter**</span></span>|
|:-----|:-----|
|<span data-ttu-id="114ed-220">**Acción**</span><span class="sxs-lookup"><span data-stu-id="114ed-220">**Action**</span></span> <br/> |<span data-ttu-id="114ed-221">**Creación**</span><span class="sxs-lookup"><span data-stu-id="114ed-221">**Create**</span></span> <br/> |
|<span data-ttu-id="114ed-222">**Subárbol**</span><span class="sxs-lookup"><span data-stu-id="114ed-222">**Hive**</span></span> <br/> | <span data-ttu-id="114ed-223">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="114ed-223">HKEY_CURRENT_USER</span></span> <br/> |
|<span data-ttu-id="114ed-224">**Ruta de la clave**</span><span class="sxs-lookup"><span data-stu-id="114ed-224">**Key Path**</span></span> <br/> |<span data-ttu-id="114ed-225">Software\\Microsoft\\Office\\Lync</span><span class="sxs-lookup"><span data-stu-id="114ed-225">Software\\Microsoft\\Office\\Lync</span></span>  <br/> |
|<span data-ttu-id="114ed-226">**Nombre de valor**</span><span class="sxs-lookup"><span data-stu-id="114ed-226">**Value name**</span></span> <br/> |<span data-ttu-id="114ed-227">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="114ed-227">EnableSkypeUI</span></span>  <br/> |
|<span data-ttu-id="114ed-228">**Tipo de valor**</span><span class="sxs-lookup"><span data-stu-id="114ed-228">**Value type**</span></span> <br/> |<span data-ttu-id="114ed-229">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="114ed-229">REG_BINARY</span></span>  <br/> |
|<span data-ttu-id="114ed-230">**Datos del valor**</span><span class="sxs-lookup"><span data-stu-id="114ed-230">**Value data**</span></span> <br/> |<span data-ttu-id="114ed-231">00000000</span><span class="sxs-lookup"><span data-stu-id="114ed-231">00000000</span></span>  <br/> |
   
<span data-ttu-id="114ed-232">Haga clic en **Aceptar** para guardar los cambios y cierre el GPO.</span><span class="sxs-lookup"><span data-stu-id="114ed-232">Click **OK** to save your changes, and then close the GPO.</span></span>
    
<span data-ttu-id="114ed-233">A continuación, tendrá que vincular el GPO que ha creado al grupo de usuarios al que desea asignar la política, como una UO.</span><span class="sxs-lookup"><span data-stu-id="114ed-233">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>
  
 <span data-ttu-id="114ed-234">**Para usar el GPO para asignar la Directiva**</span><span class="sxs-lookup"><span data-stu-id="114ed-234">**To use the GPO to assign the policy**</span></span>
  
1. <span data-ttu-id="114ed-235">En la consola de administración de directivas de grupo, haga clic con el botón derecho en la UO a la que desea asignar la directiva y seleccione **Vincular a un GPO existente**.</span><span class="sxs-lookup"><span data-stu-id="114ed-235">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>
    
2. <span data-ttu-id="114ed-236">En el diálogo **Seleccionar GPO**, seleccione el GPO que ha creado y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="114ed-236">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>
    
3. <span data-ttu-id="114ed-237">En el equipo del usuario de destino, abra un símbolo del sistema y escriba el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="114ed-237">On the target user's computer, open a command prompt and type the following command:</span></span>
    
    <span data-ttu-id="114ed-238">**gpupdate /target:usuario**</span><span class="sxs-lookup"><span data-stu-id="114ed-238">**gpupdate /target:user**</span></span>
    
    <span data-ttu-id="114ed-p117">El mensaje "Actualizando directiva..." se muestra mientras se aplica el GPO. Cuando se ha completado, aparece el mensaje "La actualización de la directiva de usuario ha concluido satisfactoriamente".</span><span class="sxs-lookup"><span data-stu-id="114ed-p117">The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.</span></span>
    
4. <span data-ttu-id="114ed-241">En el símbolo del sistema, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="114ed-241">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="114ed-242">**gpresult /r**</span><span class="sxs-lookup"><span data-stu-id="114ed-242">**gpresult /r**</span></span>
    
    <span data-ttu-id="114ed-243">Debería ver "Objetos de directiva de grupo asignados" con el nombre del GPO que creó mostrado a continuación.</span><span class="sxs-lookup"><span data-stu-id="114ed-243">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>
    
<span data-ttu-id="114ed-p118">También puede comprobar que el GPO ha actualizado correctamente el registro en el equipo del usuario al examinar el registro. Abra el Editor del Registro y vaya a la clave **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]**. Si el GPO ha actualizado correctamente el registro, verá un valor denominado EnableSkypeUI con un valor de 0.</span><span class="sxs-lookup"><span data-stu-id="114ed-p118">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry. Open Registry Editor and navigate to the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]** key. If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="114ed-247">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="114ed-247">Related topics</span></span>
[<span data-ttu-id="114ed-248">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="114ed-248">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="114ed-249">Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype</span><span class="sxs-lookup"><span data-stu-id="114ed-249">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
