---
title: Visitas virtuales con Microsoft Teams y la aplicación Bookings
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
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: ''
description: Microsoft Teams y visitas virtuales con la aplicación Bookings
ms.openlocfilehash: 582c59b4c389d687c529a7db9d9f1825d488f9f3
ms.sourcegitcommit: 1b11a2b74b8db6ed9e5da9b04cf3ed9c02a1d892
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "50125753"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a><span data-ttu-id="ed12e-103">Visitas virtuales con Microsoft Teams y la aplicación Bookings</span><span class="sxs-lookup"><span data-stu-id="ed12e-103">Virtual visits with Microsoft Teams and the Bookings app</span></span>

<span data-ttu-id="ed12e-104">La aplicación Bookings de Microsoft Teams ofrece una forma sencilla de programar citas en persona y virtuales, como visitas médicas, consultas financieras, entrevistas, soporte al cliente, horarios de oficina para educación y mucho más.</span><span class="sxs-lookup"><span data-stu-id="ed12e-104">The Bookings app in Microsoft Teams offers a simple way to schedule in-person and virtual appointments, such as healthcare visits, financial consultations, interviews, customer support, education office hours, and much more.</span></span>

<span data-ttu-id="ed12e-105">Los programadores pueden administrar calendarios de varios departamentos y de personal, así como las comunicaciones con asistentes internos y externos, desde una única experiencia.</span><span class="sxs-lookup"><span data-stu-id="ed12e-105">Schedulers can manage multiple department and staff calendars, as well as communications with internal and external attendees, from a single experience.</span></span> <span data-ttu-id="ed12e-106">Las propias citas virtuales se mantienen a través de reuniones de Microsoft Teams, que ofrece sólidas capacidades de videoconferencia.</span><span class="sxs-lookup"><span data-stu-id="ed12e-106">The virtual appointments themselves are held via Microsoft Teams Meetings, which offers robust videoconferencing capabilities.</span></span>

> [!NOTE]
> <span data-ttu-id="ed12e-107">Solo los programadores deben tener la aplicación Bookings instalada en Teams.</span><span class="sxs-lookup"><span data-stu-id="ed12e-107">Only schedulers need to have the Bookings app installed in Teams.</span></span> <span data-ttu-id="ed12e-108">El personal que dirige o participa en citas virtuales no necesita la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ed12e-108">Staff conducting or participating in virtual appointments do not need the app.</span></span> <span data-ttu-id="ed12e-109">Simplemente pueden unirse a citas desde su calendario de Outlook o Teams o desde un vínculo en el correo electrónico de confirmación de reserva.</span><span class="sxs-lookup"><span data-stu-id="ed12e-109">They can simply join appointments from their Outlook or Teams calendar or from a link in their booking confirmation email.</span></span>

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a><span data-ttu-id="ed12e-110">Requisitos previos para usar la aplicación Bookings en Teams</span><span class="sxs-lookup"><span data-stu-id="ed12e-110">Prerequisites for using the Bookings app in Teams</span></span>

- <span data-ttu-id="ed12e-111">El buzón de Exchange debe estar en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ed12e-111">The Exchange mailbox must be in Exchange Online.</span></span> <span data-ttu-id="ed12e-112">Los buzones de correo Exchange Server local no son compatibles.</span><span class="sxs-lookup"><span data-stu-id="ed12e-112">On-premises Exchange Server mailboxes are not supported.</span></span>

- <span data-ttu-id="ed12e-113">Microsoft Bookings debe estar activado para la organización.</span><span class="sxs-lookup"><span data-stu-id="ed12e-113">Microsoft Bookings must be turned on for the organization.</span></span>

- <span data-ttu-id="ed12e-114">Los usuarios deben tener una licencia apropiada.</span><span class="sxs-lookup"><span data-stu-id="ed12e-114">Users must have an appropriate license.</span></span> <span data-ttu-id="ed12e-115">Office 365 A3, A5, E3 y E5, así como Microsoft 365 Empresa Estándar, A3, A5, E3 y E5 son compatibles.</span><span class="sxs-lookup"><span data-stu-id="ed12e-115">Office 365 A3, A5, E3, and E5, as well as Microsoft 365 Business Standard, A3, A5, E3, and E5 are supported.</span></span>

- <span data-ttu-id="ed12e-116">Todos los usuarios de la aplicación Bookings y todos los miembros del personal que participen en las reuniones deben tener una licencia compatible con la programación de reuniones de Teams.</span><span class="sxs-lookup"><span data-stu-id="ed12e-116">All users of the Bookings app and all staff participating in meetings must have a license that supports Teams Meeting scheduling.</span></span>

- <span data-ttu-id="ed12e-117">Los sistemas deben cumplir todos los requisitos [previos del software y del explorador.](hardware-requirements-for-the-teams-app.md)</span><span class="sxs-lookup"><span data-stu-id="ed12e-117">Your systems must meet all [Software and browser prerequisites](hardware-requirements-for-the-teams-app.md).</span></span>

## <a name="availability-of-bookings-in-teams"></a><span data-ttu-id="ed12e-118">Disponibilidad de Bookings en Teams</span><span class="sxs-lookup"><span data-stu-id="ed12e-118">Availability of Bookings in Teams</span></span>

