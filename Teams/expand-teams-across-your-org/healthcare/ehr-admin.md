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
- m365solution-healthcare
- m365solution-scenario
appliesto:
- Microsoft Teams
ms.reviewer: ansantam
description: Utilice Microsoft Teams para configurar el sistema de visitas virtuales
ms.openlocfilehash: 9c002a90cd91014ca4887386ca5834a4b5b41266
ms.sourcegitcommit: d73dc8505a5cc5af29635a50cbbf0f25bbb17eac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2021
ms.locfileid: "52705254"
---
# <a name="virtual-visits-with-teams---integration-into-ehr"></a><span data-ttu-id="ace55-103">Visitas virtuales con Teams: integración en EHR</span><span class="sxs-lookup"><span data-stu-id="ace55-103">Virtual visits with Teams - Integration into EHR</span></span>

<span data-ttu-id="ace55-104">Microsoft Teams El conector de registro de salud electrónico (EHR) facilita a los médicos iniciar una visita virtual a pacientes o consultas con otro proveedor en Teams directamente desde el sistema EHR.</span><span class="sxs-lookup"><span data-stu-id="ace55-104">Microsoft Teams Electronic Health Record (EHR) connector makes it easy for clinicians to launch a virtual patient visit or consultation with another provider in Teams directly from the EHR system.</span></span> <span data-ttu-id="ace55-105">Integrado en la nube de Microsoft 365, Microsoft Teams permite colaborar y comunicarse de forma sencilla y segura con herramientas de chat, vídeo, voz y salud en un único sitio central compatible con el cumplimiento de la ley HIPAA, la certificación HITECH y mucho más.</span><span class="sxs-lookup"><span data-stu-id="ace55-105">Built on the Microsoft 365 cloud, Microsoft Teams enables simple, secure collaboration and communication with chat, video, voice, and healthcare tools in a single hub that supports compliance with HIPAA, HITECH certification, and more.</span></span>
<span data-ttu-id="ace55-106">Con la plataforma de comunicación y colaboración de Teams, los profesionales de la medicina pueden poner fin fácilmente al desorden de los sistemas fragmentados y así dedicar su tiempo a proporcionar la mejor atención posible.</span><span class="sxs-lookup"><span data-stu-id="ace55-106">The communication and collaboration platform of Teams makes it easy for clinicians to cut through the clutter of fragmented systems so they can spend time providing the best possible care.</span></span> <span data-ttu-id="ace55-107">Microsoft Teams El conector registro de estado electrónico (EHR) puede:</span><span class="sxs-lookup"><span data-stu-id="ace55-107">Microsoft Teams Electronic Health Record (EHR) connector can:</span></span>

- <span data-ttu-id="ace55-108">Inicie Teams visitas virtuales desde el sistema EHR del proveedor con un flujo de trabajo clínico integrado.</span><span class="sxs-lookup"><span data-stu-id="ace55-108">Launch Teams virtual visits from the provider EHR system with an integrated clinical workflow.</span></span>
- <span data-ttu-id="ace55-109">Permitir que los pacientes se unan Teams visitas virtuales desde el portal del paciente.</span><span class="sxs-lookup"><span data-stu-id="ace55-109">Enable patients to join Teams virtual visits from within the patient portal.</span></span>
- <span data-ttu-id="ace55-110">Vuelva a escribir metadatos en el sistema EHR con respecto Teams visitas virtuales para grabar cuando los asistentes se conecten y se desconecten y habiliten la auditoría automática y la conservación de registros.</span><span class="sxs-lookup"><span data-stu-id="ace55-110">Write metadata back to the EHR system regarding Teams virtual visits to record when attendees connect and disconnect and enable automatic auditing and record keeping.</span></span>

  <span data-ttu-id="ace55-111">Vea el vídeo sobre cómo administrar las visitas virtuales desde el portal de EHR.</span><span class="sxs-lookup"><span data-stu-id="ace55-111">Watch the video of How to manage virtual visits from the EHR portal.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

## <a name="before-you-begin"></a><span data-ttu-id="ace55-112">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="ace55-112">Before you begin</span></span>

