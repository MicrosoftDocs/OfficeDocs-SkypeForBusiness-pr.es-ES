---
title: Configurar audioconferencias para Skype empresarial
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords:
- O365P_DialInConfDesc
ms.custom:
- Audio Conferencing
- LIL_Placement
description: 'Obtenga información sobre cómo configurar las conferencias de acceso telefónico local o de audio para las personas de su empresa que necesitan usar un teléfono para unirse a llamadas en conferencia. '
ms.openlocfilehash: fd259553794f0ed56d5e3a59752017b50478a97c
ms.sourcegitcommit: 2f8b9c7c8d20f2605d09cae4bbaeb10667f2ddea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2019
ms.locfileid: "34329564"
---
# <a name="set-up-audio-conferencing-for-skype-for-business"></a><span data-ttu-id="d42d1-103">Configurar audioconferencias para Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="d42d1-103">Set up Audio Conferencing for Skype for Business</span></span>

<span data-ttu-id="d42d1-104">En algunas ocasiones, en su organización se necesitará un teléfono para llamar a una reunión.</span><span class="sxs-lookup"><span data-stu-id="d42d1-104">Sometimes people in your organization will need to use a phone to call in to a meeting.</span></span> <span data-ttu-id="d42d1-105">Skype empresarial incluye la característica de audioconferencia solo en esta situación.</span><span class="sxs-lookup"><span data-stu-id="d42d1-105">Skype for Business includes the audio conferencing feature for just this situation!</span></span> <span data-ttu-id="d42d1-106">Las personas pueden llamar a reuniones de Skype empresarial con un teléfono, en lugar de usar la aplicación de Skype empresarial en un dispositivo móvil o PC.</span><span class="sxs-lookup"><span data-stu-id="d42d1-106">People can call in to Skype for Business meetings using a phone, instead of using the Skype for Business app on a mobile device or PC.</span></span> 
  
<span data-ttu-id="d42d1-p102">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span><span class="sxs-lookup"><span data-stu-id="d42d1-p102">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="d42d1-109">Para ver las preguntas más frecuentes acerca de las audioconferencias, consulte [Preguntas frecuentes sobre audioconferencias](/MicrosoftTeams/audio-conferencing-common-questions).</span><span class="sxs-lookup"><span data-stu-id="d42d1-109">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](/MicrosoftTeams/audio-conferencing-common-questions).</span></span>

## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a><span data-ttu-id="d42d1-110">Paso 1: averiguar si Audioconferencia está disponible en su país o región</span><span class="sxs-lookup"><span data-stu-id="d42d1-110">Step 1: Find out if Audio Conferencing is available in your country/region</span></span>
<span data-ttu-id="d42d1-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="d42d1-111"><a name="__top"> </a></span></span>

<span data-ttu-id="d42d1-112">Vaya a la [Disponibilidad de país y región para Audioconferencia y Planes de llamadas](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) y seleccione su país o región para obtener información sobre la disponibilidad de Audioconferencia, así como información sobre Sistema telefónico, Planes de llamadas, números gratuitos y de pago, y Créditos de comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="d42d1-112">Go to [Country and region availability for Audio Conferencing and Calling Plans](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) and select your country or region to get availability information about Audio Conferencing, as well as information about Phone System, Calling Plans, toll and toll-free numbers, and Communications Credits.</span></span> 
 
## <a name="step-2-get-and-assign-licenses"></a><span data-ttu-id="d42d1-113">Paso 2: obtener licencias y asignarlas</span><span class="sxs-lookup"><span data-stu-id="d42d1-113">Step 2: Get and assign licenses</span></span>
 
