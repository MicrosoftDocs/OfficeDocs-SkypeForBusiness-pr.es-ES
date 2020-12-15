---
title: Disponibilidad de la aplicación de aprobaciones en Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aravin
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Obtenga más información sobre la disponibilidad de la aplicación aprobaciones en Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4326408b7e27aa19af8e6c404d7275d26ba90969
ms.sourcegitcommit: d73d732591944b899a9366f79b4ea97f4a7f2260
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2020
ms.locfileid: "49675198"
---
# <a name="teams-approvals-app-availability"></a><span data-ttu-id="6dd9f-103">Disponibilidad de la aplicación de aprobaciones de Teams</span><span class="sxs-lookup"><span data-stu-id="6dd9f-103">Teams Approvals app availability</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="6dd9f-104">La aplicación aprobaciones está disponible como una aplicación personal para todos los usuarios de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6dd9f-104">The Approvals app is available as a personal app for all Microsoft Teams users.</span></span>
<span data-ttu-id="6dd9f-105">La aplicación aprobaciones ofrece una manera sencilla de realizar auditorías, cumplimiento, responsabilidad y flujos de trabajo tanto de aprobaciones estructuradas como sin estructurar en Teams.</span><span class="sxs-lookup"><span data-stu-id="6dd9f-105">The Approvals app provides a simple way to bring auditing, compliance, accountability, and workflows to both structured and unstructured Approvals in Teams.</span></span>

 ![muestra la aplicación aprobaciones](media/approvals-selection.png)

<span data-ttu-id="6dd9f-107">Los usuarios pueden anclar la aplicación aprobaciones para guardarla en la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="6dd9f-107">Users can pin the Approvals app to save it to the menu bar.</span></span>

 ![muestra la aplicación aprobaciones con la opción PIN](media/approvalApp-pin.png)

<span data-ttu-id="6dd9f-109">La primera aprobación creada desde la aplicación aprobaciones desencadenará el aprovisionamiento de la solución de aprobación en el entorno predeterminado de Common Data Service (CD).</span><span class="sxs-lookup"><span data-stu-id="6dd9f-109">The first approval created from the Approvals app will trigger the provisioning of the Approval Solution in the default Common Data Service (CDS) environment.</span></span> <span data-ttu-id="6dd9f-110">Las aprobaciones creadas desde la aplicación aprobaciones se almacenarán en el entorno de CDS predeterminado.</span><span class="sxs-lookup"><span data-stu-id="6dd9f-110">Approvals created from the Approvals app will be stored in the default CDS environment.</span></span>

<span data-ttu-id="6dd9f-111">En este artículo se describen los requisitos y los roles de la aplicación aprobaciones.</span><span class="sxs-lookup"><span data-stu-id="6dd9f-111">This article describes the Approvals app requirements and roles.</span></span>

## <a name="required-permissions-and-licenses"></a><span data-ttu-id="6dd9f-112">Permisos y licencias necesarios</span><span class="sxs-lookup"><span data-stu-id="6dd9f-112">Required permissions and licenses</span></span>

<span data-ttu-id="6dd9f-113">Para usar la aplicación aprobaciones, necesita permiso para los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="6dd9f-113">To use the Approvals app, you need permission for the following items:</span></span>

- <span data-ttu-id="6dd9f-114">Permisos para crear una base de datos de Microsoft CD.</span><span class="sxs-lookup"><span data-stu-id="6dd9f-114">Permissions to create a Microsoft CDS database.</span></span>

