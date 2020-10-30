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
description: Obtenga información sobre cómo integrar registros de asistencia electrónica en la aplicación de pacientes de Microsoft Teams con las API de FHIR.
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
> Desde el 30 de octubre de 2020, la aplicación de pacientes se ha retirado y se ha sustituido por la [aplicación listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) en Teams. Los datos de la aplicación patients se almacenan en el buzón de grupo del grupo Office 365 que respalda al equipo. Todos los datos asociados con la aplicación patients se conservan en este grupo, pero ya no se puede obtener acceso a ellos a través de la interfaz de usuario. Los usuarios pueden volver a crear sus listas con la [aplicación listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).
>
>Con las listas, los equipos de cuidados de la organización de la salud pueden crear listas de pacientes para escenarios que abarcan desde rondas y reuniones interdisciplinarias hasta supervisión general de pacientes. Consulte la plantilla patients en listas para comenzar. Para obtener más información sobre cómo administrar la aplicación listas de su organización, vea [administrar la aplicación listas](../../manage-lists-app.md).

Este artículo está dirigido a un desarrollador de TI de medicina general interesado en usar API de FHIR sobre un sistema de información de medicina para conectar con Microsoft Teams. Esto permitiría escenarios de coordinación de cuidados que se ajusten a las necesidades de una organización de salud.

Los artículos vinculados documentan las especificaciones de la interfaz de FHIR para la aplicación de pacientes de Microsoft Teams, y las siguientes secciones explican qué se necesita para configurar un servidor de FHIR y conectarse a la aplicación de pacientes en el entorno de desarrollo o en el inquilino. También necesitará estar familiarizado con la documentación del servidor de FHIR que haya elegido, que debe ser una de las opciones admitidas:

