---
title: Información general de la implementación empresarial de Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Obtenga información sobre cómo implementar características empresariales de Microsoft Teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: bd3e60fafecd3cf025187935a9dc28b492c39d1b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121418"
---
# <a name="teams-enterprise-deployment-overview"></a>Información general de la implementación empresarial de Teams

Si es una empresa mediana o grande, debe pensar en cómo se desarrollará el servicio para los usuarios, cómo va a implementar el cliente de Microsoft Teams en ellos, cómo su diseño de red podría afectar a la calidad de la comunicación en tiempo real, y así sucesivamente. Consulte las siguientes secciones para punteros a artículos que le ayudarán a planear Teams en su organización.

> [!NOTE]
> Si aún no lo ha hecho, le recomendamos encarecidamente que empiece la implementación de Teams con un programa piloto. Un programa piloto le permitirá a usted y a algunos usuarios pioneros familiarizarse con Teams y sus características antes de su planeación y lanzamiento. Para obtener más información sobre cómo iniciar el programa piloto, consulte [Introducción a Microsoft Teams](get-started-with-teams-quick-start.md).

Cuando haya leído las secciones siguientes y tenga todo listo para empezar a implementar Teams en su organización, vea [Configurar Microsoft Teams en su empresa](deploy-enterprise-setup.md).

## <a name="architecture"></a>Arquitectura

Teams está totalmente integrado en Microsoft 365 y utiliza muchas características para impulsar el chat, el uso compartido de archivos, las reuniones, la telefonía, la transmisión de vídeo y mucho más. Antes de familiarizarse con Teams, consulte los [pósteres de arquitectura de TI y soluciones de telefonía de Microsoft Teams](teams-architecture-solutions-posters.md) para familiarizarse con el funcionamiento de Teams con el resto de Microsoft 365 para crear una experiencia de colaboración completa para los usuarios.

## <a name="workloads"></a>Cargas de trabajo

Teams tiene tres cargas de trabajo que se pueden implementar independientemente entre sí: **chat, equipos y canales**; **conferencias y reuniones**; y **sistema telefónico y conectividad RTC (red telefónica conmutada)**. Cada carga de trabajo tiene su propia sección en la documentación para que sea más fácil encontrar información sobre esa carga de trabajo. Esto incluye información de planeación de implementación.

Para ver información de planeación de implementación para la carga de trabajo que quiere implementar, vea los artículos siguientes:

- [Chat, equipos y canales](deploy-chat-teams-channels-microsoft-teams-landing-page.md)
- [Reuniones y conferencias](deploy-meetings-microsoft-teams-landing-page.md)
- [Sistema telefónico y conectividad RTC](cloud-voice-landing-page.md)

## <a name="network-planner"></a>Planificador de red

La planeación de red de Teams es muy importante cuando tiene un gran número de usuarios, redes complejas o ambos. Los equipos admiten las llamadas de voz y las videoconferencias, que dependen de las comunicaciones en tiempo real para proporcionar la mejor experiencia posible a los usuarios. Las redes deben:

- Tener suficiente capacidad de ancho de banda para dar cabida al número de llamadas de voz, videoconferencias, reuniones, uso compartido de pantallas, entre otros.
- Tener hardware de red compatible con protocolos de comunicación en tiempo real.
- Permita los puertos de red necesarios entre los dispositivos en sus redes, los servicios de Microsoft 365 y los usuarios externos.

Consulte los artículos siguientes para ayudarle a comprender los requisitos de red de Teams:

- [Preparar la red de la organización para Microsoft Teams](prepare-network.md)
- [Servidores proxy para Skype Empresarial Online o Teams](proxy-servers-for-skype-for-business-online.md)

Para ayudarle con la planeación, Teams incluye el planificador de red. El planificador de red le pregunta sobre el número y los tipos de usuarios que tiene, cuántos sitios tiene su organización, la capacidad de ancho de banda de los vínculos de red y mucho más. Con esta información, el planificador de red crea un informe que muestra los requisitos de ancho de banda para cada actividad, junto con las recomendaciones.

 > [!div class="nextstepaction"]
