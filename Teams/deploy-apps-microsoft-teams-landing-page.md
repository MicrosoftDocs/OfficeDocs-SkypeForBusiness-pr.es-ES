---
title: Información sobre las aplicaciones de Microsoft Teams
ms.reviewer: ''
description: Obtenga información sobre las aplicaciones, los bots y los conectores, y sobre cómo decidir qué implementar en Microsoft Teams según el perfil y los requisitos empresariales de su organización.
ms.topic: conceptual
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
audience: admin
ms.service: msteams
ms.subservice: teams-apps
ms.date: 10/01/2022
ms.collection:
- M365-collaboration
- m365-frontline
- tier2
- highpri
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020; intro-overview; intro-hub-or-landing
ms.openlocfilehash: 701cdcd1f822018be777f6d22f2063871ea5c7fa
ms.sourcegitcommit: ff161779577ce9cc892f1b6b8861ad49ff4c3ca3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2022
ms.locfileid: "69130869"
---
# <a name="understand-microsoft-teams-apps-and-their-capabilities"></a>Comprender las aplicaciones de Microsoft Teams y sus capacidades

Las aplicaciones de Teams ayudan a los usuarios a unir las herramientas y los servicios de su lugar de trabajo y a colaborar con otros usuarios. Algunos ejemplos son los usuarios finales que usan un calendario anclado en Teams para colaborar rápidamente con otros usuarios, una aplicación con la funcionalidad de bots que informa a los usuarios de la calidad de un servicio web en un canal de Teams, y una aplicación para compartir y asignar tareas a varios usuarios finales en un canal. Las aplicaciones de Microsoft Teams son aplicaciones SaaS basadas en web que no necesitan implementarse localmente.

Como administrador, puede establecer un proceso de gobierno de aplicaciones que equilibre requisitos amplios de los usuarios finales junto con las directivas de TI, los estándares y los perfiles de riesgo de su organización.

