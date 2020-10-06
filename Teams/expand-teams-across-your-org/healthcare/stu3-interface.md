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
ms.openlocfilehash: 1c5e19ff28c67641ac5b643e1944bf2435fbf164
ms.sourcegitcommit: 3b54a56ec1fe4366580621e19cdbb6a833a01161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2020
ms.locfileid: "48361350"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="cb5cd-103">Especificación de la interfaz STU3</span><span class="sxs-lookup"><span data-stu-id="cb5cd-103">STU3 interface specification</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cb5cd-104">**A partir del 15 de octubre de 2020, la aplicación para pacientes quedará obsoleta y los usuarios ya no podrán instalarla desde la tienda de aplicaciones de Teams. Le recomendamos que empiece a usar la [aplicación lists](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) en Teams hoy.**</span><span class="sxs-lookup"><span data-stu-id="cb5cd-104">**Effective October 15, 2020, the Patients app will be deprecated and users will no longer be able to install it from the Teams app store. We encourage you to start using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams today.**</span></span>
>
><span data-ttu-id="cb5cd-105">Los datos de la aplicación patients se almacenan en el buzón de grupo del grupo Office 365 que respalda al equipo.</span><span class="sxs-lookup"><span data-stu-id="cb5cd-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="cb5cd-106">Cuando se retira la aplicación de pacientes, todos los datos asociados con ella se conservarán en este grupo, pero ya no se podrá obtener acceso a ellas a través de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="cb5cd-106">When the Patients app is retired, all data associated with it will be retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="cb5cd-107">Los usuarios actuales pueden volver a crear sus listas con la [aplicación listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span><span class="sxs-lookup"><span data-stu-id="cb5cd-107">Current users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="cb5cd-108">La [aplicación listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) está preinstalada para todos los usuarios de Teams y está disponible como una pestaña en todos los equipos y canales.</span><span class="sxs-lookup"><span data-stu-id="cb5cd-108">The [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) is pre-installed for all Teams users and is available as a tab in every team and channel.</span></span> <span data-ttu-id="cb5cd-109">Con las listas, los equipos de cuidados pueden crear listas de pacientes con la plantilla de pacientes integrados, desde cero o importando datos a Excel.</span><span class="sxs-lookup"><span data-stu-id="cb5cd-109">With Lists, care teams can create patient lists using the built-in Patients template, from scratch, or by importing data to Excel.</span></span> <span data-ttu-id="cb5cd-110">Para obtener más información sobre cómo administrar la aplicación listas de su organización, vea [administrar la aplicación listas](../../manage-lists-app.md).</span><span class="sxs-lookup"><span data-stu-id="cb5cd-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="cb5cd-111">Para configurar o volver a configurar un servidor de FHIR para que funcione con la aplicación para pacientes de Microsoft Teams, es necesario comprender a qué datos necesita acceder la aplicación.</span><span class="sxs-lookup"><span data-stu-id="cb5cd-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="cb5cd-112">El servidor de FHIR debe admitir solicitudes POST con paquetes para los siguientes recursos:</span><span class="sxs-lookup"><span data-stu-id="cb5cd-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="cb5cd-113">Propio</span><span class="sxs-lookup"><span data-stu-id="cb5cd-113">Patient</span></span>](#patient)
- [<span data-ttu-id="cb5cd-114">Observación</span><span class="sxs-lookup"><span data-stu-id="cb5cd-114">Observation</span></span>](#observation)
- [<span data-ttu-id="cb5cd-115">Condición</span><span class="sxs-lookup"><span data-stu-id="cb5cd-115">Condition</span></span>](#condition)
- [<span data-ttu-id="cb5cd-116">Detect</span><span class="sxs-lookup"><span data-stu-id="cb5cd-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="cb5cd-117">Intolerancia de alergia</span><span class="sxs-lookup"><span data-stu-id="cb5cd-117">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="cb5cd-118">Beneficios</span><span class="sxs-lookup"><span data-stu-id="cb5cd-118">Coverage</span></span>](#coverage)
- <span data-ttu-id="cb5cd-119">[Declaración de medicación](#medication-request) (reemplaza MedicationOrder en la versión DSTU2 de la PatientsApp)</span><span class="sxs-lookup"><span data-stu-id="cb5cd-119">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="cb5cd-120">Ubicación (la información necesaria de este recurso puede estar incluida en encontrarse)</span><span class="sxs-lookup"><span data-stu-id="cb5cd-120">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="cb5cd-121">El recurso paciente es el único recurso obligatorio (sin que la aplicación se cargue); Sin embargo, se recomienda que el socio implemente la compatibilidad de todos los recursos mencionados anteriormente según las especificaciones proporcionadas a continuación para obtener la mejor experiencia para el usuario final con la aplicación de pacientes de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="cb5cd-121">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="cb5cd-122">Las consultas de la aplicación de pacientes de Microsoft Teams para más de un recurso deben publicar un paquete (lote) de solicitudes a la dirección URL del servidor de FHIR.</span><span class="sxs-lookup"><span data-stu-id="cb5cd-122">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="cb5cd-123">El servidor debe procesar cada solicitud y devolver un paquete de los recursos coincidentes con cada solicitud.</span><span class="sxs-lookup"><span data-stu-id="cb5cd-123">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="cb5cd-124">Para obtener más información y ejemplos, consulte [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) .</span><span class="sxs-lookup"><span data-stu-id="cb5cd-124">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="cb5cd-125">Declaración de capacidad</span><span class="sxs-lookup"><span data-stu-id="cb5cd-125">Capability Statement</span></span>

<span data-ttu-id="cb5cd-126">Estos son los campos mínimos obligatorios:</span><span class="sxs-lookup"><span data-stu-id="cb5cd-126">These are the minimum required fields:</span></span>

1. <span data-ttu-id="cb5cd-127">DESCANSO</span><span class="sxs-lookup"><span data-stu-id="cb5cd-127">REST</span></span>
   1. <span data-ttu-id="cb5cd-128">Modo</span><span class="sxs-lookup"><span data-stu-id="cb5cd-128">Mode</span></span>
   2. <span data-ttu-id="cb5cd-129">MOV</span><span class="sxs-lookup"><span data-stu-id="cb5cd-129">Interaction</span></span>
   3. <span data-ttu-id="cb5cd-130">Recurso: tipo</span><span class="sxs-lookup"><span data-stu-id="cb5cd-130">Resource: Type</span></span>
   4. <span data-ttu-id="cb5cd-131">Seguridad: [extensión para URI de OAuth](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="cb5cd-131">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="cb5cd-132">FhirVersion (nuestro código requiere esto para comprender a qué versión debemos dinamizar).</span><span class="sxs-lookup"><span data-stu-id="cb5cd-132">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="cb5cd-133">Consulte [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="cb5cd-133">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="cb5cd-134">Propio</span><span class="sxs-lookup"><span data-stu-id="cb5cd-134">Patient</span></span>

<span data-ttu-id="cb5cd-135">Estos son los campos mínimos obligatorios, que son un subconjunto de los campos de perfil del paciente de Argonaut:</span><span class="sxs-lookup"><span data-stu-id="cb5cd-135">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

1. <span data-ttu-id="cb5cd-136">Nombre. dado</span><span class="sxs-lookup"><span data-stu-id="cb5cd-136">Name.Given</span></span>
2. <span data-ttu-id="cb5cd-137">Nombre. familia</span><span class="sxs-lookup"><span data-stu-id="cb5cd-137">Name.Family</span></span>
3. <span data-ttu-id="cb5cd-138">Hombres</span><span class="sxs-lookup"><span data-stu-id="cb5cd-138">Gender</span></span>
4. <span data-ttu-id="cb5cd-139">FechaNacimiento</span><span class="sxs-lookup"><span data-stu-id="cb5cd-139">BirthDate</span></span>
5. <span data-ttu-id="cb5cd-140">MRN (identificador)</span><span class="sxs-lookup"><span data-stu-id="cb5cd-140">MRN (Identifier)</span></span>

<span data-ttu-id="cb5cd-141">Además de los [campos Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), para una experiencia de usuario excelente, la aplicación de pacientes también puede leer los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="cb5cd-141">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="cb5cd-142">Nombre. Use</span><span class="sxs-lookup"><span data-stu-id="cb5cd-142">Name.Use</span></span>
2. <span data-ttu-id="cb5cd-143">Nombre. Prefix</span><span class="sxs-lookup"><span data-stu-id="cb5cd-143">Name.Prefix</span></span>
3. <span data-ttu-id="cb5cd-144">[GeneralPractitioner]-la referencia de GeneralPractitioner debe incluirse en el recurso patient (solo campo de mostrar)</span><span class="sxs-lookup"><span data-stu-id="cb5cd-144">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="cb5cd-145">Una búsqueda de recursos usa el método POST en/patient/_search y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="cb5cd-145">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="cb5cd-146">identificar</span><span class="sxs-lookup"><span data-stu-id="cb5cd-146">id</span></span>
2. <span data-ttu-id="cb5cd-147">Family = (busca todos los pacientes cuyo nombre contenga el valor)</span><span class="sxs-lookup"><span data-stu-id="cb5cd-147">family=(searches for all patients whose family name contains the value)</span></span>
3. <span data-ttu-id="cb5cd-148">dado =\<substring></span><span class="sxs-lookup"><span data-stu-id="cb5cd-148">given=\<substring></span></span>
4. <span data-ttu-id="cb5cd-149">FechaNacimiento = (coincidencia exacta)</span><span class="sxs-lookup"><span data-stu-id="cb5cd-149">birthdate=(exact match)</span></span>
5. <span data-ttu-id="cb5cd-150">Gender = (los valores son uno de los sexos administrativos)</span><span class="sxs-lookup"><span data-stu-id="cb5cd-150">gender=(values being one of the administrative-gender)</span></span>
6. <span data-ttu-id="cb5cd-151">\_contar (número máximo de resultados que se deben devolver)</span><span class="sxs-lookup"><span data-stu-id="cb5cd-151">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="cb5cd-152">La respuesta debe contener el recuento total de registros devueltos como resultado de la búsqueda y el \_ recuento que usará el PatientsApp para limitar el número de registros devueltos.</span><span class="sxs-lookup"><span data-stu-id="cb5cd-152">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="cb5cd-153">Identifier =\<mrn></span><span class="sxs-lookup"><span data-stu-id="cb5cd-153">identifier=\<mrn></span></span>

<span data-ttu-id="cb5cd-154">El objetivo es poder buscar y filtrar a un paciente por lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cb5cd-154">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="cb5cd-155">ID: es el identificador de recurso que tiene cada recurso en FHIR.</span><span class="sxs-lookup"><span data-stu-id="cb5cd-155">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="cb5cd-156">MRN: este es el identificador real del paciente que sabría el personal clínico.</span><span class="sxs-lookup"><span data-stu-id="cb5cd-156">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="cb5cd-157">Entendemos que este MRN se basa en el tipo de identificador dentro del recurso Identifier en FHIR.</span><span class="sxs-lookup"><span data-stu-id="cb5cd-157">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="cb5cd-158">Nombre</span><span class="sxs-lookup"><span data-stu-id="cb5cd-158">Name</span></span>
- <span data-ttu-id="cb5cd-159">FechaNacimiento</span><span class="sxs-lookup"><span data-stu-id="cb5cd-159">Birthdate</span></span>

<span data-ttu-id="cb5cd-160">Vea el ejemplo siguiente de la llamada:</span><span class="sxs-lookup"><span data-stu-id="cb5cd-160">See the following example of the call:</span></span>

* * *

    <span data-ttu-id="cb5cd-161">Solicitud: publique <fhir-Server>/patient/_search cuerpo de solicitud: proporcionado = Ruth&Family = Black</span><span class="sxs-lookup"><span data-stu-id="cb5cd-161">Request: POST <fhir-server>/Patient/_search Request Body: given=ruth&family=black</span></span>
    
    <span data-ttu-id="cb5cd-162">Respuesta: {"resourceType": "bundle", "ID": "<paquete-ID>", "meta": {"14T23:45.052 + 00:00"}, "tipo": "searchset", "total": 1, "link": [{"Relation": "self", "URL": <fhir-Server>/patient/_search "}]," Entry ": [{" fullUrl ": <fhir-Server>/patient/<ID de paciente>", "recurso": {"resourceType": "patient", "ID": "<patient-ID>", "meta": {"versionId": "1", "lastUpdated": "2017-10-18T18:32:37.000 + 00:00"}, "texto": {"status": "generated", "div": "</span><span class="sxs-lookup"><span data-stu-id="cb5cd-162">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "meta": { "lastUpdated": "2019-01-14T23:44:45.052+00:00" }, "type": "searchset", "total": 1, "link": [ { "relation": "self", "url": <fhir-server>/Patient/_search" } ], "entry": [ { "fullUrl": <fhir-server>/Patient/<patient-id>", "resource": { "resourceType": "Patient", "id": "<patient-id>", "meta": { "versionId": "1", "lastUpdated": "2017-10-18T18:32:37.000+00:00" }, "text": { "status": "generated", "div": "</span></span><div><span data-ttu-id="cb5cd-163">\n</span><span class="sxs-lookup"><span data-stu-id="cb5cd-163">\n</span></span>        <p><span data-ttu-id="cb5cd-164">Ruth negro</span><span class="sxs-lookup"><span data-stu-id="cb5cd-164">Ruth Black</span></span></p><span data-ttu-id="cb5cd-165">\n</span><span class="sxs-lookup"><span data-stu-id="cb5cd-165">\n</span></span>      </div><span data-ttu-id="cb5cd-166">"}," identificador ": [{" use ":" normal "," tipo ": {" codificación ": [{" System ":" "," código ":" https://hl7.org/fhir/v2/0203 Mr "," display ":" número de registro médico "," userSelected ": falso}]," texto ":" número de registro médico "}," sistema ":" "," nombre ":". ","} http://hospital.smarthealthit.org ], "activo": verdadero, "nombre": [{"use": "funcionario", "unidad": "negro", "dado": ["Ruth", "C". 1234567</span><span class="sxs-lookup"><span data-stu-id="cb5cd-166">" }, "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "https://hl7.org/fhir/v2/0203", "code": "MR", "display": "Medical record number", "userSelected": false } ], "text": "Medical record number" }, "system": "http://hospital.smarthealthit.org", "value": "1234567" } ], "active": true, "name": [ { "use": "official", "family": "Black", "given": [ "Ruth", "C."</span></span>
    <span data-ttu-id="cb5cd-167">]}], "Telecom": [{"System": "Phone", "Value": "800-599-2739", "uso": "Home"}, {"System": "Phone", "Value": "[re800-808-7785", "use": "Mobile"}, "", "": ".": "mujer", "FechaNacimiento": "1951-08-23", "dirección": [{"use": "casa", "línea": ["26 South RdApt 22"], "ciudad": "Sapulpa", "estado": "correcto", "CódigoPostal": "74066", "país": "USA"}]}, "Buscar": {"MODE": "match"}}]}</span><span class="sxs-lookup"><span data-stu-id="cb5cd-167">] } ], "telecom": [ { "system": "phone", "value": "800-599-2739", "use": "home" }, { "system": "phone", "value": "800-808-7785", "use": "mobile" }, { "system": "email", "value": "ruth.black@example.com" } ], "gender": "female", "birthDate": "1951-08-23", "address": [ { "use": "home", "line": [ "26 South RdApt 22" ], "city": "Sapulpa", "state": "OK", "postalCode": "74066", "country": "USA" } ] }, "search": { "mode": "match" } } ] }</span></span>

