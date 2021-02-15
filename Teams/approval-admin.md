---
title: Disponibilidad de aplicaciones de aprobación en Teams
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
description: Obtenga información sobre la disponibilidad de la aplicación Aprobaciones en Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f916b4e794c862a05a42f075ca2f210a079ff42a
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909524"
---
# <a name="teams-approvals-app-availability"></a><span data-ttu-id="5f7b2-103">Disponibilidad de la aplicación Aprobaciones de Teams</span><span class="sxs-lookup"><span data-stu-id="5f7b2-103">Teams Approvals app availability</span></span>

<span data-ttu-id="5f7b2-104">La aplicación Aprobaciones está disponible como aplicación personal para todos los usuarios de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5f7b2-104">The Approvals app is available as a personal app for all Microsoft Teams users.</span></span>
<span data-ttu-id="5f7b2-105">La aplicación Aprobaciones ofrece una forma sencilla de auditar, cumplir, responsabilidad y flujos de trabajo a aprobaciones estructuradas y no estructuradas en Teams.</span><span class="sxs-lookup"><span data-stu-id="5f7b2-105">The Approvals app provides a simple way to bring auditing, compliance, accountability, and workflows to both structured and unstructured Approvals in Teams.</span></span>

 ![muestra la aplicación de aprobaciones](media/approvals-selection.png)

<span data-ttu-id="5f7b2-107">Los usuarios pueden anclar la aplicación Aprobaciones para guardarla en la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="5f7b2-107">Users can pin the Approvals app to save it to the menu bar.</span></span>

 ![muestra la aplicación de aprobaciones con la opción anclar](media/approvalApp-pin.png)

<span data-ttu-id="5f7b2-109">La primera aprobación creada desde la aplicación Aprobaciones desencadenará el aprovisionamiento de la solución de aprobación en el entorno predeterminado del Servicio de datos comunes (CDS).</span><span class="sxs-lookup"><span data-stu-id="5f7b2-109">The first approval created from the Approvals app will trigger the provisioning of the Approval Solution in the default Common Data Service (CDS) environment.</span></span> <span data-ttu-id="5f7b2-110">Las aprobaciones creadas desde la aplicación Aprobaciones se almacenarán en el entorno de CDS predeterminado.</span><span class="sxs-lookup"><span data-stu-id="5f7b2-110">Approvals created from the Approvals app will be stored in the default CDS environment.</span></span>

<span data-ttu-id="5f7b2-111">En este artículo se describen los requisitos y los roles de la aplicación Aprobaciones.</span><span class="sxs-lookup"><span data-stu-id="5f7b2-111">This article describes the Approvals app requirements and roles.</span></span>

## <a name="required-permissions-and-licenses"></a><span data-ttu-id="5f7b2-112">Permisos y licencias necesarios</span><span class="sxs-lookup"><span data-stu-id="5f7b2-112">Required permissions and licenses</span></span>

<span data-ttu-id="5f7b2-113">Para usar la aplicación Aprobaciones, necesita permiso para los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="5f7b2-113">To use the Approvals app, you need permission for the following items:</span></span>

- <span data-ttu-id="5f7b2-114">Permisos para crear una base de datos de CDS de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5f7b2-114">Permissions to create a Microsoft CDS database.</span></span>

