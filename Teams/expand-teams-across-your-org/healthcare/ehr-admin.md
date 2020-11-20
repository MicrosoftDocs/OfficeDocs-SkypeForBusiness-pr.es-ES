---
title: Teams para visitas virtuales
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Usar Microsoft Teams para configurar el sistema de visitas virtuales
ms.openlocfilehash: 808d957cd86273852e7c2c98ec223b1988e5bd0d
ms.sourcegitcommit: cbf87fc914a19088af8ec08fb0976db9f838a45d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/19/2020
ms.locfileid: "49355970"
---
# <a name="virtual-visits-with-teams---integration-into-ehr"></a><span data-ttu-id="8d7be-103">Visitas virtuales con Teams: integración en EHR</span><span class="sxs-lookup"><span data-stu-id="8d7be-103">Virtual visits with Teams - Integration into EHR</span></span>

<span data-ttu-id="8d7be-104">El conector de mantenimiento Electrónico de Microsoft Teams (EHR) facilita el inicio de una visita de pacientes virtuales o la consulta con otro proveedor en Teams directamente desde el sistema HCI.</span><span class="sxs-lookup"><span data-stu-id="8d7be-104">Microsoft Teams Electronic Health Record (EHR) Connector makes it easy for clinicians to launch a virtual patient visit or consultation with another provider in Teams directly from the EHR system.</span></span> <span data-ttu-id="8d7be-105">Basado en la nube de Microsoft 365, Microsoft Teams permite una colaboración y una comunicación segura y sencilla con las herramientas de chat, vídeo, voz y atención médica en un único Hub que admite el cumplimiento de la normativa HIPAA, la certificación de alta tecnología y más.</span><span class="sxs-lookup"><span data-stu-id="8d7be-105">Built on the Microsoft 365 cloud, Microsoft Teams enables simple, secure collaboration and communication with chat, video, voice, and healthcare tools in a single hub that supports compliance with HIPAA, HITECH certification, and more.</span></span>

<span data-ttu-id="8d7be-106">La plataforma de comunicación y colaboración de Teams facilita a los médicos el corte en el desorden de los sistemas fragmentados para que puedan gastar tiempo proporcionando la mejor atención posible.</span><span class="sxs-lookup"><span data-stu-id="8d7be-106">The communication and collaboration platform of Teams makes it easy for clinicians to cut through the clutter of fragmented systems so they can spend time providing the best possible care.</span></span> <span data-ttu-id="8d7be-107">El conector de estado electrónico (EHR) de Microsoft Teams puede:</span><span class="sxs-lookup"><span data-stu-id="8d7be-107">Microsoft Teams Electronic Health Record (EHR) Connector can:</span></span>

- <span data-ttu-id="8d7be-108">Iniciar visitas virtuales de equipos desde portales de proveedores y de pacientes.</span><span class="sxs-lookup"><span data-stu-id="8d7be-108">Launch Teams virtual visits from both provider and patient portals.</span></span>

- <span data-ttu-id="8d7be-109">Vuelva a escribir los metadatos de EHR en los eventos Connect y Disconnect para habilitar la auditoría automática y la conservación de registros.</span><span class="sxs-lookup"><span data-stu-id="8d7be-109">Write back into EHR metadata on connect and disconnect events to enable automatic auditing and record keeping.</span></span>

- <span data-ttu-id="8d7be-110">Integrarse en flujos de trabajo médicos y pacientes existentes, a la vez que permite que usen Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8d7be-110">Integrate into existing clinician and patient workflows while allowing them to use Microsoft Teams.</span></span>

  <span data-ttu-id="8d7be-111">Vea el vídeo sobre cómo administrar las visitas virtuales desde el portal de EHR.</span><span class="sxs-lookup"><span data-stu-id="8d7be-111">Watch the video of How to manage virtual visits from the EHR portal.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

## <a name="before-you-begin"></a><span data-ttu-id="8d7be-112">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="8d7be-112">Before you begin</span></span>

