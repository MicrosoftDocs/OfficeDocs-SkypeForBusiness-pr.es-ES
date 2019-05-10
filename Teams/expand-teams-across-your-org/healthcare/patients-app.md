---
title: Introducción a la aplicación de los pacientes
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
ms.openlocfilehash: f157061666dc72a8420b9b9331387b42d6918cea
ms.sourcegitcommit: b2acf18ba6487154ebb4ee46938e96dc56cb2c9a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/09/2019
ms.locfileid: "33865041"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a>Integración de registros sanitarios electrónicos en Microsoft Teams

[!INCLUDE [preview-feature](../../includes/preview-feature.md)] 

Para participar en la vista previa privada, vea [inscribirse en la vista previa privada](#enroll-in-the-private-preview).

En este artículo está destinada a un healthcare general para desarrolladores de TI interesados en usar las API FHIR encima de un sistema de información médica para conectarse a Microsoft Teams. Esto permitiría escenarios de coordinación de atención que coinciden con las necesidades de una organización de salud.

Los artículos vinculados documentar las especificaciones de la interfaz FHIR para la aplicación de los pacientes de los equipos de Microsoft, y en las secciones siguientes se explican lo que se requiere para configurar un servidor FHIR y conectarse a la aplicación de los pacientes en el inquilino o el entorno de desarrollo. También debe estar familiarizado con la documentación del servidor FHIR que ha elegido, que debe ser una de las opciones compatibles:
- Datica (a través de su oferta [CMI](https://datica.com/compliant-managed-integration/) )
- Información Cloverleaf (a través de la [Información FHIR puente](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))
- Redox (a través de la [R ^ server FHIR](https://www.redoxengine.com/fhir/))
- Dapasoft (a través de [Corolar en FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))

> [!NOTE]
> Este proceso no incluye los pasos que usan el centro de administración de Microsoft Teams o los cmdlets de PowerShell para habilitar las características. La configuración se realiza en su totalidad en el lado del servidor o servicio FHIR y en el cliente de aplicación de los pacientes.

Se muestra a continuación es la arquitectura de la aplicación de los pacientes:

![Arquitectura de aplicación de los pacientes](../../media/patients-app-architecture.png)

En las secciones siguientes se explican los requisitos de la capa de acceso a datos de sólo FHIR para la aplicación de los pacientes que un servidor FHIR (EHR habilitado o las API de FHIR) debe cumplir con el fin de integrar con la aplicación de los pacientes, incluidos los siguientes:

- Expectativas alrededor de autenticación de usuario
- Requisitos funcionales y técnicos de la interfaz de integración
- Expectativas alrededor de rendimiento y la confiabilidad
- Expectativas alrededor de recursos FHIR para ser compatible con la aplicación de los pacientes
- Proceso de integración y el modelo de contratación esperado
- Cómo inscribirse a usted y su cliente en la vista previa privada de la aplicación de los pacientes
- Cómo empezar a trabajar con FHIR y algunos de los desafíos comunes que se enfrentan con la aplicación de los pacientes
- Requisitos futuros para la siguiente iteración de la aplicación de los pacientes

> [!NOTE]
> En las secciones siguientes, se utiliza la palabra "asociado" o "Asociado de interoperabilidad" para hacer referencia a ninguna parte 3 de organización que permite la integración con sistemas EHR para la aplicación de los pacientes a través de FHIR y está implementando un servidor FHIR para que coincidan con las especificaciones de la lista.

## <a name="functional-and-technical-requirements"></a>Requisitos funcionales y técnicos  

### <a name="authentication"></a>Autenticación  

Autorización de nivel de aplicación *no se admite para la autorización de nivel de usuario* es la forma compatible con más frecuencia para realizar transformaciones de datos y exponer las conexiones a datos EHR a través de FHIR, incluso aunque el sistema EHR podría implementar la autorización de nivel de usuario . El servicio de interoperabilidad (Partner) obtiene acceso con privilegios elevados a los datos EHR y exponen los mismos datos que los recursos adecuados de FHIR hay ningún contexto de autorización que se pasan al cliente del servicio de interoperabilidad (la aplicación de los pacientes) integración con la interoperabilidad Servicio o plataforma. La aplicación de los pacientes no podrá exigir la aplicación de autorización de nivel de usuario, pero es compatible con la autenticación de una aplicación a otra entre la aplicación de los pacientes y servicio de interoperabilidad del socio.

A continuación se describe el modelo de autenticación de una aplicación a otra:

Servicio de autenticación del servicio debe realizarse a través del [flujo de la credencial del cliente](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)de OAuth 2.0. El servicio de socio debe proporcionar lo siguiente:

1. El servicio de socio permite la aplicación de los pacientes para crear una cuenta con el socio, lo que permite que la aplicación de los pacientes generar y propio client_id y client_secret, que se administran a través de un portal de registro de autenticación en el servidor de autenticación del socio.
2. El servicio de socio posee el sistema de autenticación, autorización, que acepta y comprueba (autentica) el cliente de credenciales proporcionada y proporciona un token de acceso con la sugerencia de inquilinos en el ámbito, tal y como se describe a continuación.
3. Por motivos de seguridad o en caso de una infracción de secreto, la aplicación de los pacientes puede volver a generar el secreto e invalidar o eliminar un secreto antiguo (ejemplo de la misma está disponible en el Portal de Azure - AAD registro de la aplicación)
4. El extremo de metadatos que hospeda la declaración de conformidad debe ser no autenticado, debe ser accesible sin símbolo (token) de autenticación.
5. El servicio de socio proporciona el extremo de símbolo (token) para la aplicación de los pacientes solicitar un token de acceso mediante un flujo de credenciales de cliente. La dirección url de símbolo (token) según el servidor de autorización debe formar parte de la declaración de conformidad (capacidad) de FHIR obtenida de metadatos en el servidor FHIR como en este ejemplo:

![Aplicación de los pacientes 5](../../media/Patient-app-5.png)

Una solicitud de un token de acceso consta de los siguientes parámetros:

* * *

    /Token POST HTTP/1.1 Host: server.com de autorización

    tipo de concesión = client_credentials &client_id = &client_secret xxxxxxxxxx = xxxxxxxxxx

* * *

El servicio de socio proporciona el client_id y client_secret para la aplicación de los pacientes, administrado a través de un portal de registro de autenticación en el lado del socio. El servicio de socio proporciona el extremo al token de acceso de solicitud con un flujo de credenciales de cliente. Una respuesta correcta debe incluir los parámetros token_type, access_token y expires_in.

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a>Enrutamiento: Asignación AAD inquilino al extremo del proveedor

La aplicación de los pacientes se conecta a un servicio de socio a través de un único extremo. El servicio de socio posee y mantiene un mecanismo para asignar a cada cliente de Microsoft (identificador de inquilino AAD) a un proveedor de servicios de salud respectivo (server FHIR) que trabaja con el servicio de socio.

Asignación del inquilino AAD a un extremo de proveedor usa el identificador de inquilino de AAD (GUID). La aplicación de los pacientes pasa el identificador de inquilino en el ámbito, mientras que solicita un token de acceso para cada solicitud. El servicio de socio mantiene la asignación de identificador de inquilino al extremo de proveedor y redirige las solicitudes a un extremo de proveedor según el identificador de inquilino. Para ello, el socio es compatible con la configuración en su extremo (manualmente o a través de un portal como parte de la incorporación de las organizaciones de proveedor a su plataforma de interoperabilidad).

A continuación se muestra el flujo de trabajo de autenticación y enrutamiento:

![Aplicación de los pacientes 6](../../media/Patient-app-6.png)

1. Solicitud de token de acceso de la aplicación mediante el envío de:
 
        {   grant_type: client_credentials,
            client_id: xxxxxx, 
            client_secret: xxxxxx,
            scope: {Provider Identifier, Ex: tenant ID}
        }

2. Responder con un token de aplicaciones:

        {  access_token: {JWT, with scope: tenant ID},
           expires_in: 156678,
           token_type: "Bearer",
        }

3. Solicitar datos protegidos con el token de acceso.
4. Mensaje de autorización: seleccione el servidor FHIR apropiado para enrutar a de identificador de inquilino de ámbito
5. Envía los datos de aplicación protegida desde el servidor FHIR autorizado después de la autenticación con el token de aplicaciones.

## <a name="interfaces"></a>Interfaces

Las llamadas específicas y campos utilizados por la aplicación de los pacientes se documentan en los siguientes artículos. Seleccione la interfaz aplicable a su servidor FHIR/FHIR API.

- [Especificación de la interfaz DSTU2](dstu2-interface.md)
- [Especificación de la interfaz STU3](stu3-interface.md)

## <a name="performance-and-reliability"></a>Rendimiento y la confiabilidad

Mientras la aplicación de los pacientes se encuentra en la vista previa privada, no hay ninguna garantía en el rendimiento de extremo a otro. Los factores de rendimiento incluyen las latencias relativas de todos los saltos implicados en el flujo de trabajo, empezando por el EHR en el entorno del sistema de mantenimiento, para la interoperabilidad de asociados y sus infra, incluidos el servidor FHIR y a través al ecosistema de Office 365 y Aplicación de los pacientes.

![Socios de interoperabilidad](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a>Empezar a trabajar con FHIR  

Si es una novedad en FHIR y necesita obtener acceso fácilmente a un servidor FHIR que puede exponer a la interfaz de integración EHR de los equipos de Microsoft, Microsoft dispone de un servidor de FHIR de código abierto disponible para todos los desarrolladores a usar. Consulte el artículo [What ' s Server FHIR de Azure](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) para obtener más información sobre el origen de open Server FHIR disponibles en Microsoft e implementar para sus organizaciones.

También puede usar el entorno de EHR HSPC Abrir espacio aislado para crear un un EHR que también es compatible con un servidor FHIR abierto y se usa para reproducir alrededor de con la aplicación de los pacientes. Se recomienda que lea la [documentación de espacio aislado HSPC](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox). No sólo proporciona una fácil el espacio aislado, orientado la interfaz de usuario y usuario descriptivo forma habitual de creación, adición y edición de los pacientes, también se ofrecen varios ejemplos para empezar a.  

## <a name="enroll-in-the-private-preview"></a>Inscribirse en la vista previa privada

Una vez haya creado el origen de open Server FHIR, es realmente fácil para conectarse a la aplicación de los pacientes dentro de su inquilino siguiendo los pasos que se mencionan a continuación:

1. Con los siguientes detalles iniciales, [póngase en contacto con nosotros](mailto:Teamsforhealthcare@service.microsoft.com?subject=Microsoft%20Teams%20Patients%20App%20private%20preview) :  
    - Te llamas
    - Su posición
    - La empresa u organización que representan
    - ¿Por qué está interesado en la aplicación de los pacientes para la integración de EHR

    Se obtendrá volver a usted tan pronto como sea posible con preguntas más y le guían a lo largo de un proceso para obtener configurado para la vista previa de privada.

2. Asegúrese de que sideloading de personalizado aplicaciones está habilitado en el inquilino donde va a probar la aplicación de los pacientes. Consulte [las directivas de permisos de aplicación](../../admin-settings.md) para obtener información sobre cómo activar esta función desde el centro de administración de equipos para el inquilino de su o su del cliente.

3. Sideload la aplicación de los pacientes de manifiesto que se obtiene de Microsoft (después de que se procese su correo electrónico para nosotros) en un equipo en el inquilino que se va a utilizar para los escenarios de redondeo pacientes y coordinación de la atención. Las instrucciones detalladas alrededor de cómo una aplicación de carga de lado están en [cargar un paquete de aplicación a los equipos de Microsoft](/microsoftteams/platform/concepts/apps/apps-upload)

4. Desplácese hasta el canal general como el propietario del equipo y, a continuación, haga clic en la ficha de los pacientes. Debería ver una primera experiencia de ejecución que se va a presentar dos opciones, es decir, modo EHR y modo Manual. Seleccione el **modo EHR** y copie el extremo del servidor de FHIR (que se ha agregado el programa de instalación sólo anteriormente con todos los datos necesarios y los recursos por encima de las especificaciones de) en el campo de vínculo y asigne un nombre que representa también el servidor de FHIR a la conexión. Haga clic en conectar, y todo lo que deberá estar preparado para ir.

    ![Configuración del servidor de aplicación de los pacientes](../../media/patients-server.png)

5. Empezar a usar la aplicación para buscar los pacientes desde el servidor FHIR/EHR y agregarlos a una lista y si algo no funciona, por favor, [envíenos sus comentarios](mailto:Teamsforhealthcare@service.microsoft.com?subject=Microsoft%20Teams%20Patients%20App%20feedback) . Además, para establecer una versión completamente autenticada de la aplicación de los pacientes-> flujo FHIR Server, por favor, integrarse en el cuadro de diálogo sin conexión con Microsoft Teams para producto asistencia sanitaria de ingeniería, a través la solicitud de correo electrónico que se menciona anteriormente para aclarar los requisitos y se lo Ayuda de habilitar esta opción para usted por los requisitos de autenticación descritos anteriormente en el documento de interfaz FHIR.  


