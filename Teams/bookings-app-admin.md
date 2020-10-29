---
title: Visitas virtuales con Microsoft Teams y la aplicación de las reservas
author: msdmaguire
ms.author: dmaguire
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- microsoftcloud-healthcare
ms.reviewer: ''
description: Microsoft Teams y visitas virtuales con la aplicación bookings
ms.openlocfilehash: 684c442765b868ca96e9d1bf243817f9378f0b5d
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790622"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a><span data-ttu-id="286d0-103">Visitas virtuales con Microsoft Teams y la aplicación de las reservas</span><span class="sxs-lookup"><span data-stu-id="286d0-103">Virtual visits with Microsoft Teams and the Bookings app</span></span>

<span data-ttu-id="286d0-104">La aplicación de reservas de Microsoft Teams ofrece una forma sencilla de programar citas en persona y virtuales, como visitas de asistencia sanitaria, consultas financieras, entrevistas, asistencia al cliente, horas de oficina de educación y mucho más.</span><span class="sxs-lookup"><span data-stu-id="286d0-104">The Bookings app in Microsoft Teams offers a simple way to schedule in-person and virtual appointments, such as healthcare visits, financial consultations, interviews, customer support, education office hours, and much more.</span></span>

<span data-ttu-id="286d0-105">Los programadores pueden administrar varios calendarios de departamentos y personal, así como comunicaciones con asistentes internos y externos, desde una sola experiencia.</span><span class="sxs-lookup"><span data-stu-id="286d0-105">Schedulers can manage multiple department and staff calendars, as well as communications with internal and external attendees, from a single experience.</span></span> <span data-ttu-id="286d0-106">Las citas virtuales en sí se mantienen a través de las reuniones de Microsoft Teams, lo que ofrece sólidas capacidades de videoconferencia.</span><span class="sxs-lookup"><span data-stu-id="286d0-106">The virtual appointments themselves are held via Microsoft Teams Meetings, which offers robust videoconferencing capabilities.</span></span>

> [!NOTE]
> <span data-ttu-id="286d0-107">Solo los programadores necesitan tener la aplicación de las reservas instalada en Teams.</span><span class="sxs-lookup"><span data-stu-id="286d0-107">Only schedulers need to have the Bookings app installed in Teams.</span></span> <span data-ttu-id="286d0-108">El personal que lleva a cabo o participa en citas virtuales no necesita la aplicación.</span><span class="sxs-lookup"><span data-stu-id="286d0-108">Staff conducting or participating in virtual appointments do not need the app.</span></span> <span data-ttu-id="286d0-109">Simplemente pueden unirse a citas desde el calendario de Outlook o Teams o desde un vínculo en el correo electrónico de confirmación de reserva.</span><span class="sxs-lookup"><span data-stu-id="286d0-109">They can simply join appointments from their Outlook or Teams calendar or from a link in their booking confirmation email.</span></span>

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a><span data-ttu-id="286d0-110">Requisitos previos para usar la aplicación de reservas en Teams</span><span class="sxs-lookup"><span data-stu-id="286d0-110">Prerequisites for using the Bookings app in Teams</span></span>

- <span data-ttu-id="286d0-111">El buzón de Exchange debe estar en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="286d0-111">The Exchange mailbox must be in Exchange Online.</span></span> <span data-ttu-id="286d0-112">No se admiten los buzones de Exchange Server locales.</span><span class="sxs-lookup"><span data-stu-id="286d0-112">On-premises Exchange Server mailboxes are not supported.</span></span>

- <span data-ttu-id="286d0-113">Microsoft bookings debe estar activado para la organización.</span><span class="sxs-lookup"><span data-stu-id="286d0-113">Microsoft Bookings must be turned on for the organization.</span></span>

- <span data-ttu-id="286d0-114">Los usuarios deben tener una licencia adecuada.</span><span class="sxs-lookup"><span data-stu-id="286d0-114">Users must have an appropriate license.</span></span> <span data-ttu-id="286d0-115">Office 365 a3, A5, E3 y E5, así como Microsoft 365 Business Standard, a3, A5, E3 y E5.</span><span class="sxs-lookup"><span data-stu-id="286d0-115">Office 365 A3, A5, E3, and E5, as well as Microsoft 365 Business Standard, A3, A5, E3, and E5 are supported.</span></span>

- <span data-ttu-id="286d0-116">Todos los usuarios de la aplicación de reservas y todo el personal que participe en las reuniones deben tener una licencia que admita la programación de reuniones de equipos.</span><span class="sxs-lookup"><span data-stu-id="286d0-116">All users of the Bookings app and all staff participating in meetings must have a license that supports Teams Meeting scheduling.</span></span>

- <span data-ttu-id="286d0-117">Sus sistemas deben cumplir con todos los [requisitos previos de software y navegador](hardware-requirements-for-the-teams-app.md).</span><span class="sxs-lookup"><span data-stu-id="286d0-117">Your systems must meet all [Software and browser prerequisites](hardware-requirements-for-the-teams-app.md).</span></span>

