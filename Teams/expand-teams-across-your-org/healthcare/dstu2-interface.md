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
description: Integración de la EHR de la aplicación pacientes de Microsoft Teams
ms.openlocfilehash: 10a6b21e583b5fdd3e70857c4cfc5e7e21a7e988
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153822"
---
# <a name="dstu2-interface-specification"></a>Especificación de la interfaz DSTU2

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Para configurar o volver a configurar un servidor de FHIR para que funcione con la aplicación para pacientes de Microsoft Teams, es necesario comprender a qué datos necesita acceder la aplicación. El servidor de FHIR debe admitir solicitudes POST con paquetes para los siguientes recursos:

- [Propio](#patient)
- [Observación](#observation)
- [Condición](#condition)
- [Detect](#encounter)
- [Intolerancia de alergia](#allergyintolerance)
- [Beneficios](#coverage)
- [Orden de los medicamentos](#medication-order)
- [Ubicación](#location)

> [!NOTE]
> El recurso paciente es el único recurso obligatorio (sin que la aplicación se cargue en absoluto). Sin embargo, se recomienda que el socio implemente la compatibilidad de todos los recursos mencionados anteriormente según las especificaciones proporcionadas a continuación para obtener la mejor experiencia para el usuario final con la aplicación de pacientes de Microsoft Teams.

Las consultas de la aplicación de pacientes de Microsoft Teams para más de un recurso publican un paquete (lote) de solicitudes a la dirección URL del servidor FHIR. El servidor procesa cada solicitud y devuelve un paquete de los recursos coincidentes con cada solicitud. Para obtener más información y ejemplos, [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction)consulte.

Todos los siguientes recursos de FHIR deben ser accesibles mediante la referencia directa de recursos.

## <a name="conformance-minimum-required-field-set"></a>Conjunto de campos obligatorios mínimos de cumplimiento

 El servidor de FHIR debe implementar la declaración de conformidad para que nosotros tenga un resumen del objetivo de sus capacidades. Esperamos los siguientes parámetros en un DSTU2 FHIR Server:

1. DESCANSO
   1. Modo
   2. MOV
   3. Recurso: tipo
   4. Seguridad: [extensión para URI de OAuth](https://hl7.org/fhir/extension-oauth-uris.html)
2. FhirVersion (nuestro código requiere esto para comprender a qué versión debemos dinamizar, ya que admitimos varias versiones).

Consulte [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) para obtener más información sobre este conjunto de campos.

## <a name="patient"></a>Propio

Estos son los campos mínimos obligatorios, que son un subconjunto de los campos de [Perfil del paciente de Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) :

1. Nombre. familia
2. Nombre. dado
3. Hombres
4. FechaNacimiento
5. MRN (identificador)

Además de los campos Argonaut, para una experiencia de usuario excelente, la aplicación para pacientes también lee los siguientes campos:

1. Nombre. Use
2. Nombre. Prefix
3. CareProvider (esta referencia en el recurso paciente debe incluir los campos de visualización que se muestran en el ejemplo siguiente).

* * *

    Solicitud: Obtén <fhir-Server>/patient/<ID de paciente>
    
    Respuesta: {"resourceType": "patient", "ID": "<ID de paciente>",.
      .
      .
      "nombre": [{"use": "funcionario", "prefijo": ["Mr"], "familia": ["Chau"], "dado": ["Hugh"]}], "identificador": [{"use": "oficial", "tipo": {"código": [{"System": "https://hl7.org/fhir/v2/0203", "": ",". ",", ",", ".", ".", ",", ",": [{"careProvider": "Juana Pérez"}],} 1957-06-05 1234567

* * *

Una búsqueda de recursos usa el método POST en/patient/_search y los siguientes parámetros:

1. identificar
2. Family: contiene = (busca todos los pacientes cuyo nombre contenga el valor).
3. proporcionado =\<substring>
4. name =\<substring>
5. FechaNacimiento = (coincidencia exacta)
6. \_contar (número máximo de resultados que se deben devolver) <br> La respuesta debe contener el recuento total de registros devueltos como resultado de la búsqueda \_, y el PatientsApp usará Count para limitar el número de registros devueltos.
7. Identifier =\<MRN>

El objetivo es poder buscar y filtrar a un paciente por lo siguiente:

- ID: es el identificador de recurso que tiene cada recurso en FHIR.
- MRN: este es el identificador real del paciente que sabría el personal clínico. Entendemos que este MRN se basa en el tipo de identificador dentro del recurso Identifier en FHIR
- Nombre
- FechaNacimiento

Consulta el siguiente ejemplo de esta llamada.

* * *

    Solicitud: publique <fhir-Server>/patient/_search cuerpo de la solicitud: dado = Hugh&Family = Chau
    
    Respuesta: {"resourceType": "bundle", "ID": "<paquete-ID>",.
      .
      .
      "entrada": [{"recurso": {"resourceType": "patient", "ID": "<> de identificación de pacientes", "nombre": [{"texto": "Hugh Chau", "familia": ["Chau"], "dado": ["Hugh"]}], "género": "," hombre "," FechaNacimiento ":" coincidencias "} 1957-06-05

* * *

Consulte [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) para obtener más información sobre este conjunto de campos.

## <a name="observation"></a>Observación

Estos son los campos mínimos obligatorios, que son un subconjunto del perfil de constantes vitales de Argonaut:

 1. Vigencia (fecha o hora)
 2. Code. Coding. Code
 3. ValueQuantity. Value

Además de los campos Argonaut, para una experiencia de usuario excelente, la aplicación para pacientes también lee los siguientes campos:

 1. Code. Coding. display
 2. Unidad ValueQuantity.

Si se usan observaciones de componentes, se aplica la misma lógica para cada observación de componentes.

Una búsqueda de recursos usa el método GET y los siguientes parámetros:

1. paciente =\<ID de paciente\>
2. ordenar: DESC =\<campo ex. Posteriormente\>

El objetivo es poder recuperar los últimos signos vitales para un paciente, [VitalSigns. DSTU. Saz] (observación?).

* * *

    Solicitud: obtener <fhir-Server>/Observation? patient =<paciente-ID>&_sort:d ESC = Date&Category = invienes
    
    Respuesta: {"resourceType": "bundle", "ID": "<paquete-ID>", "escribe": "searchset", "total": 20, "Entry": [{"recurso": {"nombre de recurso": "," nombre "," nombre ":", "", "," <= ">."} ","} "," "código": {"codificación": [{"System": "http://loinc.org", "Code": "39156-5", "display": "BMI"}],}, "effectiveDateTime": "2009-12-01", "valueQuantity": {"valor": 34,4, "unidad": "kg/m2", "sistema": "http://unitsofmeasure.org", "código": "kg/m2"}},},.
        .
        .
      ] }

* * *

Consulte [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) para obtener más información sobre este conjunto de campos.

## <a name="condition"></a>Condición

Estos son los campos mínimos obligatorios, que son un subconjunto del [Perfil de condición Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):

1. Code. Coding [0]. Aparecen

Además de los campos Argonaut, para una experiencia de usuario excelente, la aplicación de pacientes también puede leer los siguientes campos:

1. Fecha de grabación
2. Gravedad

Una búsqueda de recursos usa el método GET y los siguientes parámetros:

1. paciente =\<ID de paciente>
2. _count =\<resultados máximos>

Consulte el siguiente ejemplo de esta llamada:

* * *

    Solicitud: obtener <fhir-Server>/Condition? patient =<ID de paciente>&_count = 10
    
    Respuesta: {"resourceType": "bundle", "ID": "<paquete-ID>", "tipo": "searchset", "total": "Entry": [{"Resource": {"resourceType": "Condition", "ID": "<Resource-ID>", "Code": {"codificar": [{"System": "http://snomed.info/sct", "Code": "386033004", "display": "neuropathy (Nerve Damage)"}]}, "dateRecorded": "2018-09-17", "Severity": {"Coding": [{"Syst em ":"http://snomed.info/sct"," código ":" 24484000 "," display ":" grave "}]}},}]}

* * *

Consulte [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) para obtener más información sobre este conjunto de campos.

## <a name="encounter"></a>Detect

Estos son los campos mínimos obligatorios, que son un subconjunto del núcleo de Estados Unidos y el perfil "debe tener" campos:

1. Statu
2. Escriba [0]. Codificación [0]. Aparecen

Además, los siguientes campos de la parte central de Estados Unidos tienen los campos "debe ser compatible" del perfil.

1. Start period
2. Ubicación [0]. Location. display

Una búsqueda de recursos usa el método GET y los siguientes parámetros:

1. paciente =\<ID de paciente>
2. _sort: DESC =\<campo ex. > de fecha
3. _count =\<resultados máximos>

El objetivo es poder recuperar el último lugar conocido del paciente. Cada uno de ellos hace referencia a un recurso de ubicación. La referencia también incluirá el campo de visualización de la ubicación. Consulta el siguiente ejemplo de esta llamada.
* * *

    Solicitud: obtener <fhir-Server>/Encounter? patient =<ID de paciente>&_sort:d ESC = Date&_count = 1
    
    Respuesta: {"resourceType": "paquete", "tipo": "searchset", "total": 1, "entrada": [{"recurso": <{"nombre> de usuario", "ID.": ",", "...", "nombre"; "<id>;"; ""}], "estado": "ha llegado", "tipo": [{"código": [{"Mostrar": "nombre de la agenda de usuarios con el nombre de la empresa>"}, "período": {"Start": "09/17/2018 1:00:00 PM"}, "ubicación": [{<             "ubicación": {"display": "Clinic-ENT"},}]}}]}

* * *

Consulte [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) para obtener más información sobre este conjunto de campos.

## <a name="allergyintolerance"></a>AllergyIntolerance

Estos son los campos mínimos obligatorios, que son un subconjunto del perfil de AllergyIntolerance de Argonaut:

1. Code. Text
2. Code. Coding [0]. Aparecen
3. Statu

Además de los campos Argonaut, para una experiencia de usuario excelente, la aplicación para pacientes también lee los siguientes campos:

1. RecordedDate
2. Nota. Text
3. Reacción [...]. Sustancia. texto
4. Reacción [...]. Manifesting [..]. Facturas
5. Text. div

Una búsqueda de recursos usa el método GET y los siguientes parámetros:

1. Paciente = \<ID de paciente>

Consulte el siguiente ejemplo de esta llamada:

* * *

    Solicitud: obtener <fhir-Server>/AllergyIntolerance? patient =<ID de paciente>
    
    Respuesta: {"resourceType": "bundle", "ID": "<paquete-ID>", "tipo": "searchset", "total": 1, "Entry": [{"Resource": {"resourceType": "AllergyIntolerance", "ID": "<> de identificación de recursos", "recordedDate": "2018-09-17T07:00:00.000 Z", "sustancia": {"texto": "cashew NUTS"}, "estado": "confirmado", "reacción": [{"sustancia": {"texto": "cashew NUTS allergenic el extraído producto inyectable"}, "manifestati on ": [{" texto ":" Anaphylactic reacción "}]}]}}]}

* * *

Consulte [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) para obtener más información sobre este conjunto de campos.

## <a name="medication-order"></a>Orden de los medicamentos

Estos son los campos mínimos obligatorios, que son un subconjunto del perfil de MedicationOrder de Argonaut:

1. DateWritten
2. Prescribir. Mostrar
3. Medicación. display (si Ref)
4. Medicación. Text (si concepto)

Además de los campos Argonaut, para una experiencia de usuario excelente, la aplicación de pacientes también puede leer los siguientes campos:

1. DateEnded
2. DosageInstruction. Text
3. Text. div

Una búsqueda de recursos usa el método GET y los siguientes parámetros:

1. paciente =\<ID de paciente>
2. _count =\<resultados máximos>

Consulte el siguiente ejemplo de esta llamada:

* * *

    Solicitud: obtener <fhir-Server>/MedicationOrder? patient =<ID de paciente>&_count = 10
    
    Respuesta: {"resourceType": "bundle", "ID": "<paquete-ID>", "tipo": "searchset", "total": "Entry": [{"Resource": {"resourceType": "MedicationOrder", "ID": "<Resource-ID>", "dateWritten": "2018-09-17", "premedicationCodeableConcept": {"Text": "nombre de la lisinopril de 20 MG de tableta oral"}, "prescribe": {"display": "?}]}, o bien

* * *  

Consulte [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) para obtener más información sobre este conjunto de campos.

## <a name="coverage"></a>Beneficios

Estos son los campos mínimos obligatorios, no incluidos en los perfiles de los Estados Unidos Core o Argonaut:

1. Payor

Una búsqueda de recursos usa el método GET y los siguientes parámetros:

1. paciente =\<ID de paciente>

Consulte el siguiente ejemplo de esta llamada:

* * *

    Solicitud: obtener <fhir-Server>/Coverage? patient =<ID de paciente>
    
    Respuesta: {"resourceType": "bundle", "type": "searchset", "total": 1, "entrada": [{"recurso": {"resourceType": "Coverage", "ID": "<Resource-ID>", "Plan": "sin seguro principal", "suscriptor": {"referencia": "patient/<ID de paciente>"}}}]}

* * *

Consulte [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) para obtener más información sobre este conjunto de campos.

## <a name="location"></a>Ubicación

Este recurso solo se usa como referencia en el recurso de [problemas](#encounter) .

Consulte [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) para obtener más información sobre este conjunto de campos.
