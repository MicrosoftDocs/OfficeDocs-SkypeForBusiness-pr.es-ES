---
title: Introducción a Teams para organizaciones sanitarias
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
ms.reviewer: ''
description: Introducción a Teams para organizaciones sanitarias
ms.openlocfilehash: 15e10a69174787d104a990f8b71a6e8ef4f8be04
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147693"
---
# <a name="get-started-with-teams-for-healthcare-organizations"></a>Introducción a Teams para organizaciones sanitarias

Microsoft Teams ofrece una serie de características útiles para hospitales y otras organizaciones de salud. Las características de Teams están en desarrollo para ayudar a los hospitales a:

- Coordinación y colaboración de cuidados
- Mensajería segura
- TeleHealth
- Integración de registro de asistencia electrónica (EHR) 
- Integración del sistema de los Firstline Worker 

El contenido de esta sección se basa en las funciones fundamentales de los equipos, como las reuniones, las llamadas y la mensajería, y supone que ya ha implementado los equipos de su organización. Si aún no ha implementado Teams, empiece por leer [cómo implementar Microsoft Teams](../../How-to-roll-out-teams.md).

## <a name="care-coordination---microsoft-teams-patients-app"></a>Coordinación de cuidados-aplicación de pacientes de Microsoft Teams

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Microsoft Teams ahora tiene una solución de coordinación de cuidados específica para las organizaciones de salud que les ayudan a proporcionar el mejor cuidado del paciente. La Crux de la solución de coordinación de cuidados, la aplicación de pacientes de Microsoft Teams, es una primera aplicación de pestañas que se integra con sistemas de registro de estado electrónico (EHR) mediante una interfaz de recursos de interoperabilidad de Fast Healthcare ([FHIR](https://www.hl7.org/fhir/)) para proporcionar valiosa información médica a Microsoft Teams, en contexto para permitir la colaboración y la comunicación clínicas.  

La solución de coordinación de cuidados puede ser una interfaz con proveedores de software independientes (ISV) líderes que pueden conectar la aplicación de pacientes a sus sistemas HCI usando estándares de datos de estado existentes como HL7v2 y FHIR. Microsoft se asocia con los siguientes líderes del sector para establecer la integración de registros electrónicos de salud con equipos:

- Datica (a través de la oferta de [CMI](https://datica.com/compliant-managed-integration/) )
- Infor cloverleaf (a través del [puente de FHIR de Infor](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))
- Redox (a través del [servidor R ^ FHIR](https://www.redoxengine.com/fhir/))
- Dapasoft (a través [de Corolar en FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))

Un socio de integración y interoperabilidad de EHR que intente implementar Microsoft Teams para una organización de proveedor de cuidados de la salud debe proporcionar a la aplicación de pacientes una conexión segura y autenticada con los sistemas HCI de la organización de proveedores de cuidados de la salud. Esto permite el flujo unidireccional (solo lectura) de los registros del paciente relevante en la aplicación de pacientes. La aplicación de pacientes comprende el formato FHIR, por lo que el socio también es responsable de transformar los datos agregados de varios otros formatos como HL7v2, etc. en FHIR DSTU2 o STU3.

<br>

![Resaltado de la ilustración coordinación y colaboración de la salud](../../media/ehr-1.png)

<br>

La aplicación de pacientes se integra con sistemas de registro de estado electrónico (EHR) y permite a los proveedores de atención médica comunicarse con la atención del paciente en tiempo real en la plataforma segura de los equipos. La aplicación de pacientes es la primera inversión importante en el área de coordinación de cuidados que tiene el objetivo de afrontar los siguientes desafíos:

- Bajo nivel de eficacia a mano y comunicaciones críticas a través de la experiencia del paciente
- Información en silos que crea cargas administrativas
- Insatisfacción entre los médicos con herramientas de colaboración complejas y fragmentadas
- Coordinación de cuidados ineficaces que pueden suplantar demasiados minutos clínicos

Microsoft Teams permite que los médicos, los médicos, los enfermeras y otras personas colaboren de manera eficaz por:

- Formar parte de un único equipo virtualizado que funciona y colabora en documentos de Office
- Hacer conversaciones persistentes sobre diferentes pacientes que necesitan atención
- Usar canales con pestañas para estructurar su trabajo, con ayuda adicional de las pestañas a las que pueden anclar fuentes de información
- Usar reuniones de canal con la potencia de los equipos características de audio, vídeo, pantalla compartida, grabación y transcripción para administrar reuniones diarias
- Uso de la aplicación de pacientes para ajustar una lista de los pacientes de alto riesgo que deben supervisarse y extrae los detalles más recientes del sistema HCI. La aplicación de pacientes en sí agrega las siguientes características a Microsoft Teams:

    - Posibilidad de crear varias listas de pacientes en un solo canal.
    - Posibilidad de ver y ordenar la información que se muestra acerca de pacientes a través de columnas configurables.
    - Capacidad de aprovisionar automáticamente la aplicación a través de una plantilla de equipo.
    - Disponible en la aplicación de Teams para iOS y Android para los primeros trabajadores sanitarios móviles, así como en Microsoft Teams web y el cliente de escritorio.
    - Compatibilidad con las versiones de FHIR DSTU2 y STU3 mediante el análisis de una instrucción de conformidad.
    - Registros de auditoría para todas las acciones de visualización y búsqueda de su interfaz de usuario para salvaguardar la PHI según las pautas de la HIPAA.

La aplicación de pacientes se ha creado en la plataforma de extensibilidad de equipos y se aprovecha del marco de pestañas para mostrar contenido enriquecido de pacientes dentro de un canal. Para obtener más información sobre otras aplicaciones de Teams y la propia plataforma, consulte [aplicaciones para Microsoft Teams](/microsoftteams/platform/concepts/apps/apps-overview).  

> [!NOTE]
> La aplicación de pacientes está en versión preliminar privada y la interfaz de FHIR está en versión beta. No se espera que las versiones publicadas sean compatibles con versiones anteriores.

![Captura de pantalla de la aplicación de pacientes en dispositivos móviles y de escritorio](../../media/ehr-2.png)

Para obtener más información sobre la implementación, consulte [integrar registros de asistencia electrónica en Microsoft Teams](patients-app.md) .

## <a name="templates"></a>Plantillas

Las nuevas plantillas para crear equipos fueron desarrolladas para aplicarse a una configuración hospitalaria y pronto se espera más. Esto facilita la creación de equipos que los trabajadores de cuidado de la salud usan para coordinar la atención de pacientes en varios departamentos o en adelante. Consulte [Introducción a las plantillas de Teams para organizaciones de salud](healthcare-templates.md). Los equipos se pueden iniciar para departamentos internos, como Cardiología, o por cuidados y más plantillas en desarrollo.

## <a name="secure-messaging"></a>Mensajería segura

Mensajería segura admite la colaboración en equipos de atención médica, incluidas varias características nuevas:

- El remitente de un mensaje puede establecer una prioridad especial para el mensaje, de modo que el destinatario reciba una notificación repetida hasta que lea el mensaje.
- El remitente de un mensaje puede solicitar una confirmación de lectura, de modo que se le notifique cuando el destinatario del mensaje Lea un mensaje enviado.


En conjunto, estas características permiten una atención más rápida a los mensajes urgentes y confían en que el mensaje se ha recibido y leído. Los nuevos equipos de atención médica que usan estas características se pueden crear para cada paciente. Estas características se basan en directivas y se pueden asignar a individuos o a equipos completos.

Para obtener más información, consulte [Introducción a las directivas de mensajería segura para organizaciones de sanidad](messaging-policies-hc.md) .

También relacionada con la mensajería segura es la capacidad de tener otros inquilinos federados por organizaciones de cuidado de la salud, lo que permite una comunicación entre inquilinos más rica. (consulte [administrar el acceso externo (Federación) en Microsoft Teams](../../manage-external-access.md)).

## <a name="firstline-worker-integration"></a>Integración de trabajadores de los Firstline

Microsoft Teams se integra con los Firstline Worker, que se puede usar para coordinar las características de personal de turnos y mucho más.

 Consulte los artículos siguientes:

- [Mover los equipos de Microsoft StaffHub a turnos en Microsoft Teams](../shifts/move-staffhub-teams-to-shifts-in-teams.md)

- [Administrar la aplicación Turnos para su organización en Microsoft Teams](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md)
