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
ms.openlocfilehash: dcd2148a3f939bd8799b7b3f8b86118359936b7c
ms.sourcegitcommit: d3d3d5a70a69359fc71f072ad6c651556f4eda00
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2022
ms.locfileid: "63783909"
---
# <a name="skype-for-business-online-retirement"></a>Retirada de Skype Empresarial Online

El 31 de julio de 2021, Microsoft se retiró Skype Empresarial Online. Esta retirada se anunció en julio de 2019 para dar a los clientes un aviso con dos años de antelación para planear sus actualizaciones a Microsoft Teams. Teams es la aplicación principal para la comunicación y la colaboración en Microsoft 365. Con Skype Empresarial Online retirado, Microsoft quiere asegurarse de que los clientes tienen la información y los recursos necesarios para planear y ejecutar una actualización correcta a Teams.  El Skype consumidor no se ve afectado por esta retirada. Para obtener información sobre por qué Skype Empresarial Online se retiró, vea Preguntas más frecuentes: Actualizar de Skype Empresarial [a Microsoft Teams](FAQ-journey.yml).

Microsoft comenzará a retirar la infraestructura Skype Empresarial online el 30 de junio de 2022 o después de esta. Este artículo contiene instrucciones para organizaciones con TeamsOnly usuarios que se actualizaron desde cualquier versión de Skype Empresarial.


## <a name="organizations-with-on-premises-deployments-of-skype-for-business-server"></a>Organizaciones con implementaciones locales de Skype Empresarial Server

