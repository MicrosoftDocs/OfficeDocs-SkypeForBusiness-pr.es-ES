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
ms.openlocfilehash: 127fc2831e58e7ddea152c7754015a9126390ecc
ms.sourcegitcommit: 5a738cbb96f09edd8c3779f9385bc9ed126e3001
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2021
ms.locfileid: "52212173"
---
# <a name="teams-approvals-app-availability"></a><span data-ttu-id="0523f-103">Disponibilidad de la aplicación Aprobaciones de Teams</span><span class="sxs-lookup"><span data-stu-id="0523f-103">Teams Approvals app availability</span></span>

<span data-ttu-id="0523f-104">La aplicación Aprobaciones está disponible como una aplicación personal para todos los usuarios de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0523f-104">The Approvals app is available as a personal app for all Microsoft Teams users.</span></span>
<span data-ttu-id="0523f-105">La aplicación Aprobaciones ofrece una forma sencilla de ejercer las auditorías, el cumplimiento, la responsabilidad y los flujos de trabajo tanto a Aprobaciones estructuradas y no estructuradas en Teams.</span><span class="sxs-lookup"><span data-stu-id="0523f-105">The Approvals app provides a simple way to bring auditing, compliance, accountability, and workflows to both structured and unstructured Approvals in Teams.</span></span>

 ![muestra la aplicación de aprobaciones](media/approvals-selection.png)

<span data-ttu-id="0523f-107">Los usuarios pueden anclar la aplicación Aprobaciones para guardarla en la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="0523f-107">Users can pin the Approvals app to save it to the menu bar.</span></span>

 ![muestra la aplicación de aprobaciones con la opción de ancla](media/approvalApp-pin.png)

<span data-ttu-id="0523f-109">La primera aprobación creada a partir de la aplicación Aprobaciones desencadenará el aprovisionamiento de la solución de aprobación en el entorno predeterminado del Servicio de datos comunes (CDS).</span><span class="sxs-lookup"><span data-stu-id="0523f-109">The first approval created from the Approvals app will trigger the provisioning of the Approval Solution in the default Common Data Service (CDS) environment.</span></span> <span data-ttu-id="0523f-110">Las aprobaciones creadas a partir de la aplicación Aprobaciones se almacenarán en el entorno de CDS predeterminado.</span><span class="sxs-lookup"><span data-stu-id="0523f-110">Approvals created from the Approvals app will be stored in the default CDS environment.</span></span>

<span data-ttu-id="0523f-111">En este artículo se describen los roles y requisitos de la aplicación Aprobaciones.</span><span class="sxs-lookup"><span data-stu-id="0523f-111">This article describes the Approvals app requirements and roles.</span></span>

> [!NOTE]
> <span data-ttu-id="0523f-112">Esta característica aún no se ha publicado para Government Community Cloud (GCC), Government Community Cloud High (GCCH) y los usuarios del Departamento de Defensa (DOD).</span><span class="sxs-lookup"><span data-stu-id="0523f-112">This feature hasn't been released to Government Community Cloud (GCC), Government Community Cloud High (GCCH), and Department of Defense (DOD) users yet.</span></span>

## <a name="required-permissions-and-licenses"></a><span data-ttu-id="0523f-113">Permisos y licencias necesarios</span><span class="sxs-lookup"><span data-stu-id="0523f-113">Required permissions and licenses</span></span>

<span data-ttu-id="0523f-114">Para usar la aplicación Aprobaciones, necesita permisos para los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="0523f-114">To use the Approvals app, you need permission for the following items:</span></span>

- <span data-ttu-id="0523f-115">Permisos para crear una base de datos de CDS de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0523f-115">Permissions to create a Microsoft CDS database.</span></span>

