---
title: Información general de la aplicación Pacientes
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Obtenga información sobre cómo integrar registros de asistencia electrónica en la aplicación de pacientes de Microsoft Teams con las API de FHIR.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f981b2fc68aa52f8ea5a48fab18977197ac813c8
ms.sourcegitcommit: 397c4840fb053238de24b8b24ae75588b33b693d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2020
ms.locfileid: "45098428"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a><span data-ttu-id="0d00d-103">Integración de registros sanitarios electrónicos en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0d00d-103">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="0d00d-104">Este artículo está dirigido a un desarrollador de TI de medicina general interesado en usar API de FHIR sobre un sistema de información de medicina para conectar con Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0d00d-104">This article is intended for a general healthcare IT developer interested in using FHIR APIs on top of a medical information system to connect to Microsoft Teams.</span></span> <span data-ttu-id="0d00d-105">Esto permitiría escenarios de coordinación de cuidados que se ajusten a las necesidades de una organización de salud.</span><span class="sxs-lookup"><span data-stu-id="0d00d-105">This would enable care coordination scenarios that match the needs of a healthcare organization.</span></span>

<span data-ttu-id="0d00d-106">Los artículos vinculados documentan las especificaciones de la interfaz de FHIR para la aplicación de pacientes de Microsoft Teams, y las siguientes secciones explican qué se necesita para configurar un servidor de FHIR y conectarse a la aplicación de pacientes en el entorno de desarrollo o en el inquilino.</span><span class="sxs-lookup"><span data-stu-id="0d00d-106">Linked articles document the FHIR interface specifications for the Microsoft Teams Patients app, and following sections explain what is required for setting up a FHIR server and connecting to the Patients app in your development environment or tenant.</span></span> <span data-ttu-id="0d00d-107">También necesitará estar familiarizado con la documentación del servidor de FHIR que haya elegido, que debe ser una de las opciones admitidas:</span><span class="sxs-lookup"><span data-stu-id="0d00d-107">You will also need to be familiar with the documentation of the FHIR server you have chosen, which must be one of the supported options:</span></span>
- <span data-ttu-id="0d00d-108">Datica (a través de la oferta de [CMI](https://datica.com/compliant-managed-integration/) )</span><span class="sxs-lookup"><span data-stu-id="0d00d-108">Datica (through their [CMI](https://datica.com/compliant-managed-integration/) offering)</span></span>
- <span data-ttu-id="0d00d-109">Infor cloverleaf (a través del [puente de FHIR de Infor](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span><span class="sxs-lookup"><span data-stu-id="0d00d-109">Infor Cloverleaf (through the [Infor FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span></span>
- <span data-ttu-id="0d00d-110">Redox (a través del [servidor R ^ FHIR](https://www.redoxengine.com/fhir/))</span><span class="sxs-lookup"><span data-stu-id="0d00d-110">Redox (through the [R^FHIR server](https://www.redoxengine.com/fhir/))</span></span>
- <span data-ttu-id="0d00d-111">Dapasoft (a través [de Corolar en FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span><span class="sxs-lookup"><span data-stu-id="0d00d-111">Dapasoft (through [Corolar on FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span></span>

> [!NOTE]
> <span data-ttu-id="0d00d-112">Este proceso no incluye los pasos que usan el centro de administración de Microsoft Teams o los cmdlets de PowerShell para habilitar características.</span><span class="sxs-lookup"><span data-stu-id="0d00d-112">This process does not includes steps that use the Microsoft Teams admin center or PowerShell cmdlets to enable features.</span></span> <span data-ttu-id="0d00d-113">La configuración se realiza por completo en el servidor FHIR y en el cliente de aplicaciones para pacientes.</span><span class="sxs-lookup"><span data-stu-id="0d00d-113">The configuration is entirely done on the FHIR server/service side and in the Patients app client.</span></span>

<span data-ttu-id="0d00d-114">A continuación se muestra la arquitectura de la aplicación para pacientes:</span><span class="sxs-lookup"><span data-stu-id="0d00d-114">Illustrated below is the architecture of the Patients app:</span></span>

![Diagrama de la arquitectura de la aplicación para pacientes](../../media/patients-app-architecture.png)

<span data-ttu-id="0d00d-116">En las siguientes secciones, se explican los requisitos de la FHIR de acceso a datos de solo lectura para la aplicación de pacientes que un servidor de FHIR (o las API de FHIR habilitadas de EHR) debe cumplirse para poder integrarse con la aplicación de pacientes, entre los que se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="0d00d-116">The following sections explain the requirements of the FHIR-only data access layer for the Patients app that a FHIR server (or EHR enabled FHIR APIs) must meet in order to integrate with the Patients app, including the following:</span></span>

- <span data-ttu-id="0d00d-117">Expectativas sobre la autenticación de usuarios</span><span class="sxs-lookup"><span data-stu-id="0d00d-117">Expectations around user authentication</span></span>
- <span data-ttu-id="0d00d-118">Requisitos técnicos y técnicos de la interfaz de integración</span><span class="sxs-lookup"><span data-stu-id="0d00d-118">Functional and technical requirements of the integration interface</span></span>
- <span data-ttu-id="0d00d-119">Expectativas sobre rendimiento y fiabilidad</span><span class="sxs-lookup"><span data-stu-id="0d00d-119">Expectations around performance and reliability</span></span>
- <span data-ttu-id="0d00d-120">Expectativas sobre los recursos de FHIR para que la aplicación de pacientes los admita</span><span class="sxs-lookup"><span data-stu-id="0d00d-120">Expectations around FHIR resources to be supported for the Patients app</span></span>
- <span data-ttu-id="0d00d-121">Proceso de integración y modelo de compromiso esperado</span><span class="sxs-lookup"><span data-stu-id="0d00d-121">Process for integration and the expected engagement model</span></span>
- <span data-ttu-id="0d00d-122">Introducción a FHIR y algunos desafíos comunes que se enfrentan a la aplicación de pacientes</span><span class="sxs-lookup"><span data-stu-id="0d00d-122">How to get started with FHIR and some common challenges faced with the Patients app</span></span>
- <span data-ttu-id="0d00d-123">Requisitos futuros para la siguiente iteración de la aplicación pacientes</span><span class="sxs-lookup"><span data-stu-id="0d00d-123">Future requirements for the next iteration of the Patients app</span></span>

> [!NOTE]
> <span data-ttu-id="0d00d-124">En las siguientes secciones, se usa la palabra "Partner" o "Partner Interop" para referirse a cualquier organización de terceros que permita la integración con sistemas HCI para la aplicación de pacientes a través de FHIR y está implementando un servidor de FHIR para que coincida con las especificaciones de la lista.</span><span class="sxs-lookup"><span data-stu-id="0d00d-124">In the following sections, the word "partner" or "Interop partner" is used to refer to any 3rd party Organization that enables integration to EHR systems for the Patients app through FHIR and is implementing a FHIR Server to match the listed specifications.</span></span>

## <a name="functional-and-technical-requirements"></a><span data-ttu-id="0d00d-125">Requisitos técnicos y técnicos</span><span class="sxs-lookup"><span data-stu-id="0d00d-125">Functional and technical requirements</span></span>  

### <a name="authentication"></a><span data-ttu-id="0d00d-126">Autenticación</span><span class="sxs-lookup"><span data-stu-id="0d00d-126">Authentication</span></span>  

<span data-ttu-id="0d00d-127">La autorización en el nivel de la aplicación *sin compatibilidad para autorización a nivel de usuario* es la forma más común admitida para realizar transformaciones de datos y exponer conexiones a datos de EHR a través de FHIR, aunque el sistema HCI pueda implementar la autorización a nivel de usuario.</span><span class="sxs-lookup"><span data-stu-id="0d00d-127">App-level authorization *with no support for user level authorization* is the more commonly supported way to perform data transformations and expose connections to EHR data through FHIR, even though the EHR system might implement user level authorization.</span></span> <span data-ttu-id="0d00d-128">El servicio de interoperabilidad (asociado) obtiene acceso elevado a los datos de EHR y cuando exponen los mismos datos que los recursos de FHIR apropiados no hay ningún contexto de autorización pasado al consumidor del servicio de interoperabilidad (la aplicación de pacientes) que se integra con el servicio o la plataforma de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="0d00d-128">The Interop Service (Partner) gets elevated access to the EHR data, and when they expose the same data as the appropriate FHIR resources there is no authorization context passed on to the Interop Service Consumer (the Patients app) integrating with the Interop Service or Platform.</span></span> <span data-ttu-id="0d00d-129">La aplicación de pacientes no podrá exigir la autorización de nivel de usuario, pero admite la autenticación de aplicaciones entre la aplicación de pacientes y el servicio del colaborador de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="0d00d-129">The Patients app will not be able to enforce user level authorization, but does support application to application authentication between the Patients app and the Interop partner's service.</span></span>

<span data-ttu-id="0d00d-130">La aplicación para el modelo de autenticación de aplicaciones se describe a continuación:</span><span class="sxs-lookup"><span data-stu-id="0d00d-130">The Application to Application authentication model is described below:</span></span>

<span data-ttu-id="0d00d-131">La autenticación de servicio a servicio debe realizarse a través del [flujo de credenciales de cliente](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)OAuth 2,0.</span><span class="sxs-lookup"><span data-stu-id="0d00d-131">Service to service authentication should be done through OAuth 2.0 [Client Credential flow](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/).</span></span> <span data-ttu-id="0d00d-132">El servicio asociado debe proporcionar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0d00d-132">The partner service needs to provide the following:</span></span>

1. <span data-ttu-id="0d00d-133">El servicio asociado permite a la aplicación de pacientes crear una cuenta con el socio, lo que permite a la aplicación de pacientes generar y poseer client_id y client_secret administrados a través de un portal de registro de autenticación en el servidor de autenticación del socio.</span><span class="sxs-lookup"><span data-stu-id="0d00d-133">The Partner service enables the Patients app to create an account with the Partner, which enables the Patients app to generate and own client_id and client_secret, managed via an Auth registration portal on the partner's Authentication server.</span></span>
2. <span data-ttu-id="0d00d-134">El servicio asociado posee el sistema de autenticación/autorización, que acepta y verifica (autentica) las credenciales de cliente proporcionadas y devuelve un token de acceso con el sugerencia de inquilino en el ámbito, como se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="0d00d-134">The Partner service owns the Authentication/Authorization system, which accepts and verifies (authenticates) the client credentials provided and gives back an access token with tenant hint in scope, as described below.</span></span>
3. <span data-ttu-id="0d00d-135">Por razones de seguridad o en el caso de una infracción secreta, la aplicación de pacientes puede volver a generar el secreto e invalidar o eliminar el secreto anterior (el ejemplo de lo mismo está disponible en el portal de Azure: registro de la aplicación AAD).</span><span class="sxs-lookup"><span data-stu-id="0d00d-135">For security reasons or in a case of a secret breach, the Patients app can re-generate the secret and invalidate or delete the old secret (example of the same is available in Azure Portal - AAD App Registration).</span></span>
4. <span data-ttu-id="0d00d-136">El punto final de metadatos que hospeda la instrucción de conformidad debe ser no autenticado, debe ser accesible sin un token de autenticación.</span><span class="sxs-lookup"><span data-stu-id="0d00d-136">The metadata endpoint hosting the conformance statement should be un-authenticated, it should be accessible without authentication token.</span></span>
5. <span data-ttu-id="0d00d-137">El servicio asociado proporciona el punto final del token de la aplicación de pacientes para solicitar un token de acceso con un flujo de credenciales de cliente.</span><span class="sxs-lookup"><span data-stu-id="0d00d-137">The Partner service provides the token endpoint for the Patients app to request an access token using a client credential flow.</span></span> <span data-ttu-id="0d00d-138">La dirección URL del token como por servidor de autorización debe formar parte de la instrucción de conformidad (Capability) FHIR capturada de los metadatos en el servidor de FHIR como en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0d00d-138">The token url as per authorization server should be part of the FHIR conformance (capability) statement fetched from metadata on the FHIR server as in this example:</span></span>

* * *
    <span data-ttu-id="0d00d-139">{"resourceType": "CapabilityStatement",.</span><span class="sxs-lookup"><span data-stu-id="0d00d-139">{ "resourceType": "CapabilityStatement", .</span></span>
        <span data-ttu-id="0d00d-140">.</span><span class="sxs-lookup"><span data-stu-id="0d00d-140">.</span></span>
        <span data-ttu-id="0d00d-141">.</span><span class="sxs-lookup"><span data-stu-id="0d00d-141">.</span></span>
        <span data-ttu-id="0d00d-142">"Rest": [{"MODE": "Server", "Security": {"Extension": [{"Extension": [{"URL": "token", "valueUri": " https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/token "}, {"URL": "autorizar", "valueUri": ""} "," URL ":" https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/authorize http://fhir-registry.smarthealthit.org/StructureDefinition/oauth-uris "}]," servicio ": [{" codificación ": [{" System ":" https://hl7.org/fhir/ValueSet/restful-security-service "," Code ":" OAuth "}]}]},.</span><span class="sxs-lookup"><span data-stu-id="0d00d-142">"rest": [ { "mode": "server", "security": { "extension": [ { "extension": [ { "url": "token", "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/token" }, { "url": "authorize", "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/authorize" } ], "url": "http://fhir-registry.smarthealthit.org/StructureDefinition/oauth-uris" } ], "service": [ { "coding": [ { "system": "https://hl7.org/fhir/ValueSet/restful-security-service", "code": "OAuth" } ] } ] }, .</span></span>
                <span data-ttu-id="0d00d-143">.</span><span class="sxs-lookup"><span data-stu-id="0d00d-143">.</span></span>
                <span data-ttu-id="0d00d-144">.</span><span class="sxs-lookup"><span data-stu-id="0d00d-144">.</span></span>
            <span data-ttu-id="0d00d-145">} ] }</span><span class="sxs-lookup"><span data-stu-id="0d00d-145">} ] }</span></span>

* * *

<span data-ttu-id="0d00d-146">Una solicitud para un token de acceso consta de los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="0d00d-146">A request for an access token consists of the following parameters:</span></span>

* * *

    <span data-ttu-id="0d00d-147">PUBLICAR/token HTTP/1.1 host: authorization-server.com</span><span class="sxs-lookup"><span data-stu-id="0d00d-147">POST /token HTTP/1.1 Host: authorization-server.com</span></span>

    <span data-ttu-id="0d00d-148">Grant-Type = client_credentials &client_id = xxxxxxxxxx &client_secret = xxxxxxxxxx</span><span class="sxs-lookup"><span data-stu-id="0d00d-148">grant-type=client_credentials &client_id=xxxxxxxxxx &client_secret=xxxxxxxxxx</span></span>

* * *

<span data-ttu-id="0d00d-149">El servicio asociado proporciona la client_id y client_secret para la aplicación de pacientes, administrada a través de un portal de registro de autenticación en el lado del socio.</span><span class="sxs-lookup"><span data-stu-id="0d00d-149">The Partner service provides the client_id and client_secret for Patients app, managed via an Auth registration portal on the partner's side.</span></span> <span data-ttu-id="0d00d-150">El servicio asociado proporciona el extremo para solicitar el token de acceso mediante un flujo de credenciales de cliente.</span><span class="sxs-lookup"><span data-stu-id="0d00d-150">The Partner service provides the endpoint to request access token using a client credential flow.</span></span> <span data-ttu-id="0d00d-151">Una respuesta correcta debe incluir los parámetros token_type, access_token y expires_in.</span><span class="sxs-lookup"><span data-stu-id="0d00d-151">A successful response must include the token_type, access_token and expires_in parameters.</span></span>

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a><span data-ttu-id="0d00d-152">Enrutamiento: asignación de inquilino de AAD al extremo de proveedor</span><span class="sxs-lookup"><span data-stu-id="0d00d-152">Routing: Mapping AAD Tenant to the Provider endpoint</span></span>

<span data-ttu-id="0d00d-153">La aplicación patients se conecta a un servicio asociado a través de un único punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="0d00d-153">The Patients app connects to a partner service through a single endpoint.</span></span> <span data-ttu-id="0d00d-154">El servicio asociado posee y mantiene un mecanismo para asignar a cada cliente de Microsoft (ID de inquilino de AAD) a un proveedor de servicios de salud respectivo (servidor FHIR) con el que está trabajando el servicio asociado.</span><span class="sxs-lookup"><span data-stu-id="0d00d-154">The Partner service owns and maintains a mechanism to map each Microsoft customer (AAD Tenant ID) to a respective healthcare Provider (FHIR server) that the Partner service is working with.</span></span>

<span data-ttu-id="0d00d-155">La asignación del inquilino de AAD a un extremo de proveedor usa el identificador de inquilino de AAD (GUID).</span><span class="sxs-lookup"><span data-stu-id="0d00d-155">Mapping the AAD tenant to a provider endpoint uses the AAD Tenant ID (GUID).</span></span> <span data-ttu-id="0d00d-156">La aplicación patients pasa el identificador de inquilino en el ámbito, mientras solicita un token de acceso para cada solicitud.</span><span class="sxs-lookup"><span data-stu-id="0d00d-156">The Patients app passes the Tenant ID in scope, while requesting an access-token for each request.</span></span> <span data-ttu-id="0d00d-157">El servicio asociado mantiene la asignación de identificador de inquilino en el extremo de proveedor y redirige las solicitudes a un extremo de proveedor basándose en el identificador de inquilino.</span><span class="sxs-lookup"><span data-stu-id="0d00d-157">The Partner service keeps the mapping of Tenant ID to Provider endpoint and redirects requests to a provider endpoint based on the Tenant ID.</span></span> <span data-ttu-id="0d00d-158">Para ello, el socio admite la configuración en su extremo (manualmente o a través de un portal como parte de la incorporación de organizaciones de proveedores a su plataforma de interoperabilidad).</span><span class="sxs-lookup"><span data-stu-id="0d00d-158">To do this, the partner supports the configuration on their end (manually or via a portal as part of onboarding of provider organizations to their Interop Platform).</span></span>

<span data-ttu-id="0d00d-159">A continuación se muestra el flujo de trabajo de autenticación y enrutamiento:</span><span class="sxs-lookup"><span data-stu-id="0d00d-159">The Authentication and Routing workflow is shown below:</span></span>

![Diagrama del flujo de trabajo de autenticación y enrutamiento](../../media/Patient-app-6.png)

1. <span data-ttu-id="0d00d-161">Solicitud de token de acceso de aplicación mediante el envío de:</span><span class="sxs-lookup"><span data-stu-id="0d00d-161">Request for app access token by sending:</span></span>
 
        {   grant_type: client_credentials,
            client_id: xxxxxx, 
            client_secret: xxxxxx,
            scope: {Provider Identifier, Ex: tenant ID}
        }

2. <span data-ttu-id="0d00d-162">Responder con un token de aplicación:</span><span class="sxs-lookup"><span data-stu-id="0d00d-162">Reply with an app token:</span></span>

        {  access_token: {JWT, with scope: tenant ID},
           expires_in: 156678,
           token_type: "Bearer",
        }

3. <span data-ttu-id="0d00d-163">Solicitar datos protegidos con token de acceso.</span><span class="sxs-lookup"><span data-stu-id="0d00d-163">Request protected data with Access token.</span></span>
4. <span data-ttu-id="0d00d-164">Mensaje de autorización: seleccione el servidor de FHIR apropiado al que desea enrutar desde el identificador de inquilino en el ámbito</span><span class="sxs-lookup"><span data-stu-id="0d00d-164">Authorization message: Select the appropriate FHIR server to route to from tenant ID in scope</span></span>
5. <span data-ttu-id="0d00d-165">Envía los datos protegidos por la aplicación desde el servidor de FHIR autorizado después de autenticarse con el token de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0d00d-165">Sends the app protected  data from the authorized FHIR server after authenticating with the app token.</span></span>

## <a name="interfaces"></a><span data-ttu-id="0d00d-166">Interactúa</span><span class="sxs-lookup"><span data-stu-id="0d00d-166">Interfaces</span></span>

<span data-ttu-id="0d00d-167">Las llamadas y los campos específicos usados por la aplicación de pacientes se documentan en los artículos siguientes.</span><span class="sxs-lookup"><span data-stu-id="0d00d-167">Specific calls and fields used by the Patients app are documented in the following articles.</span></span> <span data-ttu-id="0d00d-168">Seleccione la interfaz aplicable a las API de FHIR Server/FHIR.</span><span class="sxs-lookup"><span data-stu-id="0d00d-168">Select the interface applicable to your FHIR server/FHIR APIs.</span></span>

- [<span data-ttu-id="0d00d-169">Especificación de la interfaz DSTU2</span><span class="sxs-lookup"><span data-stu-id="0d00d-169">DSTU2 interface specification</span></span>](dstu2-interface.md)
- [<span data-ttu-id="0d00d-170">Especificación de la interfaz STU3</span><span class="sxs-lookup"><span data-stu-id="0d00d-170">STU3 interface specification</span></span>](stu3-interface.md)

## <a name="performance-and-reliability"></a><span data-ttu-id="0d00d-171">Rendimiento y confiabilidad</span><span class="sxs-lookup"><span data-stu-id="0d00d-171">Performance and Reliability</span></span>

<span data-ttu-id="0d00d-172">Mientras la aplicación patients está en la vista previa privada, no hay ninguna garantía en el rendimiento de un extremo a otro.</span><span class="sxs-lookup"><span data-stu-id="0d00d-172">While the Patients app is in private preview, there are no guarantees on the end-to-end performance.</span></span> <span data-ttu-id="0d00d-173">Entre los factores en el rendimiento se incluyen las latencias relativas de todos los saltos implicados en el flujo de trabajo, empezando desde el EHR del entorno del sistema, hasta el socio de interoperabilidad y su infra, incluido el servidor de FHIR y el ecosistema y la aplicación de pacientes de Office 365.</span><span class="sxs-lookup"><span data-stu-id="0d00d-173">Factors in performance include the relative latencies of all the hops involved in the workflow, starting from the EHR in the health system's environment, to the Interop partner and their infra, including the FHIR Server and across to the Office 365 ecosystem and Patients app.</span></span>

![Ilustración del rendimiento de los socios de interoperabilidad](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a><span data-ttu-id="0d00d-175">Introducción a FHIR</span><span class="sxs-lookup"><span data-stu-id="0d00d-175">Get started with FHIR</span></span>  

<span data-ttu-id="0d00d-176">Si es nuevo en FHIR y necesita acceder fácilmente a un servidor de FHIR que pueda exponer a la interfaz de integración de Microsoft Teams HCI, Microsoft tiene un servidor de FHIR de código abierto para que todos los programadores lo usen.</span><span class="sxs-lookup"><span data-stu-id="0d00d-176">If you're new to FHIR and need easy access to a FHIR Server that you can expose to the Microsoft Teams EHR integration interface, Microsoft has an open-source FHIR Server available for all developers to use.</span></span> <span data-ttu-id="0d00d-177">Para obtener más información sobre el servidor de FHIR de código abierto de Microsoft, consulte el artículo [What is FHIR Server for Azure](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) e impleméntelo para sus organizaciones.</span><span class="sxs-lookup"><span data-stu-id="0d00d-177">Please see the [What is FHIR Server for Azure](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) article to learn more about the open source FHIR Server available from Microsoft and deploy it for your organizations.</span></span>

<span data-ttu-id="0d00d-178">También puede usar el entorno HSPC de espacio aislado abierto de Open para crear un EHR que también admita un servidor de FHIR abierto y use esta opción para familiarizarse con la aplicación de pacientes.</span><span class="sxs-lookup"><span data-stu-id="0d00d-178">You can also use the HSPC Open sandbox EHR environment to create an an EHR which also supports an open FHIR Server and use this to play around with the Patients app.</span></span> <span data-ttu-id="0d00d-179">Le recomendamos que lea la [documentación del espacio aislado de HSPC](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox).</span><span class="sxs-lookup"><span data-stu-id="0d00d-179">We recommend that you read through the [HSPC Sandbox documentation](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox).</span></span> <span data-ttu-id="0d00d-180">El espacio aislado no solo ofrece una forma sencilla, orientada a la interfaz de usuario y sencilla de usar para crear, agregar y editar pacientes, sino que también le ofrece varias muestras para comenzar.</span><span class="sxs-lookup"><span data-stu-id="0d00d-180">Not only does the sandbox provide an easy, UI oriented, and user friendly way of creating, adding and editing Patients, it also gives you several samples to get started.</span></span> 