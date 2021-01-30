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
description: Usar Microsoft Teams para configurar su sistema de visitas virtuales
ms.openlocfilehash: 6753afbabf6bbcb420f9ddf479249a968d33eb2c
ms.sourcegitcommit: 2639da2c9f903a9a82866be9db2b69a705c54200
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055713"
---
# <a name="virtual-visits-with-teams---integration-into-ehr"></a><span data-ttu-id="0475a-103">Visitas virtuales con Teams: integración en EHR</span><span class="sxs-lookup"><span data-stu-id="0475a-103">Virtual visits with Teams - Integration into EHR</span></span>

<span data-ttu-id="0475a-104">El conector del registro sanitario electrónico (EHR) de Microsoft Teams facilita a los médicos iniciar una visita virtual a un paciente o una consulta con otro proveedor en Teams directamente desde el sistema EHR.</span><span class="sxs-lookup"><span data-stu-id="0475a-104">Microsoft Teams Electronic Health Record (EHR) Connector makes it easy for clinicians to launch a virtual patient visit or consultation with another provider in Teams directly from the EHR system.</span></span> <span data-ttu-id="0475a-105">Microsoft Teams, integrado en la nube de Microsoft 365, permite una colaboración y comunicación sencillas y seguras con herramientas de chat, vídeo, voz y salud en un único hub que cumple con la certificación HIPAA, HITECH y mucho más.</span><span class="sxs-lookup"><span data-stu-id="0475a-105">Built on the Microsoft 365 cloud, Microsoft Teams enables simple, secure collaboration and communication with chat, video, voice, and healthcare tools in a single hub that supports compliance with HIPAA, HITECH certification, and more.</span></span>
<span data-ttu-id="0475a-106">La plataforma de comunicación y colaboración de Teams facilita a los médicos cortar el desorden de sistemas fragmentados para que puedan dedicar el tiempo a proporcionar la mejor atención posible.</span><span class="sxs-lookup"><span data-stu-id="0475a-106">The communication and collaboration platform of Teams makes it easy for clinicians to cut through the clutter of fragmented systems so they can spend time providing the best possible care.</span></span> <span data-ttu-id="0475a-107">El conector del registro de salud electrónico (EHR) de Microsoft Teams puede:</span><span class="sxs-lookup"><span data-stu-id="0475a-107">Microsoft Teams Electronic Health Record (EHR) Connector can:</span></span>
- <span data-ttu-id="0475a-108">Inicie las visitas virtuales de Teams desde los portales del proveedor y del paciente.</span><span class="sxs-lookup"><span data-stu-id="0475a-108">Launch Teams virtual visits from both provider and patient portals.</span></span>
- <span data-ttu-id="0475a-109">Reescriba los metadatos EHR en los eventos de conexión y desconexión para habilitar la auditoría automática y la conservación de registros.</span><span class="sxs-lookup"><span data-stu-id="0475a-109">Write back into EHR metadata on connect and disconnect events to enable automatic auditing and record keeping.</span></span>
- <span data-ttu-id="0475a-110">Inténtese en flujos de trabajo existentes de médicos y pacientes al tiempo que les permite usar Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0475a-110">Integrate into existing clinician and patient workflows while allowing them to use Microsoft Teams.</span></span>

  <span data-ttu-id="0475a-111">Vea el vídeo sobre cómo administrar las visitas virtuales desde el portal de EHR.</span><span class="sxs-lookup"><span data-stu-id="0475a-111">Watch the video of How to manage virtual visits from the EHR portal.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

## <a name="before-you-begin"></a><span data-ttu-id="0475a-112">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="0475a-112">Before you begin</span></span>

<span data-ttu-id="0475a-113">Debe asegurarse de que tiene los siguientes requisitos previos para poder integrar el conector EHR:</span><span class="sxs-lookup"><span data-stu-id="0475a-113">You’ll need to make sure you have the following prerequisites before you can integrate the EHR connector:</span></span>

