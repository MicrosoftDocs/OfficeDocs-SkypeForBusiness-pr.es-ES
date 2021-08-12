---
title: Interfaz DSTU2 de integración de DSTU2 y aplicación para pacientes
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
description: Obtenga información sobre la especificación de interfaz DSTU2 en Teams, incluida la configuración o reconfiguración de un servidor FHIR para que funcione con la aplicación Microsoft Teams pacientes.
ms.custom: seo-marvel-mar2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 8ec2b1a88d99937e83bc8553f7dbcdd8d92f78b5a8e5708301147a26f0cffe4a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54308769"
---
# <a name="dstu2-interface-specification"></a>Especificación de la interfaz DSTU2

> [!NOTE]
> Desde el 30 de octubre de 2020, la aplicación Pacientes se retiró y se reemplazó por la aplicación [Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) en Teams. Los datos de la aplicación Pacientes se almacenan en el buzón de correo del grupo de Office 365 que respalda al equipo. Todos los datos asociados con la aplicación Pacientes se conservan en este grupo, pero ya no se puede acceder a ellos a través de la interfaz de usuario. Los usuarios pueden volver a crear sus listas mediante la [aplicación Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).
>
>Con Listas, los equipos del cuidado de la salud de su organización sanitaria pueden crear listas de pacientes para escenarios que van desde guardias y reuniones interdisciplinarias de equipo, hasta el seguimiento general de pacientes. Consulte la plantilla Pacientes en Listas para comenzar. Para obtener más información sobre cómo administrar la aplicación Listas en su organización, consulte [Administrar la aplicación Listas](../../manage-lists-app.md).

Configurar o volver a configurar un servidor FHIR para trabajar con la aplicación Microsoft Teams pacientes requiere comprender a qué datos necesita acceder la aplicación. El servidor FHIR debe admitir las solicitudes POST con paquetes para los siguientes recursos:

