---
title: Interfaz de DSTU2 y integración de EHR de la aplicación para pacientes
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
description: Obtenga más información sobre la especificación de la interfaz de DSTU2 en Teams, incluida la configuración o la reconfiguración de un servidor de FHIR para que funcione con la aplicación de pacientes de Microsoft Teams.
ms.custom: seo-marvel-mar2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 15bcc5fcaff50d6d41c45ef2d38e34719ebca999
ms.sourcegitcommit: 18b5e3487ba1350c5d2e6d676a4ab582b5b638d4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "48772211"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="7b8a1-103">Especificación de la interfaz DSTU2</span><span class="sxs-lookup"><span data-stu-id="7b8a1-103">DSTU2 interface specification</span></span>

> [!NOTE]
> <span data-ttu-id="7b8a1-104">Desde el 30 de octubre de 2020, la aplicación de pacientes se ha retirado y se ha sustituido por la [aplicación listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) en Teams.</span><span class="sxs-lookup"><span data-stu-id="7b8a1-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="7b8a1-105">Con las listas, los equipos de cuidados de la organización de la salud pueden crear listas de pacientes para escenarios que abarcan desde rondas y reuniones interdisciplinarias hasta supervisión general de pacientes.</span><span class="sxs-lookup"><span data-stu-id="7b8a1-105">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="7b8a1-106">Consulte la plantilla patients en listas para comenzar.</span><span class="sxs-lookup"><span data-stu-id="7b8a1-106">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="7b8a1-107">Para obtener más información sobre cómo administrar la aplicación listas de su organización, vea [administrar la aplicación listas](../../manage-lists-app.md) .</span><span class="sxs-lookup"><span data-stu-id="7b8a1-107">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md)</span></span>

