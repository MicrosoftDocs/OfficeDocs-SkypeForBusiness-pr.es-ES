---
title: Eliminar una colección existente de opciones de configuración de tronco SIP en Skype Empresarial Server
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
description: 'Resumen: obtenga información sobre cómo eliminar una colección de opciones de configuración de tronco mediante el Panel de control de Skype Empresarial Server.'
ms.openlocfilehash: a9065304860a257a7787c557e59da38d03abfef0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836980"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="53f32-103">Eliminar una colección existente de opciones de configuración de tronco SIP en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="53f32-103">Delete an existing collection of SIP trunk configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="53f32-104">**Resumen:** Obtenga información sobre cómo eliminar una colección de opciones de configuración de tronco mediante el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="53f32-104">**Summary:** Learn how to delete a collection of trunk configuration settings by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="53f32-105">Las opciones de configuración del tronco SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de red telefónica conmutada (RTC), una central de conmutación (PBX) de IP-Public o un controlador de borde de sesión (SBC) en el proveedor de servicios.</span><span class="sxs-lookup"><span data-stu-id="53f32-105">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the Public Switched Telephone Network (PSTN) gateway, an IP-Public Branch eXchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="53f32-106">Estos valores determinan lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="53f32-106">These settings do such things as specify:</span></span>
  
- <span data-ttu-id="53f32-107">Si se debe habilitar el desvío de medios en los troncos.</span><span class="sxs-lookup"><span data-stu-id="53f32-107">Whether media bypass should be enabled on the trunks.</span></span>
    
- <span data-ttu-id="53f32-108">Condiciones en las que se envían paquetes del Protocolo de control de transporte en tiempo real (RTCP).</span><span class="sxs-lookup"><span data-stu-id="53f32-108">The conditions under which Realtime Transport Control Protocol (RTCP) packets are sent.</span></span>
    
- <span data-ttu-id="53f32-109">Indica si se requiere o no cifrado de Protocolo de transporte en tiempo real seguro (SRTP) en cada tronco.</span><span class="sxs-lookup"><span data-stu-id="53f32-109">Whether or not Secure Realtime Transport Protocol (SRTP) encryption is required on each trunk.</span></span>
    
<span data-ttu-id="53f32-110">Al instalar Skype Empresarial Server, se crea automáticamente una colección global de opciones de configuración de tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="53f32-110">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="53f32-111">Esta recopilación global de configuraciones no puede eliminarse.</span><span class="sxs-lookup"><span data-stu-id="53f32-111">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="53f32-112">Sin embargo, puede usar el Panel de control de Skype Empresarial Server o el cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) para "restablecer" los valores predeterminados de las propiedades de la colección global.</span><span class="sxs-lookup"><span data-stu-id="53f32-112">However, you can use the Skype for Business Server Control Panel or the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="53f32-113">Por ejemplo, si ha definido el parámetro Enable3pccRefer como True, cuando restablece la recopilación global el parámetro Enable3pccRefer volverá al valor predeterminado False.</span><span class="sxs-lookup"><span data-stu-id="53f32-113">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>
  
<span data-ttu-id="53f32-p103">Los Administradores también pueden crear configuraciones de tronco personalizadas en el ámbito del sitio o en el ámbito del servicio (para una puerta de enlace PSTN individual); estas configuraciones personalizadas pueden eliminarse. Al eliminar estas configuraciones personalizadas tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="53f32-p103">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed. When removing these custom settings keep the following in mind:</span></span>
  
- <span data-ttu-id="53f32-p104">Si elimina la configuración del ámbito del servicio, el tronco SIP administrado por esas configuraciones será administrado por las configuraciones aplicadas a su sitio, si existieran. Si no existen las configuraciones del sitio, esos troncos serán administrados por la recopilación global de configuraciones de tronco.</span><span class="sxs-lookup"><span data-stu-id="53f32-p104">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist. If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>
    
- <span data-ttu-id="53f32-118">Si elimina las configuraciones del ámbito del sitio, cualquier tronco SIP administrado por esas configuraciones será entonces administrado por la recopilación global de configuraciones de tronco.</span><span class="sxs-lookup"><span data-stu-id="53f32-118">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>
    
### <a name="to-remove-trunk-configuration-settings-with-skype-for-business-server-control-panel"></a><span data-ttu-id="53f32-119">Para quitar las opciones de configuración del tronco con el Panel de control de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="53f32-119">To remove trunk configuration settings with Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="53f32-120">En el Panel de control de Skype Empresarial Server, haga clic en **Enrutamiento de** voz y, a continuación, en Configuración **del tronco.**</span><span class="sxs-lookup"><span data-stu-id="53f32-120">In Skype for Business Server Control Panel, click **Voice Routing** and then click **Trunk Configuration**.</span></span>
    
