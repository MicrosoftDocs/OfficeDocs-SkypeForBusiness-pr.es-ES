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
description: Obtenga información sobre la integración de registros electrónicos de atención sanitaria en la aplicación Pacientes de Microsoft Teams con API de FHIR.
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 2b4878f67b7738a13e3c1385ee0713d6e3e3d481
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096214"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a>Integración de los registros sanitarios electrónicos en Microsoft Teams

> [!NOTE]
> Desde el 30 de octubre de 2020, la aplicación Pacientes se retiró y se reemplazó por la aplicación [Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) en Teams. Los datos de la aplicación Pacientes se almacenan en el buzón de correo del grupo de Office 365 que respalda al equipo. Todos los datos asociados con la aplicación Pacientes se conservan en este grupo, pero ya no se puede acceder a ellos a través de la interfaz de usuario. Los usuarios pueden volver a crear sus listas mediante la [aplicación Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).
>
>Con Listas, los equipos del cuidado de la salud de su organización sanitaria pueden crear listas de pacientes para escenarios que van desde guardias y reuniones interdisciplinarias de equipo, hasta el seguimiento general de pacientes. Consulte la plantilla Pacientes en Listas para comenzar. Para obtener más información sobre cómo administrar la aplicación Listas en su organización, consulte [Administrar la aplicación Listas](../../manage-lists-app.md).

Este artículo está destinado a un desarrollador de TI de salud general interesado en usar las API de FHIR en la parte superior de un sistema de información médica para conectarse a Microsoft Teams. Esto habilitaría escenarios de coordinación asistencial que coincidan con las necesidades de una organización sanitaria.

En los artículos vinculados se documentan las especificaciones de la interfaz FHIR para la aplicación Pacientes de Microsoft Teams y, a continuación, se explica qué es necesario para configurar un servidor FHIR y conectarse a la aplicación Pacientes en su entorno de desarrollo o inquilino. También tendrá que estar familiarizado con la documentación del servidor FHIR que ha elegido, que debe ser una de las opciones admitidas:

