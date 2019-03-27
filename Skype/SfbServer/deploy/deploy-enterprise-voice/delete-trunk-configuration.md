---
title: Eliminar una colección existente de opciones de configuración del tronco SIP en Skype para Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
description: 'Resumen: Obtenga información sobre cómo eliminar una colección de configuraciones de tronco mediante el Skype para el Panel de Control de servidor empresarial.'
ms.openlocfilehash: da86cbaf45afa47de580c02ab74e3b0b9bb344bf
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890553"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="ed211-103">Eliminar una colección existente de opciones de configuración del tronco SIP en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="ed211-103">Delete an existing collection of SIP trunk configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="ed211-104">**Resumen:** Obtenga información sobre cómo eliminar una colección de configuraciones de tronco mediante el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="ed211-104">**Summary:** Learn how to delete a collection of trunk configuration settings by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="ed211-p101">Las opciones de configuración de los troncos SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de la red telefónica conmutada (RTC), una central de conmutación pública de IP (PBX) o un controlador de borde de sesión (SBC) en el proveedor de servicios. Estas opciones de configuración especifican:</span><span class="sxs-lookup"><span data-stu-id="ed211-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the Public Switched Telephone Network (PSTN) gateway, an IP-Public Branch eXchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>
  
- <span data-ttu-id="ed211-107">Si se debe activar la omisión de medios en los troncos.</span><span class="sxs-lookup"><span data-stu-id="ed211-107">Whether media bypass should be enabled on the trunks.</span></span>
    
- <span data-ttu-id="ed211-108">Las condiciones en las que se envían los paquetes de protocolo de control de transporte en tiempo real (RTCP).</span><span class="sxs-lookup"><span data-stu-id="ed211-108">The conditions under which Realtime Transport Control Protocol (RTCP) packets are sent.</span></span>
    
- <span data-ttu-id="ed211-109">Si se requiere el cifrado mediante el protocolo de transporte seguro en tiempo real (SRTP) en todos los troncos.</span><span class="sxs-lookup"><span data-stu-id="ed211-109">Whether or not Secure Realtime Transport Protocol (SRTP) encryption is required on each trunk.</span></span>
    
<span data-ttu-id="ed211-110">Al instalar Skype para Business Server, se crea una colección global de opciones de configuración de tronco SIP para usted.</span><span class="sxs-lookup"><span data-stu-id="ed211-110">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="ed211-111">Esta recopilación global de configuraciones no puede eliminarse.</span><span class="sxs-lookup"><span data-stu-id="ed211-111">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="ed211-112">Sin embargo, puede usar el Skype para el Panel de Control de servidor empresarial o el cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) "Restablecer" las propiedades de la colección global a sus valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="ed211-112">However, you can use the Skype for Business Server Control Panel or the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="ed211-113">Por ejemplo, si ha definido el parámetro Enable3pccRefer en True, al restablecer la recopilación global el parámetro Enable3pccRefer volverá al valor predeterminado False.</span><span class="sxs-lookup"><span data-stu-id="ed211-113">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>
  
<span data-ttu-id="ed211-p103">Los Administradores también pueden crear configuraciones de tronco personalizadas en el ámbito del sitio o en el ámbito del servicio (para una puerta de enlace PSTN individual); estas configuraciones personalizadas pueden eliminarse. Al eliminar estas configuraciones personalizadas tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ed211-p103">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed. When removing these custom settings keep the following in mind:</span></span>
  
- <span data-ttu-id="ed211-p104">Si elimina la configuración del ámbito del servicio, el tronco SIP administrado por esas configuraciones será administrado por las configuraciones aplicadas a su sitio, si existieran. Si no existen las configuraciones del sitio, esos troncos serán administrados por la recopilación global de configuraciones de tronco.</span><span class="sxs-lookup"><span data-stu-id="ed211-p104">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist. If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>
    
- <span data-ttu-id="ed211-118">Si elimina las configuraciones del ámbito del sitio, cualquier tronco SIP administrado por esas configuraciones será entonces administrado por la recopilación global de configuraciones de tronco.</span><span class="sxs-lookup"><span data-stu-id="ed211-118">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>
    
### <a name="to-remove-trunk-configuration-settings-with-skype-for-business-server-control-panel"></a><span data-ttu-id="ed211-119">Para quitar las opciones de configuración de tronco con Skype de Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="ed211-119">To remove trunk configuration settings with Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="ed211-120">En Skype para el Panel de Control de servidor empresarial, haga clic en **Enrutamiento de voz** y, a continuación, haga clic en **Configuración del tronco**.</span><span class="sxs-lookup"><span data-stu-id="ed211-120">In Skype for Business Server Control Panel, click **Voice Routing** and then click **Trunk Configuration**.</span></span>
    
