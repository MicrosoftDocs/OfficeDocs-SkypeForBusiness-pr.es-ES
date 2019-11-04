---
title: Configurar audioconferencias para Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
- LIL_Placement
description: 'Obtenga información sobre cómo configurar las conferencias de acceso telefónico local o de audio para las personas de su empresa que necesitan usar un teléfono para unirse a llamadas en conferencia. '
ms.openlocfilehash: d630f6f149f61609209cc4ead23ed7232647cb08
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "37925371"
---
# <a name="set-up-audio-conferencing-for-microsoft-teams"></a><span data-ttu-id="85fb7-103">Configurar audioconferencias para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="85fb7-103">Set up Audio Conferencing for Microsoft Teams</span></span>

<span data-ttu-id="85fb7-104">En algunas ocasiones, en su organización se necesitará un teléfono para llamar a una reunión.</span><span class="sxs-lookup"><span data-stu-id="85fb7-104">Sometimes people in your organization will need to use a phone to call in to a meeting.</span></span> <span data-ttu-id="85fb7-105">Microsoft Teams incluye la característica de audioconferencia solo para esta situación.</span><span class="sxs-lookup"><span data-stu-id="85fb7-105">Microsoft Teams includes the audio conferencing feature for just this situation!</span></span> <span data-ttu-id="85fb7-106">Los usuarios pueden llamar a las reuniones de Teams mediante un teléfono, en lugar de usar la aplicación de Teams en un dispositivo móvil o PC.</span><span class="sxs-lookup"><span data-stu-id="85fb7-106">People can call in to Teams meetings using a phone, instead of using the Teams app on a mobile device or PC.</span></span> 
  
