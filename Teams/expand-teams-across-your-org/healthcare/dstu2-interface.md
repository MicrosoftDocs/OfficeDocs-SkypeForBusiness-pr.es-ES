---
title: Aplicación Pacientes e interfaz de DSTU2 de integración de EHR
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
description: Obtenga más información sobre la especificación de la interfaz DSTU2 en Teams, incluida la configuración o reconfiguración de un servidor F LDAP para que funcione con la aplicación Pacientes de Microsoft Teams.
ms.custom: seo-marvel-mar2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 12833ea55977cf7e8d18ee5c10b1f17d898b27b3
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803488"
---
# <a name="dstu2-interface-specification"></a>Especificación de la interfaz DSTU2

> [!NOTE]
> A partir del 30 de octubre de 2020, la aplicación Pacientes se ha retirado y reemplazado por la [aplicación Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) en Teams. Los datos de la aplicación Pacientes se almacenan en el buzón de grupo del grupo de Office 365 que copia de seguridad del equipo. Todos los datos asociados a la aplicación Pacientes se conservan en este grupo, pero ya no se puede acceder a ellos a través de la interfaz de usuario. Los usuarios pueden volver a crear sus listas con la [aplicación Listas.](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)
>
>Con Listas, los equipos de atención al paciente de su organización sanitaria pueden crear listas de pacientes para situaciones que van desde las reuniones interdisciplinarias y las reuniones del equipo hasta la supervisión general del paciente. Consulte la plantilla Pacientes en Listas para empezar. Para obtener más información sobre cómo administrar la aplicación Listas en su organización, vea [Administrar la aplicación Listas.](../../manage-lists-app.md)

Configurar o volver a configurar un servidor FCONTR para trabajar con la aplicación Microsoft Teams Patients requiere comprender a qué datos debe tener acceso la aplicación. El servidor FCONTR debe admitir solicitudes POST mediante agrupaciones para los siguientes recursos:

