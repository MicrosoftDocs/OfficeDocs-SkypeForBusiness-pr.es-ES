---
title: Interfaz de STU3 de integración de aplicación de los pacientes y EHR
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
ms.openlocfilehash: 34fd6bb1ecaf788a55aca877c671c9a51cb07944
ms.sourcegitcommit: cf2cb5b7e03385b33e34a5ff89719adb882525b1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2019
ms.locfileid: "33643139"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="8beb1-103">Especificación de la interfaz STU3</span><span class="sxs-lookup"><span data-stu-id="8beb1-103">STU3 interface specification</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="8beb1-104">Configurar o volver a configurar un servidor FHIR para trabajar con la aplicación de los pacientes de los equipos de Microsoft requiere la descripción de los datos que la aplicación necesita obtener acceso a.</span><span class="sxs-lookup"><span data-stu-id="8beb1-104">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="8beb1-105">El servidor FHIR debe admitir solicitudes POST con paquetes para los siguientes recursos:</span><span class="sxs-lookup"><span data-stu-id="8beb1-105">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="8beb1-106">Paciente</span><span class="sxs-lookup"><span data-stu-id="8beb1-106">Patient</span></span>](#patient)
- [<span data-ttu-id="8beb1-107">Observación</span><span class="sxs-lookup"><span data-stu-id="8beb1-107">Observation</span></span>](#observation)
- [<span data-ttu-id="8beb1-108">Condición</span><span class="sxs-lookup"><span data-stu-id="8beb1-108">Condition</span></span>](#condition)
- [<span data-ttu-id="8beb1-109">Encontrar</span><span class="sxs-lookup"><span data-stu-id="8beb1-109">Encounter</span></span>](#encounter)
- [<span data-ttu-id="8beb1-110">Alergia intolerancia</span><span class="sxs-lookup"><span data-stu-id="8beb1-110">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="8beb1-111">Cobertura</span><span class="sxs-lookup"><span data-stu-id="8beb1-111">Coverage</span></span>](#coverage)
- <span data-ttu-id="8beb1-112">[Instrucción de medicación](#medication-request) (sustituye a la MedicationOrder en la versión DSTU2 de la PatientsApp)</span><span class="sxs-lookup"><span data-stu-id="8beb1-112">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="8beb1-113">Ubicación (la información necesaria desde este recurso puede estar incluida en encontró)</span><span class="sxs-lookup"><span data-stu-id="8beb1-113">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="8beb1-114">El paciente recurso es el recurso sólo es obligatorio (sin que la aplicación no se cargará en absoluto); Sin embargo, se recomienda que el socio implementar la compatibilidad de todos los recursos mencionados anteriormente por especificaciones proporcionados por debajo de la mejor experiencia del usuario final con la aplicación de los pacientes de los equipos de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8beb1-114">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="8beb1-115">Las consultas de la aplicación de los pacientes de los equipos de Microsoft para más de un recurso deberán registrar una agrupación (lote) de solicitudes a la dirección URL del servidor FHIR.</span><span class="sxs-lookup"><span data-stu-id="8beb1-115">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="8beb1-116">El servidor debe procesar cada solicitud y devolver una agrupación de los recursos que coinciden con cada solicitud.</span><span class="sxs-lookup"><span data-stu-id="8beb1-116">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="8beb1-117">Para obtener más información y ejemplos, consulte [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span><span class="sxs-lookup"><span data-stu-id="8beb1-117">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="8beb1-118">Instrucción de capacidad</span><span class="sxs-lookup"><span data-stu-id="8beb1-118">Capability Statement</span></span>

<span data-ttu-id="8beb1-119">Estos son los campos obligatorios mínimos:</span><span class="sxs-lookup"><span data-stu-id="8beb1-119">These are the minimum required fields:</span></span>

1. <span data-ttu-id="8beb1-120">reposo</span><span class="sxs-lookup"><span data-stu-id="8beb1-120">REST</span></span>
   1. <span data-ttu-id="8beb1-121">Modo</span><span class="sxs-lookup"><span data-stu-id="8beb1-121">Mode</span></span>
   2. <span data-ttu-id="8beb1-122">Interacción</span><span class="sxs-lookup"><span data-stu-id="8beb1-122">Interaction</span></span>
   3. <span data-ttu-id="8beb1-123">Recurso: tipo</span><span class="sxs-lookup"><span data-stu-id="8beb1-123">Resource: Type</span></span>
   4. <span data-ttu-id="8beb1-124">Seguridad: [extensión para los identificadores URI de OAuth](http://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="8beb1-124">Security: [Extension for OAuth URIs](http://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="8beb1-125">FhirVersion (nuestro código requiere esto para comprender qué versión se deberíamos dinámicas a).</span><span class="sxs-lookup"><span data-stu-id="8beb1-125">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="8beb1-126">Vea [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) establecer otros detalles en este campo.</span><span class="sxs-lookup"><span data-stu-id="8beb1-126">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="8beb1-127">Paciente</span><span class="sxs-lookup"><span data-stu-id="8beb1-127">Patient</span></span>

<span data-ttu-id="8beb1-128">Estos son los mínimos campos obligatorios, que son un subconjunto de los campos de perfil de pacientes Argonaut:</span><span class="sxs-lookup"><span data-stu-id="8beb1-128">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

1. <span data-ttu-id="8beb1-129">Name.Given</span><span class="sxs-lookup"><span data-stu-id="8beb1-129">Name.Given</span></span>
2. <span data-ttu-id="8beb1-130">Name.Family</span><span class="sxs-lookup"><span data-stu-id="8beb1-130">Name.Family</span></span>
3. <span data-ttu-id="8beb1-131">Género</span><span class="sxs-lookup"><span data-stu-id="8beb1-131">Gender</span></span>
4. <span data-ttu-id="8beb1-132">Fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="8beb1-132">BirthDate</span></span>
5. <span data-ttu-id="8beb1-133">NRM (identificador)</span><span class="sxs-lookup"><span data-stu-id="8beb1-133">MRN (Identifier)</span></span>

<span data-ttu-id="8beb1-134">Además de los [campos de Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), para una experiencia de usuario excelente la aplicación de los pacientes también puede leer los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="8beb1-134">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="8beb1-135">Name.Use</span><span class="sxs-lookup"><span data-stu-id="8beb1-135">Name.Use</span></span>
2. <span data-ttu-id="8beb1-136">Name.Prefix</span><span class="sxs-lookup"><span data-stu-id="8beb1-136">Name.Prefix</span></span>
3. <span data-ttu-id="8beb1-137">[GeneralPractitioner] - GeneralPractitioner la referencia debe incluirse en el recurso de pacientes (sólo en el campo para mostrar)</span><span class="sxs-lookup"><span data-stu-id="8beb1-137">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="8beb1-138">Una búsqueda de recursos, utiliza el método POST en /Patient/_search y los parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="8beb1-138">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="8beb1-139">Id.</span><span class="sxs-lookup"><span data-stu-id="8beb1-139">id</span></span>
2. <span data-ttu-id="8beb1-140">familia de = (busca todos los pacientes cuyo nombre familia contiene el valor)</span><span class="sxs-lookup"><span data-stu-id="8beb1-140">family=(searches for all patients whose family name contains the value)</span></span>
3. <span data-ttu-id="8beb1-141">determinado =\<substring></span><span class="sxs-lookup"><span data-stu-id="8beb1-141">given=\<substring></span></span>
4. <span data-ttu-id="8beb1-142">fecha de nacimiento =(exact match)</span><span class="sxs-lookup"><span data-stu-id="8beb1-142">birthdate=(exact match)</span></span>
5. <span data-ttu-id="8beb1-143">género = (valores que se va a uno del género-administrativas)</span><span class="sxs-lookup"><span data-stu-id="8beb1-143">gender=(values being one of the administrative-gender)</span></span>
6. <span data-ttu-id="8beb1-144">\_Count (número máximo de resultados que se deben devolver)</span><span class="sxs-lookup"><span data-stu-id="8beb1-144">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="8beb1-145">La respuesta debe contener el número total de registros devueltos como resultado de la búsqueda y \_count usará el PatientsApp para limitar el número de registros devueltos.</span><span class="sxs-lookup"><span data-stu-id="8beb1-145">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="8beb1-146">identificador =\<mrn></span><span class="sxs-lookup"><span data-stu-id="8beb1-146">identifier=\<mrn></span></span>

<span data-ttu-id="8beb1-147">El objetivo es que puedan buscar y filtrar un paciente por lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8beb1-147">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="8beb1-148">ID: Este es el identificador de recursos que tiene todos los recursos en FHIR.</span><span class="sxs-lookup"><span data-stu-id="8beb1-148">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="8beb1-149">NRM: Éste es el identificador real para el paciente que sabe ensayos personal.</span><span class="sxs-lookup"><span data-stu-id="8beb1-149">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="8beb1-150">Somos conscientes de que este NRM se basa en el tipo de identificador dentro de los recursos de identificador en FHIR.</span><span class="sxs-lookup"><span data-stu-id="8beb1-150">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="8beb1-151">Nombre</span><span class="sxs-lookup"><span data-stu-id="8beb1-151">Name</span></span>
- <span data-ttu-id="8beb1-152">Fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="8beb1-152">Birthdate</span></span>

<span data-ttu-id="8beb1-153">Vea el ejemplo siguiente de la llamada:</span><span class="sxs-lookup"><span data-stu-id="8beb1-153">See the following example of the call:</span></span>

* * *

    <span data-ttu-id="8beb1-154">Solicitud: Cuerpo de la solicitud POST <fhir-server>/paciente/_search: determinado = ruth&family = negro</span><span class="sxs-lookup"><span data-stu-id="8beb1-154">Request: POST <fhir-server>/Patient/_search Request Body: given=ruth&family=black</span></span>
    
    <span data-ttu-id="8beb1-155">Respuesta: {"resourceType": "Agrupar", "id": "<bundle id>", "meta": {"lastUpdated": "2019-01-14T23:44:45.052 + 00:00"}, "tipo": "searchset", "total": 1, "vínculo": [{"relation": "self", "url": <fhir-server>/paciente/_search "}],"entry": [{ "fullUrl": <fhir-server>/paciente/<patient-id> ","recursos": {"resourceType":"Paciente","id":"<patient id>","meta": {"versionId":"1","lastUpdated":" 2017-10-18T18:32:37.000 + 00:00 "},"texto": {"estado":"generado por","div ": "</span><span class="sxs-lookup"><span data-stu-id="8beb1-155">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "meta": { "lastUpdated": "2019-01-14T23:44:45.052+00:00" }, "type": "searchset", "total": 1, "link": [ { "relation": "self", "url": <fhir-server>/Patient/_search" } ], "entry": [ { "fullUrl": <fhir-server>/Patient/<patient-id>", "resource": { "resourceType": "Patient", "id": "<patient-id>", "meta": { "versionId": "1", "lastUpdated": "2017-10-18T18:32:37.000+00:00" }, "text": { "status": "generated", "div": "</span></span><div><span data-ttu-id="8beb1-156">\n</span><span class="sxs-lookup"><span data-stu-id="8beb1-156">\n</span></span>        <p><span data-ttu-id="8beb1-157">Ruth negro</span><span class="sxs-lookup"><span data-stu-id="8beb1-157">Ruth Black</span></span></p><span data-ttu-id="8beb1-158">\n</span><span class="sxs-lookup"><span data-stu-id="8beb1-158">\n</span></span>      </div><span data-ttu-id="8beb1-159">"},"identificador": [{"usar":"normal","tipo": {"codificación": [{"sistema":"http://hl7.org/fhir/v2/0203","código":"MR","Mostrar":"número de registro médico","userSelected": false}],"texto":"número de registro médico"},"sistema":"http://hospital.smarthealthit.org","valor":"1234567"}],"activa": true," nombre": [{"usar":"oficial","familia":"Negro","asignado": ["Ruth","c ".</span><span class="sxs-lookup"><span data-stu-id="8beb1-159">" }, "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "http://hl7.org/fhir/v2/0203", "code": "MR", "display": "Medical record number", "userSelected": false } ], "text": "Medical record number" }, "system": "http://hospital.smarthealthit.org", "value": "1234567" } ], "active": true, "name": [ { "use": "official", "family": "Black", "given": [ "Ruth", "C."</span></span>
    <span data-ttu-id="8beb1-160">[]}] "telecomunicaciones": [{"sistema": "phone", "valor": "uso de"800-599-2739",": "principal"}, {"sistema": "phone", "valor": "uso de"800-808-7785",": "móvil"}, {"sistema": "correo electrónico", "valor": "ruth.black@example.com"}], "género": "femenino", "fecha de nacimiento": "1951-08-23", " dirección": [{"usar":"principal","línea": ["26 sur RdApt 22"],"city":"Sapulpa","estado":"OK","CódigoPostal":"74066","country":"USA"}]},"búsqueda": {"modo de":"coincide con"}}]}</span><span class="sxs-lookup"><span data-stu-id="8beb1-160">] } ], "telecom": [ { "system": "phone", "value": "800-599-2739", "use": "home" }, { "system": "phone", "value": "800-808-7785", "use": "mobile" }, { "system": "email", "value": "ruth.black@example.com" } ], "gender": "female", "birthDate": "1951-08-23", "address": [ { "use": "home", "line": [ "26 South RdApt 22" ], "city": "Sapulpa", "state": "OK", "postalCode": "74066", "country": "USA" } ] }, "search": { "mode": "match" } } ] }</span></span>