- <span data-ttu-id="0475a-114">Acceso para usar en la aplicación Microsoft Teams en [El catálogo de catálogos de aplicaciones de Épico.](https://apporchard.epic.com/Gallery?id=6153)</span><span class="sxs-lookup"><span data-stu-id="0475a-114">Access to use to the Microsoft Teams app in [Epic’s App Orchard marketplace](https://apporchard.epic.com/Gallery?id=6153).</span></span>

- <span data-ttu-id="0475a-115">Suscripción activa a Microsoft Cloud para el ámbito sanitario o suscripción a la oferta independiente de Microsoft Teams EHR Connector.</span><span class="sxs-lookup"><span data-stu-id="0475a-115">Active subscription to Microsoft Cloud for Healthcare or subscription to Microsoft Teams EHR Connector standalone offer.</span></span>

- <span data-ttu-id="0475a-116">Los usuarios deben tener una licencia adecuada de Microsoft 365 u Office 365 que incluya las reuniones de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0475a-116">Users must have an appropriate Microsoft 365 or Office 365 license that includes Microsoft Teams meetings.</span></span>

- <span data-ttu-id="0475a-117">Microsoft Teams debe adoptarse y usarse dentro de la organización.</span><span class="sxs-lookup"><span data-stu-id="0475a-117">Microsoft Teams should be adopted and used inside the organization.</span></span>

- <span data-ttu-id="0475a-118">Las organizaciones deben tener la versión Épicos de noviembre de 2018 o posterior.</span><span class="sxs-lookup"><span data-stu-id="0475a-118">Organizations must have with Epic version November 2018 or later.</span></span>

- <span data-ttu-id="0475a-119">Los sistemas deben cumplir todos los requisitos [previos del software y del explorador.](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app)</span><span class="sxs-lookup"><span data-stu-id="0475a-119">Your systems must meet all [software and browser prerequisites](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span></span>

<span data-ttu-id="0475a-120">También necesitará información de las siguientes personas de su organización:</span><span class="sxs-lookup"><span data-stu-id="0475a-120">You’ll also need information from the following people in your organization:</span></span>

- <span data-ttu-id="0475a-121">Administrador de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0475a-121">Microsoft 365 administrator</span></span>

- <span data-ttu-id="0475a-122">Analista de clientes épicos</span><span class="sxs-lookup"><span data-stu-id="0475a-122">Epic customer analyst</span></span>

> [!Note]
> <span data-ttu-id="0475a-123">Solicite a su especialista técnico épico que proporcione la guía de Epic-Microsoft integración de Telehealth de Teams en el Catálogo de soluciones épicos.</span><span class="sxs-lookup"><span data-stu-id="0475a-123">Request your Epic technical specialist to provide the Epic-Microsoft Teams Telehealth Integration Guide available in the Epic marketplace.</span></span>

## <a name="connector-setup"></a><span data-ttu-id="0475a-124">Configuración del conector</span><span class="sxs-lookup"><span data-stu-id="0475a-124">Connector setup</span></span>

<span data-ttu-id="0475a-125">La configuración del conector requiere que:</span><span class="sxs-lookup"><span data-stu-id="0475a-125">The connector setup requires that you:</span></span>

- [<span data-ttu-id="0475a-126">Iniciar el portal de configuración del conector EHR</span><span class="sxs-lookup"><span data-stu-id="0475a-126">Launch the EHR Connector configuration portal</span></span>](ehr-admin.md#launch-the-ehr-connector-configuration-portal)
- [<span data-ttu-id="0475a-127">Información de configuración</span><span class="sxs-lookup"><span data-stu-id="0475a-127">Configuration information</span></span>](ehr-admin.md#configuration-information)
- [<span data-ttu-id="0475a-128">Aprobar o ver la configuración</span><span class="sxs-lookup"><span data-stu-id="0475a-128">Approve or view configuration</span></span>](ehr-admin.md#approve-or-view-configuration)
- [<span data-ttu-id="0475a-129">Revisar y finalizar la configuración</span><span class="sxs-lookup"><span data-stu-id="0475a-129">Review and finish the configuration</span></span>](ehr-admin.md#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>[<span data-ttu-id="0475a-130">Iniciar el portal de configuración del conector EHR</span><span class="sxs-lookup"><span data-stu-id="0475a-130">Launch the EHR Connector configuration portal</span></span>](#launch-the-ehr-connector-configuration-portal)

<span data-ttu-id="0475a-131">La configuración de su organización sanitaria para iniciar visitas virtuales con Microsoft Teams se inicia iniciando el portal de configuración de EHR Connector.</span><span class="sxs-lookup"><span data-stu-id="0475a-131">Configuring your healthcare organization to launch virtual visits with Microsoft Teams starts by launching the EHR Connector configuration portal.</span></span> <span data-ttu-id="0475a-132">Configure una o varias organizaciones para probar la integración.</span><span class="sxs-lookup"><span data-stu-id="0475a-132">You configure a single or multiple organizations to test the integration.</span></span> <span data-ttu-id="0475a-133">Configure la dirección URL de prueba y producción en el portal de configuración.</span><span class="sxs-lookup"><span data-stu-id="0475a-133">Configure the test and production URL in the configuration portal.</span></span> <span data-ttu-id="0475a-134">Pruebe la integración del entorno de prueba de Épico antes de pasar a la producción.</span><span class="sxs-lookup"><span data-stu-id="0475a-134">Test the integration from Epic’s test environment before moving to production.</span></span>
  
- <span data-ttu-id="0475a-135">URL de configuración del conector EHR: [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="0475a-135">EHR connector configuration URL: [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span></span>

<span data-ttu-id="0475a-136">El administrador de Microsoft 365 y analista de clientes De su organización deben completar los pasos de información e integración en el portal de configuración.</span><span class="sxs-lookup"><span data-stu-id="0475a-136">The Microsoft 365 admin and Epic customer analyst from your organization must complete the information and integration steps in the configuration portal.</span></span> <span data-ttu-id="0475a-137">Para ver los pasos de configuración Épico, póngase en contacto con el recurso de especialista técnico épico asignado a su organización.</span><span class="sxs-lookup"><span data-stu-id="0475a-137">For Epic configuration steps, contact the Epic technical specialist resource assigned to your organization.</span></span>

### <a name="configuration-information"></a>[<span data-ttu-id="0475a-138">Información de configuración</span><span class="sxs-lookup"><span data-stu-id="0475a-138">Configuration information</span></span>](#configuration-information)

<span data-ttu-id="0475a-139">Este paso lo completará el administrador **de Microsoft 365.**</span><span class="sxs-lookup"><span data-stu-id="0475a-139">This step is to be completed by the **Microsoft 365 administrator**.</span></span> <span data-ttu-id="0475a-140">El administrador de Microsoft 365 debe iniciar el portal de configuración del conector e iniciar sesión con credenciales de Microsoft para iniciar el proceso de configuración.</span><span class="sxs-lookup"><span data-stu-id="0475a-140">The Microsoft 365 administrator must launch the connector configuration portal and sign in with Microsoft credentials to start the configuration process.</span></span>

<span data-ttu-id="0475a-141">Para completar este paso, el administrador de Microsoft 365 debe recibir una DIRECCIÓN URL válida de la base de recursos de interoperabilidad de estado rápido (FCONTR) de su especialista épico y el nombre de usuario del analista de clientes Épico que aprobará la configuración.</span><span class="sxs-lookup"><span data-stu-id="0475a-141">To complete this step, the Microsoft 365 administrator must receive a valid Fast Health Interoperability Resources (FHIR) base URL from your Epic technical specialist and the username of the Epic customer analyst who will be approving the configuration.</span></span> <span data-ttu-id="0475a-142">El administrador de Microsoft 365 debe iniciar la página de configuración del conector e iniciar sesión con credenciales de Microsoft para iniciar el proceso de configuración.</span><span class="sxs-lookup"><span data-stu-id="0475a-142">The Microsoft 365 administrator must launch the connector configuration page and sign in with Microsoft credentials to start the configuration process.</span></span>

- <span data-ttu-id="0475a-143">La dirección URL de la base FCONTR es una dirección estática que corresponde al extremo de la API F LDAP del servidor.</span><span class="sxs-lookup"><span data-stu-id="0475a-143">The FHIR base URL is a static address corresponding to your server FHIR API endpoint.</span></span> <span data-ttu-id="0475a-144">Una dirección URL de ejemplo `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST` es.</span><span class="sxs-lookup"><span data-stu-id="0475a-144">An example URL is `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.</span></span>

- <span data-ttu-id="0475a-145">El nombre del aprobador de configuración es el nombre del analista de clientes épicos que será el responsable de aprobar la configuración en el siguiente paso.</span><span class="sxs-lookup"><span data-stu-id="0475a-145">Configuration approver name is the name of the Epic customer analyst who will be responsible for approving the configuration in the next step.</span></span> <span data-ttu-id="0475a-146">El analista de clientes Épicos es una persona de su organización con acceso de inicio de sesión a Épico.</span><span class="sxs-lookup"><span data-stu-id="0475a-146">The Epic customer analyst is a person in your organization with signin access to Epic.</span></span>

  ![El nombre del aprobador de configuración se selecciona de una lista en el conector EHR.](../../media/teams-ehr-connector.png)

### <a name="approve-or-view-configuration"></a>[<span data-ttu-id="0475a-148">Aprobar o ver la configuración</span><span class="sxs-lookup"><span data-stu-id="0475a-148">Approve or view configuration</span></span>](#approve-or-view-configuration)

<span data-ttu-id="0475a-149">La analista de clientes épicos de su organización sanitaria que se agregó como aprobador ahora debe usar la misma URL del conector EHR del paso anterior para iniciar sesión con sus credenciales de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0475a-149">The Epic customer analyst for your healthcare organization who was added as an approver must now use the same EHR Connector URL from the previous step to sign in using their Microsoft 365 credentials.</span></span> <span data-ttu-id="0475a-150">Después de la validación correcta, se le pedirá al aprobador que inicie sesión con sus credenciales épicos para validar la organización épicos.</span><span class="sxs-lookup"><span data-stu-id="0475a-150">After successful validation, the approver is going to be asked to sign in using their Epic credentials to validate the Epic organization.</span></span>

> [!Note]
> <span data-ttu-id="0475a-151">El administrador de Microsoft 365 y el analista de clientes Épicos de su organización pueden ser la misma persona.</span><span class="sxs-lookup"><span data-stu-id="0475a-151">The Microsoft 365 admin and Epic customer analyst in your organization can be the same person.</span></span> <span data-ttu-id="0475a-152">En ese caso, agregue su propio nombre de usuario como aprobador.</span><span class="sxs-lookup"><span data-stu-id="0475a-152">In that case, add your own username as approver.</span></span> <span data-ttu-id="0475a-153">Igualmente tendrás que iniciar sesión en Épico para validar tu acceso.</span><span class="sxs-lookup"><span data-stu-id="0475a-153">You'll still need to sign in to Epic to validate your access.</span></span> <span data-ttu-id="0475a-154">El inicio de sesión épico solo se usa para validar la dirección URL de la base FCONTR.</span><span class="sxs-lookup"><span data-stu-id="0475a-154">The Epic sign in is only used to validate your FHIR base URL.</span></span> <span data-ttu-id="0475a-155">Microsoft no almacenará credenciales ni accederá a datos EHR con este inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="0475a-155">Microsoft won't store credentials or access EHR data with this sign in.</span></span>

  ![Compruebe y apruebe la configuración de credenciales.](../../media/approve-view-configuration.png)

<span data-ttu-id="0475a-157">Después de un inicio de sesión épico correcto, el analista de clientes épicos **debe** aprobar la configuración.</span><span class="sxs-lookup"><span data-stu-id="0475a-157">After a successful Epic sign in, the Epic customer analyst **must** approve the configuration.</span></span> <span data-ttu-id="0475a-158">Si la configuración no es correcta, el administrador de Microsoft 365 podrá modificar las configuraciones originales iniciando sesión de nuevo en el portal del conector EHR de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0475a-158">If the configuration isn't correct, the Microsoft 365 admin will have the ability to modify the original configurations by signing in to the Microsoft EHR connector portal again.</span></span> 

![Confirme que el conector EHR está configurado y la opción de cambiar la configuración.](../../media/ehc-approve-3.png)

### <a name="review-and-finish-the-configuration"></a>[<span data-ttu-id="0475a-160">Revisar y finalizar la configuración</span><span class="sxs-lookup"><span data-stu-id="0475a-160">Review and finish the configuration</span></span>](#review-and-finish-the-configuration)

<span data-ttu-id="0475a-161">Cuando el administrador épico apruebe la información de configuración, se le presentarán registros de integración para el lanzamiento del proveedor y el paciente.</span><span class="sxs-lookup"><span data-stu-id="0475a-161">When the configuration information is approved by the Epic administrator, you'll be presented with integration records for patient and provider launch.</span></span> <span data-ttu-id="0475a-162">Estos registros son necesarios para completar la configuración de visita virtual en Épico.</span><span class="sxs-lookup"><span data-stu-id="0475a-162">These records are necessary to complete the virtual visit configuration in Epic.</span></span> <span data-ttu-id="0475a-163">Consulte la guía Epic-Microsoft integración de Telehealth de Teams para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="0475a-163">Refer to the Epic-Microsoft Teams Telehealth Integration guide for more details.</span></span>

> [!Note]  
> <span data-ttu-id="0475a-164">En cualquier momento, el analista de clientes de Microsoft 365 o Épicos puede iniciar sesión en el portal de configuración para ver los registros de integración y modificar la configuración de la organización, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="0475a-164">At any time the Microsoft 365 or Epic customer analyst can sign in to the configuration portal to view integration records and modify organization configuration, if needed.</span></span>

![Se muestra la información de integración.](../../media/finish-configuration.png)

> [!Note]
> <span data-ttu-id="0475a-166">El proceso de aprobación lo debe completar el analista de clientes épicos para cada URL de FCONTR configurada por el administrador de Microsoft anteriormente.</span><span class="sxs-lookup"><span data-stu-id="0475a-166">The approval process must be completed by the Epic customer analyst for every FHIR URL configured by the Microsoft admin before.</span></span>

![La información de configuración se ha aprobado.](../../media/approve-configuration-2.png)

## <a name="launch-teams-virtual-visits"></a><span data-ttu-id="0475a-168">Iniciar visitas virtuales de Teams</span><span class="sxs-lookup"><span data-stu-id="0475a-168">Launch Teams virtual visits</span></span>

<span data-ttu-id="0475a-169">Después de completar los pasos del conector EHR y la configuración épicos, su organización está lista para admitir las visitas en vídeo con Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0475a-169">After completing the EHR Connector steps and Epic configuration, your organization is ready to support video visits with Microsoft Teams.</span></span>

### <a name="virtual-visit-prerequisites"></a><span data-ttu-id="0475a-170">Requisitos previos de la visita virtual</span><span class="sxs-lookup"><span data-stu-id="0475a-170">Virtual visit prerequisites</span></span>

- <span data-ttu-id="0475a-171">Los sistemas deben cumplir todos los requisitos [previos del software y del explorador.](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app)</span><span class="sxs-lookup"><span data-stu-id="0475a-171">Your systems must meet all [software and browser prerequisites](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span></span>

- <span data-ttu-id="0475a-172">La organización sanitaria debe haber completado la configuración entre la organización Épicos y la organización de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0475a-172">Healthcare organization must have completed the setup between the Epic organization and Microsoft 365 organization.</span></span>

### <a name="provider-experience"></a><span data-ttu-id="0475a-173">Experiencia del proveedor</span><span class="sxs-lookup"><span data-stu-id="0475a-173">Provider experience</span></span>

<span data-ttu-id="0475a-174">Los proveedores de salud de su organización también pueden unirse a visitas virtuales con Microsoft Teams desde sus aplicaciones de proveedor de épicos (Hyperspace, Havelo, Canton).</span><span class="sxs-lookup"><span data-stu-id="0475a-174">Healthcare providers from your organization can also join virtual visits with Microsoft Teams from their Epic provider applications (Hyperspace, Haiku, Canto).</span></span> <span data-ttu-id="0475a-175">El **botón Comenzar visita virtual** está insertado en el flujo del proveedor.</span><span class="sxs-lookup"><span data-stu-id="0475a-175">The **Begin virtual visit** button is embedded in the provider flow.</span></span>

<span data-ttu-id="0475a-176">Características clave de la experiencia del proveedor:</span><span class="sxs-lookup"><span data-stu-id="0475a-176">Key features of the provider experience:</span></span>

- <span data-ttu-id="0475a-177">Los proveedores pueden unirse a visitas virtuales mediante exploradores compatibles o la aplicación Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0475a-177">Providers can join virtual visits using supported browsers or the Microsoft Teams application.</span></span>

- <span data-ttu-id="0475a-178">Los proveedores deben realizar un inicio de sesión único con su cuenta de Microsoft 365 al unirse a una visita virtual por primera vez.</span><span class="sxs-lookup"><span data-stu-id="0475a-178">Providers must do a one-time sign-in with their Microsoft 365 account when joining a virtual visit for the first time.</span></span>

- <span data-ttu-id="0475a-179">Después del inicio de sesión único, el proveedor se le llevará directamente a la cita virtual en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0475a-179">After the one-time sign-in, the provider will be taken straight to the virtual appointment in Microsoft Teams.</span></span> <span data-ttu-id="0475a-180">(El proveedor debe haber iniciado sesión en Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="0475a-180">(Provider must be signed-in to Microsoft Teams).</span></span>

- <span data-ttu-id="0475a-181">El proveedor puede ver actualizaciones en tiempo real de los participantes que se conectan y se desconectan para una cita determinada.</span><span class="sxs-lookup"><span data-stu-id="0475a-181">Provider can see real-time updates of participants connect and disconnect for a given appointment.</span></span> <span data-ttu-id="0475a-182">El proveedor puede ver cuándo está conectado el paciente a una visita virtual.</span><span class="sxs-lookup"><span data-stu-id="0475a-182">The provider can see when the patient is connected to a virtual visit.</span></span>

  ![Experiencia del proveedor de una visita virtual con un paciente](../../media/ehc-provider-experience-6.png)

### <a name="patient-experience"></a><span data-ttu-id="0475a-184">Experiencia del paciente</span><span class="sxs-lookup"><span data-stu-id="0475a-184">Patient experience</span></span>

<span data-ttu-id="0475a-185">El conector admite a los pacientes que se unen a visitas virtuales a través de MyChart Web y dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="0475a-185">The connector supports patients joining virtual visits through MyChart web and mobile.</span></span> <span data-ttu-id="0475a-186">Cuando se haga la cita, los pacientes pueden iniciar una visita virtual desde MyChart con el **botón Comenzar visita virtual.**</span><span class="sxs-lookup"><span data-stu-id="0475a-186">At the time of the appointment, patients can start a virtual visit from MyChart using the **Begin virtual visit** button.</span></span>

<span data-ttu-id="0475a-187">Características clave de la experiencia del paciente:</span><span class="sxs-lookup"><span data-stu-id="0475a-187">Key features of the patient experience:</span></span>

- <span data-ttu-id="0475a-188">Los pacientes pueden unirse a visitas virtuales de exploradores web modernos en equipos de escritorio y dispositivos móviles sin instalación de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="0475a-188">Patients can join virtual visits from modern web browsers on desktop and mobile without app installation.</span></span>

- <span data-ttu-id="0475a-189">Los pacientes pueden unirse a visitas virtuales con un solo clic y no se requiere otra cuenta ni inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="0475a-189">Patients can join virtual visits with a single click and there is no other account or sign-in required.</span></span>

- <span data-ttu-id="0475a-190">No es necesario que los pacientes creen una cuenta de Microsoft ni que inicien sesión para iniciar una visita virtual.</span><span class="sxs-lookup"><span data-stu-id="0475a-190">Patients aren't required to create a Microsoft account or sign in to launch a virtual visit.</span></span>

- <span data-ttu-id="0475a-191">Los pacientes se colocarán en una sala de espera hasta que el proveedor de salud se una a la cita y los admita en la visita virtual.</span><span class="sxs-lookup"><span data-stu-id="0475a-191">Patients will be placed in a lobby until the healthcare provider joins the appointment and admits them to the virtual visit.</span></span>

- <span data-ttu-id="0475a-192">Las pruebas del vídeo y el micrófono están disponibles en la sala de espera antes de unirse a la visita virtual.</span><span class="sxs-lookup"><span data-stu-id="0475a-192">Testing of the video and microphone is available in the lobby before joining the virtual visit.</span></span>

  ![Experiencia del paciente con la visita virtual](../../media/ehc-virtual-visit-5.png)

> [!Note]
> <span data-ttu-id="0475a-194">Épico, MyChart, Halio y Canton son marcas comerciales de Épico Systems Corporation.</span><span class="sxs-lookup"><span data-stu-id="0475a-194">Epic, MyChart, Haiku, and Canto are trademarks of Epic Systems Corporation.</span></span>

### <a name="privacy-and-location-of-data"></a><span data-ttu-id="0475a-195">Privacidad y ubicación de los datos</span><span class="sxs-lookup"><span data-stu-id="0475a-195">Privacy and location of data</span></span>

<span data-ttu-id="0475a-196">La integración de Teams en sistemas EHR optimiza la cantidad de datos que se usan y almacenan durante los flujos de integración y visitas virtuales.</span><span class="sxs-lookup"><span data-stu-id="0475a-196">Teams integration into EHR systems optimizes the amount of data being used and stored during integration and virtual visit flows.</span></span> <span data-ttu-id="0475a-197">La solución sigue los principios y directrices generales de privacidad y administración de datos de Teams que se describen en Privacidad de Teams.</span><span class="sxs-lookup"><span data-stu-id="0475a-197">The solution follows the overall Teams privacy and data management principles and guidelines outlined in Teams Privacy.</span></span>

<span data-ttu-id="0475a-198">El conector EHR de Microsoft Teams no almacena ni transfiere ningún dato personal identificable ni ningún registro de salud de pacientes o proveedores sanitarios desde el sistema EHR.</span><span class="sxs-lookup"><span data-stu-id="0475a-198">The Microsoft Teams EHR connector doesn't store nor transfer any identifiable personal data or any health records of patients or healthcare providers from the EHR system.</span></span> <span data-ttu-id="0475a-199">Los únicos datos que almacena el conector EHR es el identificador único del usuario de EHR, que se usa durante la configuración de la reunión de Teams.</span><span class="sxs-lookup"><span data-stu-id="0475a-199">The only data that is stored by the EHR connector is the EHR user’s unique ID, which is used during Teams meeting setup.</span></span> <span data-ttu-id="0475a-200">El id. único del usuario de EHR se almacena en una de las tres regiones geográficas que se describen en el lugar donde se almacenan los datos de cliente de [Microsoft 365.](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies)</span><span class="sxs-lookup"><span data-stu-id="0475a-200">The EHR user’s unique ID is stored in one of the three geographic regions described in [Where your Microsoft 365 customer data is stored](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies).</span></span> <span data-ttu-id="0475a-201">Todos los chats, las grabaciones y otros datos introducidos en Teams por los participantes de la reunión se almacenan según las directivas de almacenamiento existentes.</span><span class="sxs-lookup"><span data-stu-id="0475a-201">All chat, recordings, and other data entered into Teams by the meeting participants are stored according to existing storage policies.</span></span> <span data-ttu-id="0475a-202">Si desea obtener más información sobre la ubicación de los datos en Microsoft Teams, visite [Ubicaciones de datos en Teams.](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams)</span><span class="sxs-lookup"><span data-stu-id="0475a-202">If you want to learn more information on the location of data in Microsoft Teams, visit [Locations of data in Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams).</span></span>