> [Ir al planificador de red](https://admin.teams.microsoft.com/networkplanner/organization)

(Debe ser [administrador global de Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles#commonly-used-microsoft-365-admin-center-roles) para abrir el planificador de red).

Para obtener más información sobre cómo funciona el planificador de red, vea [Usar el planificador de red para Microsoft Teams](network-planner.md).

Para ver un ejemplo de cómo el planificador de red puede planear su red, vea [Usar el planificador de red ( escenario de ejemplo](tutorial-network-planner-example.yml)).

## <a name="teams-advisor"></a>Asesor de Teams

El asesor de Teams es una solución de Teams que reúne equipos, canales, uso compartido de archivos y planificador para crear un proyecto de implementación para su organización. El asesor de Teams crea un plan de proyecto específico para la carga de trabajo que seleccione (como chat, equipos y canales), que incluye las tareas recomendadas que debe realizar durante la implementación. Cada tarea contiene instrucciones, sugerencias y vínculos a artículos relevantes que le guiarán a través del proceso. Puede asignar fácilmente tareas a una o más personas, y especificar las fechas de inicio y finalización para cada tarea.

> [!TIP]
> Vea cómo puede usar el asesor de Teams para ayudarle a planear la implementación de Teams completando el módulo [Implementación con el asesor de Teams](/learn/modules/m365-teams-rollout-using-advisor/) en Microsoft Learn.

> [!div class="nextstepaction"]
> [Ir al asesor de Teams](https://admin.teams.microsoft.com/teams-deployment)

(Debe ser [administrador global de Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles#commonly-used-microsoft-365-admin-center-roles) para abrir el asesor de Teams).

Para obtener detalles sobre el funcionamiento del asesor de Teams, consulte [Usar el asesor de Teams para ayudarle a implementar Microsoft Teams](use-advisor-teams-roll-out.md).

## <a name="lifecycle-and-governance-planning"></a>Planificación del ciclo de vida y el gobierno

Al planear la implementación de Teams, necesita tener en cuenta el ciclo de vida de los equipos, canales, archivos, entre otros, de la organización. También debe pensar qué tipos de información se almacenarán en ellos. Los equipos se pueden crear para un proyecto específico, para un departamento, o pueden usarse como un recurso central para toda la organización. Cada uno de estos usos tiene requisitos diferentes, que dan lugar a preguntas como las siguientes:

- ¿Cuánto tiempo permanecerán activos los equipos?
- ¿Quién debe ser el propietario y el propietario de los equipos y sus canales?
- ¿Deben aplicarse determinados requisitos de cumplimiento a algunos equipos, pero no a otros?
- ¿Debe haber una directiva de nomenclatura para ayudar a los usuarios a identificar el equipo adecuado?

Crear directivas y directrices como parte de la implementación inicial le ayudará a asegurarse de que los usuarios pueden encontrar la información que necesitan. Pero también es importante tener en cuenta que las directivas adecuadas le ayudarán a proteger la organización de filtraciones de información, le ayudarán a cumplir con los requisitos reglamentarios y a retener la información según sea necesario para fines de archivo.

Para obtener más información sobre la administración del ciclo de vida y el gobierno en Teams, consulte lo siguiente:

- [Plan para la administración del ciclo de vida en Teams](plan-teams-lifecycle.md)
- [Planificar el gobierno en Teams](plan-teams-governance.md)

## <a name="adoption"></a>Adopción

Para asegurarse de que su organización y sus usuarios obtengan el máximo partido de Teams, necesita un programa de adopción. Un programa de adopción eficaz puede ayudar a los usuarios pioneros que pueden:

- Articular las ventajas de Teams a sus compañeros y a los líderes empresariales o de grupo.
- Provocar la emoción de otros usuarios que ven cómo Teams mejora la colaboración y facilita la conexión entre ellos.
- Ayudar a evaluar los procesos empresariales existentes y realizar recomendaciones sobre cómo se pueden integrar Equipos en ellos.
- Informar de nuevo al equipo de implementación, tanto los éxitos como las dificultades para ayudar a mejorar el proceso de adopción.

Para obtener más información sobre cómo configurar un programa de adopción, consulte [Adoptar Microsoft Teams](adopt-microsoft-teams-landing-page.md).