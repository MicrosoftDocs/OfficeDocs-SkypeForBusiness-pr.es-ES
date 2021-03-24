---
title: Aprobaciones de disponibilidad de aplicaciones en Teams
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
description: Más información sobre la disponibilidad de la aplicación de aprobaciones en Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4235232a9d74b4583ecaed19b68ff87de982085c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103016"
---
# <a name="teams-approvals-app-availability"></a><span data-ttu-id="150f0-103">Disponibilidad de la aplicación Aprobaciones de Teams</span><span class="sxs-lookup"><span data-stu-id="150f0-103">Teams Approvals app availability</span></span>

<span data-ttu-id="150f0-104">La aplicación Aprobaciones está disponible como una aplicación personal para todos los usuarios de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="150f0-104">The Approvals app is available as a personal app for all Microsoft Teams users.</span></span>
<span data-ttu-id="150f0-105">La aplicación Aprobaciones ofrece una forma sencilla de ejercer las auditorías, el cumplimiento, la responsabilidad y los flujos de trabajo tanto a Aprobaciones estructuradas y no estructuradas en Teams.</span><span class="sxs-lookup"><span data-stu-id="150f0-105">The Approvals app provides a simple way to bring auditing, compliance, accountability, and workflows to both structured and unstructured Approvals in Teams.</span></span>

 ![muestra la aplicación de aprobaciones](media/approvals-selection.png)

<span data-ttu-id="150f0-107">Los usuarios pueden anclar la aplicación Aprobaciones para guardarla en la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="150f0-107">Users can pin the Approvals app to save it to the menu bar.</span></span>

 ![muestra la aplicación de aprobaciones con la opción de ancla](media/approvalApp-pin.png)

<span data-ttu-id="150f0-109">La primera aprobación creada a partir de la aplicación Aprobaciones desencadenará el aprovisionamiento de la solución de aprobación en el entorno predeterminado del Servicio de datos comunes (CDS).</span><span class="sxs-lookup"><span data-stu-id="150f0-109">The first approval created from the Approvals app will trigger the provisioning of the Approval Solution in the default Common Data Service (CDS) environment.</span></span> <span data-ttu-id="150f0-110">Las aprobaciones creadas a partir de la aplicación Aprobaciones se almacenarán en el entorno de CDS predeterminado.</span><span class="sxs-lookup"><span data-stu-id="150f0-110">Approvals created from the Approvals app will be stored in the default CDS environment.</span></span>

<span data-ttu-id="150f0-111">En este artículo se describen los roles y requisitos de la aplicación Aprobaciones.</span><span class="sxs-lookup"><span data-stu-id="150f0-111">This article describes the Approvals app requirements and roles.</span></span>

## <a name="required-permissions-and-licenses"></a><span data-ttu-id="150f0-112">Permisos y licencias necesarios</span><span class="sxs-lookup"><span data-stu-id="150f0-112">Required permissions and licenses</span></span>

<span data-ttu-id="150f0-113">Para usar la aplicación Aprobaciones, necesita permisos para los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="150f0-113">To use the Approvals app, you need permission for the following items:</span></span>

- <span data-ttu-id="150f0-114">Permisos para crear una base de datos de CDS de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="150f0-114">Permissions to create a Microsoft CDS database.</span></span>