## <a name="availability-of-bookings-in-teams"></a><span data-ttu-id="286d0-118">Disponibilidad de las reservas en Teams</span><span class="sxs-lookup"><span data-stu-id="286d0-118">Availability of Bookings in Teams</span></span>

<span data-ttu-id="286d0-119">La aplicación Microsoft bookings para Teams está disponible en el escritorio y en la Web.</span><span class="sxs-lookup"><span data-stu-id="286d0-119">Microsoft Bookings App for Teams is available on the desktop and web.</span></span> <span data-ttu-id="286d0-120">Puede encontrarla en [aplicaciones de Microsoft Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) y en **Administrar aplicaciones** dentro del centro de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="286d0-120">It can be found under [Apps within Microsoft Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) and under **Manage Apps** within Teams Admin Center.</span></span>

### <a name="control-access-to-bookings-within-your-organization"></a><span data-ttu-id="286d0-121">Controlar el acceso a las reservas de la organización</span><span class="sxs-lookup"><span data-stu-id="286d0-121">Control access to Bookings within your organization</span></span>

<span data-ttu-id="286d0-122">Hay varias maneras de controlar quién tiene acceso a la aplicación de las reservas y a características específicas de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="286d0-122">There are several ways to control who has access to the Bookings app and to specific features of the app.</span></span> <span data-ttu-id="286d0-123">Para obtener información sobre cómo activar o desactivar Microsoft Books en el centro de administración de Microsoft 365, así como la forma de crear una directiva de aplicación de reservas para permitir que los usuarios seleccionados creen calendarios de reservas, vea [obtener acceso a Microsoft bookings](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce).</span><span class="sxs-lookup"><span data-stu-id="286d0-123">To learn how to turn Microsoft Bookings on or off in the Microsoft 365 admin center, as well as how to create a Bookings app policy to allow selected users to create Bookings calendars, see [Get access to Microsoft Bookings](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce).</span></span> <span data-ttu-id="286d0-124">También puede obtener información sobre cómo [crear una directiva de la aplicación de Teams para anclar la aplicación de las reservas a los usuarios seleccionados](teams-app-setup-policies.md).</span><span class="sxs-lookup"><span data-stu-id="286d0-124">You can also learn how to [Create a Teams app policy to pin the Bookings app for select users](teams-app-setup-policies.md).</span></span>

## <a name="recommended-meeting-policy-settings"></a><span data-ttu-id="286d0-125">Configuración de directiva de reunión recomendada</span><span class="sxs-lookup"><span data-stu-id="286d0-125">Recommended Meeting Policy Settings</span></span>

