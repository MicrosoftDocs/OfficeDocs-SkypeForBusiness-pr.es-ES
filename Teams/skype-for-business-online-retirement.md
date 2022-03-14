---
title: Retirada de Skype Empresarial Online
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Obtenga información sobre el plan de jubilación de Skype Empresarial Online y cómo Microsoft está ayudando a los clientes a migrar a Teams.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6c18871756c8081b7013666d98d1599cfec4117f
ms.sourcegitcommit: b635f3765498ae23f535a33fa9ffea5068eecb14
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2022
ms.locfileid: "63463743"
---
# <a name="skype-for-business-online-retirement"></a>Retirada de Skype Empresarial Online

El 31 de julio de 2021, Microsoft se retiró Skype Empresarial Online. Esta retirada se anunció en julio de 2019 para dar a los clientes un aviso con dos años de antelación para planear sus actualizaciones a Microsoft Teams. Teams es la aplicación principal para la comunicación y la colaboración en Microsoft 365. Con Skype Empresarial Online retirado, Microsoft quiere asegurarse de que los clientes tienen la información y los recursos necesarios para planear y ejecutar una actualización correcta a Teams.  El Skype consumidor no se ve afectado por esta retirada.

## <a name="why-is-skype-for-business-online-retiring"></a>¿Por qué Skype Empresarial online se retira?

Desde su introducción, Skype Empresarial Online ha sido una herramienta valiosa para millones de personas de todo el mundo. Al combinar mensajería instantánea, llamadas y vídeo, Skype Empresarial Online estableció nuevas posibilidades para las comunicaciones empresariales. Teams es el siguiente capítulo de esa visión. 

Las capacidades de Microsoft Teams van más allá de las de Skype Empresarial Online. La innovación y el desarrollo continuos de la plataforma Teams los usuarios se benefician de un rendimiento, funcionalidad, flexibilidad y seguridad más completos. Al combinar las siguientes funcionalidades en una sola experiencia, Teams nuevas formas de trabajar:

- Chat
- Vídeo
- Llamadas
- Colaboración en documentos
- Integración de aplicaciones

