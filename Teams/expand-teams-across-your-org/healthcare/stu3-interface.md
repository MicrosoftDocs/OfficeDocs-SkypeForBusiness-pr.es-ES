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
# <a name="stu3-interface-specification"></a>Especificación de la interfaz STU3

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Configurar o volver a configurar un servidor FHIR para trabajar con la aplicación de los pacientes de los equipos de Microsoft requiere la descripción de los datos que la aplicación necesita obtener acceso a. El servidor FHIR debe admitir solicitudes POST con paquetes para los siguientes recursos:

- [Paciente](#patient)
- [Observación](#observation)
- [Condición](#condition)
- [Encontrar](#encounter)
- [Alergia intolerancia](#allergyintolerance)
- [Cobertura](#coverage)
- [Instrucción de medicación](#medication-request) (sustituye a la MedicationOrder en la versión DSTU2 de la PatientsApp)
- Ubicación (la información necesaria desde este recurso puede estar incluida en encontró)

> [!NOTE]
> El paciente recurso es el recurso sólo es obligatorio (sin que la aplicación no se cargará en absoluto); Sin embargo, se recomienda que el socio implementar la compatibilidad de todos los recursos mencionados anteriormente por especificaciones proporcionados por debajo de la mejor experiencia del usuario final con la aplicación de los pacientes de los equipos de Microsoft.

Las consultas de la aplicación de los pacientes de los equipos de Microsoft para más de un recurso deberán registrar una agrupación (lote) de solicitudes a la dirección URL del servidor FHIR. El servidor debe procesar cada solicitud y devolver una agrupación de los recursos que coinciden con cada solicitud. Para obtener más información y ejemplos, consulte [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).

## <a name="capability-statement"></a>Instrucción de capacidad

Estos son los campos obligatorios mínimos:

1. reposo
   1. Modo
   2. Interacción
   3. Recurso: tipo
   4. Seguridad: [extensión para los identificadores URI de OAuth](http://hl7.org/fhir/extension-oauth-uris.html)
2. FhirVersion (nuestro código requiere esto para comprender qué versión se deberíamos dinámicas a).

Vea [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) establecer otros detalles en este campo.

## <a name="patient"></a>Paciente

Estos son los mínimos campos obligatorios, que son un subconjunto de los campos de perfil de pacientes Argonaut:

1. Name.Given
2. Name.Family
3. Género
4. Fecha de nacimiento
5. NRM (identificador)

Además de los [campos de Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), para una experiencia de usuario excelente la aplicación de los pacientes también puede leer los siguientes campos:

1. Name.Use
2. Name.Prefix
3. [GeneralPractitioner] - GeneralPractitioner la referencia debe incluirse en el recurso de pacientes (sólo en el campo para mostrar)

Una búsqueda de recursos, utiliza el método POST en /Patient/_search y los parámetros siguientes:

1. Id.
2. familia de = (busca todos los pacientes cuyo nombre familia contiene el valor)
3. determinado =\<substring>
4. fecha de nacimiento =(exact match)
5. género = (valores que se va a uno del género-administrativas)
6. \_Count (número máximo de resultados que se deben devolver) <br> La respuesta debe contener el número total de registros devueltos como resultado de la búsqueda y \_count usará el PatientsApp para limitar el número de registros devueltos.
7. identificador =\<mrn>

El objetivo es que puedan buscar y filtrar un paciente por lo siguiente:

- ID: Este es el identificador de recursos que tiene todos los recursos en FHIR.
- NRM: Éste es el identificador real para el paciente que sabe ensayos personal. Somos conscientes de que este NRM se basa en el tipo de identificador dentro de los recursos de identificador en FHIR.
- Nombre
- Fecha de nacimiento

Vea el ejemplo siguiente de la llamada:

* * *

    Solicitud: Cuerpo de la solicitud POST <fhir-server>/paciente/_search: determinado = ruth&family = negro
    
    Respuesta: {"resourceType": "Agrupar", "id": "<bundle id>", "meta": {"lastUpdated": "2019-01-14T23:44:45.052 + 00:00"}, "tipo": "searchset", "total": 1, "vínculo": [{"relation": "self", "url": <fhir-server>/paciente/_search "}],"entry": [{ "fullUrl": <fhir-server>/paciente/<patient-id> ","recursos": {"resourceType":"Paciente","id":"<patient id>","meta": {"versionId":"1","lastUpdated":" 2017-10-18T18:32:37.000 + 00:00 "},"texto": {"estado":"generado por","div ": "<div>\n        <p>Ruth negro</p>\n      </div>"},"identificador": [{"usar":"normal","tipo": {"codificación": [{"sistema":"http://hl7.org/fhir/v2/0203","código":"MR","Mostrar":"número de registro médico","userSelected": false}],"texto":"número de registro médico"},"sistema":"http://hospital.smarthealthit.org","valor":"1234567"}],"activa": true," nombre": [{"usar":"oficial","familia":"Negro","asignado": ["Ruth","c ".
    []}] "telecomunicaciones": [{"sistema": "phone", "valor": "uso de"800-599-2739",": "principal"}, {"sistema": "phone", "valor": "uso de"800-808-7785",": "móvil"}, {"sistema": "correo electrónico", "valor": "ruth.black@example.com"}], "género": "femenino", "fecha de nacimiento": "1951-08-23", " dirección": [{"usar":"principal","línea": ["26 sur RdApt 22"],"city":"Sapulpa","estado":"OK","CódigoPostal":"74066","country":"USA"}]},"búsqueda": {"modo de":"coincide con"}}]}

* * *

    Solicitud: Obtener <fhir-server>/paciente/<patient-id>
    
    Respuesta: {"resourceType": "Paciente", "id": "<patient id>", "identificador": [{"usar": "normal", "tipo": {"codificación": [{"sistema": "http://hl7.org/fhir/v2/0203", "código": "MR,"}], "texto": "número de registro médico"}, "valor": "1234567"}], "nombre": [{"usar": "oficial", " familia de":"Adams","asignado": ["Daniel","X". {}]], "género": "hombre", "fecha de nacimiento": "1925-12-23"}

* * *

Vea [http://hl7.org/fhir/stu3/patient.html](http://hl7.org/fhir/stu3/patient.html) establecer otros detalles en este campo.

## <a name="observation"></a>Observación

Estos son los mínimos campos obligatorios, que son un subconjunto de los [perfiles de Argonaut vitales](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).

1. Eficaces (fecha, hora o período)
2. Code.Coding.Code
3. ValueQuantity.Value

Además de los campos Argonaut, para una experiencia de usuario excelente la aplicación de los pacientes también puede leer los siguientes campos:

1. Code.Coding.Display
2. ValueQuantity.Unit

Una búsqueda de recursos utiliza el método GET y los parámetros siguientes:

1. paciente =\<id> paciente
2. _sort =-fecha
3. categoría (se van a consultar "categoría = vital signos") para recuperar la lista de constantes vitales.

Hacer referencia a este ejemplo de la llamada:

* * *

    Solicitud: Obtener <fhir-server> de observación? paciente = <patient id>&category = vital signos
    
    Respuesta: {"resourceType": "Agrupar", "id": "<bundle id>", "tipo": "searchset", "total": 20, "entry": [{"recursos": {"resourceType": "Observación", "id": "<resource id>", "categoría": [{"codificación": [{"sistema": "http://hl7.org/fhir/observation-category", "código": " vital-signos"}],}],"código": {"codificación": [{"sistema":"http://loinc.org","código":"8867-4","presentación":"heart_rate"}]},"effectiveDateTime":" 2009-04-08T00:00:00-06:00 ","valueQuantity": {"valor": 72,0,"unidad":" {pulsaciones} / min ","sistema":"http://unitsofmeasure.org",}}},.
        .
        .
      ] }

* * *

Vea [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) establecer otros detalles en este campo.

## <a name="condition"></a>Condición

Aquí tiene los campos obligatorios mínimos, que son un subconjunto del [perfil de condición de Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).

1. Code.Coding[0]. Monitor

Además de los campos Argonaut, para una experiencia de usuario excelente la aplicación de los pacientes también puede leer los siguientes campos:

1. AssertedDate
2. Gravedad

Una búsqueda de recursos utiliza el método GET y los parámetros siguientes:

1. paciente =\<id> paciente
2. _Count =\<results> máx.

Vea el siguiente ejemplo de esta llamada:

* * *

    Solicitud: Obtener <fhir-server>/condición? paciente = <patient id>&_count = 10
    
    Respuesta: {"resourceType": "Agrupar", "id": "<bundle id>", "tipo": "searchset", "total": 2, "entry": [{"recursos": {"resourceType": "Condición", "id": "<resource id>", "código": {"codificación": [{"sistema": "http://snomed.info/sct", "código": "185903001", " Mostrar":"Las necesidades de inmunización de influenza,"}]},"severity": {"codificación": [{"sistema":"http://snomed.info/sct","código":"24484000","Mostrar":"Grave"}]},"assertedDate":"2018-04-04"}},.
        .
        .
      ] }

* * *
Vea [http://hl7.org/fhir/stu3/condition.html](http://hl7.org/fhir/stu3/condition.html) establecer otros detalles en este campo.

## <a name="encounter"></a>Encontrar

Estos son los mínimos campos obligatorios, que son un subconjunto de los campos de "debe tener" [perfil surgir de núcleo de Estados Unidos](http://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) ).

1. Estado
2. Tipo [0]. Codificación [0]. Monitor

Además, los siguientes campos de perfil nos surgir Core "deben admitir" de campos:

1. Period.Start
2. Ubicación [0]. Location.Display

Una búsqueda de recursos utiliza el método GET y los parámetros siguientes:

1. paciente =\<id> paciente
2. _sort:desc =\<campo ex. date>
3. _Count =\<results> máx.

El objetivo es poder recuperar la última ubicación conocida del paciente. Cada hace referencia a un recurso de ubicación. La referencia también incluirá el campo de visualización de la ubicación.

Vea [http://hl7.org/fhir/stu3/encounter.html](http://hl7.org/fhir/stu3/encounter.html) establecer otros detalles en este campo.

## <a name="allergyintolerance"></a>AllergyIntolerance

Estos son los mínimos campos obligatorios, que son un subconjunto de los perfiles de [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) :

1. Code.Text
2. Code.Coding[0]. Monitor
3. ClinicalStatus/VerificationStatus (se lea ambos)

Además de los campos Argonaut, para una experiencia de usuario excelente la aplicación de los pacientes también puede leer el siguiente campo:

1. AssertedDate
2. Note.Text
3. Reacción
    1. Sustancia (elemento de codificación uno)
    2. Manifestación (elemento de codificación uno)

Una búsqueda de recursos utiliza el método GET y los parámetros siguientes:

1. Paciente = \<id> paciente

Vea el ejemplo siguiente de la llamada: 

* * *

    Solicitud: Obtener <fhir-server>/AllergyIntolerance? paciente = <patient-id>
    
    Respuesta: {"resourceType": "Agrupar", "id": "<bundle id>", "tipo": "searchset", "total": 1, "entry": [{"recursos": {"resourceType": "AllergyIntolerance", "id": "<resource id>", "clinicalStatus": "activo", "ve rificationStatus":"confirmado","código": {"codificación": [{"sistema":"http://rxnav.nlm.nih.gov/REST/Ndfrt","código":"N0000175503","Mostrar":"sulfonamide antibacterianas"}],"texto":"ant sulfonamide ibacterial"},"assertedDate":" 2018-01-01T00:00:00-07:00 ","reacción": [{"manifestación": [{"codificación": [{"sistema":"http://snomed.info/sct","código":  "271807003", "Mostrar": "sarpullido de máscara,"}], "texto": "sarpullido máscara"}],}]}}]}

* * *

Vea [http://hl7.org/fhir/stu3/allergyintolerance.html](http://hl7.org/fhir/stu3/allergyintolerance.html) establecer otros detalles en este campo.

## <a name="medication-request"></a>Solicitud de medicación

Estos son los mínimos campos obligatorios, que son un subconjunto de los [Estados Unidos principales medicación solicitar perfil](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):

1. Medication.Display (si referencia)
2. Medication.Text (si CodableConcept)
3. AuthoredOn
4. Requester.Agent.Display

Además de los campos nos principal, para una experiencia de usuario excelente la aplicación de los pacientes también puede leer los siguientes campos:

1. DosageInstruction [.]. Texto
2. Texto

Una búsqueda de recursos utiliza el método GET y los parámetros siguientes:

1. paciente =\<id> paciente
2. _Count =\<results> máx.

Vea [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) establecer otros detalles en este campo.

## <a name="coverage"></a>Cobertura

Estos son los campos obligatorios mínimos, no están cubiertos por nosotros principales o Argonaut perfiles:

1. Agrupación, al menos un elemento con
    1. Grupo IPMPVisualice
    2. PlanDisplay
2. Período
3. SubscriberId

Una búsqueda de recursos utiliza el método GET y los parámetros siguientes:

1. Paciente = \<id> paciente

Vea [http://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) establecer otros detalles en este campo.