* * *

    <span data-ttu-id="8beb1-161">Solicitud: Obtener <fhir-server>/paciente/<patient-id></span><span class="sxs-lookup"><span data-stu-id="8beb1-161">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="8beb1-162">Respuesta: {"resourceType": "Paciente", "id": "<patient id>", "identificador": [{"usar": "normal", "tipo": {"codificación": [{"sistema": "http://hl7.org/fhir/v2/0203", "código": "MR,"}], "texto": "número de registro médico"}, "valor": "1234567"}], "nombre": [{"usar": "oficial", " familia de":"Adams","asignado": ["Daniel","X".</span><span class="sxs-lookup"><span data-stu-id="8beb1-162">Response: { "resourceType": "Patient", "id": "<patient-id>", "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "http://hl7.org/fhir/v2/0203", "code": "MR", } ], "text": "Medical record number" }, "value": "1234567" } ], "name": [ { "use": "official", "family": "Adams", "given": [ "Daniel", "X."</span></span> <span data-ttu-id="8beb1-163">{}]], "género": "hombre", "fecha de nacimiento": "1925-12-23"}</span><span class="sxs-lookup"><span data-stu-id="8beb1-163">] } ], "gender": "male", "birthDate": "1925-12-23", }</span></span>

* * *

<span data-ttu-id="8beb1-164">Vea [http://hl7.org/fhir/stu3/patient.html](http://hl7.org/fhir/stu3/patient.html) establecer otros detalles en este campo.</span><span class="sxs-lookup"><span data-stu-id="8beb1-164">See [http://hl7.org/fhir/stu3/patient.html](http://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="8beb1-165">Observación</span><span class="sxs-lookup"><span data-stu-id="8beb1-165">Observation</span></span>

<span data-ttu-id="8beb1-166">Estos son los mínimos campos obligatorios, que son un subconjunto de los [perfiles de Argonaut vitales](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span><span class="sxs-lookup"><span data-stu-id="8beb1-166">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

1. <span data-ttu-id="8beb1-167">Eficaces (fecha, hora o período)</span><span class="sxs-lookup"><span data-stu-id="8beb1-167">Effective (date time or period)</span></span>
2. <span data-ttu-id="8beb1-168">Code.Coding.Code</span><span class="sxs-lookup"><span data-stu-id="8beb1-168">Code.Coding.Code</span></span>
3. <span data-ttu-id="8beb1-169">ValueQuantity.Value</span><span class="sxs-lookup"><span data-stu-id="8beb1-169">ValueQuantity.Value</span></span>

<span data-ttu-id="8beb1-170">Además de los campos Argonaut, para una experiencia de usuario excelente la aplicación de los pacientes también puede leer los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="8beb1-170">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="8beb1-171">Code.Coding.Display</span><span class="sxs-lookup"><span data-stu-id="8beb1-171">Code.Coding.Display</span></span>
2. <span data-ttu-id="8beb1-172">ValueQuantity.Unit</span><span class="sxs-lookup"><span data-stu-id="8beb1-172">ValueQuantity.Unit</span></span>

<span data-ttu-id="8beb1-173">Una búsqueda de recursos utiliza el método GET y los parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="8beb1-173">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="8beb1-174">paciente =\<id> paciente</span><span class="sxs-lookup"><span data-stu-id="8beb1-174">patient=\<patient id></span></span>
2. <span data-ttu-id="8beb1-175">_sort =-fecha</span><span class="sxs-lookup"><span data-stu-id="8beb1-175">_sort=-date</span></span>
3. <span data-ttu-id="8beb1-176">categoría (se van a consultar "categoría = vital signos") para recuperar la lista de constantes vitales.</span><span class="sxs-lookup"><span data-stu-id="8beb1-176">category (we will query for “category=vital-signs”) to retrieve the list of vital signs.</span></span>

<span data-ttu-id="8beb1-177">Hacer referencia a este ejemplo de la llamada:</span><span class="sxs-lookup"><span data-stu-id="8beb1-177">Refer to this example of the call:</span></span>

* * *

    <span data-ttu-id="8beb1-178">Solicitud: Obtener <fhir-server> de observación? paciente = <patient id>&category = vital signos</span><span class="sxs-lookup"><span data-stu-id="8beb1-178">Request: GET <fhir-server>/Observation?patient=<patient-id>&category=vital-signs</span></span>
    
    <span data-ttu-id="8beb1-179">Respuesta: {"resourceType": "Agrupar", "id": "<bundle id>", "tipo": "searchset", "total": 20, "entry": [{"recursos": {"resourceType": "Observación", "id": "<resource id>", "categoría": [{"codificación": [{"sistema": "http://hl7.org/fhir/observation-category", "código": " vital-signos"}],}],"código": {"codificación": [{"sistema":"http://loinc.org","código":"8867-4","presentación":"heart_rate"}]},"effectiveDateTime":" 2009-04-08T00:00:00-06:00 ","valueQuantity": {"valor": 72,0,"unidad":" {pulsaciones} / min ","sistema":"http://unitsofmeasure.org",}}},.</span><span class="sxs-lookup"><span data-stu-id="8beb1-179">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": [ { "coding": [ { "system": "http://hl7.org/fhir/observation-category", "code": "vital-signs" } ], } ], "code": { "coding": [ { "system": "http://loinc.org", "code": "8867-4", "display": "heart_rate" } ] }, "effectiveDateTime": "2009-04-08T00:00:00-06:00", "valueQuantity": { "value": 72.0, "unit": "{beats}/min", "system": "http://unitsofmeasure.org", } } }, .</span></span>
        <span data-ttu-id="8beb1-180">.</span><span class="sxs-lookup"><span data-stu-id="8beb1-180"></span></span>
        <span data-ttu-id="8beb1-181">.</span><span class="sxs-lookup"><span data-stu-id="8beb1-181"></span></span>
      <span data-ttu-id="8beb1-182">] }</span><span class="sxs-lookup"><span data-stu-id="8beb1-182"></span></span>

* * *

<span data-ttu-id="8beb1-183">Vea [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) establecer otros detalles en este campo.</span><span class="sxs-lookup"><span data-stu-id="8beb1-183">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="8beb1-184">Condición</span><span class="sxs-lookup"><span data-stu-id="8beb1-184">Condition</span></span>

<span data-ttu-id="8beb1-185">Aquí tiene los campos obligatorios mínimos, que son un subconjunto del [perfil de condición de Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span><span class="sxs-lookup"><span data-stu-id="8beb1-185">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

1. <span data-ttu-id="8beb1-186">Code.Coding[0]. Monitor</span><span class="sxs-lookup"><span data-stu-id="8beb1-186">Code.Coding[0].Display</span></span>

<span data-ttu-id="8beb1-187">Además de los campos Argonaut, para una experiencia de usuario excelente la aplicación de los pacientes también puede leer los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="8beb1-187">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="8beb1-188">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="8beb1-188">AssertedDate</span></span>
2. <span data-ttu-id="8beb1-189">Gravedad</span><span class="sxs-lookup"><span data-stu-id="8beb1-189">Severity</span></span>

<span data-ttu-id="8beb1-190">Una búsqueda de recursos utiliza el método GET y los parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="8beb1-190">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="8beb1-191">paciente =\<id> paciente</span><span class="sxs-lookup"><span data-stu-id="8beb1-191">patient=\<patient id></span></span>
2. <span data-ttu-id="8beb1-192">_Count =\<results> máx.</span><span class="sxs-lookup"><span data-stu-id="8beb1-192">_count=\<max results></span></span>

<span data-ttu-id="8beb1-193">Vea el siguiente ejemplo de esta llamada:</span><span class="sxs-lookup"><span data-stu-id="8beb1-193">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="8beb1-194">Solicitud: Obtener <fhir-server>/condición? paciente = <patient id>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="8beb1-194">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="8beb1-195">Respuesta: {"resourceType": "Agrupar", "id": "<bundle id>", "tipo": "searchset", "total": 2, "entry": [{"recursos": {"resourceType": "Condición", "id": "<resource id>", "código": {"codificación": [{"sistema": "http://snomed.info/sct", "código": "185903001", " Mostrar":"Las necesidades de inmunización de influenza,"}]},"severity": {"codificación": [{"sistema":"http://snomed.info/sct","código":"24484000","Mostrar":"Grave"}]},"assertedDate":"2018-04-04"}},.</span><span class="sxs-lookup"><span data-stu-id="8beb1-195">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 2, "entry": [ { "resource": { "resourceType": "Condition", "id": "<resource-id>", "code": { "coding": [ { "system": "http://snomed.info/sct", "code": "185903001", "display": "Needs influenza immunization", } ] }, "severity": { "coding": [ { "system": "http://snomed.info/sct", "code": "24484000", "display": "Severe" } ] }, "assertedDate": "2018-04-04" } }, .</span></span>
        <span data-ttu-id="8beb1-196">.</span><span class="sxs-lookup"><span data-stu-id="8beb1-196"></span></span>
        <span data-ttu-id="8beb1-197">.</span><span class="sxs-lookup"><span data-stu-id="8beb1-197"></span></span>
      <span data-ttu-id="8beb1-198">] }</span><span class="sxs-lookup"><span data-stu-id="8beb1-198"></span></span>

* * *
<span data-ttu-id="8beb1-199">Vea [http://hl7.org/fhir/stu3/condition.html](http://hl7.org/fhir/stu3/condition.html) establecer otros detalles en este campo.</span><span class="sxs-lookup"><span data-stu-id="8beb1-199">See [http://hl7.org/fhir/stu3/condition.html](http://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="8beb1-200">Encontrar</span><span class="sxs-lookup"><span data-stu-id="8beb1-200">Encounter</span></span>

<span data-ttu-id="8beb1-201">Estos son los mínimos campos obligatorios, que son un subconjunto de los campos de "debe tener" [perfil surgir de núcleo de Estados Unidos](http://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) ).</span><span class="sxs-lookup"><span data-stu-id="8beb1-201">These are the minimum required fields, which are a subset of the [US Core Encounter profile](http://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) “must have” fields).</span></span>

1. <span data-ttu-id="8beb1-202">Estado</span><span class="sxs-lookup"><span data-stu-id="8beb1-202">Status</span></span>
2. <span data-ttu-id="8beb1-203">Tipo [0]. Codificación [0]. Monitor</span><span class="sxs-lookup"><span data-stu-id="8beb1-203">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="8beb1-204">Además, los siguientes campos de perfil nos surgir Core "deben admitir" de campos:</span><span class="sxs-lookup"><span data-stu-id="8beb1-204">In addition, the following fields from US Core Encounter profile’s “must support” fields:</span></span>

1. <span data-ttu-id="8beb1-205">Period.Start</span><span class="sxs-lookup"><span data-stu-id="8beb1-205">Period.Start</span></span>
2. <span data-ttu-id="8beb1-206">Ubicación [0]. Location.Display</span><span class="sxs-lookup"><span data-stu-id="8beb1-206">Location[0].Location.Display</span></span>

<span data-ttu-id="8beb1-207">Una búsqueda de recursos utiliza el método GET y los parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="8beb1-207">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="8beb1-208">paciente =\<id> paciente</span><span class="sxs-lookup"><span data-stu-id="8beb1-208">patient=\<patient id></span></span>
2. <span data-ttu-id="8beb1-209">_sort:desc =\<campo ex.</span><span class="sxs-lookup"><span data-stu-id="8beb1-209">_sort:desc=\<field ex.</span></span> <span data-ttu-id="8beb1-210">date></span><span class="sxs-lookup"><span data-stu-id="8beb1-210">date></span></span>
3. <span data-ttu-id="8beb1-211">_Count =\<results> máx.</span><span class="sxs-lookup"><span data-stu-id="8beb1-211">_count=\<max results></span></span>

<span data-ttu-id="8beb1-212">El objetivo es poder recuperar la última ubicación conocida del paciente.</span><span class="sxs-lookup"><span data-stu-id="8beb1-212">The goal is to be able to retrieve the patient’s last known location.</span></span> <span data-ttu-id="8beb1-213">Cada hace referencia a un recurso de ubicación.</span><span class="sxs-lookup"><span data-stu-id="8beb1-213">Each encounter references a location resource.</span></span> <span data-ttu-id="8beb1-214">La referencia también incluirá el campo de visualización de la ubicación.</span><span class="sxs-lookup"><span data-stu-id="8beb1-214">The reference shall also include the location’s display field.</span></span>

<span data-ttu-id="8beb1-215">Vea [http://hl7.org/fhir/stu3/encounter.html](http://hl7.org/fhir/stu3/encounter.html) establecer otros detalles en este campo.</span><span class="sxs-lookup"><span data-stu-id="8beb1-215">See [http://hl7.org/fhir/stu3/encounter.html](http://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="8beb1-216">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="8beb1-216">AllergyIntolerance</span></span>

<span data-ttu-id="8beb1-217">Estos son los mínimos campos obligatorios, que son un subconjunto de los perfiles de [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) :</span><span class="sxs-lookup"><span data-stu-id="8beb1-217">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

1. <span data-ttu-id="8beb1-218">Code.Text</span><span class="sxs-lookup"><span data-stu-id="8beb1-218">Code.Text</span></span>
2. <span data-ttu-id="8beb1-219">Code.Coding[0]. Monitor</span><span class="sxs-lookup"><span data-stu-id="8beb1-219">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="8beb1-220">ClinicalStatus/VerificationStatus (se lea ambos)</span><span class="sxs-lookup"><span data-stu-id="8beb1-220">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="8beb1-221">Además de los campos Argonaut, para una experiencia de usuario excelente la aplicación de los pacientes también puede leer el siguiente campo:</span><span class="sxs-lookup"><span data-stu-id="8beb1-221">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

1. <span data-ttu-id="8beb1-222">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="8beb1-222">AssertedDate</span></span>
2. <span data-ttu-id="8beb1-223">Note.Text</span><span class="sxs-lookup"><span data-stu-id="8beb1-223">Note.Text</span></span>
3. <span data-ttu-id="8beb1-224">Reacción</span><span class="sxs-lookup"><span data-stu-id="8beb1-224">Reaction</span></span>
    1. <span data-ttu-id="8beb1-225">Sustancia (elemento de codificación uno)</span><span class="sxs-lookup"><span data-stu-id="8beb1-225">Substance (one coding element)</span></span>
    2. <span data-ttu-id="8beb1-226">Manifestación (elemento de codificación uno)</span><span class="sxs-lookup"><span data-stu-id="8beb1-226">Manifestation (one coding element)</span></span>

<span data-ttu-id="8beb1-227">Una búsqueda de recursos utiliza el método GET y los parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="8beb1-227">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="8beb1-228">Paciente = \<id> paciente</span><span class="sxs-lookup"><span data-stu-id="8beb1-228">Patient =  \<patient id></span></span>

<span data-ttu-id="8beb1-229">Vea el ejemplo siguiente de la llamada:</span><span class="sxs-lookup"><span data-stu-id="8beb1-229">See the following example of the call:</span></span> 

* * *

    <span data-ttu-id="8beb1-230">Solicitud: Obtener <fhir-server>/AllergyIntolerance? paciente = <patient-id></span><span class="sxs-lookup"><span data-stu-id="8beb1-230">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="8beb1-231">Respuesta: {"resourceType": "Agrupar", "id": "<bundle id>", "tipo": "searchset", "total": 1, "entry": [{"recursos": {"resourceType": "AllergyIntolerance", "id": "<resource id>", "clinicalStatus": "activo", "ve rificationStatus":"confirmado","código": {"codificación": [{"sistema":"http://rxnav.nlm.nih.gov/REST/Ndfrt","código":"N0000175503","Mostrar":"sulfonamide antibacterianas"}],"texto":"ant sulfonamide ibacterial"},"assertedDate":" 2018-01-01T00:00:00-07:00 ","reacción": [{"manifestación": [{"codificación": [{"sistema":"http://snomed.info/sct","código":  "271807003", "Mostrar": "sarpullido de máscara,"}], "texto": "sarpullido máscara"}],}]}}]}</span><span class="sxs-lookup"><span data-stu-id="8beb1-231">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "clinicalStatus": "active",         "verificationStatus": "confirmed",         "code": {           "coding": [             {               "system": "http://rxnav.nlm.nih.gov/REST/Ndfrt",               "code": "N0000175503",               "display": "sulfonamide antibacterial",             }           ],           "text": "sulfonamide antibacterial"         },         "assertedDate": "2018-01-01T00:00:00-07:00",         "reaction": [           {             "manifestation": [               {                 "coding": [                   {                     "system": "http://snomed.info/sct",                     "code": "271807003",                     "display": "skin rash",                   }                 ],                 "text": "skin rash"               }             ],           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="8beb1-232">Vea [http://hl7.org/fhir/stu3/allergyintolerance.html](http://hl7.org/fhir/stu3/allergyintolerance.html) establecer otros detalles en este campo.</span><span class="sxs-lookup"><span data-stu-id="8beb1-232">See [http://hl7.org/fhir/stu3/allergyintolerance.html](http://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="8beb1-233">Solicitud de medicación</span><span class="sxs-lookup"><span data-stu-id="8beb1-233">Medication Request</span></span>

<span data-ttu-id="8beb1-234">Estos son los mínimos campos obligatorios, que son un subconjunto de los [Estados Unidos principales medicación solicitar perfil](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span><span class="sxs-lookup"><span data-stu-id="8beb1-234">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

1. <span data-ttu-id="8beb1-235">Medication.Display (si referencia)</span><span class="sxs-lookup"><span data-stu-id="8beb1-235">Medication.Display (if Reference)</span></span>
2. <span data-ttu-id="8beb1-236">Medication.Text (si CodableConcept)</span><span class="sxs-lookup"><span data-stu-id="8beb1-236">Medication.Text (if CodableConcept)</span></span>
3. <span data-ttu-id="8beb1-237">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="8beb1-237">AuthoredOn</span></span>
4. <span data-ttu-id="8beb1-238">Requester.Agent.Display</span><span class="sxs-lookup"><span data-stu-id="8beb1-238">Requester.Agent.Display</span></span>

<span data-ttu-id="8beb1-239">Además de los campos nos principal, para una experiencia de usuario excelente la aplicación de los pacientes también puede leer los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="8beb1-239">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="8beb1-240">DosageInstruction [.]. Texto</span><span class="sxs-lookup"><span data-stu-id="8beb1-240">DosageInstruction[..].Text</span></span>
2. <span data-ttu-id="8beb1-241">Texto</span><span class="sxs-lookup"><span data-stu-id="8beb1-241">Text</span></span>

<span data-ttu-id="8beb1-242">Una búsqueda de recursos utiliza el método GET y los parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="8beb1-242">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="8beb1-243">paciente =\<id> paciente</span><span class="sxs-lookup"><span data-stu-id="8beb1-243">patient=\<patient id></span></span>
2. <span data-ttu-id="8beb1-244">_Count =\<results> máx.</span><span class="sxs-lookup"><span data-stu-id="8beb1-244">_count=\<max results></span></span>

<span data-ttu-id="8beb1-245">Vea [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) establecer otros detalles en este campo.</span><span class="sxs-lookup"><span data-stu-id="8beb1-245">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="8beb1-246">Cobertura</span><span class="sxs-lookup"><span data-stu-id="8beb1-246">Coverage</span></span>

<span data-ttu-id="8beb1-247">Estos son los campos obligatorios mínimos, no están cubiertos por nosotros principales o Argonaut perfiles:</span><span class="sxs-lookup"><span data-stu-id="8beb1-247">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="8beb1-248">Agrupación, al menos un elemento con</span><span class="sxs-lookup"><span data-stu-id="8beb1-248">Grouping, at least one element with</span></span>
    1. <span data-ttu-id="8beb1-249">Grupo IPMPVisualice</span><span class="sxs-lookup"><span data-stu-id="8beb1-249">GroupDisplay</span></span>
    2. <span data-ttu-id="8beb1-250">PlanDisplay</span><span class="sxs-lookup"><span data-stu-id="8beb1-250">PlanDisplay</span></span>
2. <span data-ttu-id="8beb1-251">Período</span><span class="sxs-lookup"><span data-stu-id="8beb1-251">Period</span></span>
3. <span data-ttu-id="8beb1-252">SubscriberId</span><span class="sxs-lookup"><span data-stu-id="8beb1-252">SubscriberId</span></span>

<span data-ttu-id="8beb1-253">Una búsqueda de recursos utiliza el método GET y los parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="8beb1-253">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="8beb1-254">Paciente = \<id> paciente</span><span class="sxs-lookup"><span data-stu-id="8beb1-254">Patient = \<patient id></span></span>

<span data-ttu-id="8beb1-255">Vea [http://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) establecer otros detalles en este campo.</span><span class="sxs-lookup"><span data-stu-id="8beb1-255">See [http://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
