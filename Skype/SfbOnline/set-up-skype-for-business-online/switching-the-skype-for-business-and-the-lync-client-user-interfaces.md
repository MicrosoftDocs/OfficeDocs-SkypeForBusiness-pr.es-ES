---
title: Cambiar de la interfaz de usuario del cliente de Lync a la de Skype Empresarial
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: a2394a4c-7522-484c-a047-7b3289742be0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: None
ms.custom:
- Setup
description: 'Learn how to switch between Skype for Business and Lync client user interfaces using PowerShell in Office 365 '
ms.openlocfilehash: 27d6d29f3a3e8528e0d9c5076249ff821a5c666d
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568377"
---
# <a name="switching-between-the-skype-for-business-and-the-lync-client-user-interfaces"></a><span data-ttu-id="aedf6-103">Cambiar de la interfaz de usuario del cliente de Lync a la de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="aedf6-103">Switching between the Skype for Business and the Lync client user interfaces</span></span>

<span data-ttu-id="aedf6-104">Para Skype para las organizaciones empresariales en línea, puede usar PowerShell remoto en Office 365 para habilitar su Skype para usuarios profesionales que se usará el Skype para clientes empresariales o la Skype para la interfaz de usuario de cliente empresarial (Lync).</span><span class="sxs-lookup"><span data-stu-id="aedf6-104">For Skype for Business Online organizations, you can use the Remote PowerShell in Office 365 to enable your Skype for Business users to use the Skype for Business client or the Skype for Business (Lync) client user interface.</span></span> <span data-ttu-id="aedf6-105">El valor predeterminado es para que los usuarios usen la Skype para la interfaz de usuario de cliente de negocio.</span><span class="sxs-lookup"><span data-stu-id="aedf6-105">The default setting is for users to use the Skype for Business client user interface.</span></span> <span data-ttu-id="aedf6-106">Si prefiere usar la experiencia del cliente Lync, puede administrar el comportamiento del cliente primer inicio para mostrar la interfaz de usuario de Lync siguiendo los pasos descritos más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="aedf6-106">If you'd prefer to use the Lync client experience, you can manage the first launch client behavior to display the Lync user interface by following the steps later in this topic.</span></span>
  
> [!NOTE]
> <span data-ttu-id="aedf6-p102">La experiencia de cliente con Lync 2013 no está disponible en las versiones de cliente de Skype Empresarial 2016. Antes de que intente configurar su entorno de cliente para usar el cliente de Lync 2013, compruebe la versión y asegúrese de que no empieza con el número 16; por ejemplo: 16.x.x.x.</span><span class="sxs-lookup"><span data-stu-id="aedf6-p102">The Lync 2013 client experience isn't an option for Skype for Business 2016 client versions. Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span> 
  
