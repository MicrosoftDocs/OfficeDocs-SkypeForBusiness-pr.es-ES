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
description: Integración de la EHR de la aplicación pacientes de Microsoft Teams
ms.openlocfilehash: d718f3d3772a08ecfa57e418a4f4fc2e22fe7172
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147703"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="a803e-103">Especificación de la interfaz STU3</span><span class="sxs-lookup"><span data-stu-id="a803e-103">STU3 interface specification</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="a803e-104">Para configurar o volver a configurar un servidor de FHIR para que funcione con la aplicación para pacientes de Microsoft Teams, es necesario comprender a qué datos necesita acceder la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a803e-104">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="a803e-105">El servidor de FHIR debe admitir solicitudes POST con paquetes para los siguientes recursos:</span><span class="sxs-lookup"><span data-stu-id="a803e-105">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="a803e-106">Propio</span><span class="sxs-lookup"><span data-stu-id="a803e-106">Patient</span></span>](#patient)
- [<span data-ttu-id="a803e-107">Observación</span><span class="sxs-lookup"><span data-stu-id="a803e-107">Observation</span></span>](#observation)
- [<span data-ttu-id="a803e-108">Condición</span><span class="sxs-lookup"><span data-stu-id="a803e-108">Condition</span></span>](#condition)
- [<span data-ttu-id="a803e-109">Detect</span><span class="sxs-lookup"><span data-stu-id="a803e-109">Encounter</span></span>](#encounter)
- [<span data-ttu-id="a803e-110">Intolerancia de alergia</span><span class="sxs-lookup"><span data-stu-id="a803e-110">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="a803e-111">Beneficios</span><span class="sxs-lookup"><span data-stu-id="a803e-111">Coverage</span></span>](#coverage)
- <span data-ttu-id="a803e-112">[Declaración de medicación](#medication-request) (reemplaza MedicationOrder en la versión DSTU2 de la PatientsApp)</span><span class="sxs-lookup"><span data-stu-id="a803e-112">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="a803e-113">Ubicación (la información necesaria de este recurso puede estar incluida en encontrarse)</span><span class="sxs-lookup"><span data-stu-id="a803e-113">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="a803e-114">El recurso paciente es el único recurso obligatorio (sin que la aplicación se cargue); Sin embargo, se recomienda que el socio implemente la compatibilidad de todos los recursos mencionados anteriormente según las especificaciones proporcionadas a continuación para obtener la mejor experiencia para el usuario final con la aplicación de pacientes de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a803e-114">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="a803e-115">Las consultas de la aplicación de pacientes de Microsoft Teams para más de un recurso deben publicar un paquete (lote) de solicitudes a la dirección URL del servidor de FHIR.</span><span class="sxs-lookup"><span data-stu-id="a803e-115">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="a803e-116">El servidor debe procesar cada solicitud y devolver un paquete de los recursos coincidentes con cada solicitud.</span><span class="sxs-lookup"><span data-stu-id="a803e-116">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="a803e-117">Para obtener más información y ejemplos, [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction)consulte.</span><span class="sxs-lookup"><span data-stu-id="a803e-117">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="a803e-118">Declaración de capacidad</span><span class="sxs-lookup"><span data-stu-id="a803e-118">Capability Statement</span></span>

<span data-ttu-id="a803e-119">Estos son los campos mínimos obligatorios:</span><span class="sxs-lookup"><span data-stu-id="a803e-119">These are the minimum required fields:</span></span>

1. <span data-ttu-id="a803e-120">DESCANSO</span><span class="sxs-lookup"><span data-stu-id="a803e-120">REST</span></span>
   1. <span data-ttu-id="a803e-121">Modo</span><span class="sxs-lookup"><span data-stu-id="a803e-121">Mode</span></span>
   2. <span data-ttu-id="a803e-122">MOV</span><span class="sxs-lookup"><span data-stu-id="a803e-122">Interaction</span></span>
   3. <span data-ttu-id="a803e-123">Recurso: tipo</span><span class="sxs-lookup"><span data-stu-id="a803e-123">Resource: Type</span></span>
   4. <span data-ttu-id="a803e-124">Seguridad: [extensión para URI de OAuth](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="a803e-124">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="a803e-125">FhirVersion (nuestro código requiere esto para comprender a qué versión debemos dinamizar).</span><span class="sxs-lookup"><span data-stu-id="a803e-125">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="a803e-126">Consulte [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="a803e-126">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="a803e-127">Propio</span><span class="sxs-lookup"><span data-stu-id="a803e-127">Patient</span></span>

<span data-ttu-id="a803e-128">Estos son los campos mínimos obligatorios, que son un subconjunto de los campos de perfil del paciente de Argonaut:</span><span class="sxs-lookup"><span data-stu-id="a803e-128">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

1. <span data-ttu-id="a803e-129">Nombre. dado</span><span class="sxs-lookup"><span data-stu-id="a803e-129">Name.Given</span></span>
2. <span data-ttu-id="a803e-130">Nombre. familia</span><span class="sxs-lookup"><span data-stu-id="a803e-130">Name.Family</span></span>
3. <span data-ttu-id="a803e-131">Hombres</span><span class="sxs-lookup"><span data-stu-id="a803e-131">Gender</span></span>
4. <span data-ttu-id="a803e-132">FechaNacimiento</span><span class="sxs-lookup"><span data-stu-id="a803e-132">BirthDate</span></span>
5. <span data-ttu-id="a803e-133">MRN (identificador)</span><span class="sxs-lookup"><span data-stu-id="a803e-133">MRN (Identifier)</span></span>

<span data-ttu-id="a803e-134">Además de los [campos Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), para una experiencia de usuario excelente, la aplicación de pacientes también puede leer los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="a803e-134">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="a803e-135">Nombre. Use</span><span class="sxs-lookup"><span data-stu-id="a803e-135">Name.Use</span></span>
2. <span data-ttu-id="a803e-136">Nombre. Prefix</span><span class="sxs-lookup"><span data-stu-id="a803e-136">Name.Prefix</span></span>
3. <span data-ttu-id="a803e-137">[GeneralPractitioner]-la referencia de GeneralPractitioner debe incluirse en el recurso patient (solo campo de mostrar)</span><span class="sxs-lookup"><span data-stu-id="a803e-137">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="a803e-138">Una búsqueda de recursos usa el método POST en/patient/_search y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="a803e-138">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="a803e-139">identificar</span><span class="sxs-lookup"><span data-stu-id="a803e-139">id</span></span>
2. <span data-ttu-id="a803e-140">Family = (busca todos los pacientes cuyo nombre contenga el valor)</span><span class="sxs-lookup"><span data-stu-id="a803e-140">family=(searches for all patients whose family name contains the value)</span></span>
3. <span data-ttu-id="a803e-141">proporcionado =\<substring></span><span class="sxs-lookup"><span data-stu-id="a803e-141">given=\<substring></span></span>
4. <span data-ttu-id="a803e-142">FechaNacimiento = (coincidencia exacta)</span><span class="sxs-lookup"><span data-stu-id="a803e-142">birthdate=(exact match)</span></span>
5. <span data-ttu-id="a803e-143">Gender = (los valores son uno de los sexos administrativos)</span><span class="sxs-lookup"><span data-stu-id="a803e-143">gender=(values being one of the administrative-gender)</span></span>
6. <span data-ttu-id="a803e-144">\_contar (número máximo de resultados que se deben devolver)</span><span class="sxs-lookup"><span data-stu-id="a803e-144">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="a803e-145">La respuesta debe contener el recuento total de registros devueltos como resultado de la \_búsqueda y el recuento que usará el PatientsApp para limitar el número de registros devueltos.</span><span class="sxs-lookup"><span data-stu-id="a803e-145">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="a803e-146">Identifier =\<MRN></span><span class="sxs-lookup"><span data-stu-id="a803e-146">identifier=\<mrn></span></span>

<span data-ttu-id="a803e-147">El objetivo es poder buscar y filtrar a un paciente por lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a803e-147">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="a803e-148">ID: es el identificador de recurso que tiene cada recurso en FHIR.</span><span class="sxs-lookup"><span data-stu-id="a803e-148">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="a803e-149">MRN: este es el identificador real del paciente que sabría el personal clínico.</span><span class="sxs-lookup"><span data-stu-id="a803e-149">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="a803e-150">Entendemos que este MRN se basa en el tipo de identificador dentro del recurso Identifier en FHIR.</span><span class="sxs-lookup"><span data-stu-id="a803e-150">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="a803e-151">Nombre</span><span class="sxs-lookup"><span data-stu-id="a803e-151">Name</span></span>
- <span data-ttu-id="a803e-152">FechaNacimiento</span><span class="sxs-lookup"><span data-stu-id="a803e-152">Birthdate</span></span>

<span data-ttu-id="a803e-153">Vea el ejemplo siguiente de la llamada:</span><span class="sxs-lookup"><span data-stu-id="a803e-153">See the following example of the call:</span></span>

* * *

    <span data-ttu-id="a803e-154">Solicitud: publique <fhir-Server>/patient/_search cuerpo de solicitud: proporcionado = Ruth&Family = Black</span><span class="sxs-lookup"><span data-stu-id="a803e-154">Request: POST <fhir-server>/Patient/_search Request Body: given=ruth&family=black</span></span>
    
    <span data-ttu-id="a803e-155">Respuesta: {"resourceType": "bundle", "ID": "<paquete-ID>", "meta": {"14T23:45.052 + 00:00"}, "tipo": "searchset", "total": 1, "link": [{"Relation": "self", "URL": <fhir-Server>/patient/_search "}]," Entry ": [{" fullUrl ": <fhir-Server>/patient/<ID de paciente>", "recurso": {"resourceType": "patient", "ID": "<patient-ID>", "meta": {"versionId": "1", "lastUpdated": "2017-10-18T18:32:37.000 + 00:00"}, "texto": {"status": "generated", "div": "</span><span class="sxs-lookup"><span data-stu-id="a803e-155">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "meta": { "lastUpdated": "2019-01-14T23:44:45.052+00:00" }, "type": "searchset", "total": 1, "link": [ { "relation": "self", "url": <fhir-server>/Patient/_search" } ], "entry": [ { "fullUrl": <fhir-server>/Patient/<patient-id>", "resource": { "resourceType": "Patient", "id": "<patient-id>", "meta": { "versionId": "1", "lastUpdated": "2017-10-18T18:32:37.000+00:00" }, "text": { "status": "generated", "div": "</span></span><div><span data-ttu-id="a803e-156">\n</span><span class="sxs-lookup"><span data-stu-id="a803e-156">\n</span></span>        <p><span data-ttu-id="a803e-157">Ruth negro</span><span class="sxs-lookup"><span data-stu-id="a803e-157">Ruth Black</span></span></p><span data-ttu-id="a803e-158">\n</span><span class="sxs-lookup"><span data-stu-id="a803e-158">\n</span></span>      </div><span data-ttu-id="a803e-159">"}," identificador ": [{" use ":" normal "," tipo ": {" codificación ": [{" System "https://hl7.org/fhir/v2/0203:" "," código ":" Mr "," display ":" número de registro médico "," userSelected ": falso}]," texto ":" número de registro médico "}," sistema ":http://hospital.smarthealthit.org" "," nombre ":". ","}], "activo": verdadero, "nombre": [{"use": "funcionario", "unidad": "negro", "dado": ["Ruth", "C". 1234567</span><span class="sxs-lookup"><span data-stu-id="a803e-159">" }, "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "https://hl7.org/fhir/v2/0203", "code": "MR", "display": "Medical record number", "userSelected": false } ], "text": "Medical record number" }, "system": "http://hospital.smarthealthit.org", "value": "1234567" } ], "active": true, "name": [ { "use": "official", "family": "Black", "given": [ "Ruth", "C."</span></span>
    <span data-ttu-id="a803e-160">]}], "Telecom": [{"System": "Phone", "Value": "800-599-2739", "uso": "Home"}, {"System": "Phone", "Value": "[re800-808-7785", "use": "Mobile"}, "", "": ".": "mujer", "FechaNacimiento": "1951-08-23", "dirección": [{"use": "casa", "línea": ["26 South RdApt 22"], "ciudad": "Sapulpa", "estado": "correcto", "CódigoPostal": "74066", "país": "USA"}]}, "Buscar": {"MODE": "match"}}]}</span><span class="sxs-lookup"><span data-stu-id="a803e-160">] } ], "telecom": [ { "system": "phone", "value": "800-599-2739", "use": "home" }, { "system": "phone", "value": "800-808-7785", "use": "mobile" }, { "system": "email", "value": "ruth.black@example.com" } ], "gender": "female", "birthDate": "1951-08-23", "address": [ { "use": "home", "line": [ "26 South RdApt 22" ], "city": "Sapulpa", "state": "OK", "postalCode": "74066", "country": "USA" } ] }, "search": { "mode": "match" } } ] }</span></span>