<span data-ttu-id="ed12e-119">La aplicación de Microsoft Bookings para Teams está disponible en el escritorio y en la web.</span><span class="sxs-lookup"><span data-stu-id="ed12e-119">Microsoft Bookings App for Teams is available on the desktop and web.</span></span> <span data-ttu-id="ed12e-120">Puede encontrarse en Aplicaciones de [Microsoft Teams y](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) en Administrar aplicaciones **en** el Centro de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="ed12e-120">It can be found under [Apps within Microsoft Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) and under **Manage Apps** within Teams Admin Center.</span></span>

### <a name="control-access-to-bookings-within-your-organization"></a><span data-ttu-id="ed12e-121">Controlar el acceso a Bookings dentro de su organización</span><span class="sxs-lookup"><span data-stu-id="ed12e-121">Control access to Bookings within your organization</span></span>

<span data-ttu-id="ed12e-122">Hay varias formas de controlar quién tiene acceso a la aplicación de Bookings y a características específicas de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ed12e-122">There are several ways to control who has access to the Bookings app and to specific features of the app.</span></span> <span data-ttu-id="ed12e-123">Para obtener información sobre cómo activar o desactivar Microsoft Bookings en el Centro de administración de Microsoft 365, así como cómo crear una directiva de aplicación de Bookings para permitir a los usuarios seleccionados crear calendarios de Bookings, vea Obtener acceso a [Microsoft Bookings.](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce)</span><span class="sxs-lookup"><span data-stu-id="ed12e-123">To learn how to turn Microsoft Bookings on or off in the Microsoft 365 admin center, as well as how to create a Bookings app policy to allow selected users to create Bookings calendars, see [Get access to Microsoft Bookings](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce).</span></span> <span data-ttu-id="ed12e-124">También puede aprender a crear una [directiva de aplicación de Teams para anclar la aplicación Bookings para usuarios seleccionados.](teams-app-setup-policies.md)</span><span class="sxs-lookup"><span data-stu-id="ed12e-124">You can also learn how to [Create a Teams app policy to pin the Bookings app for select users](teams-app-setup-policies.md).</span></span>

## <a name="recommended-meeting-policy-settings"></a><span data-ttu-id="ed12e-125">Configuración de directiva de reunión recomendada</span><span class="sxs-lookup"><span data-stu-id="ed12e-125">Recommended Meeting Policy Settings</span></span>

