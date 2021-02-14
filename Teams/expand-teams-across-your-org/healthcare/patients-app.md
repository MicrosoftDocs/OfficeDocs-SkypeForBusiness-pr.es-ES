---
title: Información general de la aplicación Pacientes
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
description: Obtenga información sobre la integración de registros sanitarios electrónicos en la aplicación Pacientes de Microsoft Teams con las API de FLC.
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 594375959a8cd7cbbfc21c6b9d5ceb6c0f8a8dac
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803548"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a>Integración de registros sanitarios electrónicos en Microsoft Teams

> [!NOTE]
> A partir del 30 de octubre de 2020, la aplicación Pacientes se ha retirado y reemplazado por la [aplicación Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) en Teams. Los datos de la aplicación Pacientes se almacenan en el buzón de grupo del grupo de Office 365 que copia de seguridad del equipo. Todos los datos asociados a la aplicación Pacientes se conservan en este grupo, pero ya no se puede acceder a ellos a través de la interfaz de usuario. Los usuarios pueden volver a crear sus listas con la [aplicación Listas.](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)
>
>Con Listas, los equipos de cuidado de su organización sanitaria pueden crear listas de pacientes para situaciones que van desde rounds y reuniones de equipo interdisciplinarias hasta la supervisión general del paciente. Consulte la plantilla Pacientes en Listas para empezar. Para obtener más información sobre cómo administrar la aplicación Listas en su organización, vea [Administrar la aplicación Listas.](../../manage-lists-app.md)

Este artículo está destinado a un desarrollador de TI para la salud general interesado en usar las API de FLC, además de un sistema de información médica, para conectarse a Microsoft Teams. Esto habilitaría escenarios de coordinación de cuidados que coincidan con las necesidades de una organización sanitaria.

En los artículos vinculados se documentan las especificaciones de la interfaz de FLC para la aplicación Microsoft Teams Pacientes y las secciones siguientes explican lo que se requiere para configurar un servidor FLC y conectarse a la aplicación Pacientes en su entorno de desarrollo o inquilino. También debe estar familiarizado con la documentación del servidor FCONTR que ha elegido, que debe ser una de las opciones admitidas:

