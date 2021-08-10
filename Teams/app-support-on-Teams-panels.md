---
title: Microsoft Teams aplicaciones/compatibilidad con aplicaciones de línea de negocio (LOB) en Teams paneles
author: amandafrechinjackson
ms.author: v-amandaf
manager: jsarrasin
ms.date: 8/5/2021
ms.topic: conceptual
audience: ITPro
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Describe la compatibilidad con aplicaciones Teams aplicaciones/aplicaciones de LOB.
ms.collection:
- M365-voice
- M365-collaboration
- skype-for-business-itpro
- skype-for-business-online
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 56c26cef98e316a821f31d3baa014cd1e9f9695743c34493c8880ac85f232830
ms.sourcegitcommit: 0e9516c51105e4d89c550d2ea2bd8e7649a1163b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2021
ms.locfileid: "54591224"
---
# <a name="microsoft-teams-appsline-of-business-lob-app-support-on-teams-panels"></a>Microsoft Teams aplicaciones/compatibilidad con aplicaciones de línea de negocio (LOB) en Teams paneles

Teams paneles agrega compatibilidad con Teams aplicaciones de línea de negocio (LOB). Esto permitirá a las empresas agregar experiencias adicionales en los paneles para satisfacer las necesidades de su organización. Esta versión admite contenido web estático.

> [!IMPORTANT]
> Esta característica solo está disponible después de actualizar los Teams dispositivos de paneles. Debes tener la versión 1449/1.0.97.2021070601 o posterior de la aplicación Teams para tener compatibilidad con aplicaciones dentro de Teams paneles.

## <a name="set-up-and-manage-teams-panels-apps-in-teams-admin-center"></a>Configurar y administrar aplicaciones Teams paneles en Teams centro de administración 

Microsoft Teams aplicaciones aportan información clave, herramientas comunes y procesos de confianza a donde las personas se reúnen, aprenden y trabajan. Teams aplicaciones funcionan [a través de funcionalidades integradas](/platform/concepts/capabilities-overview). Ahora, como administrador de TI, tienes la opción de qué aplicaciones incluir en el dispositivo de paneles de Teams de tu organización y personalizar los permisos a través del centro de administración Teams organización.

Ahora puedes usar las aplicaciones Teams en Teams paneles y personalizar la experiencia del usuario en función de las necesidades de la organización. Puedes decidir a qué aplicación web pueden acceder los usuarios y usar y priorizar las vistas de la aplicación. Algunas opciones, como el bot y las capacidades de mensajería, no se admiten en este momento. Obtenga más información sobre las Teams y cómo administrar los dispositivos en Microsoft Teams.

## <a name="manage-apps-on-teams-panels-in-teams-admin-center"></a>Administrar aplicaciones en Teams paneles en Teams centro de administración

**Nota:** Debe ser un administrador global o un administrador Teams de servicio para acceder al centro Teams administración.