- Datica (a través de su [oferta CMI)](https://datica.com/compliant-managed-integration/)
- Infor Cloverleaf (a través del [puente Infor FHIR)](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html)
- Redox (a través del [servidor R^FHIR)](https://www.redoxengine.com/fhir/)
- Dapasoft (a [través de Corolar en FHIR)](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/)

> [!NOTE]
> Este proceso no incluye los pasos que usan el Centro de administración de Microsoft Teams o los cmdlets de PowerShell para habilitar las características. La configuración se realiza por completo en el servidor/servicio FHIR y en el cliente de la aplicación Pacientes.

A continuación se muestra la arquitectura de la aplicación Pacientes:

![Diagrama de la arquitectura de la aplicación Pacientes](../../media/patients-app-architecture.png)

En las secciones siguientes se explican los requisitos de la capa de acceso a datos solo FHIR para la aplicación Pacientes que debe cumplir un servidor FHIR (o API FHIR habilitadas para EHR) para poder integrarse con la aplicación Pacientes, incluidos los siguientes:

- Expectativas en torno a la autenticación de usuario
- Requisitos funcionales y técnicos de la interfaz de integración
- Expectativas en torno al rendimiento y la confiabilidad
- Expectativas en torno a los recursos de FHIR que se admiten para la aplicación Pacientes
- Proceso de integración y el modelo de participación esperado
- Cómo empezar a usar FHIR y algunos desafíos comunes a los que se enfrenta la aplicación Pacientes
- Requisitos futuros para la siguiente iteración de la aplicación Pacientes

> [!NOTE]
> En las secciones siguientes, se usa la palabra "partner" o "Partner de interoperabilidad" para hacer referencia a cualquier organización de terceros que permita la integración en sistemas EHR para la aplicación Pacientes a través de FHIR e implemente un servidor FHIR para que coincida con las especificaciones enumeradas.

## <a name="functional-and-technical-requirements"></a>Requisitos técnicos y funcionales  

### <a name="authentication"></a>Autenticación  

La autorización  a nivel de aplicación sin compatibilidad con la autorización de nivel de usuario es la forma más común de realizar transformaciones de datos y exponer conexiones a datos EHR a través de FHIR, aunque el sistema EHR pueda implementar la autorización de nivel de usuario. El servicio de interoperabilidad (partner) obtiene acceso elevado a los datos EHR y, cuando exponen los mismos datos que los recursos FHIR adecuados, no se pasa ningún contexto de autorización al consumidor de servicios de interoperabilidad (la aplicación Pacientes) que se integra con el servicio de interoperabilidad o la plataforma. La aplicación Pacientes no podrá exigir la autorización de nivel de usuario, pero sí admite la autenticación de aplicaciones entre la aplicación Pacientes y el servicio del partner de interoperabilidad.

El modelo de autenticación de aplicación a aplicación se describe a continuación:

La autenticación de servicio al servicio debe realizarse a través del flujo de credenciales de cliente [de](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)OAuth 2.0. El servicio de partners debe proporcionar lo siguiente:

1. El servicio partner permite a la aplicación Pacientes crear una cuenta con el partner, lo que permite a la aplicación Pacientes generar y ser el propietario de client_id y client_secret, administrados a través de un portal de registro de autenticación en el servidor de autenticación del partner.

2. El servicio partner es el propietario del sistema de autenticación o autorización, que acepta y comprueba (autentica) las credenciales de cliente proporcionadas y devuelve un token de acceso con sugerencia de inquilino en el ámbito, como se describe a continuación.

3. Por motivos de seguridad o en caso de una infracción secreta, la aplicación Pacientes puede volver a generar el secreto e invalidar o eliminar el secreto antiguo (ejemplo del mismo está disponible en Azure Portal: registro de aplicaciones de AAD).

4. El punto de conexión de metadatos que hospeda la instrucción de conformidad debe no autenticarse, debe ser accesible sin token de autenticación.

5. El servicio de partners proporciona el punto de conexión de token para que la aplicación Pacientes solicite un token de acceso con un flujo de credenciales de cliente. La dirección URL del token según el servidor de autorización debe formar parte de la instrucción de conformidad (capacidad) FHIR capturada de metadatos en el servidor FHIR como en este ejemplo:

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

El servicio de partners proporciona client_id y client_secret aplicación para pacientes, administrada a través de un portal de registro de autenticación del lado del partner. El servicio partner proporciona el punto de conexión para solicitar el token de acceso con un flujo de credenciales de cliente. Una respuesta correcta debe incluir los token_type, access_token y expires_in parámetros.

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a>Enrutamiento: Asignación de inquilino de AAD al punto de conexión del proveedor

La aplicación Pacientes se conecta a un servicio asociado a través de un único punto de conexión. El servicio de partners es el propietario y mantiene un mecanismo para asignar cada cliente de Microsoft (Id. de inquilino de AAD) a un proveedor de atención sanitaria (servidor FHIR) correspondiente con el que trabaja el servicio de partners.

La asignación del inquilino de AAD a un punto de conexión de proveedor usa el Id. de inquilino de AAD (GUID). La aplicación Pacientes pasa el id. de inquilino en el ámbito, mientras solicita un token de acceso para cada solicitud. El servicio de partners mantiene la asignación del id. de inquilino al punto de conexión del proveedor y redirige las solicitudes a un punto de conexión de proveedor en función del id. de inquilino. Para ello, el partner admite la configuración en su extremo (manualmente o a través de un portal como parte de la incorporación de organizaciones de proveedores a su plataforma de interoperabilidad).

A continuación se muestra el flujo de trabajo Autenticación y enrutamiento:

![Diagrama del flujo de trabajo de autenticación y enrutamiento](../../media/Patient-app-6.png)

1. Solicitar un token de acceso a la aplicación enviando:
 
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

3. Solicitar datos protegidos con el token de Access.

4. Mensaje de autorización: Seleccione el servidor FHIR adecuado al que dirigirse desde el id. de inquilino en el ámbito.

5. Envía los datos protegidos de la aplicación desde el servidor FHIR autorizado después de autenticar con el token de aplicación.

## <a name="interfaces"></a>Interfaces

Las llamadas y campos específicos usados por la aplicación Pacientes se documentan en los siguientes artículos. Seleccione la interfaz aplicable a su servidor FHIR/API de FHIR.

- [Especificación de la interfaz DSTU2](dstu2-interface.md)
- [Especificación de la interfaz STU3](stu3-interface.md)

## <a name="performance-and-reliability"></a>Rendimiento y confiabilidad

Aunque la aplicación Pacientes está en versión preliminar privada, no hay garantías sobre el rendimiento de un extremo a otro. Los factores de rendimiento incluyen las latencias relativas de todos los saltos implicados en el flujo de trabajo, empezando desde el EHR en el entorno del sistema de salud, hasta el partner de interoperabilidad y su infraestructura, incluido el servidor FHIR y hasta el ecosistema de Office 365 y la aplicación Pacientes.

![Ilustración del rendimiento de los partners de interoperabilidad](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a>Introducción a FHIR  

Si es nuevo en FHIR y necesita un acceso sencillo a un servidor FHIR que puede exponer a la interfaz de integración de EHR de Microsoft Teams, Microsoft tiene un servidor FHIR de código abierto disponible para todos los desarrolladores. Consulte el artículo [¿Qué es FHIR Server para Azure?](/azure/healthcare-apis/overview-open-source-server) para obtener más información sobre el servidor FHIR de código abierto disponible en Microsoft e implementarlo para sus organizaciones.

También puede usar el entorno HSPC Open sandbox EHR para crear un EHR que también admita un servidor FHIR abierto y usarlo para jugar con la aplicación Pacientes. Le recomendamos que lea la documentación de [espacio aislado de HSPC.](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox) El espacio aislado no solo proporciona una forma fácil, orientada a la interfaz de usuario y fácil de usar para crear, agregar y editar pacientes, sino que también le ofrece varias muestras para empezar.