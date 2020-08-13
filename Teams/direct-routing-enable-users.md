---
title: Habilitar a los usuarios para el enrutamiento directo
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Aprenda a habilitar el enrutamiento directo de los usuarios de Microsoft Phone.
ms.openlocfilehash: 5fc3955430e5aa441d3c1099a86011d2b0c760f0
ms.sourcegitcommit: 875c854547b5d3ad838ad10c1eada3f0cddc8e66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656151"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a><span data-ttu-id="edbef-103">Habilitar a los usuarios para el enrutamiento directo, la voz y el buzón de voz</span><span class="sxs-lookup"><span data-stu-id="edbef-103">Enable users for Direct Routing, voice, and voicemail</span></span>

<span data-ttu-id="edbef-104">En este artículo se describe cómo habilitar a los usuarios para el enrutamiento directo del sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="edbef-104">This article describes how to enable users for Phone System Direct Routing.</span></span>  <span data-ttu-id="edbef-105">Este es el paso 2 de los siguientes pasos para configurar el enrutamiento directo:</span><span class="sxs-lookup"><span data-stu-id="edbef-105">This is step 2 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="edbef-106">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="edbef-106">Step 1.</span></span> [<span data-ttu-id="edbef-107">Conectar el SBC con Microsoft Phone System y validar la conexión</span><span class="sxs-lookup"><span data-stu-id="edbef-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="edbef-108">**Paso 2. Habilitar a los usuarios para el enrutamiento directo, la voz y el buzón de voz** (este artículo)</span><span class="sxs-lookup"><span data-stu-id="edbef-108">**Step 2. Enable users for Direct Routing, voice, and voicemail**    (This article)</span></span>
- <span data-ttu-id="edbef-109">Paso 3.</span><span class="sxs-lookup"><span data-stu-id="edbef-109">Step 3.</span></span> [<span data-ttu-id="edbef-110">Configurar el enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="edbef-110">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="edbef-111">Paso 4.</span><span class="sxs-lookup"><span data-stu-id="edbef-111">Step 4.</span></span> [<span data-ttu-id="edbef-112">Traducir números a un formato alternativo</span><span class="sxs-lookup"><span data-stu-id="edbef-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 


<span data-ttu-id="edbef-113">Para obtener información sobre todos los pasos necesarios para configurar el enrutamiento directo, consulte [configurar el enrutamiento directo](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="edbef-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

<span data-ttu-id="edbef-114">Cuando esté listo para habilitar a los usuarios para el enrutamiento directo, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="edbef-114">When you are ready to enable users for Direct Routing, follow these steps:</span></span> 

1. <span data-ttu-id="edbef-115">Cree un usuario en Microsoft 365 u Office 365 y asigne una licencia de sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="edbef-115">Create a user in Microsoft 365 or Office 365 and assign a Phone System license.</span></span> 
2. <span data-ttu-id="edbef-116">Asegúrese de que el usuario se ha alojado en Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="edbef-116">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="edbef-117">Configure el número de teléfono y habilite la telefonía IP empresarial y el buzón de voz.</span><span class="sxs-lookup"><span data-stu-id="edbef-117">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="edbef-118">Asigne el modo solo de Teams a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="edbef-118">Assign Teams Only mode to users.</span></span>

## <a name="create-a-user-and-assign-the-license"></a><span data-ttu-id="edbef-119">Crear un usuario y asignar la licencia</span><span class="sxs-lookup"><span data-stu-id="edbef-119">Create a user and assign the license</span></span> 

<span data-ttu-id="edbef-120">Existen dos opciones para crear un nuevo usuario en Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="edbef-120">There are two options for creating a new user in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="edbef-121">Sin embargo, Microsoft recomienda que su organización elija una opción para evitar problemas de enrutamiento:</span><span class="sxs-lookup"><span data-stu-id="edbef-121">However, Microsoft recommends that your organization choose one option to avoid routing issues:</span></span> 

- <span data-ttu-id="edbef-122">Crear el usuario en Active Directory local y sincronizar el usuario con la nube.</span><span class="sxs-lookup"><span data-stu-id="edbef-122">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="edbef-123">Consulte [integrar los directorios locales con Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="edbef-123">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="edbef-124">Cree directamente el usuario en el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="edbef-124">Create the user directly in the Microsoft 365 admin center.</span></span> <span data-ttu-id="edbef-125">Consulte [Agregar usuarios individualmente o de forma masiva a Microsoft 365 u Office 365: ayuda de administración](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="edbef-125">See [Add users individually or in bulk to Microsoft 365 or Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="edbef-126">Si su implementación de Skype empresarial online coexiste con Skype empresarial 2015 o Lync 2010 o 2013 local, la única opción admitida es crear el usuario en Active Directory local y sincronizar el usuario con la nube (opción 1).</span><span class="sxs-lookup"><span data-stu-id="edbef-126">If your Skype for Business Online deployment coexists with Skype for Business 2015 or Lync 2010 or 2013 on-premises, the only supported option is to create the user in the on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="edbef-127">Para obtener información sobre los requisitos de licencia, consulte [licencias y otros requisitos](direct-routing-plan.md#licensing-and-other-requirements) en [planificar enrutamiento directo](direct-routing-plan.md).</span><span class="sxs-lookup"><span data-stu-id="edbef-127">For information about license requirements, see [licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements) in [Plan Direct Routing](direct-routing-plan.md).</span></span>

## <a name="ensure-that-the-user-is-homed-online"></a><span data-ttu-id="edbef-128">Asegurarse de que el usuario está conectado en línea</span><span class="sxs-lookup"><span data-stu-id="edbef-128">Ensure that the user is homed online</span></span> 

<span data-ttu-id="edbef-129">El enrutamiento directo requiere que el usuario se conecte en línea.</span><span class="sxs-lookup"><span data-stu-id="edbef-129">Direct Routing requires the user to be homed online.</span></span> <span data-ttu-id="edbef-130">Puede consultar el parámetro RegistrarPool, que necesita tener un valor en el dominio de infra.lync.com.</span><span class="sxs-lookup"><span data-stu-id="edbef-130">You can check by looking at the RegistrarPool parameter, which needs to have a value in the infra.lync.com domain.</span></span>

1. <span data-ttu-id="edbef-131">Conéctese a PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="edbef-131">Connect to remote PowerShell.</span></span>
2. <span data-ttu-id="edbef-132">Emita el comando:</span><span class="sxs-lookup"><span data-stu-id="edbef-132">Issue the command:</span></span> 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
    ``` 

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="edbef-133">Configurar el número de teléfono y habilitar la telefonía IP empresarial y el buzón de voz</span><span class="sxs-lookup"><span data-stu-id="edbef-133">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="edbef-134">Una vez que haya creado el usuario y haya asignado una licencia, el siguiente paso es configurar el número de teléfono del usuario y el buzón de voz.</span><span class="sxs-lookup"><span data-stu-id="edbef-134">After you have created the user and assigned a license, the next step is to configure the user's phone number and voicemail.</span></span> 

<span data-ttu-id="edbef-135">Para agregar el número de teléfono y habilitar el buzón de voz:</span><span class="sxs-lookup"><span data-stu-id="edbef-135">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="edbef-136">Conectarse a una sesión de PowerShell remota.</span><span class="sxs-lookup"><span data-stu-id="edbef-136">Connect to a remote PowerShell session.</span></span> 
2. <span data-ttu-id="edbef-137">Escribe el comando:</span><span class="sxs-lookup"><span data-stu-id="edbef-137">Enter the command:</span></span> 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
    ```

    <span data-ttu-id="edbef-138">Por ejemplo, para agregar un número de teléfono para el usuario "Spencer Low", escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="edbef-138">For example, to add a phone number for user "Spencer Low," enter the following:</span></span> 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    <span data-ttu-id="edbef-139">El número de teléfono usado debe configurarse como un número de teléfono E. 164 completo con prefijo internacional.</span><span class="sxs-lookup"><span data-stu-id="edbef-139">The phone number used has to be configured as a full E.164 phone number with country code.</span></span> 

      > [!NOTE]
      > <span data-ttu-id="edbef-140">Si el número de teléfono del usuario se administra localmente, use el shell local de administración de Skype empresarial o el panel de control para configurar el número de teléfono del usuario.</span><span class="sxs-lookup"><span data-stu-id="edbef-140">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 


## <a name="configuring-sending-calls-directly-to-voicemail"></a><span data-ttu-id="edbef-141">Configurar el envío de llamadas directamente al buzón de voz</span><span class="sxs-lookup"><span data-stu-id="edbef-141">Configuring sending calls directly to voicemail</span></span>

<span data-ttu-id="edbef-142">El enrutamiento directo le permite finalizar la llamada a un usuario y enviarlo directamente al buzón de voz del usuario.</span><span class="sxs-lookup"><span data-stu-id="edbef-142">Direct Routing allows you to end the call to a user and send it directly to the user's voicemail.</span></span> <span data-ttu-id="edbef-143">Si deseas enviar la llamada directamente al buzón de voz, adjunta Opaque = App: el buzón de voz al encabezado de URI de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="edbef-143">If you want to send the call directly to voicemail, attach opaque=app:voicemail to the Request URI header.</span></span> <span data-ttu-id="edbef-144">Por ejemplo, "SIP: user@yourdomain. com; Opaque = App: buzón de voz".</span><span class="sxs-lookup"><span data-stu-id="edbef-144">For example, "sip:user@yourdomain.com;opaque=app:voicemail".</span></span> <span data-ttu-id="edbef-145">En este caso, el usuario de Teams no recibirá la notificación de llamada, la llamada se conectará al buzón de voz del usuario directamente.</span><span class="sxs-lookup"><span data-stu-id="edbef-145">In this case, the Teams user will not receive the calling notification, the call will be connected to the voicemail of the user directly.</span></span>

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a><span data-ttu-id="edbef-146">Asignar el modo solo de Teams a los usuarios para garantizar la superficie de llamadas en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="edbef-146">Assign Teams Only mode to users to ensure calls land in Microsoft Teams</span></span>

<span data-ttu-id="edbef-147">El enrutamiento directo requiere que los usuarios estén en el modo solo de equipos para garantizar las llamadas entrantes en el cliente de Teams.</span><span class="sxs-lookup"><span data-stu-id="edbef-147">Direct Routing requires that users be in Teams Only mode to ensure incoming calls land in the Teams client.</span></span> <span data-ttu-id="edbef-148">Para poner los usuarios en modo de solo equipos, asígnelos a la instancia "UpgradeToTeams" de TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="edbef-148">To put users in Teams Only mode, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> <span data-ttu-id="edbef-149">Para obtener más información, consulte [Guía de actualización para administradores de ti](upgrade-to-teams-on-prem-overview.md).</span><span class="sxs-lookup"><span data-stu-id="edbef-149">For more information, see [Upgrade guidance for IT administrators](upgrade-to-teams-on-prem-overview.md).</span></span> <span data-ttu-id="edbef-150">Si su organización usa Skype empresarial Server o Skype empresarial online, consulte el artículo siguiente para obtener información sobre la interoperabilidad entre Skype y Teams: [migración y interoperabilidad con Skype empresarial](migration-interop-guidance-for-teams-with-skype.md).</span><span class="sxs-lookup"><span data-stu-id="edbef-150">If your organization uses Skype for Business Server or Skype for Business Online, see the following article for information about interoperability between Skype and Teams: [Migration and interoperability with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="edbef-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="edbef-151">See also</span></span>

[<span data-ttu-id="edbef-152">Planear el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="edbef-152">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="edbef-153">Configurar el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="edbef-153">Configure Direct Routing</span></span>](direct-routing-configure.md)