* * *

    <span data-ttu-id="cb5cd-168">Solicitud: Obtén <fhir-Server>/patient/<ID de paciente></span><span class="sxs-lookup"><span data-stu-id="cb5cd-168">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="cb5cd-169">Respuesta: {"resourceType": "patient", "ID": "<patient-ID>", "identificador": [{"use": "normal", "type": {"codificación": [{"sistema": " https://hl7.org/fhir/v2/0203 ", "código": "Mr",}], "texto": "número de registro médico"}, "valor": "1234567"}], "nombre": [{"use": "oficial", "familia": ",". "</span><span class="sxs-lookup"><span data-stu-id="cb5cd-169">Response: { "resourceType": "Patient", "id": "<patient-id>", "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "https://hl7.org/fhir/v2/0203", "code": "MR", } ], "text": "Medical record number" }, "value": "1234567" } ], "name": [ { "use": "official", "family": "Adams", "given": [ "Daniel", "X."</span></span> <span data-ttu-id="cb5cd-170">]}], "sexo": "hombre", "FechaNacimiento": "1925-12-23",}</span><span class="sxs-lookup"><span data-stu-id="cb5cd-170">] } ], "gender": "male", "birthDate": "1925-12-23", }</span></span>

* * *

<span data-ttu-id="cb5cd-171">Consulte [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="cb5cd-171">See [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="cb5cd-172">Observación</span><span class="sxs-lookup"><span data-stu-id="cb5cd-172">Observation</span></span>

<span data-ttu-id="cb5cd-173">Estos son los campos mínimos obligatorios, que son un subconjunto del [Perfil de signos vitales Argonaut](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span><span class="sxs-lookup"><span data-stu-id="cb5cd-173">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

1. <span data-ttu-id="cb5cd-174">Vigencia (fecha o hora)</span><span class="sxs-lookup"><span data-stu-id="cb5cd-174">Effective (date time or period)</span></span>
2. <span data-ttu-id="cb5cd-175">Code. Coding. Code</span><span class="sxs-lookup"><span data-stu-id="cb5cd-175">Code.Coding.Code</span></span>
3. <span data-ttu-id="cb5cd-176">ValueQuantity. Value</span><span class="sxs-lookup"><span data-stu-id="cb5cd-176">ValueQuantity.Value</span></span>

<span data-ttu-id="cb5cd-177">Además de los campos Argonaut, para una experiencia de usuario excelente, la aplicación de pacientes también puede leer los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="cb5cd-177">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="cb5cd-178">Code. Coding. display</span><span class="sxs-lookup"><span data-stu-id="cb5cd-178">Code.Coding.Display</span></span>
2. <span data-ttu-id="cb5cd-179">Unidad ValueQuantity.</span><span class="sxs-lookup"><span data-stu-id="cb5cd-179">ValueQuantity.Unit</span></span>

<span data-ttu-id="cb5cd-180">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="cb5cd-180">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="cb5cd-181">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="cb5cd-181">patient=\<patient id></span></span>
2. <span data-ttu-id="cb5cd-182">_sort =-Date</span><span class="sxs-lookup"><span data-stu-id="cb5cd-182">_sort=-date</span></span>
3. <span data-ttu-id="cb5cd-183">Categoría (consultaremos "las señales de categoría = vitales") para recuperar la lista de constantes vitales.</span><span class="sxs-lookup"><span data-stu-id="cb5cd-183">category (we will query for "category=vital-signs") to retrieve the list of vital signs.</span></span>

<span data-ttu-id="cb5cd-184">Consulte este ejemplo de la llamada:</span><span class="sxs-lookup"><span data-stu-id="cb5cd-184">Refer to this example of the call:</span></span>

* * *

    <span data-ttu-id="cb5cd-185">Solicitud: obtener <fhir-Server>/Observation? patient =<patient-ID>&Category = Vital-Signs</span><span class="sxs-lookup"><span data-stu-id="cb5cd-185">Request: GET <fhir-server>/Observation?patient=<patient-id>&category=vital-signs</span></span>
    
    <span data-ttu-id="cb5cd-186">Respuesta: {"resourceType": "bundle", "ID": "<paquete-ID>", "type": "searchset", "total": 20, "Entry": [{"Resource": {"resourceType": "observación", "ID": "<Resource-ID>", "Category": [{"Code": [{"System": " https://hl7.org/fhir/observation-category ", "", "in código": {"codificación": [{"System": "" http://loinc.org , "Code": "8867-4", "display": "heart_rate"}]}, "effectiveDateTime": "2009-04-08T00:00:00-06:00", "valueQuantity": {"valor": 72,0, "unidad": "{pulsaciones}/min.", "sistema": " http://unitsofmeasure.org ",}}},.</span><span class="sxs-lookup"><span data-stu-id="cb5cd-186">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": [ { "coding": [ { "system": "https://hl7.org/fhir/observation-category", "code": "vital-signs" } ], } ], "code": { "coding": [ { "system": "http://loinc.org", "code": "8867-4", "display": "heart_rate" } ] }, "effectiveDateTime": "2009-04-08T00:00:00-06:00", "valueQuantity": { "value": 72.0, "unit": "{beats}/min", "system": "http://unitsofmeasure.org", } } }, .</span></span>
        <span data-ttu-id="cb5cd-187">.</span><span class="sxs-lookup"><span data-stu-id="cb5cd-187">.</span></span>
        <span data-ttu-id="cb5cd-188">.</span><span class="sxs-lookup"><span data-stu-id="cb5cd-188">.</span></span>
      <span data-ttu-id="cb5cd-189">] }</span><span class="sxs-lookup"><span data-stu-id="cb5cd-189">] }</span></span>

* * *

<span data-ttu-id="cb5cd-190">Consulte [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="cb5cd-190">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="cb5cd-191">Condición</span><span class="sxs-lookup"><span data-stu-id="cb5cd-191">Condition</span></span>

<span data-ttu-id="cb5cd-192">Estos son los campos mínimos obligatorios, que son un subconjunto del [Perfil de condición Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span><span class="sxs-lookup"><span data-stu-id="cb5cd-192">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

1. <span data-ttu-id="cb5cd-193">Code. Coding [0]. Aparecen</span><span class="sxs-lookup"><span data-stu-id="cb5cd-193">Code.Coding[0].Display</span></span>

<span data-ttu-id="cb5cd-194">Además de los campos Argonaut, para una experiencia de usuario excelente, la aplicación de pacientes también puede leer los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="cb5cd-194">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="cb5cd-195">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="cb5cd-195">AssertedDate</span></span>
2. <span data-ttu-id="cb5cd-196">Gravedad</span><span class="sxs-lookup"><span data-stu-id="cb5cd-196">Severity</span></span>

<span data-ttu-id="cb5cd-197">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="cb5cd-197">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="cb5cd-198">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="cb5cd-198">patient=\<patient id></span></span>
2. <span data-ttu-id="cb5cd-199">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="cb5cd-199">_count=\<max results></span></span>

<span data-ttu-id="cb5cd-200">Consulte el siguiente ejemplo de esta llamada:</span><span class="sxs-lookup"><span data-stu-id="cb5cd-200">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="cb5cd-201">Solicitud: obtener <fhir-Server>/Condition? patient =<ID de paciente>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="cb5cd-201">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="cb5cd-202">Respuesta: {"resourceType": "bundle", "ID": "paquete de <-ID>", "type": "searchset", "total": 2, "Entry": [{"Resource": {"resourceType": "Condition", "ID": "", "",> <"" "," " http://snomed.info/sct ", "código": "185903001", "display": "necesita la vacuna de la influenza",}]}, "gravedad": {"codificación": [{"System": " http://snomed.info/sct ", "código": "24484000", "display": "assertedDate"]}, "" ":" 2018-04-04 "}},.</span><span class="sxs-lookup"><span data-stu-id="cb5cd-202">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 2, "entry": [ { "resource": { "resourceType": "Condition", "id": "<resource-id>", "code": { "coding": [ { "system": "http://snomed.info/sct", "code": "185903001", "display": "Needs influenza immunization", } ] }, "severity": { "coding": [ { "system": "http://snomed.info/sct", "code": "24484000", "display": "Severe" } ] }, "assertedDate": "2018-04-04" } }, .</span></span>
        <span data-ttu-id="cb5cd-203">.</span><span class="sxs-lookup"><span data-stu-id="cb5cd-203">.</span></span>
        <span data-ttu-id="cb5cd-204">.</span><span class="sxs-lookup"><span data-stu-id="cb5cd-204">.</span></span>
      <span data-ttu-id="cb5cd-205">] }</span><span class="sxs-lookup"><span data-stu-id="cb5cd-205">] }</span></span>

* * *
<span data-ttu-id="cb5cd-206">Consulte [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="cb5cd-206">See [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="cb5cd-207">Detect</span><span class="sxs-lookup"><span data-stu-id="cb5cd-207">Encounter</span></span>

<span data-ttu-id="cb5cd-208">Estos son los campos mínimos obligatorios, que son un subconjunto del [núcleo de Estados Unidos](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) y el perfil "debe tener campos".</span><span class="sxs-lookup"><span data-stu-id="cb5cd-208">These are the minimum required fields, which are a subset of the [US Core Encounter profile](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "must have" fields).</span></span>

1. <span data-ttu-id="cb5cd-209">Statu</span><span class="sxs-lookup"><span data-stu-id="cb5cd-209">Status</span></span>
2. <span data-ttu-id="cb5cd-210">Escriba [0]. Codificación [0]. Aparecen</span><span class="sxs-lookup"><span data-stu-id="cb5cd-210">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="cb5cd-211">Además, los siguientes campos de la parte central de EE. UU. se encuentran en los campos "debe ser compatible" del perfil:</span><span class="sxs-lookup"><span data-stu-id="cb5cd-211">In addition, the following fields from US Core Encounter profile's "must support" fields:</span></span>

1. <span data-ttu-id="cb5cd-212">Start period</span><span class="sxs-lookup"><span data-stu-id="cb5cd-212">Period.Start</span></span>
2. <span data-ttu-id="cb5cd-213">Ubicación [0]. Location. display</span><span class="sxs-lookup"><span data-stu-id="cb5cd-213">Location[0].Location.Display</span></span>

<span data-ttu-id="cb5cd-214">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="cb5cd-214">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="cb5cd-215">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="cb5cd-215">patient=\<patient id></span></span>
2. <span data-ttu-id="cb5cd-216">_sort: DESC =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="cb5cd-216">_sort:desc=\<field ex. date></span></span>
3. <span data-ttu-id="cb5cd-217">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="cb5cd-217">_count=\<max results></span></span>

<span data-ttu-id="cb5cd-218">El objetivo es poder recuperar el último lugar conocido del paciente.</span><span class="sxs-lookup"><span data-stu-id="cb5cd-218">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="cb5cd-219">Cada uno de ellos hace referencia a un recurso de ubicación.</span><span class="sxs-lookup"><span data-stu-id="cb5cd-219">Each encounter references a location resource.</span></span> <span data-ttu-id="cb5cd-220">La referencia también incluirá el campo de visualización de la ubicación.</span><span class="sxs-lookup"><span data-stu-id="cb5cd-220">The reference shall also include the location's display field.</span></span>

<span data-ttu-id="cb5cd-221">Consulte [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="cb5cd-221">See [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="cb5cd-222">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="cb5cd-222">AllergyIntolerance</span></span>

<span data-ttu-id="cb5cd-223">Estos son los campos mínimos obligatorios, que son un subconjunto del perfil de [AllergyIntolerance de Argonaut](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) :</span><span class="sxs-lookup"><span data-stu-id="cb5cd-223">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

1. <span data-ttu-id="cb5cd-224">Code. Text</span><span class="sxs-lookup"><span data-stu-id="cb5cd-224">Code.Text</span></span>
2. <span data-ttu-id="cb5cd-225">Code. Coding [0]. Aparecen</span><span class="sxs-lookup"><span data-stu-id="cb5cd-225">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="cb5cd-226">ClinicalStatus/VerificationStatus (hemos leído ambas)</span><span class="sxs-lookup"><span data-stu-id="cb5cd-226">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="cb5cd-227">Además de los campos Argonaut, para una experiencia de usuario excelente, la aplicación de pacientes también puede leer el siguiente campo:</span><span class="sxs-lookup"><span data-stu-id="cb5cd-227">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

1. <span data-ttu-id="cb5cd-228">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="cb5cd-228">AssertedDate</span></span>
2. <span data-ttu-id="cb5cd-229">Nota. Text</span><span class="sxs-lookup"><span data-stu-id="cb5cd-229">Note.Text</span></span>
3. <span data-ttu-id="cb5cd-230">Ataque</span><span class="sxs-lookup"><span data-stu-id="cb5cd-230">Reaction</span></span>
    1. <span data-ttu-id="cb5cd-231">Sustancia (un elemento de codificación)</span><span class="sxs-lookup"><span data-stu-id="cb5cd-231">Substance (one coding element)</span></span>
    2. <span data-ttu-id="cb5cd-232">Manifiesto (un elemento de codificación)</span><span class="sxs-lookup"><span data-stu-id="cb5cd-232">Manifestation (one coding element)</span></span>

<span data-ttu-id="cb5cd-233">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="cb5cd-233">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="cb5cd-234">Paciente =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="cb5cd-234">Patient =  \<patient id></span></span>

<span data-ttu-id="cb5cd-235">Vea el ejemplo siguiente de la llamada:</span><span class="sxs-lookup"><span data-stu-id="cb5cd-235">See the following example of the call:</span></span> 

* * *

    <span data-ttu-id="cb5cd-236">Solicitud: obtener <fhir-Server>/AllergyIntolerance? patient =<ID de paciente></span><span class="sxs-lookup"><span data-stu-id="cb5cd-236">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="cb5cd-237">Respuesta: {"resourceType": "bundle", "ID": "<paquete-ID>", "type": "searchset", "total": 1 "Entry": [{"Resource": {"resourceType": "AllergyIntolerance", "ID": "<Resource-ID>", "clinicalStatus": "Active", "verificationStatus": "Confirmed", "código": {"no se pudo escribir el http://rxnav.nlm.nih.gov/REST/Ndfrt código" N0000175503 "," display ":" sulfonamide antibacteriasl ",}]," texto ":" sulfonamide antibacteriasl "}," assertedDate ":" 2018-01-01T00:00:00-07:00 "," reacción ": [{" manifest ": [{" codificación ": [{" System ":" http://snomed.info/sct "," Code ":" 271807003 "," display ":" Skin rash ",}]," texto ":" Skin rash "}],}]}}]}</span><span class="sxs-lookup"><span data-stu-id="cb5cd-237">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "clinicalStatus": "active",         "verificationStatus": "confirmed",         "code": {           "coding": [             {               "system": "http://rxnav.nlm.nih.gov/REST/Ndfrt",               "code": "N0000175503",               "display": "sulfonamide antibacterial",             }           ],           "text": "sulfonamide antibacterial"         },         "assertedDate": "2018-01-01T00:00:00-07:00",         "reaction": [           {             "manifestation": [               {                 "coding": [                   {                     "system": "http://snomed.info/sct",                     "code": "271807003",                     "display": "skin rash",                   }                 ],                 "text": "skin rash"               }             ],           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="cb5cd-238">Consulte [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="cb5cd-238">See [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="cb5cd-239">Solicitud de medicación</span><span class="sxs-lookup"><span data-stu-id="cb5cd-239">Medication Request</span></span>

<span data-ttu-id="cb5cd-240">Estos son los campos mínimos obligatorios, que son un subconjunto del [Perfil de solicitud de medicación del núcleo de Estados Unidos](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span><span class="sxs-lookup"><span data-stu-id="cb5cd-240">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

1. <span data-ttu-id="cb5cd-241">Medicación. display (si Ref)</span><span class="sxs-lookup"><span data-stu-id="cb5cd-241">Medication.Display (if Reference)</span></span>
2. <span data-ttu-id="cb5cd-242">Medicación. Text (si CodableConcept)</span><span class="sxs-lookup"><span data-stu-id="cb5cd-242">Medication.Text (if CodableConcept)</span></span>
3. <span data-ttu-id="cb5cd-243">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="cb5cd-243">AuthoredOn</span></span>
4. <span data-ttu-id="cb5cd-244">Solicitante. Agent. display</span><span class="sxs-lookup"><span data-stu-id="cb5cd-244">Requester.Agent.Display</span></span>

<span data-ttu-id="cb5cd-245">Además de los campos básicos de Estados Unidos, para disfrutar de una experiencia de usuario excelente, la aplicación de pacientes también puede leer los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="cb5cd-245">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="cb5cd-246">DosageInstruction[..]. Facturas</span><span class="sxs-lookup"><span data-stu-id="cb5cd-246">DosageInstruction[..].Text</span></span>
2. <span data-ttu-id="cb5cd-247">Facturas</span><span class="sxs-lookup"><span data-stu-id="cb5cd-247">Text</span></span>

<span data-ttu-id="cb5cd-248">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="cb5cd-248">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="cb5cd-249">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="cb5cd-249">patient=\<patient id></span></span>
2. <span data-ttu-id="cb5cd-250">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="cb5cd-250">_count=\<max results></span></span>

<span data-ttu-id="cb5cd-251">Consulte [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="cb5cd-251">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="cb5cd-252">Beneficios</span><span class="sxs-lookup"><span data-stu-id="cb5cd-252">Coverage</span></span>

<span data-ttu-id="cb5cd-253">Estos son los campos mínimos obligatorios, no incluidos en los perfiles de los Estados Unidos Core o Argonaut:</span><span class="sxs-lookup"><span data-stu-id="cb5cd-253">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="cb5cd-254">Agrupar, al menos un elemento con</span><span class="sxs-lookup"><span data-stu-id="cb5cd-254">Grouping, at least one element with</span></span>
    1. <span data-ttu-id="cb5cd-255">GroupDisplay</span><span class="sxs-lookup"><span data-stu-id="cb5cd-255">GroupDisplay</span></span>
    2. <span data-ttu-id="cb5cd-256">PlanDisplay</span><span class="sxs-lookup"><span data-stu-id="cb5cd-256">PlanDisplay</span></span>
2. <span data-ttu-id="cb5cd-257">Período</span><span class="sxs-lookup"><span data-stu-id="cb5cd-257">Period</span></span>
3. <span data-ttu-id="cb5cd-258">SubscriberId</span><span class="sxs-lookup"><span data-stu-id="cb5cd-258">SubscriberId</span></span>

<span data-ttu-id="cb5cd-259">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="cb5cd-259">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="cb5cd-260">Paciente = \<patient id></span><span class="sxs-lookup"><span data-stu-id="cb5cd-260">Patient = \<patient id></span></span>

<span data-ttu-id="cb5cd-261">Consulte [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="cb5cd-261">See [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
