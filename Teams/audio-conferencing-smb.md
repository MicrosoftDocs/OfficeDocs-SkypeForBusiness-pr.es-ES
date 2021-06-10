---
title: Configurar la Audioconferencia para empresas pequeñas y medianas
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: jonorton, tonysmit
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
description: 'Obtenga información sobre cómo configurar las audioconferencias en su pequeña o mediana empresa para las personas que necesitan usar un teléfono para llamar a las reuniones. '
ms.openlocfilehash: e7a3461453255a7a61f6a1095e9cb9697070771c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122354"
---
# <a name="set-up-audio-conferencing-for-small-and-medium-businesses"></a><span data-ttu-id="70730-103">Configurar la Audioconferencia para empresas pequeñas y medianas</span><span class="sxs-lookup"><span data-stu-id="70730-103">Set up Audio Conferencing for small and medium businesses</span></span>

<span data-ttu-id="70730-104">Con audioconferencia, los usuarios pueden llamar Teams reuniones con un teléfono en lugar de usar la aplicación Teams en su dispositivo móvil o desde su equipo.</span><span class="sxs-lookup"><span data-stu-id="70730-104">With Audio Conferencing, people can call in to Teams meetings using a phone instead of using the Teams app on their mobile device or from their computer.</span></span>  

<span data-ttu-id="70730-105">Si es una pequeña o mediana empresa con hasta 300 usuarios y actualmente no tiene ninguna licencia de Conferencias de audio, puede obtener Conferencias de audio gratis durante un año.</span><span class="sxs-lookup"><span data-stu-id="70730-105">If you're a small or medium-sized business with up to 300 users and you currently don’t have any Audio Conferencing licenses, you can get Audio Conferencing free for one year.</span></span> <span data-ttu-id="70730-106">Esta oferta gratuita está disponible a partir del 1 de octubre de 2020.</span><span class="sxs-lookup"><span data-stu-id="70730-106">This free offer is available starting October 1, 2020.</span></span>

