---
title: Aplicación Pacientes e interfaz de DSTU2 de integración de EHR
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
description: Obtenga más información sobre la especificación de la interfaz DSTU2 en Teams, incluida la configuración o reconfiguración de un servidor F LDAP para que funcione con la aplicación Pacientes de Microsoft Teams.
ms.custom: seo-marvel-mar2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 12833ea55977cf7e8d18ee5c10b1f17d898b27b3
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803488"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="36be5-103">Especificación de la interfaz DSTU2</span><span class="sxs-lookup"><span data-stu-id="36be5-103">DSTU2 interface specification</span></span>

> [!NOTE]
> <span data-ttu-id="36be5-104">A partir del 30 de octubre de 2020, la aplicación Pacientes se ha retirado y reemplazado por la [aplicación Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) en Teams.</span><span class="sxs-lookup"><span data-stu-id="36be5-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="36be5-105">Los datos de la aplicación Pacientes se almacenan en el buzón de grupo del grupo de Office 365 que copia de seguridad del equipo.</span><span class="sxs-lookup"><span data-stu-id="36be5-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="36be5-106">Todos los datos asociados a la aplicación Pacientes se conservan en este grupo, pero ya no se puede acceder a ellos a través de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="36be5-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="36be5-107">Los usuarios pueden volver a crear sus listas con la [aplicación Listas.](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)</span><span class="sxs-lookup"><span data-stu-id="36be5-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="36be5-108">Con Listas, los equipos de atención al paciente de su organización sanitaria pueden crear listas de pacientes para situaciones que van desde las reuniones interdisciplinarias y las reuniones del equipo hasta la supervisión general del paciente.</span><span class="sxs-lookup"><span data-stu-id="36be5-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="36be5-109">Consulte la plantilla Pacientes en Listas para empezar.</span><span class="sxs-lookup"><span data-stu-id="36be5-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="36be5-110">Para obtener más información sobre cómo administrar la aplicación Listas en su organización, vea [Administrar la aplicación Listas.](../../manage-lists-app.md)</span><span class="sxs-lookup"><span data-stu-id="36be5-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="36be5-111">Configurar o volver a configurar un servidor FCONTR para trabajar con la aplicación Microsoft Teams Patients requiere comprender a qué datos debe tener acceso la aplicación.</span><span class="sxs-lookup"><span data-stu-id="36be5-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="36be5-112">El servidor FCONTR debe admitir solicitudes POST mediante agrupaciones para los siguientes recursos:</span><span class="sxs-lookup"><span data-stu-id="36be5-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="36be5-113">Paciente</span><span class="sxs-lookup"><span data-stu-id="36be5-113">Patient</span></span>](#patient)
- [<span data-ttu-id="36be5-114">Observación</span><span class="sxs-lookup"><span data-stu-id="36be5-114">Observation</span></span>](#observation)
- [<span data-ttu-id="36be5-115">Condición</span><span class="sxs-lookup"><span data-stu-id="36be5-115">Condition</span></span>](#condition)
- [<span data-ttu-id="36be5-116">Encounter</span><span class="sxs-lookup"><span data-stu-id="36be5-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="36be5-117">Ser insondosa</span><span class="sxs-lookup"><span data-stu-id="36be5-117">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="36be5-118">Cobertura</span><span class="sxs-lookup"><span data-stu-id="36be5-118">Coverage</span></span>](#coverage)
- [<span data-ttu-id="36be5-119">Orden de medicamentos</span><span class="sxs-lookup"><span data-stu-id="36be5-119">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="36be5-120">Ubicación</span><span class="sxs-lookup"><span data-stu-id="36be5-120">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="36be5-121">El recurso paciente es el único recurso obligatorio (sin el que la aplicación no se cargará en absoluto).</span><span class="sxs-lookup"><span data-stu-id="36be5-121">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="36be5-122">Sin embargo, se recomienda que el partner implemente soporte técnico para todos los recursos mencionados anteriormente según las especificaciones que se proporcionan a continuación para obtener la mejor experiencia del usuario final con la aplicación Pacientes de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="36be5-122">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="36be5-123">Las consultas desde la aplicación Pacientes de Microsoft Teams para más de un recurso publican un paquete (BATCH) de solicitudes en la dirección URL del servidor FCONF.</span><span class="sxs-lookup"><span data-stu-id="36be5-123">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="36be5-124">El servidor procesa cada solicitud y devuelve un paquete de los recursos que coinciden con cada solicitud.</span><span class="sxs-lookup"><span data-stu-id="36be5-124">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="36be5-125">Para obtener más información y ejemplos, vea [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) .</span><span class="sxs-lookup"><span data-stu-id="36be5-125">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="36be5-126">Todos los siguientes recursos de FCONTR deben ser accesibles por referencia directa de recursos.</span><span class="sxs-lookup"><span data-stu-id="36be5-126">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="36be5-127">Conjunto de campos requeridos de conformidad mínima</span><span class="sxs-lookup"><span data-stu-id="36be5-127">Conformance minimum required field set</span></span>

 <span data-ttu-id="36be5-128">El servidor FCONTRA debe implementar la declaración de conformidad para que tendrán un resumen objetiva de sus capacidades.</span><span class="sxs-lookup"><span data-stu-id="36be5-128">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="36be5-129">Esperamos los parámetros siguientes en un servidor DSTU2 FCONTR:</span><span class="sxs-lookup"><span data-stu-id="36be5-129">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

 - <span data-ttu-id="36be5-130">REST</span><span class="sxs-lookup"><span data-stu-id="36be5-130">REST</span></span>

    - <span data-ttu-id="36be5-131">Modo</span><span class="sxs-lookup"><span data-stu-id="36be5-131">Mode</span></span>
    - <span data-ttu-id="36be5-132">Interacción</span><span class="sxs-lookup"><span data-stu-id="36be5-132">Interaction</span></span>
    - <span data-ttu-id="36be5-133">Recurso: tipo</span><span class="sxs-lookup"><span data-stu-id="36be5-133">Resource: Type</span></span>
    - <span data-ttu-id="36be5-134">Seguridad: [Extensión para URI de OAuth](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="36be5-134">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
   
 - <span data-ttu-id="36be5-135">FcontrVersion (Nuestro código requiere esto para comprender a qué versión debemos cambiar, ya que se admiten varias versiones).</span><span class="sxs-lookup"><span data-stu-id="36be5-135">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="36be5-136">Consulte [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) otros detalles sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="36be5-136">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="36be5-137">Paciente</span><span class="sxs-lookup"><span data-stu-id="36be5-137">Patient</span></span>

<span data-ttu-id="36be5-138">Estos son los campos necesarios mínimos, que son un subconjunto de los campos del perfil [de paciente:](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)</span><span class="sxs-lookup"><span data-stu-id="36be5-138">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

 - <span data-ttu-id="36be5-139">Name.Family</span><span class="sxs-lookup"><span data-stu-id="36be5-139">Name.Family</span></span>
 - <span data-ttu-id="36be5-140">Name.Given</span><span class="sxs-lookup"><span data-stu-id="36be5-140">Name.Given</span></span>
 - <span data-ttu-id="36be5-141">Sexo</span><span class="sxs-lookup"><span data-stu-id="36be5-141">Gender</span></span>
 - <span data-ttu-id="36be5-142">FechaDe Nacimiento</span><span class="sxs-lookup"><span data-stu-id="36be5-142">BirthDate</span></span>
 - <span data-ttu-id="36be5-143">MRN (identificador)</span><span class="sxs-lookup"><span data-stu-id="36be5-143">MRN (Identifier)</span></span>

<span data-ttu-id="36be5-144">Además de los campos Salesforce, para una excelente experiencia del usuario, la aplicación Pacientes también lee los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="36be5-144">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="36be5-145">Name.Use</span><span class="sxs-lookup"><span data-stu-id="36be5-145">Name.Use</span></span>
 - <span data-ttu-id="36be5-146">Name.Prefix</span><span class="sxs-lookup"><span data-stu-id="36be5-146">Name.Prefix</span></span>
 - <span data-ttu-id="36be5-147">CareProvider (esta referencia del recurso Paciente debe incluir los campos para mostrar que se muestran en el ejemplo siguiente).</span><span class="sxs-lookup"><span data-stu-id="36be5-147">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

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

<span data-ttu-id="36be5-148">Una búsqueda de recursos usa el método POST en /Patient/_search y los parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="36be5-148">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="36be5-149">id</span><span class="sxs-lookup"><span data-stu-id="36be5-149">id</span></span>
 - <span data-ttu-id="36be5-150">familia:contains=(busca a todos los pacientes cuyo nombre de familia contiene el valor).</span><span class="sxs-lookup"><span data-stu-id="36be5-150">family:contains=(searches for all patients whose family name contains the value.)</span></span>
 - <span data-ttu-id="36be5-151">given=\<substring></span><span class="sxs-lookup"><span data-stu-id="36be5-151">given=\<substring></span></span>
 - <span data-ttu-id="36be5-152">name=\<substring></span><span class="sxs-lookup"><span data-stu-id="36be5-152">name=\<substring></span></span>
 - <span data-ttu-id="36be5-153">fechade nacimiento=(coincidencia exacta)</span><span class="sxs-lookup"><span data-stu-id="36be5-153">birthdate=(exact match)</span></span>
 - <span data-ttu-id="36be5-154">\_recuento (número máximo de resultados que se deben devolver)</span><span class="sxs-lookup"><span data-stu-id="36be5-154">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="36be5-155">La respuesta debe contener el recuento total de registros devueltos como resultado de la búsqueda y el recuento la utilizará la Aplicación Pacientes para limitar el número de registros \_ devueltos.</span><span class="sxs-lookup"><span data-stu-id="36be5-155">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="36be5-156">identifier=\<mrn></span><span class="sxs-lookup"><span data-stu-id="36be5-156">identifier=\<mrn></span></span>

<span data-ttu-id="36be5-157">El objetivo es poder buscar y filtrar a un paciente siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="36be5-157">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="36be5-158">Id.: este es el id. de recurso que tiene cada recurso de FCONTR.</span><span class="sxs-lookup"><span data-stu-id="36be5-158">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="36be5-159">MRN: este es el identificador real para el paciente que el personal clínico conocería.</span><span class="sxs-lookup"><span data-stu-id="36be5-159">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="36be5-160">Entendemos que este MRN se basa en el tipo de identificador dentro del recurso de identificador en FCONTRA</span><span class="sxs-lookup"><span data-stu-id="36be5-160">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="36be5-161">Nombre</span><span class="sxs-lookup"><span data-stu-id="36be5-161">Name</span></span>
- <span data-ttu-id="36be5-162">Fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="36be5-162">Birthdate</span></span>

<span data-ttu-id="36be5-163">Vea el siguiente ejemplo de esta llamada.</span><span class="sxs-lookup"><span data-stu-id="36be5-163">See the following example  of this call.</span></span>

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

<span data-ttu-id="36be5-164">Consulte [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) otros detalles sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="36be5-164">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="36be5-165">Observación</span><span class="sxs-lookup"><span data-stu-id="36be5-165">Observation</span></span>

<span data-ttu-id="36be5-166">Estos son los campos necesarios mínimos, que son un subconjunto del perfil de signos vitales:</span><span class="sxs-lookup"><span data-stu-id="36be5-166">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 - <span data-ttu-id="36be5-167">Efectivo (fecha y hora)</span><span class="sxs-lookup"><span data-stu-id="36be5-167">Effective (date time or period)</span></span>
 - <span data-ttu-id="36be5-168">Code.Coding.Code</span><span class="sxs-lookup"><span data-stu-id="36be5-168">Code.Coding.Code</span></span>
 - <span data-ttu-id="36be5-169">ValueQuantity.Value</span><span class="sxs-lookup"><span data-stu-id="36be5-169">ValueQuantity.Value</span></span>

<span data-ttu-id="36be5-170">Además de los campos Salesforce, para una excelente experiencia del usuario, la aplicación Pacientes también lee los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="36be5-170">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="36be5-171">Code.Coding.Display</span><span class="sxs-lookup"><span data-stu-id="36be5-171">Code.Coding.Display</span></span>
 - <span data-ttu-id="36be5-172">ValueQuantity.Unit</span><span class="sxs-lookup"><span data-stu-id="36be5-172">ValueQuantity.Unit</span></span>

<span data-ttu-id="36be5-173">Si se utilizan observaciones de componentes, se aplica la misma lógica a cada observación del componente.</span><span class="sxs-lookup"><span data-stu-id="36be5-173">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="36be5-174">Una búsqueda de recursos usa el método GET y los parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="36be5-174">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="36be5-175">patient=\<patient id\></span><span class="sxs-lookup"><span data-stu-id="36be5-175">patient=\<patient id\></span></span>
 - <span data-ttu-id="36be5-176">sort:desc=\<field ex. date\></span><span class="sxs-lookup"><span data-stu-id="36be5-176">sort:desc=\<field ex. date\></span></span>

<span data-ttu-id="36be5-177">El objetivo es poder recuperar los signos vitales más recientes para un paciente, [VitalSigns.DSTU.saz] (observación?).</span><span class="sxs-lookup"><span data-stu-id="36be5-177">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

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

<span data-ttu-id="36be5-178">Consulte [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) otros detalles sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="36be5-178">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="36be5-179">Condición</span><span class="sxs-lookup"><span data-stu-id="36be5-179">Condition</span></span>

<span data-ttu-id="36be5-180">Estos son los campos requeridos mínimos, que son un subconjunto del perfil de [condición :](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)</span><span class="sxs-lookup"><span data-stu-id="36be5-180">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="36be5-181">Code.Coding[0]. Pantalla</span><span class="sxs-lookup"><span data-stu-id="36be5-181">Code.Coding[0].Display</span></span>

<span data-ttu-id="36be5-182">Además de los campos Salesforce, para una excelente experiencia del usuario, la aplicación Pacientes también puede leer los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="36be5-182">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="36be5-183">Fecha de grabación</span><span class="sxs-lookup"><span data-stu-id="36be5-183">Date Recorded</span></span>
 - <span data-ttu-id="36be5-184">Gravedad</span><span class="sxs-lookup"><span data-stu-id="36be5-184">Severity</span></span>

<span data-ttu-id="36be5-185">Una búsqueda de recursos usa el método GET y los parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="36be5-185">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="36be5-186">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="36be5-186">patient=\<patient id></span></span>
 - <span data-ttu-id="36be5-187">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="36be5-187">_count=\<max results></span></span>

<span data-ttu-id="36be5-188">Vea el siguiente ejemplo de esta llamada:</span><span class="sxs-lookup"><span data-stu-id="36be5-188">See the following example of this call:</span></span>

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

<span data-ttu-id="36be5-189">Consulte [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) otros detalles sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="36be5-189">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="36be5-190">Encounter</span><span class="sxs-lookup"><span data-stu-id="36be5-190">Encounter</span></span>

<span data-ttu-id="36be5-191">Estos son los campos requeridos mínimos, que son un subconjunto de los campos "debe tener" del perfil principal de EE. UU.:</span><span class="sxs-lookup"><span data-stu-id="36be5-191">These are the minimum required fields, which are a subset of the US Core Encounter profile "must have" fields:</span></span>

 - <span data-ttu-id="36be5-192">Estado</span><span class="sxs-lookup"><span data-stu-id="36be5-192">Status</span></span>
 - <span data-ttu-id="36be5-193">Escriba[0]. Coding[0]. Pantalla</span><span class="sxs-lookup"><span data-stu-id="36be5-193">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="36be5-194">Además, los siguientes campos del perfil del Core Encounter de EE. UU. también se admiten</span><span class="sxs-lookup"><span data-stu-id="36be5-194">In addition, the following fields from US Core Encounter profile's "must support" fields</span></span>

 - <span data-ttu-id="36be5-195">Period.Start</span><span class="sxs-lookup"><span data-stu-id="36be5-195">Period.Start</span></span>
 - <span data-ttu-id="36be5-196">Ubicación[0]. Location.Display</span><span class="sxs-lookup"><span data-stu-id="36be5-196">Location[0].Location.Display</span></span>

<span data-ttu-id="36be5-197">Una búsqueda de recursos usa el método GET y los parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="36be5-197">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="36be5-198">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="36be5-198">patient=\<patient id></span></span>
 - <span data-ttu-id="36be5-199">_sort:desc=\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="36be5-199">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="36be5-200">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="36be5-200">_count=\<max results></span></span>

<span data-ttu-id="36be5-201">El objetivo es poder recuperar la última ubicación conocida del paciente.</span><span class="sxs-lookup"><span data-stu-id="36be5-201">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="36be5-202">Cada encuentro hace referencia a un recurso de ubicación.</span><span class="sxs-lookup"><span data-stu-id="36be5-202">Each encounter references a location resource.</span></span> <span data-ttu-id="36be5-203">La referencia también incluirá el campo de visualización de la ubicación.</span><span class="sxs-lookup"><span data-stu-id="36be5-203">The reference shall also include the location's display field.</span></span> <span data-ttu-id="36be5-204">Vea el siguiente ejemplo de esta llamada.</span><span class="sxs-lookup"><span data-stu-id="36be5-204">See the following example of this call.</span></span>

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

<span data-ttu-id="36be5-205">Consulte [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) otros detalles sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="36be5-205">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="36be5-206">Desenladigo</span><span class="sxs-lookup"><span data-stu-id="36be5-206">AllergyIntolerance</span></span>

<span data-ttu-id="36be5-207">Estos son los campos requeridos mínimos, que son un subconjunto del perfil de VagoSerance:</span><span class="sxs-lookup"><span data-stu-id="36be5-207">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

 - <span data-ttu-id="36be5-208">Code.Text</span><span class="sxs-lookup"><span data-stu-id="36be5-208">Code.Text</span></span>
 - <span data-ttu-id="36be5-209">Code.Coding[0]. Pantalla</span><span class="sxs-lookup"><span data-stu-id="36be5-209">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="36be5-210">Estado</span><span class="sxs-lookup"><span data-stu-id="36be5-210">Status</span></span>

<span data-ttu-id="36be5-211">Además de los campos Salesforce, para una excelente experiencia del usuario, la aplicación Pacientes también lee los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="36be5-211">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="36be5-212">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="36be5-212">RecordedDate</span></span>
 - <span data-ttu-id="36be5-213">Note.Text</span><span class="sxs-lookup"><span data-stu-id="36be5-213">Note.Text</span></span>
 - <span data-ttu-id="36be5-214">Reacción[..]. Texto.texto.</span><span class="sxs-lookup"><span data-stu-id="36be5-214">Reaction[..].Substance.Text</span></span>
 - <span data-ttu-id="36be5-215">Reacción[..]. Editar[.]. Texto</span><span class="sxs-lookup"><span data-stu-id="36be5-215">Reaction[..].Manifestation[..].Text</span></span>
 - <span data-ttu-id="36be5-216">Text.Div</span><span class="sxs-lookup"><span data-stu-id="36be5-216">Text.Div</span></span>

<span data-ttu-id="36be5-217">Una búsqueda de recursos usa el método GET y los parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="36be5-217">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="36be5-218">Patient =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="36be5-218">Patient =  \<patient id></span></span>

<span data-ttu-id="36be5-219">Vea el siguiente ejemplo de esta llamada:</span><span class="sxs-lookup"><span data-stu-id="36be5-219">See the following example of this call:</span></span>

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

<span data-ttu-id="36be5-220">Consulte [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) otros detalles sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="36be5-220">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="36be5-221">Orden de medicamentos</span><span class="sxs-lookup"><span data-stu-id="36be5-221">Medication Order</span></span>

<span data-ttu-id="36be5-222">Estos son los campos requeridos mínimos, que son un subconjunto del perfil deOrder de medicamentos:</span><span class="sxs-lookup"><span data-stu-id="36be5-222">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

 - <span data-ttu-id="36be5-223">Fecha escrita</span><span class="sxs-lookup"><span data-stu-id="36be5-223">DateWritten</span></span>
 - <span data-ttu-id="36be5-224">Ara.Pantalla</span><span class="sxs-lookup"><span data-stu-id="36be5-224">Prescriber.Display</span></span>
 - <span data-ttu-id="36be5-225">Medicamentos.Pantalla (si referencia)</span><span class="sxs-lookup"><span data-stu-id="36be5-225">Medication.Display (if reference)</span></span>
 - <span data-ttu-id="36be5-226">Medicamentos.Texto (si concepto)</span><span class="sxs-lookup"><span data-stu-id="36be5-226">Medication.Text (if concept)</span></span>

<span data-ttu-id="36be5-227">Además de los campos Salesforce, para una excelente experiencia del usuario, la aplicación Pacientes también puede leer los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="36be5-227">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="36be5-228">DateEnded</span><span class="sxs-lookup"><span data-stu-id="36be5-228">DateEnded</span></span>
 - <span data-ttu-id="36be5-229">DosageInstruction.Text</span><span class="sxs-lookup"><span data-stu-id="36be5-229">DosageInstruction.Text</span></span>
 - <span data-ttu-id="36be5-230">Text.Div</span><span class="sxs-lookup"><span data-stu-id="36be5-230">Text.Div</span></span>

<span data-ttu-id="36be5-231">Una búsqueda de recursos usa el método GET y los parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="36be5-231">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="36be5-232">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="36be5-232">patient=\<patient id></span></span>
 - <span data-ttu-id="36be5-233">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="36be5-233">_count=\<max results></span></span>

<span data-ttu-id="36be5-234">Vea el siguiente ejemplo de esta llamada:</span><span class="sxs-lookup"><span data-stu-id="36be5-234">See the following example of this call:</span></span>

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

<span data-ttu-id="36be5-235">Consulte [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) otros detalles sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="36be5-235">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="36be5-236">Cobertura</span><span class="sxs-lookup"><span data-stu-id="36be5-236">Coverage</span></span>

<span data-ttu-id="36be5-237">Estos son los campos necesarios mínimos, no cubiertos por los perfiles US Core o Core:</span><span class="sxs-lookup"><span data-stu-id="36be5-237">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="36be5-238">Payor</span><span class="sxs-lookup"><span data-stu-id="36be5-238">Payor</span></span>

<span data-ttu-id="36be5-239">Una búsqueda de recursos usa el método GET y los parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="36be5-239">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="36be5-240">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="36be5-240">patient=\<patient id></span></span>

<span data-ttu-id="36be5-241">Vea el siguiente ejemplo de esta llamada:</span><span class="sxs-lookup"><span data-stu-id="36be5-241">See the following example of this call:</span></span>

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
    
<span data-ttu-id="36be5-242">Consulte [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) otros detalles sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="36be5-242">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="36be5-243">Ubicación</span><span class="sxs-lookup"><span data-stu-id="36be5-243">Location</span></span>

<span data-ttu-id="36be5-244">Este recurso solo se está utilizando como referencia en el recurso [De encuentro.](#encounter)</span><span class="sxs-lookup"><span data-stu-id="36be5-244">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="36be5-245">Consulte [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) otros detalles sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="36be5-245">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