- <span data-ttu-id="6dd9f-115">Una cuenta en [Flow.Microsoft.com](https://flow.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="6dd9f-115">An account on [flow.microsoft.com](https://flow.microsoft.com/)</span></span>

- <span data-ttu-id="6dd9f-116">Rol de administrador en el entorno de destino.</span><span class="sxs-lookup"><span data-stu-id="6dd9f-116">Administrator Role in the target environment.</span></span>

- <span data-ttu-id="6dd9f-117">Licencia para una [automatización de potencia](https://docs.microsoft.com/power-automate/get-started-approvals), un Office 365 o un Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="6dd9f-117">License for a [Power Automate](https://docs.microsoft.com/power-automate/get-started-approvals), an Office 365, or a Dynamics 365.</span></span>

## <a name="storage-with-cds"></a><span data-ttu-id="6dd9f-118">Almacenamiento con CD</span><span class="sxs-lookup"><span data-stu-id="6dd9f-118">Storage with CDS</span></span>

<span data-ttu-id="6dd9f-119">El modelo de datos común (CDM) es el idioma de datos compartidos que usan las aplicaciones empresariales y analíticas en los CD.</span><span class="sxs-lookup"><span data-stu-id="6dd9f-119">The Common Data Model (CDM) is the shared data language used by business and analytical applications in the CDS.</span></span> <span data-ttu-id="6dd9f-120">Consta de un conjunto de esquemas de datos estandarizados y extensibles publicados por Microsoft y nuestros socios que permiten la coherencia de los datos y su significado entre las aplicaciones y los procesos empresariales.</span><span class="sxs-lookup"><span data-stu-id="6dd9f-120">It consists of a set of a standardized, extensible data schemas published by Microsoft and our partners that enables consistency of data and its meaning across applications and business processes.</span></span> <span data-ttu-id="6dd9f-121">Obtenga más información sobre el [modelo de datos común de la plataforma Power de Microsoft](https://docs.microsoft.com/power-automate/get-started-approvals).</span><span class="sxs-lookup"><span data-stu-id="6dd9f-121">Learn more about the [Common Data Model of the Microsoft Power Platform](https://docs.microsoft.com/power-automate/get-started-approvals).</span></span>

<span data-ttu-id="6dd9f-122">Obtenga más información sobre el [flujo de trabajo de aprobación](https://docs.microsoft.com/power-automate/modern-approvals).</span><span class="sxs-lookup"><span data-stu-id="6dd9f-122">Learn more about the [Approval workflow](https://docs.microsoft.com/power-automate/modern-approvals).</span></span>

## <a name="approvals-teams-app-permissions"></a><span data-ttu-id="6dd9f-123">Permisos de la aplicación Teams de aprobaciones</span><span class="sxs-lookup"><span data-stu-id="6dd9f-123">Approvals Teams app permissions</span></span>

<span data-ttu-id="6dd9f-124">La aplicación equipos de aprobaciones le permite acceder a las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="6dd9f-124">The Approvals Teams app lets you access the following features:</span></span>

- <span data-ttu-id="6dd9f-125">Reciba los mensajes y los datos que le proporcione.</span><span class="sxs-lookup"><span data-stu-id="6dd9f-125">Receive messages and data that you provide to it.</span></span>

- <span data-ttu-id="6dd9f-126">Envíale mensajes y notificaciones.</span><span class="sxs-lookup"><span data-stu-id="6dd9f-126">Send you messages and notifications.</span></span>

- <span data-ttu-id="6dd9f-127">Representar cuadros de diálogo y aplicaciones personales sin un encabezado proporcionado por Teams.</span><span class="sxs-lookup"><span data-stu-id="6dd9f-127">Render personal apps and dialogs without a Teams-provided header.</span></span>

- <span data-ttu-id="6dd9f-128">Obtenga acceso a la información de su perfil, como el nombre, la dirección de correo electrónico, el nombre de la empresa y el idioma preferido.</span><span class="sxs-lookup"><span data-stu-id="6dd9f-128">Access your profile information such as your name, email address, company name, and preferred language.</span></span>

- <span data-ttu-id="6dd9f-129">Recibir mensajes y datos que los miembros del equipo proporcionan a él en un canal.</span><span class="sxs-lookup"><span data-stu-id="6dd9f-129">Receive messages and data that team members provide to it in a channel.</span></span>

- <span data-ttu-id="6dd9f-130">Enviar mensajes y notificaciones en un canal.</span><span class="sxs-lookup"><span data-stu-id="6dd9f-130">Send messages and notifications in a channel.</span></span>

- <span data-ttu-id="6dd9f-131">Obtener acceso a la información de su equipo:</span><span class="sxs-lookup"><span data-stu-id="6dd9f-131">Access your team's information:</span></span>
  - <span data-ttu-id="6dd9f-132">nombre del equipo</span><span class="sxs-lookup"><span data-stu-id="6dd9f-132">team name</span></span>
  - <span data-ttu-id="6dd9f-133">lista de canales</span><span class="sxs-lookup"><span data-stu-id="6dd9f-133">channel list</span></span>
  - <span data-ttu-id="6dd9f-134">lista (nombres de los miembros del equipo y direcciones de correo electrónico).</span><span class="sxs-lookup"><span data-stu-id="6dd9f-134">roster (team member's names and email addresses).</span></span>

- <span data-ttu-id="6dd9f-135">Use la información del equipo para ponerse en contacto con él.</span><span class="sxs-lookup"><span data-stu-id="6dd9f-135">Use the team's information to contact them.</span></span>

## <a name="disable-the-approvals-app"></a><span data-ttu-id="6dd9f-136">Deshabilitar la aplicación aprobaciones</span><span class="sxs-lookup"><span data-stu-id="6dd9f-136">Disable the Approvals app</span></span>

<span data-ttu-id="6dd9f-137">La aplicación aprobaciones está disponible de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="6dd9f-137">The Approvals app is available by default.</span></span> <span data-ttu-id="6dd9f-138">Puede deshabilitar la aplicación en el centro de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="6dd9f-138">You can disable the app in the Teams admin center.</span></span>

  1. <span data-ttu-id="6dd9f-139">Inicie sesión en el centro de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="6dd9f-139">Sign in to the Teams admin center.</span></span>

  2. <span data-ttu-id="6dd9f-140">Expanda **aplicaciones de Teams** y seleccione **Administrar aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="6dd9f-140">Expand **Teams apps** and select **Manage apps**.</span></span>

  3. <span data-ttu-id="6dd9f-141">Busque la aplicación aprobaciones.</span><span class="sxs-lookup"><span data-stu-id="6dd9f-141">Search for the Approvals app.</span></span>

![muestra la navegación del centro de administración con aplicaciones de Teams > administrar aplicaciones resaltadas](media/manage-approval-apps.png)

  4. <span data-ttu-id="6dd9f-143">Seleccione aprobaciones.</span><span class="sxs-lookup"><span data-stu-id="6dd9f-143">Select Approvals.</span></span>

  5. <span data-ttu-id="6dd9f-144">Seleccione el botón de alternancia para deshabilitar la aplicación de su organización.</span><span class="sxs-lookup"><span data-stu-id="6dd9f-144">Select the toggle to disable the app for your organization.</span></span>

![muestra los detalles de la aplicación aprobaciones](media/approvals-details.png)

## <a name="retention-policy"></a><span data-ttu-id="6dd9f-146">Directiva de retención</span><span class="sxs-lookup"><span data-stu-id="6dd9f-146">Retention policy</span></span>

<span data-ttu-id="6dd9f-147">Las aprobaciones creadas desde la aplicación aprobaciones se almacenan en el entorno de CDS predeterminado, que no es compatible con las copias de seguridad en este momento.</span><span class="sxs-lookup"><span data-stu-id="6dd9f-147">Approvals created from the Approvals App are stored in the default CDS environment, which doesn’t support backups at this time.</span></span> <span data-ttu-id="6dd9f-148">Más información sobre cómo [realizar copias de seguridad y restaurar entornos: Power Platform de \| Microsoft docs](https://docs.microsoft.com/power-platform/admin/backup-restore-environments).</span><span class="sxs-lookup"><span data-stu-id="6dd9f-148">Learn more about how to [Back up and restore environments - Power Platform \| Microsoft Docs](https://docs.microsoft.com/power-platform/admin/backup-restore-environments).</span></span>

## <a name="auditing"></a><span data-ttu-id="6dd9f-149">Auditoría</span><span class="sxs-lookup"><span data-stu-id="6dd9f-149">Auditing</span></span>

<span data-ttu-id="6dd9f-150">La aplicación aprobaciones registra los eventos de auditoría en el centro de seguridad y cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6dd9f-150">The Approvals App logs audit events within the Microsoft 365 Security and Compliance Center.</span></span> <span data-ttu-id="6dd9f-151">Puede ver el registro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="6dd9f-151">You can view the audit log.</span></span>

1. <span data-ttu-id="6dd9f-152">Vaya al sitio de cumplimiento de M365.</span><span class="sxs-lookup"><span data-stu-id="6dd9f-152">Go to the M365 Compliance Site.</span></span>

2. <span data-ttu-id="6dd9f-153">Seleccione la sección **Auditoría** .</span><span class="sxs-lookup"><span data-stu-id="6dd9f-153">Select the **Audit** section.</span></span>

3. <span data-ttu-id="6dd9f-154">Buscar actividades en **actividades de aprobaciones de Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="6dd9f-154">Search for activities under **Microsoft Teams approvals activities**.</span></span>

<span data-ttu-id="6dd9f-155">Puede buscar las actividades siguientes:</span><span class="sxs-lookup"><span data-stu-id="6dd9f-155">You can search for the following activities:</span></span>

- <span data-ttu-id="6dd9f-156">Crear nueva solicitud de aprobación</span><span class="sxs-lookup"><span data-stu-id="6dd9f-156">Create new approval request</span></span>

- <span data-ttu-id="6dd9f-157">Ver detalles de solicitud de aprobación</span><span class="sxs-lookup"><span data-stu-id="6dd9f-157">View approval request details</span></span>

- <span data-ttu-id="6dd9f-158">Solicitud de aprobación aprobada</span><span class="sxs-lookup"><span data-stu-id="6dd9f-158">Approved approval request</span></span>

- <span data-ttu-id="6dd9f-159">Solicitud de aprobación rechazada</span><span class="sxs-lookup"><span data-stu-id="6dd9f-159">Rejected approval request</span></span>

- <span data-ttu-id="6dd9f-160">Solicitud de aprobación cancelada</span><span class="sxs-lookup"><span data-stu-id="6dd9f-160">Canceled approval request</span></span>

- <span data-ttu-id="6dd9f-161">Solicitud de aprobación compartida</span><span class="sxs-lookup"><span data-stu-id="6dd9f-161">Shared approval request</span></span>

- <span data-ttu-id="6dd9f-162">Archivo adjunto a solicitud de aprobación</span><span class="sxs-lookup"><span data-stu-id="6dd9f-162">File attached to approval request</span></span>

- <span data-ttu-id="6dd9f-163">Solicitud de aprobación reasignada</span><span class="sxs-lookup"><span data-stu-id="6dd9f-163">Reassigned approval request</span></span>

- <span data-ttu-id="6dd9f-164">Se ha agregado la firma electrónica a la solicitud de aprobación</span><span class="sxs-lookup"><span data-stu-id="6dd9f-164">Added e-signature to approval request</span></span>

<span data-ttu-id="6dd9f-165">Para obtener acceso a más aprobaciones de auditoría dentro del flujo, habilite y configure la auditoría en el entorno predeterminado para la aprobación de las principales entidades de aprobación, la solicitud de aprobación y la respuesta de aprobación.</span><span class="sxs-lookup"><span data-stu-id="6dd9f-165">For access to more auditing approvals within Flow, enable and configure auditing in the default environment for the primary approval entities Approval, Approval Request, and Approval Response.</span></span> <span data-ttu-id="6dd9f-166">Las operaciones de crear, actualizar y eliminar son eventos que se pueden auditar para registros de aprobación.</span><span class="sxs-lookup"><span data-stu-id="6dd9f-166">Create, update, and delete operations are auditable events for Approval records.</span></span> <span data-ttu-id="6dd9f-167">Obtenga más información sobre los [datos de auditoría y la actividad de los usuarios para seguridad y cumplimiento: plataforma de energía \| Microsoft docs](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity).</span><span class="sxs-lookup"><span data-stu-id="6dd9f-167">Learn more about [Audit data and user activity for security and compliance - Power Platform \| Microsoft Docs](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity).</span></span>

<span data-ttu-id="6dd9f-168">La auditoría se puede personalizar en el [centro de seguridad y cumplimiento de Microsoft 365](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span><span class="sxs-lookup"><span data-stu-id="6dd9f-168">Auditing can be customized further in the [Microsoft 365 Security and Compliance Center](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span></span>

1. <span data-ttu-id="6dd9f-169">Para usar los informes preconfigurados, inicie sesión en Office 365 Security and Compliance.</span><span class="sxs-lookup"><span data-stu-id="6dd9f-169">To use the preconfigured reports, sign in to Office 365 Security and Compliance.</span></span>

2. <span data-ttu-id="6dd9f-170">Seleccione **buscar & investigación**.</span><span class="sxs-lookup"><span data-stu-id="6dd9f-170">Select **Search & investigation**.</span></span>

3. <span data-ttu-id="6dd9f-171">Busque en el registro de auditoría y seleccione la pestaña **actividades de Dynamics 365** .</span><span class="sxs-lookup"><span data-stu-id="6dd9f-171">Search the Audit log and select the **Dynamics 365 activities** tab.</span></span>

<span data-ttu-id="6dd9f-172">Más información sobre [el registro de actividad de Microsoft inverso y aplicaciones controladas por modelos: plataforma de energía](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing).</span><span class="sxs-lookup"><span data-stu-id="6dd9f-172">Learn more about [Microsoft Dataverse and model-driven apps activity logging - Power Platform](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing).</span></span>

## <a name="security"></a><span data-ttu-id="6dd9f-173">Seguridad</span><span class="sxs-lookup"><span data-stu-id="6dd9f-173">Security</span></span>

<span data-ttu-id="6dd9f-174">Desde la aplicación de aprobación de equipos, los usuarios tienen acceso para crear nuevas aprobaciones y ver aprobaciones que hayan enviado y recibido.</span><span class="sxs-lookup"><span data-stu-id="6dd9f-174">From the Teams Approval App, users have access to create new Approvals and view Approvals that they have sent and received.</span></span> <span data-ttu-id="6dd9f-175">Los usuarios no tendrán acceso a las aprobaciones creadas por otros usuarios, a menos que sean un respondedor o un visor de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="6dd9f-175">Users won't have access to Approvals that are created by others unless they're either a responder or a viewer of the request.</span></span>

> [!Note]
> <span data-ttu-id="6dd9f-176">Un usuario tendrá la función de visor de una solicitud si forma parte de la conversación o del canal en el que se creó la aprobación.</span><span class="sxs-lookup"><span data-stu-id="6dd9f-176">A user will be given a viewer role of a request if they are part of the chat or channel where the approval was created.</span></span> <span data-ttu-id="6dd9f-177">No tendrán la posibilidad de tomar medidas en la solicitud si no se dieron a ese rol cuando se creó la aprobación.</span><span class="sxs-lookup"><span data-stu-id="6dd9f-177">They won't have the ability to take action on the request if they weren't given that role when the approval was created.</span></span>
