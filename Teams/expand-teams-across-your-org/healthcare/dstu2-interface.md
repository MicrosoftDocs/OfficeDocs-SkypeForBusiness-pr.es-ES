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
# <a name="dstu2-interface-specification"></a>Especificación de la interfaz DSTU2

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Configurar o volver a configurar un servidor FHIR para trabajar con la aplicación de los pacientes de los equipos de Microsoft requiere la descripción de los datos que la aplicación necesita obtener acceso a. El servidor FHIR debe admitir solicitudes POST con paquetes para los siguientes recursos:

- [Paciente](#patient)
- [Observación](#observation)
- [Condición](#condition)
- [Encontrar](#encounter)
- [Intolerancia alergias](#allergyintolerance)
- [Cobertura](#coverage)
- [Orden de medicación](#medication-order)
- [Ubicación](#location)

> [!NOTE]
> El paciente recurso es el recurso sólo es obligatorio (sin que la aplicación no se cargará en absoluto. Sin embargo, se recomienda que el socio implementar la compatibilidad de todos los recursos mencionados anteriormente por especificaciones proporcionados por debajo de la mejor experiencia del usuario final con la aplicación de los pacientes de los equipos de Microsoft.

Las consultas de la aplicación de los pacientes de los equipos de Microsoft para más de un recurso registrar una agrupación (lote) de solicitudes a la dirección URL del servidor FHIR. El servidor procesa cada solicitud y devuelve una agrupación de los recursos que coinciden con cada solicitud. Para obtener más información y ejemplos, consulte [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).

Los siguientes recursos FHIR deben ser accesibles por referencia de recurso directo.

## <a name="conformance-minimum-required-field-set"></a>Establece campo de conformidad mínimo requerido

 El servidor de FHIR debe implementar la declaración de conformidad para que podamos tienen un resumen de sus capacidades de objetivo. Esperamos que los siguientes parámetros en un servidor de FHIR DSTU2:

1. reposo
   1. Modo
   2. Interacción
   3. Recurso: tipo
   4. Seguridad: [extensión para los identificadores URI de OAuth](http://hl7.org/fhir/extension-oauth-uris.html)
2. FhirVersion (nuestro código requiere esto para comprender qué versión se deberíamos dinámicas a tal y como se admiten varias versiones).

Vea [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) establecer otros detalles en este campo.

## <a name="patient"></a>Paciente

Estos son los mínimos campos obligatorios, que son un subconjunto de los campos de [perfil de pacientes Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) :

1. Name.Family
2. Name.Given
3. Género
4. Fecha de nacimiento
5. NRM (identificador)

Además de los campos Argonaut, para una experiencia de usuario excelente la aplicación de los pacientes también lee los siguientes campos:

1. Name.Use
2. Name.Prefix
3. CareProvider (esta referencia en el recurso de pacientes debe incluir los campos de visualización que se muestra en el siguiente ejemplo).

* * *

    Solicitud: Obtener <fhir-server>/paciente/<patient-id>
    
    Respuesta: {"resourceType": "Paciente", "id": "<patient-id>".
      .
      .
      "nombre": [{"usar": "oficial", "prefijo": ["Mr"], "familia": ["Chau"], "asignado": ["Hugh"]}], "identificador": [{"usar": "oficial", "tipo": {"codificación": [{"sistema": "http://hl7.org/fhir/v2/0203", "código": "MR"}]}, "valor": "1234567"}], "género": "hombre", "fecha de nacimiento": "1957-06-05 ","careProvider": [{"Mostrar":"Jane Doe"}],}

* * *

Una búsqueda de recursos, utiliza el método POST en /Patient/_search y los parámetros siguientes:

1. Id.
2. familia: contiene = (búsquedas para todos los pacientes cuyo nombre familia contiene el valor).
3. determinado =\<substring>
4. nombre =\<substring>
5. fecha de nacimiento =(exact match)
6. \_Count (número máximo de resultados que se deben devolver) <br> La respuesta debe contener el número total de registros devueltos como resultado de la búsqueda, y \_count usará el PatientsApp para limitar el número de registros devueltos.
7. identificador =\<mrn>

El objetivo es que puedan buscar y filtrar un paciente por lo siguiente:

- ID: Este es el identificador de recursos que tiene todos los recursos en FHIR.
- NRM: Éste es el identificador real para el paciente que sabe ensayos personal. Somos conscientes de que este NRM se basa en el tipo de identificador dentro de los recursos de identificador en FHIR
- Nombre
- Fecha de nacimiento

Vea el siguiente ejemplo de esta llamada.

* * *

    Solicitud: Cuerpo de la solicitud POST <fhir-server>/paciente/_search: determinado = hugh&family = chau
    
    Respuesta: {"resourceType": "Agrupar", "id": "<bundle-id>".
      .
      .
      "entry": [{"recursos": {"resourceType": "Paciente", "id": "<patient id>", "nombre": [{"texto": "Hugh Chau", "familia": ["Chau"], "asignado": ["Hugh"]}], "género": "hombre", "fecha de nacimiento": "1957-06-05"}, "búsqueda": {"modo de": "coincide con"}}]}

* * *

Vea [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) establecer otros detalles en este campo.

## <a name="observation"></a>Observación

Estos son los mínimos campos obligatorios, que son un subconjunto de los perfiles de vitales Argonaut:

 1. Eficaces (fecha, hora o período)
 2. Code.Coding.Code
 3. ValueQuantity.Value

Además de los campos Argonaut, para una experiencia de usuario excelente la aplicación de los pacientes también lee los siguientes campos:

 1. Code.Coding.Display
 2. ValueQuantity.Unit

Si usa las observaciones de componente, se aplica la misma lógica para cada observación del componente.

Una búsqueda de recursos utiliza el método GET y los parámetros siguientes:

1. paciente =\<identificador de pacientes\>
2. ordenación: desc =\<campo ex. fecha\>

El objetivo es poder recuperar las constantes vitales más recientes de un paciente, [VitalSigns.DSTU.saz] (observación?).

* * *

    Solicitud: Obtener <fhir-server> de observación? paciente = <patient-id>&_sort:desc = date&category = vital signos
    
    Respuesta: {"resourceType": "Agrupar", "id": "<bundle id>", "tipo": "searchset", "total": 20, "entry": [{"recursos": {"resourceType": "Observación", "id": "<resource id>", "categoría": {"codificación": [{código":"vital de signos"}],},"código": {" codificación": [{"sistema":"http://loinc.org","código":"39156-5","presentación":"IMC"}],},"effectiveDateTime":"2009-12-01","valueQuantity": {"valor": 34,4,"unidad":" kg/m2","sistema":"http://unitsofmeasure.org","código":" kg/m2"}},},.
        .
        .
      ] }

* * *

Vea [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) establecer otros detalles en este campo.

## <a name="condition"></a>Condición

Estos son los mínimos campos obligatorios, que son un subconjunto del [perfil de condición de Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):

1. Code.Coding[0]. Monitor

Además de los campos Argonaut, para una experiencia de usuario excelente la aplicación de los pacientes también puede leer los siguientes campos:

1. Fecha registrada
2. Gravedad

Una búsqueda de recursos utiliza el método GET y los parámetros siguientes:

1. paciente =\<id> paciente
2. _Count =\<results> máx.

Vea el siguiente ejemplo de esta llamada:

* * *

    Solicitud: Obtener <fhir-server>/condición? paciente = <patient id>&_count = 10
    
    Respuesta: {"resourceType": "Agrupar", "id": "<bundle id>", "tipo": "searchset", "total": 1, "entry": [{"recursos": {"resourceType": "Condición", "id": "<resource id>", "código": {"codificación": [{               "sistema": "http://snomed.info/sct", "código": "386033004", "Mostrar": "Neuropathy (daño de los nervios)"}]}, "dateRecorded": "2018-09-17", "severity": {"codificación": [{"syst MT":"http://snomed.info/sct","código":"24484000","Mostrar":"Grave"}]}},}]}

* * *

Vea [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) establecer otros detalles en este campo.

## <a name="encounter"></a>Encontrar

Estos son los mínimos campos obligatorios, que son un subconjunto de los campos de "debe tener" de perfil nos surgir principales:

1. Estado
2. Tipo [0]. Codificación [0]. Monitor

Además, los siguientes campos de perfil nos surgir Core "deben admitir" de campos

1. Period.Start
2. Ubicación [0]. Location.Display

Una búsqueda de recursos utiliza el método GET y los parámetros siguientes:

1. paciente =\<id> paciente
2. _sort:desc =\<campo ex. date>
3. _Count =\<results> máx.

El objetivo es poder recuperar la última ubicación conocida del paciente. Cada hace referencia a un recurso de ubicación. La referencia también incluirá el campo de visualización de la ubicación. Vea el siguiente ejemplo de esta llamada.
* * *

    Solicitud: Obtener <fhir-server>/encontró? paciente = <patient-id>&_sort:desc = date&_count = 1
    
    Respuesta: {"resourceType": "Agrupación", "tipo": "searchset", "total": 1, "entry": [{"recursos": {"resourceType": "Encontrar", "id": "<resource id>", "identificador": [{"usar": "oficial", "valor": "<id>"}], "estado" : "llegó a", "tipo": [{"codificación": [{"Mostrar": "Cita"}],}], "paciente": {"referencia": "<patient/paciente-id>"}, "punto": {"iniciar": "17/09/2018 1:00:00 P.M."}, "ubicación": [{              "ubicación de": {"Mostrar": "Inmensas – ENT"},}]}}]}

* * *

Vea [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) establecer otros detalles en este campo.

## <a name="allergyintolerance"></a>AllergyIntolerance

Estos son los mínimos campos obligatorios, que son un subconjunto de los perfiles de Argonaut AllergyIntolerance:

1. Code.Text
2. Code.Coding[0]. Monitor
3. Estado

Además de los campos Argonaut, para una experiencia de usuario excelente la aplicación de los pacientes también lee los siguientes campos:

1. RecordedDate
2. Note.Text
3. Reacción [.]. Substance.Text
4. Reacción [.]. Manifestación [.]. Texto
5. Text.Div

Una búsqueda de recursos utiliza el método GET y los parámetros siguientes:

1. Paciente = \<id> paciente

Vea el siguiente ejemplo de esta llamada:

* * *

    Solicitud: Obtener <fhir-server>/AllergyIntolerance? paciente = <patient-id>
    
    Respuesta: {"resourceType": "Agrupar", "id": "<bundle id>", "tipo": "searchset", "total": 1, "entry": [{"recursos": {"resourceType": "AllergyIntolerance", "id": "<resource id>", "recordedDate": "2018-09-17T07:00:00.00 0Z","sustancia": {"texto":"Cajuil"},"estado":"confirmado","reacción": [{"sustancia": {"texto":"cajuil tuerca alergénicos extraer inyectables producto"},"manifestati en": [{"texto":"Anaphylactic reacción"}]}]}}]}

* * *

Vea [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) establecer otros detalles en este campo.

## <a name="medication-order"></a>Orden de medicación

Estos son los mínimos campos obligatorios, que son un subconjunto de los perfiles de Argonaut MedicationOrder:

1. DateWritten
2. Prescriber.Display
3. Medication.Display (si referencia)
4. Medication.Text (si concepto)

Además de los campos Argonaut, para una experiencia de usuario excelente la aplicación de los pacientes también puede leer los siguientes campos:

1. DateEnded
2. DosageInstruction.Text
3. Text.Div

Una búsqueda de recursos utiliza el método GET y los parámetros siguientes:

1. paciente =\<id> paciente
2. _Count =\<results> máx.

Vea el siguiente ejemplo de esta llamada:

* * *

    Solicitud: Obtener <fhir-server>/MedicationOrder? paciente = <patient id>&_count = 10
    
    Respuesta: {"resourceType": "Agrupar", "id": "<bundle id>", "tipo": "searchset", "total": 1, "entry": [{"recursos": {"resourceType": "MedicationOrder", "id": "<resource id>", "dateWritten": "2018-09-17", "medi cationCodeableConcept": {"texto":"Lisinopril 20 MB verbal Tablet"},"prescriber": {"Mostrar":"Jane Doe"},"dosageInstruction": [{"texto":"1 diario"}]}}]}

* * *  

Vea [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) establecer otros detalles en este campo.

## <a name="coverage"></a>Cobertura

Estos son los campos obligatorios mínimos, no están cubiertos por nosotros principales o Argonaut perfiles:

1. Paga

Una búsqueda de recursos utiliza el método GET y los parámetros siguientes:

1. paciente =\<id> paciente

Vea el siguiente ejemplo de esta llamada:

* * *

    Solicitud: Obtener la <fhir-server>/cobertura? paciente = <patient-id>
    
    Respuesta: {"resourceType": "Agrupación", "tipo": "searchset", "total": 1, "entry": [{"recursos": {"resourceType": "Cobertura", "id": "<resource id>", "plan": "No principal seguro", "suscriptor": {"referencia": "paciente / <patient-id> "}}}]}

* * *

Vea [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) establecer otros detalles en este campo.

## <a name="location"></a>Ubicación

Este recurso sólo se utiliza como una referencia en el recurso de [encontrar](#encounter) .

Vea [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) establecer otros detalles en este campo.