<span data-ttu-id="ed12e-126">Para habilitar la mejor experiencia para Bookings, cree una directiva de reunión de personal para admitir automáticamente a **todos los usuarios de su organización.**</span><span class="sxs-lookup"><span data-stu-id="ed12e-126">To enable the best experience for Bookings, create a staff meeting policy to automatically admit **Everyone in your organization**.</span></span> <span data-ttu-id="ed12e-127">Esto permitirá al personal unirse a la cita automáticamente y habilitar la experiencia de sala de espera para los asistentes externos.</span><span class="sxs-lookup"><span data-stu-id="ed12e-127">This will allow staff to join the appointment automatically and enable lobby experience for external attendees.</span></span> <span data-ttu-id="ed12e-128">Puede obtener más información sobre [cómo admitir automáticamente a las personas a las reuniones.](meeting-policies-in-teams.md#automatically-admit-people)</span><span class="sxs-lookup"><span data-stu-id="ed12e-128">You can learn more about [automatically admitting people to meetings](meeting-policies-in-teams.md#automatically-admit-people).</span></span>

### <a name="optional-staff-approvals-setting"></a><span data-ttu-id="ed12e-129">Configuración opcional de aprobaciones de personal</span><span class="sxs-lookup"><span data-stu-id="ed12e-129">Optional staff approvals setting</span></span>

<span data-ttu-id="ed12e-130">Como configuración de privacidad adicional, puede optar por requerir que el personal opte por participar antes de compartir la información de disponibilidad de su programación a través de Bookings y antes de que se puedan reservar para una cita.</span><span class="sxs-lookup"><span data-stu-id="ed12e-130">As an extra privacy setting, you can choose to require staff to opt in before their schedule availability information is shared through Bookings and before they can be booked for an appointment.</span></span>  

<span data-ttu-id="ed12e-131">Para habilitar esta configuración, vaya a Configuración del centro de administración de **Microsoft 365** \>  \> y seleccione **Bookings.**</span><span class="sxs-lookup"><span data-stu-id="ed12e-131">To enable this setting, go to **Microsoft 365 admin center** \> **Settings** \> **Settings**, then select **Bookings**.</span></span>

<span data-ttu-id="ed12e-132">Con esta configuración activada, el personal recibirá un correo electrónico en el que se le pedirá que aprueben la pertenencia como miembro a un calendario de reservas.</span><span class="sxs-lookup"><span data-stu-id="ed12e-132">With this setting turned on, staff will receive an email in which they are asked to approve membership to a booking calendar.</span></span>  

<span data-ttu-id="ed12e-133">Esta característica se está implantando gradualmente en todo el mundo para los clientes de Microsoft 365 y Office 365.</span><span class="sxs-lookup"><span data-stu-id="ed12e-133">This feature is gradually being rolled out worldwide to Microsoft 365 and Office 365 customers.</span></span> <span data-ttu-id="ed12e-134">Si todas las opciones aún no están disponibles en su entorno, vuelva a comprobarlo pronto.</span><span class="sxs-lookup"><span data-stu-id="ed12e-134">If all options are not yet available in your environment, check back soon.</span></span>

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a><span data-ttu-id="ed12e-135">Cambiar el dominio predeterminado al configurar buzones de Bookings</span><span class="sxs-lookup"><span data-stu-id="ed12e-135">Changing your default domain when setting up Bookings mailboxes</span></span>

<span data-ttu-id="ed12e-136">Al configurar un buzón de Bookings, se usa el dominio de correo electrónico predeterminado de su organización de Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="ed12e-136">When setting up a Bookings mailbox, the default email domain of your Microsoft 365 or Office 365 organization is used.</span></span> <span data-ttu-id="ed12e-137">Sin embargo, esto puede provocar problemas al enviar invitaciones a reuniones a destinatarios externos; Es posible que su invitación se haya marcado como correo no deseado y se haya movido a la carpeta de correo no deseado del destinatario, por lo que es posible que nunca vea la invitación.</span><span class="sxs-lookup"><span data-stu-id="ed12e-137">However, this can cause problems when sending meeting invites to external recipients; your invite might be flagged as spam and moved to the recipient’s junk folder, so the recipient might never see your invite.</span></span>

<span data-ttu-id="ed12e-138">Le recomendamos que cambie el dominio predeterminado antes de crear el buzón de Bookings.</span><span class="sxs-lookup"><span data-stu-id="ed12e-138">We recommend that you change the default domain prior to creating your Bookings mailbox.</span></span> <span data-ttu-id="ed12e-139">Para obtener información sobre cómo hacerlo, consulte Preguntas más frecuentes [sobre dominios.](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="ed12e-139">For information on how to do this, see the [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).</span></span>

<span data-ttu-id="ed12e-140">Si necesita cambiar el dominio predeterminado después de que su buzón de Bookings ya se haya creado, puede hacerlo con PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ed12e-140">If you need to change the default domain after your Bookings mailbox has already been created, you can do so with PowerShell:</span></span>

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

<span data-ttu-id="ed12e-141">Para obtener más información, consulte la documentación de PowerShell para el cmdlet [Set-Mailbox.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)</span><span class="sxs-lookup"><span data-stu-id="ed12e-141">For more information, see the PowerShell documentation for the [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="ed12e-142">Si usa una configuración híbrida de Exchange, le recomendamos que pruebe a fondo el flujo de correo entre exchange local y Exchange Online al cambiar el dominio predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ed12e-142">If you are using an Exchange hybrid configuration, we recommend that you thoroughly test mail flow between on-premises Exchange and Exchange Online when changing the default domain.</span></span>

## <a name="sending-feedback"></a><span data-ttu-id="ed12e-143">Enviar comentarios</span><span class="sxs-lookup"><span data-stu-id="ed12e-143">Sending feedback</span></span>

<span data-ttu-id="ed12e-144">Agradecemos sus comentarios sobre:</span><span class="sxs-lookup"><span data-stu-id="ed12e-144">We welcome your feedback on:</span></span>

  - <span data-ttu-id="ed12e-145">Experiencia de usuario o facilidad de uso</span><span class="sxs-lookup"><span data-stu-id="ed12e-145">User experience or ease of use</span></span>
  - <span data-ttu-id="ed12e-146">Funcionalidad que falta o falta de funcionalidad</span><span class="sxs-lookup"><span data-stu-id="ed12e-146">Feature gaps or missing functionality</span></span>
  - <span data-ttu-id="ed12e-147">Errores o problemas</span><span class="sxs-lookup"><span data-stu-id="ed12e-147">Bugs or issues</span></span>
  
<span data-ttu-id="ed12e-148">Para enviar comentarios,  haga clic en el botón Ayuda cerca de la parte inferior de la barra de navegación izquierda de Teams y, **a** continuación, haga clic en Informar de un problema **para TODOS los** problemas.</span><span class="sxs-lookup"><span data-stu-id="ed12e-148">To send feedback, click the **Help** button near the bottom of the Teams left navigation bar, then click **Report a Problem** for **ALL** issues.</span></span> <span data-ttu-id="ed12e-149">Al principio de su informe de comentarios, tenga en cuenta que va a enviar comentarios sobre "Bookings" para que podamos identificar fácilmente los problemas de Bookings.</span><span class="sxs-lookup"><span data-stu-id="ed12e-149">Please note at the beginning of your feedback report that you are sending feedback about "Bookings" so we can easily identify Bookings issues.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ed12e-150">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ed12e-150">Related topics</span></span>

[<span data-ttu-id="ed12e-151">Documentación de Bookings para usuarios finales</span><span class="sxs-lookup"><span data-stu-id="ed12e-151">Bookings documentation for end users</span></span>](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