<span data-ttu-id="70730-107">La licencia de complemento de audioconferencia se puede aplicar a los usuarios que tienen Microsoft 365 Empresa Básico, Business Standard, Business Premium, Enterprise E1 o Enterprise licencias de E3.</span><span class="sxs-lookup"><span data-stu-id="70730-107">The Audio Conferencing add-on license can be applied to users who have Microsoft 365 Business Basic, Business Standard, Business Premium, Enterprise E1, or Enterprise E3 licenses.</span></span> <span data-ttu-id="70730-108">Para obtener más información, [vea Teams de complementos](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="70730-108">To learn more, see [Teams add-on licenses](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span></span>

> [!NOTE]
> <span data-ttu-id="70730-109">Si tiene Enterprise E5 o Microsoft 365 Business Voice, no podrá usar la oferta gratuita de audioconferencia porque estas licencias ya incluyen Conferencias de audio.</span><span class="sxs-lookup"><span data-stu-id="70730-109">If you have Enterprise E5 or Microsoft 365 Business Voice, you won't be able to use the free Audio Conferencing offer because these licenses already include Audio Conferencing.</span></span>

<span data-ttu-id="70730-110">En este artículo, le explicamos cómo configurar audioconferencias.</span><span class="sxs-lookup"><span data-stu-id="70730-110">In this article, we'll walk you through how to set up Audio Conferencing.</span></span> <span data-ttu-id="70730-111">Solo debe configurar las audioconferencias para los usuarios que van a programar o dirigir las reuniones.</span><span class="sxs-lookup"><span data-stu-id="70730-111">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings.</span></span> <span data-ttu-id="70730-112">Los asistentes a la reunión que llaman a las reuniones no necesitan licencias u otra configuración.</span><span class="sxs-lookup"><span data-stu-id="70730-112">Meeting attendees who call in to meetings don't need licenses or other setup.</span></span> <span data-ttu-id="70730-113">Para obtener más información, vea [Audioconferencia.](audio-conferencing-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="70730-113">To learn more, see [Audio Conferencing](audio-conferencing-in-office-365.md).</span></span>

## <a name="set-up-audio-conferencing"></a><span data-ttu-id="70730-114">Configurar Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="70730-114">Set up Audio Conferencing</span></span>

<span data-ttu-id="70730-115">Al configurar audioconferencias, se asigna automáticamente un número de teléfono al puente de conferencias para que se pueda usar en invitaciones a reuniones.</span><span class="sxs-lookup"><span data-stu-id="70730-115">When you set up Audio Conferencing, a phone number is automatically assigned to your conferencing bridge so that it can be used in meeting invitations.</span></span> <span data-ttu-id="70730-116">El número de teléfono asignado como número predeterminado del puente de conferencia será uno del país o región de su organización.</span><span class="sxs-lookup"><span data-stu-id="70730-116">The phone number that's assigned as the default number of your conferencing bridge will be one from the country or region of your organization.</span></span> <span data-ttu-id="70730-117">Este número de teléfono es un número de pago, en el que se pueden aplicar cargos de larga distancia.</span><span class="sxs-lookup"><span data-stu-id="70730-117">This phone number is a toll number, in which long-distance charges may apply.</span></span>

> [!NOTE]
> <span data-ttu-id="70730-118">También puede usar un número gratuito, que requiere algunos pasos adicionales.</span><span class="sxs-lookup"><span data-stu-id="70730-118">You can also use a toll-free number, which requires a few additional steps.</span></span> <span data-ttu-id="70730-119">Para obtener más información sobre los números de teléfono para el puente de conferencias, vea Números de teléfono de [audioconferencia](#audio-conferencing-phone-numbers) más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="70730-119">To learn more about phone numbers for your conferencing bridge, see [Audio Conferencing phone numbers](#audio-conferencing-phone-numbers) later in this article.</span></span>

### <a name="step-1-get-audio-conferencing-licenses"></a><span data-ttu-id="70730-120">Paso 1: Obtener licencias de audioconferencia</span><span class="sxs-lookup"><span data-stu-id="70730-120">Step 1: Get Audio Conferencing licenses</span></span>

<span data-ttu-id="70730-121">Obtenga una licencia de audioconferencia para cada persona que dirigirá las reuniones.</span><span class="sxs-lookup"><span data-stu-id="70730-121">Get one Audio Conferencing license for each person who will lead meetings.</span></span> <span data-ttu-id="70730-122">Use el Microsoft 365 de administración para ello.</span><span class="sxs-lookup"><span data-stu-id="70730-122">Use the Microsoft 365 admin center to do this.</span></span>

1. <span data-ttu-id="70730-123">En el Microsoft 365 de administración, vaya a Servicios de compra de facturación y, a continuación, en la parte inferior de la página, seleccione  >   **Complementos.**</span><span class="sxs-lookup"><span data-stu-id="70730-123">In the Microsoft 365 admin center, go to **Billing** > **Purchase services**, and then at the bottom of the page, select **Add-ons**.</span></span>
2. <span data-ttu-id="70730-124">Seleccione Microsoft 365 detalles de promoción de adopción de **audioconferencias** y, a  >  continuación, **seleccione Obtener ahora.**</span><span class="sxs-lookup"><span data-stu-id="70730-124">Select **Microsoft 365 Audio Conferencing Adoption Promo** > **Details**, and then select **Get now**.</span></span>
3. <span data-ttu-id="70730-125">Escriba el número de licencias que necesita para los organizadores de la reunión y, a continuación, complete el pedido.</span><span class="sxs-lookup"><span data-stu-id="70730-125">Enter the number of licenses you need for your meeting organizers, and then complete your order.</span></span>

    :::image type="content" source="media/audio-conferencing-smb-add.png" alt-text="Captura de pantalla de la licencia de promoción de adopción de audioconferencias":::

    > [!NOTE]
    > <span data-ttu-id="70730-127">Desactive o seleccione asignar automáticamente a todos los usuarios sin licencias, dependiendo de si desea asignar automáticamente una licencia de audioconferencia a todos los usuarios que **no** tengan esta licencia.</span><span class="sxs-lookup"><span data-stu-id="70730-127">Clear or select the **Automatically assign to all of your users with no licenses**, depending on whether you want to automatically assign an Audio Conferencing license to all users who don't have this license.</span></span>

### <a name="step-2-assign-an-audio-conferencing-license-to-users-who-lead-meetings"></a><span data-ttu-id="70730-128">Paso 2: Asignar una licencia de audioconferencia a los usuarios que conducen reuniones</span><span class="sxs-lookup"><span data-stu-id="70730-128">Step 2: Assign an Audio Conferencing license to users who lead meetings</span></span>

<span data-ttu-id="70730-129">Asigne una licencia a cada persona que dirigirá las reuniones.</span><span class="sxs-lookup"><span data-stu-id="70730-129">Assign a license to each person who will lead meetings.</span></span> <span data-ttu-id="70730-130">Use el Microsoft 365 de administración para ello.</span><span class="sxs-lookup"><span data-stu-id="70730-130">Use the Microsoft 365 admin center to do this.</span></span>

#### <a name="assign-a-license-to-one-user"></a><span data-ttu-id="70730-131">Asignar una licencia a un usuario</span><span class="sxs-lookup"><span data-stu-id="70730-131">Assign a license to one user</span></span>

1. <span data-ttu-id="70730-132">En el Microsoft 365 de administración, vaya a **Usuarios**  >  **usuarios activos.**</span><span class="sxs-lookup"><span data-stu-id="70730-132">In the Microsoft 365 admin center, go to **Users** > **Active users**.</span></span>  
2. <span data-ttu-id="70730-133">Seleccione la fila del usuario al que desea asignar la licencia y, a continuación, en el panel, seleccione **Licencias y aplicaciones.**</span><span class="sxs-lookup"><span data-stu-id="70730-133">Select the row of the user you want to assign the license to, and then in the pane, select **Licenses and Apps**.</span></span>
3. <span data-ttu-id="70730-134">Active la **Microsoft 365 de audioconferencia y,** a continuación, **seleccione Guardar cambios.**</span><span class="sxs-lookup"><span data-stu-id="70730-134">Select the **Microsoft 365 Audio Conferencing** check box, and then select **Save changes**.</span></span>

#### <a name="assign-a-license-to-multiple-users"></a><span data-ttu-id="70730-135">Asignar una licencia a varios usuarios</span><span class="sxs-lookup"><span data-stu-id="70730-135">Assign a license to multiple users</span></span>

1. <span data-ttu-id="70730-136">En el Microsoft 365 de administración, vaya a **Usuarios**  >  **usuarios activos.**</span><span class="sxs-lookup"><span data-stu-id="70730-136">In the Microsoft 365 admin center, go to **Users** > **Active users**.</span></span>  
2. <span data-ttu-id="70730-137">Seleccione los círculos junto a los usuarios a los que desea asignar la licencia y, a continuación, seleccione **Administrar licencias de producto.**</span><span class="sxs-lookup"><span data-stu-id="70730-137">Select the circles next to the users you want to assign the license to, and then select **Manage product licenses**.</span></span>
3. <span data-ttu-id="70730-138">En el **panel Administrar licencias de producto,** seleccione Asignar **más**.</span><span class="sxs-lookup"><span data-stu-id="70730-138">In the **Manage product licenses** pane, select **Assign more**.</span></span>
4. <span data-ttu-id="70730-139">Active la **Microsoft 365 de audioconferencia y,** a continuación, **seleccione Guardar cambios.**</span><span class="sxs-lookup"><span data-stu-id="70730-139">Select the **Microsoft 365 Audio Conferencing** check box, and then select **Save changes**.</span></span>  

## <a name="schedule-teams-meetings-in-outlook"></a><span data-ttu-id="70730-140">Programar Teams reuniones en Outlook</span><span class="sxs-lookup"><span data-stu-id="70730-140">Schedule Teams meetings in Outlook</span></span>

<span data-ttu-id="70730-141">Los organizadores de la reunión ahora pueden programar reuniones en Outlook.</span><span class="sxs-lookup"><span data-stu-id="70730-141">Your meeting organizers can now schedule meetings in Outlook.</span></span> <span data-ttu-id="70730-142">En Outlook, vaya **a Calendario** y, a continuación, seleccione el **botón Nueva Teams reunión.**</span><span class="sxs-lookup"><span data-stu-id="70730-142">In Outlook, go to **Calendar**, and then select the **New Teams meeting** button.</span></span> <span data-ttu-id="70730-143">Los números de acceso telefónico de la reunión y el id. de conferencia se agregan automáticamente a la invitación de reunión que se envía a los asistentes a la reunión.</span><span class="sxs-lookup"><span data-stu-id="70730-143">The meeting dial-in numbers and the conference ID are automatically added to the meeting invitation that's sent to meeting attendees.</span></span> <span data-ttu-id="70730-144">Para obtener más información, vea [Programar una reunión Teams en Outlook](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f).</span><span class="sxs-lookup"><span data-stu-id="70730-144">To learn more, see [Schedule a Teams meeting in Outlook](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f).</span></span>

> [!NOTE]
> <span data-ttu-id="70730-145">Si lo desea, puede personalizar invitaciones a reuniones para agregar el logotipo de su empresa, vínculos a su sitio web de soporte técnico y declinación de responsabilidades legales y un pie de página de solo texto.</span><span class="sxs-lookup"><span data-stu-id="70730-145">If you want, you can customize meeting invitations to add your company logo, links to your support website and legal disclaimer, and a text-only footer.</span></span> <span data-ttu-id="70730-146">Para obtener más información, vea [Personalizar invitaciones a reuniones.](meeting-settings-in-teams.md#customize-meeting-invitations)</span><span class="sxs-lookup"><span data-stu-id="70730-146">To learn more, see [Customize meeting invitations](meeting-settings-in-teams.md#customize-meeting-invitations).</span></span>

## <a name="audio-conferencing-phone-numbers"></a><span data-ttu-id="70730-147">Números de teléfono de audioconferencia</span><span class="sxs-lookup"><span data-stu-id="70730-147">Audio Conferencing phone numbers</span></span>

<span data-ttu-id="70730-148">Hay dos tipos de números que puede usar para el puente de conferencias.</span><span class="sxs-lookup"><span data-stu-id="70730-148">There are two types of numbers that you can use for your conferencing bridge.</span></span> <span data-ttu-id="70730-149">Puede usar números **compartidos** (como en la sección Configurar audioconferencias anteriores en este artículo) o **números dedicados.** [](#set-up-audio-conferencing)</span><span class="sxs-lookup"><span data-stu-id="70730-149">You can use either **shared numbers** (as in the [Set up Audio Conferencing](#set-up-audio-conferencing) section earlier in this article) or **dedicated numbers**.</span></span> <span data-ttu-id="70730-150">Aquí encontrará más información sobre cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="70730-150">Here's more information about each.</span></span>

### <a name="shared-numbers"></a><span data-ttu-id="70730-151">Números compartidos</span><span class="sxs-lookup"><span data-stu-id="70730-151">Shared numbers</span></span>

<span data-ttu-id="70730-152">Un número compartido es un número que se comparte en todas las organizaciones.</span><span class="sxs-lookup"><span data-stu-id="70730-152">A shared number is a number that's shared across all organizations.</span></span> <span data-ttu-id="70730-153">Los números compartidos son números de pago y se asignan automáticamente al configurar las audioconferencias.</span><span class="sxs-lookup"><span data-stu-id="70730-153">Shared numbers are toll numbers and are automatically assigned when you set up Audio Conferencing.</span></span>

<span data-ttu-id="70730-154">Para ver el número predeterminado asignado al puente de conferencias, en el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Puentes** de conferencia de reuniones y, a continuación, busque el número de la ubicación más cercana a  >  usted.</span><span class="sxs-lookup"><span data-stu-id="70730-154">To see the default number that's assigned to your conferencing bridge, in the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Conference bridges**, and then find the number for the location that's nearest to you.</span></span>

### <a name="dedicated-numbers"></a><span data-ttu-id="70730-155">Números dedicados</span><span class="sxs-lookup"><span data-stu-id="70730-155">Dedicated numbers</span></span>

<span data-ttu-id="70730-156">Un número dedicado es un número que solo está disponible para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="70730-156">A dedicated number is a number that's available only to your users.</span></span> <span data-ttu-id="70730-157">Un número dedicado puede ser un número de pago o un número gratuito.</span><span class="sxs-lookup"><span data-stu-id="70730-157">A dedicated number can be a toll number or a toll-free number.</span></span> <span data-ttu-id="70730-158">Para usar un número dedicado, primero tendrá que obtener el número, asignarlo al puente de conferencias y, a continuación, asignar el número a cada persona que dirigirá las reuniones.</span><span class="sxs-lookup"><span data-stu-id="70730-158">To use a dedicated number, you'll have to first get the number, assign it to your conferencing bridge, and then assign the number to each person who will lead meetings.</span></span>

<span data-ttu-id="70730-159">Hay un par de formas de obtener un número dedicado.</span><span class="sxs-lookup"><span data-stu-id="70730-159">There are a couple ways to get a dedicated number.</span></span> <span data-ttu-id="70730-160">Puede obtener un número de Microsoft o transferir (puerto) un número existente de su proveedor de servicios actual a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="70730-160">You can get a number from Microsoft or transfer (port) an existing number from your current service provider to Microsoft.</span></span> <span data-ttu-id="70730-161">Para obtener más información sobre cómo hacerlo, vea [Obtener números de servicio.](getting-service-phone-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="70730-161">To learn more about how to do this, see [Getting service numbers](getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="70730-162">Tenga en cuenta que si usa un número gratuito, primero tiene que asignar una licencia de créditos de comunicaciones a cada persona que dirigirá las reuniones.</span><span class="sxs-lookup"><span data-stu-id="70730-162">Keep in mind that if you use a toll-free number, you have to first assign a Communications Credits license to each person who will lead meetings.</span></span> <span data-ttu-id="70730-163">Para obtener más información, vea [Configurar créditos de comunicaciones para su organización.](set-up-communications-credits-for-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="70730-163">To learn more, see [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>

<span data-ttu-id="70730-164">Después de tener su número, asígnelo al puente de conferencia.</span><span class="sxs-lookup"><span data-stu-id="70730-164">After you have your number, assign it to your conference bridge.</span></span> <span data-ttu-id="70730-165">Use el Microsoft Teams de administración para ello.</span><span class="sxs-lookup"><span data-stu-id="70730-165">Use the Microsoft Teams admin center to do this.</span></span>

1. <span data-ttu-id="70730-166">En el panel de navegación izquierdo del Microsoft Teams de administración, vaya a **Puentes de conferencia**  >  **reuniones.**</span><span class="sxs-lookup"><span data-stu-id="70730-166">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="70730-167">Seleccione **Agregar** y, a continuación, **seleccione Número de pago** o Número **gratuito.**</span><span class="sxs-lookup"><span data-stu-id="70730-167">Select **Add**, and then select **Toll number** or **Toll-free number**.</span></span>
3. <span data-ttu-id="70730-168">En el **panel Agregar número de** teléfono, seleccione el número y, a continuación, seleccione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="70730-168">In the **Add phone number** pane, select the number, and then select **Apply**.</span></span>

<span data-ttu-id="70730-169">A continuación, asigne el número a cada persona que dirigirá las reuniones.</span><span class="sxs-lookup"><span data-stu-id="70730-169">Then, assign the number to each person who will lead meetings.</span></span> <span data-ttu-id="70730-170">Use el Microsoft Teams de administración para ello.</span><span class="sxs-lookup"><span data-stu-id="70730-170">Use the Microsoft Teams admin center to do this.</span></span>

1. <span data-ttu-id="70730-171">En el panel de navegación izquierdo del Microsoft Teams de administración, seleccione **Usuarios,** haga clic en el nombre para mostrar del usuario y seleccione **Editar.**</span><span class="sxs-lookup"><span data-stu-id="70730-171">In the left navigation of the Microsoft Teams admin center, select **Users**, click the display name of the user, and select **Edit**.</span></span>
2. <span data-ttu-id="70730-172">Seleccione **Editar** junto a **Audioconferencia** y, a continuación, en el  panel  **Audioconferencia,** seleccione un número en las listas Número de pago o Número gratuito y, a continuación, seleccione **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="70730-172">Select **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, select a number in the **Toll number** or **Toll-free** number lists, and then select **Apply**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="70730-173">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="70730-173">Related topics</span></span>

- [<span data-ttu-id="70730-174">Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="70730-174">Audio Conferencing</span></span>](audio-conferencing-in-office-365.md)
- [<span data-ttu-id="70730-175">Configurar conferencias de audio para Teams</span><span class="sxs-lookup"><span data-stu-id="70730-175">Set up Audio Conferencing for Teams</span></span>](set-up-audio-conferencing-in-teams.md)
- [<span data-ttu-id="70730-176">Números de teléfono para Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="70730-176">Phone numbers for Audio Conferencing</span></span>](phone-numbers-for-audio-conferencing-in-teams.md)
- [<span data-ttu-id="70730-177">Preguntas frecuentes sobre Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="70730-177">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
- [<span data-ttu-id="70730-178">Obtener números de servicio</span><span class="sxs-lookup"><span data-stu-id="70730-178">Getting service numbers</span></span>](getting-service-phone-numbers.md)
- [<span data-ttu-id="70730-179">Teams de complementos</span><span class="sxs-lookup"><span data-stu-id="70730-179">Teams add-on licenses</span></span>](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="70730-180">Asignar licencias a usuarios</span><span class="sxs-lookup"><span data-stu-id="70730-180">Assign licenses to users</span></span>](/microsoft-365/admin/manage/assign-licenses-to-users)