2. <span data-ttu-id="ed211-p105">En la pestaña **Configuración de tronco**, seleccione la recopilación de configuraciones de tronco SIP que desea eliminar, haga clic en **Editar** y, a continuación, haga clic en **Eliminar**. Para eliminar varias recopilaciones en la misma operación, haga clic en la primera recopilación que desea eliminar, luego mantenga presionada la tecla Ctrl y haga clic en cualquier otra recopilación que desee eliminar.</span><span class="sxs-lookup"><span data-stu-id="ed211-p105">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit** and then click **Delete**. To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>
    
3. <span data-ttu-id="ed211-p106">La propiedad **Estado** para la recopilación se actualizará a **No confirmado**. Para confirmar los cambios y eliminar la recopilación, haga clic en **Confirmar** y luego en **Confirmar todo**.</span><span class="sxs-lookup"><span data-stu-id="ed211-p106">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>
    
4. <span data-ttu-id="ed211-125">En el cuadro de diálogo **Valores de configuración de voz no confirmados**, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ed211-125">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>
    
5. <span data-ttu-id="ed211-126">En el cuadro de diálogo de **Skype para el Panel de Control de Business Server** haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ed211-126">In the **Skype for Business Server Control Panel** dialog box click **OK**.</span></span>
    
6. <span data-ttu-id="ed211-127">If you change your mind and decide not to delete the collection, click **Commit** and then click **Cancel All Uncommitted Changes**.</span><span class="sxs-lookup"><span data-stu-id="ed211-127">If you change your mind and decide not to delete the collection, click **Commit** and then click **Cancel All Uncommitted Changes**.</span></span> <span data-ttu-id="ed211-128">Cuando aparezca el cuadro de diálogo de **Skype para el Panel de Control de servidor empresarial** , haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ed211-128">When the **Skype for Business Server Control Panel** dialog box appears, click **OK**.</span></span>
    
## <a name="removing-trunk-configuration-settings-by-using-skype-for-business-server-management-shell-cmdlets"></a><span data-ttu-id="ed211-129">Eliminación de opciones de configuración de tronco utilizando Skype para Cmdlets de Shell de administración de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="ed211-129">Removing Trunk Configuration Settings by Using Skype for Business Server Management Shell Cmdlets</span></span>

<span data-ttu-id="ed211-130">Puede eliminar las configuraciones de tronco con Skype para Shell de administración de servidor empresarial y el cmdlet **Remove-CsTrunkConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="ed211-130">You can delete trunk configuration settings by using Skype for Business Server Management Shell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="ed211-131">Puede ejecutar este cmdlet, ya sea desde el Skype para Shell de administración de servidor empresarial o desde una sesión remota de Skype para Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="ed211-131">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Skype for Business Server Management Shell.</span></span>
  
### <a name="to-remove-a-specified-collection-of-settings"></a><span data-ttu-id="ed211-132">Para quitar una recopilación concreta de opciones de configuración</span><span class="sxs-lookup"><span data-stu-id="ed211-132">To remove a specified collection of settings</span></span>

- <span data-ttu-id="ed211-133">El siguiente comando elimina las configuraciones de tronco aplicadas al sitio Redmond:</span><span class="sxs-lookup"><span data-stu-id="ed211-133">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>
    
  ```
  Remove-CsTrunkConfiguration -Identity site:Redmond
  ```

### <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a><span data-ttu-id="ed211-134">Quitar todas las recopilaciones aplicadas al ámbito del sitio</span><span class="sxs-lookup"><span data-stu-id="ed211-134">To remove all the collections applied to the site scope</span></span>

- <span data-ttu-id="ed211-135">Este comando elimina todas las configuraciones de tronco aplicadas al ámbito del servicio:</span><span class="sxs-lookup"><span data-stu-id="ed211-135">This command removes all the trunk configuration settings applied to the service scope:</span></span>
    
  ```
  Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration
  ```

### <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a><span data-ttu-id="ed211-136">Quitar todas las recopilaciones en las que la omisión de medios está habilitada</span><span class="sxs-lookup"><span data-stu-id="ed211-136">To remove all the collections where media bypass is enabled</span></span>

- <span data-ttu-id="ed211-137">El siguiente comando quita las configuraciones de tronco en las que la omisión de medios se ha habilitado:</span><span class="sxs-lookup"><span data-stu-id="ed211-137">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>
    
  ```
  Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration
  ```

<span data-ttu-id="ed211-138">Para obtener más información, vea el tema de ayuda para el cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="ed211-138">For more information, see the help topic for the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet.</span></span>
  

