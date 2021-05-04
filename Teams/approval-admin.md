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
ms.openlocfilehash: c71f08840ffa9c41622d07376933c14a7ae6b493
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2021
ms.locfileid: "52129799"
---
# <a name="teams-approvals-app-availability"></a><span data-ttu-id="e7051-103">Disponibilidad de la aplicación Aprobaciones de Teams</span><span class="sxs-lookup"><span data-stu-id="e7051-103">Teams Approvals app availability</span></span>

<span data-ttu-id="e7051-104">La aplicación Aprobaciones está disponible como una aplicación personal para todos los usuarios de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e7051-104">The Approvals app is available as a personal app for all Microsoft Teams users.</span></span>
<span data-ttu-id="e7051-105">La aplicación Aprobaciones ofrece una forma sencilla de ejercer las auditorías, el cumplimiento, la responsabilidad y los flujos de trabajo tanto a Aprobaciones estructuradas y no estructuradas en Teams.</span><span class="sxs-lookup"><span data-stu-id="e7051-105">The Approvals app provides a simple way to bring auditing, compliance, accountability, and workflows to both structured and unstructured Approvals in Teams.</span></span>

 ![muestra la aplicación de aprobaciones](media/approvals-selection.png)

<span data-ttu-id="e7051-107">Los usuarios pueden anclar la aplicación Aprobaciones para guardarla en la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="e7051-107">Users can pin the Approvals app to save it to the menu bar.</span></span>

 ![muestra la aplicación de aprobaciones con la opción de ancla](media/approvalApp-pin.png)

<span data-ttu-id="e7051-109">La primera aprobación creada a partir de la aplicación Aprobaciones desencadenará el aprovisionamiento de la solución de aprobación en el entorno predeterminado del Servicio de datos comunes (CDS).</span><span class="sxs-lookup"><span data-stu-id="e7051-109">The first approval created from the Approvals app will trigger the provisioning of the Approval Solution in the default Common Data Service (CDS) environment.</span></span> <span data-ttu-id="e7051-110">Las aprobaciones creadas a partir de la aplicación Aprobaciones se almacenarán en el entorno de CDS predeterminado.</span><span class="sxs-lookup"><span data-stu-id="e7051-110">Approvals created from the Approvals app will be stored in the default CDS environment.</span></span>

<span data-ttu-id="e7051-111">En este artículo se describen los roles y requisitos de la aplicación Aprobaciones.</span><span class="sxs-lookup"><span data-stu-id="e7051-111">This article describes the Approvals app requirements and roles.</span></span>

> [!NOTE]
> <span data-ttu-id="e7051-112">Esta característica aún no se ha publicado para Government Community Cloud (GCC), Government Community Cloud High (GCCH) y los usuarios del Departamento de Defensa (DOD).</span><span class="sxs-lookup"><span data-stu-id="e7051-112">This feature hasn't been released to Government Community Cloud (GCC), Government Community Cloud High (GCCH), and Department of Defense (DOD) users yet.</span></span>

## <a name="required-permissions-and-licenses"></a><span data-ttu-id="e7051-113">Permisos y licencias necesarios</span><span class="sxs-lookup"><span data-stu-id="e7051-113">Required permissions and licenses</span></span>

<span data-ttu-id="e7051-114">Para usar la aplicación Aprobaciones, necesita permisos para los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="e7051-114">To use the Approvals app, you need permission for the following items:</span></span>

- <span data-ttu-id="e7051-115">Permisos para crear una base de datos de CDS de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e7051-115">Permissions to create a Microsoft CDS database.</span></span>

