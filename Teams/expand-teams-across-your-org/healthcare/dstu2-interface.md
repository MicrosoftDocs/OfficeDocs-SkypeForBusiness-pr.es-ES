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
ms.openlocfilehash: 2fa5575d6d7a4cbdffec6c3396004c38e743720a
ms.sourcegitcommit: 3b54a56ec1fe4366580621e19cdbb6a833a01161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2020
ms.locfileid: "48361460"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="e4877-103">Especificación de la interfaz DSTU2</span><span class="sxs-lookup"><span data-stu-id="e4877-103">DSTU2 interface specification</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e4877-104">**A partir del 15 de octubre de 2020, la aplicación para pacientes quedará obsoleta y los usuarios ya no podrán instalarla desde la tienda de aplicaciones de Teams. Le recomendamos que empiece a usar la [aplicación lists](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) en Teams hoy.**</span><span class="sxs-lookup"><span data-stu-id="e4877-104">**Effective October 15, 2020, the Patients app will be deprecated and users will no longer be able to install it from the Teams app store. We encourage you to start using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams today.**</span></span>
>
><span data-ttu-id="e4877-105">Los datos de la aplicación patients se almacenan en el buzón de grupo del grupo Office 365 que respalda al equipo.</span><span class="sxs-lookup"><span data-stu-id="e4877-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="e4877-106">Cuando se retira la aplicación de pacientes, todos los datos asociados con ella se conservarán en este grupo, pero ya no se podrá obtener acceso a ellas a través de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="e4877-106">When the Patients app is retired, all data associated with it will be retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="e4877-107">Los usuarios actuales pueden volver a crear sus listas con la [aplicación listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span><span class="sxs-lookup"><span data-stu-id="e4877-107">Current users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="e4877-108">La [aplicación listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) está preinstalada para todos los usuarios de Teams y está disponible como una pestaña en todos los equipos y canales.</span><span class="sxs-lookup"><span data-stu-id="e4877-108">The [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) is pre-installed for all Teams users and is available as a tab in every team and channel.</span></span> <span data-ttu-id="e4877-109">Con las listas, los equipos de cuidados pueden crear listas de pacientes con la plantilla de pacientes integrados, desde cero o importando datos a Excel.</span><span class="sxs-lookup"><span data-stu-id="e4877-109">With Lists, care teams can create patient lists using the built-in Patients template, from scratch, or by importing data to Excel.</span></span> <span data-ttu-id="e4877-110">Para obtener más información sobre cómo administrar la aplicación listas de su organización, vea [administrar la aplicación listas](../../manage-lists-app.md).</span><span class="sxs-lookup"><span data-stu-id="e4877-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="e4877-111">Para configurar o volver a configurar un servidor de FHIR para que funcione con la aplicación para pacientes de Microsoft Teams, es necesario comprender a qué datos necesita acceder la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e4877-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="e4877-112">El servidor de FHIR debe admitir solicitudes POST con paquetes para los siguientes recursos:</span><span class="sxs-lookup"><span data-stu-id="e4877-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="e4877-113">Propio</span><span class="sxs-lookup"><span data-stu-id="e4877-113">Patient</span></span>](#patient)
- [<span data-ttu-id="e4877-114">Observación</span><span class="sxs-lookup"><span data-stu-id="e4877-114">Observation</span></span>](#observation)
- [<span data-ttu-id="e4877-115">Condición</span><span class="sxs-lookup"><span data-stu-id="e4877-115">Condition</span></span>](#condition)
- [<span data-ttu-id="e4877-116">Detect</span><span class="sxs-lookup"><span data-stu-id="e4877-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="e4877-117">Intolerancia de alergia</span><span class="sxs-lookup"><span data-stu-id="e4877-117">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="e4877-118">Beneficios</span><span class="sxs-lookup"><span data-stu-id="e4877-118">Coverage</span></span>](#coverage)
- [<span data-ttu-id="e4877-119">Orden de los medicamentos</span><span class="sxs-lookup"><span data-stu-id="e4877-119">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="e4877-120">Ubicación</span><span class="sxs-lookup"><span data-stu-id="e4877-120">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="e4877-121">El recurso paciente es el único recurso obligatorio (sin que la aplicación se cargue en absoluto).</span><span class="sxs-lookup"><span data-stu-id="e4877-121">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="e4877-122">Sin embargo, se recomienda que el socio implemente la compatibilidad de todos los recursos mencionados anteriormente según las especificaciones proporcionadas a continuación para obtener la mejor experiencia para el usuario final con la aplicación de pacientes de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e4877-122">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="e4877-123">Las consultas de la aplicación de pacientes de Microsoft Teams para más de un recurso publican un paquete (lote) de solicitudes a la dirección URL del servidor FHIR.</span><span class="sxs-lookup"><span data-stu-id="e4877-123">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="e4877-124">El servidor procesa cada solicitud y devuelve un paquete de los recursos coincidentes con cada solicitud.</span><span class="sxs-lookup"><span data-stu-id="e4877-124">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="e4877-125">Para obtener más información y ejemplos, consulte [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) .</span><span class="sxs-lookup"><span data-stu-id="e4877-125">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="e4877-126">Todos los siguientes recursos de FHIR deben ser accesibles mediante la referencia directa de recursos.</span><span class="sxs-lookup"><span data-stu-id="e4877-126">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="e4877-127">Conjunto de campos obligatorios mínimos de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="e4877-127">Conformance minimum required field set</span></span>

 <span data-ttu-id="e4877-128">El servidor de FHIR debe implementar la declaración de conformidad para que nosotros tenga un resumen del objetivo de sus capacidades.</span><span class="sxs-lookup"><span data-stu-id="e4877-128">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="e4877-129">Esperamos los siguientes parámetros en un DSTU2 FHIR Server:</span><span class="sxs-lookup"><span data-stu-id="e4877-129">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

1. <span data-ttu-id="e4877-130">DESCANSO</span><span class="sxs-lookup"><span data-stu-id="e4877-130">REST</span></span>
   1. <span data-ttu-id="e4877-131">Modo</span><span class="sxs-lookup"><span data-stu-id="e4877-131">Mode</span></span>
   2. <span data-ttu-id="e4877-132">MOV</span><span class="sxs-lookup"><span data-stu-id="e4877-132">Interaction</span></span>
   3. <span data-ttu-id="e4877-133">Recurso: tipo</span><span class="sxs-lookup"><span data-stu-id="e4877-133">Resource: Type</span></span>
   4. <span data-ttu-id="e4877-134">Seguridad: [extensión para URI de OAuth](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="e4877-134">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="e4877-135">FhirVersion (nuestro código requiere esto para comprender a qué versión debemos dinamizar, ya que admitimos varias versiones).</span><span class="sxs-lookup"><span data-stu-id="e4877-135">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="e4877-136">Consulte [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="e4877-136">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="e4877-137">Propio</span><span class="sxs-lookup"><span data-stu-id="e4877-137">Patient</span></span>

<span data-ttu-id="e4877-138">Estos son los campos mínimos obligatorios, que son un subconjunto de los campos de [Perfil del paciente de Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) :</span><span class="sxs-lookup"><span data-stu-id="e4877-138">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

1. <span data-ttu-id="e4877-139">Nombre. familia</span><span class="sxs-lookup"><span data-stu-id="e4877-139">Name.Family</span></span>
2. <span data-ttu-id="e4877-140">Nombre. dado</span><span class="sxs-lookup"><span data-stu-id="e4877-140">Name.Given</span></span>
3. <span data-ttu-id="e4877-141">Hombres</span><span class="sxs-lookup"><span data-stu-id="e4877-141">Gender</span></span>
4. <span data-ttu-id="e4877-142">FechaNacimiento</span><span class="sxs-lookup"><span data-stu-id="e4877-142">BirthDate</span></span>
5. <span data-ttu-id="e4877-143">MRN (identificador)</span><span class="sxs-lookup"><span data-stu-id="e4877-143">MRN (Identifier)</span></span>

<span data-ttu-id="e4877-144">Además de los campos Argonaut, para una experiencia de usuario excelente, la aplicación para pacientes también lee los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="e4877-144">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="e4877-145">Nombre. Use</span><span class="sxs-lookup"><span data-stu-id="e4877-145">Name.Use</span></span>
2. <span data-ttu-id="e4877-146">Nombre. Prefix</span><span class="sxs-lookup"><span data-stu-id="e4877-146">Name.Prefix</span></span>
3. <span data-ttu-id="e4877-147">CareProvider (esta referencia en el recurso paciente debe incluir los campos de visualización que se muestran en el ejemplo siguiente).</span><span class="sxs-lookup"><span data-stu-id="e4877-147">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

* * *

    <span data-ttu-id="e4877-148">Solicitud: Obtén <fhir-Server>/patient/<ID de paciente></span><span class="sxs-lookup"><span data-stu-id="e4877-148">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="e4877-149">Respuesta: {"resourceType": "patient", "ID": "<ID de paciente>",.</span><span class="sxs-lookup"><span data-stu-id="e4877-149">Response: { "resourceType": "Patient", "id": "<patient-id>", .</span></span>
      <span data-ttu-id="e4877-150">.</span><span class="sxs-lookup"><span data-stu-id="e4877-150">.</span></span>
      <span data-ttu-id="e4877-151">.</span><span class="sxs-lookup"><span data-stu-id="e4877-151">.</span></span>
      <span data-ttu-id="e4877-152">"nombre": [{"use": "funcionario", "prefijo": ["Mr"], "familia": ["Chau"], "dado": ["Hugh"]}], "identificador": [{"use": "oficial", "tipo": {"código": [{"System": "", "": ",". ",", ",", ".", ".", ",", ",": [{ https://hl7.org/fhir/v2/0203 "careProvider": "Juana Pérez"}],} 1957-06-05 1234567</span><span class="sxs-lookup"><span data-stu-id="e4877-152">"name": [ { "use": "official", "prefix": [ "Mr" ], "family": [ "Chau" ], "given": [ "Hugh" ] } ], "identifier": [ { "use": "official", "type": { "coding": [ { "system": "https://hl7.org/fhir/v2/0203", "code": "MR" } ] }, "value": "1234567" } ], "gender": "male", "birthDate": "1957-06-05", "careProvider": [{ "display": "Jane Doe" }], }</span></span>

* * *

<span data-ttu-id="e4877-153">Una búsqueda de recursos usa el método POST en/patient/_search y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="e4877-153">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="e4877-154">identificar</span><span class="sxs-lookup"><span data-stu-id="e4877-154">id</span></span>
2. <span data-ttu-id="e4877-155">Family: contiene = (busca todos los pacientes cuyo nombre contenga el valor).</span><span class="sxs-lookup"><span data-stu-id="e4877-155">family:contains=(searches for all patients whose family name contains the value.)</span></span>
3. <span data-ttu-id="e4877-156">dado =\<substring></span><span class="sxs-lookup"><span data-stu-id="e4877-156">given=\<substring></span></span>
4. <span data-ttu-id="e4877-157">Name =\<substring></span><span class="sxs-lookup"><span data-stu-id="e4877-157">name=\<substring></span></span>
5. <span data-ttu-id="e4877-158">FechaNacimiento = (coincidencia exacta)</span><span class="sxs-lookup"><span data-stu-id="e4877-158">birthdate=(exact match)</span></span>
6. <span data-ttu-id="e4877-159">\_contar (número máximo de resultados que se deben devolver)</span><span class="sxs-lookup"><span data-stu-id="e4877-159">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="e4877-160">La respuesta debe contener el recuento total de registros devueltos como resultado de la búsqueda, y \_ el PatientsApp usará Count para limitar el número de registros devueltos.</span><span class="sxs-lookup"><span data-stu-id="e4877-160">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="e4877-161">Identifier =\<mrn></span><span class="sxs-lookup"><span data-stu-id="e4877-161">identifier=\<mrn></span></span>

<span data-ttu-id="e4877-162">El objetivo es poder buscar y filtrar a un paciente por lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e4877-162">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="e4877-163">ID: es el identificador de recurso que tiene cada recurso en FHIR.</span><span class="sxs-lookup"><span data-stu-id="e4877-163">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="e4877-164">MRN: este es el identificador real del paciente que sabría el personal clínico.</span><span class="sxs-lookup"><span data-stu-id="e4877-164">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="e4877-165">Entendemos que este MRN se basa en el tipo de identificador dentro del recurso Identifier en FHIR</span><span class="sxs-lookup"><span data-stu-id="e4877-165">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="e4877-166">Nombre</span><span class="sxs-lookup"><span data-stu-id="e4877-166">Name</span></span>
- <span data-ttu-id="e4877-167">FechaNacimiento</span><span class="sxs-lookup"><span data-stu-id="e4877-167">Birthdate</span></span>

<span data-ttu-id="e4877-168">Consulta el siguiente ejemplo de esta llamada.</span><span class="sxs-lookup"><span data-stu-id="e4877-168">See the following example  of this call.</span></span>

* * *

    <span data-ttu-id="e4877-169">Solicitud: publique <fhir-Server>/patient/_search cuerpo de la solicitud: dado = Hugh&Family = Chau</span><span class="sxs-lookup"><span data-stu-id="e4877-169">Request: POST <fhir-server>/Patient/_search Request Body: given=hugh&family=chau</span></span>
    
    <span data-ttu-id="e4877-170">Respuesta: {"resourceType": "bundle", "ID": "<paquete-ID>",.</span><span class="sxs-lookup"><span data-stu-id="e4877-170">Response: { "resourceType": "Bundle", "id": "<bundle-id>", .</span></span>
      <span data-ttu-id="e4877-171">.</span><span class="sxs-lookup"><span data-stu-id="e4877-171">.</span></span>
      <span data-ttu-id="e4877-172">.</span><span class="sxs-lookup"><span data-stu-id="e4877-172">.</span></span>
      <span data-ttu-id="e4877-173">"entrada": [{"recurso": {"resourceType": "patient", "ID": "<> de identificación de pacientes", "nombre": [{"texto": "Hugh Chau", "familia": ["Chau"], "dado": ["Hugh"]}], "género": "," hombre "," FechaNacimiento ":" coincidencias "} 1957-06-05</span><span class="sxs-lookup"><span data-stu-id="e4877-173">"entry": [ { "resource": { "resourceType": "Patient", "id": "<patient-id>", "name": [ { "text": "Hugh Chau", "family": [ "Chau" ], "given": [ "Hugh" ] } ], "gender": "male", "birthDate": "1957-06-05" }, "search": { "mode": "match" } } ] }</span></span>

* * *

<span data-ttu-id="e4877-174">Consulte [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="e4877-174">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="e4877-175">Observación</span><span class="sxs-lookup"><span data-stu-id="e4877-175">Observation</span></span>

<span data-ttu-id="e4877-176">Estos son los campos mínimos obligatorios, que son un subconjunto del perfil de constantes vitales de Argonaut:</span><span class="sxs-lookup"><span data-stu-id="e4877-176">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 1. <span data-ttu-id="e4877-177">Vigencia (fecha o hora)</span><span class="sxs-lookup"><span data-stu-id="e4877-177">Effective (date time or period)</span></span>
 2. <span data-ttu-id="e4877-178">Code. Coding. Code</span><span class="sxs-lookup"><span data-stu-id="e4877-178">Code.Coding.Code</span></span>
 3. <span data-ttu-id="e4877-179">ValueQuantity. Value</span><span class="sxs-lookup"><span data-stu-id="e4877-179">ValueQuantity.Value</span></span>

<span data-ttu-id="e4877-180">Además de los campos Argonaut, para una experiencia de usuario excelente, la aplicación para pacientes también lee los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="e4877-180">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 1. <span data-ttu-id="e4877-181">Code. Coding. display</span><span class="sxs-lookup"><span data-stu-id="e4877-181">Code.Coding.Display</span></span>
 2. <span data-ttu-id="e4877-182">Unidad ValueQuantity.</span><span class="sxs-lookup"><span data-stu-id="e4877-182">ValueQuantity.Unit</span></span>

<span data-ttu-id="e4877-183">Si se usan observaciones de componentes, se aplica la misma lógica para cada observación de componentes.</span><span class="sxs-lookup"><span data-stu-id="e4877-183">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="e4877-184">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="e4877-184">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="e4877-185">paciente =\<patient id\></span><span class="sxs-lookup"><span data-stu-id="e4877-185">patient=\<patient id\></span></span>
2. <span data-ttu-id="e4877-186">ordenar: DESC =\<field ex. date\></span><span class="sxs-lookup"><span data-stu-id="e4877-186">sort:desc=\<field ex. date\></span></span>

<span data-ttu-id="e4877-187">El objetivo es poder recuperar los últimos signos vitales para un paciente, [VitalSigns. DSTU. Saz] (observación?).</span><span class="sxs-lookup"><span data-stu-id="e4877-187">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

* * *

    <span data-ttu-id="e4877-188">Solicitud: obtener <fhir-Server>/Observation? patient =<paciente-ID>&_sort:d ESC = Date&Category = invienes</span><span class="sxs-lookup"><span data-stu-id="e4877-188">Request: GET <fhir-server>/Observation?patient=<patient-id>&_sort:desc=date&category=vital-signs</span></span>
    
    <span data-ttu-id="e4877-189">Respuesta: {"resourceType": "bundle", "ID": "<paquete-ID>", "escribe": "searchset", "total": 20, "Entry": [{"recurso": {"nombre de recurso": "," nombre "," nombre ":", "", "," <= ">."} ","} "," "código": {"codificación": [{"System": " http://loinc.org ", "Code": "39156-5", "display": "BMI"}],}, "effectiveDateTime": "2009-12-01", "valueQuantity": {"valor": 34,4, "unidad": "kg/m2", "sistema": " http://unitsofmeasure.org ", "código": "kg/m2"}},},.</span><span class="sxs-lookup"><span data-stu-id="e4877-189">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": { "coding": [ { code": "vital-signs" } ], }, "code": { "coding": [ { "system": "http://loinc.org", "code": "39156-5", "display": "bmi" } ], }, "effectiveDateTime": "2009-12-01", "valueQuantity": { "value": 34.4, "unit": "kg/m2", "system": "http://unitsofmeasure.org", "code": "kg/m2" } }, }, .</span></span>
        <span data-ttu-id="e4877-190">.</span><span class="sxs-lookup"><span data-stu-id="e4877-190">.</span></span>
        <span data-ttu-id="e4877-191">.</span><span class="sxs-lookup"><span data-stu-id="e4877-191">.</span></span>
      <span data-ttu-id="e4877-192">] }</span><span class="sxs-lookup"><span data-stu-id="e4877-192">] }</span></span>

* * *

<span data-ttu-id="e4877-193">Consulte [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="e4877-193">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="e4877-194">Condición</span><span class="sxs-lookup"><span data-stu-id="e4877-194">Condition</span></span>

<span data-ttu-id="e4877-195">Estos son los campos mínimos obligatorios, que son un subconjunto del [Perfil de condición Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span><span class="sxs-lookup"><span data-stu-id="e4877-195">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="e4877-196">Code. Coding [0]. Aparecen</span><span class="sxs-lookup"><span data-stu-id="e4877-196">Code.Coding[0].Display</span></span>

<span data-ttu-id="e4877-197">Además de los campos Argonaut, para una experiencia de usuario excelente, la aplicación de pacientes también puede leer los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="e4877-197">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="e4877-198">Fecha de grabación</span><span class="sxs-lookup"><span data-stu-id="e4877-198">Date Recorded</span></span>
2. <span data-ttu-id="e4877-199">Gravedad</span><span class="sxs-lookup"><span data-stu-id="e4877-199">Severity</span></span>

<span data-ttu-id="e4877-200">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="e4877-200">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="e4877-201">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="e4877-201">patient=\<patient id></span></span>
2. <span data-ttu-id="e4877-202">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="e4877-202">_count=\<max results></span></span>

<span data-ttu-id="e4877-203">Consulte el siguiente ejemplo de esta llamada:</span><span class="sxs-lookup"><span data-stu-id="e4877-203">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="e4877-204">Solicitud: obtener <fhir-Server>/Condition? patient =<ID de paciente>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="e4877-204">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="e4877-205">Respuesta: {"resourceType": "bundle", "ID": "<paquete-ID>", "type": "searchset", "total": 1, "Entry": [{"recurso": {"resourceType": "Condition", "ID": "<Resource-ID>", "Code": {"codificación": [{"System": " http://snomed.info/sct ", "Code": "386033004", "display": "neuropathy (Nerve Damage)"}]}, "dateRecorded": "2018-09-17", "gravedad": {"codificación": [{"System": " http://snomed.info/sct ", "Code": "24484000", "display": "grave"}]}},}]}</span><span class="sxs-lookup"><span data-stu-id="e4877-205">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Condition",         "id": "<resource-id>",         "code": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "386033004",               "display": "Neuropathy (nerve damage)"             }           ]         },         "dateRecorded": "2018-09-17",         "severity": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "24484000",               "display": "Severe"             }           ]         }       },     }   ] }</span></span>

* * *

<span data-ttu-id="e4877-206">Consulte [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="e4877-206">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="e4877-207">Detect</span><span class="sxs-lookup"><span data-stu-id="e4877-207">Encounter</span></span>

<span data-ttu-id="e4877-208">Estos son los campos mínimos obligatorios, que son un subconjunto del núcleo de Estados Unidos y el perfil "debe tener" campos:</span><span class="sxs-lookup"><span data-stu-id="e4877-208">These are the minimum required fields, which are a subset of the US Core Encounter profile "must have" fields:</span></span>

1. <span data-ttu-id="e4877-209">Statu</span><span class="sxs-lookup"><span data-stu-id="e4877-209">Status</span></span>
2. <span data-ttu-id="e4877-210">Escriba [0]. Codificación [0]. Aparecen</span><span class="sxs-lookup"><span data-stu-id="e4877-210">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="e4877-211">Además, los siguientes campos de la parte central de Estados Unidos tienen los campos "debe ser compatible" del perfil.</span><span class="sxs-lookup"><span data-stu-id="e4877-211">In addition, the following fields from US Core Encounter profile's "must support" fields</span></span>

1. <span data-ttu-id="e4877-212">Start period</span><span class="sxs-lookup"><span data-stu-id="e4877-212">Period.Start</span></span>
2. <span data-ttu-id="e4877-213">Ubicación [0]. Location. display</span><span class="sxs-lookup"><span data-stu-id="e4877-213">Location[0].Location.Display</span></span>

<span data-ttu-id="e4877-214">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="e4877-214">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="e4877-215">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="e4877-215">patient=\<patient id></span></span>
2. <span data-ttu-id="e4877-216">_sort: DESC =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="e4877-216">_sort:desc=\<field ex. date></span></span>
3. <span data-ttu-id="e4877-217">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="e4877-217">_count=\<max results></span></span>

<span data-ttu-id="e4877-218">El objetivo es poder recuperar el último lugar conocido del paciente.</span><span class="sxs-lookup"><span data-stu-id="e4877-218">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="e4877-219">Cada uno de ellos hace referencia a un recurso de ubicación.</span><span class="sxs-lookup"><span data-stu-id="e4877-219">Each encounter references a location resource.</span></span> <span data-ttu-id="e4877-220">La referencia también incluirá el campo de visualización de la ubicación.</span><span class="sxs-lookup"><span data-stu-id="e4877-220">The reference shall also include the location's display field.</span></span> <span data-ttu-id="e4877-221">Consulta el siguiente ejemplo de esta llamada.</span><span class="sxs-lookup"><span data-stu-id="e4877-221">See the following example of this call.</span></span>
* * *

    <span data-ttu-id="e4877-222">Solicitud: obtener <fhir-Server>/Encounter? patient =<ID de paciente>&_sort:d ESC = Date&_count = 1</span><span class="sxs-lookup"><span data-stu-id="e4877-222">Request: GET <fhir-server>/Encounter?patient=<patient-id>&_sort:desc=date&_count=1</span></span>
    
    <span data-ttu-id="e4877-223">Respuesta: {"resourceType": "paquete", "tipo": "searchset", "total": 1, "entrada": [{"recurso": {"nombre del recurso": "<nombre", "id.": ","> "," nombre de recurso: ""} ","... " <id> } Estado": "ha llegado", "tipo": [{"código": [{"display": "appointment}", "... a. de paciente de pacientes/<>"}, "período": {"Start": "09/17/2018 1:00:00 PM"}, "ubicación": [{"ubicación": {"display": "Clinic-ENT"},}]}}]}</span><span class="sxs-lookup"><span data-stu-id="e4877-223">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Encounter",         "id": "<resource-id>",         "identifier": [{ "use": "official", "value": "<id>" }],         "status": "arrived",         "type": [           {             "coding": [{ "display": "Appointment" }],           }         ],         "patient": { "reference": "Patient/<patient-id>" },         "period": { "start": "09/17/2018 1:00:00 PM" },         "location": [           {             "location": { "display": "Clinic - ENT" },           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="e4877-224">Consulte [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="e4877-224">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="e4877-225">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="e4877-225">AllergyIntolerance</span></span>

<span data-ttu-id="e4877-226">Estos son los campos mínimos obligatorios, que son un subconjunto del perfil de AllergyIntolerance de Argonaut:</span><span class="sxs-lookup"><span data-stu-id="e4877-226">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

1. <span data-ttu-id="e4877-227">Code. Text</span><span class="sxs-lookup"><span data-stu-id="e4877-227">Code.Text</span></span>
2. <span data-ttu-id="e4877-228">Code. Coding [0]. Aparecen</span><span class="sxs-lookup"><span data-stu-id="e4877-228">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="e4877-229">Statu</span><span class="sxs-lookup"><span data-stu-id="e4877-229">Status</span></span>

<span data-ttu-id="e4877-230">Además de los campos Argonaut, para una experiencia de usuario excelente, la aplicación para pacientes también lee los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="e4877-230">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="e4877-231">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="e4877-231">RecordedDate</span></span>
2. <span data-ttu-id="e4877-232">Nota. Text</span><span class="sxs-lookup"><span data-stu-id="e4877-232">Note.Text</span></span>
3. <span data-ttu-id="e4877-233">Reacción [...]. Sustancia. texto</span><span class="sxs-lookup"><span data-stu-id="e4877-233">Reaction[..].Substance.Text</span></span>
4. <span data-ttu-id="e4877-234">Reacción [...]. Manifesting [..]. Facturas</span><span class="sxs-lookup"><span data-stu-id="e4877-234">Reaction[..].Manifestation[..].Text</span></span>
5. <span data-ttu-id="e4877-235">Text. div</span><span class="sxs-lookup"><span data-stu-id="e4877-235">Text.Div</span></span>

<span data-ttu-id="e4877-236">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="e4877-236">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="e4877-237">Paciente =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="e4877-237">Patient =  \<patient id></span></span>

<span data-ttu-id="e4877-238">Consulte el siguiente ejemplo de esta llamada:</span><span class="sxs-lookup"><span data-stu-id="e4877-238">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="e4877-239">Solicitud: obtener <fhir-Server>/AllergyIntolerance? patient =<ID de paciente></span><span class="sxs-lookup"><span data-stu-id="e4877-239">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="e4877-240">Respuesta: {"resourceType": "bundle", "ID": "<paquete-ID>", "type": "searchset", "total": 1, "Entry": [{"recurso": {"resourceType": "AllergyIntolerance", "ID": "<Resource-ID>", "recordedDate": "2018-09-17T07:00:00.000 Z", "sustancia": {"texto": "cashew NUTS"}, "estado": "confirmado", "reacción": [{"sustancia": {"texto": "cashew tuerca allergenic extraer producto inyectable"}, "manifiesto": [{"texto": "respuesta Anaphylactic"}]}]}}</span><span class="sxs-lookup"><span data-stu-id="e4877-240">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "recordedDate": "2018-09-17T07:00:00.000Z",         "substance": {           "text": "Cashew nuts"         },         "status": "confirmed",         "reaction": [           {             "substance": {               "text": "cashew nut allergenic extract Injectable Product"             },             "manifestation": [               {                 "text": "Anaphylactic reaction"               }             ]           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="e4877-241">Consulte [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="e4877-241">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="e4877-242">Orden de los medicamentos</span><span class="sxs-lookup"><span data-stu-id="e4877-242">Medication Order</span></span>

<span data-ttu-id="e4877-243">Estos son los campos mínimos obligatorios, que son un subconjunto del perfil de MedicationOrder de Argonaut:</span><span class="sxs-lookup"><span data-stu-id="e4877-243">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

1. <span data-ttu-id="e4877-244">DateWritten</span><span class="sxs-lookup"><span data-stu-id="e4877-244">DateWritten</span></span>
2. <span data-ttu-id="e4877-245">Prescribir. Mostrar</span><span class="sxs-lookup"><span data-stu-id="e4877-245">Prescriber.Display</span></span>
3. <span data-ttu-id="e4877-246">Medicación. display (si Ref)</span><span class="sxs-lookup"><span data-stu-id="e4877-246">Medication.Display (if reference)</span></span>
4. <span data-ttu-id="e4877-247">Medicación. Text (si concepto)</span><span class="sxs-lookup"><span data-stu-id="e4877-247">Medication.Text (if concept)</span></span>

<span data-ttu-id="e4877-248">Además de los campos Argonaut, para una experiencia de usuario excelente, la aplicación de pacientes también puede leer los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="e4877-248">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="e4877-249">DateEnded</span><span class="sxs-lookup"><span data-stu-id="e4877-249">DateEnded</span></span>
2. <span data-ttu-id="e4877-250">DosageInstruction. Text</span><span class="sxs-lookup"><span data-stu-id="e4877-250">DosageInstruction.Text</span></span>
3. <span data-ttu-id="e4877-251">Text. div</span><span class="sxs-lookup"><span data-stu-id="e4877-251">Text.Div</span></span>

<span data-ttu-id="e4877-252">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="e4877-252">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="e4877-253">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="e4877-253">patient=\<patient id></span></span>
2. <span data-ttu-id="e4877-254">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="e4877-254">_count=\<max results></span></span>

<span data-ttu-id="e4877-255">Consulte el siguiente ejemplo de esta llamada:</span><span class="sxs-lookup"><span data-stu-id="e4877-255">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="e4877-256">Solicitud: obtener <fhir-Server>/MedicationOrder? patient =<ID de paciente>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="e4877-256">Request: GET <fhir-server>/MedicationOrder?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="e4877-257">Respuesta: {"resourceType": "bundle", "ID": "<paquete-ID>", "tipo": "searchset", "total": "Entry": [{"Resource": {"resourceType": "MedicationOrder", "ID": "<Resource-ID>", "dateWritten": "2018-09-17", "premedicationCodeableConcept": {"Text": "nombre de la lisinopril de 20 MG de tableta oral"}, "prescribe": {"display": "?}]}, o bien</span><span class="sxs-lookup"><span data-stu-id="e4877-257">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "MedicationOrder",         "id": "<resource-id>",         "dateWritten": "2018-09-17",         "medicationCodeableConcept": {           "text": "Lisinopril 20 MG Oral Tablet"         },         "prescriber": {           "display": "Jane Doe"         },         "dosageInstruction": [           {             "text": "1 daily"           }         ]       }     }   ] }</span></span>

* * *  

<span data-ttu-id="e4877-258">Consulte [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="e4877-258">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="e4877-259">Beneficios</span><span class="sxs-lookup"><span data-stu-id="e4877-259">Coverage</span></span>

<span data-ttu-id="e4877-260">Estos son los campos mínimos obligatorios, no incluidos en los perfiles de los Estados Unidos Core o Argonaut:</span><span class="sxs-lookup"><span data-stu-id="e4877-260">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="e4877-261">Payor</span><span class="sxs-lookup"><span data-stu-id="e4877-261">Payor</span></span>

<span data-ttu-id="e4877-262">Una búsqueda de recursos usa el método GET y los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="e4877-262">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="e4877-263">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="e4877-263">patient=\<patient id></span></span>

<span data-ttu-id="e4877-264">Consulte el siguiente ejemplo de esta llamada:</span><span class="sxs-lookup"><span data-stu-id="e4877-264">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="e4877-265">Solicitud: obtener <fhir-Server>/Coverage? patient =<ID de paciente></span><span class="sxs-lookup"><span data-stu-id="e4877-265">Request: GET <fhir-server>/Coverage?patient=<patient-id></span></span>
    
    <span data-ttu-id="e4877-266">Respuesta: {"resourceType": "bundle", "type": "searchset", "total": 1, "entrada": [{"recurso": {"resourceType": "Coverage", "ID": "<Resource-ID>", "Plan": "sin seguro principal", "suscriptor": {"referencia": "patient/<ID de paciente>"}}}]}</span><span class="sxs-lookup"><span data-stu-id="e4877-266">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Coverage",         "id": "<resource-id>",         "plan": "No Primary Insurance",         "subscriber": { "reference": "Patient/<patient-id>" }       }     }   ] }</span></span>

* * *

<span data-ttu-id="e4877-267">Consulte [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="e4877-267">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="e4877-268">Ubicación</span><span class="sxs-lookup"><span data-stu-id="e4877-268">Location</span></span>

<span data-ttu-id="e4877-269">Este recurso solo se usa como referencia en el recurso de [problemas](#encounter) .</span><span class="sxs-lookup"><span data-stu-id="e4877-269">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="e4877-270">Consulte [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) para obtener más información sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="e4877-270">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