- <span data-ttu-id="5f7b2-115">Una cuenta en [flow.microsoft.com](https://flow.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="5f7b2-115">An account on [flow.microsoft.com](https://flow.microsoft.com/)</span></span>

- <span data-ttu-id="5f7b2-116">Rol de administrador en el entorno de destino.</span><span class="sxs-lookup"><span data-stu-id="5f7b2-116">Administrator Role in the target environment.</span></span>

- <span data-ttu-id="5f7b2-117">Licencia para [Power Automate,](https://docs.microsoft.com/power-automate/get-started-approvals)Office 365 o Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="5f7b2-117">License for a [Power Automate](https://docs.microsoft.com/power-automate/get-started-approvals), an Office 365, or a Dynamics 365.</span></span>

## <a name="storage-with-cds"></a><span data-ttu-id="5f7b2-118">Almacenamiento con CDS</span><span class="sxs-lookup"><span data-stu-id="5f7b2-118">Storage with CDS</span></span>

<span data-ttu-id="5f7b2-119">El modelo de datos común (CDM) es el lenguaje de datos compartido que usan las aplicaciones empresariales y analíticas en los CDS.</span><span class="sxs-lookup"><span data-stu-id="5f7b2-119">The Common Data Model (CDM) is the shared data language used by business and analytical applications in the CDS.</span></span> <span data-ttu-id="5f7b2-120">Se compone de un conjunto de esquemas de datos estandarizados y extensibles publicados por Microsoft y nuestros socios que permite la coherencia de los datos y su significado en todas las aplicaciones y procesos empresariales.</span><span class="sxs-lookup"><span data-stu-id="5f7b2-120">It consists of a set of a standardized, extensible data schemas published by Microsoft and our partners that enables consistency of data and its meaning across applications and business processes.</span></span> <span data-ttu-id="5f7b2-121">Obtenga más información sobre el [modelo de datos común de Microsoft Power Platform.](https://docs.microsoft.com/power-automate/get-started-approvals)</span><span class="sxs-lookup"><span data-stu-id="5f7b2-121">Learn more about the [Common Data Model of the Microsoft Power Platform](https://docs.microsoft.com/power-automate/get-started-approvals).</span></span>

<span data-ttu-id="5f7b2-122">Obtenga más información sobre el flujo [de trabajo Aprobación.](https://docs.microsoft.com/power-automate/modern-approvals)</span><span class="sxs-lookup"><span data-stu-id="5f7b2-122">Learn more about the [Approval workflow](https://docs.microsoft.com/power-automate/modern-approvals).</span></span>

## <a name="approvals-teams-app-permissions"></a><span data-ttu-id="5f7b2-123">Permisos de la aplicación de Teams de aprobación</span><span class="sxs-lookup"><span data-stu-id="5f7b2-123">Approvals Teams app permissions</span></span>

<span data-ttu-id="5f7b2-124">La aplicación Desaprobaciones de Teams le permite acceder a las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="5f7b2-124">The Approvals Teams app lets you access the following features:</span></span>

- <span data-ttu-id="5f7b2-125">Recibir mensajes y datos que se le proporcionen.</span><span class="sxs-lookup"><span data-stu-id="5f7b2-125">Receive messages and data that you provide to it.</span></span>

- <span data-ttu-id="5f7b2-126">Envíate mensajes y notificaciones.</span><span class="sxs-lookup"><span data-stu-id="5f7b2-126">Send you messages and notifications.</span></span>

- <span data-ttu-id="5f7b2-127">Representar cuadros de diálogo y aplicaciones personales sin un encabezado proporcionado por Teams.</span><span class="sxs-lookup"><span data-stu-id="5f7b2-127">Render personal apps and dialogs without a Teams-provided header.</span></span>

- <span data-ttu-id="5f7b2-128">Obtenga acceso a la información de su perfil, como su nombre, dirección de correo electrónico, nombre de la empresa e idioma preferido.</span><span class="sxs-lookup"><span data-stu-id="5f7b2-128">Access your profile information such as your name, email address, company name, and preferred language.</span></span>

- <span data-ttu-id="5f7b2-129">Recibir mensajes y datos que los miembros del equipo le proporcionan en un canal.</span><span class="sxs-lookup"><span data-stu-id="5f7b2-129">Receive messages and data that team members provide to it in a channel.</span></span>

- <span data-ttu-id="5f7b2-130">Enviar mensajes y notificaciones en un canal.</span><span class="sxs-lookup"><span data-stu-id="5f7b2-130">Send messages and notifications in a channel.</span></span>

- <span data-ttu-id="5f7b2-131">Obtenga acceso a la información de su equipo:</span><span class="sxs-lookup"><span data-stu-id="5f7b2-131">Access your team's information:</span></span>
  - <span data-ttu-id="5f7b2-132">nombre del equipo</span><span class="sxs-lookup"><span data-stu-id="5f7b2-132">team name</span></span>
  - <span data-ttu-id="5f7b2-133">lista de canales</span><span class="sxs-lookup"><span data-stu-id="5f7b2-133">channel list</span></span>
  - <span data-ttu-id="5f7b2-134">lista (nombres y direcciones de correo electrónico de los miembros del equipo).</span><span class="sxs-lookup"><span data-stu-id="5f7b2-134">roster (team member's names and email addresses).</span></span>

- <span data-ttu-id="5f7b2-135">Use la información del equipo para ponerse en contacto con ellos.</span><span class="sxs-lookup"><span data-stu-id="5f7b2-135">Use the team's information to contact them.</span></span>

## <a name="disable-the-approvals-app"></a><span data-ttu-id="5f7b2-136">Deshabilitar la aplicación Aprobaciones</span><span class="sxs-lookup"><span data-stu-id="5f7b2-136">Disable the Approvals app</span></span>

<span data-ttu-id="5f7b2-137">La aplicación Aprobaciones está disponible de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5f7b2-137">The Approvals app is available by default.</span></span> <span data-ttu-id="5f7b2-138">Puede deshabilitar la aplicación en el Centro de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="5f7b2-138">You can disable the app in the Teams admin center.</span></span>

  1. <span data-ttu-id="5f7b2-139">Inicie sesión en el Centro de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="5f7b2-139">Sign in to the Teams admin center.</span></span>

  2. <span data-ttu-id="5f7b2-140">Expanda **las aplicaciones de Teams** y seleccione Administrar **aplicaciones.**</span><span class="sxs-lookup"><span data-stu-id="5f7b2-140">Expand **Teams apps** and select **Manage apps**.</span></span>

  3. <span data-ttu-id="5f7b2-141">Busque la aplicación Aprobaciones.</span><span class="sxs-lookup"><span data-stu-id="5f7b2-141">Search for the Approvals app.</span></span>

![muestra la navegación del Centro de administración con las aplicaciones de Teams > Administrar aplicaciones resaltada](media/manage-approval-apps.png)

  4. <span data-ttu-id="5f7b2-143">Seleccione Aprobaciones.</span><span class="sxs-lookup"><span data-stu-id="5f7b2-143">Select Approvals.</span></span>

  5. <span data-ttu-id="5f7b2-144">Seleccione el botón de alternancia para deshabilitar la aplicación para su organización.</span><span class="sxs-lookup"><span data-stu-id="5f7b2-144">Select the toggle to disable the app for your organization.</span></span>

![muestra los detalles de la aplicación Aprobaciones](media/approvals-details.png)

## <a name="retention-policy"></a><span data-ttu-id="5f7b2-146">Directiva de retención</span><span class="sxs-lookup"><span data-stu-id="5f7b2-146">Retention policy</span></span>

<span data-ttu-id="5f7b2-147">Las aprobaciones creadas desde la aplicación Aprobaciones se almacenan en el entorno predeterminado de CDS, que no admite copias de seguridad en este momento.</span><span class="sxs-lookup"><span data-stu-id="5f7b2-147">Approvals created from the Approvals App are stored in the default CDS environment, which doesn’t support backups at this time.</span></span> <span data-ttu-id="5f7b2-148">Obtenga más información sobre cómo hacer [copias de seguridad y restaurar entornos: Documentos de Microsoft de la plataforma \| móvil.](https://docs.microsoft.com/power-platform/admin/backup-restore-environments)</span><span class="sxs-lookup"><span data-stu-id="5f7b2-148">Learn more about how to [Back up and restore environments - Power Platform \| Microsoft Docs](https://docs.microsoft.com/power-platform/admin/backup-restore-environments).</span></span>

## <a name="auditing"></a><span data-ttu-id="5f7b2-149">Auditoría</span><span class="sxs-lookup"><span data-stu-id="5f7b2-149">Auditing</span></span>

<span data-ttu-id="5f7b2-150">La aplicación Aprobaciones registra eventos de auditoría en el Centro de seguridad y cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5f7b2-150">The Approvals App logs audit events within the Microsoft 365 Security and Compliance Center.</span></span> <span data-ttu-id="5f7b2-151">Puede ver el registro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="5f7b2-151">You can view the audit log.</span></span>

1. <span data-ttu-id="5f7b2-152">Vaya al Sitio de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5f7b2-152">Go to the Microsoft 365 Compliance Site.</span></span>

2. <span data-ttu-id="5f7b2-153">Seleccione la **sección** Auditoría.</span><span class="sxs-lookup"><span data-stu-id="5f7b2-153">Select the **Audit** section.</span></span>

3. <span data-ttu-id="5f7b2-154">Busque actividades en las **actividades de aprobación de Microsoft Teams.**</span><span class="sxs-lookup"><span data-stu-id="5f7b2-154">Search for activities under **Microsoft Teams approvals activities**.</span></span>

<span data-ttu-id="5f7b2-155">Puede buscar las siguientes actividades:</span><span class="sxs-lookup"><span data-stu-id="5f7b2-155">You can search for the following activities:</span></span>

- <span data-ttu-id="5f7b2-156">Crear una nueva solicitud de aprobación</span><span class="sxs-lookup"><span data-stu-id="5f7b2-156">Create new approval request</span></span>

- <span data-ttu-id="5f7b2-157">Ver detalles de la solicitud de aprobación</span><span class="sxs-lookup"><span data-stu-id="5f7b2-157">View approval request details</span></span>

- <span data-ttu-id="5f7b2-158">Solicitud de aprobación aprobada</span><span class="sxs-lookup"><span data-stu-id="5f7b2-158">Approved approval request</span></span>

- <span data-ttu-id="5f7b2-159">Solicitud de aprobación rechazada</span><span class="sxs-lookup"><span data-stu-id="5f7b2-159">Rejected approval request</span></span>

- <span data-ttu-id="5f7b2-160">Solicitud de aprobación cancelada</span><span class="sxs-lookup"><span data-stu-id="5f7b2-160">Canceled approval request</span></span>

- <span data-ttu-id="5f7b2-161">Solicitud de aprobación compartida</span><span class="sxs-lookup"><span data-stu-id="5f7b2-161">Shared approval request</span></span>

- <span data-ttu-id="5f7b2-162">Archivo adjunto a la solicitud de aprobación</span><span class="sxs-lookup"><span data-stu-id="5f7b2-162">File attached to approval request</span></span>

- <span data-ttu-id="5f7b2-163">Solicitud de aprobación reasignada</span><span class="sxs-lookup"><span data-stu-id="5f7b2-163">Reassigned approval request</span></span>

- <span data-ttu-id="5f7b2-164">Firma electrónica agregada a la solicitud de aprobación</span><span class="sxs-lookup"><span data-stu-id="5f7b2-164">Added e-signature to approval request</span></span>

<span data-ttu-id="5f7b2-165">Para obtener acceso a más aprobaciones de auditoría en Flow, habilite y configure la auditoría en el entorno predeterminado de las entidades de aprobación principales: Aprobación, Solicitud de aprobación y Respuesta de aprobación.</span><span class="sxs-lookup"><span data-stu-id="5f7b2-165">For access to more auditing approvals within Flow, enable and configure auditing in the default environment for the primary approval entities Approval, Approval Request, and Approval Response.</span></span> <span data-ttu-id="5f7b2-166">Las operaciones crear, actualizar y eliminar son eventos auditables para registros de aprobación.</span><span class="sxs-lookup"><span data-stu-id="5f7b2-166">Create, update, and delete operations are auditable events for Approval records.</span></span> <span data-ttu-id="5f7b2-167">Más información sobre datos [de auditoría y la actividad de usuario para seguridad y cumplimiento: Documentos de Microsoft de la plataforma \| móvil.](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity)</span><span class="sxs-lookup"><span data-stu-id="5f7b2-167">Learn more about [Audit data and user activity for security and compliance - Power Platform \| Microsoft Docs](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity).</span></span>

<span data-ttu-id="5f7b2-168">La auditoría puede personalizarse aún más en el Centro de seguridad y cumplimiento [de Microsoft 365.](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US)</span><span class="sxs-lookup"><span data-stu-id="5f7b2-168">Auditing can be customized further in the [Microsoft 365 Security and Compliance Center](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span></span>

1. <span data-ttu-id="5f7b2-169">Para usar los informes preconfigurados, inicie sesión en Seguridad y cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5f7b2-169">To use the preconfigured reports, sign in to Microsoft 365 Security and Compliance.</span></span>

2. <span data-ttu-id="5f7b2-170">Seleccione **Búsqueda & investigación.**</span><span class="sxs-lookup"><span data-stu-id="5f7b2-170">Select **Search & investigation**.</span></span>

3. <span data-ttu-id="5f7b2-171">Busque en el registro de auditoría y seleccione la **pestaña actividades de Dynamics 365.**</span><span class="sxs-lookup"><span data-stu-id="5f7b2-171">Search the Audit log and select the **Dynamics 365 activities** tab.</span></span>

<span data-ttu-id="5f7b2-172">Más información sobre el registro de actividades de aplicaciones controladas por el modelo y los datos [inversos de Microsoft : Plataforma de energía.](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing)</span><span class="sxs-lookup"><span data-stu-id="5f7b2-172">Learn more about [Microsoft Dataverse and model-driven apps activity logging - Power Platform](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing).</span></span>

## <a name="security"></a><span data-ttu-id="5f7b2-173">Seguridad</span><span class="sxs-lookup"><span data-stu-id="5f7b2-173">Security</span></span>

<span data-ttu-id="5f7b2-174">Desde la aplicación Aprobaciones de Teams, los usuarios tienen acceso para crear nuevas aprobaciones y ver las aprobaciones que han enviado y recibido.</span><span class="sxs-lookup"><span data-stu-id="5f7b2-174">From the Teams Approvals app, users have access to create new Approvals and view Approvals that they have sent and received.</span></span> <span data-ttu-id="5f7b2-175">Los usuarios no tendrán acceso a las aprobaciones creadas por otros usuarios a menos que sean respondedores o lectores de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="5f7b2-175">Users won't have access to Approvals that are created by others unless they're either a responder or a viewer of the request.</span></span>

> [!Note]
> <span data-ttu-id="5f7b2-176">A un usuario se le asigna el rol de visor de una solicitud si forma parte del chat o del canal en el que se creó la aprobación.</span><span class="sxs-lookup"><span data-stu-id="5f7b2-176">A user will be given a viewer role of a request if they are part of the chat or channel where the approval was created.</span></span> <span data-ttu-id="5f7b2-177">No tendrán la capacidad de realizar acciones en la solicitud si no se les ha dado ese rol cuando se creó la aprobación.</span><span class="sxs-lookup"><span data-stu-id="5f7b2-177">They won't have the ability to take action on the request if they weren't given that role when the approval was created.</span></span>
