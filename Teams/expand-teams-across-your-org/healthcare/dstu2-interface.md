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
ms.openlocfilehash: d29dab88f6ee53eb4c758f6c95f71278e20ecdbe
ms.sourcegitcommit: 0a51738879b13991986a3a872445daa8bd20533d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "48766983"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="a652d-103">Especificación de la interfaz DSTU2</span><span class="sxs-lookup"><span data-stu-id="a652d-103">DSTU2 interface specification</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a652d-104">**Desde el 30 de octubre de 2020, la aplicación de pacientes estará obsoleta y los usuarios ya no podrán instalarla desde la tienda de aplicaciones de Teams. Le recomendamos que empiece a usar la [aplicación lists](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) en Teams hoy.**</span><span class="sxs-lookup"><span data-stu-id="a652d-104">**Effective October 30, 2020, the Patients app will be deprecated and users will no longer be able to install it from the Teams app store. We encourage you to start using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams today.**</span></span>
>
><span data-ttu-id="a652d-105">Los datos de la aplicación patients se almacenan en el buzón de grupo del grupo Office 365 que respalda al equipo.</span><span class="sxs-lookup"><span data-stu-id="a652d-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="a652d-106">Cuando se retira la aplicación de pacientes, todos los datos asociados con ella se conservarán en este grupo, pero ya no se podrá obtener acceso a ellas a través de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="a652d-106">When the Patients app is retired, all data associated with it will be retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="a652d-107">Los usuarios actuales pueden volver a crear sus listas con la [aplicación listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span><span class="sxs-lookup"><span data-stu-id="a652d-107">Current users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="a652d-108">La [aplicación listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) está preinstalada para todos los usuarios de Teams y está disponible como una pestaña en todos los equipos y canales.</span><span class="sxs-lookup"><span data-stu-id="a652d-108">The [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) is pre-installed for all Teams users and is available as a tab in every team and channel.</span></span> <span data-ttu-id="a652d-109">Con las listas, los equipos de estado pueden crear listas de pacientes con la plantilla de pacientes integrados, desde cero o importando datos a Excel.</span><span class="sxs-lookup"><span data-stu-id="a652d-109">With Lists, health teams can create patient lists using the built-in Patients template, from scratch, or by importing data to Excel.</span></span> <span data-ttu-id="a652d-110">Para obtener más información sobre cómo administrar la aplicación listas de su organización, vea [administrar la aplicación listas](../../manage-lists-app.md).</span><span class="sxs-lookup"><span data-stu-id="a652d-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="a652d-111">Para configurar o volver a configurar un servidor de FHIR para que funcione con la aplicación para pacientes de Microsoft Teams, es necesario comprender a qué datos necesita acceder la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a652d-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="a652d-112">El servidor de FHIR debe admitir solicitudes POST con paquetes para los siguientes recursos:</span><span class="sxs-lookup"><span data-stu-id="a652d-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="a652d-113">Propio</span><span class="sxs-lookup"><span data-stu-id="a652d-113">Patient</span></span>](#patient)
- [<span data-ttu-id="a652d-114">Observación</span><span class="sxs-lookup"><span data-stu-id="a652d-114">Observation</span></span>](#observation)
- [<span data-ttu-id="a652d-115">Condición</span><span class="sxs-lookup"><span data-stu-id="a652d-115">Condition</span></span>](#condition)
- [<span data-ttu-id="a652d-116">Detect</span><span class="sxs-lookup"><span data-stu-id="a652d-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="a652d-117">Intolerancia de alergia</span><span class="sxs-lookup"><span data-stu-id="a652d-117">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="a652d-118">Beneficios</span><span class="sxs-lookup"><span data-stu-id="a652d-118">Coverage</span></span>](#coverage)
- [<span data-ttu-id="a652d-119">Orden de los medicamentos</span><span class="sxs-lookup"><span data-stu-id="a652d-119">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="a652d-120">Ubicación</span><span class="sxs-lookup"><span data-stu-id="a652d-120">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="a652d-121">El recurso paciente es el único recurso obligatorio (sin que la aplicación se cargue en absoluto).</span><span class="sxs-lookup"><span data-stu-id="a652d-121">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="a652d-122">Sin embargo, se recomienda que el socio implemente la compatibilidad de todos los recursos mencionados anteriormente según las especificaciones proporcionadas a continuación para obtener la mejor experiencia para el usuario final con la aplicación de pacientes de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a652d-122">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="a652d-123">Las consultas de la aplicación de pacientes de Microsoft Teams para más de un recurso publican un paquete (lote) de solicitudes a la dirección URL del servidor FHIR.</span><span class="sxs-lookup"><span data-stu-id="a652d-123">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="a652d-124">El servidor procesa cada solicitud y devuelve un paquete de los recursos coincidentes con cada solicitud.</span><span class="sxs-lookup"><span data-stu-id="a652d-124">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="a652d-125">Para obtener más información y ejemplos, consulte [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) .</span><span class="sxs-lookup"><span data-stu-id="a652d-125">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="a652d-126">Todos los siguientes recursos de FHIR deben ser accesibles mediante la referencia directa de recursos.</span><span class="sxs-lookup"><span data-stu-id="a652d-126">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="a652d-127">Conjunto de campos obligatorios mínimos de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="a652d-127">Conformance minimum required field set</span></span>

 <span data-ttu-id="a652d-128">El servidor de FHIR debe implementar la declaración de conformidad para que nosotros tenga un resumen del objetivo de sus capacidades.</span><span class="sxs-lookup"><span data-stu-id="a652d-128">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="a652d-129">Esperamos los siguientes parámetros en un DSTU2 FHIR Server:</span><span class="sxs-lookup"><span data-stu-id="a652d-129">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

 - <span data-ttu-id="a652d-130">DESCANSO</span><span class="sxs-lookup"><span data-stu-id="a652d-130">REST</span></span>

    - <span data-ttu-id="a652d-131">Modo</span><span class="sxs-lookup"><span data-stu-id="a652d-131">Mode</span></span>
    - <span data-ttu-id="a652d-132">MOV</span><span class="sxs-lookup"><span data-stu-id="a652d-132">Interaction</span></span>
    - <span data-ttu-id="a652d-133">Recurso: tipo</span><span class="sxs-lookup"><span data-stu-id="a652d-133">Resource: Type</span></span>
    - <span data-ttu-id="a652d-134">Seguridad: [extensión para URI de OAuth](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="a652d-134">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
   
 - <span data-ttu-id="a652d-135">FhirVersion (nuestro código requiere esto para comprender a qué versión debemos dinamizar, ya que admitimos varias versiones).</span><span class="sxs-lookup"><span data-stu-id="a652d-135">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="a652d-136">Consulte [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="a652d-136">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="a652d-137">Propio</span><span class="sxs-lookup"><span data-stu-id="a652d-137">Patient</span></span>

<span data-ttu-id="a652d-138">Estos son los campos mínimos obligatorios, que son un subconjunto de los campos de [Perfil del paciente de Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) :</span><span class="sxs-lookup"><span data-stu-id="a652d-138">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

 - <span data-ttu-id="a652d-139">Nombre. familia</span><span class="sxs-lookup"><span data-stu-id="a652d-139">Name.Family</span></span>
 - <span data-ttu-id="a652d-140">Nombre. dado</span><span class="sxs-lookup"><span data-stu-id="a652d-140">Name.Given</span></span>
 - <span data-ttu-id="a652d-141">Hombres</span><span class="sxs-lookup"><span data-stu-id="a652d-141">Gender</span></span>
 - <span data-ttu-id="a652d-142">FechaNacimiento</span><span class="sxs-lookup"><span data-stu-id="a652d-142">BirthDate</span></span>
 - <span data-ttu-id="a652d-143">MRN (identificador)</span><span class="sxs-lookup"><span data-stu-id="a652d-143">MRN (Identifier)</span></span>

<span data-ttu-id="a652d-144">Además de los campos Argonaut, para una experiencia de usuario excelente, la aplicación para pacientes también lee los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="a652d-144">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="a652d-145">Nombre. Use</span><span class="sxs-lookup"><span data-stu-id="a652d-145">Name.Use</span></span>
 - <span data-ttu-id="a652d-146">Nombre. Prefix</span><span class="sxs-lookup"><span data-stu-id="a652d-146">Name.Prefix</span></span>
 - <span data-ttu-id="a652d-147">CareProvider (esta referencia en el recurso paciente debe incluir los campos de visualización que se muestran en el ejemplo siguiente).</span><span class="sxs-lookup"><span data-stu-id="a652d-147">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

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

<span data-ttu-id="a652d-148">Una búsqueda de recursos usa el método POST en/patient/_search y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="a652d-148">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="a652d-149">identificar</span><span class="sxs-lookup"><span data-stu-id="a652d-149">id</span></span>
 - <span data-ttu-id="a652d-150">Family: contiene = (busca todos los pacientes cuyo nombre contenga el valor).</span><span class="sxs-lookup"><span data-stu-id="a652d-150">family:contains=(searches for all patients whose family name contains the value.)</span></span>
 - <span data-ttu-id="a652d-151">dado =\<substring></span><span class="sxs-lookup"><span data-stu-id="a652d-151">given=\<substring></span></span>
 - <span data-ttu-id="a652d-152">Name =\<substring></span><span class="sxs-lookup"><span data-stu-id="a652d-152">name=\<substring></span></span>
 - <span data-ttu-id="a652d-153">FechaNacimiento = (coincidencia exacta)</span><span class="sxs-lookup"><span data-stu-id="a652d-153">birthdate=(exact match)</span></span>
 - <span data-ttu-id="a652d-154">\_contar (número máximo de resultados que se deben devolver)</span><span class="sxs-lookup"><span data-stu-id="a652d-154">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="a652d-155">La respuesta debe contener el recuento total de registros devueltos como resultado de la búsqueda, y \_ el PatientsApp usará Count para limitar el número de registros devueltos.</span><span class="sxs-lookup"><span data-stu-id="a652d-155">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="a652d-156">Identifier =\<mrn></span><span class="sxs-lookup"><span data-stu-id="a652d-156">identifier=\<mrn></span></span>

<span data-ttu-id="a652d-157">El objetivo es poder buscar y filtrar a un paciente por lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a652d-157">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="a652d-158">ID: es el identificador de recurso que tiene cada recurso en FHIR.</span><span class="sxs-lookup"><span data-stu-id="a652d-158">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="a652d-159">MRN: este es el identificador real del paciente que sabría el personal clínico.</span><span class="sxs-lookup"><span data-stu-id="a652d-159">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="a652d-160">Entendemos que este MRN se basa en el tipo de identificador dentro del recurso Identifier en FHIR</span><span class="sxs-lookup"><span data-stu-id="a652d-160">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="a652d-161">Nombre</span><span class="sxs-lookup"><span data-stu-id="a652d-161">Name</span></span>
- <span data-ttu-id="a652d-162">FechaNacimiento</span><span class="sxs-lookup"><span data-stu-id="a652d-162">Birthdate</span></span>

<span data-ttu-id="a652d-163">Consulta el siguiente ejemplo de esta llamada.</span><span class="sxs-lookup"><span data-stu-id="a652d-163">See the following example  of this call.</span></span>

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

<span data-ttu-id="a652d-164">Consulte [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="a652d-164">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="a652d-165">Observación</span><span class="sxs-lookup"><span data-stu-id="a652d-165">Observation</span></span>

<span data-ttu-id="a652d-166">Estos son los campos mínimos obligatorios, que son un subconjunto del perfil de constantes vitales de Argonaut:</span><span class="sxs-lookup"><span data-stu-id="a652d-166">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 - <span data-ttu-id="a652d-167">Vigencia (fecha o hora)</span><span class="sxs-lookup"><span data-stu-id="a652d-167">Effective (date time or period)</span></span>
 - <span data-ttu-id="a652d-168">Code. Coding. Code</span><span class="sxs-lookup"><span data-stu-id="a652d-168">Code.Coding.Code</span></span>
 - <span data-ttu-id="a652d-169">ValueQuantity. Value</span><span class="sxs-lookup"><span data-stu-id="a652d-169">ValueQuantity.Value</span></span>

<span data-ttu-id="a652d-170">Además de los campos Argonaut, para una experiencia de usuario excelente, la aplicación para pacientes también lee los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="a652d-170">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="a652d-171">Code. Coding. display</span><span class="sxs-lookup"><span data-stu-id="a652d-171">Code.Coding.Display</span></span>
 - <span data-ttu-id="a652d-172">Unidad ValueQuantity.</span><span class="sxs-lookup"><span data-stu-id="a652d-172">ValueQuantity.Unit</span></span>

<span data-ttu-id="a652d-173">Si se usan observaciones de componentes, se aplica la misma lógica para cada observación de componentes.</span><span class="sxs-lookup"><span data-stu-id="a652d-173">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="a652d-174">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="a652d-174">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="a652d-175">paciente =\<patient id\></span><span class="sxs-lookup"><span data-stu-id="a652d-175">patient=\<patient id\></span></span>
 - <span data-ttu-id="a652d-176">ordenar: DESC =\<field ex. date\></span><span class="sxs-lookup"><span data-stu-id="a652d-176">sort:desc=\<field ex. date\></span></span>

<span data-ttu-id="a652d-177">El objetivo es poder recuperar los últimos signos vitales para un paciente, [VitalSigns. DSTU. Saz] (observación?).</span><span class="sxs-lookup"><span data-stu-id="a652d-177">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

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

<span data-ttu-id="a652d-178">Consulte [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="a652d-178">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="a652d-179">Condición</span><span class="sxs-lookup"><span data-stu-id="a652d-179">Condition</span></span>

<span data-ttu-id="a652d-180">Estos son los campos mínimos obligatorios, que son un subconjunto del [Perfil de condición Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span><span class="sxs-lookup"><span data-stu-id="a652d-180">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="a652d-181">Code. Coding [0]. Aparecen</span><span class="sxs-lookup"><span data-stu-id="a652d-181">Code.Coding[0].Display</span></span>

<span data-ttu-id="a652d-182">Además de los campos Argonaut, para una experiencia de usuario excelente, la aplicación de pacientes también puede leer los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="a652d-182">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="a652d-183">Fecha de grabación</span><span class="sxs-lookup"><span data-stu-id="a652d-183">Date Recorded</span></span>
 - <span data-ttu-id="a652d-184">Gravedad</span><span class="sxs-lookup"><span data-stu-id="a652d-184">Severity</span></span>

<span data-ttu-id="a652d-185">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="a652d-185">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="a652d-186">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="a652d-186">patient=\<patient id></span></span>
 - <span data-ttu-id="a652d-187">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="a652d-187">_count=\<max results></span></span>

<span data-ttu-id="a652d-188">Consulte el siguiente ejemplo de esta llamada:</span><span class="sxs-lookup"><span data-stu-id="a652d-188">See the following example of this call:</span></span>

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

<span data-ttu-id="a652d-189">Consulte [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="a652d-189">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="a652d-190">Detect</span><span class="sxs-lookup"><span data-stu-id="a652d-190">Encounter</span></span>

<span data-ttu-id="a652d-191">Estos son los campos mínimos obligatorios, que son un subconjunto del núcleo de Estados Unidos y el perfil "debe tener" campos:</span><span class="sxs-lookup"><span data-stu-id="a652d-191">These are the minimum required fields, which are a subset of the US Core Encounter profile "must have" fields:</span></span>

 - <span data-ttu-id="a652d-192">Statu</span><span class="sxs-lookup"><span data-stu-id="a652d-192">Status</span></span>
 - <span data-ttu-id="a652d-193">Escriba [0]. Codificación [0]. Aparecen</span><span class="sxs-lookup"><span data-stu-id="a652d-193">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="a652d-194">Además, los siguientes campos de la parte central de Estados Unidos tienen los campos "debe ser compatible" del perfil.</span><span class="sxs-lookup"><span data-stu-id="a652d-194">In addition, the following fields from US Core Encounter profile's "must support" fields</span></span>

 - <span data-ttu-id="a652d-195">Start period</span><span class="sxs-lookup"><span data-stu-id="a652d-195">Period.Start</span></span>
 - <span data-ttu-id="a652d-196">Ubicación [0]. Location. display</span><span class="sxs-lookup"><span data-stu-id="a652d-196">Location[0].Location.Display</span></span>

<span data-ttu-id="a652d-197">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="a652d-197">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="a652d-198">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="a652d-198">patient=\<patient id></span></span>
 - <span data-ttu-id="a652d-199">_sort: DESC =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="a652d-199">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="a652d-200">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="a652d-200">_count=\<max results></span></span>

<span data-ttu-id="a652d-201">El objetivo es poder recuperar el último lugar conocido del paciente.</span><span class="sxs-lookup"><span data-stu-id="a652d-201">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="a652d-202">Cada uno de ellos hace referencia a un recurso de ubicación.</span><span class="sxs-lookup"><span data-stu-id="a652d-202">Each encounter references a location resource.</span></span> <span data-ttu-id="a652d-203">La referencia también incluirá el campo de visualización de la ubicación.</span><span class="sxs-lookup"><span data-stu-id="a652d-203">The reference shall also include the location's display field.</span></span> <span data-ttu-id="a652d-204">Consulta el siguiente ejemplo de esta llamada.</span><span class="sxs-lookup"><span data-stu-id="a652d-204">See the following example of this call.</span></span>

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

<span data-ttu-id="a652d-205">Consulte [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="a652d-205">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="a652d-206">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="a652d-206">AllergyIntolerance</span></span>

<span data-ttu-id="a652d-207">Estos son los campos mínimos obligatorios, que son un subconjunto del perfil de AllergyIntolerance de Argonaut:</span><span class="sxs-lookup"><span data-stu-id="a652d-207">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

 - <span data-ttu-id="a652d-208">Code. Text</span><span class="sxs-lookup"><span data-stu-id="a652d-208">Code.Text</span></span>
 - <span data-ttu-id="a652d-209">Code. Coding [0]. Aparecen</span><span class="sxs-lookup"><span data-stu-id="a652d-209">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="a652d-210">Statu</span><span class="sxs-lookup"><span data-stu-id="a652d-210">Status</span></span>

<span data-ttu-id="a652d-211">Además de los campos Argonaut, para una experiencia de usuario excelente, la aplicación para pacientes también lee los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="a652d-211">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="a652d-212">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="a652d-212">RecordedDate</span></span>
 - <span data-ttu-id="a652d-213">Nota. Text</span><span class="sxs-lookup"><span data-stu-id="a652d-213">Note.Text</span></span>
 - <span data-ttu-id="a652d-214">Reacción [...]. Sustancia. texto</span><span class="sxs-lookup"><span data-stu-id="a652d-214">Reaction[..].Substance.Text</span></span>
 - <span data-ttu-id="a652d-215">Reacción [...]. Manifesting [..]. Facturas</span><span class="sxs-lookup"><span data-stu-id="a652d-215">Reaction[..].Manifestation[..].Text</span></span>
 - <span data-ttu-id="a652d-216">Text. div</span><span class="sxs-lookup"><span data-stu-id="a652d-216">Text.Div</span></span>

<span data-ttu-id="a652d-217">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="a652d-217">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="a652d-218">Paciente =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="a652d-218">Patient =  \<patient id></span></span>

<span data-ttu-id="a652d-219">Consulte el siguiente ejemplo de esta llamada:</span><span class="sxs-lookup"><span data-stu-id="a652d-219">See the following example of this call:</span></span>

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

<span data-ttu-id="a652d-220">Consulte [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="a652d-220">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="a652d-221">Orden de los medicamentos</span><span class="sxs-lookup"><span data-stu-id="a652d-221">Medication Order</span></span>

<span data-ttu-id="a652d-222">Estos son los campos mínimos obligatorios, que son un subconjunto del perfil de MedicationOrder de Argonaut:</span><span class="sxs-lookup"><span data-stu-id="a652d-222">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

 - <span data-ttu-id="a652d-223">DateWritten</span><span class="sxs-lookup"><span data-stu-id="a652d-223">DateWritten</span></span>
 - <span data-ttu-id="a652d-224">Prescribir. Mostrar</span><span class="sxs-lookup"><span data-stu-id="a652d-224">Prescriber.Display</span></span>
 - <span data-ttu-id="a652d-225">Medicación. display (si Ref)</span><span class="sxs-lookup"><span data-stu-id="a652d-225">Medication.Display (if reference)</span></span>
 - <span data-ttu-id="a652d-226">Medicación. Text (si concepto)</span><span class="sxs-lookup"><span data-stu-id="a652d-226">Medication.Text (if concept)</span></span>

<span data-ttu-id="a652d-227">Además de los campos Argonaut, para una experiencia de usuario excelente, la aplicación de pacientes también puede leer los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="a652d-227">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="a652d-228">DateEnded</span><span class="sxs-lookup"><span data-stu-id="a652d-228">DateEnded</span></span>
 - <span data-ttu-id="a652d-229">DosageInstruction. Text</span><span class="sxs-lookup"><span data-stu-id="a652d-229">DosageInstruction.Text</span></span>
 - <span data-ttu-id="a652d-230">Text. div</span><span class="sxs-lookup"><span data-stu-id="a652d-230">Text.Div</span></span>

<span data-ttu-id="a652d-231">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="a652d-231">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="a652d-232">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="a652d-232">patient=\<patient id></span></span>
 - <span data-ttu-id="a652d-233">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="a652d-233">_count=\<max results></span></span>

<span data-ttu-id="a652d-234">Consulte el siguiente ejemplo de esta llamada:</span><span class="sxs-lookup"><span data-stu-id="a652d-234">See the following example of this call:</span></span>

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

<span data-ttu-id="a652d-235">Consulte [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="a652d-235">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="a652d-236">Beneficios</span><span class="sxs-lookup"><span data-stu-id="a652d-236">Coverage</span></span>

<span data-ttu-id="a652d-237">Estos son los campos mínimos obligatorios, no incluidos en los perfiles de los Estados Unidos Core o Argonaut:</span><span class="sxs-lookup"><span data-stu-id="a652d-237">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="a652d-238">Payor</span><span class="sxs-lookup"><span data-stu-id="a652d-238">Payor</span></span>

<span data-ttu-id="a652d-239">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="a652d-239">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="a652d-240">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="a652d-240">patient=\<patient id></span></span>

<span data-ttu-id="a652d-241">Consulte el siguiente ejemplo de esta llamada:</span><span class="sxs-lookup"><span data-stu-id="a652d-241">See the following example of this call:</span></span>

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
    
<span data-ttu-id="a652d-242">Consulte [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="a652d-242">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="a652d-243">Ubicación</span><span class="sxs-lookup"><span data-stu-id="a652d-243">Location</span></span>

<span data-ttu-id="a652d-244">Este recurso solo se usa como referencia en el recurso de [problemas](#encounter) .</span><span class="sxs-lookup"><span data-stu-id="a652d-244">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="a652d-245">Consulte [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="a652d-245">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