<span data-ttu-id="85fb7-107">Solo debe configurar las audioconferencias para los usuarios que van a programar o dirigir las reuniones.</span><span class="sxs-lookup"><span data-stu-id="85fb7-107">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings.</span></span> <span data-ttu-id="85fb7-108">Los asistentes que se conectan por teléfono a la reunión no necesitan tener asignada ninguna licencia ni otra configuración.</span><span class="sxs-lookup"><span data-stu-id="85fb7-108">Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="85fb7-109">Para ver las preguntas más frecuentes acerca de las audioconferencias, consulte [Preguntas frecuentes sobre audioconferencias](audio-conferencing-common-questions.md).</span><span class="sxs-lookup"><span data-stu-id="85fb7-109">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](audio-conferencing-common-questions.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a><span data-ttu-id="85fb7-110">Paso 1: averiguar si Audioconferencia está disponible en su país o región</span><span class="sxs-lookup"><span data-stu-id="85fb7-110">Step 1: Find out if Audio Conferencing is available in your country/region</span></span>
<span data-ttu-id="85fb7-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="85fb7-111"></span></span>

<span data-ttu-id="85fb7-112">Vaya a la [Disponibilidad de país y región para Audioconferencia y Planes de llamadas](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) y seleccione su país o región para obtener información sobre la disponibilidad de Audioconferencia, así como información sobre Sistema telefónico, Planes de llamadas, números gratuitos y de pago, y Créditos de comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="85fb7-112">Go to [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) and select your country or region to get availability information about Audio Conferencing, as well as information about Phone System, Calling Plans, toll and toll-free numbers, and Communications Credits.</span></span> 
 
## <a name="step-2-get-and-assign-licenses"></a><span data-ttu-id="85fb7-113">Paso 2: obtener licencias y asignarlas</span><span class="sxs-lookup"><span data-stu-id="85fb7-113">Step 2: Get and assign licenses</span></span>
 
1. <span data-ttu-id="85fb7-114">Para Audioconferencia, necesita una licencia para cada usuario que vaya a configurar reuniones de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="85fb7-114">For Audio Conferencing, you need a license for each user who will set up dial-in meetings.</span></span> <span data-ttu-id="85fb7-115">Para conocer las licencias que necesita comprar para la audioconferencia y cuánto cuestan, vea [licencias complementarias de Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="85fb7-115">To learn which licenses you need to buy for Audio Conferencing and how much they will cost, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

    >[!NOTE] 
    > <span data-ttu-id="85fb7-116">Las conferencias de audio se incluyen en las licencias de Office 365 Enterprise E5 y como complemento.</span><span class="sxs-lookup"><span data-stu-id="85fb7-116">Audio Conferencing is included in Office 365 Enterprise E5 licenses and as an add-on.</span></span>
        
2. <span data-ttu-id="85fb7-117">Después de comprar las licencias de audioconferencia, tendrá que asignarlas a las personas de su organización que vayan a programar o coordinar reuniones.</span><span class="sxs-lookup"><span data-stu-id="85fb7-117">After you buy the Audio Conferencing licenses, you will need to assign them to those people in your organization who are going to schedule or lead meetings.</span></span> <span data-ttu-id="85fb7-118">Consulte [asignar licencias a usuarios en Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) que compró a las personas de su organización que van a programar o coordinar reuniones.</span><span class="sxs-lookup"><span data-stu-id="85fb7-118">See [Assign licenses to users in Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.</span></span>
    
3. <span data-ttu-id="85fb7-119">También se recomienda que asigne licencias de Créditos de comunicaciones (que no cuesta nada) a los mismos usuarios que asignó licencias en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="85fb7-119">We also recommend that you assign Communications Credits licenses (they don’t cost anything) to the same people you assigned licenses to in the previous step.</span></span> <span data-ttu-id="85fb7-120">Para obtener información sobre cómo configurar créditos de comunicaciones, consulte [configurar créditos de comunicaciones para su organización](set-up-communications-credits-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="85fb7-120">To learn how to set up Communications Credits, see [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="85fb7-121">También puedes configurar las [conferencias de audio por minuto](audio-conferencing-pay-per-minute.md).</span><span class="sxs-lookup"><span data-stu-id="85fb7-121">You can also set up [pay-per-minute Audio Conferencing](audio-conferencing-pay-per-minute.md).</span></span>

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a><span data-ttu-id="85fb7-122">Paso 3: obtener los números de servicio para el puente de conferencia</span><span class="sxs-lookup"><span data-stu-id="85fb7-122">Step 3: Get service numbers for your conferencing bridges</span></span>
<span data-ttu-id="85fb7-123"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="85fb7-123"></span></span>

<span data-ttu-id="85fb7-124">En Audioconferencia, no puede usar números de teléfono para los usuarios; debe obtener números de servicio.</span><span class="sxs-lookup"><span data-stu-id="85fb7-124">For Audio Conferencing, you can’t use phone numbers for users; you will need to get service numbers.</span></span> <span data-ttu-id="85fb7-125">Puede obtener números de pago o números gratuitos de servicio para el puente de conferencia.</span><span class="sxs-lookup"><span data-stu-id="85fb7-125">You can get either toll or toll-free service numbers for your conferencing bridges.</span></span> <span data-ttu-id="85fb7-126">Hay tres formas de obtene números de servicio gratuitos y de pago:</span><span class="sxs-lookup"><span data-stu-id="85fb7-126">There are three ways to get toll and toll-free service numbers:</span></span> 
  
- <span data-ttu-id="85fb7-127">**Use el centro de administración de Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="85fb7-127">**Use the Microsoft Teams admin center**.</span></span> <span data-ttu-id="85fb7-128">Para algunos países o regiones, puede obtener números de servicio para sus puentes de conferencia con el centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="85fb7-128">For some countries/regions, you can get service numbers for your conferencing bridges using the Microsoft Teams admin center.</span></span> <span data-ttu-id="85fb7-129">Consulta [obtener números de teléfono de servicio](/microsoftteams/getting-service-phone-numbers).</span><span class="sxs-lookup"><span data-stu-id="85fb7-129">See [Getting service phone numbers](/microsoftteams/getting-service-phone-numbers).</span></span>
    
- <span data-ttu-id="85fb7-130">**Porte los números de servicio existentes**.</span><span class="sxs-lookup"><span data-stu-id="85fb7-130">**Port your existing service numbers**.</span></span> <span data-ttu-id="85fb7-131">Para migrar o transferir números existentes de su proveedor de servicios actual u operador telefónico a Office 365.</span><span class="sxs-lookup"><span data-stu-id="85fb7-131">To port or transfer existing numbers from your current service provider or phone carrier to Office 365.</span></span> <span data-ttu-id="85fb7-132">Puede ver [transferir números de teléfono a teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) o [administrar números de teléfono de su organización](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) para obtener más información que le ayude a hacerlo.</span><span class="sxs-lookup"><span data-stu-id="85fb7-132">You can see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) or [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="85fb7-133">**Usar un formulario de solicitud para números nuevos**.</span><span class="sxs-lookup"><span data-stu-id="85fb7-133">**Use a request form for new numbers**.</span></span> <span data-ttu-id="85fb7-134">A veces, en función de su país o región, no podrá obtener los números de servicio nuevos mediante el centro de administración de Microsoft Teams o necesitará números de teléfono o códigos de área específicos.</span><span class="sxs-lookup"><span data-stu-id="85fb7-134">Sometimes (depending on your country/region) you won't be able to get your new service numbers using the Microsoft Teams admin center, or you will need specific phone numbers or area codes.</span></span> <span data-ttu-id="85fb7-135">En ese caso, tendrá que descargar un formulario y enviárnoslo.</span><span class="sxs-lookup"><span data-stu-id="85fb7-135">If so, you will need to download a form and send it back to us.</span></span> <span data-ttu-id="85fb7-136">Para obtener más información, vea [Administrar los números de teléfono de su organización](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="85fb7-136">See [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) for more information.</span></span> 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a><span data-ttu-id="85fb7-137">Paso 4: asignar un número de servicio al puente de conferencia</span><span class="sxs-lookup"><span data-stu-id="85fb7-137">Step 4: Assign a service number to the conferencing bridge</span></span>
<span data-ttu-id="85fb7-138"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="85fb7-138"></span></span>

<span data-ttu-id="85fb7-139">Una vez que haya obtenido sus números de teléfono gratuitos o de pago para su puente de conferencia, tendrá que asignar los números para que puedan usarse en las invitaciones a reuniones.</span><span class="sxs-lookup"><span data-stu-id="85fb7-139">Once you get your toll and/or toll-free phone numbers for your conferencing bridge, you need to assign the numbers so they can be used on meeting invitations.</span></span>  

<span data-ttu-id="85fb7-140">Siga estos pasos para asignar un nuevo número de teléfono a su puente de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="85fb7-140">Follow these steps to assign a new phone number to your audio conferencing bridge.</span></span>

<span data-ttu-id="85fb7-141">![Un icono que muestra el logotipo](media/sfb-logo-30x30.png) de Skype empresarial **con el centro de administración de Skype empresarial:**</span><span class="sxs-lookup"><span data-stu-id="85fb7-141">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

 1. <span data-ttu-id="85fb7-142">Vaya al portal de > **Administración** > de **centro de administración de Microsoft 365\*\*\*\*Teams** > **Legacy**.</span><span class="sxs-lookup"><span data-stu-id="85fb7-142">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
 2. <span data-ttu-id="85fb7-143">Seleccione \*\*\*\* > **números de teléfono**de voz.</span><span class="sxs-lookup"><span data-stu-id="85fb7-143">Select **Voice** > **Phone numbers**.</span></span>
 3. <span data-ttu-id="85fb7-144">Seleccione el número de teléfono y haga clic en **asignar**.</span><span class="sxs-lookup"><span data-stu-id="85fb7-144">Select the phone number, and click **Assign**.</span></span>

<span data-ttu-id="85fb7-145">Para obtener más información, consulte [cambiar los números de teléfono en el puente de audioconferencia](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="85fb7-145">For more details, see [Change the phone numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a><span data-ttu-id="85fb7-146">Paso 5: establecer el valor predeterminado e idiomas alternativos para un puente de conferencia</span><span class="sxs-lookup"><span data-stu-id="85fb7-146">Step 5: Set the default and alternate languages for a conferencing bridge</span></span>
<span data-ttu-id="85fb7-147"><a name="__top"></a> A continuación, desea [configurar los idiomas del operador automático para audioconferencia en Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) que el operador automático de conferencias usa para saludar a las personas que llaman a un número de teléfono para las conferencias de audio.</span><span class="sxs-lookup"><span data-stu-id="85fb7-147"><a name="__top"> </a> Next, you want to [Set auto attendant languages for Audio Conferencing in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) that the conferencing auto attendant uses to greet callers when they dial in to a phone number for Audio Conferencing.</span></span> 

<span data-ttu-id="85fb7-148">![Un icono que muestra el logotipo](media/teams-logo-30x30.png) de Microsoft Teams **con el centro de administración de Microsoft Teams**:</span><span class="sxs-lookup"><span data-stu-id="85fb7-148">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="85fb7-149">Desde el panel, vaya a conferencias de**Conferencia**de **reuniones** > .</span><span class="sxs-lookup"><span data-stu-id="85fb7-149">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="85fb7-150">Seleccione el número de teléfono del puente de conferencia, haga clic en **Editar**y, a continuación, elija el idioma predeterminado.</span><span class="sxs-lookup"><span data-stu-id="85fb7-150">Select the conferencing bridge phone number, click **Edit**, and then choose the default language.</span></span>

## <a name="step-6-set-your-conferencing-bridge-settings"></a><span data-ttu-id="85fb7-151">Paso 6: configurar el puente de conferencia</span><span class="sxs-lookup"><span data-stu-id="85fb7-151">Step 6: Set your conferencing bridge settings</span></span>
<span data-ttu-id="85fb7-152"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="85fb7-152"></span></span>
    
<span data-ttu-id="85fb7-153">Después de configurar el puente de conferencia, compruebe que la configuración predeterminada, como las notificaciones de entrada o salida y la longitud PIN, sea la que va a usar; si no lo es, se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="85fb7-153">After setting up your conferencing bridge, verify that the default settings such as entry/exit notifications and PIN length are the ones you want to use; if they're not, you can change them.</span></span> 

<span data-ttu-id="85fb7-154">![Un icono que muestra el logotipo](media/teams-logo-30x30.png) de Microsoft Teams **con el centro de administración de Microsoft Teams**:</span><span class="sxs-lookup"><span data-stu-id="85fb7-154">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="85fb7-155">Desde el panel, vaya a conferencias de**Conferencia**de **reuniones** > .</span><span class="sxs-lookup"><span data-stu-id="85fb7-155">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="85fb7-156">Seleccione **configuración de puente**.</span><span class="sxs-lookup"><span data-stu-id="85fb7-156">Select **Bridge settings**.</span></span> <span data-ttu-id="85fb7-157">Se abrirá el panel **Configuración de puente**.</span><span class="sxs-lookup"><span data-stu-id="85fb7-157">This will open the **Bridge settings** pane.</span></span> 

<span data-ttu-id="85fb7-158">Para obtener más información, consulte [Cambiar la configuración de un puente de Audioconferencia](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="85fb7-158">For more details, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a><span data-ttu-id="85fb7-159">Paso 7: asignar los números de teléfono de acceso telefónico a los usuarios que coordinan las reuniones</span><span class="sxs-lookup"><span data-stu-id="85fb7-159">Step 7: Assign dial-in phone numbers for users who lead meetings</span></span>

<span data-ttu-id="85fb7-160">Después de haber creado un puente de Audioconferencia, debe establecer los números gratuitos y de pago para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="85fb7-160">After you have created an Audio Conferencing bridge, you need to set the toll and toll-free numbers for your users.</span></span>

<span data-ttu-id="85fb7-161">Debe hacer esto para todas las personas de su organización que coordinen o programen reuniones.</span><span class="sxs-lookup"><span data-stu-id="85fb7-161">You will need to do this for all of the people in your organization who lead or schedule meetings.</span></span> 

<span data-ttu-id="85fb7-162">![Un icono que muestra el logotipo](media/teams-logo-30x30.png) de Microsoft Teams **con el centro de administración de Microsoft Teams**:</span><span class="sxs-lookup"><span data-stu-id="85fb7-162">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="85fb7-163">En el panel, haga clic en **usuarios**, seleccione el usuario de la lista y seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="85fb7-163">From the Dashboard, click **Users**, select the user from the list, and select **Edit**.</span></span>
2. <span data-ttu-id="85fb7-164">Seleccione **Editar** junto a **audioconferencia**y, en el panel **audioconferencia** , elija un número en las listas número de **teléfono de pago** y número **gratuito** .</span><span class="sxs-lookup"><span data-stu-id="85fb7-164">Select **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, choose a number in the **Toll number** and **Toll-free** number lists.</span></span>

<span data-ttu-id="85fb7-165">Si necesita más detalles, vea [Asignar a Microsoft como proveedor de audioconferencias](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span><span class="sxs-lookup"><span data-stu-id="85fb7-165">If you need more details, see [Assign Microsoft as the audio conferencing provider](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>


## <a name="step-8-set-up-meeting-invitations-optional"></a><span data-ttu-id="85fb7-166">Paso 8: configurar las invitaciones a reuniones (opcional)</span><span class="sxs-lookup"><span data-stu-id="85fb7-166">Step 8: Set up meeting invitations (optional)</span></span>
<span data-ttu-id="85fb7-167"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="85fb7-167"></span></span>
 
<span data-ttu-id="85fb7-168">Los números de acceso telefónico local establecidos para el usuario se agregarán automáticamente a las invitaciones a reuniones que se envíen a los asistentes de la reunión.</span><span class="sxs-lookup"><span data-stu-id="85fb7-168">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to meeting attendees.</span></span> <span data-ttu-id="85fb7-169">Sin embargo, si lo desea, puede agregar su propia ayuda y vínculos legales, un mensaje de texto y un gráfico de pequeña empresa.</span><span class="sxs-lookup"><span data-stu-id="85fb7-169">However, you can add your own help and legal links, a text message, and small company graphic if you want.</span></span> <span data-ttu-id="85fb7-170">Consulte [personalizar invitaciones a reuniones](meeting-settings-in-teams.md#customize-meeting-invitations).</span><span class="sxs-lookup"><span data-stu-id="85fb7-170">See [Customize meeting invitations](meeting-settings-in-teams.md#customize-meeting-invitations).</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="85fb7-171">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="85fb7-171">Related topics</span></span>

[<span data-ttu-id="85fb7-172">Preguntas comunes sobre Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="85fb7-172">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
  
[<span data-ttu-id="85fb7-173">Números de teléfono para Audioconferencia en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="85fb7-173">Phone numbers for Audio Conferencing in Microsoft Teams</span></span>](phone-numbers-for-audio-conferencing-in-teams.md)
  
[<span data-ttu-id="85fb7-174">Establecer opciones para reuniones y conferencias telefónicas en línea</span><span class="sxs-lookup"><span data-stu-id="85fb7-174">Set options for online meetings and conference calls</span></span>](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