- <span data-ttu-id="150f0-115">Una cuenta en [flow.microsoft.com](https://flow.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="150f0-115">An account on [flow.microsoft.com](https://flow.microsoft.com/)</span></span>

- <span data-ttu-id="150f0-116">Rol de administrador en el entorno de destino.</span><span class="sxs-lookup"><span data-stu-id="150f0-116">Administrator Role in the target environment.</span></span>

- <span data-ttu-id="150f0-117">Licencia para un [Power Automate](/power-automate/get-started-approvals), un Office 365 o una Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="150f0-117">License for a [Power Automate](/power-automate/get-started-approvals), an Office 365, or a Dynamics 365.</span></span>

## <a name="storage-with-cds"></a><span data-ttu-id="150f0-118">Almacenamiento con CDS</span><span class="sxs-lookup"><span data-stu-id="150f0-118">Storage with CDS</span></span>

<span data-ttu-id="150f0-119">El modelo de datos común (CDM) es el lenguaje de datos compartido que usan las aplicaciones empresariales y de análisis en el CDS.</span><span class="sxs-lookup"><span data-stu-id="150f0-119">The Common Data Model (CDM) is the shared data language used by business and analytical applications in the CDS.</span></span> <span data-ttu-id="150f0-120">Consiste en un conjunto de esquemas de datos estandarizados y extensibles publicados por Microsoft y nuestros asociados, que permiten la coherencia de los datos y su significado en aplicaciones y procesos empresariales.</span><span class="sxs-lookup"><span data-stu-id="150f0-120">It consists of a set of a standardized, extensible data schemas published by Microsoft and our partners that enables consistency of data and its meaning across applications and business processes.</span></span> <span data-ttu-id="150f0-121">Obtenga más información sobre los [Modelos de datos común de la plataforma de Microsoft Power](/power-automate/get-started-approvals).</span><span class="sxs-lookup"><span data-stu-id="150f0-121">Learn more about the [Common Data Model of the Microsoft Power Platform](/power-automate/get-started-approvals).</span></span>

<span data-ttu-id="150f0-122">Obtenga más información sobre el [flujo de trabajo de Aprobación](/power-automate/modern-approvals).</span><span class="sxs-lookup"><span data-stu-id="150f0-122">Learn more about the [Approval workflow](/power-automate/modern-approvals).</span></span>

## <a name="approvals-teams-app-permissions"></a><span data-ttu-id="150f0-123">Permisos de aplicación de Approvals Teams</span><span class="sxs-lookup"><span data-stu-id="150f0-123">Approvals Teams app permissions</span></span>

<span data-ttu-id="150f0-124">La aplicación Approvals Teams le permite acceder a las características siguientes:</span><span class="sxs-lookup"><span data-stu-id="150f0-124">The Approvals Teams app lets you access the following features:</span></span>

- <span data-ttu-id="150f0-125">Recibir los mensajes y los datos que usted solicite.</span><span class="sxs-lookup"><span data-stu-id="150f0-125">Receive messages and data that you provide to it.</span></span>

- <span data-ttu-id="150f0-126">Envío de mensajes y notificaciones.</span><span class="sxs-lookup"><span data-stu-id="150f0-126">Send you messages and notifications.</span></span>

- <span data-ttu-id="150f0-127">Mostar cuadros de diálogo y aplicaciones personales sin un encabezado proporcionado por Teams.</span><span class="sxs-lookup"><span data-stu-id="150f0-127">Render personal apps and dialogs without a Teams-provided header.</span></span>

- <span data-ttu-id="150f0-128">Obtenga acceso a la información del perfil, como su nombre, dirección de correo electrónico, nombre de la empresa e idioma de preferencia.</span><span class="sxs-lookup"><span data-stu-id="150f0-128">Access your profile information such as your name, email address, company name, and preferred language.</span></span>

- <span data-ttu-id="150f0-129">Recibir mensajes y datos que los miembros del equipo le proporcionen en un canal.</span><span class="sxs-lookup"><span data-stu-id="150f0-129">Receive messages and data that team members provide to it in a channel.</span></span>

- <span data-ttu-id="150f0-130">Enviar mensajes y notificaciones en un canal.</span><span class="sxs-lookup"><span data-stu-id="150f0-130">Send messages and notifications in a channel.</span></span>

- <span data-ttu-id="150f0-131">Obtener acceso a la información del equipo:</span><span class="sxs-lookup"><span data-stu-id="150f0-131">Access your team's information:</span></span>
  - <span data-ttu-id="150f0-132">nombre del equipo</span><span class="sxs-lookup"><span data-stu-id="150f0-132">team name</span></span>
  - <span data-ttu-id="150f0-133">lista de canales</span><span class="sxs-lookup"><span data-stu-id="150f0-133">channel list</span></span>
  - <span data-ttu-id="150f0-134">lista (nombres y direcciones de correo electrónico de los miembros del equipo).</span><span class="sxs-lookup"><span data-stu-id="150f0-134">roster (team member's names and email addresses).</span></span>

- <span data-ttu-id="150f0-135">Use la información del equipo para ponerse en contacto con ellos.</span><span class="sxs-lookup"><span data-stu-id="150f0-135">Use the team's information to contact them.</span></span>

## <a name="disable-the-approvals-app"></a><span data-ttu-id="150f0-136">Administrar la aplicación Aprobaciones</span><span class="sxs-lookup"><span data-stu-id="150f0-136">Disable the Approvals app</span></span>

<span data-ttu-id="150f0-137">La aplicación Aprobaciones está disponible de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="150f0-137">The Approvals app is available by default.</span></span> <span data-ttu-id="150f0-138">Puede deshabilitar la aplicación en el Centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="150f0-138">You can disable the app in the Teams admin center.</span></span>

  1. <span data-ttu-id="150f0-139">Inicie la sesión en el Centro de administración de Teams</span><span class="sxs-lookup"><span data-stu-id="150f0-139">Sign in to the Teams admin center.</span></span>

  2. <span data-ttu-id="150f0-140">Expanda **aplicación de Teams** y seleccione **Administrar aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="150f0-140">Expand **Teams apps** and select **Manage apps**.</span></span>

  3. <span data-ttu-id="150f0-141">Busque la aplicación Aprobaciones.</span><span class="sxs-lookup"><span data-stu-id="150f0-141">Search for the Approvals app.</span></span>

![muestra la navegación del Centro de administración donde se muestra Aplicaciones de Microsoft Teams > Administrar aplicaciones de forma resaltada](media/manage-approval-apps.png)

  4. <span data-ttu-id="150f0-143">Seleccione Aprobaciones.</span><span class="sxs-lookup"><span data-stu-id="150f0-143">Select Approvals.</span></span>

  5. <span data-ttu-id="150f0-144">Seleccione el botón de alternancia para deshabilitar la aplicación para su organización.</span><span class="sxs-lookup"><span data-stu-id="150f0-144">Select the toggle to disable the app for your organization.</span></span>

![muestra los detalles de la aplicación Aprobaciones](media/approvals-details.png)

## <a name="retention-policy"></a><span data-ttu-id="150f0-146">Directiva de retención</span><span class="sxs-lookup"><span data-stu-id="150f0-146">Retention policy</span></span>

<span data-ttu-id="150f0-147">Las aprobaciones creadas a partir de la aplicación de Aprobaciones se almacenan en el entorno de CDS predeterminado, que no admite copias de seguridad en este momento.</span><span class="sxs-lookup"><span data-stu-id="150f0-147">Approvals created from the Approvals App are stored in the default CDS environment, which doesn’t support backups at this time.</span></span> <span data-ttu-id="150f0-148">Obtenga más información sobre cómo [Respaldar y restaurar entornos - Power Platform \| Microsoft Docs](/power-platform/admin/backup-restore-environments).</span><span class="sxs-lookup"><span data-stu-id="150f0-148">Learn more about how to [Back up and restore environments - Power Platform \| Microsoft Docs](/power-platform/admin/backup-restore-environments).</span></span>

## <a name="auditing"></a><span data-ttu-id="150f0-149">Auditoría</span><span class="sxs-lookup"><span data-stu-id="150f0-149">Auditing</span></span>

<span data-ttu-id="150f0-150">La aplicación Aprobaciones registra eventos de auditoría del Centro de seguridad y cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="150f0-150">The Approvals App logs audit events within the Microsoft 365 Security and Compliance Center.</span></span> <span data-ttu-id="150f0-151">Puede ver el registro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="150f0-151">You can view the audit log.</span></span>

1. <span data-ttu-id="150f0-152">Vaya al sitio de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="150f0-152">Go to the Microsoft 365 Compliance Site.</span></span>

2. <span data-ttu-id="150f0-153">Seleccione la sección **Auditoría**.</span><span class="sxs-lookup"><span data-stu-id="150f0-153">Select the **Audit** section.</span></span>

3. <span data-ttu-id="150f0-154">Buscar actividades en las actividades **Aprobación de Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="150f0-154">Search for activities under **Microsoft Teams approvals activities**.</span></span>

<span data-ttu-id="150f0-155">Puede buscar las actividades siguientes:</span><span class="sxs-lookup"><span data-stu-id="150f0-155">You can search for the following activities:</span></span>

- <span data-ttu-id="150f0-156">Crear una nueva solicitud de aprobación</span><span class="sxs-lookup"><span data-stu-id="150f0-156">Create new approval request</span></span>

- <span data-ttu-id="150f0-157">Ver detalles de la solicitud de aprobación</span><span class="sxs-lookup"><span data-stu-id="150f0-157">View approval request details</span></span>

- <span data-ttu-id="150f0-158">Solicitud de aprobación aprobada</span><span class="sxs-lookup"><span data-stu-id="150f0-158">Approved approval request</span></span>

- <span data-ttu-id="150f0-159">Solicitud de aprobación rechazada</span><span class="sxs-lookup"><span data-stu-id="150f0-159">Rejected approval request</span></span>

- <span data-ttu-id="150f0-160">Solicitud de aprobación cancelada</span><span class="sxs-lookup"><span data-stu-id="150f0-160">Canceled approval request</span></span>

- <span data-ttu-id="150f0-161">Solicitud de aprobación compartida</span><span class="sxs-lookup"><span data-stu-id="150f0-161">Shared approval request</span></span>

- <span data-ttu-id="150f0-162">Archivo adjunto a solicitud de aprobación</span><span class="sxs-lookup"><span data-stu-id="150f0-162">File attached to approval request</span></span>

- <span data-ttu-id="150f0-163">Solicitud de aprobación reasignada</span><span class="sxs-lookup"><span data-stu-id="150f0-163">Reassigned approval request</span></span>

- <span data-ttu-id="150f0-164">Firma electrónica agregada a la solicitud de aprobación</span><span class="sxs-lookup"><span data-stu-id="150f0-164">Added e-signature to approval request</span></span>

<span data-ttu-id="150f0-165">Para tener acceso a más aprobaciones de auditoría en Flujo, habilite y configure la auditoría en el entorno predeterminado para las entidades de aprobación primaria Aprobación, solicitud de aprobación y respuesta de aprobación.</span><span class="sxs-lookup"><span data-stu-id="150f0-165">For access to more auditing approvals within Flow, enable and configure auditing in the default environment for the primary approval entities Approval, Approval Request, and Approval Response.</span></span> <span data-ttu-id="150f0-166">Las operaciones de creación, actualización y eliminación son eventos auditables para los registros de Aprobación.</span><span class="sxs-lookup"><span data-stu-id="150f0-166">Create, update, and delete operations are auditable events for Approval records.</span></span> <span data-ttu-id="150f0-167">Obtenga más información sobre [Datos de Auditoría y la actividad de usuario para la seguridad y el cumplimiento: Power Platform \| Microsoft Docs](/power-platform/admin/audit-data-user-activity).</span><span class="sxs-lookup"><span data-stu-id="150f0-167">Learn more about [Audit data and user activity for security and compliance - Power Platform \| Microsoft Docs](/power-platform/admin/audit-data-user-activity).</span></span>

<span data-ttu-id="150f0-168">Las auditorías se pueden personalizar aún más en el [Centro de seguridad y cumplimiento de Microsoft 365](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span><span class="sxs-lookup"><span data-stu-id="150f0-168">Auditing can be customized further in the [Microsoft 365 Security and Compliance Center](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span></span>

1. <span data-ttu-id="150f0-169">Para usar los informes preconfigurados, inicie sesión en Seguridad y cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="150f0-169">To use the preconfigured reports, sign in to Microsoft 365 Security and Compliance.</span></span>

2. <span data-ttu-id="150f0-170">Seleccione **Búsqueda e investigación**.</span><span class="sxs-lookup"><span data-stu-id="150f0-170">Select **Search & investigation**.</span></span>

3. <span data-ttu-id="150f0-171">Busque en el registro de Auditoría y seleccione la pestaña **Actividades de Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="150f0-171">Search the Audit log and select the **Dynamics 365 activities** tab.</span></span>

<span data-ttu-id="150f0-172">Obtenga más información sobre el [Registro de actividad de aplicaciones basadas en modelos y Microsoft Dataverse: Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).</span><span class="sxs-lookup"><span data-stu-id="150f0-172">Learn more about [Microsoft Dataverse and model-driven apps activity logging - Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).</span></span>

## <a name="security"></a><span data-ttu-id="150f0-173">Seguridad</span><span class="sxs-lookup"><span data-stu-id="150f0-173">Security</span></span>

<span data-ttu-id="150f0-174">Desde la aplicación Aprobaciones de Teams, los usuarios tienen acceso para crear nuevas aprobaciones y ver las aprobaciones que han enviado y recibido.</span><span class="sxs-lookup"><span data-stu-id="150f0-174">From the Teams Approvals app, users have access to create new Approvals and view Approvals that they have sent and received.</span></span> <span data-ttu-id="150f0-175">Los usuarios no tendrán acceso a Aprobaciones creadas por otros usuarios, excepto si son respondedores o lectores de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="150f0-175">Users won't have access to Approvals that are created by others unless they're either a responder or a viewer of the request.</span></span>

> [!Note]
> <span data-ttu-id="150f0-176">A un usuario se le asigna un rol de visor de una solicitud si forma parte del chat o canal donde se creó la aprobación.</span><span class="sxs-lookup"><span data-stu-id="150f0-176">A user will be given a viewer role of a request if they are part of the chat or channel where the approval was created.</span></span> <span data-ttu-id="150f0-177">No tendrán la capacidad de realizar acciones en la solicitud si no se les ha concedido ese rol cuando se creó la aprobación.</span><span class="sxs-lookup"><span data-stu-id="150f0-177">They won't have the ability to take action on the request if they weren't given that role when the approval was created.</span></span>