---
title: Introducción a Teams para organizaciones sanitarias
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Introducción a Teams para organizaciones sanitarias
ms.openlocfilehash: 7f68a21e835edb3b5ebcd8ff794f4fd3d0716bee
ms.sourcegitcommit: cf2cb5b7e03385b33e34a5ff89719adb882525b1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2019
ms.locfileid: "33632301"
---
# <a name="get-started-with-teams-for-healthcare-organizations"></a>Introducción a Teams para organizaciones sanitarias

Microsoft Teams ofrece una serie de características útiles para hospitales y otras organizaciones de asistencia sanitarios. Características de los equipos se encuentran en desarrollo para ayudar a hospitales con:

- Coordinación de la atención
- Mensajería segura
- Integración de presentación electrónica Healthcare registro (EHR)
- Integración de trabajo Firstline

## <a name="care-coordination---microsoft-teams-patients-app"></a>Aplicación de los pacientes de los equipos de coordinación de la atención - Microsoft

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Microsoft Teams ahora tiene una solución de coordinación de atención específica para las organizaciones de salud para ayudarles a cumplir su objetivo de proporcionar la mejor atención de pacientes. El punto más importante de la solución de coordinación de atención, la aplicación de los pacientes de los equipos de Microsoft, es la primera aplicación de ficha de terceros que se integra con los sistemas de (EHR) registros electrónicos de salud mediante una interfaz de Fast recursos de interoperabilidad de Healthcare ([FHIR](https://www.hl7.org/fhir/)) para incorporar valiosos información médica en Microsoft Teams.  

La solución de coordinación de atención puede interactuar con proveedores independientes de Software (ISV) que pueden conectarse a la aplicación de los pacientes a los sistemas EHR utilizando estándares de datos de estado existente como HL7v2 y FHIR. Microsoft está asociado con el siguiente líderes del sector para establecer la integración de registros de salud electrónicos con los equipos:

- Datica (a través de su oferta [CMI](https://datica.com/compliant-managed-integration/) )
- Información Cloverleaf (a través de la [Información FHIR puente](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))
- Redox (a través de la [R ^ server FHIR](https://www.redoxengine.com/fhir/))
- Dapasoft (a través de [Corolar en FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))

Una integración EHR y socio interoperabilidad intenta implementar Microsoft Teams para una organización de proveedor de atención médica debe proporcionar una conexión segura y autenticada con sistemas de la organización de proveedor de atención médica EHR de la aplicación de los pacientes. Esto permite que el flujo de unidireccional (solo lectura) de los registros de pacientes relevantes en que la aplicación de los pacientes. La aplicación de los pacientes comprende el formato FHIR, por lo que el socio también es responsable de transformar los datos agregados de diversos otros formatos como HL7v2, etc. en FHIR DSTU2 o STU3.

<br>

![Integración de EHR](../../media/ehr-1.png)

<br>

La aplicación de los pacientes se integra con sistemas (EHR) de registros de salud electrónicos y permite tener cuidado proveedores para comunicarse acerca de la atención a los pacientes en tiempo real dentro de plataforma segura de equipos. La aplicación de los pacientes es la primera inversión principal en el área de coordinación de atención que pretende abordar los retos de los siguientes:

- Eficacia baja de entregas y comunicación crítica a través de la experiencia del paciente
- En silos de información que crea cargas administrativas
- Insatisfacción entre los médicos con herramientas de colaboración compleja y fragmentados
- Coordinación de la atención en persona ineficaz que puede grabar costosa demasiado tiempo clínico

Microsoft Teams permite médicos, médicos, enfermeras y otros miembros del personal a colaborar de forma eficaz mediante:

- Que se va parte de un único equipo virtualizado que funciona y colabora en documentos de Office
- Tener conversaciones persistentes acerca de la necesidad de atención de pacientes diferentes
- Uso de canales con fichas como una forma de estructurar su trabajo, con la ayuda adicional de las fichas a la que pueden anclar fuentes de información
- Uso de las reuniones de canal con la eficacia de los equipos audio, vídeo, uso compartido de la pantalla, grabación y las características de transcripción para administrar reuniones diarias
- Uso de la aplicación de los pacientes para curate una lista de los pacientes de alto riesgo que debe supervisarse y extrae sus detalles más recientes desde el sistema EHR. La propia aplicación de los pacientes agrega las siguientes características a Microsoft Teams:

    - Capacidad de crear a varios paciente listas dentro de un único canal.
    - Capacidad para ver y ordenar la información que se muestran sobre los pacientes a través de columnas configurables.
    - Capacidad de la aplicación a través de una plantilla de equipo de aprovisionamiento automático.
    - Está disponible en la aplicación de los equipos para iOS y Android para trabajadores móviles de atención sanitarios primera, así como cliente web y de escritorio de Microsoft Teams.
    - Compatibilidad con las versiones de FHIR DSTU2 y STU3 a través de análisis de la declaración de conformidad.
    - Registros de auditoría para todas las acciones de vista y búsqueda en su interfaz de usuario para salvaguardar PHI por instrucciones HIPAA.

La aplicación de los pacientes se basa en la plataforma de extensibilidad de los equipos y aprovecha las ventajas del marco de trabajo de las fichas para mostrar contenido enriquecido de pacientes dentro de un canal. Para obtener más información acerca de otras aplicaciones de los equipos y la misma plataforma, consulte [aplicaciones para equipos de Microsoft](/microsoftteams/platform/concepts/apps/apps-overview).  

> [!NOTE]
> La aplicación de los pacientes está en vista previa privada y la interfaz FHIR está en la versión beta. No se esperan versiones publicadas para ser compatibles con versiones anteriores.

![Captura de pantalla de aplicación de los pacientes](../../media/ehr-2.png)

Vea [Integración de registros electrónicos de salud en los equipos de Microsoft](patients-app.md) para obtener información detallada de la implementación.

## <a name="templates"></a>Plantillas

Nuevas plantillas para crear los equipos se desarrollaron para aplicar a una configuración de Hospital, y mucho más se esperan pronto. Esto facilita la creación de los equipos que usan los trabajadores de la asistencia sanitarios para coordinar la atención de los pacientes en diversos departamentos o salas de consulta. Vea [Introducción a las plantillas de equipos para las organizaciones de salud](healthcare-templates.md). Se pueden iniciar los equipos de los departamentos internos como cardiología, o para salas de consulta de atención y, más plantillas están en desarrollo.

## <a name="secure-messaging"></a>Mensajería segura

Mensajería admite colaboración segura dentro de los equipos sanitarios, incluidas varias características nuevas:

- Remitente de un mensaje puede establecer una prioridad especial para su mensaje, por lo que el destinatario se notificará repetidamente hasta que lea el mensaje.
- Remitente de un mensaje puede solicitar una confirmación de lectura para que se le notifique cuando se leyó un mensaje que se envían por el destinatario del mensaje.

Juntos, estas características permiten más rápida atención a los mensajes urgentes y confianza que el mensaje se recibió y leer. Los equipos sanitarios nuevo con estas características se pueden crear en una base por paciente. Estas características son basada en directivas y se pueden asignar a individuos o equipos completos.

Para obtener más información, vea [Introducción a las directivas de mensajería segura para las organizaciones de salud](messaging-policies-hc.md) .

## <a name="firstline-worker-integration"></a>Integración de trabajo Firstline

Microsoft Teams se integra con Firstline de trabajo, que se puede utilizar para coordinar las características de personal MAYÚS y mucho más.

 Vea los siguientes artículos:

- [Mover los equipos de Microsoft StaffHub a turnos en Microsoft Teams](../shifts/move-staffhub-teams-to-shifts-in-teams.md)

- [Administrar la aplicación Turnos para su organización en Microsoft Teams](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md)