- Datica (a través de su [oferta de CMI)](https://datica.com/compliant-managed-integration/)
- Infor Copleaf (a través del [puente Infor FCONTR)](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html)
- Redxa (a través [del servidor R^FCONTR)](https://www.redoxengine.com/fhir/)
- Dapasoft (a [través de Corolar en FCONTR)](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/)

> [!NOTE]
> Este proceso no incluye los pasos que usan el centro de administración de Microsoft Teams o los cmdlets de PowerShell para habilitar las características. La configuración se realiza por completo en el lado del servidor/servicio FCONTRA y en el cliente de la aplicación Pacientes.

A continuación se muestra la arquitectura de la aplicación Pacientes:

![Diagrama de la arquitectura de la aplicación Pacientes](../../media/patients-app-architecture.png)

En las siguientes secciones se explican los requisitos de la capa de acceso de datos solo de FCONTR para la aplicación Pacientes que debe cumplir un servidor FCONTR (o API de F LDAP habilitada para EHR) para realizar la integración con la aplicación Pacientes, lo que incluye lo siguiente:

- Expectativas sobre la autenticación de usuario
- Requisitos técnicos y funcionales de la interfaz de integración
- Expectativas en torno al rendimiento y la confiabilidad
- Expectativas en torno a los recursos de FLC para que puedan ser compatibles con la aplicación Pacientes
- Proceso de integración y del modelo de participación esperado
- Cómo comenzar a usar la FCONTR y algunos de los desafíos comunes que se deben enfrentar con la aplicación Pacientes
- Requisitos futuros para la siguiente iteración de la aplicación Pacientes

> [!NOTE]
> En las secciones siguientes, se usa la palabra "partner" o "interoperabilidad" para hacer referencia a cualquier organización de terceros que permita la integración con sistemas EHR para la aplicación Pacientes a través de FLC y está implementando un servidor FLC para que coincida con las especificaciones enumeradas.

## <a name="functional-and-technical-requirements"></a>Requisitos técnicos y funcionales  

### <a name="authentication"></a>Autenticación  

La autorización a nivel de aplicación *sin* soporte para autorización a nivel de usuario es la forma más común de realizar transformaciones de datos y exponer conexiones a datos EHR a través de FCONTR, aunque el sistema EHR pueda implementar la autorización a nivel de usuario. El servicio de interoperabilidad (partner) obtiene acceso elevado a los datos EHR y, cuando exponen los mismos datos que los recursos de FLC adecuados, no se aplica ningún contexto de autorización al consumidor del servicio de interoperabilidad (la aplicación Pacientes) para la integración con el Servicio de interoperabilidad o la plataforma. La aplicación Pacientes no podrá exigir la autorización a nivel de usuario, pero admite la aplicación para la autenticación de aplicación entre la aplicación Pacientes y el servicio del partner de interoperabilidad.

El modelo de autenticación de aplicación a aplicación se describe a continuación:

El servicio de autenticación de servicio debe [](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)realizarse a través del flujo de credenciales de cliente de OAuth 2.0. El servicio de asociados debe proporcionar lo siguiente:

1. El servicio de partner permite a la aplicación Pacientes crear una cuenta con el partner, que permite que la aplicación Pacientes genere y sea propietario de client_id y client_secret, administrados mediante un portal de registro de autenticación en el servidor de autenticación del partner.

2. El servicio de partner es el propietario del sistema de autenticación/autorización, que acepta y comprueba (autentica) las credenciales de cliente proporcionadas y devuelve un token de acceso con sugerencia de inquilino en el ámbito, como se describe a continuación.

3. Por motivos de seguridad o en caso de infracción de secreto, la aplicación Pacientes puede volver a generar el secreto e invalidarlo o eliminarlo (por ejemplo, el mismo está disponible en Azure Portal - Registro de aplicaciones de AAD).

4. El extremo de metadatos que hospeda la instrucción de conformidad debe ser no autenticado, debe ser accesible sin el token de autenticación.

5. El servicio de asociado proporciona el punto de conexión del token para la aplicación Pacientes para solicitar un token de acceso mediante un flujo de credenciales de cliente. La dirección URL del token según el servidor de autorización debe formar parte de la instrucción de conformidad (funcionalidad) F LDAP capturada de los metadatos del servidor F LDAP, como en este ejemplo:

    ```
    {
        "resourceType": "CapabilityStatement",
        .
        .
        .
        "rest": [
            {
                "mode": "server",
                "security": {
                    "extension": [
                        {
                            "extension": [
                                {
                                    "url": "token",
                                    "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/token"
                                },
                                {
                                    "url": "authorize",
                                    "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/authorize"
                                }
                            ],
                            "url": "http://fhir-registry.smarthealthit.org/StructureDefinition/oauth-uris"
                        }
                    ],
                    "service": [
                        {
                            "coding": [
                                {
                                    "system": "https://hl7.org/fhir/ValueSet/restful-security-service",
                                    "code": "OAuth"
                                }
                            ]
                        }
                    ]
                },
                .
                .
                .
            }
        ]
    }
    ```

Una solicitud de un token de acceso consta de los siguientes parámetros:

```http
POST /token HTTP/1.1
Host: authorization-server.com

grant-type=client_credentials
&client_id=xxxxxxxxxx
&client_secret=xxxxxxxxxx
```

El servicio de partners proporciona client_id y client_secret para pacientes, administrada a través de un portal de registro de autenticación del lado del partner. El servicio de asociado proporciona el punto de conexión para solicitar el token de acceso mediante un flujo de credenciales de cliente. Una respuesta correcta debe incluir los parámetros token_type, access_token y expires_in correctos.

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a>Enrutamiento: asignación del inquilino de AAD al punto de conexión del proveedor

La aplicación Pacientes se conecta a un servicio asociado a través de un único punto de conexión. El servicio de partners es propietario y mantiene un mecanismo para asignar cada cliente de Microsoft (id. de inquilino de AAD) a un proveedor de servicios médicos correspondiente (servidor FLC) con el que el servicio de asociado esté trabajando.

Al asignar el inquilino de AAD a un punto de conexión de proveedor se usa el id. de inquilino de AAD (GUID). La aplicación Pacientes pasa el id. de inquilino dentro del ámbito, mientras solicita un token de acceso para cada solicitud. El servicio de partner mantiene la asignación del id. de inquilino al punto de conexión del proveedor y redirige las solicitudes a un punto de conexión del proveedor en función del id. de inquilino. Para ello, el partner admite la configuración por su parte (manualmente o a través de un portal como parte de la incorporación de las organizaciones proveedoras a su plataforma de interoperabilidad).

El flujo de trabajo de autenticación y enrutamiento se muestra a continuación:

![Diagrama del flujo de trabajo de autenticación y enrutamiento](../../media/Patient-app-6.png)

1. Solicitar token de acceso de aplicaciones enviando:
 
    ```
    {   grant_type: client_credentials,
        client_id: xxxxxx, 
        client_secret: xxxxxx,
        scope: {Provider Identifier, Ex: tenant ID}
    }
    ```

2. Responder con un token de aplicación:

    ```
    {  access_token: {JWT, with scope: tenant ID},
       expires_in: 156678,
       token_type: "Bearer",
    }
    ```

3. Solicitar datos protegidos con el token de Acceso.

4. Mensaje de autorización: Seleccione el servidor FCONTR adecuado al que enrutar desde el id. de inquilino en el ámbito.

5. Envía los datos protegidos de la aplicación desde el servidor FCONTR autorizado después de autenticar con el token de aplicación.

## <a name="interfaces"></a>Interfaces

Las llamadas y los campos específicos que usa la aplicación Pacientes se documentan en los artículos siguientes. Seleccione la interfaz aplicable a las API del servidor FCONTR/FCONTR.

- [Especificación de la interfaz DSTU2](dstu2-interface.md)
- [Especificación de la interfaz STU3](stu3-interface.md)

## <a name="performance-and-reliability"></a>Rendimiento y confiabilidad

Aunque la aplicación Pacientes está en versión preliminar privada, no hay ninguna garantía sobre el rendimiento de un extremo a otro. Los factores en el rendimiento incluyen las latencias relativas de todos los saltos implicados en el flujo de trabajo, empezando desde el EHR en el entorno del sistema de mantenimiento hasta el partner de interoperabilidad y su infraestructura, incluido el servidor FLC y hasta el ecosistema de Office 365 y la aplicación Pacientes.

![Ilustración del rendimiento de partners de interoperabilidad](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a>Introducción a FCONTR  

Si es nuevo en FCONTR y necesita acceder fácilmente a un servidor FCONTR que puede exponer a la interfaz de integración EHR de Microsoft Teams, Microsoft tiene un servidor F ODBC de código abierto disponible para todos los desarrolladores que los use. Consulte el artículo [¿Qué es el servidor F ODBC](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) para Azure? para obtener más información sobre el servidor F LDAP de código abierto disponible en Microsoft e implementarlo para sus organizaciones.

También puedes usar el entorno de ehr de espacio aislado abierto de HSPC para crear un EHR que también admita un servidor FCONTR abierto y usarlo para jugar con la aplicación Pacientes. Te recomendamos que leas la documentación del espacio aislado [HSPC.](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox) El espacio aislado no solo ofrece una forma fácil, orientada a la interfaz de usuario y fácil de usar para crear, agregar y editar Pacientes, sino que también ofrece varias muestras para comenzar. 