<span data-ttu-id="8d7be-113">Para poder integrar el conector de EHR, debe asegurarse de que tiene los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="8d7be-113">You’ll need to make sure you have the following prerequisites before you can integrate the EHR connector:</span></span>

- <span data-ttu-id="8d7be-114">Suscripción activa a la nube de Microsoft para el cuidado de la salud o suscripción a la oferta independiente del conector de Microsoft Teams HCI.</span><span class="sxs-lookup"><span data-stu-id="8d7be-114">Active subscription to Microsoft Cloud for Healthcare or subscription to Microsoft Teams EHR Connector standalone offer.</span></span>

- <span data-ttu-id="8d7be-115">Los usuarios deben tener una licencia adecuada de Microsoft 365 o de Office 365 que incluya reuniones de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8d7be-115">Users must have an appropriate Microsoft 365 or Office 365 license that includes Microsoft Teams meetings.</span></span>

- <span data-ttu-id="8d7be-116">Microsoft Teams debe adoptarse y utilizarse dentro de la organización.</span><span class="sxs-lookup"><span data-stu-id="8d7be-116">Microsoft Teams should be adopted and used inside the organization.</span></span>

- <span data-ttu-id="8d7be-117">Las organizaciones deben tener una versión de noviembre de 2018 o posterior.</span><span class="sxs-lookup"><span data-stu-id="8d7be-117">Organizations must have with Epic version November 2018 or later.</span></span>