- <span data-ttu-id="e7051-116">Una cuenta en [flow.microsoft.com](https://flow.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="e7051-116">An account on [flow.microsoft.com](https://flow.microsoft.com/)</span></span>

- <span data-ttu-id="e7051-117">Rol de administrador en el entorno de destino.</span><span class="sxs-lookup"><span data-stu-id="e7051-117">Administrator Role in the target environment.</span></span>

- <span data-ttu-id="e7051-118">Licencia para un [Power Automate](/power-automate/get-started-approvals), un Office 365 o una Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="e7051-118">License for a [Power Automate](/power-automate/get-started-approvals), an Office 365, or a Dynamics 365.</span></span>

## <a name="storage-with-cds"></a><span data-ttu-id="e7051-119">Almacenamiento con CDS</span><span class="sxs-lookup"><span data-stu-id="e7051-119">Storage with CDS</span></span>

<span data-ttu-id="e7051-120">El modelo de datos común (CDM) es el lenguaje de datos compartido que usan las aplicaciones empresariales y de análisis en el CDS.</span><span class="sxs-lookup"><span data-stu-id="e7051-120">The Common Data Model (CDM) is the shared data language used by business and analytical applications in the CDS.</span></span> <span data-ttu-id="e7051-121">Consiste en un conjunto de esquemas de datos estandarizados y extensibles publicados por Microsoft y nuestros asociados, que permiten la coherencia de los datos y su significado en aplicaciones y procesos empresariales.</span><span class="sxs-lookup"><span data-stu-id="e7051-121">It consists of a set of a standardized, extensible data schemas published by Microsoft and our partners that enables consistency of data and its meaning across applications and business processes.</span></span> <span data-ttu-id="e7051-122">Obtenga más información sobre los [Modelos de datos común de la plataforma de Microsoft Power](/power-automate/get-started-approvals).</span><span class="sxs-lookup"><span data-stu-id="e7051-122">Learn more about the [Common Data Model of the Microsoft Power Platform](/power-automate/get-started-approvals).</span></span>

<span data-ttu-id="e7051-123">Obtenga más información sobre el [flujo de trabajo de Aprobación](/power-automate/modern-approvals).</span><span class="sxs-lookup"><span data-stu-id="e7051-123">Learn more about the [Approval workflow](/power-automate/modern-approvals).</span></span>

## <a name="approvals-teams-app-permissions"></a><span data-ttu-id="e7051-124">Permisos de aplicación de Approvals Teams</span><span class="sxs-lookup"><span data-stu-id="e7051-124">Approvals Teams app permissions</span></span>

<span data-ttu-id="e7051-125">La aplicación Approvals Teams le permite acceder a las características siguientes:</span><span class="sxs-lookup"><span data-stu-id="e7051-125">The Approvals Teams app lets you access the following features:</span></span>

- <span data-ttu-id="e7051-126">Recibir los mensajes y los datos que usted solicite.</span><span class="sxs-lookup"><span data-stu-id="e7051-126">Receive messages and data that you provide to it.</span></span>

- <span data-ttu-id="e7051-127">Envío de mensajes y notificaciones.</span><span class="sxs-lookup"><span data-stu-id="e7051-127">Send you messages and notifications.</span></span>

- <span data-ttu-id="e7051-128">Mostar cuadros de diálogo y aplicaciones personales sin un encabezado proporcionado por Teams.</span><span class="sxs-lookup"><span data-stu-id="e7051-128">Render personal apps and dialogs without a Teams-provided header.</span></span>

- <span data-ttu-id="e7051-129">Obtenga acceso a la información del perfil, como su nombre, dirección de correo electrónico, nombre de la empresa e idioma de preferencia.</span><span class="sxs-lookup"><span data-stu-id="e7051-129">Access your profile information such as your name, email address, company name, and preferred language.</span></span>

- <span data-ttu-id="e7051-130">Recibir mensajes y datos que los miembros del equipo le proporcionen en un canal.</span><span class="sxs-lookup"><span data-stu-id="e7051-130">Receive messages and data that team members provide to it in a channel.</span></span>

- <span data-ttu-id="e7051-131">Enviar mensajes y notificaciones en un canal.</span><span class="sxs-lookup"><span data-stu-id="e7051-131">Send messages and notifications in a channel.</span></span>

- <span data-ttu-id="e7051-132">Obtener acceso a la información del equipo:</span><span class="sxs-lookup"><span data-stu-id="e7051-132">Access your team's information:</span></span>
  - <span data-ttu-id="e7051-133">nombre del equipo</span><span class="sxs-lookup"><span data-stu-id="e7051-133">team name</span></span>
  - <span data-ttu-id="e7051-134">lista de canales</span><span class="sxs-lookup"><span data-stu-id="e7051-134">channel list</span></span>
  - <span data-ttu-id="e7051-135">lista (nombres y direcciones de correo electrónico de los miembros del equipo).</span><span class="sxs-lookup"><span data-stu-id="e7051-135">roster (team member's names and email addresses).</span></span>

- <span data-ttu-id="e7051-136">Use la información del equipo para ponerse en contacto con ellos.</span><span class="sxs-lookup"><span data-stu-id="e7051-136">Use the team's information to contact them.</span></span>

## <a name="disable-the-approvals-app"></a><span data-ttu-id="e7051-137">Administrar la aplicación Aprobaciones</span><span class="sxs-lookup"><span data-stu-id="e7051-137">Disable the Approvals app</span></span>

<span data-ttu-id="e7051-138">La aplicación Aprobaciones está disponible de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e7051-138">The Approvals app is available by default.</span></span> <span data-ttu-id="e7051-139">Puede deshabilitar la aplicación en el Centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e7051-139">You can disable the app in the Teams admin center.</span></span>

  1. <span data-ttu-id="e7051-140">Inicie la sesión en el Centro de administración de Teams</span><span class="sxs-lookup"><span data-stu-id="e7051-140">Sign in to the Teams admin center.</span></span>

  2. <span data-ttu-id="e7051-141">Expanda **aplicación de Teams** y seleccione **Administrar aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="e7051-141">Expand **Teams apps** and select **Manage apps**.</span></span>

  3. <span data-ttu-id="e7051-142">Busque la aplicación Aprobaciones.</span><span class="sxs-lookup"><span data-stu-id="e7051-142">Search for the Approvals app.</span></span>

     ![muestra la navegación del Centro de administración donde se muestra Aplicaciones de Microsoft Teams > Administrar aplicaciones de forma resaltada](media/manage-approval-apps.png)

  4. <span data-ttu-id="e7051-144">Seleccione Aprobaciones.</span><span class="sxs-lookup"><span data-stu-id="e7051-144">Select Approvals.</span></span>

  5. <span data-ttu-id="e7051-145">Seleccione el botón de alternancia para deshabilitar la aplicación para su organización.</span><span class="sxs-lookup"><span data-stu-id="e7051-145">Select the toggle to disable the app for your organization.</span></span>

     ![muestra los detalles de la aplicación Aprobaciones](media/approvals-details.png)

## <a name="retention-policy"></a><span data-ttu-id="e7051-147">Directiva de retención</span><span class="sxs-lookup"><span data-stu-id="e7051-147">Retention policy</span></span>

<span data-ttu-id="e7051-148">Las aprobaciones creadas a partir de la aplicación de Aprobaciones se almacenan en el entorno de CDS predeterminado, que no admite copias de seguridad en este momento.</span><span class="sxs-lookup"><span data-stu-id="e7051-148">Approvals created from the Approvals App are stored in the default CDS environment, which doesn’t support backups at this time.</span></span> <span data-ttu-id="e7051-149">Obtenga más información sobre cómo [Respaldar y restaurar entornos - Power Platform \| Microsoft Docs](/power-platform/admin/backup-restore-environments).</span><span class="sxs-lookup"><span data-stu-id="e7051-149">Learn more about how to [Back up and restore environments - Power Platform \| Microsoft Docs](/power-platform/admin/backup-restore-environments).</span></span>

## <a name="auditing"></a><span data-ttu-id="e7051-150">Auditoría</span><span class="sxs-lookup"><span data-stu-id="e7051-150">Auditing</span></span>

<span data-ttu-id="e7051-151">La aplicación Aprobaciones registra eventos de auditoría del Centro de seguridad y cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e7051-151">The Approvals App logs audit events within the Microsoft 365 Security and Compliance Center.</span></span> <span data-ttu-id="e7051-152">Puede ver el registro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="e7051-152">You can view the audit log.</span></span>

1. <span data-ttu-id="e7051-153">Vaya al sitio de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e7051-153">Go to the Microsoft 365 Compliance Site.</span></span>

2. <span data-ttu-id="e7051-154">Seleccione la sección **Auditoría**.</span><span class="sxs-lookup"><span data-stu-id="e7051-154">Select the **Audit** section.</span></span>

3. <span data-ttu-id="e7051-155">Buscar actividades en las actividades **Aprobación de Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="e7051-155">Search for activities under **Microsoft Teams approvals activities**.</span></span>

<span data-ttu-id="e7051-156">Puede buscar las actividades siguientes:</span><span class="sxs-lookup"><span data-stu-id="e7051-156">You can search for the following activities:</span></span>

- <span data-ttu-id="e7051-157">Crear una nueva solicitud de aprobación</span><span class="sxs-lookup"><span data-stu-id="e7051-157">Create new approval request</span></span>

- <span data-ttu-id="e7051-158">Ver detalles de la solicitud de aprobación</span><span class="sxs-lookup"><span data-stu-id="e7051-158">View approval request details</span></span>

- <span data-ttu-id="e7051-159">Solicitud de aprobación aprobada</span><span class="sxs-lookup"><span data-stu-id="e7051-159">Approved approval request</span></span>

- <span data-ttu-id="e7051-160">Solicitud de aprobación rechazada</span><span class="sxs-lookup"><span data-stu-id="e7051-160">Rejected approval request</span></span>

- <span data-ttu-id="e7051-161">Solicitud de aprobación cancelada</span><span class="sxs-lookup"><span data-stu-id="e7051-161">Canceled approval request</span></span>

- <span data-ttu-id="e7051-162">Solicitud de aprobación compartida</span><span class="sxs-lookup"><span data-stu-id="e7051-162">Shared approval request</span></span>

- <span data-ttu-id="e7051-163">Archivo adjunto a solicitud de aprobación</span><span class="sxs-lookup"><span data-stu-id="e7051-163">File attached to approval request</span></span>

- <span data-ttu-id="e7051-164">Solicitud de aprobación reasignada</span><span class="sxs-lookup"><span data-stu-id="e7051-164">Reassigned approval request</span></span>

- <span data-ttu-id="e7051-165">Firma electrónica agregada a la solicitud de aprobación</span><span class="sxs-lookup"><span data-stu-id="e7051-165">Added e-signature to approval request</span></span>

- <span data-ttu-id="e7051-166">Detalles de solicitud de firma electrónica vistas</span><span class="sxs-lookup"><span data-stu-id="e7051-166">Viewed e-signature request details</span></span>

- <span data-ttu-id="e7051-167">Solicitud de firma electrónica revisada</span><span class="sxs-lookup"><span data-stu-id="e7051-167">Reviewed e-signature request</span></span>

- <span data-ttu-id="e7051-168">Solicitud de firma electrónica cancelada</span><span class="sxs-lookup"><span data-stu-id="e7051-168">Canceled e-signature request</span></span>

<span data-ttu-id="e7051-169">Para tener acceso a más aprobaciones de auditoría en Flujo, habilite y configure la auditoría en el entorno predeterminado para las entidades de aprobación primaria Aprobación, solicitud de aprobación y respuesta de aprobación.</span><span class="sxs-lookup"><span data-stu-id="e7051-169">For access to more auditing approvals within Flow, enable and configure auditing in the default environment for the primary approval entities Approval, Approval Request, and Approval Response.</span></span> <span data-ttu-id="e7051-170">Las operaciones de creación, actualización y eliminación son eventos auditables para los registros de Aprobación.</span><span class="sxs-lookup"><span data-stu-id="e7051-170">Create, update, and delete operations are auditable events for Approval records.</span></span> <span data-ttu-id="e7051-171">Obtenga más información sobre [Datos de Auditoría y la actividad de usuario para la seguridad y el cumplimiento: Power Platform \| Microsoft Docs](/power-platform/admin/audit-data-user-activity).</span><span class="sxs-lookup"><span data-stu-id="e7051-171">Learn more about [Audit data and user activity for security and compliance - Power Platform \| Microsoft Docs](/power-platform/admin/audit-data-user-activity).</span></span>

<span data-ttu-id="e7051-172">Las auditorías se pueden personalizar aún más en el [Centro de seguridad y cumplimiento de Microsoft 365](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span><span class="sxs-lookup"><span data-stu-id="e7051-172">Auditing can be customized further in the [Microsoft 365 Security and Compliance Center](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span></span>

1. <span data-ttu-id="e7051-173">Para usar los informes preconfigurados, inicie sesión en Seguridad y cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e7051-173">To use the preconfigured reports, sign in to Microsoft 365 Security and Compliance.</span></span>

2. <span data-ttu-id="e7051-174">Seleccione **Búsqueda e investigación**.</span><span class="sxs-lookup"><span data-stu-id="e7051-174">Select **Search & investigation**.</span></span>

3. <span data-ttu-id="e7051-175">Busque en el registro de Auditoría y seleccione la pestaña **Actividades de Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="e7051-175">Search the Audit log and select the **Dynamics 365 activities** tab.</span></span>

<span data-ttu-id="e7051-176">Obtenga más información sobre el [Registro de actividad de aplicaciones basadas en modelos y Microsoft Dataverse: Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).</span><span class="sxs-lookup"><span data-stu-id="e7051-176">Learn more about [Microsoft Dataverse and model-driven apps activity logging - Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).</span></span>

## <a name="security"></a><span data-ttu-id="e7051-177">Seguridad</span><span class="sxs-lookup"><span data-stu-id="e7051-177">Security</span></span>

<span data-ttu-id="e7051-178">Desde la aplicación Aprobaciones de Teams, los usuarios tienen acceso para crear nuevas aprobaciones y ver las aprobaciones que han enviado y recibido.</span><span class="sxs-lookup"><span data-stu-id="e7051-178">From the Teams Approvals app, users have access to create new Approvals and view Approvals that they have sent and received.</span></span> <span data-ttu-id="e7051-179">Los usuarios no tendrán acceso a Aprobaciones creadas por otros usuarios, excepto si son respondedores o lectores de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="e7051-179">Users won't have access to Approvals that are created by others unless they're either a responder or a viewer of the request.</span></span>

> [!Note]
> <span data-ttu-id="e7051-180">A un usuario se le asigna un rol de visor de una solicitud si forma parte del chat o canal donde se creó la aprobación.</span><span class="sxs-lookup"><span data-stu-id="e7051-180">A user will be given a viewer role of a request if they are part of the chat or channel where the approval was created.</span></span> <span data-ttu-id="e7051-181">No tendrán la capacidad de realizar acciones en la solicitud si no se les ha concedido ese rol cuando se creó la aprobación.</span><span class="sxs-lookup"><span data-stu-id="e7051-181">They won't have the ability to take action on the request if they weren't given that role when the approval was created.</span></span>

## <a name="approvals-e-signature-integration"></a><span data-ttu-id="e7051-182">Integración de firmas electrónicas de aprobaciones</span><span class="sxs-lookup"><span data-stu-id="e7051-182">Approvals e-signature integration</span></span>

<span data-ttu-id="e7051-183">Las aprobaciones de firma electrónica creadas desde la aplicación Aprobaciones se almacenan en el entorno en la nube del proveedor seleccionado.</span><span class="sxs-lookup"><span data-stu-id="e7051-183">E-signature approvals created from the Approvals app are stored in the selected provider's cloud environment.</span></span> <span data-ttu-id="e7051-184">Para obtener más información sobre el almacenamiento en torno al contrato de firma electrónica, vea la documentación de almacenamiento del proveedor seleccionado.</span><span class="sxs-lookup"><span data-stu-id="e7051-184">For further information about storage around the e-signature agreement, view the selected provider's storage documentation.</span></span>

<span data-ttu-id="e7051-185">Para usar la característica de firma electrónica de la aplicación Aprobaciones, necesita los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="e7051-185">To use the Approvals app e-signature feature, you need the following items:</span></span>

- <span data-ttu-id="e7051-186">Licencia para el proveedor de firma electrónico específico que elija usar.</span><span class="sxs-lookup"><span data-stu-id="e7051-186">License for the specific e-signature provider you're choosing to use.</span></span> <span data-ttu-id="e7051-187">Para obtener una licencia para su organización, tendrá que ir al sitio del proveedor.</span><span class="sxs-lookup"><span data-stu-id="e7051-187">In order to obtain a license for your organization, you'll need to go to the provider’s site.</span></span>

<span data-ttu-id="e7051-188">Para la funcionalidad de firma electrónica Aprobaciones, los partners de firma de terceros aparecerán en la aplicación Teams aprobaciones de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e7051-188">For the Approvals e-signature functionality, third-party signature partners will appear in the Teams Approvals app by default.</span></span> <span data-ttu-id="e7051-189">Puede deshabilitar determinados proveedores de firma electrónica accediendo a la configuración de la aplicación en el Teams de administración.</span><span class="sxs-lookup"><span data-stu-id="e7051-189">You can disable specific e-signature providers by accessing app settings in the Teams admin center.</span></span>

1. <span data-ttu-id="e7051-190">En el Teams de administración, en Administrar **aplicaciones,** seleccione la aplicación Aprobaciones **y** **elija Configuración**.</span><span class="sxs-lookup"><span data-stu-id="e7051-190">In the Teams admin center, under **Manage apps**, select the **Approvals app** and choose **Settings**.</span></span>

2. <span data-ttu-id="e7051-191">Cada proveedor de firma electrónica tiene un botón de alternancia junto a él que se encuentra en la posición activa (derecha) de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e7051-191">Each e-signature provider has a toggle next to it that is in the on position (right) by default.</span></span> <span data-ttu-id="e7051-192">Deslice el botón de alternancia a la izquierda para deshabilitar un proveedor específico de firma electrónica.</span><span class="sxs-lookup"><span data-stu-id="e7051-192">Slide the toggle to the left to disable a specific e-signature provider.</span></span> <span data-ttu-id="e7051-193">Si un Teams deshabilita un proveedor, los usuarios finales no verán el proveedor al crear una aprobación.</span><span class="sxs-lookup"><span data-stu-id="e7051-193">If a Teams admin disables a provider, end users won't see the provider when creating an approval.</span></span> <span data-ttu-id="e7051-194">Los usuarios finales tampoco podrán ver las solicitudes de firma electrónica realizadas con ese proveedor.</span><span class="sxs-lookup"><span data-stu-id="e7051-194">End users will also be unable to view any e-signature requests that were made with that provider.</span></span>

<span data-ttu-id="e7051-195">Las aprobaciones de firma electrónica creadas desde la aplicación Aprobaciones se almacenan en la nube del proveedor seleccionado.</span><span class="sxs-lookup"><span data-stu-id="e7051-195">E-signature Approvals created from the Approvals App are stored in the selected provider’s cloud.</span></span> <span data-ttu-id="e7051-196">Por lo tanto, tendrá que ir al sitio del proveedor para exportar los datos sobre firmas electrónicas.</span><span class="sxs-lookup"><span data-stu-id="e7051-196">You will therefore need to go to the provider's site in order to export any data about e-signatures.</span></span> <span data-ttu-id="e7051-197">Consulte la documentación del proveedor sobre la exportación y retención de estos contratos.</span><span class="sxs-lookup"><span data-stu-id="e7051-197">Refer to the provider's documentation about export and retention of these agreements.</span></span>
