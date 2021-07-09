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
description: Obtenga información sobre cómo habilitar a los Teléfono Microsoft System Direct Routing.
ms.openlocfilehash: 86132778226702577068d9502ae46cba949667c6
ms.sourcegitcommit: 5df33e7fe912426e3e158b3be7334e05dc3803a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2021
ms.locfileid: "53345716"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a><span data-ttu-id="83dd5-103">Habilitar usuarios para enrutamiento directo, voz y correo de voz</span><span class="sxs-lookup"><span data-stu-id="83dd5-103">Enable users for Direct Routing, voice, and voicemail</span></span>

<span data-ttu-id="83dd5-104">En este artículo se describe cómo habilitar usuarios para Sistema telefónico enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="83dd5-104">This article describes how to enable users for Phone System Direct Routing.</span></span>  <span data-ttu-id="83dd5-105">Este es el paso 2 de los pasos siguientes para configurar enrutamiento directo:</span><span class="sxs-lookup"><span data-stu-id="83dd5-105">This is step 2 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="83dd5-106">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="83dd5-106">Step 1.</span></span> [<span data-ttu-id="83dd5-107">Conectar el SBC con Teléfono Microsoft y validar la conexión</span><span class="sxs-lookup"><span data-stu-id="83dd5-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="83dd5-108">**Paso 2. Habilitar usuarios para enrutamiento directo, voz y correo de voz**   (este artículo)</span><span class="sxs-lookup"><span data-stu-id="83dd5-108">**Step 2. Enable users for Direct Routing, voice, and voicemail**   (this article)</span></span>
- <span data-ttu-id="83dd5-109">Paso 3.</span><span class="sxs-lookup"><span data-stu-id="83dd5-109">Step 3.</span></span> [<span data-ttu-id="83dd5-110">Configurar el enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="83dd5-110">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="83dd5-111">Paso 4.</span><span class="sxs-lookup"><span data-stu-id="83dd5-111">Step 4.</span></span> [<span data-ttu-id="83dd5-112">Traducir números a un formato alternativo</span><span class="sxs-lookup"><span data-stu-id="83dd5-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 


<span data-ttu-id="83dd5-113">Para obtener información sobre todos los pasos necesarios para configurar el enrutamiento directo, vea [Configurar enrutamiento directo.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="83dd5-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

<span data-ttu-id="83dd5-114">Cuando esté listo para habilitar usuarios para enrutamiento directo, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="83dd5-114">When you are ready to enable users for Direct Routing, follow these steps:</span></span> 

1. <span data-ttu-id="83dd5-115">Cree un usuario en Microsoft 365 o Office 365 y asigne una Sistema telefónico licencia.</span><span class="sxs-lookup"><span data-stu-id="83dd5-115">Create a user in Microsoft 365 or Office 365 and assign a Phone System license.</span></span> 
2. <span data-ttu-id="83dd5-116">Asegúrese de que el usuario se encuentra en Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="83dd5-116">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="83dd5-117">Configure el número de teléfono y habilite la voz empresarial y el correo de voz.</span><span class="sxs-lookup"><span data-stu-id="83dd5-117">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="83dd5-118">Asignar Teams solo a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="83dd5-118">Assign Teams Only mode to users.</span></span>

## <a name="create-a-user-and-assign-the-license"></a><span data-ttu-id="83dd5-119">Crear un usuario y asignar la licencia</span><span class="sxs-lookup"><span data-stu-id="83dd5-119">Create a user and assign the license</span></span>

<span data-ttu-id="83dd5-120">Hay dos opciones para crear un nuevo usuario en Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="83dd5-120">There are two options for creating a new user in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="83dd5-121">Sin embargo, Microsoft recomienda que su organización elija una opción para evitar problemas de enrutamiento:</span><span class="sxs-lookup"><span data-stu-id="83dd5-121">However, Microsoft recommends that your organization choose one option to avoid routing issues:</span></span> 

- <span data-ttu-id="83dd5-122">Cree el usuario en Active Directory local y sincronice el usuario con la nube.</span><span class="sxs-lookup"><span data-stu-id="83dd5-122">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="83dd5-123">Vea [Integrar los directorios locales con Azure Active Directory](/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="83dd5-123">See [Integrate your on-premises directories with Azure Active Directory](/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="83dd5-124">Cree el usuario directamente en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="83dd5-124">Create the user directly in the Microsoft 365 admin center.</span></span> <span data-ttu-id="83dd5-125">Vea Agregar usuarios individualmente o en masa [a Microsoft 365 o Office 365- Ayuda para administradores.](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</span><span class="sxs-lookup"><span data-stu-id="83dd5-125">See [Add users individually or in bulk to Microsoft 365 or Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="83dd5-126">Si su implementación de Skype Empresarial Online coexiste con Skype Empresarial 2015 o Lync 2010 o 2013 local, la única opción compatible es crear el usuario en el Active Directory local y sincronizar el usuario con la nube (opción 1).</span><span class="sxs-lookup"><span data-stu-id="83dd5-126">If your Skype for Business Online deployment coexists with Skype for Business 2015 or Lync 2010 or 2013 on-premises, the only supported option is to create the user in the on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="83dd5-127">Para obtener información sobre los requisitos de licencia, vea [Licencias y otros requisitos](direct-routing-plan.md#licensing-and-other-requirements) en [Plan de enrutamiento directo.](direct-routing-plan.md)</span><span class="sxs-lookup"><span data-stu-id="83dd5-127">For information about license requirements, see [licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements) in [Plan Direct Routing](direct-routing-plan.md).</span></span>

## <a name="ensure-that-the-user-is-homed-online"></a><span data-ttu-id="83dd5-128">Asegurarse de que el usuario está conectado</span><span class="sxs-lookup"><span data-stu-id="83dd5-128">Ensure that the user is homed online</span></span> 

<span data-ttu-id="83dd5-129">Este paso es aplicable a Skype Empresarial Server Telefonía IP empresarial usuarios habilitados que se migran a Teams enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="83dd5-129">This step is applicable to Skype for Business Server Enterprise Voice enabled users being migrated to Teams Direct Routing.</span></span>

<span data-ttu-id="83dd5-130">Enrutamiento directo requiere que el usuario esté conectado.</span><span class="sxs-lookup"><span data-stu-id="83dd5-130">Direct Routing requires the user to be homed online.</span></span> <span data-ttu-id="83dd5-131">Para comprobarlo, consulte el parámetro RegistrarPool, que debe tener un valor en el infra.lync.com usuario.</span><span class="sxs-lookup"><span data-stu-id="83dd5-131">You can check by looking at the RegistrarPool parameter, which needs to have a value in the infra.lync.com domain.</span></span> <span data-ttu-id="83dd5-132">También se recomienda, pero no necesario, cambiar la administración de LineURI de local a online al migrar usuarios a Teams enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="83dd5-132">It's also recommended, but not required, to change management of the LineURI from on-premises to online when migrating users to Teams Direct Routing.</span></span> 

1. <span data-ttu-id="83dd5-133">Conectar una sesión Skype Empresarial PowerShell en línea.</span><span class="sxs-lookup"><span data-stu-id="83dd5-133">Connect a Skype for Business Online PowerShell session.</span></span>

2. <span data-ttu-id="83dd5-134">Publique el comando:</span><span class="sxs-lookup"><span data-stu-id="83dd5-134">Issue the command:</span></span> 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    <span data-ttu-id="83dd5-135">En caso de que OnPremLineUriManuallySet se establezca en False y LineUri se rellene con un número de teléfono de <E.164>, el número de teléfono se asignó localmente y se sincronizó en O365.</span><span class="sxs-lookup"><span data-stu-id="83dd5-135">In case OnPremLineUriManuallySet is set to False and LineUri is populated with a <E.164 phone number>, the phone number was assigned on-premises and synchronized to O365.</span></span> <span data-ttu-id="83dd5-136">Si desea administrar el número de teléfono en línea, limpie el parámetro con el Shell de administración local de Skype Empresarial y sincronice con O365, antes de configurar el número de teléfono con Skype Empresarial PowerShell en línea.</span><span class="sxs-lookup"><span data-stu-id="83dd5-136">If you want manage the phone number online, clean the parameter using on-premises Skype for Business Management Shell and synchronize to O365, before configuring the phone number using Skype for Business Online PowerShell.</span></span> 

1. <span data-ttu-id="83dd5-137">Desde Skype Empresarial Shell de administración emite el comando:</span><span class="sxs-lookup"><span data-stu-id="83dd5-137">From Skype for Business Management Shell issue the command:</span></span> 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null
    ``` 
 > [!NOTE]
 > <span data-ttu-id="83dd5-138">No establezca EnterpriseVoiceEnabled en False, ya que no es necesario hacerlo y esto puede provocar problemas de normalización del plan de marcado si los teléfonos Skype Empresarial heredados están en uso y la configuración híbrida de Inquilino se establece con UseOnPremDialPlan $True.</span><span class="sxs-lookup"><span data-stu-id="83dd5-138">Do not set EnterpriseVoiceEnabled to False as there is no requirement to do so and this can lead to dial plan normalization issues if legacy Skype for Business phones are in use and the Tenant hybrid configuration is set with UseOnPremDialPlan $True.</span></span> 
    
   <span data-ttu-id="83dd5-139">Después de que los cambios se sincronicen Office 365 el resultado esperado `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` sería:</span><span class="sxs-lookup"><span data-stu-id="83dd5-139">After the changes have synced to Office 365 the expected output of `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` would be:</span></span>

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```
 > [!NOTE]
 > <span data-ttu-id="83dd5-140">Todos los atributos de teléfono del usuario deben administrarse en línea antes [de descomissionr](/skypeforbusiness/hybrid/decommission-on-prem-overview)su entorno Skype Empresarial local.</span><span class="sxs-lookup"><span data-stu-id="83dd5-140">All user's phone attributes must be managed online before you [decomission your on-premises Skype for Business environment](/skypeforbusiness/hybrid/decommission-on-prem-overview).</span></span> 

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online"></a><span data-ttu-id="83dd5-141">Configurar el número de teléfono y habilitar la voz empresarial y el correo de voz en línea</span><span class="sxs-lookup"><span data-stu-id="83dd5-141">Configure the phone number and enable enterprise voice and voicemail online</span></span> 

<span data-ttu-id="83dd5-142">Después de crear el usuario y asignar una licencia, el siguiente paso es configurar la configuración del teléfono en línea del usuario.</span><span class="sxs-lookup"><span data-stu-id="83dd5-142">After you have created the user and assigned a license, the next step is to configure the user's online phone settings.</span></span> 

 
1. <span data-ttu-id="83dd5-143">Conectar una sesión Skype Empresarial PowerShell en línea.</span><span class="sxs-lookup"><span data-stu-id="83dd5-143">Connect a Skype for Business Online PowerShell session.</span></span> 

2. <span data-ttu-id="83dd5-144">Si administra el número de teléfono del usuario local, ejecute el comando:</span><span class="sxs-lookup"><span data-stu-id="83dd5-144">If managing the user's phone number on-premises, issue the command:</span></span> 

    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```
3. <span data-ttu-id="83dd5-145">Si administra el número de teléfono del usuario en línea, ejecute el comando:</span><span class="sxs-lookup"><span data-stu-id="83dd5-145">If managing the user's phone number online, issue the command:</span></span> 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<phone number>
    ```
    
    <span data-ttu-id="83dd5-146">Por ejemplo, para agregar un número de teléfono para el usuario "Spencer Low", escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="83dd5-146">For example, to add a phone number for user "Spencer Low," enter the following:</span></span> 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```
    <span data-ttu-id="83dd5-147">Si los usuarios "Spencer Low" y "Stacy Quinn" comparten el mismo número base con extensiones únicas, escriba lo siguiente</span><span class="sxs-lookup"><span data-stu-id="83dd5-147">If the users "Spencer Low" and "Stacy Quinn" share the same base number with unique extensions, enter the following</span></span>
    
    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI "tel:+14255388701;ext=1001" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    Set-CsUser -Identity "stacy.quinn@contoso.com" -OnPremLineURI "tel:+14255388701;ext=1002" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    <span data-ttu-id="83dd5-148">Se recomienda, pero no necesario, que el número de teléfono usado esté configurado como un número de teléfono E.164 completo con código de país.</span><span class="sxs-lookup"><span data-stu-id="83dd5-148">It's recommended, but not required, that the phone number used is configured as a full E.164 phone number with country code.</span></span> <span data-ttu-id="83dd5-149">Es compatible con configurar números de teléfono con extensiones que se usarán para buscar usuarios cuando la búsqueda en el número base devuelva más de un resultado.</span><span class="sxs-lookup"><span data-stu-id="83dd5-149">It is supported to configure phone numbers with extensions which will be used to lookup users when the lookup against the base number returns more than one result.</span></span> <span data-ttu-id="83dd5-150">Esto permite a las empresas configurar números de teléfono con el mismo número base y extensiones únicas.</span><span class="sxs-lookup"><span data-stu-id="83dd5-150">This allows companies to configure phone numbers with the same base number and unique extensions.</span></span> <span data-ttu-id="83dd5-151">Para que la búsqueda se realice correctamente, la invitación debe incluir el número completo con la extensión de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="83dd5-151">For lookup to be successful, the invite must include the full number with extension as follows:</span></span>
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```
    
    > [!NOTE]
    > <span data-ttu-id="83dd5-152">Si el número de teléfono del usuario se administra localmente, use el Shell de administración local o el Panel de control Skype Empresarial local para configurar el número de teléfono del usuario.</span><span class="sxs-lookup"><span data-stu-id="83dd5-152">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 


## <a name="configuring-sending-calls-directly-to-voicemail"></a><span data-ttu-id="83dd5-153">Configurar el envío de llamadas directamente al correo de voz</span><span class="sxs-lookup"><span data-stu-id="83dd5-153">Configuring sending calls directly to voicemail</span></span>

<span data-ttu-id="83dd5-154">Enrutamiento directo le permite finalizar la llamada a un usuario y enviarla directamente al correo de voz del usuario.</span><span class="sxs-lookup"><span data-stu-id="83dd5-154">Direct Routing allows you to end the call to a user and send it directly to the user's voicemail.</span></span> <span data-ttu-id="83dd5-155">Si desea enviar la llamada directamente al correo de voz, adjunte opaque=app:voicemail al encabezado Solicitar URI.</span><span class="sxs-lookup"><span data-stu-id="83dd5-155">If you want to send the call directly to voicemail, attach opaque=app:voicemail to the Request URI header.</span></span> <span data-ttu-id="83dd5-156">Por ejemplo, "sip:user@yourdomain.com;opaque=app:voicemail".</span><span class="sxs-lookup"><span data-stu-id="83dd5-156">For example, "sip:user@yourdomain.com;opaque=app:voicemail".</span></span> <span data-ttu-id="83dd5-157">En este caso, Teams usuario no recibirá la notificación de llamada, la llamada se conectará directamente al correo de voz del usuario.</span><span class="sxs-lookup"><span data-stu-id="83dd5-157">In this case, the Teams user will not receive the calling notification, the call will be connected to the voicemail of the user directly.</span></span>

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a><span data-ttu-id="83dd5-158">Asignar Teams solo a los usuarios para asegurarse de que las llamadas se Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="83dd5-158">Assign Teams Only mode to users to ensure calls land in Microsoft Teams</span></span>

<span data-ttu-id="83dd5-159">Enrutamiento directo requiere que los usuarios se Teams modo solo para asegurarse de que las llamadas entrantes se aterrice en el Teams cliente.</span><span class="sxs-lookup"><span data-stu-id="83dd5-159">Direct Routing requires that users be in Teams Only mode to ensure incoming calls land in the Teams client.</span></span> <span data-ttu-id="83dd5-160">Para poner a los usuarios en Teams solo, asígneles la instancia "UpgradeToTeams" de TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="83dd5-160">To put users in Teams Only mode, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> <span data-ttu-id="83dd5-161">Para obtener más información, vea [Estrategias de actualización para administradores de TI.](upgrade-to-teams-on-prem-implement.md)</span><span class="sxs-lookup"><span data-stu-id="83dd5-161">For more information, see [Upgrade strategies for IT administrators](upgrade-to-teams-on-prem-implement.md).</span></span> <span data-ttu-id="83dd5-162">Si su organización usa Skype Empresarial Server o Skype Empresarial Online, vea el siguiente artículo para obtener información sobre la interoperabilidad entre Skype y Teams: Migración e interoperabilidad [con Skype Empresarial](migration-interop-guidance-for-teams-with-skype.md).</span><span class="sxs-lookup"><span data-stu-id="83dd5-162">If your organization uses Skype for Business Server or Skype for Business Online, see the following article for information about interoperability between Skype and Teams: [Migration and interoperability with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="83dd5-163">Vea también</span><span class="sxs-lookup"><span data-stu-id="83dd5-163">See also</span></span>

[<span data-ttu-id="83dd5-164">Planear el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="83dd5-164">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="83dd5-165">Configurar el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="83dd5-165">Configure Direct Routing</span></span>](direct-routing-configure.md)
