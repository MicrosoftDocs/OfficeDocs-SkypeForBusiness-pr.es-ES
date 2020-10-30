---
title: Interfaz de STU3 y integración de EHR de la aplicación para pacientes
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
description: Obtenga información sobre cómo integrar los registros de mantenimiento Electrónico en la aplicación de pacientes de Microsoft Teams y la especificación de la interfaz de STU3.
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 4e20619badb2509d0a90f396563a98796e718e2f
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803498"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="11c64-103">Especificación de la interfaz STU3</span><span class="sxs-lookup"><span data-stu-id="11c64-103">STU3 interface specification</span></span>

> [!NOTE]
> <span data-ttu-id="11c64-104">Desde el 30 de octubre de 2020, la aplicación de pacientes se ha retirado y se ha sustituido por la [aplicación listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) en Teams.</span><span class="sxs-lookup"><span data-stu-id="11c64-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="11c64-105">Los datos de la aplicación patients se almacenan en el buzón de grupo del grupo Office 365 que respalda al equipo.</span><span class="sxs-lookup"><span data-stu-id="11c64-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="11c64-106">Todos los datos asociados con la aplicación patients se conservan en este grupo, pero ya no se puede obtener acceso a ellos a través de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="11c64-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="11c64-107">Los usuarios pueden volver a crear sus listas con la [aplicación listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span><span class="sxs-lookup"><span data-stu-id="11c64-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="11c64-108">Con las listas, los equipos de cuidados de la organización de la salud pueden crear listas de pacientes para escenarios que abarcan desde rondas y reuniones interdisciplinarias hasta supervisión general de pacientes.</span><span class="sxs-lookup"><span data-stu-id="11c64-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="11c64-109">Consulte la plantilla patients en listas para comenzar.</span><span class="sxs-lookup"><span data-stu-id="11c64-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="11c64-110">Para obtener más información sobre cómo administrar la aplicación listas de su organización, vea [administrar la aplicación listas](../../manage-lists-app.md).</span><span class="sxs-lookup"><span data-stu-id="11c64-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="11c64-111">Para configurar o volver a configurar un servidor de FHIR para que funcione con la aplicación para pacientes de Microsoft Teams, es necesario comprender a qué datos necesita acceder la aplicación.</span><span class="sxs-lookup"><span data-stu-id="11c64-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="11c64-112">El servidor de FHIR debe admitir solicitudes POST con paquetes para los siguientes recursos:</span><span class="sxs-lookup"><span data-stu-id="11c64-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="11c64-113">Propio</span><span class="sxs-lookup"><span data-stu-id="11c64-113">Patient</span></span>](#patient)
- [<span data-ttu-id="11c64-114">Observación</span><span class="sxs-lookup"><span data-stu-id="11c64-114">Observation</span></span>](#observation)
- [<span data-ttu-id="11c64-115">Condición</span><span class="sxs-lookup"><span data-stu-id="11c64-115">Condition</span></span>](#condition)
- [<span data-ttu-id="11c64-116">Detect</span><span class="sxs-lookup"><span data-stu-id="11c64-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="11c64-117">Intolerancia de alergia</span><span class="sxs-lookup"><span data-stu-id="11c64-117">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="11c64-118">Beneficios</span><span class="sxs-lookup"><span data-stu-id="11c64-118">Coverage</span></span>](#coverage)
- <span data-ttu-id="11c64-119">[Declaración de medicación](#medication-request) (reemplaza MedicationOrder en la versión DSTU2 de la PatientsApp)</span><span class="sxs-lookup"><span data-stu-id="11c64-119">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="11c64-120">Ubicación (la información necesaria de este recurso puede estar incluida en encontrarse)</span><span class="sxs-lookup"><span data-stu-id="11c64-120">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="11c64-121">El recurso paciente es el único recurso obligatorio (sin que la aplicación se cargue); Sin embargo, se recomienda que el socio implemente la compatibilidad de todos los recursos mencionados anteriormente según las especificaciones proporcionadas a continuación para obtener la mejor experiencia para el usuario final con la aplicación de pacientes de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="11c64-121">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="11c64-122">Las consultas de la aplicación de pacientes de Microsoft Teams para más de un recurso deben publicar un paquete (lote) de solicitudes a la dirección URL del servidor de FHIR.</span><span class="sxs-lookup"><span data-stu-id="11c64-122">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="11c64-123">El servidor debe procesar cada solicitud y devolver un paquete de los recursos coincidentes con cada solicitud.</span><span class="sxs-lookup"><span data-stu-id="11c64-123">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="11c64-124">Para obtener más información y ejemplos, consulte [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) .</span><span class="sxs-lookup"><span data-stu-id="11c64-124">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="11c64-125">Declaración de capacidad</span><span class="sxs-lookup"><span data-stu-id="11c64-125">Capability Statement</span></span>

<span data-ttu-id="11c64-126">Estos son los campos mínimos obligatorios:</span><span class="sxs-lookup"><span data-stu-id="11c64-126">These are the minimum required fields:</span></span>

 - <span data-ttu-id="11c64-127">DESCANSO</span><span class="sxs-lookup"><span data-stu-id="11c64-127">REST</span></span>

    - <span data-ttu-id="11c64-128">Modo</span><span class="sxs-lookup"><span data-stu-id="11c64-128">Mode</span></span>
    - <span data-ttu-id="11c64-129">MOV</span><span class="sxs-lookup"><span data-stu-id="11c64-129">Interaction</span></span>
    - <span data-ttu-id="11c64-130">Recurso: tipo</span><span class="sxs-lookup"><span data-stu-id="11c64-130">Resource: Type</span></span>
    - <span data-ttu-id="11c64-131">Seguridad: [extensión para URI de OAuth](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="11c64-131">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
    
 - <span data-ttu-id="11c64-132">FhirVersion (nuestro código requiere esto para comprender a qué versión debemos dinamizar).</span><span class="sxs-lookup"><span data-stu-id="11c64-132">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="11c64-133">Consulte [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="11c64-133">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="11c64-134">Propio</span><span class="sxs-lookup"><span data-stu-id="11c64-134">Patient</span></span>

<span data-ttu-id="11c64-135">Estos son los campos mínimos obligatorios, que son un subconjunto de los campos de perfil del paciente de Argonaut:</span><span class="sxs-lookup"><span data-stu-id="11c64-135">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

 - <span data-ttu-id="11c64-136">Nombre. dado</span><span class="sxs-lookup"><span data-stu-id="11c64-136">Name.Given</span></span>
 - <span data-ttu-id="11c64-137">Nombre. familia</span><span class="sxs-lookup"><span data-stu-id="11c64-137">Name.Family</span></span>
 - <span data-ttu-id="11c64-138">Hombres</span><span class="sxs-lookup"><span data-stu-id="11c64-138">Gender</span></span>
 - <span data-ttu-id="11c64-139">FechaNacimiento</span><span class="sxs-lookup"><span data-stu-id="11c64-139">BirthDate</span></span>
 - <span data-ttu-id="11c64-140">MRN (identificador)</span><span class="sxs-lookup"><span data-stu-id="11c64-140">MRN (Identifier)</span></span>

<span data-ttu-id="11c64-141">Además de los [campos Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), para una experiencia de usuario excelente, la aplicación de pacientes también puede leer los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="11c64-141">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="11c64-142">Nombre. Use</span><span class="sxs-lookup"><span data-stu-id="11c64-142">Name.Use</span></span>
 - <span data-ttu-id="11c64-143">Nombre. Prefix</span><span class="sxs-lookup"><span data-stu-id="11c64-143">Name.Prefix</span></span>
 - <span data-ttu-id="11c64-144">[GeneralPractitioner]-la referencia de GeneralPractitioner debe incluirse en el recurso patient (solo campo de mostrar)</span><span class="sxs-lookup"><span data-stu-id="11c64-144">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="11c64-145">Una búsqueda de recursos usa el método POST en/patient/_search y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="11c64-145">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="11c64-146">identificar</span><span class="sxs-lookup"><span data-stu-id="11c64-146">id</span></span>
 - <span data-ttu-id="11c64-147">Family = (busca todos los pacientes cuyo nombre contenga el valor)</span><span class="sxs-lookup"><span data-stu-id="11c64-147">family=(searches for all patients whose family name contains the value)</span></span>
 - <span data-ttu-id="11c64-148">dado =\<substring></span><span class="sxs-lookup"><span data-stu-id="11c64-148">given=\<substring></span></span>
 - <span data-ttu-id="11c64-149">FechaNacimiento = (coincidencia exacta)</span><span class="sxs-lookup"><span data-stu-id="11c64-149">birthdate=(exact match)</span></span>
 - <span data-ttu-id="11c64-150">Gender = (los valores son uno de los sexos administrativos)</span><span class="sxs-lookup"><span data-stu-id="11c64-150">gender=(values being one of the administrative-gender)</span></span>
 - <span data-ttu-id="11c64-151">\_contar (número máximo de resultados que se deben devolver)</span><span class="sxs-lookup"><span data-stu-id="11c64-151">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="11c64-152">La respuesta debe contener el recuento total de registros devueltos como resultado de la búsqueda y el \_ recuento que usará el PatientsApp para limitar el número de registros devueltos.</span><span class="sxs-lookup"><span data-stu-id="11c64-152">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="11c64-153">Identifier =\<mrn></span><span class="sxs-lookup"><span data-stu-id="11c64-153">identifier=\<mrn></span></span>

<span data-ttu-id="11c64-154">El objetivo es poder buscar y filtrar a un paciente por lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="11c64-154">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="11c64-155">ID: es el identificador de recurso que tiene cada recurso en FHIR.</span><span class="sxs-lookup"><span data-stu-id="11c64-155">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="11c64-156">MRN: este es el identificador real del paciente que sabría el personal clínico.</span><span class="sxs-lookup"><span data-stu-id="11c64-156">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="11c64-157">Entendemos que este MRN se basa en el tipo de identificador dentro del recurso Identifier en FHIR.</span><span class="sxs-lookup"><span data-stu-id="11c64-157">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="11c64-158">Nombre</span><span class="sxs-lookup"><span data-stu-id="11c64-158">Name</span></span>
- <span data-ttu-id="11c64-159">FechaNacimiento</span><span class="sxs-lookup"><span data-stu-id="11c64-159">Birthdate</span></span>

<span data-ttu-id="11c64-160">Vea el ejemplo siguiente de la llamada:</span><span class="sxs-lookup"><span data-stu-id="11c64-160">See the following example of the call:</span></span>

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

<span data-ttu-id="11c64-161">Consulte [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="11c64-161">See [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="11c64-162">Observación</span><span class="sxs-lookup"><span data-stu-id="11c64-162">Observation</span></span>

<span data-ttu-id="11c64-163">Estos son los campos mínimos obligatorios, que son un subconjunto del [Perfil de Vital-Signs de Argonaut](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span><span class="sxs-lookup"><span data-stu-id="11c64-163">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

 - <span data-ttu-id="11c64-164">Vigencia (fecha o hora)</span><span class="sxs-lookup"><span data-stu-id="11c64-164">Effective (date time or period)</span></span>
 - <span data-ttu-id="11c64-165">Code. Coding. Code</span><span class="sxs-lookup"><span data-stu-id="11c64-165">Code.Coding.Code</span></span>
 - <span data-ttu-id="11c64-166">ValueQuantity. Value</span><span class="sxs-lookup"><span data-stu-id="11c64-166">ValueQuantity.Value</span></span>

<span data-ttu-id="11c64-167">Además de los campos Argonaut, para una experiencia de usuario excelente, la aplicación de pacientes también puede leer los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="11c64-167">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="11c64-168">Code. Coding. display</span><span class="sxs-lookup"><span data-stu-id="11c64-168">Code.Coding.Display</span></span>
 - <span data-ttu-id="11c64-169">Unidad ValueQuantity.</span><span class="sxs-lookup"><span data-stu-id="11c64-169">ValueQuantity.Unit</span></span>

<span data-ttu-id="11c64-170">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="11c64-170">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="11c64-171">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="11c64-171">patient=\<patient id></span></span>
 - <span data-ttu-id="11c64-172">_sort =-Date</span><span class="sxs-lookup"><span data-stu-id="11c64-172">_sort=-date</span></span>
 - <span data-ttu-id="11c64-173">Categoría (consultaremos "las señales de categoría = vitales") para recuperar la lista de constantes vitales.</span><span class="sxs-lookup"><span data-stu-id="11c64-173">category (we will query for "category=vital-signs") to retrieve the list of vital signs.</span></span>

<span data-ttu-id="11c64-174">Consulte este ejemplo de la llamada:</span><span class="sxs-lookup"><span data-stu-id="11c64-174">Refer to this example of the call:</span></span>

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

<span data-ttu-id="11c64-175">Consulte [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="11c64-175">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="11c64-176">Condición</span><span class="sxs-lookup"><span data-stu-id="11c64-176">Condition</span></span>

<span data-ttu-id="11c64-177">Estos son los campos mínimos obligatorios, que son un subconjunto del [Perfil de condición Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span><span class="sxs-lookup"><span data-stu-id="11c64-177">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

 - <span data-ttu-id="11c64-178">Code. Coding [0]. Aparecen</span><span class="sxs-lookup"><span data-stu-id="11c64-178">Code.Coding[0].Display</span></span>

<span data-ttu-id="11c64-179">Además de los campos Argonaut, para una experiencia de usuario excelente, la aplicación de pacientes también puede leer los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="11c64-179">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="11c64-180">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="11c64-180">AssertedDate</span></span>
 - <span data-ttu-id="11c64-181">Gravedad</span><span class="sxs-lookup"><span data-stu-id="11c64-181">Severity</span></span>

<span data-ttu-id="11c64-182">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="11c64-182">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="11c64-183">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="11c64-183">patient=\<patient id></span></span>
 - <span data-ttu-id="11c64-184">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="11c64-184">_count=\<max results></span></span>

<span data-ttu-id="11c64-185">Consulte el siguiente ejemplo de esta llamada:</span><span class="sxs-lookup"><span data-stu-id="11c64-185">See the following example of this call:</span></span>

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

<span data-ttu-id="11c64-186">Consulte [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="11c64-186">See [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="11c64-187">Detect</span><span class="sxs-lookup"><span data-stu-id="11c64-187">Encounter</span></span>

<span data-ttu-id="11c64-188">Estos son los campos mínimos obligatorios, que son un subconjunto del [núcleo de Estados Unidos](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) y el perfil "debe tener campos".</span><span class="sxs-lookup"><span data-stu-id="11c64-188">These are the minimum required fields, which are a subset of the [US Core Encounter profile](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "must have" fields).</span></span>

 - <span data-ttu-id="11c64-189">Statu</span><span class="sxs-lookup"><span data-stu-id="11c64-189">Status</span></span>
 - <span data-ttu-id="11c64-190">Escriba [0]. Codificación [0]. Aparecen</span><span class="sxs-lookup"><span data-stu-id="11c64-190">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="11c64-191">Además, los siguientes campos de la parte central de EE. UU. se encuentran en los campos "debe ser compatible" del perfil:</span><span class="sxs-lookup"><span data-stu-id="11c64-191">In addition, the following fields from US Core Encounter profile's "must support" fields:</span></span>

 - <span data-ttu-id="11c64-192">Start period</span><span class="sxs-lookup"><span data-stu-id="11c64-192">Period.Start</span></span>
 - <span data-ttu-id="11c64-193">Ubicación [0]. Location. display</span><span class="sxs-lookup"><span data-stu-id="11c64-193">Location[0].Location.Display</span></span>

<span data-ttu-id="11c64-194">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="11c64-194">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="11c64-195">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="11c64-195">patient=\<patient id></span></span>
 - <span data-ttu-id="11c64-196">_sort: DESC =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="11c64-196">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="11c64-197">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="11c64-197">_count=\<max results></span></span>

<span data-ttu-id="11c64-198">El objetivo es poder recuperar el último lugar conocido del paciente.</span><span class="sxs-lookup"><span data-stu-id="11c64-198">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="11c64-199">Cada uno de ellos hace referencia a un recurso de ubicación.</span><span class="sxs-lookup"><span data-stu-id="11c64-199">Each encounter references a location resource.</span></span> <span data-ttu-id="11c64-200">La referencia también incluirá el campo de visualización de la ubicación.</span><span class="sxs-lookup"><span data-stu-id="11c64-200">The reference shall also include the location's display field.</span></span>

<span data-ttu-id="11c64-201">Consulte [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="11c64-201">See [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="11c64-202">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="11c64-202">AllergyIntolerance</span></span>

<span data-ttu-id="11c64-203">Estos son los campos mínimos obligatorios, que son un subconjunto del perfil de [AllergyIntolerance de Argonaut](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) :</span><span class="sxs-lookup"><span data-stu-id="11c64-203">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

 - <span data-ttu-id="11c64-204">Code. Text</span><span class="sxs-lookup"><span data-stu-id="11c64-204">Code.Text</span></span>
 - <span data-ttu-id="11c64-205">Code. Coding [0]. Aparecen</span><span class="sxs-lookup"><span data-stu-id="11c64-205">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="11c64-206">ClinicalStatus/VerificationStatus (hemos leído ambas)</span><span class="sxs-lookup"><span data-stu-id="11c64-206">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="11c64-207">Además de los campos Argonaut, para una experiencia de usuario excelente, la aplicación de pacientes también puede leer el siguiente campo:</span><span class="sxs-lookup"><span data-stu-id="11c64-207">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

 - <span data-ttu-id="11c64-208">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="11c64-208">AssertedDate</span></span>
 - <span data-ttu-id="11c64-209">Nota. Text</span><span class="sxs-lookup"><span data-stu-id="11c64-209">Note.Text</span></span>
 - <span data-ttu-id="11c64-210">Ataque</span><span class="sxs-lookup"><span data-stu-id="11c64-210">Reaction</span></span>
    - <span data-ttu-id="11c64-211">Sustancia (un elemento de codificación)</span><span class="sxs-lookup"><span data-stu-id="11c64-211">Substance (one coding element)</span></span>
    - <span data-ttu-id="11c64-212">Manifiesto (un elemento de codificación)</span><span class="sxs-lookup"><span data-stu-id="11c64-212">Manifestation (one coding element)</span></span>

<span data-ttu-id="11c64-213">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="11c64-213">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="11c64-214">Paciente =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="11c64-214">Patient =  \<patient id></span></span>

<span data-ttu-id="11c64-215">Vea el ejemplo siguiente de la llamada:</span><span class="sxs-lookup"><span data-stu-id="11c64-215">See the following example of the call:</span></span> 

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

<span data-ttu-id="11c64-216">Consulte [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="11c64-216">See [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="11c64-217">Solicitud de medicación</span><span class="sxs-lookup"><span data-stu-id="11c64-217">Medication Request</span></span>

<span data-ttu-id="11c64-218">Estos son los campos mínimos obligatorios, que son un subconjunto del [Perfil de solicitud de medicación del núcleo de Estados Unidos](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span><span class="sxs-lookup"><span data-stu-id="11c64-218">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

 - <span data-ttu-id="11c64-219">Medicación. display (si Ref)</span><span class="sxs-lookup"><span data-stu-id="11c64-219">Medication.Display (if Reference)</span></span>
 - <span data-ttu-id="11c64-220">Medicación. Text (si CodableConcept)</span><span class="sxs-lookup"><span data-stu-id="11c64-220">Medication.Text (if CodableConcept)</span></span>
 - <span data-ttu-id="11c64-221">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="11c64-221">AuthoredOn</span></span>
 - <span data-ttu-id="11c64-222">Solicitante. Agent. display</span><span class="sxs-lookup"><span data-stu-id="11c64-222">Requester.Agent.Display</span></span>

<span data-ttu-id="11c64-223">Además de los campos básicos de Estados Unidos, para disfrutar de una experiencia de usuario excelente, la aplicación de pacientes también puede leer los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="11c64-223">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="11c64-224">DosageInstruction[..]. Facturas</span><span class="sxs-lookup"><span data-stu-id="11c64-224">DosageInstruction[..].Text</span></span>
 - <span data-ttu-id="11c64-225">Facturas</span><span class="sxs-lookup"><span data-stu-id="11c64-225">Text</span></span>

<span data-ttu-id="11c64-226">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="11c64-226">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="11c64-227">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="11c64-227">patient=\<patient id></span></span>
 - <span data-ttu-id="11c64-228">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="11c64-228">_count=\<max results></span></span>

<span data-ttu-id="11c64-229">Consulte [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="11c64-229">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="11c64-230">Beneficios</span><span class="sxs-lookup"><span data-stu-id="11c64-230">Coverage</span></span>

<span data-ttu-id="11c64-231">Estos son los campos mínimos obligatorios, no incluidos en los perfiles de los Estados Unidos Core o Argonaut:</span><span class="sxs-lookup"><span data-stu-id="11c64-231">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="11c64-232">Agrupar, al menos un elemento con</span><span class="sxs-lookup"><span data-stu-id="11c64-232">Grouping, at least one element with</span></span>
    - <span data-ttu-id="11c64-233">GroupDisplay</span><span class="sxs-lookup"><span data-stu-id="11c64-233">GroupDisplay</span></span>
    - <span data-ttu-id="11c64-234">PlanDisplay</span><span class="sxs-lookup"><span data-stu-id="11c64-234">PlanDisplay</span></span>
 - <span data-ttu-id="11c64-235">Período</span><span class="sxs-lookup"><span data-stu-id="11c64-235">Period</span></span>
 - <span data-ttu-id="11c64-236">SubscriberId</span><span class="sxs-lookup"><span data-stu-id="11c64-236">SubscriberId</span></span>

<span data-ttu-id="11c64-237">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="11c64-237">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="11c64-238">Paciente = \<patient id></span><span class="sxs-lookup"><span data-stu-id="11c64-238">Patient = \<patient id></span></span>

<span data-ttu-id="11c64-239">Consulte [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="11c64-239">See [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