<span data-ttu-id="ace55-113">Debe asegurarse de que cumple los siguientes requisitos previos para poder integrar el conector de EHR:</span><span class="sxs-lookup"><span data-stu-id="ace55-113">You’ll need to make sure you have the following prerequisites before you can integrate the EHR connector:</span></span>

- <span data-ttu-id="ace55-114">Acceso para usar la aplicación Microsoft Teams en [catálogo de App Orchard de Epic](https://apporchard.epic.com/Gallery?id=6153).</span><span class="sxs-lookup"><span data-stu-id="ace55-114">Access to use to the Microsoft Teams app in [Epic’s App Orchard marketplace](https://apporchard.epic.com/Gallery?id=6153).</span></span>

- <span data-ttu-id="ace55-115">Suscripción activa a Microsoft Cloud para el cuidado de la salud o suscripción Microsoft Teams oferta independiente del conector EHR (solo se aplica durante las pruebas de producción).</span><span class="sxs-lookup"><span data-stu-id="ace55-115">Active subscription to Microsoft Cloud for Healthcare or subscription to Microsoft Teams EHR connector standalone offer (only enforced during production testing).</span></span>

- <span data-ttu-id="ace55-116">Los usuarios deben tener una licencia adecuada de Microsoft 365 u Office 365 que incluya reuniones de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ace55-116">Users must have an appropriate Microsoft 365 or Office 365 license that includes Microsoft Teams meetings.</span></span>

- <span data-ttu-id="ace55-117">Microsoft Teams debe adoptarse y usarse dentro de la organización.</span><span class="sxs-lookup"><span data-stu-id="ace55-117">Microsoft Teams should be adopted and used inside the organization.</span></span>

- <span data-ttu-id="ace55-118">Las organizaciones deben tener la versión de Epic de noviembre de 2018 o posterior.</span><span class="sxs-lookup"><span data-stu-id="ace55-118">Organizations must have with Epic version November 2018 or later.</span></span>

- <span data-ttu-id="ace55-119">Los sistemas deben cumplir todos los [requisitos previos de software y explorador web](../../hardware-requirements-for-the-teams-app.md).</span><span class="sxs-lookup"><span data-stu-id="ace55-119">Your systems must meet all [software and browser prerequisites](../../hardware-requirements-for-the-teams-app.md).</span></span>

<span data-ttu-id="ace55-120">También necesitará información de las siguientes personas de la organización:</span><span class="sxs-lookup"><span data-stu-id="ace55-120">You’ll also need information from the following people in your organization:</span></span>

- <span data-ttu-id="ace55-121">Administrador de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ace55-121">Microsoft 365 administrator</span></span>

- <span data-ttu-id="ace55-122">Analista de clientes de Epic</span><span class="sxs-lookup"><span data-stu-id="ace55-122">Epic customer analyst</span></span>

> [!Note]
> <span data-ttu-id="ace55-123">Revise la [integración de teleasistencia sanitaria de Microsoft Teams](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357) con su especialista técnico profesional.</span><span class="sxs-lookup"><span data-stu-id="ace55-123">Review the [Epic-Microsoft Teams Telehealth Integration Guide](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357) with your Epic technical specialist.</span></span> <span data-ttu-id="ace55-124">Asegúrese de que se han completado todos los requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="ace55-124">Make sure that all pre-requisites are completed.</span></span> 

## <a name="connector-setup"></a><span data-ttu-id="ace55-125">Configuración del conector</span><span class="sxs-lookup"><span data-stu-id="ace55-125">Connector setup</span></span>

<span data-ttu-id="ace55-126">Para la configuración del conector, debe realizar las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="ace55-126">The connector setup requires that you:</span></span>

- [<span data-ttu-id="ace55-127">Iniciar el portal de configuración del conector EHR</span><span class="sxs-lookup"><span data-stu-id="ace55-127">Launch the EHR connector configuration portal</span></span>](ehr-admin.md#launch-the-ehr-connector-configuration-portal)
- [<span data-ttu-id="ace55-128">Información de configuración</span><span class="sxs-lookup"><span data-stu-id="ace55-128">Configuration information</span></span>](ehr-admin.md#configuration-information)
- [<span data-ttu-id="ace55-129">Aprobar o ver configuración</span><span class="sxs-lookup"><span data-stu-id="ace55-129">Approve or view configuration</span></span>](ehr-admin.md#approve-or-view-configuration)
- [<span data-ttu-id="ace55-130">Revisar y finalizar la configuración</span><span class="sxs-lookup"><span data-stu-id="ace55-130">Review and finish the configuration</span></span>](ehr-admin.md#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>[<span data-ttu-id="ace55-131">Iniciar el portal de configuración del conector EHR</span><span class="sxs-lookup"><span data-stu-id="ace55-131">Launch the EHR connector configuration portal</span></span>](#launch-the-ehr-connector-configuration-portal)

<span data-ttu-id="ace55-132">Configurar su organización sanitaria para iniciar visitas virtuales con Microsoft Teams inicia iniciando el portal de configuración del conector EHR.</span><span class="sxs-lookup"><span data-stu-id="ace55-132">Configuring your healthcare organization to launch virtual visits with Microsoft Teams starts by launching the EHR connector configuration portal.</span></span> <span data-ttu-id="ace55-133">Configure una o varias organizaciones para probar la integración.</span><span class="sxs-lookup"><span data-stu-id="ace55-133">You configure a single or multiple organizations to test the integration.</span></span> <span data-ttu-id="ace55-134">Configure la dirección URL de prueba y producción en el portal de configuración.</span><span class="sxs-lookup"><span data-stu-id="ace55-134">Configure the test and production URL in the configuration portal.</span></span> <span data-ttu-id="ace55-135">Pruebe la integración del entorno de prueba de Epic antes de pasar a la producción.</span><span class="sxs-lookup"><span data-stu-id="ace55-135">Test the integration from Epic’s test environment before moving to production.</span></span>
  
- <span data-ttu-id="ace55-136">URL de configuración del conector de EHR: [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="ace55-136">EHR connector configuration URL: [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span></span>

<span data-ttu-id="ace55-137">El administrador de Microsoft 365 y el analista de clientes de Epic de su organización deben completar los pasos de información e integración en el portal de configuración.</span><span class="sxs-lookup"><span data-stu-id="ace55-137">The Microsoft 365 admin and Epic customer analyst from your organization must complete the information and integration steps in the configuration portal.</span></span> <span data-ttu-id="ace55-138">Para obtener los pasos de configuración de Epic, póngase en contacto con el recurso de especialista técnico de Epic asignado a su organización.</span><span class="sxs-lookup"><span data-stu-id="ace55-138">For Epic configuration steps, contact the Epic technical specialist resource assigned to your organization.</span></span>

### <a name="configuration-information"></a>[<span data-ttu-id="ace55-139">Información de configuración</span><span class="sxs-lookup"><span data-stu-id="ace55-139">Configuration information</span></span>](#configuration-information)

<span data-ttu-id="ace55-140">El **administrador de Microsoft 365** debe realizar este paso.</span><span class="sxs-lookup"><span data-stu-id="ace55-140">This step is to be completed by the **Microsoft 365 administrator**.</span></span> <span data-ttu-id="ace55-141">El administrador de Microsoft 365 debe iniciar el portal de configuración del conector e iniciar sesión con las credenciales de Microsoft para iniciar el proceso de configuración.</span><span class="sxs-lookup"><span data-stu-id="ace55-141">The Microsoft 365 administrator must launch the connector configuration portal and sign in with Microsoft credentials to start the configuration process.</span></span>

<span data-ttu-id="ace55-142">Para completar este paso, el administrador de Microsoft 365 debe recibir una URL base válida de los Recursos Rápidos de Interoperabilidad en Salud (FHIR) de su especialista técnico de Epic y el nombre de usuario del analista de clientes de Epic que aprobará la configuración.</span><span class="sxs-lookup"><span data-stu-id="ace55-142">To complete this step, the Microsoft 365 administrator must receive a valid Fast Health Interoperability Resources (FHIR) base URL from your Epic technical specialist and the username of the Epic customer analyst who will be approving the configuration.</span></span> <span data-ttu-id="ace55-143">El administrador de Microsoft 365 debe iniciar la página de configuración del conector e iniciar sesión con las credenciales de Microsoft para iniciar el proceso de configuración.</span><span class="sxs-lookup"><span data-stu-id="ace55-143">The Microsoft 365 administrator must launch the connector configuration page and sign in with Microsoft credentials to start the configuration process.</span></span>

- <span data-ttu-id="ace55-144">La URL base de los FHIR es una dirección estática correspondiente al punto de conexión de API de los FHIR del servidor.</span><span class="sxs-lookup"><span data-stu-id="ace55-144">The FHIR base URL is a static address corresponding to your server FHIR API endpoint.</span></span> <span data-ttu-id="ace55-145">Una dirección URL de ejemplo es `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.</span><span class="sxs-lookup"><span data-stu-id="ace55-145">An example URL is `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.</span></span>

- <span data-ttu-id="ace55-146">El nombre del aprobador de la configuración es el nombre del analista de clientes de Epic que será responsable de aprobar la configuración en el siguiente paso.</span><span class="sxs-lookup"><span data-stu-id="ace55-146">Configuration approver name is the name of the Epic customer analyst who will be responsible for approving the configuration in the next step.</span></span> <span data-ttu-id="ace55-147">El analista de clientes de Epic es una persona de su organización que tiene acceso de inicio de sesión a Epic.</span><span class="sxs-lookup"><span data-stu-id="ace55-147">The Epic customer analyst is a person in your organization with sign-in access to Epic.</span></span>

  ![El nombre del aprobador de la configuración se selecciona en una lista en el conector de EHR.](../../media/teams-ehr-connector.png)

### <a name="approve-or-view-configuration"></a>[<span data-ttu-id="ace55-149">Aprobar o ver configuración</span><span class="sxs-lookup"><span data-stu-id="ace55-149">Approve or view configuration</span></span>](#approve-or-view-configuration)

<span data-ttu-id="ace55-150">El analista de clientes épicos de su organización sanitaria que se agregó como aprobador ahora debe usar la misma dirección URL del conector EHR del paso anterior para iniciar sesión con sus credenciales Microsoft 365 usuario.</span><span class="sxs-lookup"><span data-stu-id="ace55-150">The Epic customer analyst for your healthcare organization who was added as an approver must now use the same EHR connector URL from the previous step to sign in using their Microsoft 365 credentials.</span></span> <span data-ttu-id="ace55-151">Tras una validación correcta, se le pedirá al aprobador que inicie sesión con sus credenciales de Epic para validar la organización de Epic.</span><span class="sxs-lookup"><span data-stu-id="ace55-151">After successful validation, the approver is going to be asked to sign in using their Epic credentials to validate the Epic organization.</span></span>

> [!Note]
> <span data-ttu-id="ace55-152">El administrador de Microsoft 365 y el analista de clientes de Epic de su organización pueden ser la misma persona.</span><span class="sxs-lookup"><span data-stu-id="ace55-152">The Microsoft 365 admin and Epic customer analyst in your organization can be the same person.</span></span> <span data-ttu-id="ace55-153">En ese caso, agregue su propio nombre de usuario como aprobador.</span><span class="sxs-lookup"><span data-stu-id="ace55-153">In that case, add your own username as approver.</span></span> <span data-ttu-id="ace55-154">Aun así, tendrá que iniciar sesión en Epic para validar su acceso.</span><span class="sxs-lookup"><span data-stu-id="ace55-154">You'll still need to sign in to Epic to validate your access.</span></span> <span data-ttu-id="ace55-155">El inicio de sesión en Epic solo se usa para validar la URL base de los FHIR.</span><span class="sxs-lookup"><span data-stu-id="ace55-155">The Epic sign in is only used to validate your FHIR base URL.</span></span> <span data-ttu-id="ace55-156">Microsoft no almacenará credenciales ni tendrá acceso a datos de EHR con este inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="ace55-156">Microsoft won't store credentials or access EHR data with this sign in.</span></span>

  ![Compruebe y apruebe la configuración de las credenciales.](../../media/approve-view-configuration.png)

<span data-ttu-id="ace55-158">Una vez que se haya iniciado sesión en Epic correctamente, el analista de clientes de Epic **debe** aprobar la configuración.</span><span class="sxs-lookup"><span data-stu-id="ace55-158">After a successful Epic sign in, the Epic customer analyst **must** approve the configuration.</span></span> <span data-ttu-id="ace55-159">Si la configuración no es correcta, el administrador de Microsoft 365 podrá modificar las configuraciones originales iniciando sesión de nuevo en el portal del conector de EHR para Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ace55-159">If the configuration isn't correct, the Microsoft 365 admin will have the ability to modify the original configurations by signing in to the Microsoft EHR connector portal again.</span></span> 

![Confirme que el conector de EHR está configurado y seleccione la opción para cambiar la configuración.](../../media/ehc-approve-3.png)

### <a name="review-and-finish-the-configuration"></a>[<span data-ttu-id="ace55-161">Revisar y finalizar la configuración</span><span class="sxs-lookup"><span data-stu-id="ace55-161">Review and finish the configuration</span></span>](#review-and-finish-the-configuration)

<span data-ttu-id="ace55-162">Cuando el administrador de Epic apruebe la información de configuración, se le presentarán registros de integración para el inicio de los proveedores y los pacientes.</span><span class="sxs-lookup"><span data-stu-id="ace55-162">When the configuration information is approved by the Epic administrator, you'll be presented with integration records for patient and provider launch.</span></span> <span data-ttu-id="ace55-163">Estos registros son necesarios para completar la configuración de la visita virtual en Epic.</span><span class="sxs-lookup"><span data-stu-id="ace55-163">These records are necessary to complete the virtual visit configuration in Epic.</span></span> <span data-ttu-id="ace55-164">Consulte la Guía de integración de teleasistencia sanitaria de Epic-Microsoft Teams para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="ace55-164">Refer to the Epic-Microsoft Teams Telehealth Integration guide for more details.</span></span>

> [!Note]  
> <span data-ttu-id="ace55-165">El analista de clientes de Epic o Microsoft 365 puede iniciar sesión en cualquier momento en el portal de configuración para ver los registros de integración y modificar la configuración de la organización, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="ace55-165">At any time the Microsoft 365 or Epic customer analyst can sign in to the configuration portal to view integration records and modify organization configuration, if needed.</span></span>

![Se muestra la información de integración.](../../media/finish-configuration.png)

> [!Note]
> <span data-ttu-id="ace55-167">El proceso de aprobación debe completarlo el analista de clientes de Epic para cada URL de los FHIR configurada previamente por el administrador de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ace55-167">The approval process must be completed by the Epic customer analyst for every FHIR URL configured by the Microsoft admin before.</span></span>

![Se aprueba la información de configuración.](../../media/approve-configuration-2.png)

## <a name="launch-teams-virtual-visits"></a><span data-ttu-id="ace55-169">Iniciar las visitas virtuales de Teams</span><span class="sxs-lookup"><span data-stu-id="ace55-169">Launch Teams virtual visits</span></span>

<span data-ttu-id="ace55-170">Después de completar los pasos del conector EHR y la configuración de Epic, su organización está lista para admitir las visitas de vídeo con Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ace55-170">After completing the EHR connector steps and Epic configuration, your organization is ready to support video visits with Microsoft Teams.</span></span>

### <a name="virtual-visit-prerequisites"></a><span data-ttu-id="ace55-171">Requisitos previos de la visita virtual</span><span class="sxs-lookup"><span data-stu-id="ace55-171">Virtual visit prerequisites</span></span>

- <span data-ttu-id="ace55-172">Los sistemas deben cumplir todos los [requisitos previos de software y explorador web](../../hardware-requirements-for-the-teams-app.md).</span><span class="sxs-lookup"><span data-stu-id="ace55-172">Your systems must meet all [software and browser prerequisites](../../hardware-requirements-for-the-teams-app.md).</span></span>

- <span data-ttu-id="ace55-173">La organización sanitaria debe haber completado la configuración entre la organización de Epic y la organización de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ace55-173">Healthcare organization must have completed the setup between the Epic organization and Microsoft 365 organization.</span></span>

### <a name="provider-experience"></a><span data-ttu-id="ace55-174">Experiencia del proveedor</span><span class="sxs-lookup"><span data-stu-id="ace55-174">Provider experience</span></span>

<span data-ttu-id="ace55-175">Los proveedores sanitarios de su organización también pueden unirse a visitas virtuales con Microsoft Teams desde sus aplicaciones de proveedor de Epic (Hyperspace, Haiku, Canto).</span><span class="sxs-lookup"><span data-stu-id="ace55-175">Healthcare providers from your organization can also join virtual visits with Microsoft Teams from their Epic provider applications (Hyperspace, Haiku, Canto).</span></span> <span data-ttu-id="ace55-176">El botón **Iniciar visita virtual** está incorporado en el flujo del proveedor.</span><span class="sxs-lookup"><span data-stu-id="ace55-176">The **Begin virtual visit** button is embedded in the provider flow.</span></span>

<span data-ttu-id="ace55-177">Características principales de la experiencia del proveedor:</span><span class="sxs-lookup"><span data-stu-id="ace55-177">Key features of the provider experience:</span></span>

- <span data-ttu-id="ace55-178">Los proveedores pueden unirse a las visitas virtuales con navegadores web compatibles o con la aplicación de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ace55-178">Providers can join virtual visits using supported browsers or the Microsoft Teams application.</span></span>

- <span data-ttu-id="ace55-179">Los proveedores deben llevar a cabo el inicio de sesión de un solo uso con su cuenta de Microsoft 365 al unirse a una visita virtual por primera vez.</span><span class="sxs-lookup"><span data-stu-id="ace55-179">Providers must do a one-time sign-in with their Microsoft 365 account when joining a virtual visit for the first time.</span></span>

- <span data-ttu-id="ace55-p114">Después del inicio de sesión único, el proveedor se le llevará directamente a la cita virtual en Microsoft Teams. (El proveedor debe haber iniciado sesión en Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="ace55-p114">After the one-time sign-in, the provider will be taken straight to the virtual appointment in Microsoft Teams. (Provider must be signed-in to Microsoft Teams).</span></span>

- <span data-ttu-id="ace55-182">El proveedor puede ver las actualizaciones en tiempo real de los participantes que se conectan y desconectan en una cita determinada.</span><span class="sxs-lookup"><span data-stu-id="ace55-182">Provider can see real-time updates of participants connect and disconnect for a given appointment.</span></span> <span data-ttu-id="ace55-183">El proveedor puede ver cuándo se conecta el paciente a una visita virtual.</span><span class="sxs-lookup"><span data-stu-id="ace55-183">The provider can see when the patient is connected to a virtual visit.</span></span>

  ![Experiencia del proveedor de una visita virtual con paciente](../../media/ehc-provider-experience-6.png)

### <a name="patient-experience"></a><span data-ttu-id="ace55-185">Experiencia del paciente</span><span class="sxs-lookup"><span data-stu-id="ace55-185">Patient experience</span></span>

<span data-ttu-id="ace55-186">El conector admite a los pacientes que se unen a visitas virtuales a través de la web y la aplicación móvil de MyChart.</span><span class="sxs-lookup"><span data-stu-id="ace55-186">The connector supports patients joining virtual visits through MyChart web and mobile.</span></span> <span data-ttu-id="ace55-187">A la hora de la cita, los pacientes pueden iniciar una visita virtual desde MyChart con el botón **Iniciar visita virtual**.</span><span class="sxs-lookup"><span data-stu-id="ace55-187">At the time of the appointment, patients can start a virtual visit from MyChart using the **Begin virtual visit** button.</span></span>

<span data-ttu-id="ace55-188">Características principales de la experiencia del paciente:</span><span class="sxs-lookup"><span data-stu-id="ace55-188">Key features of the patient experience:</span></span>

- <span data-ttu-id="ace55-189">Los pacientes pueden unirse a visitas virtuales desde exploradores web modernos en equipos de sobremesa y dispositivos móviles sin instalar aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="ace55-189">Patients can join virtual visits from modern web browsers on desktop and mobile without app installation.</span></span>

- <span data-ttu-id="ace55-190">Los pacientes pueden unirse a las visitas virtuales con un solo clic y no se necesita ninguna otra cuenta ni inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="ace55-190">Patients can join virtual visits with a single click and there is no other account or sign-in required.</span></span>

- <span data-ttu-id="ace55-191">No es necesario que los pacientes creen una cuenta de Microsoft ni que inicien sesión para iniciar una visita virtual.</span><span class="sxs-lookup"><span data-stu-id="ace55-191">Patients aren't required to create a Microsoft account or sign in to launch a virtual visit.</span></span>

- <span data-ttu-id="ace55-192">Los pacientes estarán en una sala de espera hasta que el proveedor sanitario se una a la cita y los admita a la visita virtual.</span><span class="sxs-lookup"><span data-stu-id="ace55-192">Patients will be placed in a lobby until the healthcare provider joins the appointment and admits them to the virtual visit.</span></span>

- <span data-ttu-id="ace55-193">Hay pruebas de vídeo y micrófono disponibles en la sala de espera antes de unirse a la visita virtual.</span><span class="sxs-lookup"><span data-stu-id="ace55-193">Testing of the video and microphone is available in the lobby before joining the virtual visit.</span></span>

  ![Experiencia del paciente en la visita virtual](../../media/ehc-virtual-visit-5.png)

> [!Note]
> <span data-ttu-id="ace55-195">Epic, MyChart, Haiku y Canto son marcas comerciales de Epic Systems Corporation.</span><span class="sxs-lookup"><span data-stu-id="ace55-195">Epic, MyChart, Haiku, and Canto are trademarks of Epic Systems Corporation.</span></span>

### <a name="privacy-and-location-of-data"></a><span data-ttu-id="ace55-196">Privacidad y ubicación de los datos</span><span class="sxs-lookup"><span data-stu-id="ace55-196">Privacy and location of data</span></span>

<span data-ttu-id="ace55-197">La integración de Teams en sistemas de EHR optimiza la cantidad de datos que se usan y almacenan durante los flujos de integración y de visita virtual.</span><span class="sxs-lookup"><span data-stu-id="ace55-197">Teams integration into EHR systems optimizes the amount of data being used and stored during integration and virtual visit flows.</span></span> <span data-ttu-id="ace55-198">La solución sigue los principios generales de privacidad y administración de datos de Teams, y las directrices estipuladas en Privacidad de Teams.</span><span class="sxs-lookup"><span data-stu-id="ace55-198">The solution follows the overall Teams privacy and data management principles and guidelines outlined in Teams Privacy.</span></span>

<span data-ttu-id="ace55-199">El conector de EHR para Microsoft Teams no almacena ni transfiere ningún dato personal de identificación ni ningún registro médico de pacientes o proveedores sanitarios desde el sistema de EHR.</span><span class="sxs-lookup"><span data-stu-id="ace55-199">The Microsoft Teams EHR connector doesn't store nor transfer any identifiable personal data or any health records of patients or healthcare providers from the EHR system.</span></span> <span data-ttu-id="ace55-200">El único dato que almacena el conector de EHR es la identificación única del usuario de EHR, que se usa durante la configuración de la reunión de Teams.</span><span class="sxs-lookup"><span data-stu-id="ace55-200">The only data that is stored by the EHR connector is the EHR user’s unique ID, which is used during Teams meeting setup.</span></span> <span data-ttu-id="ace55-201">La identificación única del usuario de EHR se almacena en una de las tres regiones geográficas que se describen en [¿Dónde se almacenan los datos de los clientes de Microsoft 365?](/microsoft-365/enterprise/o365-data-locations)</span><span class="sxs-lookup"><span data-stu-id="ace55-201">The EHR user’s unique ID is stored in one of the three geographic regions described in [Where your Microsoft 365 customer data is stored](/microsoft-365/enterprise/o365-data-locations).</span></span> <span data-ttu-id="ace55-202">Todos los chats, las grabaciones y demás datos que introduzcan en Teams los participantes de la reunión se almacenan según las directivas de almacenamiento existentes.</span><span class="sxs-lookup"><span data-stu-id="ace55-202">All chat, recordings, and other data entered into Teams by the meeting participants are stored according to existing storage policies.</span></span> <span data-ttu-id="ace55-203">Si desea obtener más información sobre la ubicación de los datos en Microsoft Teams, visite [Ubicaciones de los datos en Teams](../../location-of-data-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="ace55-203">If you want to learn more information on the location of data in Microsoft Teams, visit [Locations of data in Teams](../../location-of-data-in-teams.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ace55-204">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ace55-204">Related topics</span></span>

[<span data-ttu-id="ace55-205">Teams visitas virtuales</span><span class="sxs-lookup"><span data-stu-id="ace55-205">Teams virtual visits</span></span>](ehr-admin-reports.md)