<span data-ttu-id="286d0-126">Para habilitar la mejor experiencia para las reservas, cree una directiva de reunión de personal para admitir automáticamente a **todos los usuarios de su organización** .</span><span class="sxs-lookup"><span data-stu-id="286d0-126">To enable the best experience for Bookings, create a staff meeting policy to automatically admit **Everyone in your organization** .</span></span> <span data-ttu-id="286d0-127">Esto permitirá al personal unirse a la cita automáticamente y habilitar la experiencia de la sala de espera para los asistentes externos.</span><span class="sxs-lookup"><span data-stu-id="286d0-127">This will allow staff to join the appointment automatically and enable lobby experience for external attendees.</span></span> <span data-ttu-id="286d0-128">Puede obtener más información sobre la [admisión automática de personas a las reuniones](meeting-policies-in-teams.md#automatically-admit-people).</span><span class="sxs-lookup"><span data-stu-id="286d0-128">You can learn more about [automatically admitting people to meetings](meeting-policies-in-teams.md#automatically-admit-people).</span></span>

### <a name="optional-staff-approvals-setting"></a><span data-ttu-id="286d0-129">Configuración opcional de aprobaciones de personal</span><span class="sxs-lookup"><span data-stu-id="286d0-129">Optional staff approvals setting</span></span>

<span data-ttu-id="286d0-130">Como configuración de privacidad adicional, puede decidir requerir que el personal participe antes de que la información de disponibilidad de programación se comparta con las reservas y antes de que se pueda reservar para una cita.</span><span class="sxs-lookup"><span data-stu-id="286d0-130">As an extra privacy setting, you can choose to require staff to opt in before their schedule availability information is shared through Bookings and before they can be booked for an appointment.</span></span>  

<span data-ttu-id="286d0-131">Para habilitar esta configuración, vaya a configuración del **centro de administración de Microsoft 365** \> **Settings** \> **Settings** y seleccione **reservas** .</span><span class="sxs-lookup"><span data-stu-id="286d0-131">To enable this setting, go to **Microsoft 365 admin center** \> **Settings** \> **Settings** , then select **Bookings** .</span></span>

<span data-ttu-id="286d0-132">Con esta configuración activada, el personal recibirá un mensaje de correo electrónico en el que se le solicitará que apruebe la pertenencia a un calendario de reserva.</span><span class="sxs-lookup"><span data-stu-id="286d0-132">With this setting turned on, staff will receive an email in which they are asked to approve membership to a booking calendar.</span></span>  

<span data-ttu-id="286d0-133">Esta característica se está implementando gradualmente en todo el mundo para los clientes de Microsoft 365 y Office 365.</span><span class="sxs-lookup"><span data-stu-id="286d0-133">This feature is gradually being rolled out worldwide to Microsoft 365 and Office 365 customers.</span></span> <span data-ttu-id="286d0-134">Si todas las opciones aún no están disponibles en su entorno, vuelva a consultar pronto.</span><span class="sxs-lookup"><span data-stu-id="286d0-134">If all options are not yet available in your environment, check back soon.</span></span>

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a><span data-ttu-id="286d0-135">Cambiar el dominio predeterminado al configurar los buzones de las reservas</span><span class="sxs-lookup"><span data-stu-id="286d0-135">Changing your default domain when setting up Bookings mailboxes</span></span>

<span data-ttu-id="286d0-136">Al configurar un buzón de reservas, se usa el dominio de correo electrónico predeterminado de su organización de Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="286d0-136">When setting up a Bookings mailbox, the default email domain of your Microsoft 365 or Office 365 organization is used.</span></span> <span data-ttu-id="286d0-137">Sin embargo, esto puede causar problemas al enviar invitaciones a reuniones a destinatarios externos; es posible que su invitación se marque como correo no deseado y se mueva a la carpeta de correo no deseado del destinatario, de modo que el destinatario nunca verá su invitación.</span><span class="sxs-lookup"><span data-stu-id="286d0-137">However, this can cause problems when sending meeting invites to external recipients; your invite might be flagged as spam and moved to the recipient’s junk folder, so the recipient might never see your invite.</span></span>

<span data-ttu-id="286d0-138">Le recomendamos que cambie el dominio predeterminado antes de crear el buzón de las reservas.</span><span class="sxs-lookup"><span data-stu-id="286d0-138">We recommend that you change the default domain prior to creating your Bookings mailbox.</span></span> <span data-ttu-id="286d0-139">Para obtener más información sobre cómo hacerlo, consulte las [preguntas más frecuentes](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365)sobre los dominios.</span><span class="sxs-lookup"><span data-stu-id="286d0-139">For information on how to do this, see the [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).</span></span>

<span data-ttu-id="286d0-140">Si necesita cambiar el dominio predeterminado una vez que ya se ha creado el buzón de las reservas, puede hacerlo con PowerShell:</span><span class="sxs-lookup"><span data-stu-id="286d0-140">If you need to change the default domain after your Bookings mailbox has already been created, you can do so with PowerShell:</span></span>

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

<span data-ttu-id="286d0-141">Para obtener más información, consulte la documentación de PowerShell para el cmdlet [set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) .</span><span class="sxs-lookup"><span data-stu-id="286d0-141">For more information, see the PowerShell documentation for the [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="286d0-142">Si usa una configuración híbrida de Exchange, le recomendamos que pruebe minuciosamente el flujo de correo entre Exchange local y Exchange Online al cambiar el dominio predeterminado.</span><span class="sxs-lookup"><span data-stu-id="286d0-142">If you are using an Exchange hybrid configuration, we recommend that you thoroughly test mail flow between on-premises Exchange and Exchange Online when changing the default domain.</span></span>

## <a name="sending-feedback"></a><span data-ttu-id="286d0-143">Enviar comentarios</span><span class="sxs-lookup"><span data-stu-id="286d0-143">Sending feedback</span></span>

<span data-ttu-id="286d0-144">Le agradecemos sus comentarios sobre:</span><span class="sxs-lookup"><span data-stu-id="286d0-144">We welcome your feedback on:</span></span>

  - <span data-ttu-id="286d0-145">Experiencia del usuario o facilidad de uso</span><span class="sxs-lookup"><span data-stu-id="286d0-145">User experience or ease of use</span></span>
  - <span data-ttu-id="286d0-146">Brechas de características o funcionalidad perdida</span><span class="sxs-lookup"><span data-stu-id="286d0-146">Feature gaps or missing functionality</span></span>
  - <span data-ttu-id="286d0-147">Errores o problemas</span><span class="sxs-lookup"><span data-stu-id="286d0-147">Bugs or issues</span></span>
  
<span data-ttu-id="286d0-148">Para enviar comentarios, haga clic en el botón **ayuda** situado cerca de la parte inferior de la barra de navegación izquierda de Teams y, a continuación, haga clic en **informar de un problema** para **todos los** problemas.</span><span class="sxs-lookup"><span data-stu-id="286d0-148">To send feedback, click the **Help** button near the bottom of the Teams left navigation bar, then click **Report a Problem** for **ALL** issues.</span></span> <span data-ttu-id="286d0-149">Nota al principio de su informe de comentarios le enviamos comentarios sobre "reservas" para que podamos identificar fácilmente los problemas relacionados con las reservas.</span><span class="sxs-lookup"><span data-stu-id="286d0-149">Please note at the beginning of your feedback report that you are sending feedback about "Bookings" so we can easily identify Bookings issues.</span></span>

## <a name="related-topics"></a><span data-ttu-id="286d0-150">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="286d0-150">Related topics</span></span>

[<span data-ttu-id="286d0-151">Documentación de las reservas para usuarios finales</span><span class="sxs-lookup"><span data-stu-id="286d0-151">Bookings documentation for end users</span></span>](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
