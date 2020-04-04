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
ms.openlocfilehash: f09f43af431b3f0cc6d9f984171206f2549a550a
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2020
ms.locfileid: "43136960"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="09873-103">Especificación de la interfaz DSTU2</span><span class="sxs-lookup"><span data-stu-id="09873-103">DSTU2 interface specification</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="09873-104">Para configurar o volver a configurar un servidor de FHIR para que funcione con la aplicación para pacientes de Microsoft Teams, es necesario comprender a qué datos necesita acceder la aplicación.</span><span class="sxs-lookup"><span data-stu-id="09873-104">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="09873-105">El servidor de FHIR debe admitir solicitudes POST con paquetes para los siguientes recursos:</span><span class="sxs-lookup"><span data-stu-id="09873-105">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="09873-106">Propio</span><span class="sxs-lookup"><span data-stu-id="09873-106">Patient</span></span>](#patient)
- [<span data-ttu-id="09873-107">Observación</span><span class="sxs-lookup"><span data-stu-id="09873-107">Observation</span></span>](#observation)
- [<span data-ttu-id="09873-108">Condición</span><span class="sxs-lookup"><span data-stu-id="09873-108">Condition</span></span>](#condition)
- [<span data-ttu-id="09873-109">Detect</span><span class="sxs-lookup"><span data-stu-id="09873-109">Encounter</span></span>](#encounter)
- [<span data-ttu-id="09873-110">Intolerancia de alergia</span><span class="sxs-lookup"><span data-stu-id="09873-110">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="09873-111">Beneficios</span><span class="sxs-lookup"><span data-stu-id="09873-111">Coverage</span></span>](#coverage)
- [<span data-ttu-id="09873-112">Orden de los medicamentos</span><span class="sxs-lookup"><span data-stu-id="09873-112">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="09873-113">Ubicación</span><span class="sxs-lookup"><span data-stu-id="09873-113">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="09873-114">El recurso paciente es el único recurso obligatorio (sin que la aplicación se cargue en absoluto).</span><span class="sxs-lookup"><span data-stu-id="09873-114">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="09873-115">Sin embargo, se recomienda que el socio implemente la compatibilidad de todos los recursos mencionados anteriormente según las especificaciones proporcionadas a continuación para obtener la mejor experiencia para el usuario final con la aplicación de pacientes de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="09873-115">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="09873-116">Las consultas de la aplicación de pacientes de Microsoft Teams para más de un recurso publican un paquete (lote) de solicitudes a la dirección URL del servidor FHIR.</span><span class="sxs-lookup"><span data-stu-id="09873-116">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="09873-117">El servidor procesa cada solicitud y devuelve un paquete de los recursos coincidentes con cada solicitud.</span><span class="sxs-lookup"><span data-stu-id="09873-117">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="09873-118">Para obtener más información y ejemplos, [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction)consulte.</span><span class="sxs-lookup"><span data-stu-id="09873-118">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="09873-119">Todos los siguientes recursos de FHIR deben ser accesibles mediante la referencia directa de recursos.</span><span class="sxs-lookup"><span data-stu-id="09873-119">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="09873-120">Conjunto de campos obligatorios mínimos de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="09873-120">Conformance minimum required field set</span></span>

 <span data-ttu-id="09873-121">El servidor de FHIR debe implementar la declaración de conformidad para que nosotros tenga un resumen del objetivo de sus capacidades.</span><span class="sxs-lookup"><span data-stu-id="09873-121">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="09873-122">Esperamos los siguientes parámetros en un DSTU2 FHIR Server:</span><span class="sxs-lookup"><span data-stu-id="09873-122">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

1. <span data-ttu-id="09873-123">DESCANSO</span><span class="sxs-lookup"><span data-stu-id="09873-123">REST</span></span>
   1. <span data-ttu-id="09873-124">Modo</span><span class="sxs-lookup"><span data-stu-id="09873-124">Mode</span></span>
   2. <span data-ttu-id="09873-125">MOV</span><span class="sxs-lookup"><span data-stu-id="09873-125">Interaction</span></span>
   3. <span data-ttu-id="09873-126">Recurso: tipo</span><span class="sxs-lookup"><span data-stu-id="09873-126">Resource: Type</span></span>
   4. <span data-ttu-id="09873-127">Seguridad: [extensión para URI de OAuth](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="09873-127">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="09873-128">FhirVersion (nuestro código requiere esto para comprender a qué versión debemos dinamizar, ya que admitimos varias versiones).</span><span class="sxs-lookup"><span data-stu-id="09873-128">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="09873-129">Consulte [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="09873-129">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="09873-130">Propio</span><span class="sxs-lookup"><span data-stu-id="09873-130">Patient</span></span>

<span data-ttu-id="09873-131">Estos son los campos mínimos obligatorios, que son un subconjunto de los campos de [Perfil del paciente de Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) :</span><span class="sxs-lookup"><span data-stu-id="09873-131">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

1. <span data-ttu-id="09873-132">Nombre. familia</span><span class="sxs-lookup"><span data-stu-id="09873-132">Name.Family</span></span>
2. <span data-ttu-id="09873-133">Nombre. dado</span><span class="sxs-lookup"><span data-stu-id="09873-133">Name.Given</span></span>
3. <span data-ttu-id="09873-134">Hombres</span><span class="sxs-lookup"><span data-stu-id="09873-134">Gender</span></span>
4. <span data-ttu-id="09873-135">FechaNacimiento</span><span class="sxs-lookup"><span data-stu-id="09873-135">BirthDate</span></span>
5. <span data-ttu-id="09873-136">MRN (identificador)</span><span class="sxs-lookup"><span data-stu-id="09873-136">MRN (Identifier)</span></span>

<span data-ttu-id="09873-137">Además de los campos Argonaut, para una experiencia de usuario excelente, la aplicación para pacientes también lee los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="09873-137">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="09873-138">Nombre. Use</span><span class="sxs-lookup"><span data-stu-id="09873-138">Name.Use</span></span>
2. <span data-ttu-id="09873-139">Nombre. Prefix</span><span class="sxs-lookup"><span data-stu-id="09873-139">Name.Prefix</span></span>
3. <span data-ttu-id="09873-140">CareProvider (esta referencia en el recurso paciente debe incluir los campos de visualización que se muestran en el ejemplo siguiente).</span><span class="sxs-lookup"><span data-stu-id="09873-140">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

* * *

    <span data-ttu-id="09873-141">Solicitud: Obtén <fhir-Server>/patient/<ID de paciente></span><span class="sxs-lookup"><span data-stu-id="09873-141">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="09873-142">Respuesta: {"resourceType": "patient", "ID": "<ID de paciente>",.</span><span class="sxs-lookup"><span data-stu-id="09873-142">Response: { "resourceType": "Patient", "id": "<patient-id>", .</span></span>
      <span data-ttu-id="09873-143">.</span><span class="sxs-lookup"><span data-stu-id="09873-143">.</span></span>
      <span data-ttu-id="09873-144">.</span><span class="sxs-lookup"><span data-stu-id="09873-144">.</span></span>
      <span data-ttu-id="09873-145">"nombre": [{"use": "funcionario", "prefijo": ["Mr"], "familia": ["Chau"], "dado": ["Hugh"]}], "identificador": [{"use": "oficial", "tipo": {"código": [{"System": "https://hl7.org/fhir/v2/0203", "": ",". ",", ",", ".", ".", ",", ",": [{"careProvider": "Juana Pérez"}],} 1957-06-05 1234567</span><span class="sxs-lookup"><span data-stu-id="09873-145">"name": [ { "use": "official", "prefix": [ "Mr" ], "family": [ "Chau" ], "given": [ "Hugh" ] } ], "identifier": [ { "use": "official", "type": { "coding": [ { "system": "https://hl7.org/fhir/v2/0203", "code": "MR" } ] }, "value": "1234567" } ], "gender": "male", "birthDate": "1957-06-05", "careProvider": [{ "display": "Jane Doe" }], }</span></span>

* * *

<span data-ttu-id="09873-146">Una búsqueda de recursos usa el método POST en/patient/_search y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="09873-146">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="09873-147">identificar</span><span class="sxs-lookup"><span data-stu-id="09873-147">id</span></span>
2. <span data-ttu-id="09873-148">Family: contiene = (busca todos los pacientes cuyo nombre contenga el valor).</span><span class="sxs-lookup"><span data-stu-id="09873-148">family:contains=(searches for all patients whose family name contains the value.)</span></span>
3. <span data-ttu-id="09873-149">proporcionado =\<substring></span><span class="sxs-lookup"><span data-stu-id="09873-149">given=\<substring></span></span>
4. <span data-ttu-id="09873-150">name =\<substring></span><span class="sxs-lookup"><span data-stu-id="09873-150">name=\<substring></span></span>
5. <span data-ttu-id="09873-151">FechaNacimiento = (coincidencia exacta)</span><span class="sxs-lookup"><span data-stu-id="09873-151">birthdate=(exact match)</span></span>
6. <span data-ttu-id="09873-152">\_contar (número máximo de resultados que se deben devolver)</span><span class="sxs-lookup"><span data-stu-id="09873-152">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="09873-153">La respuesta debe contener el recuento total de registros devueltos como resultado de la búsqueda \_, y el PatientsApp usará Count para limitar el número de registros devueltos.</span><span class="sxs-lookup"><span data-stu-id="09873-153">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="09873-154">Identifier =\<MRN></span><span class="sxs-lookup"><span data-stu-id="09873-154">identifier=\<mrn></span></span>

<span data-ttu-id="09873-155">El objetivo es poder buscar y filtrar a un paciente por lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="09873-155">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="09873-156">ID: es el identificador de recurso que tiene cada recurso en FHIR.</span><span class="sxs-lookup"><span data-stu-id="09873-156">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="09873-157">MRN: este es el identificador real del paciente que sabría el personal clínico.</span><span class="sxs-lookup"><span data-stu-id="09873-157">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="09873-158">Entendemos que este MRN se basa en el tipo de identificador dentro del recurso Identifier en FHIR</span><span class="sxs-lookup"><span data-stu-id="09873-158">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="09873-159">Nombre</span><span class="sxs-lookup"><span data-stu-id="09873-159">Name</span></span>
- <span data-ttu-id="09873-160">FechaNacimiento</span><span class="sxs-lookup"><span data-stu-id="09873-160">Birthdate</span></span>

<span data-ttu-id="09873-161">Consulta el siguiente ejemplo de esta llamada.</span><span class="sxs-lookup"><span data-stu-id="09873-161">See the following example  of this call.</span></span>

* * *

    <span data-ttu-id="09873-162">Solicitud: publique <fhir-Server>/patient/_search cuerpo de la solicitud: dado = Hugh&Family = Chau</span><span class="sxs-lookup"><span data-stu-id="09873-162">Request: POST <fhir-server>/Patient/_search Request Body: given=hugh&family=chau</span></span>
    
    <span data-ttu-id="09873-163">Respuesta: {"resourceType": "bundle", "ID": "<paquete-ID>",.</span><span class="sxs-lookup"><span data-stu-id="09873-163">Response: { "resourceType": "Bundle", "id": "<bundle-id>", .</span></span>
      <span data-ttu-id="09873-164">.</span><span class="sxs-lookup"><span data-stu-id="09873-164">.</span></span>
      <span data-ttu-id="09873-165">.</span><span class="sxs-lookup"><span data-stu-id="09873-165">.</span></span>
      <span data-ttu-id="09873-166">"entrada": [{"recurso": {"resourceType": "patient", "ID": "<> de identificación de pacientes", "nombre": [{"texto": "Hugh Chau", "familia": ["Chau"], "dado": ["Hugh"]}], "género": "," hombre "," FechaNacimiento ":" coincidencias "} 1957-06-05</span><span class="sxs-lookup"><span data-stu-id="09873-166">"entry": [ { "resource": { "resourceType": "Patient", "id": "<patient-id>", "name": [ { "text": "Hugh Chau", "family": [ "Chau" ], "given": [ "Hugh" ] } ], "gender": "male", "birthDate": "1957-06-05" }, "search": { "mode": "match" } } ] }</span></span>

* * *

<span data-ttu-id="09873-167">Consulte [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="09873-167">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="09873-168">Observación</span><span class="sxs-lookup"><span data-stu-id="09873-168">Observation</span></span>

<span data-ttu-id="09873-169">Estos son los campos mínimos obligatorios, que son un subconjunto del perfil de constantes vitales de Argonaut:</span><span class="sxs-lookup"><span data-stu-id="09873-169">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 1. <span data-ttu-id="09873-170">Vigencia (fecha o hora)</span><span class="sxs-lookup"><span data-stu-id="09873-170">Effective (date time or period)</span></span>
 2. <span data-ttu-id="09873-171">Code. Coding. Code</span><span class="sxs-lookup"><span data-stu-id="09873-171">Code.Coding.Code</span></span>
 3. <span data-ttu-id="09873-172">ValueQuantity. Value</span><span class="sxs-lookup"><span data-stu-id="09873-172">ValueQuantity.Value</span></span>

<span data-ttu-id="09873-173">Además de los campos Argonaut, para una experiencia de usuario excelente, la aplicación para pacientes también lee los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="09873-173">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 1. <span data-ttu-id="09873-174">Code. Coding. display</span><span class="sxs-lookup"><span data-stu-id="09873-174">Code.Coding.Display</span></span>
 2. <span data-ttu-id="09873-175">Unidad ValueQuantity.</span><span class="sxs-lookup"><span data-stu-id="09873-175">ValueQuantity.Unit</span></span>

<span data-ttu-id="09873-176">Si se usan observaciones de componentes, se aplica la misma lógica para cada observación de componentes.</span><span class="sxs-lookup"><span data-stu-id="09873-176">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="09873-177">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="09873-177">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="09873-178">paciente =\<ID de paciente\></span><span class="sxs-lookup"><span data-stu-id="09873-178">patient=\<patient id\></span></span>
2. <span data-ttu-id="09873-179">ordenar: DESC =\<campo ex.</span><span class="sxs-lookup"><span data-stu-id="09873-179">sort:desc=\<field ex.</span></span> <span data-ttu-id="09873-180">Posteriormente\></span><span class="sxs-lookup"><span data-stu-id="09873-180">date\></span></span>

<span data-ttu-id="09873-181">El objetivo es poder recuperar los últimos signos vitales para un paciente, [VitalSigns. DSTU. Saz] (observación?).</span><span class="sxs-lookup"><span data-stu-id="09873-181">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

* * *

    <span data-ttu-id="09873-182">Solicitud: obtener <fhir-Server>/Observation? patient =<paciente-ID>&_sort:d ESC = Date&Category = invienes</span><span class="sxs-lookup"><span data-stu-id="09873-182">Request: GET <fhir-server>/Observation?patient=<patient-id>&_sort:desc=date&category=vital-signs</span></span>
    
    <span data-ttu-id="09873-183">Respuesta: {"resourceType": "bundle", "ID": "<paquete-ID>", "escribe": "searchset", "total": 20, "Entry": [{"recurso": {"nombre de recurso": "," nombre "," nombre ":", "", "," <= ">."} ","} "," "código": {"codificación": [{"System": "http://loinc.org", "Code": "39156-5", "display": "BMI"}],}, "effectiveDateTime": "2009-12-01", "valueQuantity": {"valor": 34,4, "unidad": "kg/m2", "sistema": "http://unitsofmeasure.org", "código": "kg/m2"}},},.</span><span class="sxs-lookup"><span data-stu-id="09873-183">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": { "coding": [ { code": "vital-signs" } ], }, "code": { "coding": [ { "system": "http://loinc.org", "code": "39156-5", "display": "bmi" } ], }, "effectiveDateTime": "2009-12-01", "valueQuantity": { "value": 34.4, "unit": "kg/m2", "system": "http://unitsofmeasure.org", "code": "kg/m2" } }, }, .</span></span>
        <span data-ttu-id="09873-184">.</span><span class="sxs-lookup"><span data-stu-id="09873-184">.</span></span>
        <span data-ttu-id="09873-185">.</span><span class="sxs-lookup"><span data-stu-id="09873-185">.</span></span>
      <span data-ttu-id="09873-186">] }</span><span class="sxs-lookup"><span data-stu-id="09873-186">] }</span></span>

* * *

<span data-ttu-id="09873-187">Consulte [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="09873-187">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="09873-188">Condición</span><span class="sxs-lookup"><span data-stu-id="09873-188">Condition</span></span>

<span data-ttu-id="09873-189">Estos son los campos mínimos obligatorios, que son un subconjunto del [Perfil de condición Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span><span class="sxs-lookup"><span data-stu-id="09873-189">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="09873-190">Code. Coding [0]. Aparecen</span><span class="sxs-lookup"><span data-stu-id="09873-190">Code.Coding[0].Display</span></span>

<span data-ttu-id="09873-191">Además de los campos Argonaut, para una experiencia de usuario excelente, la aplicación de pacientes también puede leer los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="09873-191">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="09873-192">Fecha de grabación</span><span class="sxs-lookup"><span data-stu-id="09873-192">Date Recorded</span></span>
2. <span data-ttu-id="09873-193">Gravedad</span><span class="sxs-lookup"><span data-stu-id="09873-193">Severity</span></span>

<span data-ttu-id="09873-194">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="09873-194">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="09873-195">paciente =\<ID de paciente></span><span class="sxs-lookup"><span data-stu-id="09873-195">patient=\<patient id></span></span>
2. <span data-ttu-id="09873-196">_count =\<resultados máximos></span><span class="sxs-lookup"><span data-stu-id="09873-196">_count=\<max results></span></span>

<span data-ttu-id="09873-197">Consulte el siguiente ejemplo de esta llamada:</span><span class="sxs-lookup"><span data-stu-id="09873-197">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="09873-198">Solicitud: obtener <fhir-Server>/Condition? patient =<ID de paciente>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="09873-198">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="09873-199">Respuesta: {"resourceType": "bundle", "ID": "<paquete-ID>", "type": "searchset", "total": 1, "Entry": [{"recurso": {"resourceType": "Condition", "ID": "<Resource-ID>", "Code": {"codificación": [{"System": "http://snomed.info/sct", "Code": "386033004", "display": "neuropathy (Nerve Damage)"}]}, "dateRecorded": "2018-09-17", "gravedad": {"codificación": [{"System": "http://snomed.info/sct", "code": "24484000", "display": "grave"}]}},}]}</span><span class="sxs-lookup"><span data-stu-id="09873-199">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Condition",         "id": "<resource-id>",         "code": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "386033004",               "display": "Neuropathy (nerve damage)"             }           ]         },         "dateRecorded": "2018-09-17",         "severity": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "24484000",               "display": "Severe"             }           ]         }       },     }   ] }</span></span>

* * *

<span data-ttu-id="09873-200">Consulte [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="09873-200">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="09873-201">Detect</span><span class="sxs-lookup"><span data-stu-id="09873-201">Encounter</span></span>

<span data-ttu-id="09873-202">Estos son los campos mínimos obligatorios, que son un subconjunto del núcleo de Estados Unidos y el perfil "debe tener" campos:</span><span class="sxs-lookup"><span data-stu-id="09873-202">These are the minimum required fields, which are a subset of the US Core Encounter profile "must have" fields:</span></span>

1. <span data-ttu-id="09873-203">Statu</span><span class="sxs-lookup"><span data-stu-id="09873-203">Status</span></span>
2. <span data-ttu-id="09873-204">Escriba [0]. Codificación [0]. Aparecen</span><span class="sxs-lookup"><span data-stu-id="09873-204">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="09873-205">Además, los siguientes campos de la parte central de Estados Unidos tienen los campos "debe ser compatible" del perfil.</span><span class="sxs-lookup"><span data-stu-id="09873-205">In addition, the following fields from US Core Encounter profile's "must support" fields</span></span>

1. <span data-ttu-id="09873-206">Start period</span><span class="sxs-lookup"><span data-stu-id="09873-206">Period.Start</span></span>
2. <span data-ttu-id="09873-207">Ubicación [0]. Location. display</span><span class="sxs-lookup"><span data-stu-id="09873-207">Location[0].Location.Display</span></span>

<span data-ttu-id="09873-208">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="09873-208">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="09873-209">paciente =\<ID de paciente></span><span class="sxs-lookup"><span data-stu-id="09873-209">patient=\<patient id></span></span>
2. <span data-ttu-id="09873-210">_sort: DESC =\<campo ex.</span><span class="sxs-lookup"><span data-stu-id="09873-210">_sort:desc=\<field ex.</span></span> <span data-ttu-id="09873-211">> de fecha</span><span class="sxs-lookup"><span data-stu-id="09873-211">date></span></span>
3. <span data-ttu-id="09873-212">_count =\<resultados máximos></span><span class="sxs-lookup"><span data-stu-id="09873-212">_count=\<max results></span></span>

<span data-ttu-id="09873-213">El objetivo es poder recuperar el último lugar conocido del paciente.</span><span class="sxs-lookup"><span data-stu-id="09873-213">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="09873-214">Cada uno de ellos hace referencia a un recurso de ubicación.</span><span class="sxs-lookup"><span data-stu-id="09873-214">Each encounter references a location resource.</span></span> <span data-ttu-id="09873-215">La referencia también incluirá el campo de visualización de la ubicación.</span><span class="sxs-lookup"><span data-stu-id="09873-215">The reference shall also include the location's display field.</span></span> <span data-ttu-id="09873-216">Consulta el siguiente ejemplo de esta llamada.</span><span class="sxs-lookup"><span data-stu-id="09873-216">See the following example of this call.</span></span>
* * *

    <span data-ttu-id="09873-217">Solicitud: obtener <fhir-Server>/Encounter? patient =<ID de paciente>&_sort:d ESC = Date&_count = 1</span><span class="sxs-lookup"><span data-stu-id="09873-217">Request: GET <fhir-server>/Encounter?patient=<patient-id>&_sort:desc=date&_count=1</span></span>
    
    <span data-ttu-id="09873-218">Respuesta: {"resourceType": "paquete", "tipo": "searchset", "total": 1, "entrada": [{"recurso": {"nombre del recurso": "<nombre", "ID.": ","> "," nombre de recurso: "<id>"} ","... "} estado": "ha llegado", "tipo": [{"código": [{"display": "appointment}", "... a. de paciente de pacientes/<>"}, "período": {"Start": "09/17/2018 1:00:00 PM"}, "ubicación": [{"ubicación": {"display": "Clinic-ENT"},}]}}]}</span><span class="sxs-lookup"><span data-stu-id="09873-218">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Encounter",         "id": "<resource-id>",         "identifier": [{ "use": "official", "value": "<id>" }],         "status": "arrived",         "type": [           {             "coding": [{ "display": "Appointment" }],           }         ],         "patient": { "reference": "Patient/<patient-id>" },         "period": { "start": "09/17/2018 1:00:00 PM" },         "location": [           {             "location": { "display": "Clinic - ENT" },           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="09873-219">Consulte [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="09873-219">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="09873-220">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="09873-220">AllergyIntolerance</span></span>

<span data-ttu-id="09873-221">Estos son los campos mínimos obligatorios, que son un subconjunto del perfil de AllergyIntolerance de Argonaut:</span><span class="sxs-lookup"><span data-stu-id="09873-221">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

1. <span data-ttu-id="09873-222">Code. Text</span><span class="sxs-lookup"><span data-stu-id="09873-222">Code.Text</span></span>
2. <span data-ttu-id="09873-223">Code. Coding [0]. Aparecen</span><span class="sxs-lookup"><span data-stu-id="09873-223">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="09873-224">Statu</span><span class="sxs-lookup"><span data-stu-id="09873-224">Status</span></span>

<span data-ttu-id="09873-225">Además de los campos Argonaut, para una experiencia de usuario excelente, la aplicación para pacientes también lee los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="09873-225">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="09873-226">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="09873-226">RecordedDate</span></span>
2. <span data-ttu-id="09873-227">Nota. Text</span><span class="sxs-lookup"><span data-stu-id="09873-227">Note.Text</span></span>
3. <span data-ttu-id="09873-228">Reacción [...]. Sustancia. texto</span><span class="sxs-lookup"><span data-stu-id="09873-228">Reaction[..].Substance.Text</span></span>
4. <span data-ttu-id="09873-229">Reacción [...]. Manifesting [..]. Facturas</span><span class="sxs-lookup"><span data-stu-id="09873-229">Reaction[..].Manifestation[..].Text</span></span>
5. <span data-ttu-id="09873-230">Text. div</span><span class="sxs-lookup"><span data-stu-id="09873-230">Text.Div</span></span>

<span data-ttu-id="09873-231">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="09873-231">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="09873-232">Paciente = \<ID de paciente></span><span class="sxs-lookup"><span data-stu-id="09873-232">Patient =  \<patient id></span></span>

<span data-ttu-id="09873-233">Consulte el siguiente ejemplo de esta llamada:</span><span class="sxs-lookup"><span data-stu-id="09873-233">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="09873-234">Solicitud: obtener <fhir-Server>/AllergyIntolerance? patient =<ID de paciente></span><span class="sxs-lookup"><span data-stu-id="09873-234">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="09873-235">Respuesta: {"resourceType": "bundle", "ID": "<paquete-ID>", "type": "searchset", "total": 1, "Entry": [{"recurso": {"resourceType": "AllergyIntolerance", "ID": "<Resource-ID>", "recordedDate": "2018-09-17T07:00:00.000 Z", "sustancia": {"texto": "cashew NUTS"}, "estado": "confirmado", "reacción": [{"sustancia": {"texto": "cashew tuerca allergenic extraer producto inyectable"}, "manifiesto": [{"texto": "respuesta Anaphylactic"}]}]}}</span><span class="sxs-lookup"><span data-stu-id="09873-235">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "recordedDate": "2018-09-17T07:00:00.000Z",         "substance": {           "text": "Cashew nuts"         },         "status": "confirmed",         "reaction": [           {             "substance": {               "text": "cashew nut allergenic extract Injectable Product"             },             "manifestation": [               {                 "text": "Anaphylactic reaction"               }             ]           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="09873-236">Consulte [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="09873-236">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="09873-237">Orden de los medicamentos</span><span class="sxs-lookup"><span data-stu-id="09873-237">Medication Order</span></span>

<span data-ttu-id="09873-238">Estos son los campos mínimos obligatorios, que son un subconjunto del perfil de MedicationOrder de Argonaut:</span><span class="sxs-lookup"><span data-stu-id="09873-238">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

1. <span data-ttu-id="09873-239">DateWritten</span><span class="sxs-lookup"><span data-stu-id="09873-239">DateWritten</span></span>
2. <span data-ttu-id="09873-240">Prescribir. Mostrar</span><span class="sxs-lookup"><span data-stu-id="09873-240">Prescriber.Display</span></span>
3. <span data-ttu-id="09873-241">Medicación. display (si Ref)</span><span class="sxs-lookup"><span data-stu-id="09873-241">Medication.Display (if reference)</span></span>
4. <span data-ttu-id="09873-242">Medicación. Text (si concepto)</span><span class="sxs-lookup"><span data-stu-id="09873-242">Medication.Text (if concept)</span></span>

<span data-ttu-id="09873-243">Además de los campos Argonaut, para una experiencia de usuario excelente, la aplicación de pacientes también puede leer los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="09873-243">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="09873-244">DateEnded</span><span class="sxs-lookup"><span data-stu-id="09873-244">DateEnded</span></span>
2. <span data-ttu-id="09873-245">DosageInstruction. Text</span><span class="sxs-lookup"><span data-stu-id="09873-245">DosageInstruction.Text</span></span>
3. <span data-ttu-id="09873-246">Text. div</span><span class="sxs-lookup"><span data-stu-id="09873-246">Text.Div</span></span>

<span data-ttu-id="09873-247">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="09873-247">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="09873-248">paciente =\<ID de paciente></span><span class="sxs-lookup"><span data-stu-id="09873-248">patient=\<patient id></span></span>
2. <span data-ttu-id="09873-249">_count =\<resultados máximos></span><span class="sxs-lookup"><span data-stu-id="09873-249">_count=\<max results></span></span>

<span data-ttu-id="09873-250">Consulte el siguiente ejemplo de esta llamada:</span><span class="sxs-lookup"><span data-stu-id="09873-250">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="09873-251">Solicitud: obtener <fhir-Server>/MedicationOrder? patient =<ID de paciente>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="09873-251">Request: GET <fhir-server>/MedicationOrder?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="09873-252">Respuesta: {"resourceType": "bundle", "ID": "<paquete-ID>", "tipo": "searchset", "total": "Entry": [{"Resource": {"resourceType": "MedicationOrder", "ID": "<Resource-ID>", "dateWritten": "2018-09-17", "premedicationCodeableConcept": {"Text": "nombre de la lisinopril de 20 MG de tableta oral"}, "prescribe": {"display": "?}]}, o bien</span><span class="sxs-lookup"><span data-stu-id="09873-252">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "MedicationOrder",         "id": "<resource-id>",         "dateWritten": "2018-09-17",         "medicationCodeableConcept": {           "text": "Lisinopril 20 MG Oral Tablet"         },         "prescriber": {           "display": "Jane Doe"         },         "dosageInstruction": [           {             "text": "1 daily"           }         ]       }     }   ] }</span></span>

* * *  

<span data-ttu-id="09873-253">Consulte [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="09873-253">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="09873-254">Beneficios</span><span class="sxs-lookup"><span data-stu-id="09873-254">Coverage</span></span>

<span data-ttu-id="09873-255">Estos son los campos mínimos obligatorios, no incluidos en los perfiles de los Estados Unidos Core o Argonaut:</span><span class="sxs-lookup"><span data-stu-id="09873-255">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="09873-256">Payor</span><span class="sxs-lookup"><span data-stu-id="09873-256">Payor</span></span>

<span data-ttu-id="09873-257">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="09873-257">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="09873-258">paciente =\<ID de paciente></span><span class="sxs-lookup"><span data-stu-id="09873-258">patient=\<patient id></span></span>

<span data-ttu-id="09873-259">Consulte el siguiente ejemplo de esta llamada:</span><span class="sxs-lookup"><span data-stu-id="09873-259">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="09873-260">Solicitud: obtener <fhir-Server>/Coverage? patient =<ID de paciente></span><span class="sxs-lookup"><span data-stu-id="09873-260">Request: GET <fhir-server>/Coverage?patient=<patient-id></span></span>
    
    <span data-ttu-id="09873-261">Respuesta: {"resourceType": "bundle", "type": "searchset", "total": 1, "entrada": [{"recurso": {"resourceType": "Coverage", "ID": "<Resource-ID>", "Plan": "sin seguro principal", "suscriptor": {"referencia": "patient/<ID de paciente>"}}}]}</span><span class="sxs-lookup"><span data-stu-id="09873-261">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Coverage",         "id": "<resource-id>",         "plan": "No Primary Insurance",         "subscriber": { "reference": "Patient/<patient-id>" }       }     }   ] }</span></span>

* * *

<span data-ttu-id="09873-262">Consulte [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="09873-262">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="09873-263">Ubicación</span><span class="sxs-lookup"><span data-stu-id="09873-263">Location</span></span>

<span data-ttu-id="09873-264">Este recurso solo se usa como referencia en el recurso de [problemas](#encounter) .</span><span class="sxs-lookup"><span data-stu-id="09873-264">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="09873-265">Consulte [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="09873-265">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
