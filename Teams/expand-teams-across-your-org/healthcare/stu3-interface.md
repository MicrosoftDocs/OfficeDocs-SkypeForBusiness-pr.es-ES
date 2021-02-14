---
title: Interfaz DE LA APLICACIÓN Pacientes y la integración de EHR STU3
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
description: Obtenga información sobre la integración de registros electrónicos de salud en la aplicación Pacientes de Microsoft Teams y la especificación de la interfaz STU3.
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 4e20619badb2509d0a90f396563a98796e718e2f
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803498"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="2f3f5-103">Especificación de la interfaz STU3</span><span class="sxs-lookup"><span data-stu-id="2f3f5-103">STU3 interface specification</span></span>

> [!NOTE]
> <span data-ttu-id="2f3f5-104">A partir del 30 de octubre de 2020, la aplicación Pacientes se ha retirado y reemplazado por la [aplicación Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) en Teams.</span><span class="sxs-lookup"><span data-stu-id="2f3f5-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="2f3f5-105">Los datos de la aplicación Pacientes se almacenan en el buzón de grupo del grupo de Office 365 que copia de seguridad del equipo.</span><span class="sxs-lookup"><span data-stu-id="2f3f5-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="2f3f5-106">Todos los datos asociados a la aplicación Pacientes se conservan en este grupo, pero ya no se puede acceder a ellos a través de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="2f3f5-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="2f3f5-107">Los usuarios pueden volver a crear sus listas con la [aplicación Listas.](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)</span><span class="sxs-lookup"><span data-stu-id="2f3f5-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="2f3f5-108">Con Listas, los equipos de atención al paciente de su organización sanitaria pueden crear listas de pacientes para situaciones que van desde las reuniones interdisciplinarias y las reuniones del equipo hasta la supervisión general del paciente.</span><span class="sxs-lookup"><span data-stu-id="2f3f5-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="2f3f5-109">Consulte la plantilla Pacientes en Listas para empezar.</span><span class="sxs-lookup"><span data-stu-id="2f3f5-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="2f3f5-110">Para obtener más información sobre cómo administrar la aplicación Listas en su organización, vea [Administrar la aplicación Listas.](../../manage-lists-app.md)</span><span class="sxs-lookup"><span data-stu-id="2f3f5-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="2f3f5-111">Configurar o volver a configurar un servidor FCONTR para trabajar con la aplicación Microsoft Teams Patients requiere comprender a qué datos debe tener acceso la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2f3f5-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="2f3f5-112">El servidor FCONTR debe admitir solicitudes POST mediante agrupaciones para los siguientes recursos:</span><span class="sxs-lookup"><span data-stu-id="2f3f5-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="2f3f5-113">Paciente</span><span class="sxs-lookup"><span data-stu-id="2f3f5-113">Patient</span></span>](#patient)
- [<span data-ttu-id="2f3f5-114">Observación</span><span class="sxs-lookup"><span data-stu-id="2f3f5-114">Observation</span></span>](#observation)
- [<span data-ttu-id="2f3f5-115">Condición</span><span class="sxs-lookup"><span data-stu-id="2f3f5-115">Condition</span></span>](#condition)
- [<span data-ttu-id="2f3f5-116">Encounter</span><span class="sxs-lookup"><span data-stu-id="2f3f5-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="2f3f5-117">Programación 365</span><span class="sxs-lookup"><span data-stu-id="2f3f5-117">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="2f3f5-118">Cobertura</span><span class="sxs-lookup"><span data-stu-id="2f3f5-118">Coverage</span></span>](#coverage)
- <span data-ttu-id="2f3f5-119">[Declaración de](#medication-request) medicamentos (reemplaza el MedicationOrder en la versión DSTU2 de la PatientsApp)</span><span class="sxs-lookup"><span data-stu-id="2f3f5-119">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="2f3f5-120">Ubicación (la información necesaria de este recurso se puede incluir en Encounter)</span><span class="sxs-lookup"><span data-stu-id="2f3f5-120">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="2f3f5-121">El recurso paciente es el único recurso obligatorio (sin el que la aplicación no se cargará en absoluto); Sin embargo, se recomienda que el partner implemente soporte técnico para todos los recursos mencionados anteriormente por las especificaciones que se proporcionan a continuación para obtener la mejor experiencia del usuario final con la aplicación Pacientes de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2f3f5-121">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="2f3f5-122">Las consultas de la aplicación Pacientes de Microsoft Teams para más de un recurso deben publicar un paquete (BATCH) de solicitudes en la dirección URL del servidor FCONF.</span><span class="sxs-lookup"><span data-stu-id="2f3f5-122">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="2f3f5-123">El servidor procesará cada solicitud y devolverá un paquete de los recursos que coincidan con cada solicitud.</span><span class="sxs-lookup"><span data-stu-id="2f3f5-123">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="2f3f5-124">Para obtener más información y ejemplos, vea [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) .</span><span class="sxs-lookup"><span data-stu-id="2f3f5-124">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="2f3f5-125">Instrucción Capability</span><span class="sxs-lookup"><span data-stu-id="2f3f5-125">Capability Statement</span></span>

<span data-ttu-id="2f3f5-126">Estos son los campos necesarios mínimos:</span><span class="sxs-lookup"><span data-stu-id="2f3f5-126">These are the minimum required fields:</span></span>

 - <span data-ttu-id="2f3f5-127">REST</span><span class="sxs-lookup"><span data-stu-id="2f3f5-127">REST</span></span>

    - <span data-ttu-id="2f3f5-128">Modo</span><span class="sxs-lookup"><span data-stu-id="2f3f5-128">Mode</span></span>
    - <span data-ttu-id="2f3f5-129">Interacción</span><span class="sxs-lookup"><span data-stu-id="2f3f5-129">Interaction</span></span>
    - <span data-ttu-id="2f3f5-130">Recurso: tipo</span><span class="sxs-lookup"><span data-stu-id="2f3f5-130">Resource: Type</span></span>
    - <span data-ttu-id="2f3f5-131">Seguridad: [Extensión para URI de OAuth](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="2f3f5-131">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
    
 - <span data-ttu-id="2f3f5-132">FcontrVersion (Nuestro código requiere esto para comprender a qué versión debemos cambiar).</span><span class="sxs-lookup"><span data-stu-id="2f3f5-132">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="2f3f5-133">Consulte [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) otros detalles de este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="2f3f5-133">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="2f3f5-134">Paciente</span><span class="sxs-lookup"><span data-stu-id="2f3f5-134">Patient</span></span>

<span data-ttu-id="2f3f5-135">Estos son los campos necesarios mínimos, que son un subconjunto de los campos del perfil del paciente:</span><span class="sxs-lookup"><span data-stu-id="2f3f5-135">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

 - <span data-ttu-id="2f3f5-136">Name.Given</span><span class="sxs-lookup"><span data-stu-id="2f3f5-136">Name.Given</span></span>
 - <span data-ttu-id="2f3f5-137">Name.Family</span><span class="sxs-lookup"><span data-stu-id="2f3f5-137">Name.Family</span></span>
 - <span data-ttu-id="2f3f5-138">Sexo</span><span class="sxs-lookup"><span data-stu-id="2f3f5-138">Gender</span></span>
 - <span data-ttu-id="2f3f5-139">FechaDe Nacimiento</span><span class="sxs-lookup"><span data-stu-id="2f3f5-139">BirthDate</span></span>
 - <span data-ttu-id="2f3f5-140">MRN (identificador)</span><span class="sxs-lookup"><span data-stu-id="2f3f5-140">MRN (Identifier)</span></span>

<span data-ttu-id="2f3f5-141">Además de los campos [Salesforce,](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)para una excelente experiencia del usuario, la aplicación Pacientes también puede leer los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="2f3f5-141">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="2f3f5-142">Name.Use</span><span class="sxs-lookup"><span data-stu-id="2f3f5-142">Name.Use</span></span>
 - <span data-ttu-id="2f3f5-143">Name.Prefix</span><span class="sxs-lookup"><span data-stu-id="2f3f5-143">Name.Prefix</span></span>
 - <span data-ttu-id="2f3f5-144">[GeneralControlctitioner]: la referencia de GeneralCtictitioner debe incluirse en el recurso paciente (solo en el campo de visualización)</span><span class="sxs-lookup"><span data-stu-id="2f3f5-144">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="2f3f5-145">Una búsqueda de recursos usa el método POST en /Patient/_search y los parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="2f3f5-145">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="2f3f5-146">id</span><span class="sxs-lookup"><span data-stu-id="2f3f5-146">id</span></span>
 - <span data-ttu-id="2f3f5-147">family=(busca a todos los pacientes cuyo nombre de familia contiene el valor)</span><span class="sxs-lookup"><span data-stu-id="2f3f5-147">family=(searches for all patients whose family name contains the value)</span></span>
 - <span data-ttu-id="2f3f5-148">given=\<substring></span><span class="sxs-lookup"><span data-stu-id="2f3f5-148">given=\<substring></span></span>
 - <span data-ttu-id="2f3f5-149">fechade nacimiento=(coincidencia exacta)</span><span class="sxs-lookup"><span data-stu-id="2f3f5-149">birthdate=(exact match)</span></span>
 - <span data-ttu-id="2f3f5-150">gender=(values being one of the administrative-gender)</span><span class="sxs-lookup"><span data-stu-id="2f3f5-150">gender=(values being one of the administrative-gender)</span></span>
 - <span data-ttu-id="2f3f5-151">\_recuento (número máximo de resultados que se deben devolver)</span><span class="sxs-lookup"><span data-stu-id="2f3f5-151">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="2f3f5-152">La respuesta debe contener el recuento total de registros devueltos como resultado de la búsqueda y el recuento lo usará la Aplicación Pacientes para limitar el número de registros \_ devueltos.</span><span class="sxs-lookup"><span data-stu-id="2f3f5-152">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="2f3f5-153">identifier=\<mrn></span><span class="sxs-lookup"><span data-stu-id="2f3f5-153">identifier=\<mrn></span></span>

<span data-ttu-id="2f3f5-154">El objetivo es poder buscar y filtrar a un paciente siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="2f3f5-154">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="2f3f5-155">Id.: este es el id. de recurso que tiene cada recurso de FCONTR.</span><span class="sxs-lookup"><span data-stu-id="2f3f5-155">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="2f3f5-156">MRN: este es el identificador real para el paciente que el personal clínico conocería.</span><span class="sxs-lookup"><span data-stu-id="2f3f5-156">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="2f3f5-157">Entendemos que este MRN se basa en el tipo de identificador dentro del recurso de identificador en FCONTR.</span><span class="sxs-lookup"><span data-stu-id="2f3f5-157">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="2f3f5-158">Nombre</span><span class="sxs-lookup"><span data-stu-id="2f3f5-158">Name</span></span>
- <span data-ttu-id="2f3f5-159">Fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="2f3f5-159">Birthdate</span></span>

<span data-ttu-id="2f3f5-160">Vea el siguiente ejemplo de la llamada:</span><span class="sxs-lookup"><span data-stu-id="2f3f5-160">See the following example of the call:</span></span>

```
Request:
POST <fhir-server>/Patient/_search
Request Body:
given=ruth&family=black

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "meta": {
    "lastUpdated": "2019-01-14T23:44:45.052+00:00"
  },
  "type": "searchset",
  "total": 1,
  "link": [
    {
      "relation": "self",
      "url": <fhir-server>/Patient/_search"
    }
  ],
  "entry": [
    {
      "fullUrl": <fhir-server>/Patient/<patient-id>",
      "resource": {
        "resourceType": "Patient",
        "id": "<patient-id>",
        "meta": {
          "versionId": "1",
          "lastUpdated": "2017-10-18T18:32:37.000+00:00"
        },
        "text": {
          "status": "generated",
          "div": "<div>\n        <p>Ruth Black</p>\n      </div>"
        },
        "identifier": [
          {
            "use": "usual",
            "type": {
              "coding": [
                {
                  "system": "https://hl7.org/fhir/v2/0203",
                  "code": "MR",
                  "display": "Medical record number",
                  "userSelected": false
                }
              ],
              "text": "Medical record number"
            },
            "system": "http://hospital.smarthealthit.org",
            "value": "1234567"
          }
        ],
        "active": true,
        "name": [
          {
            "use": "official",
            "family": "Black",
            "given": [
              "Ruth",
              "C."
            ]
          }
        ],
        "telecom": [
          {
            "system": "phone",
            "value": "800-599-2739",
            "use": "home"
          },
          {
            "system": "phone",
            "value": "800-808-7785",
            "use": "mobile"
          },
          {
            "system": "email",
            "value": "ruth.black@example.com"
          }
        ],
        "gender": "female",
        "birthDate": "1951-08-23",
        "address": [
          {
            "use": "home",
            "line": [
              "26 South RdApt 22"
            ],
            "city": "Sapulpa",
            "state": "OK",
            "postalCode": "74066",
            "country": "USA"
          }
        ]
      },
      "search": {
        "mode": "match"
      }
    }
  ]
}
```

```
Request:
GET <fhir-server>/Patient/<patient-id>

Response:
{
  "resourceType": "Patient",
  "id": "<patient-id>",
  "identifier": [
    {
      "use": "usual",
      "type": {
        "coding": [
          {
            "system": "https://hl7.org/fhir/v2/0203",
            "code": "MR",
          }
        ],
        "text": "Medical record number"
      },
      "value": "1234567"
    }
  ],
  "name": [
    {
      "use": "official",
      "family": "Adams",
      "given": [ "Daniel", "X." ]
    }
  ],
  "gender": "male",
  "birthDate": "1925-12-23",
}
```

<span data-ttu-id="2f3f5-161">Consulte [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) otros detalles sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="2f3f5-161">See [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="2f3f5-162">Observación</span><span class="sxs-lookup"><span data-stu-id="2f3f5-162">Observation</span></span>

<span data-ttu-id="2f3f5-163">Estos son los campos necesarios mínimos, que son un subconjunto del perfil [de Vital-Signs grupo.](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)</span><span class="sxs-lookup"><span data-stu-id="2f3f5-163">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

 - <span data-ttu-id="2f3f5-164">Efectivo (fecha y hora o período)</span><span class="sxs-lookup"><span data-stu-id="2f3f5-164">Effective (date time or period)</span></span>
 - <span data-ttu-id="2f3f5-165">Code.Coding.Code</span><span class="sxs-lookup"><span data-stu-id="2f3f5-165">Code.Coding.Code</span></span>
 - <span data-ttu-id="2f3f5-166">ValueQuantity.Value</span><span class="sxs-lookup"><span data-stu-id="2f3f5-166">ValueQuantity.Value</span></span>

<span data-ttu-id="2f3f5-167">Además de los campos Salesforce, para una excelente experiencia del usuario, la aplicación Pacientes también puede leer los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="2f3f5-167">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="2f3f5-168">Code.Coding.Display</span><span class="sxs-lookup"><span data-stu-id="2f3f5-168">Code.Coding.Display</span></span>
 - <span data-ttu-id="2f3f5-169">ValueQuantity.Unit</span><span class="sxs-lookup"><span data-stu-id="2f3f5-169">ValueQuantity.Unit</span></span>

<span data-ttu-id="2f3f5-170">Una búsqueda de recursos usa el método GET y los parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="2f3f5-170">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="2f3f5-171">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="2f3f5-171">patient=\<patient id></span></span>
 - <span data-ttu-id="2f3f5-172">_sort=-date</span><span class="sxs-lookup"><span data-stu-id="2f3f5-172">_sort=-date</span></span>
 - <span data-ttu-id="2f3f5-173">(consultaremos "category=vital-signs") para recuperar la lista de signos vitales.</span><span class="sxs-lookup"><span data-stu-id="2f3f5-173">category (we will query for "category=vital-signs") to retrieve the list of vital signs.</span></span>

<span data-ttu-id="2f3f5-174">Consulte este ejemplo de la llamada:</span><span class="sxs-lookup"><span data-stu-id="2f3f5-174">Refer to this example of the call:</span></span>

```
Request:
GET <fhir-server>/Observation?patient=<patient-id>&category=vital-signs

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 20,
  "entry": [
    {
      "resource": {
        "resourceType": "Observation",
        "id": "<resource-id>",
        "category": [
          {
            "coding": [
              {
                "system": "https://hl7.org/fhir/observation-category",
                "code": "vital-signs"
              }
            ],
          }
        ],
        "code": {
          "coding": [
            {
              "system": "http://loinc.org",
              "code": "8867-4",
              "display": "heart_rate"
            }
          ]
        },
        "effectiveDateTime": "2009-04-08T00:00:00-06:00",
        "valueQuantity": {
          "value": 72.0,
          "unit": "{beats}/min",
          "system": "http://unitsofmeasure.org",
        }
      }
    },
    .
    .
    .
  ]
}
```

<span data-ttu-id="2f3f5-175">Consulte [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) otros detalles de este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="2f3f5-175">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="2f3f5-176">Condición</span><span class="sxs-lookup"><span data-stu-id="2f3f5-176">Condition</span></span>

<span data-ttu-id="2f3f5-177">Estos son los campos necesarios mínimos, que son un subconjunto del perfil de [condición Desc.](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)</span><span class="sxs-lookup"><span data-stu-id="2f3f5-177">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

 - <span data-ttu-id="2f3f5-178">Code.Coding[0]. Pantalla</span><span class="sxs-lookup"><span data-stu-id="2f3f5-178">Code.Coding[0].Display</span></span>

<span data-ttu-id="2f3f5-179">Además de los campos Salesforce, para una excelente experiencia del usuario, la aplicación Pacientes también puede leer los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="2f3f5-179">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="2f3f5-180">FechaDespedido</span><span class="sxs-lookup"><span data-stu-id="2f3f5-180">AssertedDate</span></span>
 - <span data-ttu-id="2f3f5-181">Gravedad</span><span class="sxs-lookup"><span data-stu-id="2f3f5-181">Severity</span></span>

<span data-ttu-id="2f3f5-182">Una búsqueda de recursos usa el método GET y los parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="2f3f5-182">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="2f3f5-183">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="2f3f5-183">patient=\<patient id></span></span>
 - <span data-ttu-id="2f3f5-184">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="2f3f5-184">_count=\<max results></span></span>

<span data-ttu-id="2f3f5-185">Vea el siguiente ejemplo de esta llamada:</span><span class="sxs-lookup"><span data-stu-id="2f3f5-185">See the following example of this call:</span></span>

```
Request:
GET <fhir-server>/Condition?patient=<patient-id>&_count=10

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 2,
  "entry": [
    {
      "resource": {
        "resourceType": "Condition",
        "id": "<resource-id>",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "185903001",
              "display": "Needs influenza immunization",
            }
          ]
        },
        "severity": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "24484000",
              "display": "Severe"
            }
          ]
        },
        "assertedDate": "2018-04-04"
      }
    },
    .
    .
    .
  ]
}
```

<span data-ttu-id="2f3f5-186">Consulte [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) otros detalles de este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="2f3f5-186">See [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="2f3f5-187">Encounter</span><span class="sxs-lookup"><span data-stu-id="2f3f5-187">Encounter</span></span>

<span data-ttu-id="2f3f5-188">Estos son los campos requeridos mínimos, que son un subconjunto de [los](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) campos "debe tener" del perfil principal de EE. UU.).</span><span class="sxs-lookup"><span data-stu-id="2f3f5-188">These are the minimum required fields, which are a subset of the [US Core Encounter profile](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "must have" fields).</span></span>

 - <span data-ttu-id="2f3f5-189">Estado</span><span class="sxs-lookup"><span data-stu-id="2f3f5-189">Status</span></span>
 - <span data-ttu-id="2f3f5-190">Escriba[0]. Coding[0]. Pantalla</span><span class="sxs-lookup"><span data-stu-id="2f3f5-190">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="2f3f5-191">Además, los siguientes campos del perfil de US Core Encounter "deben admitir":</span><span class="sxs-lookup"><span data-stu-id="2f3f5-191">In addition, the following fields from US Core Encounter profile's "must support" fields:</span></span>

 - <span data-ttu-id="2f3f5-192">Period.Start</span><span class="sxs-lookup"><span data-stu-id="2f3f5-192">Period.Start</span></span>
 - <span data-ttu-id="2f3f5-193">Ubicación[0]. Location.Display</span><span class="sxs-lookup"><span data-stu-id="2f3f5-193">Location[0].Location.Display</span></span>

<span data-ttu-id="2f3f5-194">Una búsqueda de recursos usa el método GET y los parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="2f3f5-194">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="2f3f5-195">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="2f3f5-195">patient=\<patient id></span></span>
 - <span data-ttu-id="2f3f5-196">_sort:desc=\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="2f3f5-196">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="2f3f5-197">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="2f3f5-197">_count=\<max results></span></span>

<span data-ttu-id="2f3f5-198">El objetivo es poder recuperar la última ubicación conocida del paciente.</span><span class="sxs-lookup"><span data-stu-id="2f3f5-198">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="2f3f5-199">Cada encuentro hace referencia a un recurso de ubicación.</span><span class="sxs-lookup"><span data-stu-id="2f3f5-199">Each encounter references a location resource.</span></span> <span data-ttu-id="2f3f5-200">La referencia también incluirá el campo de visualización de la ubicación.</span><span class="sxs-lookup"><span data-stu-id="2f3f5-200">The reference shall also include the location's display field.</span></span>

<span data-ttu-id="2f3f5-201">Consulte [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) otros detalles de este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="2f3f5-201">See [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="2f3f5-202">Desenladigo</span><span class="sxs-lookup"><span data-stu-id="2f3f5-202">AllergyIntolerance</span></span>

<span data-ttu-id="2f3f5-203">Estos son los campos requeridos mínimos, que son un subconjunto del perfil [Desenladigo:](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html)</span><span class="sxs-lookup"><span data-stu-id="2f3f5-203">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

 - <span data-ttu-id="2f3f5-204">Code.Text</span><span class="sxs-lookup"><span data-stu-id="2f3f5-204">Code.Text</span></span>
 - <span data-ttu-id="2f3f5-205">Code.Coding[0]. Pantalla</span><span class="sxs-lookup"><span data-stu-id="2f3f5-205">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="2f3f5-206">Estado Desctivo/Estado De Comprobación (leemos ambos)</span><span class="sxs-lookup"><span data-stu-id="2f3f5-206">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="2f3f5-207">Además de los campos Field, para una excelente experiencia del usuario, la aplicación Pacientes también puede leer el siguiente campo:</span><span class="sxs-lookup"><span data-stu-id="2f3f5-207">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

 - <span data-ttu-id="2f3f5-208">FechaDespedido</span><span class="sxs-lookup"><span data-stu-id="2f3f5-208">AssertedDate</span></span>
 - <span data-ttu-id="2f3f5-209">Note.Text</span><span class="sxs-lookup"><span data-stu-id="2f3f5-209">Note.Text</span></span>
 - <span data-ttu-id="2f3f5-210">Reacción</span><span class="sxs-lookup"><span data-stu-id="2f3f5-210">Reaction</span></span>
    - <span data-ttu-id="2f3f5-211">Sedán (un elemento de codificación)</span><span class="sxs-lookup"><span data-stu-id="2f3f5-211">Substance (one coding element)</span></span>
    - <span data-ttu-id="2f3f5-212">Se muestra una gran conocimiento (un elemento de codificación)</span><span class="sxs-lookup"><span data-stu-id="2f3f5-212">Manifestation (one coding element)</span></span>

<span data-ttu-id="2f3f5-213">Una búsqueda de recursos usa el método GET y los parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="2f3f5-213">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="2f3f5-214">Patient =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="2f3f5-214">Patient =  \<patient id></span></span>

<span data-ttu-id="2f3f5-215">Vea el siguiente ejemplo de la llamada:</span><span class="sxs-lookup"><span data-stu-id="2f3f5-215">See the following example of the call:</span></span> 

```
Request:
GET <fhir-server>/AllergyIntolerance?patient=<patient-id>

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "AllergyIntolerance",
        "id": "<resource-id>",
        "clinicalStatus": "active",
        "verificationStatus": "confirmed",
        "code": {
          "coding": [
            {
              "system": "http://rxnav.nlm.nih.gov/REST/Ndfrt",
              "code": "N0000175503",
              "display": "sulfonamide antibacterial",
            }
          ],
          "text": "sulfonamide antibacterial"
        },
        "assertedDate": "2018-01-01T00:00:00-07:00",
        "reaction": [
          {
            "manifestation": [
              {
                "coding": [
                  {
                    "system": "http://snomed.info/sct",
                    "code": "271807003",
                    "display": "skin rash",
                  }
                ],
                "text": "skin rash"
              }
            ],
          }
        ]
      }
    }
  ]
}
```

<span data-ttu-id="2f3f5-216">Consulte [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) otros detalles de este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="2f3f5-216">See [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="2f3f5-217">Solicitud de medicamentos</span><span class="sxs-lookup"><span data-stu-id="2f3f5-217">Medication Request</span></span>

<span data-ttu-id="2f3f5-218">Estos son los campos requeridos mínimos, que son un subconjunto del perfil de solicitud de medicamentos principales [de ESTADOS UNIDOS:](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html)</span><span class="sxs-lookup"><span data-stu-id="2f3f5-218">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

 - <span data-ttu-id="2f3f5-219">Medicamentos.Pantalla (si referencia)</span><span class="sxs-lookup"><span data-stu-id="2f3f5-219">Medication.Display (if Reference)</span></span>
 - <span data-ttu-id="2f3f5-220">Medication.Text (if CodableConcept)</span><span class="sxs-lookup"><span data-stu-id="2f3f5-220">Medication.Text (if CodableConcept)</span></span>
 - <span data-ttu-id="2f3f5-221">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="2f3f5-221">AuthoredOn</span></span>
 - <span data-ttu-id="2f3f5-222">Requester.Agent.Display</span><span class="sxs-lookup"><span data-stu-id="2f3f5-222">Requester.Agent.Display</span></span>

<span data-ttu-id="2f3f5-223">Además de los campos Centro de EE. UU., para una excelente experiencia del usuario, la aplicación Pacientes también puede leer los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="2f3f5-223">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="2f3f5-224">AstructiónInstructión[..]. Texto</span><span class="sxs-lookup"><span data-stu-id="2f3f5-224">DosageInstruction[..].Text</span></span>
 - <span data-ttu-id="2f3f5-225">Texto</span><span class="sxs-lookup"><span data-stu-id="2f3f5-225">Text</span></span>

<span data-ttu-id="2f3f5-226">Una búsqueda de recursos usa el método GET y los parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="2f3f5-226">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="2f3f5-227">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="2f3f5-227">patient=\<patient id></span></span>
 - <span data-ttu-id="2f3f5-228">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="2f3f5-228">_count=\<max results></span></span>

<span data-ttu-id="2f3f5-229">Consulte [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) otros detalles de este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="2f3f5-229">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="2f3f5-230">Cobertura</span><span class="sxs-lookup"><span data-stu-id="2f3f5-230">Coverage</span></span>

<span data-ttu-id="2f3f5-231">Estos son los campos requeridos mínimos, no cubiertos por los perfiles de US Core o Core:</span><span class="sxs-lookup"><span data-stu-id="2f3f5-231">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="2f3f5-232">Agrupación, al menos un elemento con</span><span class="sxs-lookup"><span data-stu-id="2f3f5-232">Grouping, at least one element with</span></span>
    - <span data-ttu-id="2f3f5-233">GroupDisplay</span><span class="sxs-lookup"><span data-stu-id="2f3f5-233">GroupDisplay</span></span>
    - <span data-ttu-id="2f3f5-234">PlanDisplay</span><span class="sxs-lookup"><span data-stu-id="2f3f5-234">PlanDisplay</span></span>
 - <span data-ttu-id="2f3f5-235">Período</span><span class="sxs-lookup"><span data-stu-id="2f3f5-235">Period</span></span>
 - <span data-ttu-id="2f3f5-236">SubscriberId</span><span class="sxs-lookup"><span data-stu-id="2f3f5-236">SubscriberId</span></span>

<span data-ttu-id="2f3f5-237">Una búsqueda de recursos usa el método GET y los parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="2f3f5-237">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="2f3f5-238">Patient = \<patient id></span><span class="sxs-lookup"><span data-stu-id="2f3f5-238">Patient = \<patient id></span></span>

<span data-ttu-id="2f3f5-239">Consulte [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) otros detalles de este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="2f3f5-239">See [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