Los usuarios finales pueden ver pero no instalar aplicaciones en Teams paneles. Como administrador, puede ver y administrar todas las aplicaciones Teams para su organización a través del centro Teams administración. Obtén más información sobre cómo puedes administrar tus aplicaciones en el Centro de administración de Microsoft Teams a través de la **página** Administrar aplicaciones. La **página Administrar aplicaciones** dentro del centro de administración Teams es también donde puedes cargar aplicaciones [personalizadas.](/manage-apps#publish-a-custom-app-to-your-organizations-app-store)

Después de configurar aplicaciones, [](/teams-app-permission-policies) puedes usar [](/teams-app-setup-policies) directivas de permisos de aplicaciones y directivas de configuración de aplicaciones para configurar la experiencia de la aplicación para cuentas de salón específicas de la organización.

## <a name="pin-apps-on-teams-panels-with-app-setup-policies"></a>Anclar aplicaciones en Teams con directivas de configuración de aplicaciones

Dado que Teams ofrece la capacidad de mostrar una amplia variedad de aplicaciones, los administradores pueden decidir qué aplicaciones son  más esenciales para la organización y anclar solo estas para los paneles de Teams Pantalla principal para un acceso rápido. Si hay más de cinco aplicaciones ancladas o alguna aplicación sin anclar, aparecerán en la **pantalla** Más. Microsoft recomienda crear una directiva de configuración de aplicaciones personalizada específicamente para Teams paneles.

![Captura de pantalla de la interfaz de usuario de la página directivas de configuración de la aplicación.](media/appsetup1.png) 

Para administrar las aplicaciones ancladas que se muestran en los paneles de Teams, inicie sesión  en el Centro de administración de Teams para su organización y vaya Teams directivas de configuración de aplicaciones Seleccione o cree una nueva directiva aplicaciones \>  \>  \> ancladas.

![Captura de pantalla de la sección aplicaciones ancladas dentro de la interfaz de usuario.](media/appsetup2.png) 

Microsoft recomienda desactivar  las aplicaciones Upload  personalizadas y Permitir la fijación de usuarios para obtener la mejor experiencia Teams aplicación en Teams paneles.

Para obtener más información sobre la anclación de aplicaciones, consulta [Administrar directivas de configuración de aplicaciones.](/teams-app-setup-policies)

## <a name="manage-apps-display-order-in-teams-panels"></a>Administrar el orden de visualización de aplicaciones Teams paneles 

![Sección Captura de pantalla de aplicaciones dentro de la interfaz de usuario.](media/appsetup3.png) 

Para administrar el orden en que se muestran las aplicaciones en los paneles de Teams, inicie sesión en el Centro de administración de Teams para su organización y vaya a **directivas** de configuración de aplicaciones de Teams Seleccione las aplicaciones ancladas a \>  \>  \> **directivas:** Subir o bajar .

## <a name="assigning-setup-policies-to-a-room-resource-account"></a>Asignar directivas de configuración a una cuenta de recursos de sala

Después de crear la directiva de configuración, el administrador tendrá que asignar esta directiva a la cuenta de recursos de sala que se firmará en los paneles Teams configuración. Para obtener más información, consulte [Asignar directivas a usuarios y grupos.](/assign-policies-users-and-groups)

## <a name="faq"></a>Preguntas más frecuentes

### <a name="how-long-does-it-take-for-teams-panels-to-get-the-new-or-updated-app-setup-policies"></a>¿Cuánto tiempo se necesita para que los Teams obtengan las directivas de configuración de aplicaciones nuevas o actualizadas?

Después de editar o asignar nuevas directivas en el centro de administración de Teams, los cambios pueden tardar hasta 24 horas en tener efecto. Los administradores pueden intentar cerrar sesión o iniciar sesión desde el panel, pulsar el  icono Configuración y volver **a** la pantalla inicio para intentar actualizar las directivas.

### <a name="what-is-the-ordering-of-the-apps-on-the-more-screen"></a>¿Cuál es el orden de las aplicaciones en la pantalla "Más"?

En la **página Más** aplicaciones, las aplicaciones ancladas aparecerán primero. A continuación, cualquier otra aplicación instalada aparecerá en orden alfabético.

### <a name="why-are-bot-apps-not-showing-up-on-teams-panels"></a>¿Por qué las aplicaciones de bot no se muestran en Teams paneles?

Solo se admite contenido web de pestañas estáticas en este momento.

### <a name="why-are-native-teams-apps-such-as-calendar-and-tasks-not-appearing-on-teams-panels"></a>¿Por qué Teams aplicaciones nativas, como Calendario y Tareas, no aparecen en Teams paneles?

Las Teams nativas, como Calendario y Tareas, no se muestran en Teams paneles.

### <a name="in-the-teams-admin-center-under-the-setup-policies-section-what-is-the-difference-between-installed-apps-and-pinned-apps"></a>En el Centro Teams administración, en la sección directivas de configuración, ¿cuál es la diferencia entre las aplicaciones instaladas y las aplicaciones ancladas?

Para Teams, Microsoft recomienda usar aplicaciones ancladas, por lo que el administrador puede seleccionar la aplicación deseada y reorganizar su ordenación.

**Nota:** Algunas aplicaciones no admiten la fijación de aplicaciones. Póngase en contacto con el desarrollador de la aplicación para habilitar la funcionalidad de anclado de aplicaciones.

### <a name="why-are-other-apps-appearing-in-the-more-screen-even-though-they-are-not-part-of-the-installed-or-pinned-apps-in-the-teams-app-setup-policy-section"></a>¿Por qué aparecen otras aplicaciones en la pantalla "Más" aunque no forman parte de las aplicaciones instaladas o ancladas en la sección directiva de configuración Teams aplicación?

Si las aplicaciones se instalaron anteriormente mediante otras directivas de aplicación o manualmente en los clientes de escritorio o web de Teams para la cuenta de recursos de sala usada en los paneles de Teams, es posible que el administrador deba iniciar sesión en la cuenta de recursos de sala en Teams y desinstalar manualmente las aplicaciones haciendo clic con el botón secundario en la aplicación y **seleccionando Desinstalar**.

### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>¿Por qué no puedo encontrar una aplicación en el panel "Agregar aplicaciones ancladas"?

No todas las aplicaciones se pueden anclar a Teams a través de una directiva de configuración de aplicaciones. Es posible que algunas aplicaciones no admitan esta funcionalidad. Para buscar aplicaciones que se pueden anclar, busca la aplicación en el panel Agregar aplicaciones **ancladas.** Para obtener más información, consulta las preguntas [más frecuentes en Trabajar con directivas de configuración de aplicaciones.](/teams-app-setup-policies#why-cant-i-find-an-app-in-the-add-pinned-apps-pane)

### <a name="why-am-i-seeing-an-allow-user-pinning-pop-up-in-the-setup-policies-panel-after-i-turn-off-allow-user-pinning"></a>¿Por qué veo una ventana emergente "Permitir anclación de usuario" en el panel de directivas de configuración después de desactivar "Permitir anclación de usuario?"

![Captura de pantalla de la sección de directiva de configuración dentro de la interfaz de usuario con una ventana emergente que confirma que la fijación del usuario está activa.](media/appsetup4.png) 

Este comportamiento se espera para un dispositivo en un espacio compartido y ayuda a evitar la fijación involuntaria de aplicaciones.