- [Paciente](#patient)
- [Observación](#observation)
- [Condición](#condition)
- [Encuentro](#encounter)
- [Alergia a la alergia](#allergyintolerance)
- [Cobertura](#coverage)
- [Pedido de medicamentos](#medication-order)
- [Ubicación](#location)

> [!NOTE]
> El recurso Paciente es el único recurso obligatorio (sin el que la aplicación no se cargará en absoluto). Sin embargo, se recomienda que el partner implemente soporte técnico para todos los recursos mencionados anteriormente según las especificaciones que se proporcionan a continuación para obtener la mejor experiencia del usuario final con la aplicación Microsoft Teams pacientes.

Las consultas de la Microsoft Teams pacientes de más de un recurso publican un paquete (LOTE) de solicitudes en la dirección URL del servidor FHIR. El servidor procesa cada solicitud y devuelve un paquete de los recursos coincidentes con cada solicitud. Para obtener más información y ejemplos, vea [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) .

Todos los siguientes recursos de FHIR deben ser accesibles mediante referencia directa de recursos.

## <a name="conformance-minimum-required-field-set"></a>Conjunto de campos mínimo de conformidad obligatorio

 El servidor FHIR debe implementar la declaración de conformidad para que tendrán un resumen fáctico de sus capacidades. Esperamos los siguientes parámetros en un servidor DSTU2 FHIR:

 - REST

    - Modo
    - Interacción
    - Recurso: Escriba
    - Seguridad: [Extensión para URI de OAuth](https://hl7.org/fhir/extension-oauth-uris.html)
   
 - FhirVersion (Nuestro código requiere esto para comprender a qué versión debemos pivotar, ya que se admiten varias versiones).

Vea [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) otros detalles sobre este conjunto de campos.

## <a name="patient"></a>Paciente

Estos son los campos mínimos necesarios, que son un subconjunto de los campos de [perfil de paciente de Argonaut:](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)

 - Name.Family
 - Name.Given
 - Género
 - FechaDe Nacimiento
 - MRN (identificador)

Además de los campos Argonaut, para una gran experiencia de usuario, la aplicación Pacientes también lee los siguientes campos:

 - Name.Use
 - Name.Prefix
 - CareProvider (Esta referencia en el recurso Paciente debe incluir los campos para mostrar que se muestran en el ejemplo siguiente).

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

Una búsqueda de recursos usa el método POST en /Patient/_search y los siguientes parámetros:

 - id
 - familia:contains=(busca todos los pacientes cuyo nombre de familia contiene el valor).
 - given=\<substring>
 - name=\<substring>
 - fecha_nacimiento=(coincidencia exacta)
 - \_recuento (número máximo de resultados que se deben devolver) <br> La respuesta debe contener el recuento total de registros devueltos como resultado de la búsqueda y el recuento lo usará la PatientsApp para limitar el número \_ de registros devueltos.
 - identificador=\<mrn>

El objetivo es poder buscar y filtrar a un paciente de la siguiente manera:

- ID: este es el id. de recurso que tiene cada recurso de FHIR.
- MRN: Este es el identificador real del paciente que el personal clínico conocería. Entendemos que este MRN se basa en el tipo de identificador dentro del recurso de identificador en FHIR
- Nombre
- Fecha de nacimiento

Vea el siguiente ejemplo de esta llamada.

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

Vea [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) otros detalles sobre este conjunto de campos.

## <a name="observation"></a>Observación

Estos son los campos mínimos necesarios, que son un subconjunto del perfil de signos vitales de Argonaut:

 - Efectivo (fecha o período)
 - Code.Coding.Code
 - ValorQuantity.Value

Además de los campos Argonaut, para una gran experiencia de usuario, la aplicación Pacientes también lee los siguientes campos:

 - Code.Coding.Display
 - ValorQuantity.Unit

Si usa observaciones de componentes, se aplica la misma lógica para cada observación de componentes.

Una búsqueda de recursos usa el método GET y los siguientes parámetros:

 - patient=\<patient id\>
 - sort:desc=\<field ex. date\>

El objetivo es poder recuperar los últimos signos vitales para un paciente, [VitalSigns.DSTU.saz] (¿observación?).

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

Vea [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) otros detalles sobre este conjunto de campos.

## <a name="condition"></a>Condición

Estos son los campos mínimos necesarios, que son un subconjunto del perfil de condición [argonauta:](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)

1. Code.Coding[0]. Mostrar

Además de los campos Argonaut, para una gran experiencia de usuario, la aplicación Pacientes también puede leer los siguientes campos:

 - Fecha grabada
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

Vea [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) otros detalles sobre este conjunto de campos.

## <a name="encounter"></a>Encuentro

Estos son los campos mínimos necesarios, que son un subconjunto de los campos "deben tener" del perfil de encuentro principal de EE. UU.:

 - Estado
 - Escriba[0]. Codificación[0]. Mostrar

Además, los siguientes campos de los campos "must support" del perfil de Encuentro principal de EE. UU.

 - Period.Start
 - Ubicación[0]. Location.Display

Una búsqueda de recursos usa el método GET y los siguientes parámetros:

 - patient=\<patient id>
 - _sort:desc=\<field ex. date>
 - _count=\<max results>

El objetivo es poder recuperar la última ubicación conocida del paciente. Cada encuentro hace referencia a un recurso de ubicación. La referencia también incluirá el campo de visualización de la ubicación. Vea el siguiente ejemplo de esta llamada.

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

Vea [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) otros detalles sobre este conjunto de campos.

## <a name="allergyintolerance"></a>AllergyIntolerance

Estos son los campos mínimos necesarios, que son un subconjunto del perfil de Alergia a argonauta:

 - Code.Text
 - Code.Coding[0]. Mostrar
 - Estado

Además de los campos Argonaut, para una gran experiencia de usuario, la aplicación Pacientes también lee los siguientes campos:

 - RecordedDate
 - Note.Text
 - Reacción[..]. Substance.Text
 - Reacción[..]. Manifestación[..]. Texto
 - Text.Div

Una búsqueda de recursos usa el método GET y los siguientes parámetros:

 - Paciente =  \<patient id>

Vea el siguiente ejemplo de esta llamada:

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

Vea [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) otros detalles sobre este conjunto de campos.

## <a name="medication-order"></a>Pedido de medicamentos

Estos son los campos mínimos necesarios, que son un subconjunto del perfil Demedicación de Argonaut:

 - DateWritten
 - Prescriptor.Display
 - Medication.Display (si referencia)
 - Medication.Text (si concepto)

Además de los campos Argonaut, para una gran experiencia de usuario, la aplicación Pacientes también puede leer los siguientes campos:

 - DateEnded
 - DosageInstruction.Text
 - Text.Div

Una búsqueda de recursos usa el método GET y los siguientes parámetros:

 - patient=\<patient id>
 - _count=\<max results>

Vea el siguiente ejemplo de esta llamada:

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

Vea [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) otros detalles sobre este conjunto de campos.

## <a name="coverage"></a>Cobertura

Estos son los campos mínimos obligatorios, no cubiertos por los perfiles de Núcleo de EE. UU. o Argonaut:

 - Pagador

Una búsqueda de recursos usa el método GET y los siguientes parámetros:

 - patient=\<patient id>

Vea el siguiente ejemplo de esta llamada:

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
    
Vea [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) otros detalles sobre este conjunto de campos.

## <a name="location"></a>Ubicación

Este recurso solo se usa como referencia en el [recurso Encuentro.](#encounter)

Vea [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) otros detalles sobre este conjunto de campos.
