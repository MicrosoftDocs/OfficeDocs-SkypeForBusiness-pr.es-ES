---
title: Eliminar una colección existente de parámetros de configuración del tronco de SIP en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Los ajustes de configuración del tronco del SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de red de telefonía pública conmutada (RTC), una central de conmutación (PBX) IP o un controlador de borde de sesión (SBC) en el proveedor de servicios. '
ms.openlocfilehash: 55636cc34df4b05ccdd4b9035ef3aa4bb169e9a0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274936"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="371c5-103">Eliminar una colección existente de parámetros de configuración del tronco de SIP en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="371c5-103">Delete an existing collection of SIP trunk configuration settings in Skype for Business Server</span></span>

<span data-ttu-id="371c5-104">Los ajustes de configuración del tronco del SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de red de telefonía pública conmutada (RTC), una central de conmutación (PBX) IP o un controlador de borde de sesión (SBC) en el proveedor de servicios.</span><span class="sxs-lookup"><span data-stu-id="371c5-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="371c5-105">Estas opciones de configuración especifican:</span><span class="sxs-lookup"><span data-stu-id="371c5-105">These settings do such things as specify:</span></span>

- <span data-ttu-id="371c5-106">Si se debe activar la omisión de medios en los troncos.</span><span class="sxs-lookup"><span data-stu-id="371c5-106">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="371c5-107">Las condiciones en que se envían paquetes de protocolo de control de transporte (RTCP) en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="371c5-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="371c5-108">Si se requiere o no cifrado de protocolo en tiempo real seguro (SRTP) en cada tronco.</span><span class="sxs-lookup"><span data-stu-id="371c5-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="371c5-109">Al instalar Skype empresarial Server, se crea una colección global de parámetros de configuración del tronco del SIP.</span><span class="sxs-lookup"><span data-stu-id="371c5-109">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="371c5-110">Esta recopilación global de configuraciones no puede eliminarse.</span><span class="sxs-lookup"><span data-stu-id="371c5-110">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="371c5-111">Sin embargo, puede usar el panel de ServerControl de Skype empresarial o el cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) para "restablecer" las propiedades de la colección global a sus valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="371c5-111">However, you can use the Skype for Business ServerControl Panel or the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="371c5-112">Por ejemplo, si ha definido el parámetro Enable3pccRefer en True, al restablecer la recopilación global el parámetro Enable3pccRefer volverá al valor predeterminado False.</span><span class="sxs-lookup"><span data-stu-id="371c5-112">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>

<span data-ttu-id="371c5-p103">Los Administradores también pueden crear configuraciones de tronco personalizadas en el ámbito del sitio o en el ámbito del servicio (para una puerta de enlace PSTN individual); estas configuraciones personalizadas pueden eliminarse. Al eliminar estas configuraciones personalizadas tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="371c5-p103">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed. When removing these custom settings keep the following in mind:</span></span>

- <span data-ttu-id="371c5-p104">Si elimina la configuración del ámbito del servicio, el tronco SIP administrado por esas configuraciones será administrado por las configuraciones aplicadas a su sitio, si existieran. Si no existen las configuraciones del sitio, esos troncos serán administrados por la recopilación global de configuraciones de tronco.</span><span class="sxs-lookup"><span data-stu-id="371c5-p104">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist. If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>
- <span data-ttu-id="371c5-117">Si elimina las configuraciones del ámbito del sitio, cualquier tronco SIP administrado por esas configuraciones será entonces administrado por la recopilación global de configuraciones de tronco.</span><span class="sxs-lookup"><span data-stu-id="371c5-117">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>

<span data-ttu-id="371c5-118">**Para quitar la configuración de troncal con el panel de control de Skype empresarial Server**</span><span class="sxs-lookup"><span data-stu-id="371c5-118">**To remove trunk configuration settings with the Skype for Business Server Control Panel**</span></span> 

