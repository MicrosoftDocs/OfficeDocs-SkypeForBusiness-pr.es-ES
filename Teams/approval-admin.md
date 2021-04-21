---
title: Aprobaciones de disponibilidad de aplicaciones en Teams
author: cichur
ms.author: v-cichur
ms.reviewer: farhazk
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Más información sobre la disponibilidad de la aplicación de aprobaciones en Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1e03ad5c562f7fd31599bbb86f08e411dfa4b415
ms.sourcegitcommit: fb87d64c6f98041a1da50cf4ef6ff54cdc8d1d29
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "51902574"
---
# <a name="teams-approvals-app-availability"></a><span data-ttu-id="1345b-103">Disponibilidad de la aplicación Aprobaciones de Teams</span><span class="sxs-lookup"><span data-stu-id="1345b-103">Teams Approvals app availability</span></span>

<span data-ttu-id="1345b-104">La aplicación Aprobaciones está disponible como una aplicación personal para todos los usuarios de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1345b-104">The Approvals app is available as a personal app for all Microsoft Teams users.</span></span>
<span data-ttu-id="1345b-105">La aplicación Aprobaciones ofrece una forma sencilla de ejercer las auditorías, el cumplimiento, la responsabilidad y los flujos de trabajo tanto a Aprobaciones estructuradas y no estructuradas en Teams.</span><span class="sxs-lookup"><span data-stu-id="1345b-105">The Approvals app provides a simple way to bring auditing, compliance, accountability, and workflows to both structured and unstructured Approvals in Teams.</span></span>

 ![muestra la aplicación de aprobaciones](media/approvals-selection.png)

<span data-ttu-id="1345b-107">Los usuarios pueden anclar la aplicación Aprobaciones para guardarla en la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="1345b-107">Users can pin the Approvals app to save it to the menu bar.</span></span>

 ![muestra la aplicación de aprobaciones con la opción de ancla](media/approvalApp-pin.png)

<span data-ttu-id="1345b-109">La primera aprobación creada a partir de la aplicación Aprobaciones desencadenará el aprovisionamiento de la solución de aprobación en el entorno predeterminado del Servicio de datos comunes (CDS).</span><span class="sxs-lookup"><span data-stu-id="1345b-109">The first approval created from the Approvals app will trigger the provisioning of the Approval Solution in the default Common Data Service (CDS) environment.</span></span> <span data-ttu-id="1345b-110">Las aprobaciones creadas a partir de la aplicación Aprobaciones se almacenarán en el entorno de CDS predeterminado.</span><span class="sxs-lookup"><span data-stu-id="1345b-110">Approvals created from the Approvals app will be stored in the default CDS environment.</span></span>

<span data-ttu-id="1345b-111">En este artículo se describen los roles y requisitos de la aplicación Aprobaciones.</span><span class="sxs-lookup"><span data-stu-id="1345b-111">This article describes the Approvals app requirements and roles.</span></span>

> [!NOTE]
> <span data-ttu-id="1345b-112">Esta característica aún no se ha publicado para los usuarios de Government Community Cloud (GCC), Government Community Cloud High (GCCH) y Department of Defense (DOD).</span><span class="sxs-lookup"><span data-stu-id="1345b-112">This feature hasn't been released to Government Community Cloud (GCC), Government Community Cloud High (GCCH), and Department of Defense (DOD) users yet.</span></span>

## <a name="required-permissions-and-licenses"></a><span data-ttu-id="1345b-113">Permisos y licencias necesarios</span><span class="sxs-lookup"><span data-stu-id="1345b-113">Required permissions and licenses</span></span>

<span data-ttu-id="1345b-114">Para usar la aplicación Aprobaciones, necesita permisos para los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="1345b-114">To use the Approvals app, you need permission for the following items:</span></span>

- <span data-ttu-id="1345b-115">Permisos para crear una base de datos de CDS de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1345b-115">Permissions to create a Microsoft CDS database.</span></span>

