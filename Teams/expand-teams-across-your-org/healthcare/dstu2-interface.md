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
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 15bcc5fcaff50d6d41c45ef2d38e34719ebca999
ms.sourcegitcommit: 18b5e3487ba1350c5d2e6d676a4ab582b5b638d4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "48772211"
---
# <a name="dstu2-interface-specification"></a>Especificación de la interfaz DSTU2

> [!NOTE]
> Desde el 30 de octubre de 2020, la aplicación de pacientes se ha retirado y se ha sustituido por la [aplicación listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) en Teams. Con las listas, los equipos de cuidados de la organización de la salud pueden crear listas de pacientes para escenarios que abarcan desde rondas y reuniones interdisciplinarias hasta supervisión general de pacientes. Consulte la plantilla patients en listas para comenzar. Para obtener más información sobre cómo administrar la aplicación listas de su organización, vea [administrar la aplicación listas](../../manage-lists-app.md) .

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

Las consultas de la aplicación de pacientes de Microsoft Teams para más de un recurso publican un paquete (lote) de solicitudes a la dirección URL del servidor FHIR. El servidor procesa cada solicitud y devuelve un paquete de los recursos coincidentes con cada solicitud. Para obtener más información y ejemplos, consulte [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) .

Todos los siguientes recursos de FHIR deben ser accesibles mediante la referencia directa de recursos.

