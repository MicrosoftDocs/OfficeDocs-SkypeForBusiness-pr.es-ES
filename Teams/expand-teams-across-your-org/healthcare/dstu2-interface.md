---
title: " Interfaz de DSTU2 de integración de aplicación de los pacientes y EHR"
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Integración de EHR de aplicación de los pacientes de los equipos de Microsoft
ms.openlocfilehash: 85fd90fb338f8b19762dc9433fa1dc281f3cedff
ms.sourcegitcommit: cf2cb5b7e03385b33e34a5ff89719adb882525b1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2019
ms.locfileid: "33643137"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="33366-103">Especificación de la interfaz DSTU2</span><span class="sxs-lookup"><span data-stu-id="33366-103">DSTU2 interface specification</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="33366-104">Configurar o volver a configurar un servidor FHIR para trabajar con la aplicación de los pacientes de los equipos de Microsoft requiere la descripción de los datos que la aplicación necesita obtener acceso a.</span><span class="sxs-lookup"><span data-stu-id="33366-104">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="33366-105">El servidor FHIR debe admitir solicitudes POST con paquetes para los siguientes recursos:</span><span class="sxs-lookup"><span data-stu-id="33366-105">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="33366-106">Paciente</span><span class="sxs-lookup"><span data-stu-id="33366-106">Patient</span></span>](#patient)
- [<span data-ttu-id="33366-107">Observación</span><span class="sxs-lookup"><span data-stu-id="33366-107">Observation</span></span>](#observation)
- [<span data-ttu-id="33366-108">Condición</span><span class="sxs-lookup"><span data-stu-id="33366-108">Condition</span></span>](#condition)
- [<span data-ttu-id="33366-109">Encontrar</span><span class="sxs-lookup"><span data-stu-id="33366-109">Encounter</span></span>](#encounter)
- [<span data-ttu-id="33366-110">Intolerancia alergias</span><span class="sxs-lookup"><span data-stu-id="33366-110">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="33366-111">Cobertura</span><span class="sxs-lookup"><span data-stu-id="33366-111">Coverage</span></span>](#coverage)
- [<span data-ttu-id="33366-112">Orden de medicación</span><span class="sxs-lookup"><span data-stu-id="33366-112">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="33366-113">Ubicación</span><span class="sxs-lookup"><span data-stu-id="33366-113">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="33366-114">El paciente recurso es el recurso sólo es obligatorio (sin que la aplicación no se cargará en absoluto.</span><span class="sxs-lookup"><span data-stu-id="33366-114">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="33366-115">Sin embargo, se recomienda que el socio implementar la compatibilidad de todos los recursos mencionados anteriormente por especificaciones proporcionados por debajo de la mejor experiencia del usuario final con la aplicación de los pacientes de los equipos de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="33366-115">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="33366-116">Las consultas de la aplicación de los pacientes de los equipos de Microsoft para más de un recurso registrar una agrupación (lote) de solicitudes a la dirección URL del servidor FHIR.</span><span class="sxs-lookup"><span data-stu-id="33366-116">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="33366-117">El servidor procesa cada solicitud y devuelve una agrupación de los recursos que coinciden con cada solicitud.</span><span class="sxs-lookup"><span data-stu-id="33366-117">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="33366-118">Para obtener más información y ejemplos, consulte [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span><span class="sxs-lookup"><span data-stu-id="33366-118">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="33366-119">Los siguientes recursos FHIR deben ser accesibles por referencia de recurso directo.</span><span class="sxs-lookup"><span data-stu-id="33366-119">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="33366-120">Establece campo de conformidad mínimo requerido</span><span class="sxs-lookup"><span data-stu-id="33366-120">Conformance minimum required field set</span></span>

 <span data-ttu-id="33366-121">El servidor de FHIR debe implementar la declaración de conformidad para que podamos tienen un resumen de sus capacidades de objetivo.</span><span class="sxs-lookup"><span data-stu-id="33366-121">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="33366-122">Esperamos que los siguientes parámetros en un servidor de FHIR DSTU2:</span><span class="sxs-lookup"><span data-stu-id="33366-122">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

1. <span data-ttu-id="33366-123">reposo</span><span class="sxs-lookup"><span data-stu-id="33366-123">REST</span></span>
   1. <span data-ttu-id="33366-124">Modo</span><span class="sxs-lookup"><span data-stu-id="33366-124">Mode</span></span>
   2. <span data-ttu-id="33366-125">Interacción</span><span class="sxs-lookup"><span data-stu-id="33366-125">Interaction</span></span>
   3. <span data-ttu-id="33366-126">Recurso: tipo</span><span class="sxs-lookup"><span data-stu-id="33366-126">Resource: Type</span></span>
   4. <span data-ttu-id="33366-127">Seguridad: [extensión para los identificadores URI de OAuth](http://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="33366-127">Security: [Extension for OAuth URIs](http://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="33366-128">FhirVersion (nuestro código requiere esto para comprender qué versión se deberíamos dinámicas a tal y como se admiten varias versiones).</span><span class="sxs-lookup"><span data-stu-id="33366-128">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="33366-129">Vea [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) establecer otros detalles en este campo.</span><span class="sxs-lookup"><span data-stu-id="33366-129">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="33366-130">Paciente</span><span class="sxs-lookup"><span data-stu-id="33366-130">Patient</span></span>

<span data-ttu-id="33366-131">Estos son los mínimos campos obligatorios, que son un subconjunto de los campos de [perfil de pacientes Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) :</span><span class="sxs-lookup"><span data-stu-id="33366-131">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

1. <span data-ttu-id="33366-132">Name.Family</span><span class="sxs-lookup"><span data-stu-id="33366-132">Name.Family</span></span>
2. <span data-ttu-id="33366-133">Name.Given</span><span class="sxs-lookup"><span data-stu-id="33366-133">Name.Given</span></span>
3. <span data-ttu-id="33366-134">Género</span><span class="sxs-lookup"><span data-stu-id="33366-134">Gender</span></span>
4. <span data-ttu-id="33366-135">Fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="33366-135">BirthDate</span></span>
5. <span data-ttu-id="33366-136">NRM (identificador)</span><span class="sxs-lookup"><span data-stu-id="33366-136">MRN (Identifier)</span></span>

<span data-ttu-id="33366-137">Además de los campos Argonaut, para una experiencia de usuario excelente la aplicación de los pacientes también lee los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="33366-137">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="33366-138">Name.Use</span><span class="sxs-lookup"><span data-stu-id="33366-138">Name.Use</span></span>
2. <span data-ttu-id="33366-139">Name.Prefix</span><span class="sxs-lookup"><span data-stu-id="33366-139">Name.Prefix</span></span>
3. <span data-ttu-id="33366-140">CareProvider (esta referencia en el recurso de pacientes debe incluir los campos de visualización que se muestra en el siguiente ejemplo).</span><span class="sxs-lookup"><span data-stu-id="33366-140">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

* * *

    <span data-ttu-id="33366-141">Solicitud: Obtener <fhir-server>/paciente/<patient-id></span><span class="sxs-lookup"><span data-stu-id="33366-141">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="33366-142">Respuesta: {"resourceType": "Paciente", "id": "<patient-id>".</span><span class="sxs-lookup"><span data-stu-id="33366-142">Response: { "resourceType": "Patient", "id": "<patient-id>", .</span></span>
      <span data-ttu-id="33366-143">.</span><span class="sxs-lookup"><span data-stu-id="33366-143"></span></span>
      <span data-ttu-id="33366-144">.</span><span class="sxs-lookup"><span data-stu-id="33366-144"></span></span>
      <span data-ttu-id="33366-145">"nombre": [{"usar": "oficial", "prefijo": ["Mr"], "familia": ["Chau"], "asignado": ["Hugh"]}], "identificador": [{"usar": "oficial", "tipo": {"codificación": [{"sistema": "http://hl7.org/fhir/v2/0203", "código": "MR"}]}, "valor": "1234567"}], "género": "hombre", "fecha de nacimiento": "1957-06-05 ","careProvider": [{"Mostrar":"Jane Doe"}],}</span><span class="sxs-lookup"><span data-stu-id="33366-145">"name": [ { "use": "official", "prefix": [ "Mr" ], "family": [ "Chau" ], "given": [ "Hugh" ] } ], "identifier": [ { "use": "official", "type": { "coding": [ { "system": "http://hl7.org/fhir/v2/0203", "code": "MR" } ] }, "value": "1234567" } ], "gender": "male", "birthDate": "1957-06-05", "careProvider": [{ "display": "Jane Doe" }], }</span></span>

* * *

<span data-ttu-id="33366-146">Una búsqueda de recursos, utiliza el método POST en /Patient/_search y los parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="33366-146">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="33366-147">Id.</span><span class="sxs-lookup"><span data-stu-id="33366-147">id</span></span>
2. <span data-ttu-id="33366-148">familia: contiene = (búsquedas para todos los pacientes cuyo nombre familia contiene el valor).</span><span class="sxs-lookup"><span data-stu-id="33366-148">family:contains=(searches for all patients whose family name contains the value.)</span></span>
3. <span data-ttu-id="33366-149">determinado =\<substring></span><span class="sxs-lookup"><span data-stu-id="33366-149">given=\<substring></span></span>
4. <span data-ttu-id="33366-150">nombre =\<substring></span><span class="sxs-lookup"><span data-stu-id="33366-150">name=\<substring></span></span>
5. <span data-ttu-id="33366-151">fecha de nacimiento =(exact match)</span><span class="sxs-lookup"><span data-stu-id="33366-151">birthdate=(exact match)</span></span>
6. <span data-ttu-id="33366-152">\_Count (número máximo de resultados que se deben devolver)</span><span class="sxs-lookup"><span data-stu-id="33366-152">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="33366-153">La respuesta debe contener el número total de registros devueltos como resultado de la búsqueda, y \_count usará el PatientsApp para limitar el número de registros devueltos.</span><span class="sxs-lookup"><span data-stu-id="33366-153">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="33366-154">identificador =\<mrn></span><span class="sxs-lookup"><span data-stu-id="33366-154">identifier=\<mrn></span></span>

<span data-ttu-id="33366-155">El objetivo es que puedan buscar y filtrar un paciente por lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="33366-155">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="33366-156">ID: Este es el identificador de recursos que tiene todos los recursos en FHIR.</span><span class="sxs-lookup"><span data-stu-id="33366-156">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="33366-157">NRM: Éste es el identificador real para el paciente que sabe ensayos personal.</span><span class="sxs-lookup"><span data-stu-id="33366-157">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="33366-158">Somos conscientes de que este NRM se basa en el tipo de identificador dentro de los recursos de identificador en FHIR</span><span class="sxs-lookup"><span data-stu-id="33366-158">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="33366-159">Nombre</span><span class="sxs-lookup"><span data-stu-id="33366-159">Name</span></span>
- <span data-ttu-id="33366-160">Fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="33366-160">Birthdate</span></span>

<span data-ttu-id="33366-161">Vea el siguiente ejemplo de esta llamada.</span><span class="sxs-lookup"><span data-stu-id="33366-161">See the following example  of this call.</span></span>

* * *

    <span data-ttu-id="33366-162">Solicitud: Cuerpo de la solicitud POST <fhir-server>/paciente/_search: determinado = hugh&family = chau</span><span class="sxs-lookup"><span data-stu-id="33366-162">Request: POST <fhir-server>/Patient/_search Request Body: given=hugh&family=chau</span></span>
    
    <span data-ttu-id="33366-163">Respuesta: {"resourceType": "Agrupar", "id": "<bundle-id>".</span><span class="sxs-lookup"><span data-stu-id="33366-163">Response: { "resourceType": "Bundle", "id": "<bundle-id>", .</span></span>
      <span data-ttu-id="33366-164">.</span><span class="sxs-lookup"><span data-stu-id="33366-164"></span></span>
      <span data-ttu-id="33366-165">.</span><span class="sxs-lookup"><span data-stu-id="33366-165"></span></span>
      <span data-ttu-id="33366-166">"entry": [{"recursos": {"resourceType": "Paciente", "id": "<patient id>", "nombre": [{"texto": "Hugh Chau", "familia": ["Chau"], "asignado": ["Hugh"]}], "género": "hombre", "fecha de nacimiento": "1957-06-05"}, "búsqueda": {"modo de": "coincide con"}}]}</span><span class="sxs-lookup"><span data-stu-id="33366-166">"entry": [ { "resource": { "resourceType": "Patient", "id": "<patient-id>", "name": [ { "text": "Hugh Chau", "family": [ "Chau" ], "given": [ "Hugh" ] } ], "gender": "male", "birthDate": "1957-06-05" }, "search": { "mode": "match" } } ] }</span></span>

* * *

<span data-ttu-id="33366-167">Vea [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) establecer otros detalles en este campo.</span><span class="sxs-lookup"><span data-stu-id="33366-167">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="33366-168">Observación</span><span class="sxs-lookup"><span data-stu-id="33366-168">Observation</span></span>

<span data-ttu-id="33366-169">Estos son los mínimos campos obligatorios, que son un subconjunto de los perfiles de vitales Argonaut:</span><span class="sxs-lookup"><span data-stu-id="33366-169">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 1. <span data-ttu-id="33366-170">Eficaces (fecha, hora o período)</span><span class="sxs-lookup"><span data-stu-id="33366-170">Effective (date time or period)</span></span>
 2. <span data-ttu-id="33366-171">Code.Coding.Code</span><span class="sxs-lookup"><span data-stu-id="33366-171">Code.Coding.Code</span></span>
 3. <span data-ttu-id="33366-172">ValueQuantity.Value</span><span class="sxs-lookup"><span data-stu-id="33366-172">ValueQuantity.Value</span></span>

<span data-ttu-id="33366-173">Además de los campos Argonaut, para una experiencia de usuario excelente la aplicación de los pacientes también lee los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="33366-173">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 1. <span data-ttu-id="33366-174">Code.Coding.Display</span><span class="sxs-lookup"><span data-stu-id="33366-174">Code.Coding.Display</span></span>
 2. <span data-ttu-id="33366-175">ValueQuantity.Unit</span><span class="sxs-lookup"><span data-stu-id="33366-175">ValueQuantity.Unit</span></span>

<span data-ttu-id="33366-176">Si usa las observaciones de componente, se aplica la misma lógica para cada observación del componente.</span><span class="sxs-lookup"><span data-stu-id="33366-176">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="33366-177">Una búsqueda de recursos utiliza el método GET y los parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="33366-177">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="33366-178">paciente =\<identificador de pacientes\></span><span class="sxs-lookup"><span data-stu-id="33366-178">patient=\<patient id\></span></span>
2. <span data-ttu-id="33366-179">ordenación: desc =\<campo ex.</span><span class="sxs-lookup"><span data-stu-id="33366-179">sort:desc=\<field ex.</span></span> <span data-ttu-id="33366-180">fecha\></span><span class="sxs-lookup"><span data-stu-id="33366-180">date\></span></span>

<span data-ttu-id="33366-181">El objetivo es poder recuperar las constantes vitales más recientes de un paciente, [VitalSigns.DSTU.saz] (observación?).</span><span class="sxs-lookup"><span data-stu-id="33366-181">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

* * *

    <span data-ttu-id="33366-182">Solicitud: Obtener <fhir-server> de observación? paciente = <patient-id>&_sort:desc = date&category = vital signos</span><span class="sxs-lookup"><span data-stu-id="33366-182">Request: GET <fhir-server>/Observation?patient=<patient-id>&_sort:desc=date&category=vital-signs</span></span>
    
    <span data-ttu-id="33366-183">Respuesta: {"resourceType": "Agrupar", "id": "<bundle id>", "tipo": "searchset", "total": 20, "entry": [{"recursos": {"resourceType": "Observación", "id": "<resource id>", "categoría": {"codificación": [{código":"vital de signos"}],},"código": {" codificación": [{"sistema":"http://loinc.org","código":"39156-5","presentación":"IMC"}],},"effectiveDateTime":"2009-12-01","valueQuantity": {"valor": 34,4,"unidad":" kg/m2","sistema":"http://unitsofmeasure.org","código":" kg/m2"}},},.</span><span class="sxs-lookup"><span data-stu-id="33366-183">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": { "coding": [ { code": "vital-signs" } ], }, "code": { "coding": [ { "system": "http://loinc.org", "code": "39156-5", "display": "bmi" } ], }, "effectiveDateTime": "2009-12-01", "valueQuantity": { "value": 34.4, "unit": "kg/m2", "system": "http://unitsofmeasure.org", "code": "kg/m2" } }, }, .</span></span>
        <span data-ttu-id="33366-184">.</span><span class="sxs-lookup"><span data-stu-id="33366-184"></span></span>
        <span data-ttu-id="33366-185">.</span><span class="sxs-lookup"><span data-stu-id="33366-185"></span></span>
      <span data-ttu-id="33366-186">] }</span><span class="sxs-lookup"><span data-stu-id="33366-186"></span></span>

* * *

<span data-ttu-id="33366-187">Vea [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) establecer otros detalles en este campo.</span><span class="sxs-lookup"><span data-stu-id="33366-187">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="33366-188">Condición</span><span class="sxs-lookup"><span data-stu-id="33366-188">Condition</span></span>

<span data-ttu-id="33366-189">Estos son los mínimos campos obligatorios, que son un subconjunto del [perfil de condición de Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span><span class="sxs-lookup"><span data-stu-id="33366-189">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="33366-190">Code.Coding[0]. Monitor</span><span class="sxs-lookup"><span data-stu-id="33366-190">Code.Coding[0].Display</span></span>

<span data-ttu-id="33366-191">Además de los campos Argonaut, para una experiencia de usuario excelente la aplicación de los pacientes también puede leer los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="33366-191">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="33366-192">Fecha registrada</span><span class="sxs-lookup"><span data-stu-id="33366-192">Date Recorded</span></span>
2. <span data-ttu-id="33366-193">Gravedad</span><span class="sxs-lookup"><span data-stu-id="33366-193">Severity</span></span>

<span data-ttu-id="33366-194">Una búsqueda de recursos utiliza el método GET y los parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="33366-194">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="33366-195">paciente =\<id> paciente</span><span class="sxs-lookup"><span data-stu-id="33366-195">patient=\<patient id></span></span>
2. <span data-ttu-id="33366-196">_Count =\<results> máx.</span><span class="sxs-lookup"><span data-stu-id="33366-196">_count=\<max results></span></span>

<span data-ttu-id="33366-197">Vea el siguiente ejemplo de esta llamada:</span><span class="sxs-lookup"><span data-stu-id="33366-197">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="33366-198">Solicitud: Obtener <fhir-server>/condición? paciente = <patient id>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="33366-198">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="33366-199">Respuesta: {"resourceType": "Agrupar", "id": "<bundle id>", "tipo": "searchset", "total": 1, "entry": [{"recursos": {"resourceType": "Condición", "id": "<resource id>", "código": {"codificación": [{               "sistema": "http://snomed.info/sct", "código": "386033004", "Mostrar": "Neuropathy (daño de los nervios)"}]}, "dateRecorded": "2018-09-17", "severity": {"codificación": [{"syst MT":"http://snomed.info/sct","código":"24484000","Mostrar":"Grave"}]}},}]}</span><span class="sxs-lookup"><span data-stu-id="33366-199">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Condition",         "id": "<resource-id>",         "code": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "386033004",               "display": "Neuropathy (nerve damage)"             }           ]         },         "dateRecorded": "2018-09-17",         "severity": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "24484000",               "display": "Severe"             }           ]         }       },     }   ] }</span></span>

* * *

<span data-ttu-id="33366-200">Vea [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) establecer otros detalles en este campo.</span><span class="sxs-lookup"><span data-stu-id="33366-200">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="33366-201">Encontrar</span><span class="sxs-lookup"><span data-stu-id="33366-201">Encounter</span></span>

<span data-ttu-id="33366-202">Estos son los mínimos campos obligatorios, que son un subconjunto de los campos de "debe tener" de perfil nos surgir principales:</span><span class="sxs-lookup"><span data-stu-id="33366-202">These are the minimum required fields, which are a subset of the US Core Encounter profile “must have” fields:</span></span>

1. <span data-ttu-id="33366-203">Estado</span><span class="sxs-lookup"><span data-stu-id="33366-203">Status</span></span>
2. <span data-ttu-id="33366-204">Tipo [0]. Codificación [0]. Monitor</span><span class="sxs-lookup"><span data-stu-id="33366-204">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="33366-205">Además, los siguientes campos de perfil nos surgir Core "deben admitir" de campos</span><span class="sxs-lookup"><span data-stu-id="33366-205">In addition, the following fields from US Core Encounter profile’s “must support” fields</span></span>

1. <span data-ttu-id="33366-206">Period.Start</span><span class="sxs-lookup"><span data-stu-id="33366-206">Period.Start</span></span>
2. <span data-ttu-id="33366-207">Ubicación [0]. Location.Display</span><span class="sxs-lookup"><span data-stu-id="33366-207">Location[0].Location.Display</span></span>

<span data-ttu-id="33366-208">Una búsqueda de recursos utiliza el método GET y los parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="33366-208">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="33366-209">paciente =\<id> paciente</span><span class="sxs-lookup"><span data-stu-id="33366-209">patient=\<patient id></span></span>
2. <span data-ttu-id="33366-210">_sort:desc =\<campo ex.</span><span class="sxs-lookup"><span data-stu-id="33366-210">_sort:desc=\<field ex.</span></span> <span data-ttu-id="33366-211">date></span><span class="sxs-lookup"><span data-stu-id="33366-211">date></span></span>
3. <span data-ttu-id="33366-212">_Count =\<results> máx.</span><span class="sxs-lookup"><span data-stu-id="33366-212">_count=\<max results></span></span>

<span data-ttu-id="33366-213">El objetivo es poder recuperar la última ubicación conocida del paciente.</span><span class="sxs-lookup"><span data-stu-id="33366-213">The goal is to be able to retrieve the patient’s last known location.</span></span> <span data-ttu-id="33366-214">Cada hace referencia a un recurso de ubicación.</span><span class="sxs-lookup"><span data-stu-id="33366-214">Each encounter references a location resource.</span></span> <span data-ttu-id="33366-215">La referencia también incluirá el campo de visualización de la ubicación.</span><span class="sxs-lookup"><span data-stu-id="33366-215">The reference shall also include the location’s display field.</span></span> <span data-ttu-id="33366-216">Vea el siguiente ejemplo de esta llamada.</span><span class="sxs-lookup"><span data-stu-id="33366-216">See the following example of this call.</span></span>
* * *

    <span data-ttu-id="33366-217">Solicitud: Obtener <fhir-server>/encontró? paciente = <patient-id>&_sort:desc = date&_count = 1</span><span class="sxs-lookup"><span data-stu-id="33366-217">Request: GET <fhir-server>/Encounter?patient=<patient-id>&_sort:desc=date&_count=1</span></span>
    
    <span data-ttu-id="33366-218">Respuesta: {"resourceType": "Agrupación", "tipo": "searchset", "total": 1, "entry": [{"recursos": {"resourceType": "Encontrar", "id": "<resource id>", "identificador": [{"usar": "oficial", "valor": "<id>"}], "estado" : "llegó a", "tipo": [{"codificación": [{"Mostrar": "Cita"}],}], "paciente": {"referencia": "<patient/paciente-id>"}, "punto": {"iniciar": "17/09/2018 1:00:00 P.M."}, "ubicación": [{              "ubicación de": {"Mostrar": "Inmensas – ENT"},}]}}]}</span><span class="sxs-lookup"><span data-stu-id="33366-218">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Encounter",         "id": "<resource-id>",         "identifier": [{ "use": "official", "value": "<id>" }],         "status": "arrived",         "type": [           {             "coding": [{ "display": "Appointment" }],           }         ],         "patient": { "reference": "Patient/<patient-id>" },         "period": { "start": "09/17/2018 1:00:00 PM" },         "location": [           {             "location": { "display": "Clinic - ENT" },           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="33366-219">Vea [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) establecer otros detalles en este campo.</span><span class="sxs-lookup"><span data-stu-id="33366-219">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="33366-220">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="33366-220">AllergyIntolerance</span></span>

<span data-ttu-id="33366-221">Estos son los mínimos campos obligatorios, que son un subconjunto de los perfiles de Argonaut AllergyIntolerance:</span><span class="sxs-lookup"><span data-stu-id="33366-221">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

1. <span data-ttu-id="33366-222">Code.Text</span><span class="sxs-lookup"><span data-stu-id="33366-222">Code.Text</span></span>
2. <span data-ttu-id="33366-223">Code.Coding[0]. Monitor</span><span class="sxs-lookup"><span data-stu-id="33366-223">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="33366-224">Estado</span><span class="sxs-lookup"><span data-stu-id="33366-224">Status</span></span>

<span data-ttu-id="33366-225">Además de los campos Argonaut, para una experiencia de usuario excelente la aplicación de los pacientes también lee los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="33366-225">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="33366-226">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="33366-226">RecordedDate</span></span>
2. <span data-ttu-id="33366-227">Note.Text</span><span class="sxs-lookup"><span data-stu-id="33366-227">Note.Text</span></span>
3. <span data-ttu-id="33366-228">Reacción [.]. Substance.Text</span><span class="sxs-lookup"><span data-stu-id="33366-228">Reaction[..].Substance.Text</span></span>
4. <span data-ttu-id="33366-229">Reacción [.]. Manifestación [.]. Texto</span><span class="sxs-lookup"><span data-stu-id="33366-229">Reaction[..].Manifestation[..].Text</span></span>
5. <span data-ttu-id="33366-230">Text.Div</span><span class="sxs-lookup"><span data-stu-id="33366-230">Text.Div</span></span>

<span data-ttu-id="33366-231">Una búsqueda de recursos utiliza el método GET y los parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="33366-231">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="33366-232">Paciente = \<id> paciente</span><span class="sxs-lookup"><span data-stu-id="33366-232">Patient =  \<patient id></span></span>

<span data-ttu-id="33366-233">Vea el siguiente ejemplo de esta llamada:</span><span class="sxs-lookup"><span data-stu-id="33366-233">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="33366-234">Solicitud: Obtener <fhir-server>/AllergyIntolerance? paciente = <patient-id></span><span class="sxs-lookup"><span data-stu-id="33366-234">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="33366-235">Respuesta: {"resourceType": "Agrupar", "id": "<bundle id>", "tipo": "searchset", "total": 1, "entry": [{"recursos": {"resourceType": "AllergyIntolerance", "id": "<resource id>", "recordedDate": "2018-09-17T07:00:00.00 0Z","sustancia": {"texto":"Cajuil"},"estado":"confirmado","reacción": [{"sustancia": {"texto":"cajuil tuerca alergénicos extraer inyectables producto"},"manifestati en": [{"texto":"Anaphylactic reacción"}]}]}}]}</span><span class="sxs-lookup"><span data-stu-id="33366-235">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "recordedDate": "2018-09-17T07:00:00.000Z",         "substance": {           "text": "Cashew nuts"         },         "status": "confirmed",         "reaction": [           {             "substance": {               "text": "cashew nut allergenic extract Injectable Product"             },             "manifestation": [               {                 "text": "Anaphylactic reaction"               }             ]           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="33366-236">Vea [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) establecer otros detalles en este campo.</span><span class="sxs-lookup"><span data-stu-id="33366-236">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="33366-237">Orden de medicación</span><span class="sxs-lookup"><span data-stu-id="33366-237">Medication Order</span></span>

<span data-ttu-id="33366-238">Estos son los mínimos campos obligatorios, que son un subconjunto de los perfiles de Argonaut MedicationOrder:</span><span class="sxs-lookup"><span data-stu-id="33366-238">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

1. <span data-ttu-id="33366-239">DateWritten</span><span class="sxs-lookup"><span data-stu-id="33366-239">DateWritten</span></span>
2. <span data-ttu-id="33366-240">Prescriber.Display</span><span class="sxs-lookup"><span data-stu-id="33366-240">Prescriber.Display</span></span>
3. <span data-ttu-id="33366-241">Medication.Display (si referencia)</span><span class="sxs-lookup"><span data-stu-id="33366-241">Medication.Display (if reference)</span></span>
4. <span data-ttu-id="33366-242">Medication.Text (si concepto)</span><span class="sxs-lookup"><span data-stu-id="33366-242">Medication.Text (if concept)</span></span>

<span data-ttu-id="33366-243">Además de los campos Argonaut, para una experiencia de usuario excelente la aplicación de los pacientes también puede leer los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="33366-243">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="33366-244">DateEnded</span><span class="sxs-lookup"><span data-stu-id="33366-244">DateEnded</span></span>
2. <span data-ttu-id="33366-245">DosageInstruction.Text</span><span class="sxs-lookup"><span data-stu-id="33366-245">DosageInstruction.Text</span></span>
3. <span data-ttu-id="33366-246">Text.Div</span><span class="sxs-lookup"><span data-stu-id="33366-246">Text.Div</span></span>

<span data-ttu-id="33366-247">Una búsqueda de recursos utiliza el método GET y los parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="33366-247">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="33366-248">paciente =\<id> paciente</span><span class="sxs-lookup"><span data-stu-id="33366-248">patient=\<patient id></span></span>
2. <span data-ttu-id="33366-249">_Count =\<results> máx.</span><span class="sxs-lookup"><span data-stu-id="33366-249">_count=\<max results></span></span>

<span data-ttu-id="33366-250">Vea el siguiente ejemplo de esta llamada:</span><span class="sxs-lookup"><span data-stu-id="33366-250">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="33366-251">Solicitud: Obtener <fhir-server>/MedicationOrder? paciente = <patient id>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="33366-251">Request: GET <fhir-server>/MedicationOrder?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="33366-252">Respuesta: {"resourceType": "Agrupar", "id": "<bundle id>", "tipo": "searchset", "total": 1, "entry": [{"recursos": {"resourceType": "MedicationOrder", "id": "<resource id>", "dateWritten": "2018-09-17", "medi cationCodeableConcept": {"texto":"Lisinopril 20 MB verbal Tablet"},"prescriber": {"Mostrar":"Jane Doe"},"dosageInstruction": [{"texto":"1 diario"}]}}]}</span><span class="sxs-lookup"><span data-stu-id="33366-252">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "MedicationOrder",         "id": "<resource-id>",         "dateWritten": "2018-09-17",         "medicationCodeableConcept": {           "text": "Lisinopril 20 MG Oral Tablet"         },         "prescriber": {           "display": "Jane Doe"         },         "dosageInstruction": [           {             "text": "1 daily"           }         ]       }     }   ] }</span></span>

* * *  

<span data-ttu-id="33366-253">Vea [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) establecer otros detalles en este campo.</span><span class="sxs-lookup"><span data-stu-id="33366-253">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="33366-254">Cobertura</span><span class="sxs-lookup"><span data-stu-id="33366-254">Coverage</span></span>

<span data-ttu-id="33366-255">Estos son los campos obligatorios mínimos, no están cubiertos por nosotros principales o Argonaut perfiles:</span><span class="sxs-lookup"><span data-stu-id="33366-255">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="33366-256">Paga</span><span class="sxs-lookup"><span data-stu-id="33366-256">Payor</span></span>

<span data-ttu-id="33366-257">Una búsqueda de recursos utiliza el método GET y los parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="33366-257">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="33366-258">paciente =\<id> paciente</span><span class="sxs-lookup"><span data-stu-id="33366-258">patient=\<patient id></span></span>

<span data-ttu-id="33366-259">Vea el siguiente ejemplo de esta llamada:</span><span class="sxs-lookup"><span data-stu-id="33366-259">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="33366-260">Solicitud: Obtener la <fhir-server>/cobertura? paciente = <patient-id></span><span class="sxs-lookup"><span data-stu-id="33366-260">Request: GET <fhir-server>/Coverage?patient=<patient-id></span></span>
    
    <span data-ttu-id="33366-261">Respuesta: {"resourceType": "Agrupación", "tipo": "searchset", "total": 1, "entry": [{"recursos": {"resourceType": "Cobertura", "id": "<resource id>", "plan": "No principal seguro", "suscriptor": {"referencia": "paciente / <patient-id> "}}}]}</span><span class="sxs-lookup"><span data-stu-id="33366-261">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Coverage",         "id": "<resource-id>",         "plan": "No Primary Insurance",         "subscriber": { "reference": "Patient/<patient-id>" }       }     }   ] }</span></span>

* * *

<span data-ttu-id="33366-262">Vea [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) establecer otros detalles en este campo.</span><span class="sxs-lookup"><span data-stu-id="33366-262">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="33366-263">Ubicación</span><span class="sxs-lookup"><span data-stu-id="33366-263">Location</span></span>

<span data-ttu-id="33366-264">Este recurso sólo se utiliza como una referencia en el recurso de [encontrar](#encounter) .</span><span class="sxs-lookup"><span data-stu-id="33366-264">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="33366-265">Vea [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) establecer otros detalles en este campo.</span><span class="sxs-lookup"><span data-stu-id="33366-265">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