- Datica (a través de la oferta de [CMI](https://datica.com/compliant-managed-integration/) )
- Infor cloverleaf (a través del [puente de FHIR de Infor](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))
- Redox (a través del [servidor R ^ FHIR](https://www.redoxengine.com/fhir/))
- Dapasoft (a través [de Corolar en FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))

> [!NOTE]
> Este proceso no incluye los pasos que usan el centro de administración de Microsoft Teams o los cmdlets de PowerShell para habilitar características. La configuración se realiza por completo en el servidor FHIR y en el cliente de aplicaciones para pacientes.

A continuación se muestra la arquitectura de la aplicación para pacientes:

![Diagrama de la arquitectura de la aplicación para pacientes](../../media/patients-app-architecture.png)

En las siguientes secciones, se explican los requisitos de la FHIR de acceso a datos de solo lectura para la aplicación de pacientes que un servidor de FHIR (o las API de FHIR habilitadas de EHR) debe cumplirse para poder integrarse con la aplicación de pacientes, entre los que se incluyen los siguientes:

- Expectativas sobre la autenticación de usuarios
- Requisitos técnicos y técnicos de la interfaz de integración
- Expectativas sobre rendimiento y fiabilidad
- Expectativas sobre los recursos de FHIR para que la aplicación de pacientes los admita
- Proceso de integración y modelo de compromiso esperado
- Introducción a FHIR y algunos desafíos comunes que se enfrentan a la aplicación de pacientes
- Requisitos futuros para la siguiente iteración de la aplicación pacientes

> [!NOTE]
> En las siguientes secciones, se usa la palabra "Partner" o "Partner Interop" para referirse a cualquier organización de terceros que permita la integración con sistemas HCI para la aplicación de pacientes a través de FHIR y está implementando un servidor de FHIR para que coincida con las especificaciones de la lista.

## <a name="functional-and-technical-requirements"></a>Requisitos técnicos y técnicos  

### <a name="authentication"></a>Autenticación  

La autorización en el nivel de la aplicación *sin compatibilidad para autorización a nivel de usuario* es la forma más común admitida para realizar transformaciones de datos y exponer conexiones a datos de EHR a través de FHIR, aunque el sistema HCI pueda implementar la autorización a nivel de usuario. El servicio de interoperabilidad (asociado) obtiene acceso elevado a los datos de EHR y cuando exponen los mismos datos que los recursos de FHIR apropiados no hay ningún contexto de autorización pasado al consumidor del servicio de interoperabilidad (la aplicación de pacientes) que se integra con el servicio o la plataforma de interoperabilidad. La aplicación de pacientes no podrá exigir la autorización de nivel de usuario, pero admite la autenticación de aplicaciones entre la aplicación de pacientes y el servicio del colaborador de interoperabilidad.

La aplicación para el modelo de autenticación de aplicaciones se describe a continuación:

La autenticación de servicio a servicio debe realizarse a través del [flujo de credenciales de cliente](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)OAuth 2,0. El servicio asociado debe proporcionar lo siguiente:

1. El servicio asociado permite a la aplicación de pacientes crear una cuenta con el socio, lo que permite a la aplicación de pacientes generar y poseer client_id y client_secret administrados a través de un portal de registro de autenticación en el servidor de autenticación del socio.

2. El servicio asociado posee el sistema de autenticación/autorización, que acepta y verifica (autentica) las credenciales de cliente proporcionadas y devuelve un token de acceso con el sugerencia de inquilino en el ámbito, como se describe a continuación.

3. Por razones de seguridad o en el caso de una infracción secreta, la aplicación de pacientes puede volver a generar el secreto e invalidar o eliminar el secreto anterior (el ejemplo de lo mismo está disponible en el portal de Azure: registro de la aplicación AAD).

4. El punto final de metadatos que hospeda la instrucción de conformidad debe ser no autenticado, debe ser accesible sin un token de autenticación.

5. El servicio asociado proporciona el punto final del token de la aplicación de pacientes para solicitar un token de acceso con un flujo de credenciales de cliente. La dirección URL del token como por servidor de autorización debe formar parte de la instrucción de conformidad (Capability) FHIR capturada de los metadatos en el servidor de FHIR como en este ejemplo:

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

Una solicitud para un token de acceso consta de los siguientes parámetros:

```http
POST /token HTTP/1.1
Host: authorization-server.com

grant-type=client_credentials
&client_id=xxxxxxxxxx
&client_secret=xxxxxxxxxx
```

El servicio asociado proporciona la client_id y client_secret para la aplicación de pacientes, administrada a través de un portal de registro de autenticación en el lado del socio. El servicio asociado proporciona el extremo para solicitar el token de acceso mediante un flujo de credenciales de cliente. Una respuesta correcta debe incluir los parámetros token_type, access_token y expires_in.

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a>Enrutamiento: asignación de inquilino de AAD al extremo de proveedor

La aplicación patients se conecta a un servicio asociado a través de un único punto de conexión. El servicio asociado posee y mantiene un mecanismo para asignar a cada cliente de Microsoft (ID de inquilino de AAD) a un proveedor de servicios de salud respectivo (servidor FHIR) con el que está trabajando el servicio asociado.

La asignación del inquilino de AAD a un extremo de proveedor usa el identificador de inquilino de AAD (GUID). La aplicación patients pasa el identificador de inquilino en el ámbito, mientras solicita un token de acceso para cada solicitud. El servicio asociado mantiene la asignación de identificador de inquilino en el extremo de proveedor y redirige las solicitudes a un extremo de proveedor basándose en el identificador de inquilino. Para ello, el socio admite la configuración en su extremo (manualmente o a través de un portal como parte de la incorporación de organizaciones de proveedores a su plataforma de interoperabilidad).

A continuación se muestra el flujo de trabajo de autenticación y enrutamiento:

![Diagrama del flujo de trabajo de autenticación y enrutamiento](../../media/Patient-app-6.png)

1. Solicitud de token de acceso de aplicación mediante el envío de:
 
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

3. Solicitar datos protegidos con token de acceso.

4. Mensaje de autorización: seleccione el servidor de FHIR apropiado al que desea enrutar desde el identificador de inquilino en el ámbito.

5. Envía los datos protegidos por la aplicación desde el servidor de FHIR autorizado después de autenticarse con el token de la aplicación.

## <a name="interfaces"></a>Interactúa

Las llamadas y los campos específicos usados por la aplicación de pacientes se documentan en los artículos siguientes. Seleccione la interfaz aplicable a las API de FHIR Server/FHIR.

- [Especificación de la interfaz DSTU2](dstu2-interface.md)
- [Especificación de la interfaz STU3](stu3-interface.md)

## <a name="performance-and-reliability"></a>Rendimiento y confiabilidad

Mientras la aplicación patients está en la vista previa privada, no hay ninguna garantía en el rendimiento de un extremo a otro. Entre los factores en el rendimiento se incluyen las latencias relativas de todos los saltos implicados en el flujo de trabajo, empezando desde el EHR del entorno del sistema, hasta el socio de interoperabilidad y su infra, incluido el servidor de FHIR y el ecosistema y la aplicación de pacientes de Office 365.

![Ilustración del rendimiento de los socios de interoperabilidad](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a>Introducción a FHIR  

Si es nuevo en FHIR y necesita acceder fácilmente a un servidor de FHIR que pueda exponer a la interfaz de integración de Microsoft Teams HCI, Microsoft tiene un servidor de FHIR de código abierto para que todos los programadores lo usen. Para obtener más información sobre el servidor de FHIR de código abierto de Microsoft, consulte el artículo [What is FHIR Server for Azure](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) e impleméntelo para sus organizaciones.

También puede usar el entorno HSPC de espacio aislado abierto de Open para crear un EHR que también admita un servidor de FHIR abierto y use esta opción para familiarizarse con la aplicación de pacientes. Le recomendamos que lea la [documentación del espacio aislado de HSPC](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox). El espacio aislado no solo ofrece una forma sencilla, orientada a la interfaz de usuario y sencilla de usar para crear, agregar y editar pacientes, sino que también le ofrece varias muestras para comenzar. 
