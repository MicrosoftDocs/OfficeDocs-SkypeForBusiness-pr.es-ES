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
description: Obtenga información sobre la integración de registros sanitarios electrónicos en la aplicación Pacientes de Microsoft Teams con las API de FLC.
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 594375959a8cd7cbbfc21c6b9d5ceb6c0f8a8dac
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803548"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a><span data-ttu-id="2a113-103">Integración de registros sanitarios electrónicos en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2a113-103">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="2a113-104">A partir del 30 de octubre de 2020, la aplicación Pacientes se ha retirado y reemplazado por la [aplicación Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) en Teams.</span><span class="sxs-lookup"><span data-stu-id="2a113-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="2a113-105">Los datos de la aplicación Pacientes se almacenan en el buzón de grupo del grupo de Office 365 que copia de seguridad del equipo.</span><span class="sxs-lookup"><span data-stu-id="2a113-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="2a113-106">Todos los datos asociados a la aplicación Pacientes se conservan en este grupo, pero ya no se puede acceder a ellos a través de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="2a113-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="2a113-107">Los usuarios pueden volver a crear sus listas con la [aplicación Listas.](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)</span><span class="sxs-lookup"><span data-stu-id="2a113-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="2a113-108">Con Listas, los equipos de cuidado de su organización sanitaria pueden crear listas de pacientes para situaciones que van desde rounds y reuniones de equipo interdisciplinarias hasta la supervisión general del paciente.</span><span class="sxs-lookup"><span data-stu-id="2a113-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="2a113-109">Consulte la plantilla Pacientes en Listas para empezar.</span><span class="sxs-lookup"><span data-stu-id="2a113-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="2a113-110">Para obtener más información sobre cómo administrar la aplicación Listas en su organización, vea [Administrar la aplicación Listas.](../../manage-lists-app.md)</span><span class="sxs-lookup"><span data-stu-id="2a113-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="2a113-111">Este artículo está destinado a un desarrollador de TI para la salud general interesado en usar las API de FLC, además de un sistema de información médica, para conectarse a Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2a113-111">This article is intended for a general healthcare IT developer interested in using FHIR APIs on top of a medical information system to connect to Microsoft Teams.</span></span> <span data-ttu-id="2a113-112">Esto habilitaría escenarios de coordinación de cuidados que coincidan con las necesidades de una organización sanitaria.</span><span class="sxs-lookup"><span data-stu-id="2a113-112">This would enable care coordination scenarios that match the needs of a healthcare organization.</span></span>

<span data-ttu-id="2a113-113">En los artículos vinculados se documentan las especificaciones de la interfaz de FLC para la aplicación Microsoft Teams Pacientes y las secciones siguientes explican lo que se requiere para configurar un servidor FLC y conectarse a la aplicación Pacientes en su entorno de desarrollo o inquilino.</span><span class="sxs-lookup"><span data-stu-id="2a113-113">Linked articles document the FHIR interface specifications for the Microsoft Teams Patients app, and following sections explain what is required for setting up a FHIR server and connecting to the Patients app in your development environment or tenant.</span></span> <span data-ttu-id="2a113-114">También debe estar familiarizado con la documentación del servidor FCONTR que ha elegido, que debe ser una de las opciones admitidas:</span><span class="sxs-lookup"><span data-stu-id="2a113-114">You will also need to be familiar with the documentation of the FHIR server you have chosen, which must be one of the supported options:</span></span>