1. <span data-ttu-id="d42d1-114">Para Audioconferencia, necesita una licencia para cada usuario que vaya a configurar reuniones de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="d42d1-114">For Audio Conferencing, you need a license for each user who will set up dial-in meetings.</span></span> <span data-ttu-id="d42d1-115">Para conocer las licencias que necesita comprar para las conferencias de audio y cuánto cuestan, vea [licencias complementarias de Skype empresarial](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="d42d1-115">To learn which licenses you need to buy for Audio Conferencing and how much they will cost, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

    >[!NOTE] 
    > <span data-ttu-id="d42d1-116">Las conferencias de audio se incluyen en las licencias de Office 365 Enterprise E5 y como complemento.</span><span class="sxs-lookup"><span data-stu-id="d42d1-116">Audio Conferencing is included in Office 365 Enterprise E5 licenses and as an add-on.</span></span>
        
2. <span data-ttu-id="d42d1-117">Después de comprar las licencias de audioconferencia, tendrá que asignarlas a las personas de su organización que vayan a programar o coordinar reuniones.</span><span class="sxs-lookup"><span data-stu-id="d42d1-117">After you buy the Audio Conferencing licenses, you will need to assign them to those people in your organization who are going to schedule or lead meetings.</span></span> <span data-ttu-id="d42d1-118">Consulte [asignar o quitar licencias de Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) que compró a las personas de su organización que vayan a programar o coordinar reuniones.</span><span class="sxs-lookup"><span data-stu-id="d42d1-118">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.</span></span>
    
3. <span data-ttu-id="d42d1-119">También se recomienda que asigne licencias de Créditos de comunicaciones (que no cuesta nada) a los mismos usuarios que asignó licencias en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="d42d1-119">We also recommend that you assign Communications Credits licenses (they don’t cost anything) to the same people you assigned licenses to in the previous step.</span></span> <span data-ttu-id="d42d1-120">Para obtener información sobre cómo configurar créditos de comunicaciones, consulte [configurar créditos de comunicaciones para su organización](/microsoftteams/set-up-communications-credits-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="d42d1-120">To learn how to set up Communications Credits, see [Set up Communications Credits for your organization](/microsoftteams/set-up-communications-credits-for-your-organization).</span></span>
    
> [!NOTE]
> <span data-ttu-id="d42d1-121">También puedes configurar las [conferencias de audio por minuto](/microsoftteams/audio-conferencing-pay-per-minute).</span><span class="sxs-lookup"><span data-stu-id="d42d1-121">You can also set up [pay-per-minute Audio Conferencing](/microsoftteams/audio-conferencing-pay-per-minute).</span></span>

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a><span data-ttu-id="d42d1-122">Paso 3: obtener los números de servicio para el puente de conferencia</span><span class="sxs-lookup"><span data-stu-id="d42d1-122">Step 3: Get service numbers for your conferencing bridges</span></span>
<span data-ttu-id="d42d1-123"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="d42d1-123"></span></span>

<span data-ttu-id="d42d1-124">En Audioconferencia, no puede usar números de teléfono para los usuarios; debe obtener números de servicio.</span><span class="sxs-lookup"><span data-stu-id="d42d1-124">For Audio Conferencing, you can’t use phone numbers for users; you will need to get service numbers.</span></span> <span data-ttu-id="d42d1-125">Puede obtener números de pago o números gratuitos de servicio para el puente de conferencia.</span><span class="sxs-lookup"><span data-stu-id="d42d1-125">You can get either toll or toll-free service numbers for your conferencing bridges.</span></span> <span data-ttu-id="d42d1-126">Hay tres formas de obtene números de servicio gratuitos y de pago:</span><span class="sxs-lookup"><span data-stu-id="d42d1-126">There are three ways to get toll and toll-free service numbers:</span></span> 
  
- <span data-ttu-id="d42d1-127">**Use el centro de administración de Skype empresarial**.</span><span class="sxs-lookup"><span data-stu-id="d42d1-127">**Use the Skype for Business admin center**.</span></span> <span data-ttu-id="d42d1-128">Para algunos países o regiones, puede obtener números de servicio para sus puentes de conferencia con el centro de administración de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="d42d1-128">For some countries/regions, you can get service numbers for your conferencing bridges using the Skype for Business admin center.</span></span> <span data-ttu-id="d42d1-129">Consulta [obtener números de teléfono de servicio](/microsoftteams/getting-service-phone-numbers).</span><span class="sxs-lookup"><span data-stu-id="d42d1-129">See [Getting service phone numbers](/microsoftteams/getting-service-phone-numbers).</span></span>
    
- <span data-ttu-id="d42d1-130">**Porte los números de servicio existentes**.</span><span class="sxs-lookup"><span data-stu-id="d42d1-130">**Port your existing service numbers**.</span></span> <span data-ttu-id="d42d1-131">Para migrar o transferir números existentes de su proveedor de servicios actual u operador telefónico a Office 365.</span><span class="sxs-lookup"><span data-stu-id="d42d1-131">To port or transfer existing numbers from your current service provider or phone carrier to Office 365.</span></span> <span data-ttu-id="d42d1-132">Consulte [Transferir números de teléfono a Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) o [Administrar los números de teléfono de su organización](/microsoftteams/manage-phone-numbers-for-your-organization) para obtener más información que le ayude a hacer esto.</span><span class="sxs-lookup"><span data-stu-id="d42d1-132">You can see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) or [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="d42d1-133">**Usar un formulario de solicitud para números nuevos**.</span><span class="sxs-lookup"><span data-stu-id="d42d1-133">**Use a request form for new numbers**.</span></span> <span data-ttu-id="d42d1-134">A veces, en función de su país o región, no podrá obtener los nuevos números de servicio con el centro de administración de Skype empresarial o necesitará números de teléfono o códigos de área específicos.</span><span class="sxs-lookup"><span data-stu-id="d42d1-134">Sometimes (depending on your country/region) you won't be able to get your new service numbers using the Skype for Business admin center, or you will need specific phone numbers or area codes.</span></span> <span data-ttu-id="d42d1-135">En ese caso, tendrá que descargar un formulario y enviárnoslo.</span><span class="sxs-lookup"><span data-stu-id="d42d1-135">If so, you will need to download a form and send it back to us.</span></span> <span data-ttu-id="d42d1-136">Para obtener más información, vea [Administrar los números de teléfono de su organización](/microsoftteams/manage-phone-numbers-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="d42d1-136">See [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information.</span></span> 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a><span data-ttu-id="d42d1-137">Paso 4: asignar un número de servicio al puente de conferencia</span><span class="sxs-lookup"><span data-stu-id="d42d1-137">Step 4: Assign a service number to the conferencing bridge</span></span>
<span data-ttu-id="d42d1-138"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="d42d1-138"></span></span>

<span data-ttu-id="d42d1-139">Una vez que haya obtenido sus números de teléfono gratuitos o de pago para su puente de conferencia, tendrá que asignar los números para que puedan usarse en las invitaciones a reuniones.</span><span class="sxs-lookup"><span data-stu-id="d42d1-139">Once you get your toll and/or toll-free phone numbers for your conferencing bridge, you need to assign the numbers so they can be used on meeting invitations.</span></span>  

<span data-ttu-id="d42d1-140">Para asignar un nuevo número de teléfono al puente de audioconferencia:</span><span class="sxs-lookup"><span data-stu-id="d42d1-140">To assign a new phone number to your audio conferencing bridge:</span></span>

<span data-ttu-id="d42d1-141">![SFB-logo-30x30. png](../images/sfb-logo-30x30.png) **con el centro de administración de Skype empresarial:**</span><span class="sxs-lookup"><span data-stu-id="d42d1-141">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

 1. <span data-ttu-id="d42d1-142">Vaya al portal de > **Administración** > de **centro de administración de Microsoft 365\*\*\*\*Teams** > **Legacy**.</span><span class="sxs-lookup"><span data-stu-id="d42d1-142">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
 2. <span data-ttu-id="d42d1-143">Seleccione \*\*\*\* > **números de teléfono**de voz.</span><span class="sxs-lookup"><span data-stu-id="d42d1-143">Select **Voice** > **Phone numbers**.</span></span>
 3. <span data-ttu-id="d42d1-144">Seleccione el número de teléfono y haga clic en **asignar**.</span><span class="sxs-lookup"><span data-stu-id="d42d1-144">Select the phone number, and click **Assign**.</span></span>

<span data-ttu-id="d42d1-145">Para obtener más información, consulte [cambiar los números de teléfono en el puente de audioconferencia](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="d42d1-145">For more details, see [Change the phone numbers on your audio conferencing bridge](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span></span>

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a><span data-ttu-id="d42d1-146">Paso 5: establecer el valor predeterminado e idiomas alternativos para un puente de conferencia</span><span class="sxs-lookup"><span data-stu-id="d42d1-146">Step 5: Set the default and alternate languages for a conferencing bridge</span></span>
<span data-ttu-id="d42d1-147"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="d42d1-147"></span></span>

<span data-ttu-id="d42d1-148">A continuación, deseas [configurar los idiomas del operador automático para las conferencias de audio](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) que el operador automático de conferencias usa para saludar a las personas que llaman a un número de teléfono para las conferencias de audio.</span><span class="sxs-lookup"><span data-stu-id="d42d1-148">Next, you want to [Set auto attendant languages for Audio Conferencing](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) that the conferencing auto attendant uses to greet callers when they dial in to a phone number for Audio Conferencing.</span></span> 

<span data-ttu-id="d42d1-149">![Teams-logo-30x30. png](../images/teams-logo-30x30.png) **con el centro de administración de Microsoft Teams**:</span><span class="sxs-lookup"><span data-stu-id="d42d1-149">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="d42d1-150">Desde el panel, vaya a conferencias de**Conferencia**de **reuniones** > .</span><span class="sxs-lookup"><span data-stu-id="d42d1-150">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="d42d1-151">Seleccione el número de teléfono del puente de conferencia, haga clic en **Editar**y, a continuación, elija el idioma predeterminado.</span><span class="sxs-lookup"><span data-stu-id="d42d1-151">Select the conferencing bridge phone number, click **Edit**, and then choose the default language.</span></span>

<span data-ttu-id="d42d1-152">![SFB-logo-30x30. png](../images/sfb-logo-30x30.png) **con el centro de administración de Skype empresarial**:</span><span class="sxs-lookup"><span data-stu-id="d42d1-152">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**:</span></span>

1. <span data-ttu-id="d42d1-153">Vaya al centro > de administración de **Office 365**administración de los**centros** > de administración de**Teams** > **Legacy**.</span><span class="sxs-lookup"><span data-stu-id="d42d1-153">Go to the **Office 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="d42d1-154"> > Seleccione \*\*\*\*\*\*Microsoft Bridge\*\*.</span><span class="sxs-lookup"><span data-stu-id="d42d1-154">Select **Audio conferencing** > **Microsoft bridge**.</span></span> 
3. <span data-ttu-id="d42d1-155">Seleccione el número de teléfono del puente de conferencia, seleccione **establecer idiomas**y, a continuación, elija el idioma predeterminado.</span><span class="sxs-lookup"><span data-stu-id="d42d1-155">Select the conferencing bridge phone number, select **Set languages**, and then choose the default language.</span></span>

## <a name="step-6-set-your-conferencing-bridge-settings"></a><span data-ttu-id="d42d1-156">Paso 6: configurar el puente de conferencia</span><span class="sxs-lookup"><span data-stu-id="d42d1-156">Step 6: Set your conferencing bridge settings</span></span>
<span data-ttu-id="d42d1-157"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="d42d1-157"></span></span>
    
<span data-ttu-id="d42d1-158">Después de configurar el puente de conferencia, compruebe que la configuración predeterminada, como las notificaciones de entrada o salida y la longitud PIN, sea la que va a usar; si no lo es, se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="d42d1-158">After setting up your conferencing bridge, verify that the default settings such as entry/exit notifications and PIN length are the ones you want to use; if they're not, you can change them.</span></span> 

<span data-ttu-id="d42d1-159">![Teams-logo-30x30. png](../images/teams-logo-30x30.png) **con el centro de administración de Microsoft Teams**:</span><span class="sxs-lookup"><span data-stu-id="d42d1-159">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="d42d1-160">Desde el panel, vaya a conferencias de**Conferencia**de **reuniones** > .</span><span class="sxs-lookup"><span data-stu-id="d42d1-160">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="d42d1-161">Seleccione **configuración de puente**.</span><span class="sxs-lookup"><span data-stu-id="d42d1-161">Select **Bridge settings**.</span></span> <span data-ttu-id="d42d1-162">Se abrirá el panel **Configuración de puente**.</span><span class="sxs-lookup"><span data-stu-id="d42d1-162">This will open the **Bridge settings** pane.</span></span> 

<span data-ttu-id="d42d1-163">Para obtener más información, consulte [Cambiar la configuración de un puente de Audioconferencia](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="d42d1-163">For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>

<span data-ttu-id="d42d1-164">![SFB-logo-30x30. png](../images/sfb-logo-30x30.png) **con el centro de administración de Skype empresarial:**</span><span class="sxs-lookup"><span data-stu-id="d42d1-164">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

1. <span data-ttu-id="d42d1-165">Vaya al portal de > **Administración** > de **centro de administración de Microsoft 365\*\*\*\*Teams** > **Legacy**.</span><span class="sxs-lookup"><span data-stu-id="d42d1-165">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="d42d1-166">Seleccione \*\*\*\* > **configuración**de conferencia de audio de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d42d1-166">Select **Audio conferencing** > **Microsoft bridge settings**.</span></span> <span data-ttu-id="d42d1-167">Se abrirá la página de **Configuración de puente de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="d42d1-167">This will open the **Microsoft bridge settings** page.</span></span> 

<span data-ttu-id="d42d1-168">Para obtener más información, consulte [Cambiar la configuración de un puente de Audioconferencia](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="d42d1-168">For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a><span data-ttu-id="d42d1-169">Paso 7: asignar los números de teléfono de acceso telefónico a los usuarios que coordinan las reuniones</span><span class="sxs-lookup"><span data-stu-id="d42d1-169">Step 7: Assign dial-in phone numbers for users who lead meetings</span></span>

<span data-ttu-id="d42d1-170">Después de haber creado un puente de Audioconferencia, debe establecer los números gratuitos y de pago para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="d42d1-170">After you have created an Audio Conferencing bridge, you need to set the toll and toll-free numbers for your users.</span></span>

<span data-ttu-id="d42d1-171">Debe hacer esto para todas las personas de su organización que coordinen o programen reuniones.</span><span class="sxs-lookup"><span data-stu-id="d42d1-171">You will need to do this for all of the people in your organization who lead or schedule meetings.</span></span> 

<span data-ttu-id="d42d1-172">![Teams-logo-30x30. png](../images/teams-logo-30x30.png) **con el centro de administración de Microsoft Teams**:</span><span class="sxs-lookup"><span data-stu-id="d42d1-172">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="d42d1-173">En el panel, haga clic en **usuarios**, seleccione el usuario de la lista y seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="d42d1-173">From the Dashboard, click **Users**, select the user from the list, and select **Edit**.</span></span>
2. <span data-ttu-id="d42d1-174">Seleccione **Editar** junto a **audioconferencia**y, en el panel **audioconferencia** , elija un número en las listas número de **teléfono de pago** y número **gratuito** .</span><span class="sxs-lookup"><span data-stu-id="d42d1-174">Select **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, choose a number in the **Toll number** and **Toll-free** number lists.</span></span>

<span data-ttu-id="d42d1-175">![SFB-logo-30x30. png](../images/sfb-logo-30x30.png) **con el centro de administración de Skype empresarial:**</span><span class="sxs-lookup"><span data-stu-id="d42d1-175">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

1. <span data-ttu-id="d42d1-176">Vaya al **Centro** > de administración de Microsoft 365**portal heredado\*\*\*\*Teams** > .</span><span class="sxs-lookup"><span data-stu-id="d42d1-176">Go to the **Microsoft 365 admin center** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="d42d1-177">Seleccione \*\*\*\* > **usuarios**de la Conferencia de audio y, a continuación, seleccione el usuario de la lista y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="d42d1-177">Select **Audio conferencing** > **Users**, and then select the user from the list and click **Edit**.</span></span> 

<span data-ttu-id="d42d1-178">Si necesita más detalles, vea [Asignar a Microsoft como proveedor de audioconferencias](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).</span><span class="sxs-lookup"><span data-stu-id="d42d1-178">If you need more details, see [Assign Microsoft as the audio conferencing provider](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>


## <a name="step-8-set-up-meeting-invitations-optional"></a><span data-ttu-id="d42d1-179">Paso 8: configurar las invitaciones a reuniones (opcional)</span><span class="sxs-lookup"><span data-stu-id="d42d1-179">Step 8: Set up meeting invitations (optional)</span></span>
<span data-ttu-id="d42d1-180"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="d42d1-180"></span></span>
 
<span data-ttu-id="d42d1-181">Los números de acceso telefónico local establecidos para el usuario se agregarán automáticamente a las invitaciones a reuniones que se envíen a los asistentes de la reunión.</span><span class="sxs-lookup"><span data-stu-id="d42d1-181">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to meeting attendees.</span></span> <span data-ttu-id="d42d1-182">Sin embargo, si lo desea, puede agregar su propia ayuda y vínculos legales, un mensaje de texto y un gráfico de pequeña empresa.</span><span class="sxs-lookup"><span data-stu-id="d42d1-182">However, you can add your own help and legal links, a text message, and small company graphic if you want.</span></span> <span data-ttu-id="d42d1-183">Consulte [personalizar invitaciones a reuniones](../set-up-skype-for-business-online/customize-meeting-invitations.md).</span><span class="sxs-lookup"><span data-stu-id="d42d1-183">See [Customize meeting invitations](../set-up-skype-for-business-online/customize-meeting-invitations.md).</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="d42d1-184">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="d42d1-184">Related topics</span></span>

[<span data-ttu-id="d42d1-185">Preguntas comunes sobre Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="d42d1-185">Audio Conferencing common questions</span></span>](/MicrosoftTeams/audio-conferencing-common-questions)
  
[<span data-ttu-id="d42d1-186">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="d42d1-186">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[<span data-ttu-id="d42d1-187">Números de teléfono para Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="d42d1-187">Phone numbers for Audio Conferencing</span></span>](phone-numbers-for-audio-conferencing.md)
  
[<span data-ttu-id="d42d1-188">Establecer opciones para reuniones y conferencias telefónicas en línea</span><span class="sxs-lookup"><span data-stu-id="d42d1-188">Set options for online meetings and conference calls</span></span>](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