La retirada de Skype Empresarial Online no afecta al soporte técnico para implementaciones locales de Skype Empresarial Server y Lync Server 2013. Sin embargo, los clientes híbridos con una combinación de usuarios en línea y locales deben actualizar los *usuarios en* línea. Todos los usuarios en línea deben tener asignado el modo TeamsOnly con TeamsUpgradePolicy. Microsoft proporciona actualizaciones asistidos para ayudar a automatizar la actualización de los usuarios Skype Empresarial online restantes al modo TeamsOnly. Las organizaciones híbridas no necesitan mover sus usuarios *locales Skype Empresarial a* la nube como resultado de esta retirada. Microsoft es totalmente compatible con organizaciones híbridas con una combinación de usuarios de TeamsOnly y usuarios Skype Empresarial locales. Los clientes con implementaciones híbridas de Skype Empresarial Server o Lync Server 2013 deben revisar la retirada [de Skype Empresarial Online](/skypeforbusiness/hybrid/plan-hybrid-connectivity#implications-of-the-upcoming-retirement-of-skype-for-business-online).

## <a name="what-to-expect-post-retirement"></a>Qué esperar después de la retirada

Ya no es posible asignar a los usuarios que se aloen en la nube un modo distinto de TeamsOnly. Esto significa:

 - Al otorgar licencias a nuevos usuarios que no se encuentran en el Skype Empresarial Server local, los usuarios se asignan automáticamente al modo TeamsOnly, independientemente de la directiva global del inquilino de TeamsUpgradePolicy.
 - En organizaciones híbridas `MoveToTeams` , al mover usuarios a la nube, se asigna automáticamente el modo TeamsOnly a los usuarios independientemente de si el modificador se especificó en `Move-CsUser`.
 - A los usuarios que se aloen en la nube no se les puede asignar un modo distinto de TeamsOnly. Los usuarios en línea *no usan* Skype Empresarial servidor local.

Es posible que los clientes tengan usuarios restantes que estén en Skype Empresarial Online y que aún no tengan asignado el modo TeamsOnly. Los clientes deben asignar el modo TeamsOnly a estos usuarios lo antes posible. Microsoft proporcionará actualizaciones asistidos para Skype Empresarial usuarios en línea que no están en modo TeamsOnly. La experiencia de actualización asistida depende de si su organización es una organización en línea pura o una organización con usuarios Skype Empresarial local. Para obtener más información, vea [Actualizaciones asistidos de Skype Empresarial Online a Microsoft Teams](upgrade-assisted.md).

Una vez completada la actualización asistida, todos los usuarios *en* línea estarán en modo TeamsOnly. Los usuarios del modo TeamsOnly reciben chats y llamadas entrantes en Teams y también programan reuniones en Teams. No pueden iniciar chats o llamadas ni programar reuniones en Skype Empresarial Online.  Sin embargo, TeamsOnly los usuarios pueden unirse Skype Empresarial reuniones que ya tienen o reciben en el futuro. Por último, *los usuarios que se aloen localmente* permanecen en el entorno local y no se podrán convertir en TeamsOnly.

## <a name="actions-to-take-before-june-30-2022"></a>Acciones que debe realizar antes del 30 de junio de 2022
Ahora que Skype Empresarial Online está retirado, Microsoft comenzará a retirar la infraestructura de soporte técnico antes del 30 de junio de 2022.  Para cualquier organización con TeamsOnly los usuarios que se actualizaron desde cualquier versión de Skype Empresarial, debe tomar medidas si se aplica alguna de estas situaciones:

- Si tiene usuarios de TeamsOnly que previaulsy tenía contactos en Skype Empresarial y que aún no han  iniciado sesión en Teams desde que se actualizó.
- Si tiene algún usuario de TeamsOnly que todavía Skype Empresarial reuniones en línea que organizaron antes de actualizar a TeamsOnly.

Si alguna de estas situaciones se aplica a su organización, debe tomar medidas antes del 30 de junio de 2022 como se describe a continuación:

 - **Skype Empresarial Contactos** en línea: después de actualizar un usuario al modo TeamsOnly, la primera vez que el usuario inicia sesión en Teams, todos los contactos existentes en la cuenta de Skype Empresarial Online de ese usuario se migrarán a Teams. Después de que Microsoft quite la Skype Empresarial en línea, ya no podrá migrar los contactos de los usuarios que aún no hayan iniciado sesión *en Teams.* Para migrar contactos de Skype Empresarial a Teams, Microsoft recomienda que todos los usuarios que previamente tenían Skype Empresarial inicien sesión en Teams al menos una vez antes del 30 de junio de 2022.

 - **Skype Empresarial reuniones en línea:** después de actualizar una organización a TeamsOnly, los usuarios crean todas las reuniones nuevas como Teams reuniones. En algunos casos, es posible que los usuarios de TeamsOnly todavía Skype Empresarial reuniones en línea que han organizado previamente. Actualmente, los usuarios actualizados de TeamsOnly y los asistentes invitados pueden unirse a estas reuniones Skype Empresarial Online con su Skype Empresarial invitado. Después de que Microsoft quite la infraestructura de Skype Empresarial Online para un determinado usuario de TeamsOnly, sin embargo, las reuniones Skype Empresarial Online restantes organizadas por ese usuario ya no existirán. El organizador y los asistentes no podrán unirse a estas reuniones. Si los usuarios de las organizaciones de TeamsOnly tienen las reuniones Skype Empresarial Online que han organizado, Microsoft recomienda que reprogramen estas reuniones Teams reuniones. Como alternativa, los administradores pueden usar el [servicio de](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms#trigger-meeting-migration-manually-via-powershell-cmdlet) migración de reuniones para convertir estas reuniones en Teams reuniones. En cualquier caso, complete estas acciones antes del 30 de junio de 2022.  


## <a name="how-microsoft-is-helping-customers-upgrade-to-teams"></a>Cómo Microsoft ayuda a los clientes a actualizar a Teams

Le recomendamos encarecidamente que comience la actualización de Skype Empresarial Online a Teams hoy. Aproveche los recursos disponibles para ayudar a planear su Teams y actualizar desde Skype Empresarial:

- [Teams de implementación y actualización](upgrade-start-here.md): guía técnica gratuita para administradores de TI.

- [Teams](./upgrade-workshops-landing-page.yml) talleres de planeación de actualizaciones: talleres interactivos gratuitos de planeación de actualizaciones, donde recibirá instrucciones, procedimientos recomendados y recursos diseñados para ayudarle a planear e implementar la actualización a Teams.

- [Actualizaciones asistidos de Skype Empresarial Online a Microsoft Teams](upgrade-assisted.md): programa automatizado que le ayuda a actualizar Skype Empresarial usuarios en línea a Teams.

- [FastTrack para Microsoft 365](https://www.microsoft.com/fasttrack/microsoft-365): Teams de implementación disponible para los planes que califiquen.

- [Teams en directo](./instructor-led-training-teams-landing-page.yml): clases de aprendizaje en línea gratuitas diseñadas para que su organización esté en marcha con Teams.

- [Teams tiza:](./chalk-talks-landing-page.yml) talleres en línea gratuitos para profesionales de TI y responsables de la toma de decisiones que describen procedimientos recomendados para escenarios clave en Teams.

- [Partners de Microsoft](https://www.microsoft.com/solution-providers/home): los proveedores de soluciones de Microsoft pueden ayudarle a aprovechar al máximo Teams.

- [Microsoft Teams blog](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog): Teams nuevas características, recursos de adopción y uso, Teams dispositivos e integración con otras aplicaciones empresariales.

Si es un cliente actual de Skype Empresarial Online, empiece a planear la actualización a Teams hoy. Estamos encantados de que experimente sus potentes capacidades de comunicación y colaboración, y nos comprometemos a ayudar en el camino.  Para obtener más información sobre la Skype Empresarial en línea, vea Preguntas más frecuentes: Actualizar de [Skype Empresarial a Microsoft Teams](FAQ-journey.yml).





