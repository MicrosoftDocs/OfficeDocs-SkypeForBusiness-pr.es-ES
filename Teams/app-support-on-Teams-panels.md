---
title: Microsoft Teams aplicaciones o la aplicación línea de negocio (LOB) en Teams paneles
author: amandafrechinjackson
ms.author: v-amandaf
manager: jsarrasin
ms.date: 06/30/2021
ms.topic: conceptual
audience: ITPro
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Describe el soporte técnico para Teams aplicaciones o aplicaciones LOB.
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
ms.openlocfilehash: f4b07078c49fd8fac9e690ed60072dfbefcfc020
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53775198"
---
# <a name="microsoft-teams-appsline-of-business-lob-app-support-on-teams-panels"></a>Microsoft Teams aplicaciones o la aplicación línea de negocio (LOB) en Teams paneles

Teams paneles está agregando compatibilidad con Teams aplicaciones de línea de negocio (LOB). Esto permitirá a las empresas agregar experiencias adicionales en los paneles para satisfacer las necesidades de su organización. Esta versión admite contenido web estático.

> [!IMPORTANT]
> Esta característica solo está disponible después de actualizar Teams dispositivos de paneles. Debe tener la versión Teams 1449/1.0.97.2021070601 o posterior de la aplicación para tener compatibilidad con aplicaciones en Teams paneles.

## <a name="set-up-and-manage-teams-panels-apps-in-teams-admin-center"></a>Configurar y administrar aplicaciones Teams paneles en Teams de administración 

Microsoft Teams aplicaciones traen información clave, herramientas comunes y procesos de confianza para que las personas se reúnan, aprendan y trabajen. Teams aplicaciones funcionan [a través de funcionalidades integradas.](/platform/concepts/capabilities-overview) Ahora, como administrador de TI, tiene la opción de qué aplicaciones incluir en el dispositivo de paneles de Teams de su organización y personalizar los permisos a través del centro de administración de Teams organización.

Ahora puede usar las aplicaciones Teams en Teams paneles y personalizar la experiencia del usuario en función de las necesidades de su organización. Puede decidir a qué aplicación web pueden acceder los usuarios, usar y priorizar las vistas de la aplicación. Algunas opciones, como el bot y las capacidades de mensajería, no son compatibles en este momento. Obtenga más información sobre las Teams aplicaciones y cómo administrar sus dispositivos en Microsoft Teams.

## <a name="manage-apps-on-teams-panels-in-teams-admin-center"></a>Administrar aplicaciones en Teams paneles en Teams centro de administración

**Nota:** Debe ser un administrador global o un administrador Teams de servicio para acceder al centro Teams administración.