## <a name="conformance-minimum-required-field-set"></a>Conjunto de campos obligatorios mínimos de cumplimiento

 El servidor de FHIR debe implementar la declaración de conformidad para que nosotros tenga un resumen del objetivo de sus capacidades. Esperamos los siguientes parámetros en un DSTU2 FHIR Server:

 - DESCANSO

    - Modo
    - MOV
    - Recurso: tipo
    - Seguridad: [extensión para URI de OAuth](https://hl7.org/fhir/extension-oauth-uris.html)
   
 - FhirVersion (nuestro código requiere esto para comprender a qué versión debemos dinamizar, ya que admitimos varias versiones).

Consulte [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) para obtener más información sobre este conjunto de campos.

## <a name="patient"></a>Propio

Estos son los campos mínimos obligatorios, que son un subconjunto de los campos de [Perfil del paciente de Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) :

 - Nombre. familia
 - Nombre. dado
 - Hombres
 - FechaNacimiento
 - MRN (identificador)

Además de los campos Argonaut, para una experiencia de usuario excelente, la aplicación para pacientes también lee los siguientes campos:

 - Nombre. Use
 - Nombre. Prefix
 - CareProvider (esta referencia en el recurso paciente debe incluir los campos de visualización que se muestran en el ejemplo siguiente).

    ```
    Request:
    GET <fhir-server>/Patient/<patient-id>
    
    Response:
    {
      "resourceType": "Patient",
      "id": "<patient-id>",
      .
      .
      .
      "name": [
        {
          "use": "official",
          "prefix": [ "Mr" ],
          "family": [ "Chau" ],
          "given": [ "Hugh" ]
        }
      ],
      "identifier": [
        {
          "use": "official",
          "type": {
            "coding": [
              {
                "system": "https://hl7.org/fhir/v2/0203",
                "code": "MR"
              }
            ]
          },
          "value": "1234567"
        }
      ],
      "gender": "male",
      "birthDate": "1957-06-05",
      "careProvider": [{ "display": "Jane Doe" }],
    }
    ```

Una búsqueda de recursos usa el método POST en/patient/_search y los siguientes parámetros:

 - identificar
 - Family: contiene = (busca todos los pacientes cuyo nombre contenga el valor).
 - dado =\<substring>
 - Name =\<substring>
 - FechaNacimiento = (coincidencia exacta)
 - \_contar (número máximo de resultados que se deben devolver) <br> La respuesta debe contener el recuento total de registros devueltos como resultado de la búsqueda, y \_ el PatientsApp usará Count para limitar el número de registros devueltos.
 - Identifier =\<mrn>

El objetivo es poder buscar y filtrar a un paciente por lo siguiente:

- ID: es el identificador de recurso que tiene cada recurso en FHIR.
- MRN: este es el identificador real del paciente que sabría el personal clínico. Entendemos que este MRN se basa en el tipo de identificador dentro del recurso Identifier en FHIR
- Nombre
- FechaNacimiento

Consulta el siguiente ejemplo de esta llamada.

```
Request:
POST <fhir-server>/Patient/_search
Request Body:
given=hugh&family=chau

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  .
  .
  .
  "entry": [
    {
      "resource": {
        "resourceType": "Patient",
        "id": "<patient-id>",
        "name": [
          {
            "text": "Hugh Chau",
            "family": [ "Chau" ],
            "given": [ "Hugh" ]
          }
        ],
        "gender": "male",
        "birthDate": "1957-06-05"
      },
      "search": {
        "mode": "match"
      }
    }
  ]
}
```

Consulte [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) para obtener más información sobre este conjunto de campos.

## <a name="observation"></a>Observación

Estos son los campos mínimos obligatorios, que son un subconjunto del perfil de constantes vitales de Argonaut:

 - Vigencia (fecha o hora)
 - Code. Coding. Code
 - ValueQuantity. Value

Además de los campos Argonaut, para una experiencia de usuario excelente, la aplicación para pacientes también lee los siguientes campos:

 - Code. Coding. display
 - Unidad ValueQuantity.

Si se usan observaciones de componentes, se aplica la misma lógica para cada observación de componentes.

Una búsqueda de recursos usa el método GET y los siguientes parámetros:

 - paciente =\<patient id\>
 - ordenar: DESC =\<field ex. date\>

El objetivo es poder recuperar los últimos signos vitales para un paciente, [VitalSigns. DSTU. Saz] (observación?).

```
Request:
GET <fhir-server>/Observation?patient=<patient-id>&_sort:desc=date&category=vital-signs

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 20,
  "entry": [
    {
      "resource": {
        "resourceType": "Observation",
        "id": "<resource-id>",
        "category": {
          "coding": [ { code": "vital-signs" } ],
        },
        "code": {
          "coding": [
            {
              "system": "http://loinc.org",
              "code": "39156-5",
              "display": "bmi"
            }
          ],
        },
        "effectiveDateTime": "2009-12-01",
        "valueQuantity": {
          "value": 34.4,
          "unit": "kg/m2",
          "system": "http://unitsofmeasure.org",
          "code": "kg/m2"
        }
      },
    },
    .
    .
    .
  ]
}
```

Consulte [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) para obtener más información sobre este conjunto de campos.

## <a name="condition"></a>Condición

Estos son los campos mínimos obligatorios, que son un subconjunto del [Perfil de condición Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):

1. Code. Coding [0]. Aparecen

Además de los campos Argonaut, para una experiencia de usuario excelente, la aplicación de pacientes también puede leer los siguientes campos:

 - Fecha de grabación
 - Gravedad

Una búsqueda de recursos usa el método GET y los siguientes parámetros:

 - paciente =\<patient id>
 - _count =\<max results>

Consulte el siguiente ejemplo de esta llamada:

```
Request:
GET <fhir-server>/Condition?patient=<patient-id>&_count=10

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "Condition",
        "id": "<resource-id>",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "386033004",
              "display": "Neuropathy (nerve damage)"
            }
          ]
        },
        "dateRecorded": "2018-09-17",
        "severity": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "24484000",
              "display": "Severe"
            }
          ]
        }
      },
    }
  ]
}
```

Consulte [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) para obtener más información sobre este conjunto de campos.

## <a name="encounter"></a>Detect

Estos son los campos mínimos obligatorios, que son un subconjunto del núcleo de Estados Unidos y el perfil "debe tener" campos:

 - Statu
 - Escriba [0]. Codificación [0]. Aparecen

Además, los siguientes campos de la parte central de Estados Unidos tienen los campos "debe ser compatible" del perfil.

 - Start period
 - Ubicación [0]. Location. display

Una búsqueda de recursos usa el método GET y los siguientes parámetros:

 - paciente =\<patient id>
 - _sort: DESC =\<field ex. date>
 - _count =\<max results>

El objetivo es poder recuperar el último lugar conocido del paciente. Cada uno de ellos hace referencia a un recurso de ubicación. La referencia también incluirá el campo de visualización de la ubicación. Consulta el siguiente ejemplo de esta llamada.

```
Request:
GET <fhir-server>/Encounter?patient=<patient-id>&_sort:desc=date&_count=1

Response:
{
  "resourceType": "Bundle",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "Encounter",
        "id": "<resource-id>",
        "identifier": [{ "use": "official", "value": "<id>" }],
        "status": "arrived",
        "type": [
          {
            "coding": [{ "display": "Appointment" }],
          }
        ],
        "patient": { "reference": "Patient/<patient-id>" },
        "period": { "start": "09/17/2018 1:00:00 PM" },
        "location": [
          {
            "location": { "display": "Clinic - ENT" },
          }
        ]
      }
    }
  ]
}
```

Consulte [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) para obtener más información sobre este conjunto de campos.

## <a name="allergyintolerance"></a>AllergyIntolerance

Estos son los campos mínimos obligatorios, que son un subconjunto del perfil de AllergyIntolerance de Argonaut:

 - Code. Text
 - Code. Coding [0]. Aparecen
 - Statu

Además de los campos Argonaut, para una experiencia de usuario excelente, la aplicación para pacientes también lee los siguientes campos:

 - RecordedDate
 - Nota. Text
 - Reacción [...]. Sustancia. texto
 - Reacción [...]. Manifesting [..]. Facturas
 - Text. div

Una búsqueda de recursos usa el método GET y los siguientes parámetros:

 - Paciente =  \<patient id>

Consulte el siguiente ejemplo de esta llamada:

```
Request:
GET <fhir-server>/AllergyIntolerance?patient=<patient-id>

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "AllergyIntolerance",
        "id": "<resource-id>",
        "recordedDate": "2018-09-17T07:00:00.000Z",
        "substance": {
          "text": "Cashew nuts"
        },
        "status": "confirmed",
        "reaction": [
          {
            "substance": {
              "text": "cashew nut allergenic extract Injectable Product"
            },
            "manifestation": [
              {
                "text": "Anaphylactic reaction"
              }
            ]
          }
        ]
      }
    }
  ]
}
```

Consulte [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) para obtener más información sobre este conjunto de campos.

## <a name="medication-order"></a>Orden de los medicamentos

Estos son los campos mínimos obligatorios, que son un subconjunto del perfil de MedicationOrder de Argonaut:

 - DateWritten
 - Prescribir. Mostrar
 - Medicación. display (si Ref)
 - Medicación. Text (si concepto)

Además de los campos Argonaut, para una experiencia de usuario excelente, la aplicación de pacientes también puede leer los siguientes campos:

 - DateEnded
 - DosageInstruction. Text
 - Text. div

Una búsqueda de recursos usa el método GET y los siguientes parámetros:

 - paciente =\<patient id>
 - _count =\<max results>

Consulte el siguiente ejemplo de esta llamada:

```
Request:
GET <fhir-server>/MedicationOrder?patient=<patient-id>&_count=10

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "MedicationOrder",
        "id": "<resource-id>",
        "dateWritten": "2018-09-17",
        "medicationCodeableConcept": {
          "text": "Lisinopril 20 MG Oral Tablet"
        },
        "prescriber": {
          "display": "Jane Doe"
        },
        "dosageInstruction": [
          {
            "text": "1 daily"
          }
        ]
      }
    }
  ]
}
```

Consulte [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) para obtener más información sobre este conjunto de campos.

## <a name="coverage"></a>Beneficios

Estos son los campos mínimos obligatorios, no incluidos en los perfiles de los Estados Unidos Core o Argonaut:

 - Payor

Una búsqueda de recursos usa el método GET y los siguientes parámetros:

 - paciente =\<patient id>

Consulte el siguiente ejemplo de esta llamada:

```
Request:
GET <fhir-server>/Coverage?patient=<patient-id>

Response:
{
  "resourceType": "Bundle",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "Coverage",
        "id": "<resource-id>",
        "plan": "No Primary Insurance",
        "subscriber": { "reference": "Patient/<patient-id>" }
      }
    }
  ]
}
```
    
Consulte [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) para obtener más información sobre este conjunto de campos.

## <a name="location"></a>Ubicación

Este recurso solo se usa como referencia en el recurso de [problemas](#encounter) .

Consulte [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) para obtener más información sobre este conjunto de campos.