<span data-ttu-id="7b8a1-108">Para configurar o volver a configurar un servidor de FHIR para que funcione con la aplicación para pacientes de Microsoft Teams, es necesario comprender a qué datos necesita acceder la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7b8a1-108">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="7b8a1-109">El servidor de FHIR debe admitir solicitudes POST con paquetes para los siguientes recursos:</span><span class="sxs-lookup"><span data-stu-id="7b8a1-109">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="7b8a1-110">Propio</span><span class="sxs-lookup"><span data-stu-id="7b8a1-110">Patient</span></span>](#patient)
- [<span data-ttu-id="7b8a1-111">Observación</span><span class="sxs-lookup"><span data-stu-id="7b8a1-111">Observation</span></span>](#observation)
- [<span data-ttu-id="7b8a1-112">Condición</span><span class="sxs-lookup"><span data-stu-id="7b8a1-112">Condition</span></span>](#condition)
- [<span data-ttu-id="7b8a1-113">Detect</span><span class="sxs-lookup"><span data-stu-id="7b8a1-113">Encounter</span></span>](#encounter)
- [<span data-ttu-id="7b8a1-114">Intolerancia de alergia</span><span class="sxs-lookup"><span data-stu-id="7b8a1-114">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="7b8a1-115">Beneficios</span><span class="sxs-lookup"><span data-stu-id="7b8a1-115">Coverage</span></span>](#coverage)
- [<span data-ttu-id="7b8a1-116">Orden de los medicamentos</span><span class="sxs-lookup"><span data-stu-id="7b8a1-116">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="7b8a1-117">Ubicación</span><span class="sxs-lookup"><span data-stu-id="7b8a1-117">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="7b8a1-118">El recurso paciente es el único recurso obligatorio (sin que la aplicación se cargue en absoluto).</span><span class="sxs-lookup"><span data-stu-id="7b8a1-118">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="7b8a1-119">Sin embargo, se recomienda que el socio implemente la compatibilidad de todos los recursos mencionados anteriormente según las especificaciones proporcionadas a continuación para obtener la mejor experiencia para el usuario final con la aplicación de pacientes de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7b8a1-119">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="7b8a1-120">Las consultas de la aplicación de pacientes de Microsoft Teams para más de un recurso publican un paquete (lote) de solicitudes a la dirección URL del servidor FHIR.</span><span class="sxs-lookup"><span data-stu-id="7b8a1-120">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="7b8a1-121">El servidor procesa cada solicitud y devuelve un paquete de los recursos coincidentes con cada solicitud.</span><span class="sxs-lookup"><span data-stu-id="7b8a1-121">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="7b8a1-122">Para obtener más información y ejemplos, consulte [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) .</span><span class="sxs-lookup"><span data-stu-id="7b8a1-122">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="7b8a1-123">Todos los siguientes recursos de FHIR deben ser accesibles mediante la referencia directa de recursos.</span><span class="sxs-lookup"><span data-stu-id="7b8a1-123">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="7b8a1-124">Conjunto de campos obligatorios mínimos de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="7b8a1-124">Conformance minimum required field set</span></span>

 <span data-ttu-id="7b8a1-125">El servidor de FHIR debe implementar la declaración de conformidad para que nosotros tenga un resumen del objetivo de sus capacidades.</span><span class="sxs-lookup"><span data-stu-id="7b8a1-125">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="7b8a1-126">Esperamos los siguientes parámetros en un DSTU2 FHIR Server:</span><span class="sxs-lookup"><span data-stu-id="7b8a1-126">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

 - <span data-ttu-id="7b8a1-127">DESCANSO</span><span class="sxs-lookup"><span data-stu-id="7b8a1-127">REST</span></span>

    - <span data-ttu-id="7b8a1-128">Modo</span><span class="sxs-lookup"><span data-stu-id="7b8a1-128">Mode</span></span>
    - <span data-ttu-id="7b8a1-129">MOV</span><span class="sxs-lookup"><span data-stu-id="7b8a1-129">Interaction</span></span>
    - <span data-ttu-id="7b8a1-130">Recurso: tipo</span><span class="sxs-lookup"><span data-stu-id="7b8a1-130">Resource: Type</span></span>
    - <span data-ttu-id="7b8a1-131">Seguridad: [extensión para URI de OAuth](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="7b8a1-131">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
   
 - <span data-ttu-id="7b8a1-132">FhirVersion (nuestro código requiere esto para comprender a qué versión debemos dinamizar, ya que admitimos varias versiones).</span><span class="sxs-lookup"><span data-stu-id="7b8a1-132">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="7b8a1-133">Consulte [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="7b8a1-133">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="7b8a1-134">Propio</span><span class="sxs-lookup"><span data-stu-id="7b8a1-134">Patient</span></span>

<span data-ttu-id="7b8a1-135">Estos son los campos mínimos obligatorios, que son un subconjunto de los campos de [Perfil del paciente de Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) :</span><span class="sxs-lookup"><span data-stu-id="7b8a1-135">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

 - <span data-ttu-id="7b8a1-136">Nombre. familia</span><span class="sxs-lookup"><span data-stu-id="7b8a1-136">Name.Family</span></span>
 - <span data-ttu-id="7b8a1-137">Nombre. dado</span><span class="sxs-lookup"><span data-stu-id="7b8a1-137">Name.Given</span></span>
 - <span data-ttu-id="7b8a1-138">Hombres</span><span class="sxs-lookup"><span data-stu-id="7b8a1-138">Gender</span></span>
 - <span data-ttu-id="7b8a1-139">FechaNacimiento</span><span class="sxs-lookup"><span data-stu-id="7b8a1-139">BirthDate</span></span>
 - <span data-ttu-id="7b8a1-140">MRN (identificador)</span><span class="sxs-lookup"><span data-stu-id="7b8a1-140">MRN (Identifier)</span></span>

<span data-ttu-id="7b8a1-141">Además de los campos Argonaut, para una experiencia de usuario excelente, la aplicación para pacientes también lee los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="7b8a1-141">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="7b8a1-142">Nombre. Use</span><span class="sxs-lookup"><span data-stu-id="7b8a1-142">Name.Use</span></span>
 - <span data-ttu-id="7b8a1-143">Nombre. Prefix</span><span class="sxs-lookup"><span data-stu-id="7b8a1-143">Name.Prefix</span></span>
 - <span data-ttu-id="7b8a1-144">CareProvider (esta referencia en el recurso paciente debe incluir los campos de visualización que se muestran en el ejemplo siguiente).</span><span class="sxs-lookup"><span data-stu-id="7b8a1-144">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

    ```
    Request:
    GET <fhir-server>/Patient/<patient-id>
    
    Response:
    {
      "resourceType": "Patient",
      "id": "<patient-id>",
      .
      .
      .
      "name": [
        {
          "use": "official",
          "prefix": [ "Mr" ],
          "family": [ "Chau" ],
          "given": [ "Hugh" ]
        }
      ],
      "identifier": [
        {
          "use": "official",
          "type": {
            "coding": [
              {
                "system": "https://hl7.org/fhir/v2/0203",
                "code": "MR"
              }
            ]
          },
          "value": "1234567"
        }
      ],
      "gender": "male",
      "birthDate": "1957-06-05",
      "careProvider": [{ "display": "Jane Doe" }],
    }
    ```

<span data-ttu-id="7b8a1-145">Una búsqueda de recursos usa el método POST en/patient/_search y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="7b8a1-145">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="7b8a1-146">identificar</span><span class="sxs-lookup"><span data-stu-id="7b8a1-146">id</span></span>
 - <span data-ttu-id="7b8a1-147">Family: contiene = (busca todos los pacientes cuyo nombre contenga el valor).</span><span class="sxs-lookup"><span data-stu-id="7b8a1-147">family:contains=(searches for all patients whose family name contains the value.)</span></span>
 - <span data-ttu-id="7b8a1-148">dado =\<substring></span><span class="sxs-lookup"><span data-stu-id="7b8a1-148">given=\<substring></span></span>
 - <span data-ttu-id="7b8a1-149">Name =\<substring></span><span class="sxs-lookup"><span data-stu-id="7b8a1-149">name=\<substring></span></span>
 - <span data-ttu-id="7b8a1-150">FechaNacimiento = (coincidencia exacta)</span><span class="sxs-lookup"><span data-stu-id="7b8a1-150">birthdate=(exact match)</span></span>
 - <span data-ttu-id="7b8a1-151">\_contar (número máximo de resultados que se deben devolver)</span><span class="sxs-lookup"><span data-stu-id="7b8a1-151">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="7b8a1-152">La respuesta debe contener el recuento total de registros devueltos como resultado de la búsqueda, y \_ el PatientsApp usará Count para limitar el número de registros devueltos.</span><span class="sxs-lookup"><span data-stu-id="7b8a1-152">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="7b8a1-153">Identifier =\<mrn></span><span class="sxs-lookup"><span data-stu-id="7b8a1-153">identifier=\<mrn></span></span>

<span data-ttu-id="7b8a1-154">El objetivo es poder buscar y filtrar a un paciente por lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7b8a1-154">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="7b8a1-155">ID: es el identificador de recurso que tiene cada recurso en FHIR.</span><span class="sxs-lookup"><span data-stu-id="7b8a1-155">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="7b8a1-156">MRN: este es el identificador real del paciente que sabría el personal clínico.</span><span class="sxs-lookup"><span data-stu-id="7b8a1-156">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="7b8a1-157">Entendemos que este MRN se basa en el tipo de identificador dentro del recurso Identifier en FHIR</span><span class="sxs-lookup"><span data-stu-id="7b8a1-157">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="7b8a1-158">Nombre</span><span class="sxs-lookup"><span data-stu-id="7b8a1-158">Name</span></span>
- <span data-ttu-id="7b8a1-159">FechaNacimiento</span><span class="sxs-lookup"><span data-stu-id="7b8a1-159">Birthdate</span></span>

<span data-ttu-id="7b8a1-160">Consulta el siguiente ejemplo de esta llamada.</span><span class="sxs-lookup"><span data-stu-id="7b8a1-160">See the following example  of this call.</span></span>

```
Request:
POST <fhir-server>/Patient/_search
Request Body:
given=hugh&family=chau

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  .
  .
  .
  "entry": [
    {
      "resource": {
        "resourceType": "Patient",
        "id": "<patient-id>",
        "name": [
          {
            "text": "Hugh Chau",
            "family": [ "Chau" ],
            "given": [ "Hugh" ]
          }
        ],
        "gender": "male",
        "birthDate": "1957-06-05"
      },
      "search": {
        "mode": "match"
      }
    }
  ]
}
```

<span data-ttu-id="7b8a1-161">Consulte [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="7b8a1-161">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="7b8a1-162">Observación</span><span class="sxs-lookup"><span data-stu-id="7b8a1-162">Observation</span></span>

<span data-ttu-id="7b8a1-163">Estos son los campos mínimos obligatorios, que son un subconjunto del perfil de constantes vitales de Argonaut:</span><span class="sxs-lookup"><span data-stu-id="7b8a1-163">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 - <span data-ttu-id="7b8a1-164">Vigencia (fecha o hora)</span><span class="sxs-lookup"><span data-stu-id="7b8a1-164">Effective (date time or period)</span></span>
 - <span data-ttu-id="7b8a1-165">Code. Coding. Code</span><span class="sxs-lookup"><span data-stu-id="7b8a1-165">Code.Coding.Code</span></span>
 - <span data-ttu-id="7b8a1-166">ValueQuantity. Value</span><span class="sxs-lookup"><span data-stu-id="7b8a1-166">ValueQuantity.Value</span></span>

<span data-ttu-id="7b8a1-167">Además de los campos Argonaut, para una experiencia de usuario excelente, la aplicación para pacientes también lee los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="7b8a1-167">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="7b8a1-168">Code. Coding. display</span><span class="sxs-lookup"><span data-stu-id="7b8a1-168">Code.Coding.Display</span></span>
 - <span data-ttu-id="7b8a1-169">Unidad ValueQuantity.</span><span class="sxs-lookup"><span data-stu-id="7b8a1-169">ValueQuantity.Unit</span></span>

<span data-ttu-id="7b8a1-170">Si se usan observaciones de componentes, se aplica la misma lógica para cada observación de componentes.</span><span class="sxs-lookup"><span data-stu-id="7b8a1-170">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="7b8a1-171">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="7b8a1-171">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="7b8a1-172">paciente =\<patient id\></span><span class="sxs-lookup"><span data-stu-id="7b8a1-172">patient=\<patient id\></span></span>
 - <span data-ttu-id="7b8a1-173">ordenar: DESC =\<field ex. date\></span><span class="sxs-lookup"><span data-stu-id="7b8a1-173">sort:desc=\<field ex. date\></span></span>

<span data-ttu-id="7b8a1-174">El objetivo es poder recuperar los últimos signos vitales para un paciente, [VitalSigns. DSTU. Saz] (observación?).</span><span class="sxs-lookup"><span data-stu-id="7b8a1-174">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

```
Request:
GET <fhir-server>/Observation?patient=<patient-id>&_sort:desc=date&category=vital-signs

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
        "category": {
          "coding": [ { code": "vital-signs" } ],
        },
        "code": {
          "coding": [
            {
              "system": "http://loinc.org",
              "code": "39156-5",
              "display": "bmi"
            }
          ],
        },
        "effectiveDateTime": "2009-12-01",
        "valueQuantity": {
          "value": 34.4,
          "unit": "kg/m2",
          "system": "http://unitsofmeasure.org",
          "code": "kg/m2"
        }
      },
    },
    .
    .
    .
  ]
}
```

<span data-ttu-id="7b8a1-175">Consulte [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="7b8a1-175">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="7b8a1-176">Condición</span><span class="sxs-lookup"><span data-stu-id="7b8a1-176">Condition</span></span>

<span data-ttu-id="7b8a1-177">Estos son los campos mínimos obligatorios, que son un subconjunto del [Perfil de condición Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span><span class="sxs-lookup"><span data-stu-id="7b8a1-177">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="7b8a1-178">Code. Coding [0]. Aparecen</span><span class="sxs-lookup"><span data-stu-id="7b8a1-178">Code.Coding[0].Display</span></span>

<span data-ttu-id="7b8a1-179">Además de los campos Argonaut, para una experiencia de usuario excelente, la aplicación de pacientes también puede leer los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="7b8a1-179">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="7b8a1-180">Fecha de grabación</span><span class="sxs-lookup"><span data-stu-id="7b8a1-180">Date Recorded</span></span>
 - <span data-ttu-id="7b8a1-181">Gravedad</span><span class="sxs-lookup"><span data-stu-id="7b8a1-181">Severity</span></span>

<span data-ttu-id="7b8a1-182">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="7b8a1-182">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="7b8a1-183">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="7b8a1-183">patient=\<patient id></span></span>
 - <span data-ttu-id="7b8a1-184">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="7b8a1-184">_count=\<max results></span></span>

<span data-ttu-id="7b8a1-185">Consulte el siguiente ejemplo de esta llamada:</span><span class="sxs-lookup"><span data-stu-id="7b8a1-185">See the following example of this call:</span></span>

```
Request:
GET <fhir-server>/Condition?patient=<patient-id>&_count=10

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "Condition",
        "id": "<resource-id>",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "386033004",
              "display": "Neuropathy (nerve damage)"
            }
          ]
        },
        "dateRecorded": "2018-09-17",
        "severity": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "24484000",
              "display": "Severe"
            }
          ]
        }
      },
    }
  ]
}
```

<span data-ttu-id="7b8a1-186">Consulte [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="7b8a1-186">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="7b8a1-187">Detect</span><span class="sxs-lookup"><span data-stu-id="7b8a1-187">Encounter</span></span>

<span data-ttu-id="7b8a1-188">Estos son los campos mínimos obligatorios, que son un subconjunto del núcleo de Estados Unidos y el perfil "debe tener" campos:</span><span class="sxs-lookup"><span data-stu-id="7b8a1-188">These are the minimum required fields, which are a subset of the US Core Encounter profile "must have" fields:</span></span>

 - <span data-ttu-id="7b8a1-189">Statu</span><span class="sxs-lookup"><span data-stu-id="7b8a1-189">Status</span></span>
 - <span data-ttu-id="7b8a1-190">Escriba [0]. Codificación [0]. Aparecen</span><span class="sxs-lookup"><span data-stu-id="7b8a1-190">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="7b8a1-191">Además, los siguientes campos de la parte central de Estados Unidos tienen los campos "debe ser compatible" del perfil.</span><span class="sxs-lookup"><span data-stu-id="7b8a1-191">In addition, the following fields from US Core Encounter profile's "must support" fields</span></span>

 - <span data-ttu-id="7b8a1-192">Start period</span><span class="sxs-lookup"><span data-stu-id="7b8a1-192">Period.Start</span></span>
 - <span data-ttu-id="7b8a1-193">Ubicación [0]. Location. display</span><span class="sxs-lookup"><span data-stu-id="7b8a1-193">Location[0].Location.Display</span></span>

<span data-ttu-id="7b8a1-194">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="7b8a1-194">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="7b8a1-195">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="7b8a1-195">patient=\<patient id></span></span>
 - <span data-ttu-id="7b8a1-196">_sort: DESC =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="7b8a1-196">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="7b8a1-197">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="7b8a1-197">_count=\<max results></span></span>

<span data-ttu-id="7b8a1-198">El objetivo es poder recuperar el último lugar conocido del paciente.</span><span class="sxs-lookup"><span data-stu-id="7b8a1-198">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="7b8a1-199">Cada uno de ellos hace referencia a un recurso de ubicación.</span><span class="sxs-lookup"><span data-stu-id="7b8a1-199">Each encounter references a location resource.</span></span> <span data-ttu-id="7b8a1-200">La referencia también incluirá el campo de visualización de la ubicación.</span><span class="sxs-lookup"><span data-stu-id="7b8a1-200">The reference shall also include the location's display field.</span></span> <span data-ttu-id="7b8a1-201">Consulta el siguiente ejemplo de esta llamada.</span><span class="sxs-lookup"><span data-stu-id="7b8a1-201">See the following example of this call.</span></span>

```
Request:
GET <fhir-server>/Encounter?patient=<patient-id>&_sort:desc=date&_count=1

Response:
{
  "resourceType": "Bundle",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "Encounter",
        "id": "<resource-id>",
        "identifier": [{ "use": "official", "value": "<id>" }],
        "status": "arrived",
        "type": [
          {
            "coding": [{ "display": "Appointment" }],
          }
        ],
        "patient": { "reference": "Patient/<patient-id>" },
        "period": { "start": "09/17/2018 1:00:00 PM" },
        "location": [
          {
            "location": { "display": "Clinic - ENT" },
          }
        ]
      }
    }
  ]
}
```

<span data-ttu-id="7b8a1-202">Consulte [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="7b8a1-202">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="7b8a1-203">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="7b8a1-203">AllergyIntolerance</span></span>

<span data-ttu-id="7b8a1-204">Estos son los campos mínimos obligatorios, que son un subconjunto del perfil de AllergyIntolerance de Argonaut:</span><span class="sxs-lookup"><span data-stu-id="7b8a1-204">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

 - <span data-ttu-id="7b8a1-205">Code. Text</span><span class="sxs-lookup"><span data-stu-id="7b8a1-205">Code.Text</span></span>
 - <span data-ttu-id="7b8a1-206">Code. Coding [0]. Aparecen</span><span class="sxs-lookup"><span data-stu-id="7b8a1-206">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="7b8a1-207">Statu</span><span class="sxs-lookup"><span data-stu-id="7b8a1-207">Status</span></span>

<span data-ttu-id="7b8a1-208">Además de los campos Argonaut, para una experiencia de usuario excelente, la aplicación para pacientes también lee los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="7b8a1-208">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="7b8a1-209">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="7b8a1-209">RecordedDate</span></span>
 - <span data-ttu-id="7b8a1-210">Nota. Text</span><span class="sxs-lookup"><span data-stu-id="7b8a1-210">Note.Text</span></span>
 - <span data-ttu-id="7b8a1-211">Reacción [...]. Sustancia. texto</span><span class="sxs-lookup"><span data-stu-id="7b8a1-211">Reaction[..].Substance.Text</span></span>
 - <span data-ttu-id="7b8a1-212">Reacción [...]. Manifesting [..]. Facturas</span><span class="sxs-lookup"><span data-stu-id="7b8a1-212">Reaction[..].Manifestation[..].Text</span></span>
 - <span data-ttu-id="7b8a1-213">Text. div</span><span class="sxs-lookup"><span data-stu-id="7b8a1-213">Text.Div</span></span>

<span data-ttu-id="7b8a1-214">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="7b8a1-214">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="7b8a1-215">Paciente =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="7b8a1-215">Patient =  \<patient id></span></span>

<span data-ttu-id="7b8a1-216">Consulte el siguiente ejemplo de esta llamada:</span><span class="sxs-lookup"><span data-stu-id="7b8a1-216">See the following example of this call:</span></span>

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
        "recordedDate": "2018-09-17T07:00:00.000Z",
        "substance": {
          "text": "Cashew nuts"
        },
        "status": "confirmed",
        "reaction": [
          {
            "substance": {
              "text": "cashew nut allergenic extract Injectable Product"
            },
            "manifestation": [
              {
                "text": "Anaphylactic reaction"
              }
            ]
          }
        ]
      }
    }
  ]
}
```

<span data-ttu-id="7b8a1-217">Consulte [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="7b8a1-217">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="7b8a1-218">Orden de los medicamentos</span><span class="sxs-lookup"><span data-stu-id="7b8a1-218">Medication Order</span></span>

<span data-ttu-id="7b8a1-219">Estos son los campos mínimos obligatorios, que son un subconjunto del perfil de MedicationOrder de Argonaut:</span><span class="sxs-lookup"><span data-stu-id="7b8a1-219">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

 - <span data-ttu-id="7b8a1-220">DateWritten</span><span class="sxs-lookup"><span data-stu-id="7b8a1-220">DateWritten</span></span>
 - <span data-ttu-id="7b8a1-221">Prescribir. Mostrar</span><span class="sxs-lookup"><span data-stu-id="7b8a1-221">Prescriber.Display</span></span>
 - <span data-ttu-id="7b8a1-222">Medicación. display (si Ref)</span><span class="sxs-lookup"><span data-stu-id="7b8a1-222">Medication.Display (if reference)</span></span>
 - <span data-ttu-id="7b8a1-223">Medicación. Text (si concepto)</span><span class="sxs-lookup"><span data-stu-id="7b8a1-223">Medication.Text (if concept)</span></span>

<span data-ttu-id="7b8a1-224">Además de los campos Argonaut, para una experiencia de usuario excelente, la aplicación de pacientes también puede leer los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="7b8a1-224">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="7b8a1-225">DateEnded</span><span class="sxs-lookup"><span data-stu-id="7b8a1-225">DateEnded</span></span>
 - <span data-ttu-id="7b8a1-226">DosageInstruction. Text</span><span class="sxs-lookup"><span data-stu-id="7b8a1-226">DosageInstruction.Text</span></span>
 - <span data-ttu-id="7b8a1-227">Text. div</span><span class="sxs-lookup"><span data-stu-id="7b8a1-227">Text.Div</span></span>

<span data-ttu-id="7b8a1-228">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="7b8a1-228">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="7b8a1-229">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="7b8a1-229">patient=\<patient id></span></span>
 - <span data-ttu-id="7b8a1-230">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="7b8a1-230">_count=\<max results></span></span>

<span data-ttu-id="7b8a1-231">Consulte el siguiente ejemplo de esta llamada:</span><span class="sxs-lookup"><span data-stu-id="7b8a1-231">See the following example of this call:</span></span>

```
Request:
GET <fhir-server>/MedicationOrder?patient=<patient-id>&_count=10

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "MedicationOrder",
        "id": "<resource-id>",
        "dateWritten": "2018-09-17",
        "medicationCodeableConcept": {
          "text": "Lisinopril 20 MG Oral Tablet"
        },
        "prescriber": {
          "display": "Jane Doe"
        },
        "dosageInstruction": [
          {
            "text": "1 daily"
          }
        ]
      }
    }
  ]
}
```

<span data-ttu-id="7b8a1-232">Consulte [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="7b8a1-232">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="7b8a1-233">Beneficios</span><span class="sxs-lookup"><span data-stu-id="7b8a1-233">Coverage</span></span>

<span data-ttu-id="7b8a1-234">Estos son los campos mínimos obligatorios, no incluidos en los perfiles de los Estados Unidos Core o Argonaut:</span><span class="sxs-lookup"><span data-stu-id="7b8a1-234">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="7b8a1-235">Payor</span><span class="sxs-lookup"><span data-stu-id="7b8a1-235">Payor</span></span>

<span data-ttu-id="7b8a1-236">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="7b8a1-236">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="7b8a1-237">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="7b8a1-237">patient=\<patient id></span></span>

<span data-ttu-id="7b8a1-238">Consulte el siguiente ejemplo de esta llamada:</span><span class="sxs-lookup"><span data-stu-id="7b8a1-238">See the following example of this call:</span></span>

```
Request:
GET <fhir-server>/Coverage?patient=<patient-id>

Response:
{
  "resourceType": "Bundle",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "Coverage",
        "id": "<resource-id>",
        "plan": "No Primary Insurance",
        "subscriber": { "reference": "Patient/<patient-id>" }
      }
    }
  ]
}
```
    
<span data-ttu-id="7b8a1-239">Consulte [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="7b8a1-239">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="7b8a1-240">Ubicación</span><span class="sxs-lookup"><span data-stu-id="7b8a1-240">Location</span></span>

<span data-ttu-id="7b8a1-241">Este recurso solo se usa como referencia en el recurso de [problemas](#encounter) .</span><span class="sxs-lookup"><span data-stu-id="7b8a1-241">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="7b8a1-242">Consulte [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="7b8a1-242">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