- <span data-ttu-id="0523f-116">Una cuenta en [flow.microsoft.com](https://flow.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="0523f-116">An account on [flow.microsoft.com](https://flow.microsoft.com/)</span></span>

- <span data-ttu-id="0523f-117">Rol de administrador en el entorno de destino.</span><span class="sxs-lookup"><span data-stu-id="0523f-117">Administrator Role in the target environment.</span></span>

- <span data-ttu-id="0523f-118">Licencia para un [Power Automate](/power-automate/get-started-approvals), un Office 365 o una Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="0523f-118">License for a [Power Automate](/power-automate/get-started-approvals), an Office 365, or a Dynamics 365.</span></span>

- <span data-ttu-id="0523f-119">La licencia de Microsoft Forms es necesaria para que los usuarios configuren nuevas plantillas de aprobación.</span><span class="sxs-lookup"><span data-stu-id="0523f-119">License for Microsoft Forms is required for users to set up new approval templates.</span></span>

## <a name="storage-with-cds"></a><span data-ttu-id="0523f-120">Almacenamiento con CDS</span><span class="sxs-lookup"><span data-stu-id="0523f-120">Storage with CDS</span></span>

<span data-ttu-id="0523f-121">El modelo de datos común (CDM) es el lenguaje de datos compartido que usan las aplicaciones empresariales y de análisis en el CDS.</span><span class="sxs-lookup"><span data-stu-id="0523f-121">The Common Data Model (CDM) is the shared data language used by business and analytical applications in the CDS.</span></span> <span data-ttu-id="0523f-122">Consiste en un conjunto de esquemas de datos estandarizados y extensibles publicados por Microsoft y nuestros asociados, que permiten la coherencia de los datos y su significado en aplicaciones y procesos empresariales.</span><span class="sxs-lookup"><span data-stu-id="0523f-122">It consists of a set of a standardized, extensible data schemas published by Microsoft and our partners that enables consistency of data and its meaning across applications and business processes.</span></span> <span data-ttu-id="0523f-123">Obtenga más información sobre los [Modelos de datos común de la plataforma de Microsoft Power](/power-automate/get-started-approvals).</span><span class="sxs-lookup"><span data-stu-id="0523f-123">Learn more about the [Common Data Model of the Microsoft Power Platform](/power-automate/get-started-approvals).</span></span>

<span data-ttu-id="0523f-124">Obtenga más información sobre el [flujo de trabajo de Aprobación](/power-automate/modern-approvals).</span><span class="sxs-lookup"><span data-stu-id="0523f-124">Learn more about the [Approval workflow](/power-automate/modern-approvals).</span></span>

<span data-ttu-id="0523f-125">Las aprobaciones creadas a partir de una plantilla siguen almacenando datos en CDS, como su título, detalles, id. de plantilla y mucho más.</span><span class="sxs-lookup"><span data-stu-id="0523f-125">Approvals that are created from a template still store data in CDS, such as their title, details, template ID, and more.</span></span> <span data-ttu-id="0523f-126">Las respuestas que se envían en la solicitud de aprobación se almacenan en Formularios.</span><span class="sxs-lookup"><span data-stu-id="0523f-126">Responses that are submitted on the approval request are stored in Forms.</span></span> <span data-ttu-id="0523f-127">Obtenga más información sobre  [el almacenamiento de datos para Microsoft Forms.](https://support.microsoft.com/office/data-storage-for-microsoft-forms-97a34e2e-98e1-4dc2-b6b4-7a8444cb1dc3#:~:text=Where%20data%20is%20stored%20for%20Microsoft%20Forms.%20Microsoft,European-based%20tenants%20is%20stored%20on%20servers%20in%20Europe)</span><span class="sxs-lookup"><span data-stu-id="0523f-127">Learn more about  [Data storage for Microsoft Forms](https://support.microsoft.com/office/data-storage-for-microsoft-forms-97a34e2e-98e1-4dc2-b6b4-7a8444cb1dc3#:~:text=Where%20data%20is%20stored%20for%20Microsoft%20Forms.%20Microsoft,European-based%20tenants%20is%20stored%20on%20servers%20in%20Europe).</span></span>

>[!Note]
><span data-ttu-id="0523f-128">Si elimina la plantilla Formulario en el sitio de Microsoft Forms, interrumpirá la plantilla de aprobación y los usuarios no podrán iniciar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="0523f-128">If you delete the Form template on the Microsoft Forms site, it will break your Approval template and users will not be able to start the request.</span></span> <span data-ttu-id="0523f-129">Los usuarios recibirán un error "CDB TableNotFound" al intentar abrir una plantilla de aprobación que se ha eliminado en Microsoft Forms.</span><span class="sxs-lookup"><span data-stu-id="0523f-129">Users will get an error "CDB TableNotFound" when trying to open an Approval template that has been deleted on Microsoft Forms.</span></span>

<span data-ttu-id="0523f-130">Las plantillas de aprobación se almacenan en Datos de Storage (SDS), que es una plataforma de almacenamiento compatible que solo se usa internamente dentro de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0523f-130">The approval templates are stored in Substrate Data Storage (SDS), which is a compliant storage platform used internally only inside Microsoft.</span></span> <span data-ttu-id="0523f-131">Las plantillas de ámbito de la organización se almacenan en "fragmento de espacio empresarial" de SDS y las plantillas de ámbito de equipo se almacenan en "fragmentos de grupo" de SDS.</span><span class="sxs-lookup"><span data-stu-id="0523f-131">The organization-scoped templates are stored in “tenant shard” of SDS, and team-scoped templates are stored in “group shards” of SDS.</span></span> <span data-ttu-id="0523f-132">Esto significa que las plantillas de ámbito de organización comparten la misma duración del espacio empresarial y las plantillas de ámbito de grupo comparten la misma duración del equipo.</span><span class="sxs-lookup"><span data-stu-id="0523f-132">This means that the org-scoped templates share the same lifetime of the tenant and team-scoped templates share the same lifetime of the team.</span></span> <span data-ttu-id="0523f-133">Por lo tanto, la eliminación permanente del equipo elimina las plantillas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="0523f-133">So, permanently deleting the team deletes the related templates.</span></span>

## <a name="approvals-teams-app-permissions"></a><span data-ttu-id="0523f-134">Permisos de aplicación de Approvals Teams</span><span class="sxs-lookup"><span data-stu-id="0523f-134">Approvals Teams app permissions</span></span>

<span data-ttu-id="0523f-135">La aplicación Approvals Teams le permite acceder a las características siguientes:</span><span class="sxs-lookup"><span data-stu-id="0523f-135">The Approvals Teams app lets you access the following features:</span></span>

- <span data-ttu-id="0523f-136">Recibir los mensajes y los datos que usted solicite.</span><span class="sxs-lookup"><span data-stu-id="0523f-136">Receive messages and data that you provide to it.</span></span>

- <span data-ttu-id="0523f-137">Envío de mensajes y notificaciones.</span><span class="sxs-lookup"><span data-stu-id="0523f-137">Send you messages and notifications.</span></span>

- <span data-ttu-id="0523f-138">Mostar cuadros de diálogo y aplicaciones personales sin un encabezado proporcionado por Teams.</span><span class="sxs-lookup"><span data-stu-id="0523f-138">Render personal apps and dialogs without a Teams-provided header.</span></span>

- <span data-ttu-id="0523f-139">Obtenga acceso a la información del perfil, como su nombre, dirección de correo electrónico, nombre de la empresa e idioma de preferencia.</span><span class="sxs-lookup"><span data-stu-id="0523f-139">Access your profile information such as your name, email address, company name, and preferred language.</span></span>

- <span data-ttu-id="0523f-140">Recibir mensajes y datos que los miembros del equipo le proporcionen en un canal.</span><span class="sxs-lookup"><span data-stu-id="0523f-140">Receive messages and data that team members provide to it in a channel.</span></span>

- <span data-ttu-id="0523f-141">Enviar mensajes y notificaciones en un canal.</span><span class="sxs-lookup"><span data-stu-id="0523f-141">Send messages and notifications in a channel.</span></span>

- <span data-ttu-id="0523f-142">Obtener acceso a la información del equipo:</span><span class="sxs-lookup"><span data-stu-id="0523f-142">Access your team's information:</span></span>
  - <span data-ttu-id="0523f-143">nombre del equipo</span><span class="sxs-lookup"><span data-stu-id="0523f-143">team name</span></span>
  - <span data-ttu-id="0523f-144">lista de canales</span><span class="sxs-lookup"><span data-stu-id="0523f-144">channel list</span></span>
  - <span data-ttu-id="0523f-145">lista (nombres y direcciones de correo electrónico de los miembros del equipo).</span><span class="sxs-lookup"><span data-stu-id="0523f-145">roster (team member's names and email addresses).</span></span>

- <span data-ttu-id="0523f-146">Use la información del equipo para ponerse en contacto con ellos.</span><span class="sxs-lookup"><span data-stu-id="0523f-146">Use the team's information to contact them.</span></span>

<span data-ttu-id="0523f-147">Permisos de plantilla de aprobación</span><span class="sxs-lookup"><span data-stu-id="0523f-147">Approval Template Permissions</span></span>

- <span data-ttu-id="0523f-148">Todos los propietarios de equipos pueden crear una plantilla de aprobación para los equipos de su propiedad.</span><span class="sxs-lookup"><span data-stu-id="0523f-148">All team owners can create an approval template for teams that they own.</span></span>

- <span data-ttu-id="0523f-149">Cuando un administrador crea una plantilla para toda su organización por primera vez, creará automáticamente un nuevo equipo de Teams para todos los administradores del inquilino, incluidos los administradores globales y de servicio del equipo.</span><span class="sxs-lookup"><span data-stu-id="0523f-149">When an Admin creates a template for their entire organization for the first time, it will automatically create a new Teams team for all admins of the tenant, including the global and Team’s service admins.</span></span> <span data-ttu-id="0523f-150">Estos administradores se agregarán como propietarios del equipo, para que puedan administrar en coadministraciones las plantillas de la organización.</span><span class="sxs-lookup"><span data-stu-id="0523f-150">These admins will be added as owners of the team, so they can co-manage organizational templates.</span></span> <span data-ttu-id="0523f-151">Los administradores que son nuevos en la organización después de crear el equipo deben agregarse manualmente como propietarios de equipos para que tengan los mismos permisos para administrar plantillas de toda la organización.</span><span class="sxs-lookup"><span data-stu-id="0523f-151">Admins that are new to the organization after the team has been created need to be manually added as team owners so they have the same permissions to manage organization-wide templates.</span></span>

> [!Note]
> <span data-ttu-id="0523f-152">Si un administrador elimina el equipo, tiene un mes para restaurarlo en el portal Azure Active Directory (AAD) para restaurar todos los datos relacionados.</span><span class="sxs-lookup"><span data-stu-id="0523f-152">If an admin deletes the team, you have one month to restore it within the Azure Active Directory (AAD) portal to restore all related data.</span></span> <span data-ttu-id="0523f-153">Después de un mes, o si el administrador elimina este equipo dentro de la papelera de reciclaje, perderá todos los datos relacionados.</span><span class="sxs-lookup"><span data-stu-id="0523f-153">After one month, or if the admin deletes this team within the recycle bin, you will lose all the related data.</span></span>

## <a name="disable-the-approvals-app"></a><span data-ttu-id="0523f-154">Administrar la aplicación Aprobaciones</span><span class="sxs-lookup"><span data-stu-id="0523f-154">Disable the Approvals app</span></span>

<span data-ttu-id="0523f-155">La aplicación Aprobaciones está disponible de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0523f-155">The Approvals app is available by default.</span></span> <span data-ttu-id="0523f-156">Puede deshabilitar la aplicación en el Centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0523f-156">You can disable the app in the Teams admin center.</span></span>

  1. <span data-ttu-id="0523f-157">Inicie la sesión en el Centro de administración de Teams</span><span class="sxs-lookup"><span data-stu-id="0523f-157">Sign in to the Teams admin center.</span></span>

  2. <span data-ttu-id="0523f-158">Expanda **aplicación de Teams** y seleccione **Administrar aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="0523f-158">Expand **Teams apps** and select **Manage apps**.</span></span>

  3. <span data-ttu-id="0523f-159">Busque la aplicación Aprobaciones.</span><span class="sxs-lookup"><span data-stu-id="0523f-159">Search for the Approvals app.</span></span>

     ![muestra la navegación del Centro de administración donde se muestra Aplicaciones de Microsoft Teams > Administrar aplicaciones de forma resaltada](media/manage-approval-apps.png)

  4. <span data-ttu-id="0523f-161">Seleccione Aprobaciones.</span><span class="sxs-lookup"><span data-stu-id="0523f-161">Select Approvals.</span></span>

  5. <span data-ttu-id="0523f-162">Seleccione el botón de alternancia para deshabilitar la aplicación para su organización.</span><span class="sxs-lookup"><span data-stu-id="0523f-162">Select the toggle to disable the app for your organization.</span></span>

     ![muestra los detalles de la aplicación Aprobaciones](media/approvals-details.png)

## <a name="retention-policy"></a><span data-ttu-id="0523f-164">Directiva de retención</span><span class="sxs-lookup"><span data-stu-id="0523f-164">Retention policy</span></span>

<span data-ttu-id="0523f-165">Las aprobaciones creadas a partir de la aplicación de Aprobaciones se almacenan en el entorno de CDS predeterminado, que no admite copias de seguridad en este momento.</span><span class="sxs-lookup"><span data-stu-id="0523f-165">Approvals created from the Approvals App are stored in the default CDS environment, which doesn’t support backups at this time.</span></span> <span data-ttu-id="0523f-166">Obtenga más información sobre cómo [Respaldar y restaurar entornos - Power Platform \| Microsoft Docs](/power-platform/admin/backup-restore-environments).</span><span class="sxs-lookup"><span data-stu-id="0523f-166">Learn more about how to [Back up and restore environments - Power Platform \| Microsoft Docs](/power-platform/admin/backup-restore-environments).</span></span>

<span data-ttu-id="0523f-167">Los datos almacenados en Formularios no se eliminarán hasta que los propietarios del equipo los limpien de la pestaña formularios **eliminados** en la aplicación web Microsoft Forms.</span><span class="sxs-lookup"><span data-stu-id="0523f-167">Data stored in Forms will not be deleted until the team owners clean it up from the **deleted forms** tab in the Microsoft Forms web app.</span></span>

## <a name="data-limitations"></a><span data-ttu-id="0523f-168">Limitaciones de datos</span><span class="sxs-lookup"><span data-stu-id="0523f-168">Data limitations</span></span>

<span data-ttu-id="0523f-169">Cada equipo puede contener como máximo 400 plantillas de aprobaciones y cada plantilla puede recopilar un máximo de 50 000 solicitudes en función de la capacidad actual de Microsoft Forms.</span><span class="sxs-lookup"><span data-stu-id="0523f-169">Each team can contain at most 400 approvals templates, and each template can collect a maximum of 50,000 requests based on the current capability in Microsoft Forms.</span></span>

## <a name="auditing"></a><span data-ttu-id="0523f-170">Auditoría</span><span class="sxs-lookup"><span data-stu-id="0523f-170">Auditing</span></span>

<span data-ttu-id="0523f-171">La aplicación Aprobaciones registra eventos de auditoría del Centro de seguridad y cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0523f-171">The Approvals App logs audit events within the Microsoft 365 Security and Compliance Center.</span></span> <span data-ttu-id="0523f-172">Puede ver el registro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="0523f-172">You can view the audit log.</span></span>

1. <span data-ttu-id="0523f-173">Vaya al sitio de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0523f-173">Go to the Microsoft 365 Compliance Site.</span></span>

2. <span data-ttu-id="0523f-174">Seleccione la sección **Auditoría**.</span><span class="sxs-lookup"><span data-stu-id="0523f-174">Select the **Audit** section.</span></span>

3. <span data-ttu-id="0523f-175">Buscar actividades en las actividades **Aprobación de Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="0523f-175">Search for activities under **Microsoft Teams approvals activities**.</span></span>

<span data-ttu-id="0523f-176">Puede buscar las actividades siguientes:</span><span class="sxs-lookup"><span data-stu-id="0523f-176">You can search for the following activities:</span></span>

- <span data-ttu-id="0523f-177">Crear una nueva solicitud de aprobación</span><span class="sxs-lookup"><span data-stu-id="0523f-177">Create new approval request</span></span>

- <span data-ttu-id="0523f-178">Ver detalles de la solicitud de aprobación</span><span class="sxs-lookup"><span data-stu-id="0523f-178">View approval request details</span></span>

- <span data-ttu-id="0523f-179">Solicitud de aprobación aprobada</span><span class="sxs-lookup"><span data-stu-id="0523f-179">Approved approval request</span></span>

- <span data-ttu-id="0523f-180">Solicitud de aprobación rechazada</span><span class="sxs-lookup"><span data-stu-id="0523f-180">Rejected approval request</span></span>

- <span data-ttu-id="0523f-181">Solicitud de aprobación cancelada</span><span class="sxs-lookup"><span data-stu-id="0523f-181">Canceled approval request</span></span>

- <span data-ttu-id="0523f-182">Solicitud de aprobación compartida</span><span class="sxs-lookup"><span data-stu-id="0523f-182">Shared approval request</span></span>

- <span data-ttu-id="0523f-183">Archivo adjunto a solicitud de aprobación</span><span class="sxs-lookup"><span data-stu-id="0523f-183">File attached to approval request</span></span>

- <span data-ttu-id="0523f-184">Solicitud de aprobación reasignada</span><span class="sxs-lookup"><span data-stu-id="0523f-184">Reassigned approval request</span></span>

- <span data-ttu-id="0523f-185">Firma electrónica agregada a la solicitud de aprobación</span><span class="sxs-lookup"><span data-stu-id="0523f-185">Added e-signature to approval request</span></span>

- <span data-ttu-id="0523f-186">Detalles de solicitud de firma electrónica vistas</span><span class="sxs-lookup"><span data-stu-id="0523f-186">Viewed e-signature request details</span></span>

- <span data-ttu-id="0523f-187">Solicitud de firma electrónica revisada</span><span class="sxs-lookup"><span data-stu-id="0523f-187">Reviewed e-signature request</span></span>

- <span data-ttu-id="0523f-188">Solicitud de firma electrónica cancelada</span><span class="sxs-lookup"><span data-stu-id="0523f-188">Canceled e-signature request</span></span>

- <span data-ttu-id="0523f-189">Crear una plantilla nueva</span><span class="sxs-lookup"><span data-stu-id="0523f-189">Create a new template</span></span>

- <span data-ttu-id="0523f-190">Editar una plantilla existente</span><span class="sxs-lookup"><span data-stu-id="0523f-190">Edit an existing template</span></span>

- <span data-ttu-id="0523f-191">Habilitar o deshabilitar una plantilla</span><span class="sxs-lookup"><span data-stu-id="0523f-191">Enable/disable a template</span></span>

- <span data-ttu-id="0523f-192">Plantilla vista</span><span class="sxs-lookup"><span data-stu-id="0523f-192">Viewed template</span></span>

<span data-ttu-id="0523f-193">Para tener acceso a más aprobaciones de auditoría en Flujo, habilite y configure la auditoría en el entorno predeterminado para las entidades de aprobación primaria Aprobación, solicitud de aprobación y respuesta de aprobación.</span><span class="sxs-lookup"><span data-stu-id="0523f-193">For access to more auditing approvals within Flow, enable and configure auditing in the default environment for the primary approval entities Approval, Approval Request, and Approval Response.</span></span> <span data-ttu-id="0523f-194">Las operaciones de creación, actualización y eliminación son eventos auditables para los registros de Aprobación.</span><span class="sxs-lookup"><span data-stu-id="0523f-194">Create, update, and delete operations are auditable events for Approval records.</span></span> <span data-ttu-id="0523f-195">Obtenga más información sobre [Datos de Auditoría y la actividad de usuario para la seguridad y el cumplimiento: Power Platform \| Microsoft Docs](/power-platform/admin/audit-data-user-activity).</span><span class="sxs-lookup"><span data-stu-id="0523f-195">Learn more about [Audit data and user activity for security and compliance - Power Platform \| Microsoft Docs](/power-platform/admin/audit-data-user-activity).</span></span>

<span data-ttu-id="0523f-196">Las auditorías se pueden personalizar aún más en el [Centro de seguridad y cumplimiento de Microsoft 365](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span><span class="sxs-lookup"><span data-stu-id="0523f-196">Auditing can be customized further in the [Microsoft 365 Security and Compliance Center](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span></span>

1. <span data-ttu-id="0523f-197">Para usar los informes preconfigurados, inicie sesión en Seguridad y cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0523f-197">To use the preconfigured reports, sign in to Microsoft 365 Security and Compliance.</span></span>

2. <span data-ttu-id="0523f-198">Seleccione **Búsqueda e investigación**.</span><span class="sxs-lookup"><span data-stu-id="0523f-198">Select **Search & investigation**.</span></span>

3. <span data-ttu-id="0523f-199">Busque en el registro de Auditoría y seleccione la pestaña **Actividades de Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="0523f-199">Search the Audit log and select the **Dynamics 365 activities** tab.</span></span>

<span data-ttu-id="0523f-200">Obtenga más información sobre el [Registro de actividad de aplicaciones basadas en modelos y Microsoft Dataverse: Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).</span><span class="sxs-lookup"><span data-stu-id="0523f-200">Learn more about [Microsoft Dataverse and model-driven apps activity logging - Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).</span></span>

## <a name="security"></a><span data-ttu-id="0523f-201">Seguridad</span><span class="sxs-lookup"><span data-stu-id="0523f-201">Security</span></span>

<span data-ttu-id="0523f-202">Desde la aplicación Aprobaciones de Teams, los usuarios tienen acceso para crear nuevas aprobaciones y ver las aprobaciones que han enviado y recibido.</span><span class="sxs-lookup"><span data-stu-id="0523f-202">From the Teams Approvals app, users have access to create new Approvals and view Approvals that they have sent and received.</span></span> <span data-ttu-id="0523f-203">Los usuarios no tendrán acceso a Aprobaciones creadas por otros usuarios, excepto si son respondedores o lectores de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="0523f-203">Users won't have access to Approvals that are created by others unless they're either a responder or a viewer of the request.</span></span>

> [!Note]
> <span data-ttu-id="0523f-204">A un usuario se le asigna un rol de visor de una solicitud si forma parte del chat o canal donde se creó la aprobación.</span><span class="sxs-lookup"><span data-stu-id="0523f-204">A user will be given a viewer role of a request if they are part of the chat or channel where the approval was created.</span></span> <span data-ttu-id="0523f-205">No tendrán la capacidad de realizar acciones en la solicitud si no se les ha concedido ese rol cuando se creó la aprobación.</span><span class="sxs-lookup"><span data-stu-id="0523f-205">They won't have the ability to take action on the request if they weren't given that role when the approval was created.</span></span>

## <a name="approvals-e-signature-integration"></a><span data-ttu-id="0523f-206">Integración de firmas electrónicas de aprobaciones</span><span class="sxs-lookup"><span data-stu-id="0523f-206">Approvals e-signature integration</span></span>

<span data-ttu-id="0523f-207">Las aprobaciones de firma electrónica creadas desde la aplicación Aprobaciones se almacenan en el entorno en la nube del proveedor seleccionado.</span><span class="sxs-lookup"><span data-stu-id="0523f-207">E-signature approvals created from the Approvals app are stored in the selected provider's cloud environment.</span></span> <span data-ttu-id="0523f-208">Para obtener más información sobre el almacenamiento en torno al contrato de firma electrónica, vea la documentación de almacenamiento del proveedor seleccionado.</span><span class="sxs-lookup"><span data-stu-id="0523f-208">For further information about storage around the e-signature agreement, view the selected provider's storage documentation.</span></span>

<span data-ttu-id="0523f-209">Para usar la característica de firma electrónica de la aplicación Aprobaciones, necesita los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="0523f-209">To use the Approvals app e-signature feature, you need the following items:</span></span>

- <span data-ttu-id="0523f-210">Licencia para el proveedor de firma electrónico específico que elija usar.</span><span class="sxs-lookup"><span data-stu-id="0523f-210">License for the specific e-signature provider you're choosing to use.</span></span> <span data-ttu-id="0523f-211">Para obtener una licencia para su organización, tendrá que ir al sitio del proveedor.</span><span class="sxs-lookup"><span data-stu-id="0523f-211">In order to obtain a license for your organization, you'll need to go to the provider’s site.</span></span>

<span data-ttu-id="0523f-212">Para la funcionalidad de firma electrónica Aprobaciones, los partners de firma de terceros aparecerán en la aplicación Teams aprobaciones de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0523f-212">For the Approvals e-signature functionality, third-party signature partners will appear in the Teams Approvals app by default.</span></span> <span data-ttu-id="0523f-213">Puede deshabilitar determinados proveedores de firma electrónica accediendo a la configuración de la aplicación en el Teams de administración.</span><span class="sxs-lookup"><span data-stu-id="0523f-213">You can disable specific e-signature providers by accessing app settings in the Teams admin center.</span></span>

1. <span data-ttu-id="0523f-214">En el Teams de administración, en Administrar **aplicaciones,** seleccione la aplicación Aprobaciones **y** **elija Configuración**.</span><span class="sxs-lookup"><span data-stu-id="0523f-214">In the Teams admin center, under **Manage apps**, select the **Approvals app** and choose **Settings**.</span></span>

2. <span data-ttu-id="0523f-215">Cada proveedor de firma electrónica tiene un botón de alternancia junto a él que se encuentra en la posición activa (derecha) de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0523f-215">Each e-signature provider has a toggle next to it that is in the on position (right) by default.</span></span> <span data-ttu-id="0523f-216">Deslice el botón de alternancia a la izquierda para deshabilitar un proveedor específico de firma electrónica.</span><span class="sxs-lookup"><span data-stu-id="0523f-216">Slide the toggle to the left to disable a specific e-signature provider.</span></span> <span data-ttu-id="0523f-217">Si un Teams deshabilita un proveedor, los usuarios finales no verán el proveedor al crear una aprobación.</span><span class="sxs-lookup"><span data-stu-id="0523f-217">If a Teams admin disables a provider, end users won't see the provider when creating an approval.</span></span> <span data-ttu-id="0523f-218">Los usuarios finales tampoco podrán ver las solicitudes de firma electrónica realizadas con ese proveedor.</span><span class="sxs-lookup"><span data-stu-id="0523f-218">End users will also be unable to view any e-signature requests that were made with that provider.</span></span>

<span data-ttu-id="0523f-219">Las aprobaciones de firma electrónica creadas desde la aplicación Aprobaciones se almacenan en la nube del proveedor seleccionado.</span><span class="sxs-lookup"><span data-stu-id="0523f-219">E-signature Approvals created from the Approvals App are stored in the selected provider’s cloud.</span></span> <span data-ttu-id="0523f-220">Por lo tanto, tendrá que ir al sitio del proveedor para exportar los datos sobre firmas electrónicas.</span><span class="sxs-lookup"><span data-stu-id="0523f-220">You will therefore need to go to the provider's site in order to export any data about e-signatures.</span></span> <span data-ttu-id="0523f-221">Consulte la documentación del proveedor sobre la exportación y retención de estos contratos.</span><span class="sxs-lookup"><span data-stu-id="0523f-221">Refer to the provider's documentation about export and retention of these agreements.</span></span>
