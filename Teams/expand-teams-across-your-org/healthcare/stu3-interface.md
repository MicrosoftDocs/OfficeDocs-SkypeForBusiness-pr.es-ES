---
title: Interfaz de STU3 y integración de EHR de la aplicación para pacientes
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Integración de la EHR de la aplicación pacientes de Microsoft Teams
ms.openlocfilehash: 836c28f339a3936f03315b005c0eedfc49e0f2ba
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569248"
---
# <a name="stu3-interface-specification"></a>Especificación de la interfaz STU3

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Para configurar o volver a configurar un servidor de FHIR para que funcione con la aplicación para pacientes de Microsoft Teams, es necesario comprender a qué datos necesita acceder la aplicación. El servidor de FHIR debe admitir solicitudes POST con paquetes para los siguientes recursos:

- [Propio](#patient)
- [Observación](#observation)
- [Condición](#condition)
- [Detect](#encounter)
- [Intolerancia de alergia](#allergyintolerance)
- [Beneficios](#coverage)
- [Declaración de medicación](#medication-request) (reemplaza MedicationOrder en la versión DSTU2 de la PatientsApp)
- Ubicación (la información necesaria de este recurso puede estar incluida en encontrarse)

> [!NOTE]
> El recurso paciente es el único recurso obligatorio (sin que la aplicación se cargue); Sin embargo, se recomienda que el socio implemente la compatibilidad de todos los recursos mencionados anteriormente según las especificaciones proporcionadas a continuación para obtener la mejor experiencia para el usuario final con la aplicación de pacientes de Microsoft Teams.

Las consultas de la aplicación de pacientes de Microsoft Teams para más de un recurso deben publicar un paquete (lote) de solicitudes a la dirección URL del servidor de FHIR. El servidor debe procesar cada solicitud y devolver un paquete de los recursos coincidentes con cada solicitud. Para obtener más información y ejemplos, [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction)consulte.

## <a name="capability-statement"></a>Declaración de capacidad

Estos son los campos mínimos obligatorios:

1. DESCANSO
   1. Multimodo
   2. MOV
   3. Recurso: tipo
   4. Seguridad: [extensión para URI de OAuth](http://hl7.org/fhir/extension-oauth-uris.html)
2. FhirVersion (nuestro código requiere esto para comprender a qué versión debemos dinamizar).

Consulte [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) para obtener más información sobre este conjunto de campos.

## <a name="patient"></a>Propio

Estos son los campos mínimos obligatorios, que son un subconjunto de los campos de perfil del paciente de Argonaut:

1. Nombre. dado
2. Nombre. familia
3. Hombres
4. FechaNacimiento
5. MRN (identificador)

Además de los [campos Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), para una experiencia de usuario excelente, la aplicación de pacientes también puede leer los siguientes campos:

1. Nombre. Use
2. Nombre. Prefix
3. [GeneralPractitioner]-la referencia de GeneralPractitioner debe incluirse en el recurso patient (solo campo de mostrar)

Una búsqueda de recursos usa el método POST en/patient/_search y los siguientes parámetros:

1. identificar
2. Family = (busca todos los pacientes cuyo nombre contenga el valor)
3. proporcionado =\<substring>
4. FechaNacimiento = (coincidencia exacta)
5. Gender = (los valores son uno de los sexos administrativos)
6. \_contar (número máximo de resultados que se deben devolver) <br> La respuesta debe contener el recuento total de registros devueltos como resultado de la \_búsqueda y el recuento que usará el PatientsApp para limitar el número de registros devueltos.
7. Identifier =\<MRN>

El objetivo es poder buscar y filtrar a un paciente por lo siguiente:

- ID: es el identificador de recurso que tiene cada recurso en FHIR.
- MRN: este es el identificador real del paciente que sabría el personal clínico. Entendemos que este MRN se basa en el tipo de identificador dentro del recurso Identifier en FHIR.
- Nombre
- FechaNacimiento

Vea el ejemplo siguiente de la llamada:

* * *

    Solicitud: publique <fhir-Server> cuerpo de solicitud/patient/_search: dado = Ruth familia&= Black
    
    Respuesta: {"resourceType": "bundle", "ID": "<paquete-ID>", "meta": {"lastUpdated": "2019-01-14T23:44:45.052 + 00:00"}, "tipo": "searchset", "total": 1, "link": [{"Relation": "self", "ID. de servidor>/patient/_search"}], "entrada": [{"<fullUrl ": <fhir-Server>/patient/<patient-ID>", "recurso": {"resourceType": "patient", "ID": "<patient-ID>", "meta": {"versionId": "1", "lastUpdated": "18T18-10-: 32:37.000 + 00:00"}, "texto": {"status": "generated", "div": "<div>\n        <p>Ruth negro</p>\n      </div>"}," identificador ": [{" use ":" normalmente "," tipo ": {" codificación ": [{" sistema ":"http://hl7.org/fhir/v2/0203"," código ":" Mr "," display ":" número de registro médico "," userSelected ": falso}]," texto ":" número de registro médico "}," sistema "http://hospital.smarthealthit.org:" bajo "," valor ":" 1234567 "}]," activo ": verdadero," nombre ": [{" use ":" oficial "," familia ":" negro "," dado ": [" Ruth "," C "," C ".
    ]}], "Telecom": [{"System": "Phone", "Value": "800-599-2739", "use": "Inicio"}, {"sistema": "teléfono", "valor": ",", ",", ",", ":" teléfono móvil "=", "800-808-7785", "", ",", ",", ",". 1951-08-23 " Dirección ": [{" use ":" casa "," línea ": [" 26 South RdApt 22 "]," ciudad ":" Sapulpa "," State ":" "74066:" busca ":" = ".". ".". "...}-{". "}

* * *

    Solicitud: Obtén <fhir-Server>/patient/<ID de paciente>
    
    Respuesta: {"resourceType": "patient", "ID": "<patient-ID>", "identificador": [{"use": "normal", "tipo": {"código": [{"System"http://hl7.org/fhir/v2/0203: "", "" "," "," ",". ",", ",", ",", ",", "...", "..." 1234567 familia ":" Adams "," dado ": [" Daniel "," X ". ]}], "sexo": "hombre", "FechaNacimiento": "1925-12-23",}

* * *

Consulte [http://hl7.org/fhir/stu3/patient.html](http://hl7.org/fhir/stu3/patient.html) para obtener más información sobre este conjunto de campos.

## <a name="observation"></a>Observación

Estos son los campos mínimos obligatorios, que son un subconjunto del [Perfil de signos vitales Argonaut](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).

1. Vigencia (fecha o hora)
2. Code. Coding. Code
3. ValueQuantity. Value

Además de los campos Argonaut, para una experiencia de usuario excelente, la aplicación de pacientes también puede leer los siguientes campos:

1. Code. Coding. display
2. Unidad ValueQuantity.

Una búsqueda de recursos usa el método GET y los siguientes parámetros:

1. paciente =\<ID de paciente>
2. _sort =-Date
3. Categoría (consultaremos "las señales de categoría = vitales") para recuperar la lista de constantes vitales.

Consulte este ejemplo de la llamada:

* * *

    Solicitud: obtener <fhir-Server>/Observation? patient =<patient-ID>&Category = Vital-Signs
    
    Respuesta: {"resourceType": "bundle", "ID": "<paquete de identificación>", "type": "searchset", "total": 20, "Entry": [{"Resource": {"resourceType": "observación", "ID": "<Resource-ID>", "Category": [{"" ".": [{"Systemhttp://hl7.org/fhir/observation-category": "", "Code": " signos esenciales "}],}]," código ": {" codificación ": [{" System ":"http://loinc.org"," código ":" 8867-4 "," display ":" heart_rate "}]}," effectiveDateTime ":" 2009-04-08T00:00:00-06:00 "," valueQuantity ": {" Value ": 72,0," Unit ":" {laters}/min. "," System ":"http://unitsofmeasure.org",}}},.
        .
        .
      ] }

* * *

Consulte [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) para obtener más información sobre este conjunto de campos.

## <a name="condition"></a>Condición

Estos son los campos mínimos obligatorios, que son un subconjunto del [Perfil de condición Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).

1. Code. Coding [0]. Aparecen

Además de los campos Argonaut, para una experiencia de usuario excelente, la aplicación de pacientes también puede leer los siguientes campos:

1. AssertedDate
2. Gravedad

Una búsqueda de recursos usa el método GET y los siguientes parámetros:

1. paciente =\<ID de paciente>
2. _count =\<> de resultados máximos

Consulte el siguiente ejemplo de esta llamada:

* * *

    Solicitud: obtener <fhir-Server>/Condition? patient =<ID de paciente>&_count = 10
    
    Respuesta: {"resourceType": "bundle", "ID": "<paquete-ID>", "escribe": "searchset", "total": 2, "entrada": [{"recurso": {"nombre del recurso": "código dehttp://snomed.info/sct", ",": "", "", "", <"código": "", ">."... ". 185903001 Display ":" necesita la vacuna de la influenza ",}]}," gravedad ": {" codificación ": [{" sistemahttp://snomed.info/sct":" "," código ":" 24484000 "," display ":" grave "}]}," assertedDate ":" 2018-04-04 "}},.
        .
        .
      ] }

* * *
Consulte [http://hl7.org/fhir/stu3/condition.html](http://hl7.org/fhir/stu3/condition.html) para obtener más información sobre este conjunto de campos.

## <a name="encounter"></a>Detect

Estos son los campos mínimos obligatorios, que son un subconjunto del [núcleo de Estados Unidos](http://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) y el perfil "debe tener campos".

1. Statu
2. Escriba [0]. Codificación [0]. Aparecen

Además, los siguientes campos de la parte central de EE. UU. se encuentran en los campos "debe ser compatible" del perfil:

1. Start period
2. Ubicación [0]. Location. display

Una búsqueda de recursos usa el método GET y los siguientes parámetros:

1. paciente =\<ID de paciente>
2. _sort: DESC =\<campo ex. > de fecha
3. _count =\<> de resultados máximos

El objetivo es poder recuperar el último lugar conocido del paciente. Cada uno de ellos hace referencia a un recurso de ubicación. La referencia también incluirá el campo de visualización de la ubicación.

Consulte [http://hl7.org/fhir/stu3/encounter.html](http://hl7.org/fhir/stu3/encounter.html) para obtener más información sobre este conjunto de campos.

## <a name="allergyintolerance"></a>AllergyIntolerance

Estos son los campos mínimos obligatorios, que son un subconjunto del perfil de [AllergyIntolerance de Argonaut](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) :

1. Code. Text
2. Code. Coding [0]. Aparecen
3. ClinicalStatus/VerificationStatus (hemos leído ambas)

Además de los campos Argonaut, para una experiencia de usuario excelente, la aplicación de pacientes también puede leer el siguiente campo:

1. AssertedDate
2. Nota. Text
3. Ataque
    1. Sustancia (un elemento de codificación)
    2. Manifiesto (un elemento de codificación)

Una búsqueda de recursos usa el método GET y los siguientes parámetros:

1. Paciente = \<ID de paciente>

Vea el ejemplo siguiente de la llamada: 

* * *

    Solicitud: obtener <fhir-Server>/AllergyIntolerance? patient =<ID de paciente>
    
    Respuesta: {"resourceType": "bundle", "ID": "<paquete-ID>", "type": "searchset", "total": 1, "Entry": [{"recurso": {"resourceType": "AllergyIntolerance", "ID": "<Resource-ID>", "clinicalStatus": "Active", "Ve rificationStatus ":" confirmado "," código ": {" codificación ": [{" System "http://rxnav.nlm.nih.gov/REST/Ndfrt:" "," "N0000175503", "display": "sulfonamide antibacteriasus",}], "Text": "sulfonamide ANT ibacterial "}," assertedDate ":" 2018-01-01T00:00:00-07:00 "," reacción ": [{" manifestity ": [{" Coding ": [{" System ":"http://snomed.info/sct"," Code ":  "271807003", "display": "Skin rash",}], "texto": "Skin rash"}],}]}}]}

* * *

Consulte [http://hl7.org/fhir/stu3/allergyintolerance.html](http://hl7.org/fhir/stu3/allergyintolerance.html) para obtener más información sobre este conjunto de campos.

## <a name="medication-request"></a>Solicitud de medicación

Estos son los campos mínimos obligatorios, que son un subconjunto del [Perfil de solicitud de medicación del núcleo de Estados Unidos](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):

1. Medicación. display (si Ref)
2. Medicación. Text (si CodableConcept)
3. AuthoredOn
4. Solicitante. Agent. display

Además de los campos básicos de Estados Unidos, para disfrutar de una experiencia de usuario excelente, la aplicación de pacientes también puede leer los siguientes campos:

1. DosageInstruction[..]. Facturas
2. Facturas

Una búsqueda de recursos usa el método GET y los siguientes parámetros:

1. paciente =\<ID de paciente>
2. _count =\<> de resultados máximos

Consulte [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) para obtener más información sobre este conjunto de campos.

## <a name="coverage"></a>Beneficios

Estos son los campos mínimos obligatorios, no incluidos en los perfiles de los Estados Unidos Core o Argonaut:

1. Agrupar, al menos un elemento con
    1. GroupDisplay
    2. PlanDisplay
2. Período
3. SubscriberId

Una búsqueda de recursos usa el método GET y los siguientes parámetros:

1. Paciente = \<ID de paciente>

Consulte [http://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) para obtener más información sobre este conjunto de campos.