* * *

    <span data-ttu-id="a803e-161">Solicitud: Obtén <fhir-Server>/patient/<ID de paciente></span><span class="sxs-lookup"><span data-stu-id="a803e-161">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="a803e-162">Respuesta: {"resourceType": "patient", "ID": "<patient-ID>", "identificador": [{"use": "normal", "type": {"codificación": [{"sistema": "https://hl7.org/fhir/v2/0203", "código": "Mr",}], "texto": "número de registro médico"}, "valor": "1234567"}], "nombre": [{"use": "oficial", "familia": ",". "</span><span class="sxs-lookup"><span data-stu-id="a803e-162">Response: { "resourceType": "Patient", "id": "<patient-id>", "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "https://hl7.org/fhir/v2/0203", "code": "MR", } ], "text": "Medical record number" }, "value": "1234567" } ], "name": [ { "use": "official", "family": "Adams", "given": [ "Daniel", "X."</span></span> <span data-ttu-id="a803e-163">]}], "sexo": "hombre", "FechaNacimiento": "1925-12-23",}</span><span class="sxs-lookup"><span data-stu-id="a803e-163">] } ], "gender": "male", "birthDate": "1925-12-23", }</span></span>

* * *

<span data-ttu-id="a803e-164">Consulte [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="a803e-164">See [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="a803e-165">Observación</span><span class="sxs-lookup"><span data-stu-id="a803e-165">Observation</span></span>

<span data-ttu-id="a803e-166">Estos son los campos mínimos obligatorios, que son un subconjunto del [Perfil de signos vitales Argonaut](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span><span class="sxs-lookup"><span data-stu-id="a803e-166">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

1. <span data-ttu-id="a803e-167">Vigencia (fecha o hora)</span><span class="sxs-lookup"><span data-stu-id="a803e-167">Effective (date time or period)</span></span>
2. <span data-ttu-id="a803e-168">Code. Coding. Code</span><span class="sxs-lookup"><span data-stu-id="a803e-168">Code.Coding.Code</span></span>
3. <span data-ttu-id="a803e-169">ValueQuantity. Value</span><span class="sxs-lookup"><span data-stu-id="a803e-169">ValueQuantity.Value</span></span>

<span data-ttu-id="a803e-170">Además de los campos Argonaut, para una experiencia de usuario excelente, la aplicación de pacientes también puede leer los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="a803e-170">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="a803e-171">Code. Coding. display</span><span class="sxs-lookup"><span data-stu-id="a803e-171">Code.Coding.Display</span></span>
2. <span data-ttu-id="a803e-172">Unidad ValueQuantity.</span><span class="sxs-lookup"><span data-stu-id="a803e-172">ValueQuantity.Unit</span></span>

<span data-ttu-id="a803e-173">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="a803e-173">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="a803e-174">paciente =\<ID de paciente></span><span class="sxs-lookup"><span data-stu-id="a803e-174">patient=\<patient id></span></span>
2. <span data-ttu-id="a803e-175">_sort =-Date</span><span class="sxs-lookup"><span data-stu-id="a803e-175">_sort=-date</span></span>
3. <span data-ttu-id="a803e-176">Categoría (consultaremos "las señales de categoría = vitales") para recuperar la lista de constantes vitales.</span><span class="sxs-lookup"><span data-stu-id="a803e-176">category (we will query for “category=vital-signs”) to retrieve the list of vital signs.</span></span>

<span data-ttu-id="a803e-177">Consulte este ejemplo de la llamada:</span><span class="sxs-lookup"><span data-stu-id="a803e-177">Refer to this example of the call:</span></span>

* * *

    <span data-ttu-id="a803e-178">Solicitud: obtener <fhir-Server>/Observation? patient =<patient-ID>&Category = Vital-Signs</span><span class="sxs-lookup"><span data-stu-id="a803e-178">Request: GET <fhir-server>/Observation?patient=<patient-id>&category=vital-signs</span></span>
    
    <span data-ttu-id="a803e-179">Respuesta: {"resourceType": "bundle", "ID": "<paquete-ID>", "type": "searchset", "total": 20, "Entry": [{"Resource": {"resourceType": "observación", "ID": "<Resource-ID>", "Category": [{"Code": [{"System":https://hl7.org/fhir/observation-category"", "", "in código": {"codificación": [{"System":http://loinc.org"", "code": "8867-4", "display": "heart_rate"}]}, "effectiveDateTime": "2009-04-08T00:00:00-06:00", "valueQuantity": {"valor": 72,0, "unidad": "{pulsaciones}/min.", "sistema": "http://unitsofmeasure.org",}}},.</span><span class="sxs-lookup"><span data-stu-id="a803e-179">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": [ { "coding": [ { "system": "https://hl7.org/fhir/observation-category", "code": "vital-signs" } ], } ], "code": { "coding": [ { "system": "http://loinc.org", "code": "8867-4", "display": "heart_rate" } ] }, "effectiveDateTime": "2009-04-08T00:00:00-06:00", "valueQuantity": { "value": 72.0, "unit": "{beats}/min", "system": "http://unitsofmeasure.org", } } }, .</span></span>
        <span data-ttu-id="a803e-180">.</span><span class="sxs-lookup"><span data-stu-id="a803e-180">.</span></span>
        <span data-ttu-id="a803e-181">.</span><span class="sxs-lookup"><span data-stu-id="a803e-181">.</span></span>
      <span data-ttu-id="a803e-182">] }</span><span class="sxs-lookup"><span data-stu-id="a803e-182">] }</span></span>

* * *

<span data-ttu-id="a803e-183">Consulte [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="a803e-183">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="a803e-184">Condición</span><span class="sxs-lookup"><span data-stu-id="a803e-184">Condition</span></span>

<span data-ttu-id="a803e-185">Estos son los campos mínimos obligatorios, que son un subconjunto del [Perfil de condición Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span><span class="sxs-lookup"><span data-stu-id="a803e-185">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

1. <span data-ttu-id="a803e-186">Code. Coding [0]. Aparecen</span><span class="sxs-lookup"><span data-stu-id="a803e-186">Code.Coding[0].Display</span></span>

<span data-ttu-id="a803e-187">Además de los campos Argonaut, para una experiencia de usuario excelente, la aplicación de pacientes también puede leer los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="a803e-187">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="a803e-188">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="a803e-188">AssertedDate</span></span>
2. <span data-ttu-id="a803e-189">Gravedad</span><span class="sxs-lookup"><span data-stu-id="a803e-189">Severity</span></span>

<span data-ttu-id="a803e-190">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="a803e-190">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="a803e-191">paciente =\<ID de paciente></span><span class="sxs-lookup"><span data-stu-id="a803e-191">patient=\<patient id></span></span>
2. <span data-ttu-id="a803e-192">_count =\<resultados máximos></span><span class="sxs-lookup"><span data-stu-id="a803e-192">_count=\<max results></span></span>

<span data-ttu-id="a803e-193">Consulte el siguiente ejemplo de esta llamada:</span><span class="sxs-lookup"><span data-stu-id="a803e-193">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="a803e-194">Solicitud: obtener <fhir-Server>/Condition? patient =<ID de paciente>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="a803e-194">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="a803e-195">Respuesta: {"resourceType": "bundle", "ID": "paquete de <-ID>", "type": "searchset", "total": 2, "Entry": [{"Resource": {"resourceType": "Condition", "ID": "", "",> <"" "," "http://snomed.info/sct", "código": "185903001", "display": "necesita la vacuna de la influenza",}]}, "gravedad": {"codificación": [{"System": "http://snomed.info/sct", "código": "24484000", "display": "assertedDate"]}, "" ":" 2018-04-04 "}},.</span><span class="sxs-lookup"><span data-stu-id="a803e-195">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 2, "entry": [ { "resource": { "resourceType": "Condition", "id": "<resource-id>", "code": { "coding": [ { "system": "http://snomed.info/sct", "code": "185903001", "display": "Needs influenza immunization", } ] }, "severity": { "coding": [ { "system": "http://snomed.info/sct", "code": "24484000", "display": "Severe" } ] }, "assertedDate": "2018-04-04" } }, .</span></span>
        <span data-ttu-id="a803e-196">.</span><span class="sxs-lookup"><span data-stu-id="a803e-196">.</span></span>
        <span data-ttu-id="a803e-197">.</span><span class="sxs-lookup"><span data-stu-id="a803e-197">.</span></span>
      <span data-ttu-id="a803e-198">] }</span><span class="sxs-lookup"><span data-stu-id="a803e-198">] }</span></span>

* * *
<span data-ttu-id="a803e-199">Consulte [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="a803e-199">See [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="a803e-200">Detect</span><span class="sxs-lookup"><span data-stu-id="a803e-200">Encounter</span></span>

<span data-ttu-id="a803e-201">Estos son los campos mínimos obligatorios, que son un subconjunto del [núcleo de Estados Unidos](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) y el perfil "debe tener campos".</span><span class="sxs-lookup"><span data-stu-id="a803e-201">These are the minimum required fields, which are a subset of the [US Core Encounter profile](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) “must have” fields).</span></span>

1. <span data-ttu-id="a803e-202">Statu</span><span class="sxs-lookup"><span data-stu-id="a803e-202">Status</span></span>
2. <span data-ttu-id="a803e-203">Escriba [0]. Codificación [0]. Aparecen</span><span class="sxs-lookup"><span data-stu-id="a803e-203">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="a803e-204">Además, los siguientes campos de la parte central de EE. UU. se encuentran en los campos "debe ser compatible" del perfil:</span><span class="sxs-lookup"><span data-stu-id="a803e-204">In addition, the following fields from US Core Encounter profile’s “must support” fields:</span></span>

1. <span data-ttu-id="a803e-205">Start period</span><span class="sxs-lookup"><span data-stu-id="a803e-205">Period.Start</span></span>
2. <span data-ttu-id="a803e-206">Ubicación [0]. Location. display</span><span class="sxs-lookup"><span data-stu-id="a803e-206">Location[0].Location.Display</span></span>

<span data-ttu-id="a803e-207">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="a803e-207">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="a803e-208">paciente =\<ID de paciente></span><span class="sxs-lookup"><span data-stu-id="a803e-208">patient=\<patient id></span></span>
2. <span data-ttu-id="a803e-209">_sort: DESC =\<campo ex.</span><span class="sxs-lookup"><span data-stu-id="a803e-209">_sort:desc=\<field ex.</span></span> <span data-ttu-id="a803e-210">> de fecha</span><span class="sxs-lookup"><span data-stu-id="a803e-210">date></span></span>
3. <span data-ttu-id="a803e-211">_count =\<resultados máximos></span><span class="sxs-lookup"><span data-stu-id="a803e-211">_count=\<max results></span></span>

<span data-ttu-id="a803e-212">El objetivo es poder recuperar el último lugar conocido del paciente.</span><span class="sxs-lookup"><span data-stu-id="a803e-212">The goal is to be able to retrieve the patient’s last known location.</span></span> <span data-ttu-id="a803e-213">Cada uno de ellos hace referencia a un recurso de ubicación.</span><span class="sxs-lookup"><span data-stu-id="a803e-213">Each encounter references a location resource.</span></span> <span data-ttu-id="a803e-214">La referencia también incluirá el campo de visualización de la ubicación.</span><span class="sxs-lookup"><span data-stu-id="a803e-214">The reference shall also include the location’s display field.</span></span>

<span data-ttu-id="a803e-215">Consulte [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="a803e-215">See [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="a803e-216">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="a803e-216">AllergyIntolerance</span></span>

<span data-ttu-id="a803e-217">Estos son los campos mínimos obligatorios, que son un subconjunto del perfil de [AllergyIntolerance de Argonaut](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) :</span><span class="sxs-lookup"><span data-stu-id="a803e-217">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

1. <span data-ttu-id="a803e-218">Code. Text</span><span class="sxs-lookup"><span data-stu-id="a803e-218">Code.Text</span></span>
2. <span data-ttu-id="a803e-219">Code. Coding [0]. Aparecen</span><span class="sxs-lookup"><span data-stu-id="a803e-219">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="a803e-220">ClinicalStatus/VerificationStatus (hemos leído ambas)</span><span class="sxs-lookup"><span data-stu-id="a803e-220">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="a803e-221">Además de los campos Argonaut, para una experiencia de usuario excelente, la aplicación de pacientes también puede leer el siguiente campo:</span><span class="sxs-lookup"><span data-stu-id="a803e-221">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

1. <span data-ttu-id="a803e-222">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="a803e-222">AssertedDate</span></span>
2. <span data-ttu-id="a803e-223">Nota. Text</span><span class="sxs-lookup"><span data-stu-id="a803e-223">Note.Text</span></span>
3. <span data-ttu-id="a803e-224">Ataque</span><span class="sxs-lookup"><span data-stu-id="a803e-224">Reaction</span></span>
    1. <span data-ttu-id="a803e-225">Sustancia (un elemento de codificación)</span><span class="sxs-lookup"><span data-stu-id="a803e-225">Substance (one coding element)</span></span>
    2. <span data-ttu-id="a803e-226">Manifiesto (un elemento de codificación)</span><span class="sxs-lookup"><span data-stu-id="a803e-226">Manifestation (one coding element)</span></span>

<span data-ttu-id="a803e-227">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="a803e-227">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="a803e-228">Paciente = \<ID de paciente></span><span class="sxs-lookup"><span data-stu-id="a803e-228">Patient =  \<patient id></span></span>

<span data-ttu-id="a803e-229">Vea el ejemplo siguiente de la llamada:</span><span class="sxs-lookup"><span data-stu-id="a803e-229">See the following example of the call:</span></span> 

* * *

    <span data-ttu-id="a803e-230">Solicitud: obtener <fhir-Server>/AllergyIntolerance? patient =<ID de paciente></span><span class="sxs-lookup"><span data-stu-id="a803e-230">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="a803e-231">Respuesta: {"resourceType": "bundle", "ID": "<paquete-ID>", "tipo": "searchset", "total": 1, "Entry": [{"Resource": {"resourceType": "AllergyIntolerance", "ID": "<Resource-ID>", "clinicalStatus": "Active", "verificationStatus": "confirmated", "Code": {"Coding": [{"System"http://rxnav.nlm.nih.gov/REST/Ndfrt: "", "Code": "N0000175503", "display": "sulfonamide antigérmenas",}], "Text": "sulfonamide ANT ibacterial "}," assertedDate ":" 2018-01-01T00:00:00-07:00 "," reacción ": [{" manifestity ": [{" código ": [{" System "http://snomed.info/sct:" "," Code ":" 271807003 "," display ":" Skin rash = ",}] =" Text ":" Skin rash "}],}]}}]}</span><span class="sxs-lookup"><span data-stu-id="a803e-231">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "clinicalStatus": "active",         "verificationStatus": "confirmed",         "code": {           "coding": [             {               "system": "http://rxnav.nlm.nih.gov/REST/Ndfrt",               "code": "N0000175503",               "display": "sulfonamide antibacterial",             }           ],           "text": "sulfonamide antibacterial"         },         "assertedDate": "2018-01-01T00:00:00-07:00",         "reaction": [           {             "manifestation": [               {                 "coding": [                   {                     "system": "http://snomed.info/sct",                     "code": "271807003",                     "display": "skin rash",                   }                 ],                 "text": "skin rash"               }             ],           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="a803e-232">Consulte [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="a803e-232">See [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="a803e-233">Solicitud de medicación</span><span class="sxs-lookup"><span data-stu-id="a803e-233">Medication Request</span></span>

<span data-ttu-id="a803e-234">Estos son los campos mínimos obligatorios, que son un subconjunto del [Perfil de solicitud de medicación del núcleo de Estados Unidos](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span><span class="sxs-lookup"><span data-stu-id="a803e-234">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

1. <span data-ttu-id="a803e-235">Medicación. display (si Ref)</span><span class="sxs-lookup"><span data-stu-id="a803e-235">Medication.Display (if Reference)</span></span>
2. <span data-ttu-id="a803e-236">Medicación. Text (si CodableConcept)</span><span class="sxs-lookup"><span data-stu-id="a803e-236">Medication.Text (if CodableConcept)</span></span>
3. <span data-ttu-id="a803e-237">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="a803e-237">AuthoredOn</span></span>
4. <span data-ttu-id="a803e-238">Solicitante. Agent. display</span><span class="sxs-lookup"><span data-stu-id="a803e-238">Requester.Agent.Display</span></span>

<span data-ttu-id="a803e-239">Además de los campos básicos de Estados Unidos, para disfrutar de una experiencia de usuario excelente, la aplicación de pacientes también puede leer los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="a803e-239">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="a803e-240">DosageInstruction[..]. Facturas</span><span class="sxs-lookup"><span data-stu-id="a803e-240">DosageInstruction[..].Text</span></span>
2. <span data-ttu-id="a803e-241">Facturas</span><span class="sxs-lookup"><span data-stu-id="a803e-241">Text</span></span>

<span data-ttu-id="a803e-242">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="a803e-242">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="a803e-243">paciente =\<ID de paciente></span><span class="sxs-lookup"><span data-stu-id="a803e-243">patient=\<patient id></span></span>
2. <span data-ttu-id="a803e-244">_count =\<resultados máximos></span><span class="sxs-lookup"><span data-stu-id="a803e-244">_count=\<max results></span></span>

<span data-ttu-id="a803e-245">Consulte [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="a803e-245">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="a803e-246">Beneficios</span><span class="sxs-lookup"><span data-stu-id="a803e-246">Coverage</span></span>

<span data-ttu-id="a803e-247">Estos son los campos mínimos obligatorios, no incluidos en los perfiles de los Estados Unidos Core o Argonaut:</span><span class="sxs-lookup"><span data-stu-id="a803e-247">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="a803e-248">Agrupar, al menos un elemento con</span><span class="sxs-lookup"><span data-stu-id="a803e-248">Grouping, at least one element with</span></span>
    1. <span data-ttu-id="a803e-249">GroupDisplay</span><span class="sxs-lookup"><span data-stu-id="a803e-249">GroupDisplay</span></span>
    2. <span data-ttu-id="a803e-250">PlanDisplay</span><span class="sxs-lookup"><span data-stu-id="a803e-250">PlanDisplay</span></span>
2. <span data-ttu-id="a803e-251">Período</span><span class="sxs-lookup"><span data-stu-id="a803e-251">Period</span></span>
3. <span data-ttu-id="a803e-252">SubscriberId</span><span class="sxs-lookup"><span data-stu-id="a803e-252">SubscriberId</span></span>

<span data-ttu-id="a803e-253">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="a803e-253">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="a803e-254">Paciente = \<ID de paciente></span><span class="sxs-lookup"><span data-stu-id="a803e-254">Patient = \<patient id></span></span>

<span data-ttu-id="a803e-255">Consulte [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="a803e-255">See [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