- <span data-ttu-id="8d7be-118">Sus sistemas deben cumplir con todos los [requisitos previos de software y navegador](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span><span class="sxs-lookup"><span data-stu-id="8d7be-118">Your systems must meet all [software and browser prerequisites](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span></span>

<span data-ttu-id="8d7be-119">También necesitará información de las siguientes personas de su organización:</span><span class="sxs-lookup"><span data-stu-id="8d7be-119">You’ll also need information from the following people in your organization:</span></span>

- <span data-ttu-id="8d7be-120">Administrador de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8d7be-120">Microsoft 365 administrator</span></span>

- <span data-ttu-id="8d7be-121">Administrador de la epopeya</span><span class="sxs-lookup"><span data-stu-id="8d7be-121">Epic administrator</span></span>

> [!Note]
> <span data-ttu-id="8d7be-122">Solicite a su administrador de Epic que proporcione la guía de integración de TeleHealth Epic-Microsoft Teams disponible en el Marketplace de la epopeya.</span><span class="sxs-lookup"><span data-stu-id="8d7be-122">Request your Epic admin to provide the Epic-Microsoft Teams Telehealth Integration Guide available in the Epic marketplace.</span></span>

## <a name="connector-setup"></a><span data-ttu-id="8d7be-123">Configuración del conector</span><span class="sxs-lookup"><span data-stu-id="8d7be-123">Connector setup</span></span>

<span data-ttu-id="8d7be-124">La configuración del conector requiere que:</span><span class="sxs-lookup"><span data-stu-id="8d7be-124">The connector setup requires that you:</span></span>

- [<span data-ttu-id="8d7be-125">Iniciar el portal de configuración del conector de EHR</span><span class="sxs-lookup"><span data-stu-id="8d7be-125">Launch the EHR Connector configuration portal</span></span>](ehr-admin.md#launch-the-ehr-connector-configuration-portal)
- [<span data-ttu-id="8d7be-126">Configurar información de la organización del proveedor</span><span class="sxs-lookup"><span data-stu-id="8d7be-126">Configure provider organization information</span></span>](ehr-admin.md#configure-provider-organization-information)
- [<span data-ttu-id="8d7be-127">Comprobar y aprobar la configuración</span><span class="sxs-lookup"><span data-stu-id="8d7be-127">Verify and approve the configuration</span></span>](ehr-admin.md#verify-and-approve-the-configuration)
- [<span data-ttu-id="8d7be-128">Revisar y finalizar la configuración</span><span class="sxs-lookup"><span data-stu-id="8d7be-128">Review and finish the configuration</span></span>](ehr-admin.md#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>[<span data-ttu-id="8d7be-129">Iniciar el portal de configuración del conector de EHR</span><span class="sxs-lookup"><span data-stu-id="8d7be-129">Launch the EHR Connector configuration portal</span></span>](#launch-the-ehr-connector-configuration-portal)

<span data-ttu-id="8d7be-130">Para configurar su organización de salud para iniciar visitas virtuales con Microsoft Teams, inicie el portal de configuración del conector de EHR.</span><span class="sxs-lookup"><span data-stu-id="8d7be-130">Configuring your healthcare organization to launch virtual visits with Microsoft Teams starts by launching the EHR Connector configuration portal.</span></span> <span data-ttu-id="8d7be-131">Use la dirección URL de prueba para configurar el conector para el entorno de prueba de Epic.</span><span class="sxs-lookup"><span data-stu-id="8d7be-131">Use the test URL to configure the connector for your Epic test environment.</span></span> <span data-ttu-id="8d7be-132">Use la dirección URL de producción cuando esté listo para habilitar el entorno de producción de la epopeya.</span><span class="sxs-lookup"><span data-stu-id="8d7be-132">Use the production URL when you're ready to enable your Epic production environment.</span></span>
  
- <span data-ttu-id="8d7be-133">Entorno de prueba [https://ehrconnector-ppe.teams.microsoft.com](https://ehrconnector-ppe.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="8d7be-133">Test environment [https://ehrconnector-ppe.teams.microsoft.com](https://ehrconnector-ppe.teams.microsoft.com)</span></span>
- <span data-ttu-id="8d7be-134">Entorno de producción [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="8d7be-134">Production environment [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span></span>

<span data-ttu-id="8d7be-135">El administrador de Microsoft 365 administrador y Epic de la organización debe completar la información y los pasos de integración en el portal de configuración.</span><span class="sxs-lookup"><span data-stu-id="8d7be-135">The Microsoft 365 admin and Epic admin from your organization must complete the information and integration steps in the configuration portal.</span></span> <span data-ttu-id="8d7be-136">Para conocer los pasos de configuración de la epopeya, póngase en contacto con el recurso Epic asignado a su organización.</span><span class="sxs-lookup"><span data-stu-id="8d7be-136">For Epic configuration steps, contact the Epic resource assigned to your organization.</span></span>

### <a name="configure-provider-organization-information"></a>[<span data-ttu-id="8d7be-137">Configurar información de la organización del proveedor</span><span class="sxs-lookup"><span data-stu-id="8d7be-137">Configure provider organization information</span></span>](#configure-provider-organization-information)

<span data-ttu-id="8d7be-138">Este paso debe completarse con el administrador de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8d7be-138">This step is to be completed by the Microsoft 365 administrator.</span></span> <span data-ttu-id="8d7be-139">El administrador de Microsoft 365 debe iniciar el portal de configuración del conector e iniciar sesión con las credenciales de Microsoft para iniciar el proceso de configuración.</span><span class="sxs-lookup"><span data-stu-id="8d7be-139">The Microsoft 365 administrator must launch the connector configuration portal and sign in with Microsoft credentials to start the configuration process.</span></span>

<span data-ttu-id="8d7be-140">Para completar este paso, el administrador de Microsoft 365 debe recibir una dirección URL base válida de interoperabilidad de mantenimiento rápido (FHIR) del administrador de Microsoft 365 y el nombre de usuario del administrador de la epopeya que aprobará la configuración.</span><span class="sxs-lookup"><span data-stu-id="8d7be-140">To complete this step, the Microsoft 365 administrator must receive a valid Fast Health Interoperability Resources (FHIR) base URL from your Microsoft 365 administrator and the username of the Epic administrator who will be approving the configuration.</span></span> <span data-ttu-id="8d7be-141">El administrador de Microsoft 365 debe iniciar la página de configuración del conector e iniciar sesión con las credenciales de Microsoft para iniciar el proceso de configuración.</span><span class="sxs-lookup"><span data-stu-id="8d7be-141">The Microsoft 365 administrator must launch the connector configuration page and sign in with Microsoft credentials to start the configuration process.</span></span>

- <span data-ttu-id="8d7be-142">La dirección URL base de FHIR es una dirección estática correspondiente a su extremo de la API de FHIR de servidor.</span><span class="sxs-lookup"><span data-stu-id="8d7be-142">The FHIR base URL is a static address corresponding to your server FHIR API endpoint.</span></span> <span data-ttu-id="8d7be-143">Una dirección URL de ejemplo es `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST` .</span><span class="sxs-lookup"><span data-stu-id="8d7be-143">An example URL is `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.</span></span>

- <span data-ttu-id="8d7be-144">Nombre del aprobador de configuración es el nombre del administrador del sistema Epic que será responsable de aprobar la configuración.</span><span class="sxs-lookup"><span data-stu-id="8d7be-144">Configuration approver name is the name of the Epic system administrator who will be responsible for approving the configuration.</span></span>

  ![El nombre del aprobador de configuración se selecciona de una lista en el conector HCI.](../../media/ehc-provider-1.png)

### <a name="verify-and-approve-the-configuration"></a>[<span data-ttu-id="8d7be-146">Comprobar y aprobar la configuración</span><span class="sxs-lookup"><span data-stu-id="8d7be-146">Verify and approve the configuration</span></span>](#verify-and-approve-the-configuration)

<span data-ttu-id="8d7be-147">El administrador de la epopeya de su organización de cuidado de la salud que se agregó como aprobador debe usar ahora la misma URL de conectores de EHR del paso anterior para iniciar sesión con sus credenciales de 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8d7be-147">The Epic administrator for your healthcare organization who was added as an approver must now use the same EHR Connector URL from the previous step to sign in using their Microsoft 365 credentials.</span></span> <span data-ttu-id="8d7be-148">Después de una validación correcta, se le solicitará al aprobador que inicie sesión con sus credenciales de la epopeya para validar la organización de la epopeya.</span><span class="sxs-lookup"><span data-stu-id="8d7be-148">After successful validation, the approver is going to be asked to sign in using their Epic credentials to validate the Epic organization.</span></span>

> [!Note]
> <span data-ttu-id="8d7be-149">El administrador de Microsoft 365 admin y Epic puede ser la misma persona.</span><span class="sxs-lookup"><span data-stu-id="8d7be-149">The Microsoft 365 admin and Epic admin in your organizations can be the same person.</span></span> <span data-ttu-id="8d7be-150">En ese caso, agregue su propio nombre de usuario como aprobador en el primer paso.</span><span class="sxs-lookup"><span data-stu-id="8d7be-150">In that case, add your own username as approver in the first step.</span></span> <span data-ttu-id="8d7be-151">Seguirá necesitando iniciar sesión en Epic para validar el acceso.</span><span class="sxs-lookup"><span data-stu-id="8d7be-151">You'll still need to sign in to Epic to validate your access.</span></span> <span data-ttu-id="8d7be-152">El inicio de sesión de Epic solo se usa para validar la dirección URL base de FHIR.</span><span class="sxs-lookup"><span data-stu-id="8d7be-152">The Epic sign in is only used to validate your FHIR base URL.</span></span> <span data-ttu-id="8d7be-153">Microsoft no almacenará credenciales ni accederá a datos de EHR con este inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="8d7be-153">Microsoft will not store credentials or access EHR data with this sign in.</span></span>

  ![Comprobar y aprobar la configuración de credenciales.](../../media/ehc-provider-2.png)

<span data-ttu-id="8d7be-155">Después de un inicio de sesión de la epopeya, el administrador de la Epic **debe** aprobar la configuración.</span><span class="sxs-lookup"><span data-stu-id="8d7be-155">After a successful Epic sign in, the Epic administrator **must** approve the configuration.</span></span> <span data-ttu-id="8d7be-156">Si la configuración no es correcta, el administrador de Microsoft 365 tendrá la capacidad de modificar las configuraciones originales iniciando sesión en el portal de conector de Microsoft EHR.</span><span class="sxs-lookup"><span data-stu-id="8d7be-156">If the configuration isn't correct, the Microsoft 365 admin will have the ability to modify the original configurations by signing in to the Microsoft EHR Connector portal again.</span></span>

![Confirme que el conector HCI está configurado y opción para cambiar la configuración.](../../media/ehc-approve-3.png)

### <a name="review-and-finish-the-configuration"></a>[<span data-ttu-id="8d7be-158">Revisar y finalizar la configuración</span><span class="sxs-lookup"><span data-stu-id="8d7be-158">Review and finish the configuration</span></span>](#review-and-finish-the-configuration)

<span data-ttu-id="8d7be-159">Cuando el administrador de la epopeya apruebe la información de configuración, se le presentarán los registros de integración para el lanzamiento de pacientes y proveedores.</span><span class="sxs-lookup"><span data-stu-id="8d7be-159">When the configuration information is approved by the Epic administrator, you'll be presented with integration records for patient and provider launch.</span></span> <span data-ttu-id="8d7be-160">Estos registros son necesarios para completar la configuración de la visita virtual en Epic.</span><span class="sxs-lookup"><span data-stu-id="8d7be-160">These records are necessary to complete the virtual visit configuration in Epic.</span></span> <span data-ttu-id="8d7be-161">Para obtener más información, consulta la guía de integración de TeleHealth de Epic-Microsofts Teams.</span><span class="sxs-lookup"><span data-stu-id="8d7be-161">Refer to the Epic-Microsoft Teams Telehealth Integration guide for more details.</span></span>

> [!Note]  
> <span data-ttu-id="8d7be-162">En cualquier momento, el administrador de Microsoft 365 o Epic puede iniciar sesión en el portal de configuración para ver los registros de integración y modificar la configuración de la organización, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="8d7be-162">At any time the Microsoft 365 or Epic administrator can sign in to the configuration portal to view integration records and modify organization configuration, if needed.</span></span>

![Se muestra la información de integración.](../../media/ehc-final-config-4.png)

## <a name="launch-teams-virtual-visits"></a><span data-ttu-id="8d7be-164">Iniciar visitas virtuales a equipos</span><span class="sxs-lookup"><span data-stu-id="8d7be-164">Launch Teams virtual visits</span></span>

<span data-ttu-id="8d7be-165">Después de completar los pasos del conector HCI y la configuración de la epopeya, su organización está preparada para admitir las visitas de video con Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8d7be-165">After completing the EHR Connector steps and Epic configuration, your organization is ready to support video visits with Microsoft Teams.</span></span>

### <a name="virtual-visit-prerequisites"></a><span data-ttu-id="8d7be-166">Requisitos previos de la visita virtual</span><span class="sxs-lookup"><span data-stu-id="8d7be-166">Virtual visit prerequisites</span></span>

- <span data-ttu-id="8d7be-167">Sus sistemas deben cumplir con todos los [requisitos previos de software y navegador](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span><span class="sxs-lookup"><span data-stu-id="8d7be-167">Your systems must meet all [software and browser prerequisites](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span></span>

- <span data-ttu-id="8d7be-168">La organización de cuidado de la salud debe haber completado la configuración entre la organización de la epopeya y la organización de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8d7be-168">Healthcare organization must have completed the setup between the Epic organization and Microsoft 365 organization.</span></span>

### <a name="provider-experience"></a><span data-ttu-id="8d7be-169">Experiencia de proveedor</span><span class="sxs-lookup"><span data-stu-id="8d7be-169">Provider experience</span></span>

<span data-ttu-id="8d7be-170">Los proveedores de asistencia sanitaria de su organización también pueden unirse a visitas virtuales con Microsoft Teams desde sus aplicaciones de proveedor EPIC (hiperespacio, Haiku, canto).</span><span class="sxs-lookup"><span data-stu-id="8d7be-170">Healthcare providers from your organization can also join virtual visits with Microsoft Teams from their Epic provider applications (Hyperspace, Haiku, Canto).</span></span> <span data-ttu-id="8d7be-171">El botón **iniciar visita virtual** está incrustado en el flujo del proveedor.</span><span class="sxs-lookup"><span data-stu-id="8d7be-171">The **Begin virtual visit** button is embedded in the provider flow.</span></span>

<span data-ttu-id="8d7be-172">Características clave de la experiencia de proveedor:</span><span class="sxs-lookup"><span data-stu-id="8d7be-172">Key features of the provider experience:</span></span>

- <span data-ttu-id="8d7be-173">Los proveedores pueden unirse a las visitas virtuales mediante exploradores compatibles o la aplicación Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8d7be-173">Providers can join virtual visits using supported browsers or the Microsoft Teams application.</span></span>

- <span data-ttu-id="8d7be-174">Los proveedores deben realizar un inicio de sesión único con su cuenta de Microsoft 365 al unirse a una visita virtual por primera vez.</span><span class="sxs-lookup"><span data-stu-id="8d7be-174">Providers must do a one time sign in with their Microsoft 365 account when joining a virtual visit for the first time.</span></span>

- <span data-ttu-id="8d7be-175">Después de iniciar sesión una vez, el proveedor se redirigirá directamente a la cita virtual en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8d7be-175">After the one time sign in, the provider will be taken straight to the virtual appointment in Microsoft Teams.</span></span> <span data-ttu-id="8d7be-176">(El proveedor debe haber iniciado sesión en Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="8d7be-176">(Provider must be signed-in to Microsoft Teams).</span></span>

- <span data-ttu-id="8d7be-177">El proveedor puede ver las actualizaciones en tiempo real de los participantes que se conectan y desconectan para una cita determinada.</span><span class="sxs-lookup"><span data-stu-id="8d7be-177">Provider can see real-time updates of participants connect and disconnect for a given appointment.</span></span> <span data-ttu-id="8d7be-178">El proveedor puede ver cuándo está conectado el paciente a una visita virtual.</span><span class="sxs-lookup"><span data-stu-id="8d7be-178">The provider can see when the patient is connected to a virtual visit.</span></span>

  ![Experiencia de proveedor de una visita virtual con un paciente](../../media/ehc-provider-experience-6.png)

### <a name="patient-experience"></a><span data-ttu-id="8d7be-180">Experiencia del paciente</span><span class="sxs-lookup"><span data-stu-id="8d7be-180">Patient experience</span></span>

<span data-ttu-id="8d7be-181">El conector permite a pacientes unir a visitas virtuales a través de MyChart web y móviles.</span><span class="sxs-lookup"><span data-stu-id="8d7be-181">The connector supports patients joining virtual visits through MyChart web and mobile.</span></span> <span data-ttu-id="8d7be-182">En el momento de la cita, los pacientes pueden iniciar una visita virtual de MyChart con el botón **comenzar virtual** .</span><span class="sxs-lookup"><span data-stu-id="8d7be-182">At the time of the appointment, patients can start a virtual visit from MyChart using the **Begin virtual visit** button.</span></span>

<span data-ttu-id="8d7be-183">Características clave de la experiencia del paciente:</span><span class="sxs-lookup"><span data-stu-id="8d7be-183">Key features of the patient experience:</span></span>

- <span data-ttu-id="8d7be-184">Los pacientes pueden unirse a visitas virtuales desde los exploradores Web modernos en el escritorio y en el móvil sin la instalación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8d7be-184">Patients can join virtual visits from modern web browsers on desktop and mobile without app installation.</span></span>

- <span data-ttu-id="8d7be-185">Los pacientes pueden unirse a visitas virtuales con un solo clic y no se necesita ninguna cuenta o inicio de sesión adicional.</span><span class="sxs-lookup"><span data-stu-id="8d7be-185">Patients can join virtual visits with a single click and there is no additional account or sign in required.</span></span>

- <span data-ttu-id="8d7be-186">No es necesario que los pacientes creen una cuenta de Microsoft ni inicien sesión para iniciar una visita virtual.</span><span class="sxs-lookup"><span data-stu-id="8d7be-186">Patients aren't required to create a Microsoft account or sign in to launch a virtual visit.</span></span>

- <span data-ttu-id="8d7be-187">Los pacientes se pondrán en una sala de espera hasta que el proveedor de atención médica se una a la cita y los pueda ir a la visita virtual.</span><span class="sxs-lookup"><span data-stu-id="8d7be-187">Patients will be placed in a lobby until the healthcare provider joins the appointment and admits them to the virtual visit.</span></span>

- <span data-ttu-id="8d7be-188">Las pruebas del video y el micrófono están disponibles en la sala de recepción antes de unirte a la visita virtual.</span><span class="sxs-lookup"><span data-stu-id="8d7be-188">Testing of the video and microphone is available in the lobby before joining the virtual visit.</span></span>

  ![Experiencia del paciente de la visita virtual](../../media/ehc-virtual-visit-5.png)

> [!Note]
> <span data-ttu-id="8d7be-190">Epic, MyChart, Haiku y canto son marcas comerciales de Epic Systems Corporation.</span><span class="sxs-lookup"><span data-stu-id="8d7be-190">Epic, MyChart, Haiku, and Canto are trademarks of Epic Systems Corporation.</span></span>

### <a name="privacy-and-location-of-data"></a><span data-ttu-id="8d7be-191">Privacidad y ubicación de los datos</span><span class="sxs-lookup"><span data-stu-id="8d7be-191">Privacy and location of data</span></span>

<span data-ttu-id="8d7be-192">La integración de equipos en sistemas HCI optimiza la cantidad de datos que se usan y almacenan durante los flujos de integración y de visitas virtuales.</span><span class="sxs-lookup"><span data-stu-id="8d7be-192">Teams integration into EHR systems optimizes the amount of data being used and stored during integration and virtual visit flows.</span></span> <span data-ttu-id="8d7be-193">La solución sigue los principios de la privacidad y la administración de datos de todos los equipos, así como las directrices descritas en privacidad de Teams.</span><span class="sxs-lookup"><span data-stu-id="8d7be-193">The solution follows the overall Teams privacy and data management principles and guidelines outlined in Teams Privacy.</span></span>

<span data-ttu-id="8d7be-194">El conector de Microsoft Teams EHR no almacena ni transfiere datos personales identificables o registros sanitarios de pacientes o de proveedores sanitarios del sistema HCI.</span><span class="sxs-lookup"><span data-stu-id="8d7be-194">The Microsoft Teams EHR connector doesn't store nor transfer any identifiable personal data or any health records of patients or healthcare providers from the EHR system.</span></span> <span data-ttu-id="8d7be-195">Los únicos datos que se almacenan en el conector HCI son el identificador único del usuario de HCI, que se usa durante la configuración de reunión de Teams.</span><span class="sxs-lookup"><span data-stu-id="8d7be-195">The only data that is stored by the EHR connector is the EHR user’s unique ID, which is used during Teams meeting setup.</span></span> <span data-ttu-id="8d7be-196">El identificador exclusivo del usuario de HCI se almacena en una de las tres regiones geográficas que se describen en el artículo [donde se almacenan los datos de los clientes de Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies) .</span><span class="sxs-lookup"><span data-stu-id="8d7be-196">The EHR user’s unique ID is stored in one of the three geographic regions described in the [Where your Microsoft 365 customer data is stored](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies) article.</span></span> <span data-ttu-id="8d7be-197">Todos los chats, las grabaciones y otros datos que los participantes de la reunión hayan introducido se almacenan según las directivas de almacenamiento existentes.</span><span class="sxs-lookup"><span data-stu-id="8d7be-197">All chat, recordings, and other data entered into Teams by the meeting participants are stored according to existing storage policies.</span></span> <span data-ttu-id="8d7be-198">Si desea obtener más información sobre la ubicación de los datos en Microsoft Teams, visite [ubicaciones de datos en Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams).</span><span class="sxs-lookup"><span data-stu-id="8d7be-198">If you want to learn more information on the location of data in Microsoft Teams, visit [Locations of data in Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams).</span></span>
