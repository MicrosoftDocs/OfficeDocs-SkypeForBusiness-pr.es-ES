---
title: Habilitar usuarios para enrutamiento directo
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
description: Obtenga información sobre cómo habilitar el enrutamiento directo de Microsoft Phone System para los usuarios.
ms.openlocfilehash: 5739797649c639e3259c6972da665ae0ced4b4bf
ms.sourcegitcommit: 0a9c5c01b37a93eecc369ca0ed49ae18f6a5065b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2020
ms.locfileid: "48655496"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a><span data-ttu-id="2ab18-103">Habilitar usuarios para enrutamiento directo, voz y correo de voz</span><span class="sxs-lookup"><span data-stu-id="2ab18-103">Enable users for Direct Routing, voice, and voicemail</span></span>

<span data-ttu-id="2ab18-104">En este artículo se describe cómo habilitar a los usuarios para el enrutamiento directo de sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="2ab18-104">This article describes how to enable users for Phone System Direct Routing.</span></span>  <span data-ttu-id="2ab18-105">Este es el paso 2 de los siguientes pasos para configurar el enrutamiento directo:</span><span class="sxs-lookup"><span data-stu-id="2ab18-105">This is step 2 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="2ab18-106">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="2ab18-106">Step 1.</span></span> [<span data-ttu-id="2ab18-107">Conectar el SBC con Microsoft Phone System y validar la conexión</span><span class="sxs-lookup"><span data-stu-id="2ab18-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="2ab18-108">**Paso 2. Habilitar a los usuarios para enrutamiento directo, voz y correo de**   voz (en este artículo)</span><span class="sxs-lookup"><span data-stu-id="2ab18-108">**Step 2. Enable users for Direct Routing, voice, and voicemail**   (this article)</span></span>
- <span data-ttu-id="2ab18-109">Paso 3.</span><span class="sxs-lookup"><span data-stu-id="2ab18-109">Step 3.</span></span> [<span data-ttu-id="2ab18-110">Configurar el enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="2ab18-110">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="2ab18-111">Paso 4.</span><span class="sxs-lookup"><span data-stu-id="2ab18-111">Step 4.</span></span> [<span data-ttu-id="2ab18-112">Traducir números a un formato alternativo</span><span class="sxs-lookup"><span data-stu-id="2ab18-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 


<span data-ttu-id="2ab18-113">Para obtener información sobre todos los pasos necesarios para configurar el enrutamiento directo, vea [Configurar enrutamiento directo.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="2ab18-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

<span data-ttu-id="2ab18-114">Cuando esté listo para habilitar a los usuarios para enrutamiento directo, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="2ab18-114">When you are ready to enable users for Direct Routing, follow these steps:</span></span> 

1. <span data-ttu-id="2ab18-115">Cree un usuario en Microsoft 365 u Office 365 y asigne una licencia de Sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="2ab18-115">Create a user in Microsoft 365 or Office 365 and assign a Phone System license.</span></span> 
2. <span data-ttu-id="2ab18-116">Asegúrese de que el usuario está en Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="2ab18-116">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="2ab18-117">Configure el número de teléfono y habilite la voz de empresa y el correo de voz.</span><span class="sxs-lookup"><span data-stu-id="2ab18-117">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="2ab18-118">Asignar el modo Solo equipos a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="2ab18-118">Assign Teams Only mode to users.</span></span>

## <a name="create-a-user-and-assign-the-license"></a><span data-ttu-id="2ab18-119">Crear un usuario y asignar la licencia</span><span class="sxs-lookup"><span data-stu-id="2ab18-119">Create a user and assign the license</span></span> 

<span data-ttu-id="2ab18-120">Hay dos opciones para crear un nuevo usuario en Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="2ab18-120">There are two options for creating a new user in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="2ab18-121">Sin embargo, Microsoft recomienda que su organización elija una opción para evitar problemas de enrutamiento:</span><span class="sxs-lookup"><span data-stu-id="2ab18-121">However, Microsoft recommends that your organization choose one option to avoid routing issues:</span></span> 

- <span data-ttu-id="2ab18-122">Cree el usuario en Active Directory local y sincronice el usuario con la nube.</span><span class="sxs-lookup"><span data-stu-id="2ab18-122">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="2ab18-123">Consulte [Integrar los directorios locales con Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)</span><span class="sxs-lookup"><span data-stu-id="2ab18-123">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="2ab18-124">Cree el usuario directamente en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2ab18-124">Create the user directly in the Microsoft 365 admin center.</span></span> <span data-ttu-id="2ab18-125">Vea [Agregar usuarios individualmente o de forma masiva a Microsoft 365 u Office 365: ayuda para administradores.](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</span><span class="sxs-lookup"><span data-stu-id="2ab18-125">See [Add users individually or in bulk to Microsoft 365 or Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="2ab18-126">Si su implementación de Skype Empresarial Online coexiste con Skype Empresarial 2015 o Lync 2010 o 2013 local, la única opción admitida es crear el usuario en la implementación local de Active Directory y sincronizar el usuario con la nube (opción 1).</span><span class="sxs-lookup"><span data-stu-id="2ab18-126">If your Skype for Business Online deployment coexists with Skype for Business 2015 or Lync 2010 or 2013 on-premises, the only supported option is to create the user in the on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="2ab18-127">Para obtener información sobre los requisitos de licencia, vea [licencias y otros requisitos](direct-routing-plan.md#licensing-and-other-requirements) en [Plan de enrutamiento directo.](direct-routing-plan.md)</span><span class="sxs-lookup"><span data-stu-id="2ab18-127">For information about license requirements, see [licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements) in [Plan Direct Routing](direct-routing-plan.md).</span></span>

## <a name="ensure-that-the-user-is-homed-online-and-phone-number-is-not-being-synced-from-on-premises-applicable-for-skype-for-business-server-enterprise-voice-enabled-users-being-migrated-to-teams-direct-routing"></a><span data-ttu-id="2ab18-128">Asegúrese de que el usuario está conectado y que el número de teléfono no se sincroniza desde la implementación local (aplicable a los usuarios con Skype Empresarial Server Telefonía IP empresarial que se están migrando a Enrutamiento directo de Teams)</span><span class="sxs-lookup"><span data-stu-id="2ab18-128">Ensure that the user is homed online and phone number is not being synced from on-premises (applicable for Skype for Business Server Enterprise Voice enabled users being migrated to Teams Direct Routing)</span></span>

<span data-ttu-id="2ab18-129">El enrutamiento directo requiere que el usuario esté conectado.</span><span class="sxs-lookup"><span data-stu-id="2ab18-129">Direct Routing requires the user to be homed online.</span></span> <span data-ttu-id="2ab18-130">Para comprobarlo, consulte el parámetro RegistrarPool, que debe tener un valor en el dominio infra.lync.com registro.</span><span class="sxs-lookup"><span data-stu-id="2ab18-130">You can check by looking at the RegistrarPool parameter, which needs to have a value in the infra.lync.com domain.</span></span> <span data-ttu-id="2ab18-131">El parámetro OnPremLineUriManuallySet también debe establecerse en True.</span><span class="sxs-lookup"><span data-stu-id="2ab18-131">OnPremLineUriManuallySet parameter should also to be set to True.</span></span> <span data-ttu-id="2ab18-132">Para ello, configure el número de teléfono y habilite el correo de voz empresarial y el correo de voz con PowerShell de Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="2ab18-132">This is achieved by configuring the phone number and enable enterprise voice and voicemail using Skype for Business Online PowerShell.</span></span>

1. <span data-ttu-id="2ab18-133">Conectar una sesión de PowerShell de Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="2ab18-133">Connect a Skype for Business Online PowerShell session.</span></span>

2. <span data-ttu-id="2ab18-134">Ejecute el comando:</span><span class="sxs-lookup"><span data-stu-id="2ab18-134">Issue the command:</span></span> 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    <span data-ttu-id="2ab18-135">Si OnPremLineUriManuallySet se establece en False y LineUri se rellena con un número de teléfono> E.164 de <, limpie los parámetros con el Shell de administración local de Skype Empresarial antes de configurar el número de teléfono con PowerShell de Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="2ab18-135">In case OnPremLineUriManuallySet is set to False and LineUri is populated with a <E.164 phone number>, please clean the parameters using on-premises Skype for Business Management Shell, before configuring the phone number using Skype for Business Online PowerShell.</span></span> 

1. <span data-ttu-id="2ab18-136">Desde el shell de administración de Skype Empresarial, ejecute el comando:</span><span class="sxs-lookup"><span data-stu-id="2ab18-136">From Skype for Business Management Shell issue the command:</span></span> 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null -EnterpriseVoiceEnabled $False -HostedVoiceMail $False
    ``` 
   <span data-ttu-id="2ab18-137">Una vez que los cambios se han sincronizado con Office 365, el resultado esperado `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` sería:</span><span class="sxs-lookup"><span data-stu-id="2ab18-137">After the changes have synced to Office 365 the expected output of `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` would be:</span></span>

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="2ab18-138">Configurar el número de teléfono y habilitar la voz y el correo de voz empresariales</span><span class="sxs-lookup"><span data-stu-id="2ab18-138">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="2ab18-139">Después de crear el usuario y asignar una licencia, el siguiente paso es configurar el número de teléfono y el correo de voz del usuario.</span><span class="sxs-lookup"><span data-stu-id="2ab18-139">After you have created the user and assigned a license, the next step is to configure the user's phone number and voicemail.</span></span> 

<span data-ttu-id="2ab18-140">Para agregar el número de teléfono y habilitar el correo de voz:</span><span class="sxs-lookup"><span data-stu-id="2ab18-140">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="2ab18-141">Conectar una sesión de PowerShell de Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="2ab18-141">Connect a Skype for Business Online PowerShell session.</span></span> 

2. <span data-ttu-id="2ab18-142">Ejecute el comando:</span><span class="sxs-lookup"><span data-stu-id="2ab18-142">Issue the command:</span></span> 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<phone number>
    ```
    
    <span data-ttu-id="2ab18-143">Por ejemplo, para agregar un número de teléfono para el usuario "Entresa bajo", escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2ab18-143">For example, to add a phone number for user "Spencer Low," enter the following:</span></span> 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```
    <span data-ttu-id="2ab18-144">Si los usuarios "Low" y "Stacy Corp" comparten el mismo número base con extensiones únicas, escribe lo siguiente</span><span class="sxs-lookup"><span data-stu-id="2ab18-144">If the users "Spencer Low" and "Stacy Quinn" share the same base number with unique extensions, enter the following</span></span>
    
    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388701;ext=1001 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    Set-CsUser -Identity "stacy.quinn@contoso.com" -OnPremLineURI tel:+14255388701;ext=1002 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    <span data-ttu-id="2ab18-145">Se recomienda, pero no es necesario, que el número de teléfono usado esté configurado como un número de teléfono E.164 completo con código de país.</span><span class="sxs-lookup"><span data-stu-id="2ab18-145">It's recommended, but not required, that the phone number used is configured as a full E.164 phone number with country code.</span></span> <span data-ttu-id="2ab18-146">Es compatible con configurar números de teléfono con extensiones que se usarán para buscar usuarios cuando la búsqueda en el número base devuelva más de un resultado.</span><span class="sxs-lookup"><span data-stu-id="2ab18-146">It is supported to configure phone numbers with extensions which will be used to lookup users when the lookup against the base number returns more than one result.</span></span> <span data-ttu-id="2ab18-147">Esto permite a las compañías configurar números de teléfono con el mismo número base y extensiones únicas.</span><span class="sxs-lookup"><span data-stu-id="2ab18-147">This allows companies to configure phone numbers with the same base number and unique extensions.</span></span> <span data-ttu-id="2ab18-148">Para que la búsqueda se realice correctamente, la invitación debe incluir el número completo con extensión de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="2ab18-148">For lookup to be successful, the invite must include the full number with extension as follows:</span></span>
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```
    
    > [!NOTE]
    > <span data-ttu-id="2ab18-149">Si el número de teléfono del usuario se administra de forma local, use el Shell de administración local de Skype Empresarial o el Panel de control para configurar el número de teléfono del usuario.</span><span class="sxs-lookup"><span data-stu-id="2ab18-149">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 


## <a name="configuring-sending-calls-directly-to-voicemail"></a><span data-ttu-id="2ab18-150">Configurar el envío de llamadas directamente al correo de voz</span><span class="sxs-lookup"><span data-stu-id="2ab18-150">Configuring sending calls directly to voicemail</span></span>

<span data-ttu-id="2ab18-151">El enrutamiento directo le permite finalizar la llamada a un usuario y enviarla directamente al correo de voz del usuario.</span><span class="sxs-lookup"><span data-stu-id="2ab18-151">Direct Routing allows you to end the call to a user and send it directly to the user's voicemail.</span></span> <span data-ttu-id="2ab18-152">Si quiere enviar la llamada directamente al correo de voz, adjunte opaque=app:voicemail al encabezado del URI de solicitud.</span><span class="sxs-lookup"><span data-stu-id="2ab18-152">If you want to send the call directly to voicemail, attach opaque=app:voicemail to the Request URI header.</span></span> <span data-ttu-id="2ab18-153">Por ejemplo, "sip:user@yourdomain.com;opaque=app:voicemail".</span><span class="sxs-lookup"><span data-stu-id="2ab18-153">For example, "sip:user@yourdomain.com;opaque=app:voicemail".</span></span> <span data-ttu-id="2ab18-154">En este caso, el usuario de Teams no recibirá la notificación de llamada, la llamada se conectará al correo de voz del usuario directamente.</span><span class="sxs-lookup"><span data-stu-id="2ab18-154">In this case, the Teams user will not receive the calling notification, the call will be connected to the voicemail of the user directly.</span></span>

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a><span data-ttu-id="2ab18-155">Asignar el modo Solo de Teams a los usuarios para garantizar que las llamadas se des fijos en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2ab18-155">Assign Teams Only mode to users to ensure calls land in Microsoft Teams</span></span>

<span data-ttu-id="2ab18-156">El enrutamiento directo requiere que los usuarios se ajusten al modo Solo en Teams para garantizar que las llamadas entrantes se agregó al cliente de Teams.</span><span class="sxs-lookup"><span data-stu-id="2ab18-156">Direct Routing requires that users be in Teams Only mode to ensure incoming calls land in the Teams client.</span></span> <span data-ttu-id="2ab18-157">Para poner a los usuarios en el modo solo de Teams, asígneles la instancia "UpgradeToTeams" de TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="2ab18-157">To put users in Teams Only mode, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> <span data-ttu-id="2ab18-158">Para obtener más información, vea [las instrucciones de actualización para administradores de TI.](upgrade-to-teams-on-prem-overview.md)</span><span class="sxs-lookup"><span data-stu-id="2ab18-158">For more information, see [Upgrade guidance for IT administrators](upgrade-to-teams-on-prem-overview.md).</span></span> <span data-ttu-id="2ab18-159">Si su organización usa Skype Empresarial Server o Skype Empresarial Online, consulte el siguiente artículo para obtener información sobre interoperabilidad entre Skype y Teams: migración e interoperabilidad [con Skype Empresarial.](migration-interop-guidance-for-teams-with-skype.md)</span><span class="sxs-lookup"><span data-stu-id="2ab18-159">If your organization uses Skype for Business Server or Skype for Business Online, see the following article for information about interoperability between Skype and Teams: [Migration and interoperability with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2ab18-160">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2ab18-160">See also</span></span>

[<span data-ttu-id="2ab18-161">Planear el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="2ab18-161">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="2ab18-162">Configurar el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="2ab18-162">Configure Direct Routing</span></span>](direct-routing-configure.md)
