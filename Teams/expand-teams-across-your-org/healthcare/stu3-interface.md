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
ms.openlocfilehash: a36c6176b4873dd41d654493bd36e9a3dbbfd49a
ms.sourcegitcommit: 18b5e3487ba1350c5d2e6d676a4ab582b5b638d4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "48772271"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="e6b29-103">Especificación de la interfaz STU3</span><span class="sxs-lookup"><span data-stu-id="e6b29-103">STU3 interface specification</span></span>

> [!NOTE]
> <span data-ttu-id="e6b29-104">Desde el 30 de octubre de 2020, la aplicación de pacientes se ha retirado y se ha sustituido por la [aplicación listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) en Teams.</span><span class="sxs-lookup"><span data-stu-id="e6b29-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="e6b29-105">Con las listas, los equipos de cuidados de la organización de la salud pueden crear listas de pacientes para escenarios que abarcan desde rondas y reuniones interdisciplinarias hasta supervisión general de pacientes.</span><span class="sxs-lookup"><span data-stu-id="e6b29-105">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="e6b29-106">Consulte la plantilla patients en listas para comenzar.</span><span class="sxs-lookup"><span data-stu-id="e6b29-106">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="e6b29-107">Para obtener más información sobre cómo administrar la aplicación listas de su organización, vea [administrar la aplicación listas](../../manage-lists-app.md).</span><span class="sxs-lookup"><span data-stu-id="e6b29-107">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="e6b29-108">Para configurar o volver a configurar un servidor de FHIR para que funcione con la aplicación para pacientes de Microsoft Teams, es necesario comprender a qué datos necesita acceder la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e6b29-108">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="e6b29-109">El servidor de FHIR debe admitir solicitudes POST con paquetes para los siguientes recursos:</span><span class="sxs-lookup"><span data-stu-id="e6b29-109">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="e6b29-110">Propio</span><span class="sxs-lookup"><span data-stu-id="e6b29-110">Patient</span></span>](#patient)
- [<span data-ttu-id="e6b29-111">Observación</span><span class="sxs-lookup"><span data-stu-id="e6b29-111">Observation</span></span>](#observation)
- [<span data-ttu-id="e6b29-112">Condición</span><span class="sxs-lookup"><span data-stu-id="e6b29-112">Condition</span></span>](#condition)
- [<span data-ttu-id="e6b29-113">Detect</span><span class="sxs-lookup"><span data-stu-id="e6b29-113">Encounter</span></span>](#encounter)
- [<span data-ttu-id="e6b29-114">Intolerancia de alergia</span><span class="sxs-lookup"><span data-stu-id="e6b29-114">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="e6b29-115">Beneficios</span><span class="sxs-lookup"><span data-stu-id="e6b29-115">Coverage</span></span>](#coverage)
- <span data-ttu-id="e6b29-116">[Declaración de medicación](#medication-request) (reemplaza MedicationOrder en la versión DSTU2 de la PatientsApp)</span><span class="sxs-lookup"><span data-stu-id="e6b29-116">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="e6b29-117">Ubicación (la información necesaria de este recurso puede estar incluida en encontrarse)</span><span class="sxs-lookup"><span data-stu-id="e6b29-117">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="e6b29-118">El recurso paciente es el único recurso obligatorio (sin que la aplicación se cargue); Sin embargo, se recomienda que el socio implemente la compatibilidad de todos los recursos mencionados anteriormente según las especificaciones proporcionadas a continuación para obtener la mejor experiencia para el usuario final con la aplicación de pacientes de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e6b29-118">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="e6b29-119">Las consultas de la aplicación de pacientes de Microsoft Teams para más de un recurso deben publicar un paquete (lote) de solicitudes a la dirección URL del servidor de FHIR.</span><span class="sxs-lookup"><span data-stu-id="e6b29-119">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="e6b29-120">El servidor debe procesar cada solicitud y devolver un paquete de los recursos coincidentes con cada solicitud.</span><span class="sxs-lookup"><span data-stu-id="e6b29-120">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="e6b29-121">Para obtener más información y ejemplos, consulte [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) .</span><span class="sxs-lookup"><span data-stu-id="e6b29-121">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="e6b29-122">Declaración de capacidad</span><span class="sxs-lookup"><span data-stu-id="e6b29-122">Capability Statement</span></span>

<span data-ttu-id="e6b29-123">Estos son los campos mínimos obligatorios:</span><span class="sxs-lookup"><span data-stu-id="e6b29-123">These are the minimum required fields:</span></span>

 - <span data-ttu-id="e6b29-124">DESCANSO</span><span class="sxs-lookup"><span data-stu-id="e6b29-124">REST</span></span>

    - <span data-ttu-id="e6b29-125">Modo</span><span class="sxs-lookup"><span data-stu-id="e6b29-125">Mode</span></span>
    - <span data-ttu-id="e6b29-126">MOV</span><span class="sxs-lookup"><span data-stu-id="e6b29-126">Interaction</span></span>
    - <span data-ttu-id="e6b29-127">Recurso: tipo</span><span class="sxs-lookup"><span data-stu-id="e6b29-127">Resource: Type</span></span>
    - <span data-ttu-id="e6b29-128">Seguridad: [extensión para URI de OAuth](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="e6b29-128">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
    
 - <span data-ttu-id="e6b29-129">FhirVersion (nuestro código requiere esto para comprender a qué versión debemos dinamizar).</span><span class="sxs-lookup"><span data-stu-id="e6b29-129">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="e6b29-130">Consulte [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="e6b29-130">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="e6b29-131">Propio</span><span class="sxs-lookup"><span data-stu-id="e6b29-131">Patient</span></span>

<span data-ttu-id="e6b29-132">Estos son los campos mínimos obligatorios, que son un subconjunto de los campos de perfil del paciente de Argonaut:</span><span class="sxs-lookup"><span data-stu-id="e6b29-132">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

 - <span data-ttu-id="e6b29-133">Nombre. dado</span><span class="sxs-lookup"><span data-stu-id="e6b29-133">Name.Given</span></span>
 - <span data-ttu-id="e6b29-134">Nombre. familia</span><span class="sxs-lookup"><span data-stu-id="e6b29-134">Name.Family</span></span>
 - <span data-ttu-id="e6b29-135">Hombres</span><span class="sxs-lookup"><span data-stu-id="e6b29-135">Gender</span></span>
 - <span data-ttu-id="e6b29-136">FechaNacimiento</span><span class="sxs-lookup"><span data-stu-id="e6b29-136">BirthDate</span></span>
 - <span data-ttu-id="e6b29-137">MRN (identificador)</span><span class="sxs-lookup"><span data-stu-id="e6b29-137">MRN (Identifier)</span></span>

<span data-ttu-id="e6b29-138">Además de los [campos Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), para una experiencia de usuario excelente, la aplicación de pacientes también puede leer los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="e6b29-138">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="e6b29-139">Nombre. Use</span><span class="sxs-lookup"><span data-stu-id="e6b29-139">Name.Use</span></span>
 - <span data-ttu-id="e6b29-140">Nombre. Prefix</span><span class="sxs-lookup"><span data-stu-id="e6b29-140">Name.Prefix</span></span>
 - <span data-ttu-id="e6b29-141">[GeneralPractitioner]-la referencia de GeneralPractitioner debe incluirse en el recurso patient (solo campo de mostrar)</span><span class="sxs-lookup"><span data-stu-id="e6b29-141">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="e6b29-142">Una búsqueda de recursos usa el método POST en/patient/_search y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="e6b29-142">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="e6b29-143">identificar</span><span class="sxs-lookup"><span data-stu-id="e6b29-143">id</span></span>
 - <span data-ttu-id="e6b29-144">Family = (busca todos los pacientes cuyo nombre contenga el valor)</span><span class="sxs-lookup"><span data-stu-id="e6b29-144">family=(searches for all patients whose family name contains the value)</span></span>
 - <span data-ttu-id="e6b29-145">dado =\<substring></span><span class="sxs-lookup"><span data-stu-id="e6b29-145">given=\<substring></span></span>
 - <span data-ttu-id="e6b29-146">FechaNacimiento = (coincidencia exacta)</span><span class="sxs-lookup"><span data-stu-id="e6b29-146">birthdate=(exact match)</span></span>
 - <span data-ttu-id="e6b29-147">Gender = (los valores son uno de los sexos administrativos)</span><span class="sxs-lookup"><span data-stu-id="e6b29-147">gender=(values being one of the administrative-gender)</span></span>
 - <span data-ttu-id="e6b29-148">\_contar (número máximo de resultados que se deben devolver)</span><span class="sxs-lookup"><span data-stu-id="e6b29-148">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="e6b29-149">La respuesta debe contener el recuento total de registros devueltos como resultado de la búsqueda y el \_ recuento que usará el PatientsApp para limitar el número de registros devueltos.</span><span class="sxs-lookup"><span data-stu-id="e6b29-149">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="e6b29-150">Identifier =\<mrn></span><span class="sxs-lookup"><span data-stu-id="e6b29-150">identifier=\<mrn></span></span>

<span data-ttu-id="e6b29-151">El objetivo es poder buscar y filtrar a un paciente por lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e6b29-151">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="e6b29-152">ID: es el identificador de recurso que tiene cada recurso en FHIR.</span><span class="sxs-lookup"><span data-stu-id="e6b29-152">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="e6b29-153">MRN: este es el identificador real del paciente que sabría el personal clínico.</span><span class="sxs-lookup"><span data-stu-id="e6b29-153">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="e6b29-154">Entendemos que este MRN se basa en el tipo de identificador dentro del recurso Identifier en FHIR.</span><span class="sxs-lookup"><span data-stu-id="e6b29-154">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="e6b29-155">Nombre</span><span class="sxs-lookup"><span data-stu-id="e6b29-155">Name</span></span>
- <span data-ttu-id="e6b29-156">FechaNacimiento</span><span class="sxs-lookup"><span data-stu-id="e6b29-156">Birthdate</span></span>

<span data-ttu-id="e6b29-157">Vea el ejemplo siguiente de la llamada:</span><span class="sxs-lookup"><span data-stu-id="e6b29-157">See the following example of the call:</span></span>

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

<span data-ttu-id="e6b29-158">Consulte [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="e6b29-158">See [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="e6b29-159">Observación</span><span class="sxs-lookup"><span data-stu-id="e6b29-159">Observation</span></span>

<span data-ttu-id="e6b29-160">Estos son los campos mínimos obligatorios, que son un subconjunto del [Perfil de Vital-Signs de Argonaut](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span><span class="sxs-lookup"><span data-stu-id="e6b29-160">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

 - <span data-ttu-id="e6b29-161">Vigencia (fecha o hora)</span><span class="sxs-lookup"><span data-stu-id="e6b29-161">Effective (date time or period)</span></span>
 - <span data-ttu-id="e6b29-162">Code. Coding. Code</span><span class="sxs-lookup"><span data-stu-id="e6b29-162">Code.Coding.Code</span></span>
 - <span data-ttu-id="e6b29-163">ValueQuantity. Value</span><span class="sxs-lookup"><span data-stu-id="e6b29-163">ValueQuantity.Value</span></span>

<span data-ttu-id="e6b29-164">Además de los campos Argonaut, para una experiencia de usuario excelente, la aplicación de pacientes también puede leer los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="e6b29-164">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="e6b29-165">Code. Coding. display</span><span class="sxs-lookup"><span data-stu-id="e6b29-165">Code.Coding.Display</span></span>
 - <span data-ttu-id="e6b29-166">Unidad ValueQuantity.</span><span class="sxs-lookup"><span data-stu-id="e6b29-166">ValueQuantity.Unit</span></span>

<span data-ttu-id="e6b29-167">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="e6b29-167">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="e6b29-168">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="e6b29-168">patient=\<patient id></span></span>
 - <span data-ttu-id="e6b29-169">_sort =-Date</span><span class="sxs-lookup"><span data-stu-id="e6b29-169">_sort=-date</span></span>
 - <span data-ttu-id="e6b29-170">Categoría (consultaremos "las señales de categoría = vitales") para recuperar la lista de constantes vitales.</span><span class="sxs-lookup"><span data-stu-id="e6b29-170">category (we will query for "category=vital-signs") to retrieve the list of vital signs.</span></span>

<span data-ttu-id="e6b29-171">Consulte este ejemplo de la llamada:</span><span class="sxs-lookup"><span data-stu-id="e6b29-171">Refer to this example of the call:</span></span>

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

<span data-ttu-id="e6b29-172">Consulte [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="e6b29-172">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="e6b29-173">Condición</span><span class="sxs-lookup"><span data-stu-id="e6b29-173">Condition</span></span>

<span data-ttu-id="e6b29-174">Estos son los campos mínimos obligatorios, que son un subconjunto del [Perfil de condición Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span><span class="sxs-lookup"><span data-stu-id="e6b29-174">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

 - <span data-ttu-id="e6b29-175">Code. Coding [0]. Aparecen</span><span class="sxs-lookup"><span data-stu-id="e6b29-175">Code.Coding[0].Display</span></span>

<span data-ttu-id="e6b29-176">Además de los campos Argonaut, para una experiencia de usuario excelente, la aplicación de pacientes también puede leer los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="e6b29-176">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="e6b29-177">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="e6b29-177">AssertedDate</span></span>
 - <span data-ttu-id="e6b29-178">Gravedad</span><span class="sxs-lookup"><span data-stu-id="e6b29-178">Severity</span></span>

<span data-ttu-id="e6b29-179">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="e6b29-179">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="e6b29-180">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="e6b29-180">patient=\<patient id></span></span>
 - <span data-ttu-id="e6b29-181">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="e6b29-181">_count=\<max results></span></span>

<span data-ttu-id="e6b29-182">Consulte el siguiente ejemplo de esta llamada:</span><span class="sxs-lookup"><span data-stu-id="e6b29-182">See the following example of this call:</span></span>

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

<span data-ttu-id="e6b29-183">Consulte [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="e6b29-183">See [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="e6b29-184">Detect</span><span class="sxs-lookup"><span data-stu-id="e6b29-184">Encounter</span></span>

<span data-ttu-id="e6b29-185">Estos son los campos mínimos obligatorios, que son un subconjunto del [núcleo de Estados Unidos](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) y el perfil "debe tener campos".</span><span class="sxs-lookup"><span data-stu-id="e6b29-185">These are the minimum required fields, which are a subset of the [US Core Encounter profile](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "must have" fields).</span></span>

 - <span data-ttu-id="e6b29-186">Statu</span><span class="sxs-lookup"><span data-stu-id="e6b29-186">Status</span></span>
 - <span data-ttu-id="e6b29-187">Escriba [0]. Codificación [0]. Aparecen</span><span class="sxs-lookup"><span data-stu-id="e6b29-187">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="e6b29-188">Además, los siguientes campos de la parte central de EE. UU. se encuentran en los campos "debe ser compatible" del perfil:</span><span class="sxs-lookup"><span data-stu-id="e6b29-188">In addition, the following fields from US Core Encounter profile's "must support" fields:</span></span>

 - <span data-ttu-id="e6b29-189">Start period</span><span class="sxs-lookup"><span data-stu-id="e6b29-189">Period.Start</span></span>
 - <span data-ttu-id="e6b29-190">Ubicación [0]. Location. display</span><span class="sxs-lookup"><span data-stu-id="e6b29-190">Location[0].Location.Display</span></span>

<span data-ttu-id="e6b29-191">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="e6b29-191">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="e6b29-192">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="e6b29-192">patient=\<patient id></span></span>
 - <span data-ttu-id="e6b29-193">_sort: DESC =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="e6b29-193">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="e6b29-194">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="e6b29-194">_count=\<max results></span></span>

<span data-ttu-id="e6b29-195">El objetivo es poder recuperar el último lugar conocido del paciente.</span><span class="sxs-lookup"><span data-stu-id="e6b29-195">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="e6b29-196">Cada uno de ellos hace referencia a un recurso de ubicación.</span><span class="sxs-lookup"><span data-stu-id="e6b29-196">Each encounter references a location resource.</span></span> <span data-ttu-id="e6b29-197">La referencia también incluirá el campo de visualización de la ubicación.</span><span class="sxs-lookup"><span data-stu-id="e6b29-197">The reference shall also include the location's display field.</span></span>

<span data-ttu-id="e6b29-198">Consulte [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="e6b29-198">See [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="e6b29-199">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="e6b29-199">AllergyIntolerance</span></span>

<span data-ttu-id="e6b29-200">Estos son los campos mínimos obligatorios, que son un subconjunto del perfil de [AllergyIntolerance de Argonaut](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) :</span><span class="sxs-lookup"><span data-stu-id="e6b29-200">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

 - <span data-ttu-id="e6b29-201">Code. Text</span><span class="sxs-lookup"><span data-stu-id="e6b29-201">Code.Text</span></span>
 - <span data-ttu-id="e6b29-202">Code. Coding [0]. Aparecen</span><span class="sxs-lookup"><span data-stu-id="e6b29-202">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="e6b29-203">ClinicalStatus/VerificationStatus (hemos leído ambas)</span><span class="sxs-lookup"><span data-stu-id="e6b29-203">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="e6b29-204">Además de los campos Argonaut, para una experiencia de usuario excelente, la aplicación de pacientes también puede leer el siguiente campo:</span><span class="sxs-lookup"><span data-stu-id="e6b29-204">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

 - <span data-ttu-id="e6b29-205">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="e6b29-205">AssertedDate</span></span>
 - <span data-ttu-id="e6b29-206">Nota. Text</span><span class="sxs-lookup"><span data-stu-id="e6b29-206">Note.Text</span></span>
 - <span data-ttu-id="e6b29-207">Ataque</span><span class="sxs-lookup"><span data-stu-id="e6b29-207">Reaction</span></span>
    - <span data-ttu-id="e6b29-208">Sustancia (un elemento de codificación)</span><span class="sxs-lookup"><span data-stu-id="e6b29-208">Substance (one coding element)</span></span>
    - <span data-ttu-id="e6b29-209">Manifiesto (un elemento de codificación)</span><span class="sxs-lookup"><span data-stu-id="e6b29-209">Manifestation (one coding element)</span></span>

<span data-ttu-id="e6b29-210">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="e6b29-210">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="e6b29-211">Paciente =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="e6b29-211">Patient =  \<patient id></span></span>

<span data-ttu-id="e6b29-212">Vea el ejemplo siguiente de la llamada:</span><span class="sxs-lookup"><span data-stu-id="e6b29-212">See the following example of the call:</span></span> 

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

<span data-ttu-id="e6b29-213">Consulte [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="e6b29-213">See [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="e6b29-214">Solicitud de medicación</span><span class="sxs-lookup"><span data-stu-id="e6b29-214">Medication Request</span></span>

<span data-ttu-id="e6b29-215">Estos son los campos mínimos obligatorios, que son un subconjunto del [Perfil de solicitud de medicación del núcleo de Estados Unidos](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span><span class="sxs-lookup"><span data-stu-id="e6b29-215">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

 - <span data-ttu-id="e6b29-216">Medicación. display (si Ref)</span><span class="sxs-lookup"><span data-stu-id="e6b29-216">Medication.Display (if Reference)</span></span>
 - <span data-ttu-id="e6b29-217">Medicación. Text (si CodableConcept)</span><span class="sxs-lookup"><span data-stu-id="e6b29-217">Medication.Text (if CodableConcept)</span></span>
 - <span data-ttu-id="e6b29-218">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="e6b29-218">AuthoredOn</span></span>
 - <span data-ttu-id="e6b29-219">Solicitante. Agent. display</span><span class="sxs-lookup"><span data-stu-id="e6b29-219">Requester.Agent.Display</span></span>

<span data-ttu-id="e6b29-220">Además de los campos básicos de Estados Unidos, para disfrutar de una experiencia de usuario excelente, la aplicación de pacientes también puede leer los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="e6b29-220">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="e6b29-221">DosageInstruction[..]. Facturas</span><span class="sxs-lookup"><span data-stu-id="e6b29-221">DosageInstruction[..].Text</span></span>
 - <span data-ttu-id="e6b29-222">Facturas</span><span class="sxs-lookup"><span data-stu-id="e6b29-222">Text</span></span>

<span data-ttu-id="e6b29-223">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="e6b29-223">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="e6b29-224">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="e6b29-224">patient=\<patient id></span></span>
 - <span data-ttu-id="e6b29-225">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="e6b29-225">_count=\<max results></span></span>

<span data-ttu-id="e6b29-226">Consulte [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="e6b29-226">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="e6b29-227">Beneficios</span><span class="sxs-lookup"><span data-stu-id="e6b29-227">Coverage</span></span>

<span data-ttu-id="e6b29-228">Estos son los campos mínimos obligatorios, no incluidos en los perfiles de los Estados Unidos Core o Argonaut:</span><span class="sxs-lookup"><span data-stu-id="e6b29-228">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="e6b29-229">Agrupar, al menos un elemento con</span><span class="sxs-lookup"><span data-stu-id="e6b29-229">Grouping, at least one element with</span></span>
    - <span data-ttu-id="e6b29-230">GroupDisplay</span><span class="sxs-lookup"><span data-stu-id="e6b29-230">GroupDisplay</span></span>
    - <span data-ttu-id="e6b29-231">PlanDisplay</span><span class="sxs-lookup"><span data-stu-id="e6b29-231">PlanDisplay</span></span>
 - <span data-ttu-id="e6b29-232">Período</span><span class="sxs-lookup"><span data-stu-id="e6b29-232">Period</span></span>
 - <span data-ttu-id="e6b29-233">SubscriberId</span><span class="sxs-lookup"><span data-stu-id="e6b29-233">SubscriberId</span></span>

<span data-ttu-id="e6b29-234">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="e6b29-234">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="e6b29-235">Paciente = \<patient id></span><span class="sxs-lookup"><span data-stu-id="e6b29-235">Patient = \<patient id></span></span>

<span data-ttu-id="e6b29-236">Consulte [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="e6b29-236">See [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