2. <span data-ttu-id="53f32-p105">En la pestaña **Configuración del tronco**, seleccione la recopilación de configuraciones de tronco SIP que desea eliminar, haga clic en **Editar** y, a continuación, haga clic en **Eliminar**. Para eliminar varias recopilaciones en la misma operación, haga clic en la primera recopilación que desea eliminar, luego mantenga presionada la tecla Ctrl y haga clic en cualquier otra recopilación que desee eliminar.</span><span class="sxs-lookup"><span data-stu-id="53f32-p105">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit** and then click **Delete**. To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>
    
3. <span data-ttu-id="53f32-p106">La propiedad **Estado** de la recopilación se actualizará a **Sin confirmar**. Para confirmar los cambios y para eliminar la recopilación, haga clic en **Confirmar** y, a continuación, haga clic en **Confirmar todo**.</span><span class="sxs-lookup"><span data-stu-id="53f32-p106">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>
    
4. <span data-ttu-id="53f32-125">En el cuadro de diálogo **Configuración de voz sin confirmar**, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="53f32-125">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>
    
5. <span data-ttu-id="53f32-126">En el cuadro de diálogo Panel de **control de Skype Empresarial Server,** haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="53f32-126">In the **Skype for Business Server Control Panel** dialog box click **OK**.</span></span>
    
6. <span data-ttu-id="53f32-127">Si cambia de opinión y decide no eliminar la recopilación, haga clic en **Confirmar** y, a continuación, haga clic en **Cancelar todos los cambios no confirmados**.</span><span class="sxs-lookup"><span data-stu-id="53f32-127">If you change your mind and decide not to delete the collection, click **Commit** and then click **Cancel All Uncommitted Changes**.</span></span> <span data-ttu-id="53f32-128">Cuando aparezca el cuadro de diálogo Panel de control de **Skype Empresarial Server,** haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="53f32-128">When the **Skype for Business Server Control Panel** dialog box appears, click **OK**.</span></span>
    
## <a name="removing-trunk-configuration-settings-by-using-skype-for-business-server-management-shell-cmdlets"></a><span data-ttu-id="53f32-129">Eliminación de opciones de configuración de tronco mediante cmdlets del Shell de administración de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="53f32-129">Removing Trunk Configuration Settings by Using Skype for Business Server Management Shell Cmdlets</span></span>

<span data-ttu-id="53f32-130">Puede eliminar las opciones de configuración del tronco mediante el Shell de administración de Skype Empresarial Server y el cmdlet **Remove-CsTrunkConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="53f32-130">You can delete trunk configuration settings by using Skype for Business Server Management Shell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="53f32-131">Puede ejecutar este cmdlet desde el Shell de administración de Skype Empresarial Server o desde una sesión remota del Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="53f32-131">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Skype for Business Server Management Shell.</span></span>
  
### <a name="to-remove-a-specified-collection-of-settings"></a><span data-ttu-id="53f32-132">Para quitar una colección de configuraciones especificada</span><span class="sxs-lookup"><span data-stu-id="53f32-132">To remove a specified collection of settings</span></span>

- <span data-ttu-id="53f32-133">El siguiente comando elimina las configuraciones de tronco aplicadas al sitio Redmond:</span><span class="sxs-lookup"><span data-stu-id="53f32-133">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>
    
  ```powershell
  Remove-CsTrunkConfiguration -Identity site:Redmond
  ```

### <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a><span data-ttu-id="53f32-134">Para quitar todas las colecciones aplicadas al ámbito de sitio</span><span class="sxs-lookup"><span data-stu-id="53f32-134">To remove all the collections applied to the site scope</span></span>

- <span data-ttu-id="53f32-135">Este comando elimina todas las configuraciones de tronco aplicadas al ámbito del servicio:</span><span class="sxs-lookup"><span data-stu-id="53f32-135">This command removes all the trunk configuration settings applied to the service scope:</span></span>
    
  ```powershell
  Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration
  ```

### <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a><span data-ttu-id="53f32-136">Para quitar todas las colecciones en las que está habilitada la omisión de medios</span><span class="sxs-lookup"><span data-stu-id="53f32-136">To remove all the collections where media bypass is enabled</span></span>

- <span data-ttu-id="53f32-137">El siguiente comando elimina las configuraciones de tronco en las que el desvío de medios se ha habilitado:</span><span class="sxs-lookup"><span data-stu-id="53f32-137">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>
    
  ```powershell
  Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration
  ```

<span data-ttu-id="53f32-138">Para obtener más información, consulte el tema de ayuda del cmdlet [Remove-CsTrunkConfiguration.](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="53f32-138">For more information, see the help topic for the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet.</span></span>
  