Los usuarios finales pueden ver pero no instalar aplicaciones en Teams paneles. Como administrador, puede ver y administrar todas las Teams aplicaciones de su organización a través del centro Teams administración. Obtenga más información sobre cómo puede administrar las aplicaciones en el centro de Microsoft Teams a través de la **página** Administrar aplicaciones. La **página Administrar aplicaciones** del centro de Teams también es donde puede cargar aplicaciones [personalizadas.](/manage-apps#publish-a-custom-app-to-your-organizations-app-store)

Después de configurar aplicaciones, [](/teams-app-permission-policies) puede usar [](/teams-app-setup-policies) directivas de permisos de aplicación y directivas de configuración de aplicaciones para configurar la experiencia de aplicación para cuentas de salón específicas de su organización.

## <a name="pin-apps-on-teams-panels-with-app-setup-policies"></a>Anclar aplicaciones en Teams paneles con directivas de configuración de aplicaciones

Como Teams ofrece la capacidad de mostrar una amplia variedad de aplicaciones, los administradores pueden decidir qué aplicaciones son más  esenciales para la organización y anclar solo estas para los paneles de Teams Pantalla principal para un acceso rápido. Si hay más de cinco aplicaciones ancladas o alguna aplicación no anclada, aparecerán en la **pantalla** Más. Microsoft recomienda crear una directiva de configuración de aplicaciones personalizada específicamente para Teams paneles.

![Captura de pantalla de la interfaz de usuario de la página directivas de configuración de aplicaciones.](media/appsetup1.png) 

Para administrar las aplicaciones ancladas que se muestran en los paneles de Teams, inicie sesión en el Centro de administración de Teams para su organización y vaya **Teams** las directivas de configuración de aplicaciones de Teams Seleccione o Cree una nueva directiva Aplicaciones \>  \>  \> ancladas.

![Captura de pantalla de la sección de aplicaciones ancladas dentro de la interfaz de usuario.](media/appsetup2.png) 

Microsoft recomienda desactivar  Upload aplicaciones personalizadas  y Permitir la anclación de usuario para obtener la mejor experiencia Teams aplicaciones en Teams paneles.

Para obtener más información sobre cómo anclar aplicaciones, vea [Administrar directivas de configuración de aplicaciones.](/teams-app-setup-policies)

## <a name="manage-apps-display-order-in-teams-panels"></a>Administrar el orden de visualización de aplicaciones en Teams paneles 

![Captura de pantalla de la sección aplicaciones de la interfaz de usuario.](media/appsetup3.png) 

Para administrar el orden en que se muestran las aplicaciones en los paneles de Teams, inicie sesión en el Centro de administración de Teams para su organización y vaya **a directivas** de configuración de aplicaciones de Teams Seleccione las aplicaciones ancladas a directivas: Subir \>  \>  \>  **o** bajar.

## <a name="assigning-setup-policies-to-a-room-resource-account"></a>Asignar directivas de configuración a una cuenta de recursos de sala

Después de crear la directiva de configuración, el administrador tendrá que asignar esta directiva a la cuenta de recursos de sala que se haya iniciado sesión en los paneles Teams sala. Para obtener más información, consulte [Asignar directivas a usuarios y grupos.](/assign-policies-users-and-groups)

## <a name="faq"></a>Preguntas más frecuentes

### <a name="how-long-does-it-take-for-teams-panels-to-get-the-new-or-updated-app-setup-policies"></a>¿Cuánto tiempo se necesita Teams paneles para obtener las directivas de configuración de aplicaciones nuevas o actualizadas?

Después de editar o asignar nuevas directivas en el Teams de administración, los cambios pueden tardar hasta 24 horas en tener efecto. Los administradores pueden intentar cerrar sesión o iniciar sesión desde el panel, pulsar el  icono **de Configuración** y volver a la pantalla Inicio para intentar actualizar las directivas.

### <a name="what-is-the-ordering-of-the-apps-on-the-more-screen"></a>¿Cuál es el orden de las aplicaciones en la pantalla "Más"?

En la **página Más** aplicaciones, las aplicaciones ancladas aparecerán en primer lugar. A continuación, cualquier otra aplicación instalada aparecerá en orden alfabético.

### <a name="why-are-bot-apps-not-showing-up-on-teams-panels"></a>¿Por qué las aplicaciones de bot no se muestran en Teams paneles?

Solo se admite el contenido web de pestañas estáticas en este momento.

### <a name="why-are-native-teams-apps-such-as-calendar-and-tasks-not-appearing-on-teams-panels"></a>¿Por qué Teams aplicaciones nativas, como Calendario y Tareas, no aparecen en Teams paneles?

Las Teams nativas, como Calendario y Tareas, no se muestran en Teams paneles.

### <a name="in-the-teams-admin-center-under-the-setup-policies-section-what-is-the-difference-between-installed-apps-and-pinned-apps"></a>En el Teams de administración, en la sección directivas de configuración, ¿cuál es la diferencia entre las aplicaciones instaladas y las aplicaciones ancladas?

Para Teams paneles, Microsoft recomienda usar aplicaciones ancladas para que el administrador pueda seleccionar la aplicación deseada y reorganizar su orden.

**Nota:** Algunas aplicaciones no admiten la anclación de aplicaciones. Póngase en contacto con el desarrollador de aplicaciones para habilitar la funcionalidad de anclado de aplicaciones.

### <a name="why-are-other-apps-appearing-in-the-more-screen-even-though-they-are-not-part-of-the-installed-or-pinned-apps-in-the-teams-app-setup-policy-section"></a>¿Por qué aparecen otras aplicaciones en la pantalla "Más" aunque no forman parte de las aplicaciones instaladas o ancladas en la sección de directiva de configuración de aplicaciones Teams aplicación?

Si las aplicaciones se instalaron previamente a través de otras directivas de aplicación o manualmente en los clientes de escritorio o web de Teams para la cuenta de recursos de sala usada en paneles de Teams, es posible que el administrador tenga que iniciar sesión en la cuenta de recursos de la sala en Teams y desinstalar manualmente las aplicaciones haciendo clic con el botón derecho en la aplicación y **seleccionando** Desinstalar .

### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>¿Por qué no puedo encontrar una aplicación en el panel "Agregar aplicaciones ancladas"?

No todas las aplicaciones se pueden anclar a Teams a través de una directiva de configuración de aplicaciones. Es posible que algunas aplicaciones no admitan esta funcionalidad. Para buscar aplicaciones que se pueden anclar, busque la aplicación en el panel Agregar aplicaciones **ancladas.** Para obtener más información, consulte las preguntas [más frecuentes en Trabajar con directivas de configuración de aplicaciones.](/teams-app-setup-policies#why-cant-i-find-an-app-in-the-add-pinned-apps-pane)

### <a name="why-am-i-seeing-an-allow-user-pinning-pop-up-in-the-setup-policies-panel-after-i-turn-off-allow-user-pinning"></a>¿Por qué veo una ventana emergente "Permitir anclación de usuario" en el panel directivas de configuración después de desactivar "Permitir anclación de usuario?"

![Captura de pantalla de la sección de directiva de configuración dentro de la interfaz de usuario con una ventana emergente que confirma que la fijación de usuario está activa.](media/appsetup4.png) 

Este comportamiento se espera para un dispositivo en un espacio compartido y ayuda a evitar la fijación involuntaria de aplicaciones.