Teams es más que una actualización para Skype Empresarial Online. Es una herramienta eficaz que permite a las escuelas y organizaciones ser más ágiles y mejorar la eficiencia de los flujos de trabajo clave. Obtenga más información sobre las ventajas de Teams en las white paper de Forrester, [The Total Economic Impact™ of Microsoft Teams](https://www.microsoft.com/microsoft-365/blog/wp-content/uploads/sites/2/2019/04/Total-Economic-Impact-Microsoft-Teams.pdf?rtc=1).

Para obtener más información sobre la Skype Empresarial en línea, consulte Preguntas más frecuentes: Actualizar de [Skype Empresarial a Microsoft Teams](FAQ-journey.yml).

## <a name="organizations-with-skype-for-business-online"></a>Organizaciones con Skype Empresarial Online

Microsoft proporciona un proceso de actualización asistido para ayudar a las organizaciones a Skype Empresarial usuarios en línea restantes a Teams solo. Teams está disponible en la mayoría Microsoft 365 planes de negocios y Enterprise, y las inversiones de licencias existentes se llevan a cabo Teams. Las funcionalidades que son cargas de trabajo premium en Skype Empresarial Online hoy seguirán considerándose del mismo modo en Microsoft Teams. Por ejemplo, si ha comprado conferencias de audio independiente o como parte de E5 con Skype Empresarial, audioconferencia se habilitará en Teams.

## <a name="organizations-with-on-premises-deployments-of-skype-for-business-server"></a>Organizaciones con implementaciones locales de Skype Empresarial Server

La retirada de Skype Empresarial Online no afecta al soporte técnico para implementaciones locales de Skype Empresarial Server Lync Server 2013. Sin embargo, los clientes híbridos con una combinación de usuarios en línea y locales deben actualizar los *usuarios en* línea. Estos usuarios en línea deben asignarse Teams modo solo con TeamsUpgradePolicy. Microsoft proporciona actualizaciones asistidos para ayudar a automatizar la actualización de los usuarios Skype Empresarial en línea a Teams modo solo técnico. Las organizaciones híbridas no necesitan mover sus usuarios *locales Skype Empresarial a* la nube como resultado de esta retirada. Microsoft es totalmente compatible con organizaciones híbridas con una combinación de Teams usuarios y usuarios locales Skype Empresarial usuarios. Los clientes con implementaciones híbridas de Skype Empresarial Server o Lync Server 2013 deben revisar las implicaciones de la próxima retirada de [Skype Empresarial Online](/skypeforbusiness/hybrid/plan-hybrid-connectivity#implications-of-the-upcoming-retirement-of-skype-for-business-online).

## <a name="what-to-expect-post-retirement"></a>Qué esperar después de la retirada

Ya no es posible asignar a los usuarios que están en la nube un modo distinto de TeamsOnly. Esto significa:
 - Al otorgar licencias a nuevos usuarios (excepto los usuarios que se aloman en Skype Empresarial Server locales), los usuarios se asignan automáticamente al modo TeamsOnly, independientemente de la directiva global del inquilino de TeamsUpgradePolicy.
 - En organizaciones híbridas, al mover usuarios a la nube, los usuarios se asignan automáticamente al modo TeamsOnly (regarldess de `MoveToTeams` si el modificador se especificó en `Move-CsUser`.)
 - Los usuarios que se encuentran en la nube (por ejemplo, no usan  un servidor Skype Empresarial local) no pueden tener asignado un modo distinto de Teams solo.

Es posible que los clientes tengan partes restantes de su población de usuarios que se encuentran en Skype Empresarial Online y que aún no están asignados Teams modo solo.  Los clientes deben asignar Teams solo a estos usuarios tan pronto como sea posible.  Además, Microsoft proporcionará actualizaciones asistidos para Skype Empresarial usuarios en línea que no Teams modo solo.  La experiencia de actualización asistida depende de si su organización es una organización en línea pura o una organización con usuarios Skype Empresarial local.  Para obtener más información, vea [Actualizaciones asistidos de Skype Empresarial Online a Microsoft Teams](upgrade-assisted.md).

Una vez completada la actualización asistido, *todos los usuarios* en línea estarán en el Teams solo. Los usuarios del Teams solo reciben chats y llamadas entrantes en Teams y también programan reuniones en Teams. No pueden iniciar chats ni llamadas ni programar reuniones en Skype Empresarial Online.  Sin embargo, Teams solo los usuarios pueden unirse Skype Empresarial reuniones que ya tengan o reciban en el futuro. Por último, *los usuarios que se* alocución local permanecen en el entorno local y no se Teams solo.


## <a name="how-microsoft-is-helping-customers-upgrade-to-teams"></a>Cómo Microsoft ayuda a los clientes a actualizar a Teams

Le recomendamos encarecidamente que comience la actualización de Skype Empresarial Online a Teams hoy.

Aproveche los recursos disponibles para ayudar a planear su Teams y actualizar desde Skype Empresarial:

- [Teams de implementación y actualización](upgrade-start-here.md): guía técnica gratuita para administradores de TI.

- [Teams](./upgrade-workshops-landing-page.yml) talleres de planeación de actualizaciones: talleres interactivos gratuitos de planeación de actualizaciones, donde recibirá instrucciones, procedimientos recomendados y recursos diseñados para ayudarle a planear e implementar la actualización a Teams.

- [Actualizaciones asistidos de Skype Empresarial Online a Microsoft Teams](upgrade-assisted.md): programa automatizado que le ayuda a actualizar Skype Empresarial usuarios en línea a Teams.

- [FastTrack para Microsoft 365](https://www.microsoft.com/fasttrack/microsoft-365): Teams de implementación disponible para los planes que califiquen.

- [Teams en directo](./instructor-led-training-teams-landing-page.yml): clases de aprendizaje en línea gratuitas diseñadas para que su organización esté en marcha con Teams.

- [Teams tiza:](./chalk-talks-landing-page.yml) talleres en línea gratuitos para profesionales de TI y responsables de la toma de decisiones que describen procedimientos recomendados para escenarios clave en Teams.

- [Partners de Microsoft](https://www.microsoft.com/solution-providers/home): los proveedores de soluciones de Microsoft pueden ayudarle a aprovechar al máximo Teams.

- [Microsoft Teams blog](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog): Teams nuevas características, recursos de adopción y uso, Teams dispositivos e integración con otras aplicaciones empresariales.

Si es un cliente actual de Skype Empresarial Online, empiece a planear la actualización a Teams hoy. Estamos encantados de que experimente sus potentes capacidades de comunicación y colaboración, y nos comprometemos a ayudar en el camino.




