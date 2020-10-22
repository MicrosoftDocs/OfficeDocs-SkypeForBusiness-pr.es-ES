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
ms.openlocfilehash: 5739797649c639e3259c6972da665ae0ced4b4bf
ms.sourcegitcommit: 0a9c5c01b37a93eecc369ca0ed49ae18f6a5065b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2020
ms.locfileid: "48655496"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a><span data-ttu-id="51d9a-103">Habilitar a los usuarios para el enrutamiento directo, la voz y el buzón de voz</span><span class="sxs-lookup"><span data-stu-id="51d9a-103">Enable users for Direct Routing, voice, and voicemail</span></span>

<span data-ttu-id="51d9a-104">En este artículo se describe cómo habilitar a los usuarios para el enrutamiento directo del sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="51d9a-104">This article describes how to enable users for Phone System Direct Routing.</span></span>  <span data-ttu-id="51d9a-105">Este es el paso 2 de los siguientes pasos para configurar el enrutamiento directo:</span><span class="sxs-lookup"><span data-stu-id="51d9a-105">This is step 2 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="51d9a-106">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="51d9a-106">Step 1.</span></span> [<span data-ttu-id="51d9a-107">Conectar el SBC con Microsoft Phone System y validar la conexión</span><span class="sxs-lookup"><span data-stu-id="51d9a-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="51d9a-108">**Paso 2. Habilitar a los usuarios para el enrutamiento directo, la voz y el buzón de voz**   (este artículo)</span><span class="sxs-lookup"><span data-stu-id="51d9a-108">**Step 2. Enable users for Direct Routing, voice, and voicemail**   (this article)</span></span>
- <span data-ttu-id="51d9a-109">Paso 3.</span><span class="sxs-lookup"><span data-stu-id="51d9a-109">Step 3.</span></span> [<span data-ttu-id="51d9a-110">Configurar el enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="51d9a-110">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="51d9a-111">Paso 4.</span><span class="sxs-lookup"><span data-stu-id="51d9a-111">Step 4.</span></span> [<span data-ttu-id="51d9a-112">Traducir números a un formato alternativo</span><span class="sxs-lookup"><span data-stu-id="51d9a-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 


<span data-ttu-id="51d9a-113">Para obtener información sobre todos los pasos necesarios para configurar el enrutamiento directo, consulte [configurar el enrutamiento directo](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="51d9a-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

<span data-ttu-id="51d9a-114">Cuando esté listo para habilitar a los usuarios para el enrutamiento directo, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="51d9a-114">When you are ready to enable users for Direct Routing, follow these steps:</span></span> 

1. <span data-ttu-id="51d9a-115">Cree un usuario en Microsoft 365 u Office 365 y asigne una licencia de sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="51d9a-115">Create a user in Microsoft 365 or Office 365 and assign a Phone System license.</span></span> 
2. <span data-ttu-id="51d9a-116">Asegúrese de que el usuario se ha alojado en Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="51d9a-116">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="51d9a-117">Configure el número de teléfono y habilite la telefonía IP empresarial y el buzón de voz.</span><span class="sxs-lookup"><span data-stu-id="51d9a-117">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="51d9a-118">Asigne el modo solo de Teams a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="51d9a-118">Assign Teams Only mode to users.</span></span>

## <a name="create-a-user-and-assign-the-license"></a><span data-ttu-id="51d9a-119">Crear un usuario y asignar la licencia</span><span class="sxs-lookup"><span data-stu-id="51d9a-119">Create a user and assign the license</span></span> 

<span data-ttu-id="51d9a-120">Existen dos opciones para crear un nuevo usuario en Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="51d9a-120">There are two options for creating a new user in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="51d9a-121">Sin embargo, Microsoft recomienda que su organización elija una opción para evitar problemas de enrutamiento:</span><span class="sxs-lookup"><span data-stu-id="51d9a-121">However, Microsoft recommends that your organization choose one option to avoid routing issues:</span></span> 

- <span data-ttu-id="51d9a-122">Crear el usuario en Active Directory local y sincronizar el usuario con la nube.</span><span class="sxs-lookup"><span data-stu-id="51d9a-122">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="51d9a-123">Consulte [integrar los directorios locales con Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="51d9a-123">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="51d9a-124">Cree directamente el usuario en el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="51d9a-124">Create the user directly in the Microsoft 365 admin center.</span></span> <span data-ttu-id="51d9a-125">Consulte [Agregar usuarios individualmente o de forma masiva a Microsoft 365 u Office 365: ayuda de administración](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="51d9a-125">See [Add users individually or in bulk to Microsoft 365 or Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="51d9a-126">Si su implementación de Skype empresarial online coexiste con Skype empresarial 2015 o Lync 2010 o 2013 local, la única opción admitida es crear el usuario en Active Directory local y sincronizar el usuario con la nube (opción 1).</span><span class="sxs-lookup"><span data-stu-id="51d9a-126">If your Skype for Business Online deployment coexists with Skype for Business 2015 or Lync 2010 or 2013 on-premises, the only supported option is to create the user in the on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="51d9a-127">Para obtener información sobre los requisitos de licencia, consulte [licencias y otros requisitos](direct-routing-plan.md#licensing-and-other-requirements) en [planificar enrutamiento directo](direct-routing-plan.md).</span><span class="sxs-lookup"><span data-stu-id="51d9a-127">For information about license requirements, see [licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements) in [Plan Direct Routing](direct-routing-plan.md).</span></span>

## <a name="ensure-that-the-user-is-homed-online-and-phone-number-is-not-being-synced-from-on-premises-applicable-for-skype-for-business-server-enterprise-voice-enabled-users-being-migrated-to-teams-direct-routing"></a><span data-ttu-id="51d9a-128">Asegúrese de que el usuario está conectado y el número de teléfono no se sincroniza desde local (aplicable para Skype empresarial Server Enterprise Voice habilitado los usuarios que se migran a un enrutamiento directo de Teams)</span><span class="sxs-lookup"><span data-stu-id="51d9a-128">Ensure that the user is homed online and phone number is not being synced from on-premises (applicable for Skype for Business Server Enterprise Voice enabled users being migrated to Teams Direct Routing)</span></span>

<span data-ttu-id="51d9a-129">El enrutamiento directo requiere que el usuario se conecte en línea.</span><span class="sxs-lookup"><span data-stu-id="51d9a-129">Direct Routing requires the user to be homed online.</span></span> <span data-ttu-id="51d9a-130">Puede consultar el parámetro RegistrarPool, que necesita tener un valor en el dominio de infra.lync.com.</span><span class="sxs-lookup"><span data-stu-id="51d9a-130">You can check by looking at the RegistrarPool parameter, which needs to have a value in the infra.lync.com domain.</span></span> <span data-ttu-id="51d9a-131">El parámetro OnPremLineUriManuallySet debe establecerse también en true.</span><span class="sxs-lookup"><span data-stu-id="51d9a-131">OnPremLineUriManuallySet parameter should also to be set to True.</span></span> <span data-ttu-id="51d9a-132">Esto se logra configurando el número de teléfono y habilitando la telefonía IP empresarial y el buzón de voz con Skype empresarial online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="51d9a-132">This is achieved by configuring the phone number and enable enterprise voice and voicemail using Skype for Business Online PowerShell.</span></span>

1. <span data-ttu-id="51d9a-133">Conectar una sesión de PowerShell de Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="51d9a-133">Connect a Skype for Business Online PowerShell session.</span></span>

2. <span data-ttu-id="51d9a-134">Emita el comando:</span><span class="sxs-lookup"><span data-stu-id="51d9a-134">Issue the command:</span></span> 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    <span data-ttu-id="51d9a-135">En caso de que OnPremLineUriManuallySet se haya establecido en false y LineUri se haya rellenado con un <E. 164 número de teléfono>, limpie los parámetros con el shell local de administración de Skype empresarial antes de configurar el número de teléfono con Skype empresarial online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="51d9a-135">In case OnPremLineUriManuallySet is set to False and LineUri is populated with a <E.164 phone number>, please clean the parameters using on-premises Skype for Business Management Shell, before configuring the phone number using Skype for Business Online PowerShell.</span></span> 

1. <span data-ttu-id="51d9a-136">Desde el shell de administración de Skype empresarial, ejecute el comando:</span><span class="sxs-lookup"><span data-stu-id="51d9a-136">From Skype for Business Management Shell issue the command:</span></span> 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null -EnterpriseVoiceEnabled $False -HostedVoiceMail $False
    ``` 
   <span data-ttu-id="51d9a-137">Una vez que los cambios se han sincronizado con Office 365, el resultado esperado `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` es:</span><span class="sxs-lookup"><span data-stu-id="51d9a-137">After the changes have synced to Office 365 the expected output of `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` would be:</span></span>

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="51d9a-138">Configurar el número de teléfono y habilitar la telefonía IP empresarial y el buzón de voz</span><span class="sxs-lookup"><span data-stu-id="51d9a-138">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="51d9a-139">Una vez que haya creado el usuario y haya asignado una licencia, el siguiente paso es configurar el número de teléfono del usuario y el buzón de voz.</span><span class="sxs-lookup"><span data-stu-id="51d9a-139">After you have created the user and assigned a license, the next step is to configure the user's phone number and voicemail.</span></span> 

<span data-ttu-id="51d9a-140">Para agregar el número de teléfono y habilitar el buzón de voz:</span><span class="sxs-lookup"><span data-stu-id="51d9a-140">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="51d9a-141">Conectar una sesión de PowerShell de Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="51d9a-141">Connect a Skype for Business Online PowerShell session.</span></span> 

2. <span data-ttu-id="51d9a-142">Emita el comando:</span><span class="sxs-lookup"><span data-stu-id="51d9a-142">Issue the command:</span></span> 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<phone number>
    ```
    
    <span data-ttu-id="51d9a-143">Por ejemplo, para agregar un número de teléfono para el usuario "Spencer Low", escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="51d9a-143">For example, to add a phone number for user "Spencer Low," enter the following:</span></span> 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```
    <span data-ttu-id="51d9a-144">Si los usuarios de "Spencer Low" y "Stacy Quinn" comparten el mismo número base con extensiones únicas, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="51d9a-144">If the users "Spencer Low" and "Stacy Quinn" share the same base number with unique extensions, enter the following</span></span>
    
    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388701;ext=1001 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    Set-CsUser -Identity "stacy.quinn@contoso.com" -OnPremLineURI tel:+14255388701;ext=1002 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    <span data-ttu-id="51d9a-145">Se recomienda, pero no es obligatorio, que el número de teléfono utilizado esté configurado como un número de teléfono E. 164 completo con prefijo internacional.</span><span class="sxs-lookup"><span data-stu-id="51d9a-145">It's recommended, but not required, that the phone number used is configured as a full E.164 phone number with country code.</span></span> <span data-ttu-id="51d9a-146">Es compatible con la configuración de números de teléfono con extensiones que se usarán para buscar usuarios cuando la búsqueda en el número base devuelva más de un resultado.</span><span class="sxs-lookup"><span data-stu-id="51d9a-146">It is supported to configure phone numbers with extensions which will be used to lookup users when the lookup against the base number returns more than one result.</span></span> <span data-ttu-id="51d9a-147">Esto permite a las empresas configurar números de teléfono con el mismo número base y las mismas extensiones.</span><span class="sxs-lookup"><span data-stu-id="51d9a-147">This allows companies to configure phone numbers with the same base number and unique extensions.</span></span> <span data-ttu-id="51d9a-148">Para que la búsqueda se realice correctamente, la invitación debe incluir el número completo con la extensión de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="51d9a-148">For lookup to be successful, the invite must include the full number with extension as follows:</span></span>
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```
    
    > [!NOTE]
    > <span data-ttu-id="51d9a-149">Si el número de teléfono del usuario se administra localmente, use el shell local de administración de Skype empresarial o el panel de control para configurar el número de teléfono del usuario.</span><span class="sxs-lookup"><span data-stu-id="51d9a-149">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 


## <a name="configuring-sending-calls-directly-to-voicemail"></a><span data-ttu-id="51d9a-150">Configurar el envío de llamadas directamente al buzón de voz</span><span class="sxs-lookup"><span data-stu-id="51d9a-150">Configuring sending calls directly to voicemail</span></span>

<span data-ttu-id="51d9a-151">El enrutamiento directo le permite finalizar la llamada a un usuario y enviarlo directamente al buzón de voz del usuario.</span><span class="sxs-lookup"><span data-stu-id="51d9a-151">Direct Routing allows you to end the call to a user and send it directly to the user's voicemail.</span></span> <span data-ttu-id="51d9a-152">Si deseas enviar la llamada directamente al buzón de voz, adjunta Opaque = App: el buzón de voz al encabezado de URI de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="51d9a-152">If you want to send the call directly to voicemail, attach opaque=app:voicemail to the Request URI header.</span></span> <span data-ttu-id="51d9a-153">Por ejemplo, "SIP: user@yourdomain. com; Opaque = App: buzón de voz".</span><span class="sxs-lookup"><span data-stu-id="51d9a-153">For example, "sip:user@yourdomain.com;opaque=app:voicemail".</span></span> <span data-ttu-id="51d9a-154">En este caso, el usuario de Teams no recibirá la notificación de llamada, la llamada se conectará al buzón de voz del usuario directamente.</span><span class="sxs-lookup"><span data-stu-id="51d9a-154">In this case, the Teams user will not receive the calling notification, the call will be connected to the voicemail of the user directly.</span></span>

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a><span data-ttu-id="51d9a-155">Asignar el modo solo de Teams a los usuarios para garantizar la superficie de llamadas en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="51d9a-155">Assign Teams Only mode to users to ensure calls land in Microsoft Teams</span></span>

<span data-ttu-id="51d9a-156">El enrutamiento directo requiere que los usuarios estén en el modo solo de equipos para garantizar las llamadas entrantes en el cliente de Teams.</span><span class="sxs-lookup"><span data-stu-id="51d9a-156">Direct Routing requires that users be in Teams Only mode to ensure incoming calls land in the Teams client.</span></span> <span data-ttu-id="51d9a-157">Para poner los usuarios en modo de solo equipos, asígnelos a la instancia "UpgradeToTeams" de TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="51d9a-157">To put users in Teams Only mode, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> <span data-ttu-id="51d9a-158">Para obtener más información, consulte [Guía de actualización para administradores de ti](upgrade-to-teams-on-prem-overview.md).</span><span class="sxs-lookup"><span data-stu-id="51d9a-158">For more information, see [Upgrade guidance for IT administrators](upgrade-to-teams-on-prem-overview.md).</span></span> <span data-ttu-id="51d9a-159">Si su organización usa Skype empresarial Server o Skype empresarial online, consulte el artículo siguiente para obtener información sobre la interoperabilidad entre Skype y Teams: [migración y interoperabilidad con Skype empresarial](migration-interop-guidance-for-teams-with-skype.md).</span><span class="sxs-lookup"><span data-stu-id="51d9a-159">If your organization uses Skype for Business Server or Skype for Business Online, see the following article for information about interoperability between Skype and Teams: [Migration and interoperability with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="51d9a-160">Consulte también</span><span class="sxs-lookup"><span data-stu-id="51d9a-160">See also</span></span>

[<span data-ttu-id="51d9a-161">Planear el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="51d9a-161">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="51d9a-162">Configurar el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="51d9a-162">Configure Direct Routing</span></span>](direct-routing-configure.md)