1. <span data-ttu-id="371c5-119">En el panel de control de Skype empresarial Server, haga clic en **enrutamiento de voz**y, a continuación, en **configuración troncal**.</span><span class="sxs-lookup"><span data-stu-id="371c5-119">In the Skype for Business Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>
2. <span data-ttu-id="371c5-120">En la pestaña **configuración de tronco** , seleccione la colección de parámetros de configuración del tronco del SIP que desea eliminar, haga clic en **Editar**y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="371c5-120">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit**, and then click **Delete**.</span></span> <span data-ttu-id="371c5-121">Para eliminar varias recopilaciones en la misma operación, haga clic en la primera recopilación que desea eliminar, luego mantenga presionada la tecla Ctrl y haga clic en cualquier otra recopilación que desee eliminar.</span><span class="sxs-lookup"><span data-stu-id="371c5-121">To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>
3. <span data-ttu-id="371c5-p106">La propiedad **Estado** para la colección se actualizará a **No confirmado**. Para confirmar los cambios y eliminar la colección, haga clic en **Confirmar** y luego en **Confirmar todo**.</span><span class="sxs-lookup"><span data-stu-id="371c5-p106">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>
4. <span data-ttu-id="371c5-124">En el cuadro de diálogo **Valores de configuración de voz no confirmados**, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="371c5-124">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>
5. <span data-ttu-id="371c5-125">En el cuadro de diálogo **Panel de control de Skype empresarial Server** , haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="371c5-125">In the **Skype for Business Server Control Panel** dialog box, click **OK**.</span></span>
6. <span data-ttu-id="371c5-126">Si cambia de opinión y decide no eliminar la colección, haga clic en **confirmar**y, a continuación, haga clic en **cancelar todos los cambios**no confirmados.</span><span class="sxs-lookup"><span data-stu-id="371c5-126">If you change your mind and decide not to delete the collection, click **Commit**, and then click **Cancel All Uncommitted Changes**.</span></span> <span data-ttu-id="371c5-127">Cuando aparezca el cuadro de diálogo **Panel de control de Skype empresarial Server** , haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="371c5-127">When the **Skype for Business Server Control Panel** dialog box appears, click **OK**.</span></span>

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="371c5-128">Quitar las opciones de configuración de troncal mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="371c5-128">Removing trunk configuration settings by using Windows PowerShell cmdlets</span></span>


<span data-ttu-id="371c5-129">Puede eliminar las opciones de configuración del tronco mediante Windows PowerShell y el cmdlet **Remove-CsTrunkConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="371c5-129">You can delete trunk configuration settings by using Windows PowerShell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="371c5-130">Puede ejecutar este cmdlet desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="371c5-130">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

<span data-ttu-id="371c5-131">**Para quitar una recopilación concreta de opciones de configuración**</span><span class="sxs-lookup"><span data-stu-id="371c5-131">**To remove a specified collection of settings**</span></span>

<span data-ttu-id="371c5-132">El siguiente comando elimina las configuraciones de tronco aplicadas al sitio Redmond:</span><span class="sxs-lookup"><span data-stu-id="371c5-132">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>

`Remove-CsTrunkConfiguration -Identity site:Redmond`

<span data-ttu-id="371c5-133">**Quitar todas las recopilaciones aplicadas al ámbito del sitio**</span><span class="sxs-lookup"><span data-stu-id="371c5-133">**To remove all the collections applied to the site scope**</span></span>

<span data-ttu-id="371c5-134">Este comando elimina todas las configuraciones de tronco aplicadas al ámbito del servicio:</span><span class="sxs-lookup"><span data-stu-id="371c5-134">This command removes all the trunk configuration settings applied to the service scope:</span></span>

`Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration`

<span data-ttu-id="371c5-135">**Quitar todas las recopilaciones en las que la omisión de medios está habilitada**</span><span class="sxs-lookup"><span data-stu-id="371c5-135">**To remove all the collections where media bypass is enabled**</span></span>

<span data-ttu-id="371c5-136">El siguiente comando quita las configuraciones de tronco en las que la omisión de medios se ha habilitado:</span><span class="sxs-lookup"><span data-stu-id="371c5-136">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>

`Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration`

<span data-ttu-id="371c5-137">Para obtener más información, consulte el tema de ayuda para el cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="371c5-137">For more information, see the help topic for the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet.</span></span>