- <span data-ttu-id="1345b-116">Una cuenta en [flow.microsoft.com](https://flow.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="1345b-116">An account on [flow.microsoft.com](https://flow.microsoft.com/)</span></span>

- <span data-ttu-id="1345b-117">Rol de administrador en el entorno de destino.</span><span class="sxs-lookup"><span data-stu-id="1345b-117">Administrator Role in the target environment.</span></span>

- <span data-ttu-id="1345b-118">Licencia para un [Power Automate](/power-automate/get-started-approvals), un Office 365 o una Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="1345b-118">License for a [Power Automate](/power-automate/get-started-approvals), an Office 365, or a Dynamics 365.</span></span>

## <a name="storage-with-cds"></a><span data-ttu-id="1345b-119">Almacenamiento con CDS</span><span class="sxs-lookup"><span data-stu-id="1345b-119">Storage with CDS</span></span>

<span data-ttu-id="1345b-120">El modelo de datos común (CDM) es el lenguaje de datos compartido que usan las aplicaciones empresariales y de análisis en el CDS.</span><span class="sxs-lookup"><span data-stu-id="1345b-120">The Common Data Model (CDM) is the shared data language used by business and analytical applications in the CDS.</span></span> <span data-ttu-id="1345b-121">Consiste en un conjunto de esquemas de datos estandarizados y extensibles publicados por Microsoft y nuestros partners, que permite la coherencia de los datos y su significado en todas las aplicaciones y procesos empresariales.</span><span class="sxs-lookup"><span data-stu-id="1345b-121">It consists of a set of a standardized, extensible data schemas published by Microsoft and our partners, that enables consistency of data and its meaning across applications and business processes.</span></span> <span data-ttu-id="1345b-122">Obtenga más información sobre los [Modelos de datos común de la plataforma de Microsoft Power](/power-automate/get-started-approvals).</span><span class="sxs-lookup"><span data-stu-id="1345b-122">Learn more about the [Common Data Model of the Microsoft Power Platform](/power-automate/get-started-approvals).</span></span>

<span data-ttu-id="1345b-123">Obtenga más información sobre el [flujo de trabajo de Aprobación](/power-automate/modern-approvals).</span><span class="sxs-lookup"><span data-stu-id="1345b-123">Learn more about the [Approval workflow](/power-automate/modern-approvals).</span></span>

## <a name="approvals-teams-app-permissions"></a><span data-ttu-id="1345b-124">Permisos de aplicación de Approvals Teams</span><span class="sxs-lookup"><span data-stu-id="1345b-124">Approvals Teams app permissions</span></span>

<span data-ttu-id="1345b-125">La aplicación Approvals Teams le permite acceder a las características siguientes:</span><span class="sxs-lookup"><span data-stu-id="1345b-125">The Approvals Teams app lets you access the following features:</span></span>

- <span data-ttu-id="1345b-126">Recibir los mensajes y los datos que usted solicite.</span><span class="sxs-lookup"><span data-stu-id="1345b-126">Receive messages and data that you provide to it.</span></span>

- <span data-ttu-id="1345b-127">Envío de mensajes y notificaciones.</span><span class="sxs-lookup"><span data-stu-id="1345b-127">Send you messages and notifications.</span></span>

- <span data-ttu-id="1345b-128">Mostar cuadros de diálogo y aplicaciones personales sin un encabezado proporcionado por Teams.</span><span class="sxs-lookup"><span data-stu-id="1345b-128">Render personal apps and dialogs without a Teams-provided header.</span></span>

- <span data-ttu-id="1345b-129">Obtenga acceso a la información del perfil, como su nombre, dirección de correo electrónico, nombre de la empresa e idioma de preferencia.</span><span class="sxs-lookup"><span data-stu-id="1345b-129">Access your profile information such as your name, email address, company name, and preferred language.</span></span>

- <span data-ttu-id="1345b-130">Recibir mensajes y datos que los miembros del equipo le proporcionen en un canal.</span><span class="sxs-lookup"><span data-stu-id="1345b-130">Receive messages and data that team members provide to it in a channel.</span></span>

- <span data-ttu-id="1345b-131">Enviar mensajes y notificaciones en un canal.</span><span class="sxs-lookup"><span data-stu-id="1345b-131">Send messages and notifications in a channel.</span></span>

- <span data-ttu-id="1345b-132">Obtener acceso a la información del equipo:</span><span class="sxs-lookup"><span data-stu-id="1345b-132">Access your team's information:</span></span>
  - <span data-ttu-id="1345b-133">nombre del equipo</span><span class="sxs-lookup"><span data-stu-id="1345b-133">team name</span></span>
  - <span data-ttu-id="1345b-134">lista de canales</span><span class="sxs-lookup"><span data-stu-id="1345b-134">channel list</span></span>
  - <span data-ttu-id="1345b-135">lista (nombres y direcciones de correo electrónico de los miembros del equipo).</span><span class="sxs-lookup"><span data-stu-id="1345b-135">roster (team member's names and email addresses).</span></span>

- <span data-ttu-id="1345b-136">Use la información del equipo para ponerse en contacto con ellos.</span><span class="sxs-lookup"><span data-stu-id="1345b-136">Use the team's information to contact them.</span></span>

## <a name="disable-the-approvals-app"></a><span data-ttu-id="1345b-137">Administrar la aplicación Aprobaciones</span><span class="sxs-lookup"><span data-stu-id="1345b-137">Disable the Approvals app</span></span>

<span data-ttu-id="1345b-138">La aplicación Aprobaciones está disponible de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1345b-138">The Approvals app is available by default.</span></span> <span data-ttu-id="1345b-139">Puede deshabilitar la aplicación en el Centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1345b-139">You can disable the app in the Teams admin center.</span></span>

  1. <span data-ttu-id="1345b-140">Inicie la sesión en el Centro de administración de Teams</span><span class="sxs-lookup"><span data-stu-id="1345b-140">Sign in to the Teams admin center.</span></span>

  2. <span data-ttu-id="1345b-141">Expanda **aplicación de Teams** y seleccione **Administrar aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="1345b-141">Expand **Teams apps** and select **Manage apps**.</span></span>

  3. <span data-ttu-id="1345b-142">Busque la aplicación Aprobaciones.</span><span class="sxs-lookup"><span data-stu-id="1345b-142">Search for the Approvals app.</span></span>

![muestra la navegación del Centro de administración donde se muestra Aplicaciones de Microsoft Teams > Administrar aplicaciones de forma resaltada](media/manage-approval-apps.png)

  4. <span data-ttu-id="1345b-144">Seleccione Aprobaciones.</span><span class="sxs-lookup"><span data-stu-id="1345b-144">Select Approvals.</span></span>

  5. <span data-ttu-id="1345b-145">Seleccione el botón de alternancia para deshabilitar la aplicación para su organización.</span><span class="sxs-lookup"><span data-stu-id="1345b-145">Select the toggle to disable the app for your organization.</span></span>

![muestra los detalles de la aplicación Aprobaciones](media/approvals-details.png)

## <a name="retention-policy"></a><span data-ttu-id="1345b-147">Directiva de retención</span><span class="sxs-lookup"><span data-stu-id="1345b-147">Retention policy</span></span>

<span data-ttu-id="1345b-148">Las aprobaciones creadas a partir de la aplicación de Aprobaciones se almacenan en el entorno de CDS predeterminado, que no admite copias de seguridad en este momento.</span><span class="sxs-lookup"><span data-stu-id="1345b-148">Approvals created from the Approvals App are stored in the default CDS environment, which doesn’t support backups at this time.</span></span> <span data-ttu-id="1345b-149">Obtenga más información sobre cómo [Respaldar y restaurar entornos - Power Platform \| Microsoft Docs](/power-platform/admin/backup-restore-environments).</span><span class="sxs-lookup"><span data-stu-id="1345b-149">Learn more about how to [Back up and restore environments - Power Platform \| Microsoft Docs](/power-platform/admin/backup-restore-environments).</span></span>

## <a name="auditing"></a><span data-ttu-id="1345b-150">Auditoría</span><span class="sxs-lookup"><span data-stu-id="1345b-150">Auditing</span></span>

<span data-ttu-id="1345b-151">La aplicación Aprobaciones registra eventos de auditoría del Centro de seguridad y cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1345b-151">The Approvals App logs audit events within the Microsoft 365 Security and Compliance Center.</span></span> <span data-ttu-id="1345b-152">Puede ver el registro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="1345b-152">You can view the audit log.</span></span>

1. <span data-ttu-id="1345b-153">Vaya al sitio de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1345b-153">Go to the Microsoft 365 Compliance Site.</span></span>

2. <span data-ttu-id="1345b-154">Seleccione la sección **Auditoría**.</span><span class="sxs-lookup"><span data-stu-id="1345b-154">Select the **Audit** section.</span></span>

3. <span data-ttu-id="1345b-155">Buscar actividades en las actividades **Aprobación de Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="1345b-155">Search for activities under **Microsoft Teams approvals activities**.</span></span>

<span data-ttu-id="1345b-156">Puede buscar las actividades siguientes:</span><span class="sxs-lookup"><span data-stu-id="1345b-156">You can search for the following activities:</span></span>

- <span data-ttu-id="1345b-157">Crear una nueva solicitud de aprobación</span><span class="sxs-lookup"><span data-stu-id="1345b-157">Create new approval request</span></span>

- <span data-ttu-id="1345b-158">Ver detalles de la solicitud de aprobación</span><span class="sxs-lookup"><span data-stu-id="1345b-158">View approval request details</span></span>

- <span data-ttu-id="1345b-159">Solicitud de aprobación aprobada</span><span class="sxs-lookup"><span data-stu-id="1345b-159">Approved approval request</span></span>

- <span data-ttu-id="1345b-160">Solicitud de aprobación rechazada</span><span class="sxs-lookup"><span data-stu-id="1345b-160">Rejected approval request</span></span>

- <span data-ttu-id="1345b-161">Solicitud de aprobación cancelada</span><span class="sxs-lookup"><span data-stu-id="1345b-161">Canceled approval request</span></span>

- <span data-ttu-id="1345b-162">Solicitud de aprobación compartida</span><span class="sxs-lookup"><span data-stu-id="1345b-162">Shared approval request</span></span>

- <span data-ttu-id="1345b-163">Archivo adjunto a solicitud de aprobación</span><span class="sxs-lookup"><span data-stu-id="1345b-163">File attached to approval request</span></span>

- <span data-ttu-id="1345b-164">Solicitud de aprobación reasignada</span><span class="sxs-lookup"><span data-stu-id="1345b-164">Reassigned approval request</span></span>

- <span data-ttu-id="1345b-165">Firma electrónica agregada a la solicitud de aprobación</span><span class="sxs-lookup"><span data-stu-id="1345b-165">Added e-signature to approval request</span></span>

<span data-ttu-id="1345b-166">Para tener acceso a más aprobaciones de auditoría en Flujo, habilite y configure la auditoría en el entorno predeterminado para las entidades de aprobación primaria Aprobación, solicitud de aprobación y respuesta de aprobación.</span><span class="sxs-lookup"><span data-stu-id="1345b-166">For access to more auditing approvals within Flow, enable and configure auditing in the default environment for the primary approval entities Approval, Approval Request, and Approval Response.</span></span> <span data-ttu-id="1345b-167">Las operaciones de creación, actualización y eliminación son eventos auditables para los registros de Aprobación.</span><span class="sxs-lookup"><span data-stu-id="1345b-167">Create, update, and delete operations are auditable events for Approval records.</span></span> <span data-ttu-id="1345b-168">Obtenga más información sobre [Datos de Auditoría y la actividad de usuario para la seguridad y el cumplimiento: Power Platform \| Microsoft Docs](/power-platform/admin/audit-data-user-activity).</span><span class="sxs-lookup"><span data-stu-id="1345b-168">Learn more about [Audit data and user activity for security and compliance - Power Platform \| Microsoft Docs](/power-platform/admin/audit-data-user-activity).</span></span>

<span data-ttu-id="1345b-169">Las auditorías se pueden personalizar aún más en el [Centro de seguridad y cumplimiento de Microsoft 365](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span><span class="sxs-lookup"><span data-stu-id="1345b-169">Auditing can be customized further in the [Microsoft 365 Security and Compliance Center](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span></span>

1. <span data-ttu-id="1345b-170">Para usar los informes preconfigurados, inicie sesión en Seguridad y cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1345b-170">To use the preconfigured reports, sign in to Microsoft 365 Security and Compliance.</span></span>

2. <span data-ttu-id="1345b-171">Seleccione **Búsqueda e investigación**.</span><span class="sxs-lookup"><span data-stu-id="1345b-171">Select **Search & investigation**.</span></span>

3. <span data-ttu-id="1345b-172">Busque en el registro de Auditoría y seleccione la pestaña **Actividades de Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="1345b-172">Search the Audit log and select the **Dynamics 365 activities** tab.</span></span>

<span data-ttu-id="1345b-173">Obtenga más información sobre el [Registro de actividad de aplicaciones basadas en modelos y Microsoft Dataverse: Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).</span><span class="sxs-lookup"><span data-stu-id="1345b-173">Learn more about [Microsoft Dataverse and model-driven apps activity logging - Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).</span></span>

## <a name="security"></a><span data-ttu-id="1345b-174">Seguridad</span><span class="sxs-lookup"><span data-stu-id="1345b-174">Security</span></span>

<span data-ttu-id="1345b-175">Desde la aplicación Aprobaciones de Teams, los usuarios tienen acceso para crear nuevas aprobaciones y ver las aprobaciones que han enviado y recibido.</span><span class="sxs-lookup"><span data-stu-id="1345b-175">From the Teams Approvals app, users have access to create new Approvals and view Approvals that they have sent and received.</span></span> <span data-ttu-id="1345b-176">Los usuarios no tendrán acceso a Aprobaciones creadas por otros usuarios, excepto si son respondedores o lectores de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="1345b-176">Users won't have access to Approvals that are created by others unless they're either a responder or a viewer of the request.</span></span>

> [!Note]
> <span data-ttu-id="1345b-177">A un usuario se le asigna un rol de visor de una solicitud si forma parte del chat o canal donde se creó la aprobación.</span><span class="sxs-lookup"><span data-stu-id="1345b-177">A user will be given a viewer role of a request if they are part of the chat or channel where the approval was created.</span></span> <span data-ttu-id="1345b-178">No tendrán la capacidad de realizar acciones en la solicitud si no se les ha concedido ese rol cuando se creó la aprobación.</span><span class="sxs-lookup"><span data-stu-id="1345b-178">They won't have the ability to take action on the request if they weren't given that role when the approval was created.</span></span>