- <span data-ttu-id="2a113-115">Datica (a través de su [oferta de CMI)](https://datica.com/compliant-managed-integration/)</span><span class="sxs-lookup"><span data-stu-id="2a113-115">Datica (through their [CMI](https://datica.com/compliant-managed-integration/) offering)</span></span>
- <span data-ttu-id="2a113-116">Infor Copleaf (a través del [puente Infor FCONTR)](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html)</span><span class="sxs-lookup"><span data-stu-id="2a113-116">Infor Cloverleaf (through the [Infor FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span></span>
- <span data-ttu-id="2a113-117">Redxa (a través [del servidor R^FCONTR)](https://www.redoxengine.com/fhir/)</span><span class="sxs-lookup"><span data-stu-id="2a113-117">Redox (through the [R^FHIR server](https://www.redoxengine.com/fhir/))</span></span>
- <span data-ttu-id="2a113-118">Dapasoft (a [través de Corolar en FCONTR)](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/)</span><span class="sxs-lookup"><span data-stu-id="2a113-118">Dapasoft (through [Corolar on FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span></span>

> [!NOTE]
> <span data-ttu-id="2a113-119">Este proceso no incluye los pasos que usan el centro de administración de Microsoft Teams o los cmdlets de PowerShell para habilitar las características.</span><span class="sxs-lookup"><span data-stu-id="2a113-119">This process does not includes steps that use the Microsoft Teams admin center or PowerShell cmdlets to enable features.</span></span> <span data-ttu-id="2a113-120">La configuración se realiza por completo en el lado del servidor/servicio FCONTRA y en el cliente de la aplicación Pacientes.</span><span class="sxs-lookup"><span data-stu-id="2a113-120">The configuration is entirely done on the FHIR server/service side and in the Patients app client.</span></span>

<span data-ttu-id="2a113-121">A continuación se muestra la arquitectura de la aplicación Pacientes:</span><span class="sxs-lookup"><span data-stu-id="2a113-121">Illustrated below is the architecture of the Patients app:</span></span>

![Diagrama de la arquitectura de la aplicación Pacientes](../../media/patients-app-architecture.png)

<span data-ttu-id="2a113-123">En las siguientes secciones se explican los requisitos de la capa de acceso de datos solo de FCONTR para la aplicación Pacientes que debe cumplir un servidor FCONTR (o API de F LDAP habilitada para EHR) para realizar la integración con la aplicación Pacientes, lo que incluye lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2a113-123">The following sections explain the requirements of the FHIR-only data access layer for the Patients app that a FHIR server (or EHR enabled FHIR APIs) must meet in order to integrate with the Patients app, including the following:</span></span>

- <span data-ttu-id="2a113-124">Expectativas sobre la autenticación de usuario</span><span class="sxs-lookup"><span data-stu-id="2a113-124">Expectations around user authentication</span></span>
- <span data-ttu-id="2a113-125">Requisitos técnicos y funcionales de la interfaz de integración</span><span class="sxs-lookup"><span data-stu-id="2a113-125">Functional and technical requirements of the integration interface</span></span>
- <span data-ttu-id="2a113-126">Expectativas en torno al rendimiento y la confiabilidad</span><span class="sxs-lookup"><span data-stu-id="2a113-126">Expectations around performance and reliability</span></span>
- <span data-ttu-id="2a113-127">Expectativas en torno a los recursos de FLC para que puedan ser compatibles con la aplicación Pacientes</span><span class="sxs-lookup"><span data-stu-id="2a113-127">Expectations around FHIR resources to be supported for the Patients app</span></span>
- <span data-ttu-id="2a113-128">Proceso de integración y del modelo de participación esperado</span><span class="sxs-lookup"><span data-stu-id="2a113-128">Process for integration and the expected engagement model</span></span>
- <span data-ttu-id="2a113-129">Cómo comenzar a usar la FCONTR y algunos de los desafíos comunes que se deben enfrentar con la aplicación Pacientes</span><span class="sxs-lookup"><span data-stu-id="2a113-129">How to get started with FHIR and some common challenges faced with the Patients app</span></span>
- <span data-ttu-id="2a113-130">Requisitos futuros para la siguiente iteración de la aplicación Pacientes</span><span class="sxs-lookup"><span data-stu-id="2a113-130">Future requirements for the next iteration of the Patients app</span></span>

> [!NOTE]
> <span data-ttu-id="2a113-131">En las secciones siguientes, se usa la palabra "partner" o "interoperabilidad" para hacer referencia a cualquier organización de terceros que permita la integración con sistemas EHR para la aplicación Pacientes a través de FLC y está implementando un servidor FLC para que coincida con las especificaciones enumeradas.</span><span class="sxs-lookup"><span data-stu-id="2a113-131">In the following sections, the word "partner" or "Interop partner" is used to refer to any 3rd party Organization that enables integration to EHR systems for the Patients app through FHIR and is implementing a FHIR Server to match the listed specifications.</span></span>

## <a name="functional-and-technical-requirements"></a><span data-ttu-id="2a113-132">Requisitos técnicos y funcionales</span><span class="sxs-lookup"><span data-stu-id="2a113-132">Functional and technical requirements</span></span>  

### <a name="authentication"></a><span data-ttu-id="2a113-133">Autenticación</span><span class="sxs-lookup"><span data-stu-id="2a113-133">Authentication</span></span>  

<span data-ttu-id="2a113-134">La autorización a nivel de aplicación *sin* soporte para autorización a nivel de usuario es la forma más común de realizar transformaciones de datos y exponer conexiones a datos EHR a través de FCONTR, aunque el sistema EHR pueda implementar la autorización a nivel de usuario.</span><span class="sxs-lookup"><span data-stu-id="2a113-134">App-level authorization *with no support for user level authorization* is the more commonly supported way to perform data transformations and expose connections to EHR data through FHIR, even though the EHR system might implement user level authorization.</span></span> <span data-ttu-id="2a113-135">El servicio de interoperabilidad (partner) obtiene acceso elevado a los datos EHR y, cuando exponen los mismos datos que los recursos de FLC adecuados, no se aplica ningún contexto de autorización al consumidor del servicio de interoperabilidad (la aplicación Pacientes) para la integración con el Servicio de interoperabilidad o la plataforma.</span><span class="sxs-lookup"><span data-stu-id="2a113-135">The Interop Service (Partner) gets elevated access to the EHR data, and when they expose the same data as the appropriate FHIR resources there is no authorization context passed on to the Interop Service Consumer (the Patients app) integrating with the Interop Service or Platform.</span></span> <span data-ttu-id="2a113-136">La aplicación Pacientes no podrá exigir la autorización a nivel de usuario, pero admite la aplicación para la autenticación de aplicación entre la aplicación Pacientes y el servicio del partner de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="2a113-136">The Patients app will not be able to enforce user level authorization, but does support application to application authentication between the Patients app and the Interop partner's service.</span></span>

<span data-ttu-id="2a113-137">El modelo de autenticación de aplicación a aplicación se describe a continuación:</span><span class="sxs-lookup"><span data-stu-id="2a113-137">The Application to Application authentication model is described below:</span></span>

<span data-ttu-id="2a113-138">El servicio de autenticación de servicio debe [](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)realizarse a través del flujo de credenciales de cliente de OAuth 2.0.</span><span class="sxs-lookup"><span data-stu-id="2a113-138">Service to service authentication should be done through OAuth 2.0 [Client Credential flow](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/).</span></span> <span data-ttu-id="2a113-139">El servicio de asociados debe proporcionar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2a113-139">The partner service needs to provide the following:</span></span>

1. <span data-ttu-id="2a113-140">El servicio de partner permite a la aplicación Pacientes crear una cuenta con el partner, que permite que la aplicación Pacientes genere y sea propietario de client_id y client_secret, administrados mediante un portal de registro de autenticación en el servidor de autenticación del partner.</span><span class="sxs-lookup"><span data-stu-id="2a113-140">The Partner service enables the Patients app to create an account with the Partner, which enables the Patients app to generate and own client_id and client_secret, managed via an Auth registration portal on the partner's Authentication server.</span></span>

2. <span data-ttu-id="2a113-141">El servicio de partner es el propietario del sistema de autenticación/autorización, que acepta y comprueba (autentica) las credenciales de cliente proporcionadas y devuelve un token de acceso con sugerencia de inquilino en el ámbito, como se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="2a113-141">The Partner service owns the Authentication/Authorization system, which accepts and verifies (authenticates) the client credentials provided and gives back an access token with tenant hint in scope, as described below.</span></span>

3. <span data-ttu-id="2a113-142">Por motivos de seguridad o en caso de infracción de secreto, la aplicación Pacientes puede volver a generar el secreto e invalidarlo o eliminarlo (por ejemplo, el mismo está disponible en Azure Portal - Registro de aplicaciones de AAD).</span><span class="sxs-lookup"><span data-stu-id="2a113-142">For security reasons or in a case of a secret breach, the Patients app can re-generate the secret and invalidate or delete the old secret (example of the same is available in Azure Portal - AAD App Registration).</span></span>

4. <span data-ttu-id="2a113-143">El extremo de metadatos que hospeda la instrucción de conformidad debe ser no autenticado, debe ser accesible sin el token de autenticación.</span><span class="sxs-lookup"><span data-stu-id="2a113-143">The metadata endpoint hosting the conformance statement should be un-authenticated, it should be accessible without authentication token.</span></span>

5. <span data-ttu-id="2a113-144">El servicio de asociado proporciona el punto de conexión del token para la aplicación Pacientes para solicitar un token de acceso mediante un flujo de credenciales de cliente.</span><span class="sxs-lookup"><span data-stu-id="2a113-144">The Partner service provides the token endpoint for the Patients app to request an access token using a client credential flow.</span></span> <span data-ttu-id="2a113-145">La dirección URL del token según el servidor de autorización debe formar parte de la instrucción de conformidad (funcionalidad) F LDAP capturada de los metadatos del servidor F LDAP, como en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2a113-145">The token URL as per authorization server should be part of the FHIR conformance (capability) statement fetched from metadata on the FHIR server as in this example:</span></span>

    ```
    {
        "resourceType": "CapabilityStatement",
        .
        .
        .
        "rest": [
            {
                "mode": "server",
                "security": {
                    "extension": [
                        {
                            "extension": [
                                {
                                    "url": "token",
                                    "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/token"
                                },
                                {
                                    "url": "authorize",
                                    "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/authorize"
                                }
                            ],
                            "url": "http://fhir-registry.smarthealthit.org/StructureDefinition/oauth-uris"
                        }
                    ],
                    "service": [
                        {
                            "coding": [
                                {
                                    "system": "https://hl7.org/fhir/ValueSet/restful-security-service",
                                    "code": "OAuth"
                                }
                            ]
                        }
                    ]
                },
                .
                .
                .
            }
        ]
    }
    ```

<span data-ttu-id="2a113-146">Una solicitud de un token de acceso consta de los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="2a113-146">A request for an access token consists of the following parameters:</span></span>

```http
POST /token HTTP/1.1
Host: authorization-server.com

grant-type=client_credentials
&client_id=xxxxxxxxxx
&client_secret=xxxxxxxxxx
```

<span data-ttu-id="2a113-147">El servicio de partners proporciona client_id y client_secret para pacientes, administrada a través de un portal de registro de autenticación del lado del partner.</span><span class="sxs-lookup"><span data-stu-id="2a113-147">The Partner service provides the client_id and client_secret for Patients app, managed via an Auth registration portal on the partner's side.</span></span> <span data-ttu-id="2a113-148">El servicio de asociado proporciona el punto de conexión para solicitar el token de acceso mediante un flujo de credenciales de cliente.</span><span class="sxs-lookup"><span data-stu-id="2a113-148">The Partner service provides the endpoint to request access token using a client credential flow.</span></span> <span data-ttu-id="2a113-149">Una respuesta correcta debe incluir los parámetros token_type, access_token y expires_in correctos.</span><span class="sxs-lookup"><span data-stu-id="2a113-149">A successful response must include the token_type, access_token and expires_in parameters.</span></span>

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a><span data-ttu-id="2a113-150">Enrutamiento: asignación del inquilino de AAD al punto de conexión del proveedor</span><span class="sxs-lookup"><span data-stu-id="2a113-150">Routing: Mapping AAD Tenant to the Provider endpoint</span></span>

<span data-ttu-id="2a113-151">La aplicación Pacientes se conecta a un servicio asociado a través de un único punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="2a113-151">The Patients app connects to a partner service through a single endpoint.</span></span> <span data-ttu-id="2a113-152">El servicio de partners es propietario y mantiene un mecanismo para asignar cada cliente de Microsoft (id. de inquilino de AAD) a un proveedor de servicios médicos correspondiente (servidor FLC) con el que el servicio de asociado esté trabajando.</span><span class="sxs-lookup"><span data-stu-id="2a113-152">The Partner service owns and maintains a mechanism to map each Microsoft customer (AAD Tenant ID) to a respective healthcare Provider (FHIR server) that the Partner service is working with.</span></span>

<span data-ttu-id="2a113-153">Al asignar el inquilino de AAD a un punto de conexión de proveedor se usa el id. de inquilino de AAD (GUID).</span><span class="sxs-lookup"><span data-stu-id="2a113-153">Mapping the AAD tenant to a provider endpoint uses the AAD Tenant ID (GUID).</span></span> <span data-ttu-id="2a113-154">La aplicación Pacientes pasa el id. de inquilino dentro del ámbito, mientras solicita un token de acceso para cada solicitud.</span><span class="sxs-lookup"><span data-stu-id="2a113-154">The Patients app passes the Tenant ID in scope, while requesting an access-token for each request.</span></span> <span data-ttu-id="2a113-155">El servicio de partner mantiene la asignación del id. de inquilino al punto de conexión del proveedor y redirige las solicitudes a un punto de conexión del proveedor en función del id. de inquilino.</span><span class="sxs-lookup"><span data-stu-id="2a113-155">The Partner service keeps the mapping of Tenant ID to Provider endpoint and redirects requests to a provider endpoint based on the Tenant ID.</span></span> <span data-ttu-id="2a113-156">Para ello, el partner admite la configuración por su parte (manualmente o a través de un portal como parte de la incorporación de las organizaciones proveedoras a su plataforma de interoperabilidad).</span><span class="sxs-lookup"><span data-stu-id="2a113-156">To do this, the partner supports the configuration on their end (manually or via a portal as part of onboarding of provider organizations to their Interop Platform).</span></span>

<span data-ttu-id="2a113-157">El flujo de trabajo de autenticación y enrutamiento se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="2a113-157">The Authentication and Routing workflow is shown below:</span></span>

![Diagrama del flujo de trabajo de autenticación y enrutamiento](../../media/Patient-app-6.png)

1. <span data-ttu-id="2a113-159">Solicitar token de acceso de aplicaciones enviando:</span><span class="sxs-lookup"><span data-stu-id="2a113-159">Request for app access token by sending:</span></span>
 
    ```
    {   grant_type: client_credentials,
        client_id: xxxxxx, 
        client_secret: xxxxxx,
        scope: {Provider Identifier, Ex: tenant ID}
    }
    ```

2. <span data-ttu-id="2a113-160">Responder con un token de aplicación:</span><span class="sxs-lookup"><span data-stu-id="2a113-160">Reply with an app token:</span></span>

    ```
    {  access_token: {JWT, with scope: tenant ID},
       expires_in: 156678,
       token_type: "Bearer",
    }
    ```

3. <span data-ttu-id="2a113-161">Solicitar datos protegidos con el token de Acceso.</span><span class="sxs-lookup"><span data-stu-id="2a113-161">Request protected data with Access token.</span></span>

4. <span data-ttu-id="2a113-162">Mensaje de autorización: Seleccione el servidor FCONTR adecuado al que enrutar desde el id. de inquilino en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="2a113-162">Authorization message: Select the appropriate FHIR server to route to from tenant ID in scope.</span></span>

5. <span data-ttu-id="2a113-163">Envía los datos protegidos de la aplicación desde el servidor FCONTR autorizado después de autenticar con el token de aplicación.</span><span class="sxs-lookup"><span data-stu-id="2a113-163">Sends the app protected  data from the authorized FHIR server after authenticating with the app token.</span></span>

## <a name="interfaces"></a><span data-ttu-id="2a113-164">Interfaces</span><span class="sxs-lookup"><span data-stu-id="2a113-164">Interfaces</span></span>

<span data-ttu-id="2a113-165">Las llamadas y los campos específicos que usa la aplicación Pacientes se documentan en los artículos siguientes.</span><span class="sxs-lookup"><span data-stu-id="2a113-165">Specific calls and fields used by the Patients app are documented in the following articles.</span></span> <span data-ttu-id="2a113-166">Seleccione la interfaz aplicable a las API del servidor FCONTR/FCONTR.</span><span class="sxs-lookup"><span data-stu-id="2a113-166">Select the interface applicable to your FHIR server/FHIR APIs.</span></span>

- [<span data-ttu-id="2a113-167">Especificación de la interfaz DSTU2</span><span class="sxs-lookup"><span data-stu-id="2a113-167">DSTU2 interface specification</span></span>](dstu2-interface.md)
- [<span data-ttu-id="2a113-168">Especificación de la interfaz STU3</span><span class="sxs-lookup"><span data-stu-id="2a113-168">STU3 interface specification</span></span>](stu3-interface.md)

## <a name="performance-and-reliability"></a><span data-ttu-id="2a113-169">Rendimiento y confiabilidad</span><span class="sxs-lookup"><span data-stu-id="2a113-169">Performance and Reliability</span></span>

<span data-ttu-id="2a113-170">Aunque la aplicación Pacientes está en versión preliminar privada, no hay ninguna garantía sobre el rendimiento de un extremo a otro.</span><span class="sxs-lookup"><span data-stu-id="2a113-170">While the Patients app is in private preview, there are no guarantees on the end-to-end performance.</span></span> <span data-ttu-id="2a113-171">Los factores en el rendimiento incluyen las latencias relativas de todos los saltos implicados en el flujo de trabajo, empezando desde el EHR en el entorno del sistema de mantenimiento hasta el partner de interoperabilidad y su infraestructura, incluido el servidor FLC y hasta el ecosistema de Office 365 y la aplicación Pacientes.</span><span class="sxs-lookup"><span data-stu-id="2a113-171">Factors in performance include the relative latencies of all the hops involved in the workflow, starting from the EHR in the health system's environment, to the Interop partner and their infra, including the FHIR Server and across to the Office 365 ecosystem and Patients app.</span></span>

![Ilustración del rendimiento de partners de interoperabilidad](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a><span data-ttu-id="2a113-173">Introducción a FCONTR</span><span class="sxs-lookup"><span data-stu-id="2a113-173">Get started with FHIR</span></span>  

<span data-ttu-id="2a113-174">Si es nuevo en FCONTR y necesita acceder fácilmente a un servidor FCONTR que puede exponer a la interfaz de integración EHR de Microsoft Teams, Microsoft tiene un servidor F ODBC de código abierto disponible para todos los desarrolladores que los use.</span><span class="sxs-lookup"><span data-stu-id="2a113-174">If you're new to FHIR and need easy access to a FHIR Server that you can expose to the Microsoft Teams EHR integration interface, Microsoft has an open-source FHIR Server available for all developers to use.</span></span> <span data-ttu-id="2a113-175">Consulte el artículo [¿Qué es el servidor F ODBC](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) para Azure? para obtener más información sobre el servidor F LDAP de código abierto disponible en Microsoft e implementarlo para sus organizaciones.</span><span class="sxs-lookup"><span data-stu-id="2a113-175">Please see the [What is FHIR Server for Azure](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) article to learn more about the open source FHIR Server available from Microsoft and deploy it for your organizations.</span></span>

<span data-ttu-id="2a113-176">También puedes usar el entorno de ehr de espacio aislado abierto de HSPC para crear un EHR que también admita un servidor FCONTR abierto y usarlo para jugar con la aplicación Pacientes.</span><span class="sxs-lookup"><span data-stu-id="2a113-176">You can also use the HSPC Open sandbox EHR environment to create an an EHR which also supports an open FHIR Server and use this to play around with the Patients app.</span></span> <span data-ttu-id="2a113-177">Te recomendamos que leas la documentación del espacio aislado [HSPC.](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox)</span><span class="sxs-lookup"><span data-stu-id="2a113-177">We recommend that you read through the [HSPC Sandbox documentation](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox).</span></span> <span data-ttu-id="2a113-178">El espacio aislado no solo ofrece una forma fácil, orientada a la interfaz de usuario y fácil de usar para crear, agregar y editar Pacientes, sino que también ofrece varias muestras para comenzar.</span><span class="sxs-lookup"><span data-stu-id="2a113-178">Not only does the sandbox provide an easy, UI oriented, and user friendly way of creating, adding and editing Patients, it also gives you several samples to get started.</span></span> 