> [!TIP]
> <span data-ttu-id="aedf6-109">Si desea cambiar fácilmente la interfaz de usuario y no desea realizar los pasos manuales, mire el [Centro de descarga de Microsoft ](https://go.microsoft.com/fwlink/?LinkId=532431) para obtener un script de PowerShell y facilitar la tarea.</span><span class="sxs-lookup"><span data-stu-id="aedf6-109">If you want to easily switch the user interface and don't want to do the manual steps, see the [Microsoft Download Center ](https://go.microsoft.com/fwlink/?LinkId=532431) for a PowerShell script to make it easier.</span></span>
  
## <a name="switching-the-skype-for-business-user-interface-for-users"></a><span data-ttu-id="aedf6-110">Cambio de la interfaz de usuario de Skype Empresarial para los usuarios</span><span class="sxs-lookup"><span data-stu-id="aedf6-110">Switching the Skype for Business user interface for users</span></span>

<span data-ttu-id="aedf6-p103">El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta a Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688). Para otra información, consulte [Cómo configurar el equipo para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=534539).</span><span class="sxs-lookup"><span data-stu-id="aedf6-p103">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). For other information, see [Configuring your computer for Skype for Business Online management](https://go.microsoft.com/fwlink/?LinkId=534539).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="aedf6-p104">La configuración de la directiva  _Global_ para cambiar la interfaz de usuario no se aplicará a un usuario que ya tenga aplicada una directiva personalizada. Para poder cambiar la interfaz de usuario, tendrá que ejecutar lo siguiente para cada usuario que tenga aplicada una directiva personalizada:</span><span class="sxs-lookup"><span data-stu-id="aedf6-p104">The  _Global_ policy setting for switching the user interface won't be applied to a user that already has a custom policy applied. To be able to change the user interface, you will need to run the following for each user that has a custom policy applied:</span></span>
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

> [!CAUTION]
> <span data-ttu-id="aedf6-116">La directiva  _ClientPolicyEnableSkypeUI_ sustituirá a la configuración de la directiva personalizada existente para el usuario.</span><span class="sxs-lookup"><span data-stu-id="aedf6-116">The  _ClientPolicyEnableSkypeUI_ policy will replace the existing custom policy setting for the user.</span></span>
  
<span data-ttu-id="aedf6-117">Para habilitar que todos los usuarios de su organización utilicen el cliente de Skype Empresarial, abra el PowerShell remoto y escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="aedf6-117">To enable all of the users in your organization to use the Skype for Business client, open the Remote PowerShell and type the following:</span></span>
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

<span data-ttu-id="aedf6-118">Si configura la directiva de forma correcta, verá:</span><span class="sxs-lookup"><span data-stu-id="aedf6-118">If you set the policy right, you will see:</span></span>
  
![PowerShell: SkypeUIEnabled](../images/b6b9d2e1-1a37-46df-9757-f81c6054e93b.png)
  
<span data-ttu-id="aedf6-120">Para habilitar que todos los usuarios de su organización utilicen el cliente de Skype Empresarial (Lync), abra el PowerShell remoto y escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="aedf6-120">To enable all of the users in your organization to use the Skype for Business (Lync) client, open the Remote PowerShell and type the following:</span></span> 
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

<span data-ttu-id="aedf6-121">Si configura la directiva de forma correcta, verá:</span><span class="sxs-lookup"><span data-stu-id="aedf6-121">If you set the policy right, you will see:</span></span>
  
![PowerShell: SkypeUIDisabled](../images/f14ec3ce-4eb8-4a11-826e-6029043ed054.png)
  
<span data-ttu-id="aedf6-123">Para permitir que solo un usuario de su organización utilice el cliente de Skype Empresarial, abra el PowerShell remoto y escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="aedf6-123">To allow a single user in your organization to use the Skype for Business client, open the Remote PowerShell and type the following:</span></span>
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

<span data-ttu-id="aedf6-124">Si configura la directiva de forma correcta, verá:</span><span class="sxs-lookup"><span data-stu-id="aedf6-124">If you set the policy right, you will see:</span></span>
  
![Skype Empresarial Online - Activar IU](../images/596aef69-41dc-4e1e-b689-2b7009ae58a1.png)
  
<span data-ttu-id="aedf6-126">Para permitir que solo un usuario de su organización utilice el cliente de Skype Empresarial (Lync), abra el PowerShell remoto y escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="aedf6-126">To allow a single user in your organization to use the Skype for Business (Lync) client, open the Remote PowerShell and type the following:</span></span>
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI -Identity <username>
```

<span data-ttu-id="aedf6-127">Si configura la directiva de forma correcta, verá:</span><span class="sxs-lookup"><span data-stu-id="aedf6-127">If you set the policy right, you will see:</span></span>
  
![Skype Empresarial Online - IU deshabilitada](../images/61c645e0-67fc-4e03-803c-b7028a47dae3.png)
  
<span data-ttu-id="aedf6-129">Para permitir que varios usuarios de su organización utilicen el cliente de Skype Empresarial, abra el PowerShell remoto y escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="aedf6-129">To allow multiple users in your organization to use the Skype for Business client, open the Remote PowerShell and type the following:</span></span>
  

```
$users = @("sip:bob@contoso.com","sip:fred@contoso.com") 

$users | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

<span data-ttu-id="aedf6-130">Para permitir que varios usuarios de su organización utilicen el cliente de Skype Empresarial (Lync), abra el PowerShell remoto y escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="aedf6-130">To allow multiple users in your organization to use the Skype for Business (Lync) client, open the Remote PowerShell and type the following:</span></span>
  
```
$users = @("sip:bob@contoso.com","sip:fred@contoso.com")

$users | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

<span data-ttu-id="aedf6-131">Para permitir que un grupo de usuarios de su organización utilice el cliente de Skype Empresarial, abra el PowerShell remoto y escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="aedf6-131">To allow a group of users in your organization to use the Skype for Business client, open the Remote PowerShell and type the following:</span></span>
  
```
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

<span data-ttu-id="aedf6-132">Para permitir que un grupo de usuarios de su organización utilice el cliente de Skype Empresarial (Lync), abra el PowerShell remoto y escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="aedf6-132">To allow a group of users in your organization to use the Skype for Business (Lync) client, open the Remote PowerShell and type the following:</span></span>
  
```
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

> [!NOTE]
>  <span data-ttu-id="aedf6-p105">El nombre del usuario es el nombre de la cuenta del usuario a la cual se asignará la directiva. El nombre de la cuenta del usuario se puede introducir en uno de los siguientes formatos:>  Dirección SIP del usuario>  Nombre principal de usuario (UPN) del usuario>  Dominio\\nombre de usuario del usuario>  Nombre para mostrar de Active Directory del usuario</span><span class="sxs-lookup"><span data-stu-id="aedf6-p105">The user's name is the name of the user's account that the policy should be assigned to. The user's account name can be entered in one of the following formats:>  SIP address of the user>  User Principal name (UPN) of the user>  Domain\\username of the user>  Active Directory display name of the user</span></span>
  
[<span data-ttu-id="aedf6-135">Uso de Windows PowerShell para administrar Lync Online</span><span class="sxs-lookup"><span data-stu-id="aedf6-135">Using Windows PowerShell to manage Lync Online</span></span>](https://go.microsoft.com/fwlink/?LinkID=525453)
  
## <a name="skype-for-business-online-policy-settings"></a><span data-ttu-id="aedf6-136">Configuración de directivas de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="aedf6-136">Skype for Business Online policy settings</span></span>

<span data-ttu-id="aedf6-137">Esta tabla muestra la experiencia de usuario cuando la directiva se aplica primero a los usuarios:</span><span class="sxs-lookup"><span data-stu-id="aedf6-137">This table shows the user experience when the policy is first applied to users:</span></span>
  
|<span data-ttu-id="aedf6-138">**Configuración de la directiva de administrador**</span><span class="sxs-lookup"><span data-stu-id="aedf6-138">**Admin policy setting**</span></span>|<span data-ttu-id="aedf6-139">**Interfaz de usuario que se muestra**</span><span class="sxs-lookup"><span data-stu-id="aedf6-139">**User interface displayed**</span></span>|
|:-----|:-----|
|<span data-ttu-id="aedf6-140">La directiva no está configurada.</span><span class="sxs-lookup"><span data-stu-id="aedf6-140">The policy isn't set.</span></span> |<span data-ttu-id="aedf6-141">El usuario continuará utilizando la interfaz de usuario del cliente de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="aedf6-141">The user will continue using the Skype for Business client user interface.</span></span>|
|`Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI`<br/>|<span data-ttu-id="aedf6-142">El usuario continuará utilizando la interfaz de usuario del cliente de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="aedf6-142">The user will continue using the Skype for Business client user interface.</span></span>|
|`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`<br/>|<span data-ttu-id="aedf6-p106">Se le solicitará al usuario cambiar a la interfaz de usuario del cliente de Skype Empresarial (Lync). Pueden realizar el cambio más tarde.</span><span class="sxs-lookup"><span data-stu-id="aedf6-p106">The user will be asked to switch to the Skype for Business (Lync) client user interface. They can switch later.</span></span>|
|`Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>`|<span data-ttu-id="aedf6-145">El usuario utilizará la interfaz de usuario del cliente de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="aedf6-145">The user will be using the Skype for Business client user interface.</span></span> |
`Grant-CsClientPolicy-PolicyName ClientPolicyDisableSkypeUI -Identity <username>`|<span data-ttu-id="aedf6-146">Para cambiar a la Skype para la interfaz de usuario de cliente empresarial (Lync) se pedirá al usuario.</span><span class="sxs-lookup"><span data-stu-id="aedf6-146">The user will be asked to switch to the Skype for Business (Lync) client user interface.</span></span> <span data-ttu-id="aedf6-147">Un administrador puede cambiar la configuración en el futuro, por lo que cambiará la interfaz de usuario del cliente de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="aedf6-147">An admin can change the setting in the future that will switch them to the Skype for Business client user interface.</span></span> |
   
<span data-ttu-id="aedf6-148">Esta tabla muestra la experiencia de usuario cuando se cambia la directiva:</span><span class="sxs-lookup"><span data-stu-id="aedf6-148">This table shows the user experience when the policy is changed:</span></span>
  
|<span data-ttu-id="aedf6-149">**Configuración de la directiva de administrador**</span><span class="sxs-lookup"><span data-stu-id="aedf6-149">**Admin policy setting**</span></span>|<span data-ttu-id="aedf6-150">**Interfaz de usuario de Skype Empresarial (Lync)**</span><span class="sxs-lookup"><span data-stu-id="aedf6-150">**Skype for Business (Lync) user interface**</span></span>|<span data-ttu-id="aedf6-151">**Interfaz de usuario de Skype Empresarial**</span><span class="sxs-lookup"><span data-stu-id="aedf6-151">**Skype for Business user interface**</span></span>|
|:-----|:-----|:-----|
|`Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI`|<span data-ttu-id="aedf6-152">Se le solicitará al usuario cambiar a la interfaz de usuario del cliente de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="aedf6-152">The user will be asked to switch to the Skype for Business client user interface.</span></span>  <br/> |<span data-ttu-id="aedf6-153">El usuario seguirá utilizando la interfaz de usuario del cliente de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="aedf6-153">The user will continue to use the Skype for Business client user interface.</span></span>  <br/> |
|`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`|<span data-ttu-id="aedf6-154">El usuario seguirán usando la Skype para la interfaz de negocio (Lync).</span><span class="sxs-lookup"><span data-stu-id="aedf6-154">The user will continue to use the Skype for Business (Lync) interface.</span></span>  <br/> |<span data-ttu-id="aedf6-155">Para cambiar a la Skype para la interfaz de usuario de cliente empresarial (Lync) se pedirá al usuario.</span><span class="sxs-lookup"><span data-stu-id="aedf6-155">The user will be asked to switch to the Skype for Business (Lync) client user interface.</span></span>  <br/> |
|<span data-ttu-id="aedf6-156">La directiva no está configurada.</span><span class="sxs-lookup"><span data-stu-id="aedf6-156">The policy isn't set.</span></span>  <br/> |<span data-ttu-id="aedf6-157">Los usuarios nunca verán el Skype para la interfaz de usuario de cliente empresarial (Lync) si no se establece la directiva.</span><span class="sxs-lookup"><span data-stu-id="aedf6-157">Users will never see the Skype for Business (Lync) client user interface if the policy is not set.</span></span> <span data-ttu-id="aedf6-158">Siempre utilizarán la interfaz de usuario del cliente de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="aedf6-158">They will always use the Skype for Business client user interface.</span></span>  <br/> |<span data-ttu-id="aedf6-159">El usuario seguirá utilizando la interfaz de usuario del cliente de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="aedf6-159">The user will continue to use the Skype for Business client user interface.</span></span>  <br/> |
   
<span data-ttu-id="aedf6-p109">Esta tabla muestra todas las directivas personalizadas disponibles en línea. Hay nuevas políticas creadas para dar flexibilidad a los administradores para que conserven la antigua directiva personalizada al cambiar entre las marcas EnableSkypeUI. Use los cmdlets de arriba para conceder una de las siguientes directivas a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="aedf6-p109">This table shows all the Online custom policies available. There are new policies created to give admins flexibility in retaining the old custom policy while switching between the EnableSkypeUI flags. Please use the cmdlets from above to grant one of the below policies to your users.</span></span>
  
|<span data-ttu-id="aedf6-163">**Nombre de la directiva**</span><span class="sxs-lookup"><span data-stu-id="aedf6-163">**Policy name**</span></span>|<span data-ttu-id="aedf6-164">**EnableSkypeUI**</span><span class="sxs-lookup"><span data-stu-id="aedf6-164">**EnableSkypeUI**</span></span>|
|:-----|:-----|
`ClientPolicyDefaultPhoto`||
`ClientPolicyDefaultPhotoDisableSkypeUI` |<span data-ttu-id="aedf6-165">Falsa</span><span class="sxs-lookup"><span data-stu-id="aedf6-165">False</span></span>|
`ClientPolicyNoIMURL`||
`ClientPolicyNoIMURLDisableSkypeUI` |<span data-ttu-id="aedf6-166">Falsa</span><span class="sxs-lookup"><span data-stu-id="aedf6-166">False</span></span>|
`ClientPolicyNoIMURLPhoto`||
`ClientPolicyNoIMURLPhotoDisableSkypeUI` |<span data-ttu-id="aedf6-167">Falsa</span><span class="sxs-lookup"><span data-stu-id="aedf6-167">False</span></span>|
`ClientPolicyNoSaveIMNoArchivingI`||
`ClientPolicyNoSaveIMNoArchivingDisableSkypeUI` |<span data-ttu-id="aedf6-168">Falsa</span><span class="sxs-lookup"><span data-stu-id="aedf6-168">False</span></span>|
`ClientPolicyNoSaveIMNoArchivingNoIMURL`||
`ClientPolicyNoSaveIMNoArchivingNoIMURLDisableSkypeUI` |<span data-ttu-id="aedf6-169">Falsa</span><span class="sxs-lookup"><span data-stu-id="aedf6-169">False</span></span>|
`ClientPolicyNoSaveIMNoArchivingNoIMURLPhoto` ||
`ClientPolicyNoSaveIMNoArchivingNoIMURLPhotoDisableSkypeUI`|<span data-ttu-id="aedf6-170">Falsa</span><span class="sxs-lookup"><span data-stu-id="aedf6-170">False</span></span>|
`ClientPolicyNoSaveIMNoArchivingPhoto`||
`ClientPolicyNoSaveIMNoArchivingPhotoDisableSkypeUI` |<span data-ttu-id="aedf6-171">Falsa</span><span class="sxs-lookup"><span data-stu-id="aedf6-171">False</span></span>|

   
<span data-ttu-id="aedf6-172">To get started with Windows PowerShell, see these topics:</span><span class="sxs-lookup"><span data-stu-id="aedf6-172">To get started with Windows PowerShell, see these topics:</span></span>
  
- [<span data-ttu-id="aedf6-173">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="aedf6-173">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- [<span data-ttu-id="aedf6-174">Las mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="aedf6-174">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
## <a name="first-launch-client-behaviors"></a><span data-ttu-id="aedf6-175">Comportamientos de los clientes al iniciarse por primera vez</span><span class="sxs-lookup"><span data-stu-id="aedf6-175">First launch client behaviors</span></span>

<span data-ttu-id="aedf6-176">De forma predeterminada, cuando los usuarios iniciar Skype para la empresa por primera vez, siempre verán la Skype para la interfaz de usuario de negocio--incluso si ha seleccionado la experiencia del cliente Lync mediante la configuración de la directiva de cliente para la experiencia del cliente Lync (`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`) tal como se describe anteriormente.</span><span class="sxs-lookup"><span data-stu-id="aedf6-176">By default, when users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the client policy to the Lync client experience (`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`) as described previously.</span></span> <span data-ttu-id="aedf6-177">Después de varios minutos, se les solicitará a los usuarios que cambien al modo Lync.</span><span class="sxs-lookup"><span data-stu-id="aedf6-177">After several minutes, users will then be asked to switch to Lync mode.</span></span>
  
<span data-ttu-id="aedf6-178">Si desea mostrar la interfaz de usuario de Lync cuando los usuarios inician el cliente Skype Empresarial por primera vez, siga estos pasos antes de que el cliente se inicie por primera vez después de la actualización:</span><span class="sxs-lookup"><span data-stu-id="aedf6-178">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>
  
1. <span data-ttu-id="aedf6-179">Siga los pasos descritos anteriormente en este tema y confirme que la directiva de cliente está configurada para deshabilitar la interfaz de usuario de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="aedf6-179">Follow the steps earlier in this topic and confirm that the client policy is set to disable the Skype for Business user interface.</span></span>
    
2. <span data-ttu-id="aedf6-p111">Actualice el registro del sistema en el equipo del usuario. Hágalo una sola vez antes de que los usuarios inicien el cliente Skype Empresarial por primera vez. Para obtener información sobre cómo crear un objeto de directiva de grupo para actualizar el registro en un equipo unido a un dominio, consulte la sección correspondiente en este mismo tema.</span><span class="sxs-lookup"><span data-stu-id="aedf6-p111">Update the system registry on the user's computer. You should do this before the first time users launch the Skype for Business client, and you should do this only once. For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="aedf6-183">En la clave **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]**, cree un nuevo valor **Binario**.</span><span class="sxs-lookup"><span data-stu-id="aedf6-183">In the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="aedf6-184">El **Nombre del valor** debe ser **EnableSkypeUI** y los **Datos del valor** deben configurarse como **00 00 00 00**.</span><span class="sxs-lookup"><span data-stu-id="aedf6-184">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="aedf6-185">La clave debería ser similar a esta:</span><span class="sxs-lookup"><span data-stu-id="aedf6-185">The key should look like the following:</span></span>
    
    <span data-ttu-id="aedf6-186">[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]</span><span class="sxs-lookup"><span data-stu-id="aedf6-186">[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]</span></span>
    
    <span data-ttu-id="aedf6-187">"CanSharePptInCollab" = dword: 00000001</span><span class="sxs-lookup"><span data-stu-id="aedf6-187">"CanSharePptInCollab"=dword:00000001</span></span>
    
    <span data-ttu-id="aedf6-188">"CanShareOneNoteInCollab" = dword: 00000001</span><span class="sxs-lookup"><span data-stu-id="aedf6-188">"CanShareOneNoteInCollab"=dword:00000001</span></span>
    
    <span data-ttu-id="aedf6-189">"CanAppShareInCollab" = dword: 00000001</span><span class="sxs-lookup"><span data-stu-id="aedf6-189">"CanAppShareInCollab"=dword:00000001</span></span>
    
    <span data-ttu-id="aedf6-190">"EnableSkypeUI" = hex: 00, 00, 00, 00</span><span class="sxs-lookup"><span data-stu-id="aedf6-190">"EnableSkypeUI"=hex:00,00,00,00</span></span>
    
<span data-ttu-id="aedf6-191">La interfaz de usuario de Lync se mostrará ahora cuando los usuarios inicien el cliente Skype Empresarial por primera vez.</span><span class="sxs-lookup"><span data-stu-id="aedf6-191">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="aedf6-192">Controlar la visualización del tutorial de la pantalla de inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="aedf6-192">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="aedf6-193">Cuando los usuarios abren la Skype para clientes empresariales, el comportamiento predeterminado es mostrar una pantalla de bienvenida que incluye la *mayoría de las personas formular a 7 sugerencias rápidas para*.</span><span class="sxs-lookup"><span data-stu-id="aedf6-193">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="aedf6-194">Puede desactivar la visualización de la pantalla de inicio de sesión, pero puede permitir que los usuarios sigan teniendo acceso al tutorial agregando el siguiente valor de registro en el equipo del cliente:</span><span class="sxs-lookup"><span data-stu-id="aedf6-194">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>
  
<span data-ttu-id="aedf6-p113">En la clave **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0 \\Lync]**, cree un nuevo **valor DWORD (32 bits)**. El **Nombre del valor** debe ser **IsBasicTutorialSeenByUser**y los **Datos del valor** deben configurarse como **1**.</span><span class="sxs-lookup"><span data-stu-id="aedf6-p113">In the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]** key, create a new **DWORD (32-bit) Value**. The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>
  
<span data-ttu-id="aedf6-197">La clave debería ser similar a esta:</span><span class="sxs-lookup"><span data-stu-id="aedf6-197">The key should look like the following:</span></span>
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="aedf6-198">Desactivar el tutorial del cliente</span><span class="sxs-lookup"><span data-stu-id="aedf6-198">Turn off the client tutorial</span></span>

<span data-ttu-id="aedf6-199">Si no desea que los usuarios puedan tener acceso al tutorial, puede desactivar el tutorial del cliente con el siguiente valor de registro:</span><span class="sxs-lookup"><span data-stu-id="aedf6-199">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>
  
<span data-ttu-id="aedf6-p114">En la clave **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0 \\Lync]**, cree un nuevo **valor DWORD (32 bits)**. El **Nombre del valor** debe ser **TutorialFeatureEnabled**y los **Datos del valor** deben configurarse como **0**.</span><span class="sxs-lookup"><span data-stu-id="aedf6-p114">In the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]** key, create a new **DWORD (32-bit) Value**. The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>
  
```
"TutorialFeatureEnabled"=dword:00000000
```

<span data-ttu-id="aedf6-202">Puede volver a activar el tutorial configurando los **Datos del valor** como **1**.</span><span class="sxs-lookup"><span data-stu-id="aedf6-202">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>
  
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="aedf6-203">Crear un objeto de directiva de grupo para modificar el registro en un equipo unido a un dominio</span><span class="sxs-lookup"><span data-stu-id="aedf6-203">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="aedf6-p115">La actualización del registro para visualizar la experiencia de cliente Lync la primera vez que el usuario inicia el cliente Skype Empresarial debe realizarse solo una vez. Si utiliza un objeto de directiva de grupo (GPO) para actualizar el registro, es necesario que defina el objeto para crear un nuevo valor en lugar de actualizar los datos de valor. Cuando se aplica el GPO, si el nuevo valor no existe, el GPO lo creará y establecerá los datos del valor en 0.</span><span class="sxs-lookup"><span data-stu-id="aedf6-p115">The registry update to display the Lync client experience the first time a user launches the Skype for Business client should be done only once. If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data. When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span>
  
<span data-ttu-id="aedf6-p116">El procedimiento siguiente describe cómo modificar el registro de manera que la experiencia de cliente Lync se muestre la primera vez que el usuario inicie Skype Empresarial. También puede utilizar este procedimiento para actualizar el registro para desactivar el tutorial de la pantalla de inicio de sesión como se ha descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="aedf6-p116">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business. You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>
  
 <span data-ttu-id="aedf6-209">**Para crear el GPO**</span><span class="sxs-lookup"><span data-stu-id="aedf6-209">**To create the GPO**</span></span>
  
1. <span data-ttu-id="aedf6-210">Inicie la **Consola de administración de directivas de grupo**.</span><span class="sxs-lookup"><span data-stu-id="aedf6-210">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="aedf6-211">Para obtener información acerca de cómo usar la consola de administración de directivas de grupo, consulte [Consola de administración de directivas de grupo](https://go.microsoft.com/fwlink/?LinkId=532759).</span><span class="sxs-lookup"><span data-stu-id="aedf6-211">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](https://go.microsoft.com/fwlink/?LinkId=532759).</span></span>
    
2. <span data-ttu-id="aedf6-212">Haga clic con el botón derecho en el nodo **Objetos de directiva de grupo** y seleccione **Nuevo** en el menú.</span><span class="sxs-lookup"><span data-stu-id="aedf6-212">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>
    
3. <span data-ttu-id="aedf6-213">En el diálogo **Nuevo GPO**, escriba un nombre para el GPO, por ejemplo, MakeLyncDefaultUIy haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="aedf6-213">In the **New GPO** dialog, enter a name for the GPO, for example,MakeLyncDefaultUI, and then click **OK**.</span></span>
    
4. <span data-ttu-id="aedf6-214">Haga clic con el botón derecho en el GPO nuevo que acaba de crear y seleccione **Editar** en el menú.</span><span class="sxs-lookup"><span data-stu-id="aedf6-214">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>
    
5. <span data-ttu-id="aedf6-215">En el **Editor de administración de directivas de grupo**, expanda **Configuración de usuario**, expanda **Preferencias**, expanda **Configuración de Windows** y seleccione el nodo **Registro**.</span><span class="sxs-lookup"><span data-stu-id="aedf6-215">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>
    
6. <span data-ttu-id="aedf6-216">Haga clic con el botón derecho en el nodo **Registro** y seleccione **Nuevo** > **Elemento de registro**.</span><span class="sxs-lookup"><span data-stu-id="aedf6-216">Right-click on the **Registry** node, and then select **New** > **Registry Item**.</span></span>
    
7. <span data-ttu-id="aedf6-217">En el diálogo **Nuevas propiedades de registro**, actualice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="aedf6-217">On the **New Registry Properties** dialog, update the following:</span></span>
    
|<span data-ttu-id="aedf6-218">**Campo**</span><span class="sxs-lookup"><span data-stu-id="aedf6-218">**Field**</span></span>|<span data-ttu-id="aedf6-219">**Valor para seleccionar o introducir**</span><span class="sxs-lookup"><span data-stu-id="aedf6-219">**Value to select or enter**</span></span>|
|:-----|:-----|
|<span data-ttu-id="aedf6-220">**Acción**</span><span class="sxs-lookup"><span data-stu-id="aedf6-220">**Action**</span></span> <br/> |<span data-ttu-id="aedf6-221">**Creación**</span><span class="sxs-lookup"><span data-stu-id="aedf6-221">**Create**</span></span> <br/> |
|<span data-ttu-id="aedf6-222">**Subárbol**</span><span class="sxs-lookup"><span data-stu-id="aedf6-222">**Hive**</span></span> <br/> | <span data-ttu-id="aedf6-223">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="aedf6-223">HKEY_CURRENT_USER</span></span> <br/> |
|<span data-ttu-id="aedf6-224">**Ruta de la clave**</span><span class="sxs-lookup"><span data-stu-id="aedf6-224">**Key Path**</span></span> <br/> |<span data-ttu-id="aedf6-225">Software\\Microsoft\\Office\\Lync</span><span class="sxs-lookup"><span data-stu-id="aedf6-225">Software\\Microsoft\\Office\\Lync</span></span>  <br/> |
|<span data-ttu-id="aedf6-226">**Nombre de valor**</span><span class="sxs-lookup"><span data-stu-id="aedf6-226">**Value name**</span></span> <br/> |<span data-ttu-id="aedf6-227">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="aedf6-227">EnableSkypeUI</span></span>  <br/> |
|<span data-ttu-id="aedf6-228">**Tipo de valor**</span><span class="sxs-lookup"><span data-stu-id="aedf6-228">**Value type**</span></span> <br/> |<span data-ttu-id="aedf6-229">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="aedf6-229">REG_BINARY</span></span>  <br/> |
|<span data-ttu-id="aedf6-230">**Datos del valor**</span><span class="sxs-lookup"><span data-stu-id="aedf6-230">**Value data**</span></span> <br/> |<span data-ttu-id="aedf6-231">00000000</span><span class="sxs-lookup"><span data-stu-id="aedf6-231">00000000</span></span>  <br/> |
   
<span data-ttu-id="aedf6-232">Haga clic en **Aceptar** para guardar los cambios y cierre el GPO.</span><span class="sxs-lookup"><span data-stu-id="aedf6-232">Click **OK** to save your changes, and then close the GPO.</span></span>
    
<span data-ttu-id="aedf6-233">A continuación, tendrá que vincular el GPO que ha creado al grupo de usuarios al que desea asignar la política, como una UO.</span><span class="sxs-lookup"><span data-stu-id="aedf6-233">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>
  
 <span data-ttu-id="aedf6-234">**Para usar el GPO para asignar la directiva**</span><span class="sxs-lookup"><span data-stu-id="aedf6-234">**To use the GPO to assign the policy**</span></span>
  
1. <span data-ttu-id="aedf6-235">En la consola de administración de directivas de grupo, haga clic con el botón derecho en la UO a la que desea asignar la directiva y seleccione **Vincular a un GPO existente**.</span><span class="sxs-lookup"><span data-stu-id="aedf6-235">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>
    
2. <span data-ttu-id="aedf6-236">En el diálogo **Seleccionar GPO**, seleccione el GPO que ha creado y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="aedf6-236">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>
    
3. <span data-ttu-id="aedf6-237">En el equipo del usuario de destino, abra un símbolo del sistema y escriba el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="aedf6-237">On the target user's computer, open a command prompt and type the following command:</span></span>
    
    <span data-ttu-id="aedf6-238">**gpupdate /target:usuario**</span><span class="sxs-lookup"><span data-stu-id="aedf6-238">**gpupdate /target:user**</span></span>
    
    <span data-ttu-id="aedf6-p117">El mensaje "Actualizando directiva..." se muestra mientras se aplica el GPO. Cuando se ha completado, aparece el mensaje "La actualización de la directiva de usuario ha concluido satisfactoriamente".</span><span class="sxs-lookup"><span data-stu-id="aedf6-p117">The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.</span></span>
    
4. <span data-ttu-id="aedf6-241">En el símbolo del sistema, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="aedf6-241">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="aedf6-242">**gpresult /r**</span><span class="sxs-lookup"><span data-stu-id="aedf6-242">**gpresult /r**</span></span>
    
    <span data-ttu-id="aedf6-243">Debería ver "Objetos de directiva de grupo asignados" con el nombre del GPO que creó mostrado a continuación.</span><span class="sxs-lookup"><span data-stu-id="aedf6-243">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>
    
<span data-ttu-id="aedf6-p118">También puede comprobar que el GPO ha actualizado correctamente el registro en el equipo del usuario al examinar el registro. Abra el Editor del Registro y vaya a la clave **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]**. Si el GPO ha actualizado correctamente el registro, verá un valor denominado EnableSkypeUI con un valor de 0.</span><span class="sxs-lookup"><span data-stu-id="aedf6-p118">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry. Open Registry Editor and navigate to the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]** key. If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="aedf6-247">See also</span><span class="sxs-lookup"><span data-stu-id="aedf6-247">Related topics</span></span>
[<span data-ttu-id="aedf6-248">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="aedf6-248">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="aedf6-249">Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype</span><span class="sxs-lookup"><span data-stu-id="aedf6-249">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 