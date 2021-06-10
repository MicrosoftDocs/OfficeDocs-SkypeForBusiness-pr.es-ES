---
title: Interfaz STU3 de integración de EHR y aplicación para pacientes
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
description: Obtenga información sobre la integración de registros de estado electrónicos en la aplicación Microsoft Teams pacientes y la especificación de interfaz de STU3.
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 4e20619badb2509d0a90f396563a98796e718e2f
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803498"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="4a461-103">Especificación de la interfaz STU3</span><span class="sxs-lookup"><span data-stu-id="4a461-103">STU3 interface specification</span></span>

> [!NOTE]
> <span data-ttu-id="4a461-104">Desde el 30 de octubre de 2020, la aplicación Pacientes se retiró y se reemplazó por la aplicación [Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) en Teams.</span><span class="sxs-lookup"><span data-stu-id="4a461-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="4a461-105">Los datos de la aplicación Pacientes se almacenan en el buzón de correo del grupo de Office 365 que respalda al equipo.</span><span class="sxs-lookup"><span data-stu-id="4a461-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="4a461-106">Todos los datos asociados con la aplicación Pacientes se conservan en este grupo, pero ya no se puede acceder a ellos a través de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="4a461-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="4a461-107">Los usuarios pueden volver a crear sus listas mediante la [aplicación Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span><span class="sxs-lookup"><span data-stu-id="4a461-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="4a461-108">Con Listas, los equipos del cuidado de la salud de su organización sanitaria pueden crear listas de pacientes para escenarios que van desde guardias y reuniones interdisciplinarias de equipo, hasta el seguimiento general de pacientes.</span><span class="sxs-lookup"><span data-stu-id="4a461-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="4a461-109">Consulte la plantilla Pacientes en Listas para comenzar.</span><span class="sxs-lookup"><span data-stu-id="4a461-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="4a461-110">Para obtener más información sobre cómo administrar la aplicación Listas en su organización, consulte [Administrar la aplicación Listas](../../manage-lists-app.md).</span><span class="sxs-lookup"><span data-stu-id="4a461-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="4a461-111">Configurar o volver a configurar un servidor FHIR para trabajar con la aplicación Microsoft Teams pacientes requiere comprender a qué datos necesita acceder la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4a461-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="4a461-112">El servidor FHIR debe admitir las solicitudes POST con paquetes para los siguientes recursos:</span><span class="sxs-lookup"><span data-stu-id="4a461-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="4a461-113">Paciente</span><span class="sxs-lookup"><span data-stu-id="4a461-113">Patient</span></span>](#patient)
- [<span data-ttu-id="4a461-114">Observación</span><span class="sxs-lookup"><span data-stu-id="4a461-114">Observation</span></span>](#observation)
- [<span data-ttu-id="4a461-115">Condición</span><span class="sxs-lookup"><span data-stu-id="4a461-115">Condition</span></span>](#condition)
- [<span data-ttu-id="4a461-116">Encuentro</span><span class="sxs-lookup"><span data-stu-id="4a461-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="4a461-117">Intolerancia a la alergia</span><span class="sxs-lookup"><span data-stu-id="4a461-117">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="4a461-118">Cobertura</span><span class="sxs-lookup"><span data-stu-id="4a461-118">Coverage</span></span>](#coverage)
- <span data-ttu-id="4a461-119">[Declaración de medicamentos](#medication-request) (reemplaza el MedicationOrder en la versión DSTU2 de PatientsApp)</span><span class="sxs-lookup"><span data-stu-id="4a461-119">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="4a461-120">Ubicación (la información necesaria de este recurso se puede incluir en Encuentro)</span><span class="sxs-lookup"><span data-stu-id="4a461-120">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="4a461-121">El recurso Paciente es el único recurso obligatorio (sin el que la aplicación no se cargará en absoluto); Sin embargo, se recomienda que el partner implemente soporte técnico para todos los recursos mencionados anteriormente según las especificaciones que se proporcionan a continuación para obtener la mejor experiencia del usuario final con la aplicación Microsoft Teams pacientes.</span><span class="sxs-lookup"><span data-stu-id="4a461-121">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="4a461-122">Las consultas de la aplicación Microsoft Teams pacientes de más de un recurso deberán publicar un paquete (LOTE) de solicitudes en la dirección URL del servidor FHIR.</span><span class="sxs-lookup"><span data-stu-id="4a461-122">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="4a461-123">El servidor procesará cada solicitud y devolverá un paquete de los recursos coincidentes con cada solicitud.</span><span class="sxs-lookup"><span data-stu-id="4a461-123">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="4a461-124">Para obtener más información y ejemplos, vea [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) .</span><span class="sxs-lookup"><span data-stu-id="4a461-124">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="4a461-125">Instrucción De funcionalidad</span><span class="sxs-lookup"><span data-stu-id="4a461-125">Capability Statement</span></span>

<span data-ttu-id="4a461-126">Estos son los campos mínimos necesarios:</span><span class="sxs-lookup"><span data-stu-id="4a461-126">These are the minimum required fields:</span></span>

 - <span data-ttu-id="4a461-127">REST</span><span class="sxs-lookup"><span data-stu-id="4a461-127">REST</span></span>

    - <span data-ttu-id="4a461-128">Modo</span><span class="sxs-lookup"><span data-stu-id="4a461-128">Mode</span></span>
    - <span data-ttu-id="4a461-129">Interacción</span><span class="sxs-lookup"><span data-stu-id="4a461-129">Interaction</span></span>
    - <span data-ttu-id="4a461-130">Recurso: Escriba</span><span class="sxs-lookup"><span data-stu-id="4a461-130">Resource: Type</span></span>
    - <span data-ttu-id="4a461-131">Seguridad: [Extensión para URI de OAuth](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="4a461-131">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
    
 - <span data-ttu-id="4a461-132">FhirVersion (Nuestro código requiere esto para comprender a qué versión debemos pivotar).</span><span class="sxs-lookup"><span data-stu-id="4a461-132">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="4a461-133">Vea [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) otros detalles sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="4a461-133">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="4a461-134">Paciente</span><span class="sxs-lookup"><span data-stu-id="4a461-134">Patient</span></span>

<span data-ttu-id="4a461-135">Estos son los campos mínimos necesarios, que son un subconjunto de los campos de perfil de pacientes de Argonaut:</span><span class="sxs-lookup"><span data-stu-id="4a461-135">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

 - <span data-ttu-id="4a461-136">Name.Given</span><span class="sxs-lookup"><span data-stu-id="4a461-136">Name.Given</span></span>
 - <span data-ttu-id="4a461-137">Name.Family</span><span class="sxs-lookup"><span data-stu-id="4a461-137">Name.Family</span></span>
 - <span data-ttu-id="4a461-138">Género</span><span class="sxs-lookup"><span data-stu-id="4a461-138">Gender</span></span>
 - <span data-ttu-id="4a461-139">FechaDe Nacimiento</span><span class="sxs-lookup"><span data-stu-id="4a461-139">BirthDate</span></span>
 - <span data-ttu-id="4a461-140">MRN (identificador)</span><span class="sxs-lookup"><span data-stu-id="4a461-140">MRN (Identifier)</span></span>

<span data-ttu-id="4a461-141">Además de los campos [De argonauta,](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)para una gran experiencia de usuario, la aplicación Pacientes también puede leer los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="4a461-141">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="4a461-142">Name.Use</span><span class="sxs-lookup"><span data-stu-id="4a461-142">Name.Use</span></span>
 - <span data-ttu-id="4a461-143">Name.Prefix</span><span class="sxs-lookup"><span data-stu-id="4a461-143">Name.Prefix</span></span>
 - <span data-ttu-id="4a461-144">[GeneralPractitioner]: la referencia de GeneralPractitioner debe incluirse en el recurso Paciente (solo para mostrar)</span><span class="sxs-lookup"><span data-stu-id="4a461-144">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="4a461-145">Una búsqueda de recursos usa el método POST en /Patient/_search y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="4a461-145">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="4a461-146">id</span><span class="sxs-lookup"><span data-stu-id="4a461-146">id</span></span>
 - <span data-ttu-id="4a461-147">family=(busca todos los pacientes cuyo nombre de familia contiene el valor)</span><span class="sxs-lookup"><span data-stu-id="4a461-147">family=(searches for all patients whose family name contains the value)</span></span>
 - <span data-ttu-id="4a461-148">given=\<substring></span><span class="sxs-lookup"><span data-stu-id="4a461-148">given=\<substring></span></span>
 - <span data-ttu-id="4a461-149">fecha_nacimiento=(coincidencia exacta)</span><span class="sxs-lookup"><span data-stu-id="4a461-149">birthdate=(exact match)</span></span>
 - <span data-ttu-id="4a461-150">gender=(valores que son uno de los géneros administrativos)</span><span class="sxs-lookup"><span data-stu-id="4a461-150">gender=(values being one of the administrative-gender)</span></span>
 - <span data-ttu-id="4a461-151">\_recuento (número máximo de resultados que se deben devolver)</span><span class="sxs-lookup"><span data-stu-id="4a461-151">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="4a461-152">La respuesta debe contener el recuento total de registros devueltos como resultado de la búsqueda y el recuento lo usará la PatientsApp para limitar el número \_ de registros devueltos.</span><span class="sxs-lookup"><span data-stu-id="4a461-152">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="4a461-153">identificador=\<mrn></span><span class="sxs-lookup"><span data-stu-id="4a461-153">identifier=\<mrn></span></span>

<span data-ttu-id="4a461-154">El objetivo es poder buscar y filtrar a un paciente de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="4a461-154">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="4a461-155">ID: este es el id. de recurso que tiene cada recurso de FHIR.</span><span class="sxs-lookup"><span data-stu-id="4a461-155">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="4a461-156">MRN: Este es el identificador real del paciente que el personal clínico conocería.</span><span class="sxs-lookup"><span data-stu-id="4a461-156">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="4a461-157">Entendemos que este MRN se basa en el tipo de identificador dentro del recurso de identificador en FHIR.</span><span class="sxs-lookup"><span data-stu-id="4a461-157">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="4a461-158">Nombre</span><span class="sxs-lookup"><span data-stu-id="4a461-158">Name</span></span>
- <span data-ttu-id="4a461-159">Fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="4a461-159">Birthdate</span></span>

<span data-ttu-id="4a461-160">Vea el siguiente ejemplo de la llamada:</span><span class="sxs-lookup"><span data-stu-id="4a461-160">See the following example of the call:</span></span>

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

<span data-ttu-id="4a461-161">Vea [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) otros detalles sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="4a461-161">See [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="4a461-162">Observación</span><span class="sxs-lookup"><span data-stu-id="4a461-162">Observation</span></span>

<span data-ttu-id="4a461-163">Estos son los campos mínimos necesarios, que son un subconjunto del perfil [Vital-Signs argonauta.](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)</span><span class="sxs-lookup"><span data-stu-id="4a461-163">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

 - <span data-ttu-id="4a461-164">Efectivo (fecha o período)</span><span class="sxs-lookup"><span data-stu-id="4a461-164">Effective (date time or period)</span></span>
 - <span data-ttu-id="4a461-165">Code.Coding.Code</span><span class="sxs-lookup"><span data-stu-id="4a461-165">Code.Coding.Code</span></span>
 - <span data-ttu-id="4a461-166">ValorQuantity.Value</span><span class="sxs-lookup"><span data-stu-id="4a461-166">ValueQuantity.Value</span></span>

<span data-ttu-id="4a461-167">Además de los campos Argonaut, para una gran experiencia de usuario, la aplicación Pacientes también puede leer los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="4a461-167">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="4a461-168">Code.Coding.Display</span><span class="sxs-lookup"><span data-stu-id="4a461-168">Code.Coding.Display</span></span>
 - <span data-ttu-id="4a461-169">ValorQuantity.Unit</span><span class="sxs-lookup"><span data-stu-id="4a461-169">ValueQuantity.Unit</span></span>

<span data-ttu-id="4a461-170">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="4a461-170">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="4a461-171">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="4a461-171">patient=\<patient id></span></span>
 - <span data-ttu-id="4a461-172">_sort=-date</span><span class="sxs-lookup"><span data-stu-id="4a461-172">_sort=-date</span></span>
 - <span data-ttu-id="4a461-173">categoría (consultaremos "category=vital-signs") para recuperar la lista de signos vitales.</span><span class="sxs-lookup"><span data-stu-id="4a461-173">category (we will query for "category=vital-signs") to retrieve the list of vital signs.</span></span>

<span data-ttu-id="4a461-174">Consulte este ejemplo de la llamada:</span><span class="sxs-lookup"><span data-stu-id="4a461-174">Refer to this example of the call:</span></span>

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

<span data-ttu-id="4a461-175">Vea [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) otros detalles sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="4a461-175">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="4a461-176">Condición</span><span class="sxs-lookup"><span data-stu-id="4a461-176">Condition</span></span>

<span data-ttu-id="4a461-177">Estos son los campos mínimos necesarios, que son un subconjunto del perfil de condición [Argonaut.](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)</span><span class="sxs-lookup"><span data-stu-id="4a461-177">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

 - <span data-ttu-id="4a461-178">Code.Coding[0]. Mostrar</span><span class="sxs-lookup"><span data-stu-id="4a461-178">Code.Coding[0].Display</span></span>

<span data-ttu-id="4a461-179">Además de los campos Argonaut, para una gran experiencia de usuario, la aplicación Pacientes también puede leer los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="4a461-179">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="4a461-180">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="4a461-180">AssertedDate</span></span>
 - <span data-ttu-id="4a461-181">Gravedad</span><span class="sxs-lookup"><span data-stu-id="4a461-181">Severity</span></span>

<span data-ttu-id="4a461-182">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="4a461-182">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="4a461-183">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="4a461-183">patient=\<patient id></span></span>
 - <span data-ttu-id="4a461-184">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="4a461-184">_count=\<max results></span></span>

<span data-ttu-id="4a461-185">Vea el siguiente ejemplo de esta llamada:</span><span class="sxs-lookup"><span data-stu-id="4a461-185">See the following example of this call:</span></span>

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

<span data-ttu-id="4a461-186">Vea [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) otros detalles sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="4a461-186">See [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="4a461-187">Encuentro</span><span class="sxs-lookup"><span data-stu-id="4a461-187">Encounter</span></span>

<span data-ttu-id="4a461-188">Estos son los campos mínimos obligatorios, que son un subconjunto de [los](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) campos "must have" del perfil de encuentro principal de EE. UU.).</span><span class="sxs-lookup"><span data-stu-id="4a461-188">These are the minimum required fields, which are a subset of the [US Core Encounter profile](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "must have" fields).</span></span>

 - <span data-ttu-id="4a461-189">Estado</span><span class="sxs-lookup"><span data-stu-id="4a461-189">Status</span></span>
 - <span data-ttu-id="4a461-190">Escriba[0]. Codificación[0]. Mostrar</span><span class="sxs-lookup"><span data-stu-id="4a461-190">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="4a461-191">Además, los siguientes campos del perfil de encuentro principal de EE. UU. "deben admitir":</span><span class="sxs-lookup"><span data-stu-id="4a461-191">In addition, the following fields from US Core Encounter profile's "must support" fields:</span></span>

 - <span data-ttu-id="4a461-192">Period.Start</span><span class="sxs-lookup"><span data-stu-id="4a461-192">Period.Start</span></span>
 - <span data-ttu-id="4a461-193">Ubicación[0]. Location.Display</span><span class="sxs-lookup"><span data-stu-id="4a461-193">Location[0].Location.Display</span></span>

<span data-ttu-id="4a461-194">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="4a461-194">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="4a461-195">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="4a461-195">patient=\<patient id></span></span>
 - <span data-ttu-id="4a461-196">_sort:desc=\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="4a461-196">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="4a461-197">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="4a461-197">_count=\<max results></span></span>

<span data-ttu-id="4a461-198">El objetivo es poder recuperar la última ubicación conocida del paciente.</span><span class="sxs-lookup"><span data-stu-id="4a461-198">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="4a461-199">Cada encuentro hace referencia a un recurso de ubicación.</span><span class="sxs-lookup"><span data-stu-id="4a461-199">Each encounter references a location resource.</span></span> <span data-ttu-id="4a461-200">La referencia también incluirá el campo de visualización de la ubicación.</span><span class="sxs-lookup"><span data-stu-id="4a461-200">The reference shall also include the location's display field.</span></span>

<span data-ttu-id="4a461-201">Vea [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) otros detalles sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="4a461-201">See [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="4a461-202">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="4a461-202">AllergyIntolerance</span></span>

<span data-ttu-id="4a461-203">Estos son los campos mínimos necesarios, que son un subconjunto del perfil [de Alergia a argonauta:](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html)</span><span class="sxs-lookup"><span data-stu-id="4a461-203">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

 - <span data-ttu-id="4a461-204">Code.Text</span><span class="sxs-lookup"><span data-stu-id="4a461-204">Code.Text</span></span>
 - <span data-ttu-id="4a461-205">Code.Coding[0]. Mostrar</span><span class="sxs-lookup"><span data-stu-id="4a461-205">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="4a461-206">ClinicalStatus/VerificationStatus (leemos ambos)</span><span class="sxs-lookup"><span data-stu-id="4a461-206">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="4a461-207">Además de los campos Argonaut, para una gran experiencia de usuario, la aplicación Pacientes también puede leer el siguiente campo:</span><span class="sxs-lookup"><span data-stu-id="4a461-207">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

 - <span data-ttu-id="4a461-208">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="4a461-208">AssertedDate</span></span>
 - <span data-ttu-id="4a461-209">Note.Text</span><span class="sxs-lookup"><span data-stu-id="4a461-209">Note.Text</span></span>
 - <span data-ttu-id="4a461-210">Reacción</span><span class="sxs-lookup"><span data-stu-id="4a461-210">Reaction</span></span>
    - <span data-ttu-id="4a461-211">Sustancia (un elemento de codificación)</span><span class="sxs-lookup"><span data-stu-id="4a461-211">Substance (one coding element)</span></span>
    - <span data-ttu-id="4a461-212">Manifestación (un elemento de codificación)</span><span class="sxs-lookup"><span data-stu-id="4a461-212">Manifestation (one coding element)</span></span>

<span data-ttu-id="4a461-213">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="4a461-213">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="4a461-214">Paciente =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="4a461-214">Patient =  \<patient id></span></span>

<span data-ttu-id="4a461-215">Vea el siguiente ejemplo de la llamada:</span><span class="sxs-lookup"><span data-stu-id="4a461-215">See the following example of the call:</span></span> 

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

<span data-ttu-id="4a461-216">Vea [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) otros detalles sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="4a461-216">See [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="4a461-217">Solicitud de medicación</span><span class="sxs-lookup"><span data-stu-id="4a461-217">Medication Request</span></span>

<span data-ttu-id="4a461-218">Estos son los campos mínimos necesarios, que son un subconjunto del perfil de solicitud de medicamentos principales de EE. [UU.](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span><span class="sxs-lookup"><span data-stu-id="4a461-218">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

 - <span data-ttu-id="4a461-219">Medication.Display (si referencia)</span><span class="sxs-lookup"><span data-stu-id="4a461-219">Medication.Display (if Reference)</span></span>
 - <span data-ttu-id="4a461-220">Medication.Text (si CodableConcept)</span><span class="sxs-lookup"><span data-stu-id="4a461-220">Medication.Text (if CodableConcept)</span></span>
 - <span data-ttu-id="4a461-221">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="4a461-221">AuthoredOn</span></span>
 - <span data-ttu-id="4a461-222">Requester.Agent.Display</span><span class="sxs-lookup"><span data-stu-id="4a461-222">Requester.Agent.Display</span></span>

<span data-ttu-id="4a461-223">Además de los campos Ee.UU. Core, para una gran experiencia de usuario, la aplicación Pacientes también puede leer los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="4a461-223">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="4a461-224">DosageInstruction[..]. Texto</span><span class="sxs-lookup"><span data-stu-id="4a461-224">DosageInstruction[..].Text</span></span>
 - <span data-ttu-id="4a461-225">Texto</span><span class="sxs-lookup"><span data-stu-id="4a461-225">Text</span></span>

<span data-ttu-id="4a461-226">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="4a461-226">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="4a461-227">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="4a461-227">patient=\<patient id></span></span>
 - <span data-ttu-id="4a461-228">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="4a461-228">_count=\<max results></span></span>

<span data-ttu-id="4a461-229">Vea [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) otros detalles sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="4a461-229">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="4a461-230">Cobertura</span><span class="sxs-lookup"><span data-stu-id="4a461-230">Coverage</span></span>

<span data-ttu-id="4a461-231">Estos son los campos mínimos obligatorios, no cubiertos por los perfiles de Núcleo de EE. UU. o Argonaut:</span><span class="sxs-lookup"><span data-stu-id="4a461-231">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="4a461-232">Agrupación, al menos un elemento con</span><span class="sxs-lookup"><span data-stu-id="4a461-232">Grouping, at least one element with</span></span>
    - <span data-ttu-id="4a461-233">GroupDisplay</span><span class="sxs-lookup"><span data-stu-id="4a461-233">GroupDisplay</span></span>
    - <span data-ttu-id="4a461-234">PlanDisplay</span><span class="sxs-lookup"><span data-stu-id="4a461-234">PlanDisplay</span></span>
 - <span data-ttu-id="4a461-235">Punto</span><span class="sxs-lookup"><span data-stu-id="4a461-235">Period</span></span>
 - <span data-ttu-id="4a461-236">SubscriberId</span><span class="sxs-lookup"><span data-stu-id="4a461-236">SubscriberId</span></span>

<span data-ttu-id="4a461-237">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="4a461-237">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="4a461-238">Paciente = \<patient id></span><span class="sxs-lookup"><span data-stu-id="4a461-238">Patient = \<patient id></span></span>

<span data-ttu-id="4a461-239">Vea [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) otros detalles sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="4a461-239">See [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