Nuestro extenso [catálogo](https://appsource.microsoft.com/marketplace/apps?product=office%3Bteams&page=1) de aplicaciones validadas y seguras de Teams proporciona a los usuarios finales acceso a las herramientas y servicios que su organización necesita a diario. El Centro de administración de Teams proporciona a los administradores controles y configuraciones de nivel empresarial para gobernar las aplicaciones. Puede controlar la disponibilidad de las aplicaciones para cada usuario en los distintos contextos, como reuniones, chats y canales.

Este artículo le ayudará a comprender los tipos de aplicaciones y desde dónde acceden los usuarios a esas aplicaciones. Para obtener más información sobre el uso de aplicaciones, lea [Información general sobre las aplicaciones para los usuarios finales](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0)

Los diferentes tipos de aplicaciones que los usuarios finales pueden usar en Teams son:

* [Aplicaciones principales que forman parte de Teams](#core-apps).
* Otras [aplicaciones creadas por Microsoft](#apps-created-by-microsoft).
* [Aplicaciones de terceros](#third-party-apps-created-by-independent-app-developers) creadas por partners (validadas por Microsoft).
* [Aplicaciones personalizadas](#custom-apps-created-within-an-organization-for-internal-use) creadas por tu propia organización.

## <a name="core-apps"></a>Aplicaciones principales

Algunas funcionalidades de Teams, como la fuente de actividades, los equipos, el chat, el calendario, las llamadas, los archivos y las tareas (inquilinos de educación) están disponibles y ancladas de forma predeterminada para facilitar el acceso a los usuarios finales. Para los trabajadores de primera línea, solo están disponibles y anclados la actividad, los turnos, el chat y las llamadas. Como administrador, puede modificar el comportamiento predeterminado mediante la [directiva de configuración](/microsoftteams/teams-app-setup-policies).

:::image type="content" source="media/core-apps-pinned1.png" alt-text="Las aplicaciones principales son las aplicaciones ancladas en Teams de forma predeterminada." lightbox="media/core-apps-pinned2.png":::

## <a name="apps-created-by-microsoft"></a>Aplicaciones creadas por Microsoft

Microsoft proporciona muchas aplicaciones para mejorar la productividad y la colaboración. Usted y los usuarios finales pueden encontrar estas aplicaciones si buscan a Microsoft como Editor en el Centro de administración de Teams o como Proveedor en la tienda de Teams.

Teams incluye un conjunto de aplicaciones integradas, como Listas, Tareas, Elogiar, Aprobaciones y más. Recomendamos que se incluyan aplicaciones destacadas de Teams, como Planner, en la implementación inicial de Teams.

:::image type="content" source="media/microsoft-apps-in-tac1.png" alt-text="Captura de pantalla que muestra una lista de aplicaciones de Microsoft en el Centro de administración de Teams." lightbox="media/microsoft-apps-in-tac2.png":::

## <a name="third-party-apps-created-by-independent-app-developers"></a>Aplicaciones de terceros creadas por desarrolladores de aplicaciones independientes

Además de las aplicaciones proporcionadas por Microsoft, puede usar aplicaciones de terceros. Microsoft valida rigurosamente la funcionalidad y la seguridad de todas estas aplicaciones. Elaborar pruebas manuales y automatizadas se ejecutan antes de hacer que estas aplicaciones estén disponibles en la tienda de Teams y muchas pruebas continúan con una cadencia regular incluso después de que las aplicaciones se publiquen en directo. Para comprender las ventajas de la validación de aplicaciones, consulte [validación de aplicaciones de terceros](overview-of-app-validation.md). Algunas de las aplicaciones se suscriben al [programa de cumplimiento de Microsoft](overview-of-app-certification.md) para pasar por varios niveles de comprobaciones adicionales más allá de la validación.

:::image type="content" source="media/3p-apps-in-teams.png" alt-text="Captura de pantalla de un ejemplo de aplicaciones de terceros en la tienda de Teams.":::

## <a name="custom-apps-created-within-an-organization-for-internal-use"></a>Aplicaciones personalizadas creadas dentro de una organización para uso interno

Las aplicaciones creadas por los desarrolladores de su organización se denominan aplicaciones personalizadas (o aplicaciones de línea de negocio). Su organización puede encargar la creación de aplicaciones personalizadas para los requisitos específicos de la organización. Tiene el control para permitir o bloquear dichas aplicaciones para toda la organización o para usuarios específicos. Los desarrolladores de su organización pueden crear rápidamente soluciones personalizadas de bajo código mediante la integración de Teams con [Microsoft Power Platform](/microsoftteams/platform/samples/teams-low-code-solutions).

Después de que un administrador permita el uso de aplicaciones personalizadas, los usuarios finales pueden encontrarlas seleccionando **Creado para su organización** en el panel de navegación izquierdo de la Tienda Teams.

:::image type="content" source="media/built-for-your-org1.png" alt-text="Captura de pantalla de aplicaciones personalizadas en la tienda de Teams en la aplicación de escritorio de Teams." lightbox="media/built-for-your-org2.png":::

Para obtener más información, consulta [Comprender y administrar aplicaciones personalizadas y de instalación de prueba](custom-app-overview.md).

## <a name="about-app-templates"></a>Información de plantillas de aplicación

Con los métodos de desarrollo de aplicaciones, Microsoft crea y proporciona aplicaciones de muestra funcionales y listas para producción. Colectivamente, estas aplicaciones se denominan plantillas de aplicaciones para Teams y se proporcionan a:

* Ilustra algunos casos de uso de colaboración en Teams.
* Muestra los procedimientos recomendados y métodos de desarrollo de aplicaciones.
* Proporciona aplicaciones de código abierto que los desarrolladores pueden ampliar para crear sus propias aplicaciones.

Los desarrolladores de la organización personalizan las plantillas de aplicación con cambios sencillos en el código fuente proporcionado. Usted proporciona estas aplicaciones como aplicaciones personalizadas para los usuarios finales, para satisfacer las necesidades de la organización.

Para obtener más información, consulte [Plantillas de aplicación de Microsoft Teams](https://adoption.microsoft.com/microsoft-teams/app-templates/).

## <a name="discover-and-use-apps-in-teams"></a>Descubrir y usar aplicaciones en Teams

Los usuarios pueden ver todas las aplicaciones disponibles en Teams desde la tienda de aplicaciones de Teams en un cliente de escritorio o web de Teams. Los usuarios pueden buscar por nombre, examinar por categoría y buscar por aplicaciones creadas para su organización y creadas con Power Platform para descubrir e instalar aplicaciones en Teams.

Las aplicaciones se pueden anclar a Teams para facilitar el acceso. Los usuarios pueden [anclar aplicaciones por su cuenta](https://support.microsoft.com/office/pin-an-app-for-easy-access-3045fd44-6604-4ba7-8ecc-1c0d525e89ec) si su directiva de configuración lo permite y si el administrador de Teams permite la aplicación. Los administradores pueden anclar aplicaciones y controlar el comportamiento de las aplicaciones ancladas. Para obtener más información, consulte [Directivas de configuración de aplicaciones](/teams-app-setup-policies).

:::image type="content" source="media/user-app-experience-find-apps.png" alt-text="Captura de pantalla que muestra todos los lugares donde los usuarios pueden examinar las aplicaciones en Microsoft Teams." lightbox="media/user-app-experience-find-apps-full.png":::

Los usuarios pueden buscar y agregar aplicaciones a Teams desde la tienda de aplicaciones de Teams. También pueden agregar aplicaciones directamente desde el contexto en el que estén trabajando, como la pestaña de chat o canal, la reunión de Teams o el área de mensajería. Para obtener más información, vea [Agregar una aplicación a Microsoft Teams](https://support.microsoft.com/office/add-an-app-to-microsoft-teams-b2217706-f7ed-4e64-8e96-c413afd02f77).

Un usuario puede agregar y usar una aplicación solo cuando un administrador permite que la aplicación esté disponible para el usuario mediante [directivas de permisos](teams-app-permission-policies.md). El administrador de TI de una organización tiene un control completo sobre quién puede instalar qué aplicaciones en cada contexto. Los usuarios no pueden agregar aplicaciones que estén bloqueadas; cualquier aplicación con un icono de candado en la tienda de Teams está bloqueada para el usuario. Sin embargo, [los usuarios pueden solicitar su aprobación al administrador de TI de su organización](https://support.microsoft.com/office/request-apps-that-require-approval-by-your-org-924e3a9e-33f0-44c2-9e81-e875214c05ae). Una vez aprobada la aplicación, los usuarios pueden agregarla desde la tienda de Teams.

> [!NOTE]
> Solo los usuarios pueden solicitar una aprobación para agregar una aplicación en Teams.

## <a name="understand-app-capabilities"></a>Comprender las funcionalidades de la aplicación

Las capacidades de la aplicación teams son las funcionalidades básicas que se pueden crear en una aplicación para habilitar la integración y la interacción.

:::row:::
    :::column span="":::
    :::column-end:::
    :::column span="3":::
        :::image type="content" source="media/teams-app-capabilities-group.png" alt-text="Gráfico que muestra las capacidades de la aplicación de una aplicación de Microsoft Teams." border="false":::
    :::column-end:::
    :::column:::
    :::column-end:::
:::row-end:::

Para proporcionar una experiencia enriquecida que permita a los usuarios finales trabajar en Teams, los desarrolladores de aplicaciones crean aplicaciones con las siguientes capacidades:

* **Bots**: Los bots también se conocen como bots chatbot o bots conversacionales. Es una aplicación que ejecuta tareas repetitivas y simples. Una interacción de bot puede ser una pregunta y una respuesta rápidas, o puede ser una conversación compleja que proporcione acceso a servicios o ayuda. Los usuarios pueden mantener una conversación con un bot en un chat personal, canal o chat grupal. Para obtener más información, consulte [Bots en Microsoft Teams](/microsoftteams/platform/bots/what-are-bots).

  Teams admite bots en los canales y conversaciones privadas. Los administradores pueden controlar si se permite el uso de bots en una organización con Microsoft 365 u Office 365. Para obtener información sobre cómo activar o desactivar los bots personalizados, consulte [Información general sobre administración y gobernanza de aplicaciones en el Centro de administración de Teams](manage-apps.md).

* **Pestañas: las** pestañas son páginas web con conocimiento de Teams ancladas en la parte superior de un canal o un chat. Las pestañas le permiten interactuar con contenido y servicios con una experiencia similar a la web. Son sencillas etiquetas HTML <iframe\> que apuntan a dominios declarados en el manifiesto de la aplicación y se pueden agregar como parte de un canal dentro de un equipo, chat de grupo o aplicación personal para un usuario individual. Para obtener más información, consulte [Pestañas de Microsoft Teams](/microsoftteams/platform/tabs/what-are-tabs).
  En cada chat privado, las pestañas de Conversaciones, Archivos, Organización y Actividad se crean de forma predeterminada. Además de estas pestañas integradas, los desarrolladores pueden diseñar y agregar pestañas personalizadas. Para obtener más información, vea [Usar fichas integradas y personalizadas en Teams](/microsoftteams/platform/tabs/what-are-tabs).

* **Webhooks y conectores**: webhooks y conectores ayudan a conectar los servicios web a canales y equipos en Microsoft Teams. Los webhooks son una devolución de llamada HTTP definida por el usuario que notifica a los usuarios cualquier acción que se haya realizado en el canal de Teams. Es una forma de que una aplicación obtenga datos en tiempo real. Los conectores permiten a los usuarios suscribirse para recibir notificaciones y mensajes de sus servicios web. Para obtener más información, vea [Webhooks and connectors (Webhooks and connectors](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)).

  Para permitir a los usuarios usar conectores personalizados en Teams, vea [Usar conectores personalizados en Teams](office-365-custom-connectors.md).

* **Extensiones de mensajería**: las extensiones de mensajería son accesos directos para insertar contenido de la aplicación o para actuar en un mensaje sin que los usuarios finales tengan que salir de la conversación. Los usuarios pueden buscar o iniciar acciones en un sistema externo desde el área redactar mensaje, el cuadro de comandos o directamente desde un mensaje. Para obtener más información, vea [Extensiones de mensajes](/microsoftteams/platform/messaging-extensions/what-are-messaging-extensions?tabs=dotnet).

* **Extensiones de reunión**: los usuarios pueden mejorar la experiencia de las reuniones integrando fichas, bots y extensiones de mensajes en las reuniones y haciendo que las reuniones sean más productivas. Puede identificar varios roles y tipos de usuario de participantes, obtener eventos de reunión y generar cuadros de diálogo en la reunión. Para obtener más información, consulte [Aplicaciones para reuniones de Teams](/microsoftteams/platform/apps-in-teams-meetings/teams-apps-in-meetings).

* **Tarjetas y módulos de tareas: las tarjetas** proporcionan a los usuarios diversos mensajes visuales, de audio y seleccionables, así como ayuda en el flujo de conversación. Los módulos de tareas le ayudan a crear experiencias emergentes modales en Microsoft Teams. Son útiles para iniciar y completar las tareas, o para mostrar información enriquecida, como vídeos o paneles de Power Business Intelligence (BI). Para obtener más información, vea [Tarjetas y módulos de tareas](/microsoftteams/platform/task-modules-and-cards/cards-and-task-modules).

Para ver casos de uso comunes asignados a las capacidades de Teams, consulte [Asignar los casos de uso a las capacidades de la aplicación Teams](/microsoftteams/platform/concepts/design/map-use-cases).

## <a name="related-articles"></a>Artículos relacionados

* [Obtenga más información sobre las plantillas de aplicaciones para Teams](/microsoftteams/platform/samples/app-templates).
* [Actualizaciones de aplicaciones de Teams y rol de administrador](apps-update-experience.md)
* [Información general sobre administración y gobierno de aplicaciones en el Centro de administración de Teams](manage-apps.md)

