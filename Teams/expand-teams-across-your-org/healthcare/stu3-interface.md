---
title: Interfaz STU3 de integración de EHR y aplicación para pacientes
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
description: Obtenga información sobre la integración de registros de estado electrónicos en la aplicación Microsoft Teams pacientes y la especificación de interfaz de STU3.
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 4e20619badb2509d0a90f396563a98796e718e2f
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803498"
---
# <a name="stu3-interface-specification"></a>Especificación de la interfaz STU3

> [!NOTE]
> Desde el 30 de octubre de 2020, la aplicación Pacientes se retiró y se reemplazó por la aplicación [Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) en Teams. Los datos de la aplicación Pacientes se almacenan en el buzón de correo del grupo de Office 365 que respalda al equipo. Todos los datos asociados con la aplicación Pacientes se conservan en este grupo, pero ya no se puede acceder a ellos a través de la interfaz de usuario. Los usuarios pueden volver a crear sus listas mediante la [aplicación Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).
>
>Con Listas, los equipos del cuidado de la salud de su organización sanitaria pueden crear listas de pacientes para escenarios que van desde guardias y reuniones interdisciplinarias de equipo, hasta el seguimiento general de pacientes. Consulte la plantilla Pacientes en Listas para comenzar. Para obtener más información sobre cómo administrar la aplicación Listas en su organización, consulte [Administrar la aplicación Listas](../../manage-lists-app.md).

Configurar o volver a configurar un servidor FHIR para trabajar con la aplicación Microsoft Teams pacientes requiere comprender a qué datos necesita acceder la aplicación. El servidor FHIR debe admitir las solicitudes POST con paquetes para los siguientes recursos:

- [Paciente](#patient)
- [Observación](#observation)
- [Condición](#condition)
- [Encuentro](#encounter)
- [Intolerancia a la alergia](#allergyintolerance)
- [Cobertura](#coverage)
- [Declaración de medicamentos](#medication-request) (reemplaza el MedicationOrder en la versión DSTU2 de PatientsApp)
- Ubicación (la información necesaria de este recurso se puede incluir en Encuentro)

> [!NOTE]
> El recurso Paciente es el único recurso obligatorio (sin el que la aplicación no se cargará en absoluto); Sin embargo, se recomienda que el partner implemente soporte técnico para todos los recursos mencionados anteriormente según las especificaciones que se proporcionan a continuación para obtener la mejor experiencia del usuario final con la aplicación Microsoft Teams pacientes.

Las consultas de la aplicación Microsoft Teams pacientes de más de un recurso deberán publicar un paquete (LOTE) de solicitudes en la dirección URL del servidor FHIR. El servidor procesará cada solicitud y devolverá un paquete de los recursos coincidentes con cada solicitud. Para obtener más información y ejemplos, vea [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) .

## <a name="capability-statement"></a>Instrucción De funcionalidad

Estos son los campos mínimos necesarios:

 - REST

    - Modo
    - Interacción
    - Recurso: Escriba
    - Seguridad: [Extensión para URI de OAuth](https://hl7.org/fhir/extension-oauth-uris.html)
    
 - FhirVersion (Nuestro código requiere esto para comprender a qué versión debemos pivotar).

Vea [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) otros detalles sobre este conjunto de campos.

## <a name="patient"></a>Paciente

Estos son los campos mínimos necesarios, que son un subconjunto de los campos de perfil de pacientes de Argonaut:

 - Name.Given
 - Name.Family
 - Género
 - FechaDe Nacimiento
 - MRN (identificador)

Además de los campos [De argonauta,](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)para una gran experiencia de usuario, la aplicación Pacientes también puede leer los siguientes campos:

 - Name.Use
 - Name.Prefix
 - [GeneralPractitioner]: la referencia de GeneralPractitioner debe incluirse en el recurso Paciente (solo para mostrar)

Una búsqueda de recursos usa el método POST en /Patient/_search y los siguientes parámetros:

 - id
 - family=(busca todos los pacientes cuyo nombre de familia contiene el valor)
 - given=\<substring>
 - fecha_nacimiento=(coincidencia exacta)
 - gender=(valores que son uno de los géneros administrativos)
 - \_recuento (número máximo de resultados que se deben devolver) <br> La respuesta debe contener el recuento total de registros devueltos como resultado de la búsqueda y el recuento lo usará la PatientsApp para limitar el número \_ de registros devueltos.
 - identificador=\<mrn>

El objetivo es poder buscar y filtrar a un paciente de la siguiente manera:

- ID: este es el id. de recurso que tiene cada recurso de FHIR.
- MRN: Este es el identificador real del paciente que el personal clínico conocería. Entendemos que este MRN se basa en el tipo de identificador dentro del recurso de identificador en FHIR.
- Nombre
- Fecha de nacimiento

Vea el siguiente ejemplo de la llamada:

```
Request:
POST <fhir-server>/Patient/_search
Request Body:
given=ruth&family=black

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "meta": {
    "lastUpdated": "2019-01-14T23:44:45.052+00:00"
  },
  "type": "searchset",
  "total": 1,
  "link": [
    {
      "relation": "self",
      "url": <fhir-server>/Patient/_search"
    }
  ],
  "entry": [
    {
      "fullUrl": <fhir-server>/Patient/<patient-id>",
      "resource": {
        "resourceType": "Patient",
        "id": "<patient-id>",
        "meta": {
          "versionId": "1",
          "lastUpdated": "2017-10-18T18:32:37.000+00:00"
        },
        "text": {
          "status": "generated",
          "div": "<div>\n        <p>Ruth Black</p>\n      </div>"
        },
        "identifier": [
          {
            "use": "usual",
            "type": {
              "coding": [
                {
                  "system": "https://hl7.org/fhir/v2/0203",
                  "code": "MR",
                  "display": "Medical record number",
                  "userSelected": false
                }
              ],
              "text": "Medical record number"
            },
            "system": "http://hospital.smarthealthit.org",
            "value": "1234567"
          }
        ],
        "active": true,
        "name": [
          {
            "use": "official",
            "family": "Black",
            "given": [
              "Ruth",
              "C."
            ]
          }
        ],
        "telecom": [
          {
            "system": "phone",
            "value": "800-599-2739",
            "use": "home"
          },
          {
            "system": "phone",
            "value": "800-808-7785",
            "use": "mobile"
          },
          {
            "system": "email",
            "value": "ruth.black@example.com"
          }
        ],
        "gender": "female",
        "birthDate": "1951-08-23",
        "address": [
          {
            "use": "home",
            "line": [
              "26 South RdApt 22"
            ],
            "city": "Sapulpa",
            "state": "OK",
            "postalCode": "74066",
            "country": "USA"
          }
        ]
      },
      "search": {
        "mode": "match"
      }
    }
  ]
}
```

```
Request:
GET <fhir-server>/Patient/<patient-id>

Response:
{
  "resourceType": "Patient",
  "id": "<patient-id>",
  "identifier": [
    {
      "use": "usual",
      "type": {
        "coding": [
          {
            "system": "https://hl7.org/fhir/v2/0203",
            "code": "MR",
          }
        ],
        "text": "Medical record number"
      },
      "value": "1234567"
    }
  ],
  "name": [
    {
      "use": "official",
      "family": "Adams",
      "given": [ "Daniel", "X." ]
    }
  ],
  "gender": "male",
  "birthDate": "1925-12-23",
}
```

Vea [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) otros detalles sobre este conjunto de campos.

## <a name="observation"></a>Observación

Estos son los campos mínimos necesarios, que son un subconjunto del perfil [Vital-Signs argonauta.](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)

 - Efectivo (fecha o período)
 - Code.Coding.Code
 - ValorQuantity.Value

Además de los campos Argonaut, para una gran experiencia de usuario, la aplicación Pacientes también puede leer los siguientes campos:

 - Code.Coding.Display
 - ValorQuantity.Unit

Una búsqueda de recursos usa el método GET y los siguientes parámetros:

 - patient=\<patient id>
 - _sort=-date
 - categoría (consultaremos "category=vital-signs") para recuperar la lista de signos vitales.

Consulte este ejemplo de la llamada:

```
Request:
GET <fhir-server>/Observation?patient=<patient-id>&category=vital-signs

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
        "category": [
          {
            "coding": [
              {
                "system": "https://hl7.org/fhir/observation-category",
                "code": "vital-signs"
              }
            ],
          }
        ],
        "code": {
          "coding": [
            {
              "system": "http://loinc.org",
              "code": "8867-4",
              "display": "heart_rate"
            }
          ]
        },
        "effectiveDateTime": "2009-04-08T00:00:00-06:00",
        "valueQuantity": {
          "value": 72.0,
          "unit": "{beats}/min",
          "system": "http://unitsofmeasure.org",
        }
      }
    },
    .
    .
    .
  ]
}
```

Vea [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) otros detalles sobre este conjunto de campos.

## <a name="condition"></a>Condición

Estos son los campos mínimos necesarios, que son un subconjunto del perfil de condición [Argonaut.](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)

 - Code.Coding[0]. Mostrar

Además de los campos Argonaut, para una gran experiencia de usuario, la aplicación Pacientes también puede leer los siguientes campos:

 - AssertedDate
 - Gravedad

Una búsqueda de recursos usa el método GET y los siguientes parámetros:

 - patient=\<patient id>
 - _count=\<max results>

Vea el siguiente ejemplo de esta llamada:

```
Request:
GET <fhir-server>/Condition?patient=<patient-id>&_count=10

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 2,
  "entry": [
    {
      "resource": {
        "resourceType": "Condition",
        "id": "<resource-id>",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "185903001",
              "display": "Needs influenza immunization",
            }
          ]
        },
        "severity": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "24484000",
              "display": "Severe"
            }
          ]
        },
        "assertedDate": "2018-04-04"
      }
    },
    .
    .
    .
  ]
}
```

Vea [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) otros detalles sobre este conjunto de campos.

## <a name="encounter"></a>Encuentro

Estos son los campos mínimos obligatorios, que son un subconjunto de [los](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) campos "must have" del perfil de encuentro principal de EE. UU.).

 - Estado
 - Escriba[0]. Codificación[0]. Mostrar

Además, los siguientes campos del perfil de encuentro principal de EE. UU. "deben admitir":

 - Period.Start
 - Ubicación[0]. Location.Display

Una búsqueda de recursos usa el método GET y los siguientes parámetros:

 - patient=\<patient id>
 - _sort:desc=\<field ex. date>
 - _count=\<max results>

El objetivo es poder recuperar la última ubicación conocida del paciente. Cada encuentro hace referencia a un recurso de ubicación. La referencia también incluirá el campo de visualización de la ubicación.

Vea [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) otros detalles sobre este conjunto de campos.

## <a name="allergyintolerance"></a>AllergyIntolerance

Estos son los campos mínimos necesarios, que son un subconjunto del perfil [de Alergia a argonauta:](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html)

 - Code.Text
 - Code.Coding[0]. Mostrar
 - ClinicalStatus/VerificationStatus (leemos ambos)

Además de los campos Argonaut, para una gran experiencia de usuario, la aplicación Pacientes también puede leer el siguiente campo:

 - AssertedDate
 - Note.Text
 - Reacción
    - Sustancia (un elemento de codificación)
    - Manifestación (un elemento de codificación)

Una búsqueda de recursos usa el método GET y los siguientes parámetros:

 - Paciente =  \<patient id>

Vea el siguiente ejemplo de la llamada: 

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
        "clinicalStatus": "active",
        "verificationStatus": "confirmed",
        "code": {
          "coding": [
            {
              "system": "http://rxnav.nlm.nih.gov/REST/Ndfrt",
              "code": "N0000175503",
              "display": "sulfonamide antibacterial",
            }
          ],
          "text": "sulfonamide antibacterial"
        },
        "assertedDate": "2018-01-01T00:00:00-07:00",
        "reaction": [
          {
            "manifestation": [
              {
                "coding": [
                  {
                    "system": "http://snomed.info/sct",
                    "code": "271807003",
                    "display": "skin rash",
                  }
                ],
                "text": "skin rash"
              }
            ],
          }
        ]
      }
    }
  ]
}
```

Vea [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) otros detalles sobre este conjunto de campos.

## <a name="medication-request"></a>Solicitud de medicación

Estos son los campos mínimos necesarios, que son un subconjunto del perfil de solicitud de medicamentos principales de EE. [UU.](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):

 - Medication.Display (si referencia)
 - Medication.Text (si CodableConcept)
 - AuthoredOn
 - Requester.Agent.Display

Además de los campos Ee.UU. Core, para una gran experiencia de usuario, la aplicación Pacientes también puede leer los siguientes campos:

 - DosageInstruction[..]. Texto
 - Texto

Una búsqueda de recursos usa el método GET y los siguientes parámetros:

 - patient=\<patient id>
 - _count=\<max results>

Vea [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) otros detalles sobre este conjunto de campos.

## <a name="coverage"></a>Cobertura

Estos son los campos mínimos obligatorios, no cubiertos por los perfiles de Núcleo de EE. UU. o Argonaut:

 - Agrupación, al menos un elemento con
    - GroupDisplay
    - PlanDisplay
 - Punto
 - SubscriberId

Una búsqueda de recursos usa el método GET y los siguientes parámetros:

 - Paciente = \<patient id>

Vea [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) otros detalles sobre este conjunto de campos.