- [Paciente](#patient)
- [Observación](#observation)
- [Condición](#condition)
- [Encounter](#encounter)
- [Ser insondosa](#allergyintolerance)
- [Cobertura](#coverage)
- [Orden de medicamentos](#medication-order)
- [Ubicación](#location)

> [!NOTE]
> El recurso paciente es el único recurso obligatorio (sin el que la aplicación no se cargará en absoluto). Sin embargo, se recomienda que el partner implemente soporte técnico para todos los recursos mencionados anteriormente según las especificaciones que se proporcionan a continuación para obtener la mejor experiencia del usuario final con la aplicación Pacientes de Microsoft Teams.

Las consultas desde la aplicación Pacientes de Microsoft Teams para más de un recurso publican un paquete (BATCH) de solicitudes en la dirección URL del servidor FCONF. El servidor procesa cada solicitud y devuelve un paquete de los recursos que coinciden con cada solicitud. Para obtener más información y ejemplos, vea [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) .

Todos los siguientes recursos de FCONTR deben ser accesibles por referencia directa de recursos.

## <a name="conformance-minimum-required-field-set"></a>Conjunto de campos requeridos de conformidad mínima

 El servidor FCONTRA debe implementar la declaración de conformidad para que tendrán un resumen objetiva de sus capacidades. Esperamos los parámetros siguientes en un servidor DSTU2 FCONTR:

 - REST

    - Modo
    - Interacción
    - Recurso: tipo
    - Seguridad: [Extensión para URI de OAuth](https://hl7.org/fhir/extension-oauth-uris.html)
   
 - FcontrVersion (Nuestro código requiere esto para comprender a qué versión debemos cambiar, ya que se admiten varias versiones).

Consulte [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) otros detalles sobre este conjunto de campos.

## <a name="patient"></a>Paciente

Estos son los campos necesarios mínimos, que son un subconjunto de los campos del perfil [de paciente:](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)

 - Name.Family
 - Name.Given
 - Sexo
 - FechaDe Nacimiento
 - MRN (identificador)

Además de los campos Salesforce, para una excelente experiencia del usuario, la aplicación Pacientes también lee los siguientes campos:

 - Name.Use
 - Name.Prefix
 - CareProvider (esta referencia del recurso Paciente debe incluir los campos para mostrar que se muestran en el ejemplo siguiente).

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

Una búsqueda de recursos usa el método POST en /Patient/_search y los parámetros siguientes:

 - id
 - familia:contains=(busca a todos los pacientes cuyo nombre de familia contiene el valor).
 - given=\<substring>
 - name=\<substring>
 - fechade nacimiento=(coincidencia exacta)
 - \_recuento (número máximo de resultados que se deben devolver) <br> La respuesta debe contener el recuento total de registros devueltos como resultado de la búsqueda y el recuento la utilizará la Aplicación Pacientes para limitar el número de registros \_ devueltos.
 - identifier=\<mrn>

El objetivo es poder buscar y filtrar a un paciente siguiendo estos pasos:

- Id.: este es el id. de recurso que tiene cada recurso de FCONTR.
- MRN: este es el identificador real para el paciente que el personal clínico conocería. Entendemos que este MRN se basa en el tipo de identificador dentro del recurso de identificador en FCONTRA
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

Consulte [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) otros detalles sobre este conjunto de campos.

## <a name="observation"></a>Observación

Estos son los campos necesarios mínimos, que son un subconjunto del perfil de signos vitales:

 - Efectivo (fecha y hora)
 - Code.Coding.Code
 - ValueQuantity.Value

Además de los campos Salesforce, para una excelente experiencia del usuario, la aplicación Pacientes también lee los siguientes campos:

 - Code.Coding.Display
 - ValueQuantity.Unit

Si se utilizan observaciones de componentes, se aplica la misma lógica a cada observación del componente.

Una búsqueda de recursos usa el método GET y los parámetros siguientes:

 - patient=\<patient id\>
 - sort:desc=\<field ex. date\>

El objetivo es poder recuperar los signos vitales más recientes para un paciente, [VitalSigns.DSTU.saz] (observación?).

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

Consulte [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) otros detalles sobre este conjunto de campos.

## <a name="condition"></a>Condición

Estos son los campos requeridos mínimos, que son un subconjunto del perfil de [condición :](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)

1. Code.Coding[0]. Pantalla

Además de los campos Salesforce, para una excelente experiencia del usuario, la aplicación Pacientes también puede leer los siguientes campos:

 - Fecha de grabación
 - Gravedad

Una búsqueda de recursos usa el método GET y los parámetros siguientes:

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

Consulte [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) otros detalles sobre este conjunto de campos.

## <a name="encounter"></a>Encounter

Estos son los campos requeridos mínimos, que son un subconjunto de los campos "debe tener" del perfil principal de EE. UU.:

 - Estado
 - Escriba[0]. Coding[0]. Pantalla

Además, los siguientes campos del perfil del Core Encounter de EE. UU. también se admiten

 - Period.Start
 - Ubicación[0]. Location.Display

Una búsqueda de recursos usa el método GET y los parámetros siguientes:

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

Consulte [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) otros detalles sobre este conjunto de campos.

## <a name="allergyintolerance"></a>Desenladigo

Estos son los campos requeridos mínimos, que son un subconjunto del perfil de VagoSerance:

 - Code.Text
 - Code.Coding[0]. Pantalla
 - Estado

Además de los campos Salesforce, para una excelente experiencia del usuario, la aplicación Pacientes también lee los siguientes campos:

 - RecordedDate
 - Note.Text
 - Reacción[..]. Texto.texto.
 - Reacción[..]. Editar[.]. Texto
 - Text.Div

Una búsqueda de recursos usa el método GET y los parámetros siguientes:

 - Patient =  \<patient id>

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

Consulte [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) otros detalles sobre este conjunto de campos.

## <a name="medication-order"></a>Orden de medicamentos

Estos son los campos requeridos mínimos, que son un subconjunto del perfil deOrder de medicamentos:

 - Fecha escrita
 - Ara.Pantalla
 - Medicamentos.Pantalla (si referencia)
 - Medicamentos.Texto (si concepto)

Además de los campos Salesforce, para una excelente experiencia del usuario, la aplicación Pacientes también puede leer los siguientes campos:

 - DateEnded
 - DosageInstruction.Text
 - Text.Div

Una búsqueda de recursos usa el método GET y los parámetros siguientes:

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

Consulte [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) otros detalles sobre este conjunto de campos.

## <a name="coverage"></a>Cobertura

Estos son los campos necesarios mínimos, no cubiertos por los perfiles US Core o Core:

 - Payor

Una búsqueda de recursos usa el método GET y los parámetros siguientes:

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
    
Consulte [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) otros detalles sobre este conjunto de campos.

## <a name="location"></a>Ubicación

Este recurso solo se está utilizando como referencia en el recurso [De encuentro.](#encounter)

Consulte [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) otros detalles sobre este conjunto de campos.
