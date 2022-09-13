---
title: Retirada de Skype Empresarial Online
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Obtenga información sobre el plan de retirada de Skype Empresarial Online y cómo Microsoft ayuda a los clientes a migrar a Teams.
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
ms.openlocfilehash: 07d5e443075a80ddad8bda2e490cdd906c3900bf
ms.sourcegitcommit: 9de6b0b03f433e71fe239d292387eed33c11b531
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2022
ms.locfileid: "67657240"
---
# <a name="skype-for-business-online-retirement"></a>Retirada de Skype Empresarial Online

El 31 de julio de 2021, Microsoft retiró Skype Empresarial Online. Esta retirada se anunció en julio de 2019 para dar a los clientes avisos con dos años de antelación para planear sus actualizaciones a Microsoft Teams. Teams es la aplicación principal para la comunicación y la colaboración en Microsoft 365. Con la retirada de Skype Empresarial Online, Microsoft quiere asegurarse de que los clientes tengan la información y los recursos necesarios para planear y ejecutar correctamente la actualización a Teams.  El servicio al consumidor de Skype no se ve afectado por esta retirada. Para obtener información general sobre por qué se retiró Skype Empresarial Online, consulte [Preguntas más frecuentes: actualizar de Skype Empresarial a Microsoft Teams](FAQ-journey.yml).

Microsoft comenzará a retirar la infraestructura de Skype Empresarial Online el 30 de junio de 2022 o después. Este artículo contiene instrucciones para organizaciones con TeamsUsuarios únicos que se actualizaron desde cualquier versión de Skype Empresarial.


## <a name="organizations-with-on-premises-deployments-of-skype-for-business-server"></a>Organizaciones con implementaciones locales de Skype Empresarial Server

La retirada de Skype Empresarial Online no afecta a la compatibilidad con las implementaciones locales de Skype Empresarial Server y Lync Server 2013. Sin embargo, los clientes híbridos con una combinación de usuarios alojados en línea y locales deben actualizar los usuarios *en línea* . Los usuarios en línea deben tener asignado el modo TeamsOnly con TeamsUpgradePolicy. Microsoft proporciona actualizaciones asistidas para ayudar a automatizar la actualización de los usuarios restantes de Skype Empresarial Online al modo TeamsOnly. Las *organizaciones híbridas* no necesitan mover sus usuarios locales Skype Empresarial a la nube como resultado de esta retirada. Microsoft es totalmente compatible con organizaciones híbridas con una combinación de usuarios de TeamsOnly y usuarios locales Skype Empresarial. Los clientes con implementaciones híbridas de Skype Empresarial Server o Lync Server 2013 deben revisar [la retirada de Skype Empresarial Online](/skypeforbusiness/hybrid/plan-hybrid-connectivity#implications-of-the-upcoming-retirement-of-skype-for-business-online).

Al crear nuevos usuarios en su entorno de Active Directory local, si estos usuarios se sincronizarán con Azure AD y su intención es licenciarlos para Teams, *antes de asignar la licencia a estos usuarios*, **primero debe habilitarlos en su implementación local Skype Empresarial y asegurarse de que el cambio se ha sincronizado con la nube a través de Azure AD Connect**.  Puede comprobar que el cambio se ha sincronizado completamente con la nube con Get-CsOnlineUser. El cambio se ha sincronizado si el usuario HostingProvider= "SRV:".  No debe ser "sipfed.online.lync.com".   

## <a name="what-to-expect-post-retirement"></a>Qué se puede esperar después de la jubilación

Ya no es posible asignar un modo distinto de TeamsOnly a los usuarios alojados en la nube. Esto significa que:

 - Al conceder licencias a nuevos usuarios que no se alojan en Skype Empresarial Server locales, se asigna automáticamente a los usuarios el modo TeamsOnly, independientemente de la directiva global del inquilino de TeamsUpgradePolicy.
 - En organizaciones híbridas, al mover usuarios locales a la nube, se asigna automáticamente a los usuarios el modo TeamsOnly independientemente de si el `MoveToTeams` cambio se ha especificado en `Move-CsUser`.
 - A los usuarios alojados en la nube no se les puede asignar un modo distinto de TeamsOnly. Los usuarios alojados en línea *no* usan Skype Empresarial servidor local.

Es posible que los clientes tengan usuarios restantes alojados en Skype Empresarial Online y que aún no tengan asignado el modo TeamsOnly. Los clientes deben asignar el modo TeamsOnly a estos usuarios lo antes posible. Microsoft proporcionará actualizaciones asistidas para los usuarios de Skype Empresarial Online que no estén en el modo TeamsOnly. La experiencia de actualización asistida depende de si su organización es una organización en línea pura o una organización con usuarios Skype Empresarial locales. Para obtener más información, consulte [Actualizaciones asistidas de Skype Empresarial en línea a Microsoft Teams](upgrade-assisted.md). Una vez completada la actualización asistida, todos los usuarios *en línea* estarán en el modo TeamsOnly. *Los usuarios locales permanecen en local y no se convierten en TeamsOnly*.

Los usuarios en El modo Desenlaza reciben llamadas y chats entrantes en Teams y también programan reuniones en Teams. No pueden iniciar chats o llamadas ni programar reuniones en Skype Empresarial En línea. TeamsLos usuarios solo pueden unirse a Skype Empresarial reuniones que ya tengan o reciban en el futuro. Sin embargo, después de que Microsoft quite la infraestructura de Skype Empresarial Online para un usuario determinado de TeamsOnly, los usuarios de TeamsOnly solo pueden unirse a Skype Empresarial reuniones de forma anónima.  A partir del 30 de junio de 2022, los usuarios recién creados de TeamsOnly ya no recibirán el aprovisionamiento de la infraestructura de Skype Empresarial Online, por lo que, si se les invita a una reunión de Skype Empresarial, tendrán que unirse de forma anónima.


## <a name="actions-to-take-before-june-30-2022"></a>Acciones que se realizarán antes del 30 de junio de 2022
Ahora que Skype Empresarial online se ha retirado, Microsoft comenzará a retirar la infraestructura auxiliar no antes del 30 de junio de 2022.  Para cualquier organización con usuarios de TeamsOnly que se actualizaron desde cualquier versión de Skype Empresarial, debe realizar una acción si se aplica alguna de estas situaciones:

- Si tiene usuarios de TeamsOnly usuarios que antes tenían contactos en Skype Empresarial *y* que aún no han iniciado sesión en Teams desde que se actualizó.
- Si tiene usuarios de TeamsOnly que todavía tienen Skype Empresarial reuniones en línea que han organizado antes de actualizarse a TeamsOnly.

Si cualquiera de estas situaciones se aplica a su organización, debe realizar una acción antes del 30 de junio de 2022 como se describe a continuación:

 - **Skype Empresarial contactos en línea:** después de actualizar un usuario al modo TeamsOnly, la primera vez que el usuario inicie sesión en Teams, todos los contactos existentes en la cuenta de Skype Empresarial Online de ese usuario se migrarán a Teams. Después de que Microsoft quite la infraestructura de Skype Empresarial Online, ya no podrá migrar los contactos *de los usuarios que aún no hayan iniciado sesión en Teams.* Para migrar contactos de Skype Empresarial a Teams, Microsoft recomienda que todos los usuarios que anteriormente tenían Skype Empresarial inicien sesión en Teams al menos una vez antes del 30 de junio de 2022.

 - **Skype Empresarial reuniones en línea:** después de actualizar una organización a TeamsOnly, los usuarios crean todas las reuniones nuevas como reuniones de Teams. En algunos casos, es posible que los usuarios de TeamsOnly todavía tengan reuniones de Skype Empresarial Online que hayan organizado anteriormente. Actualmente, los usuarios actualizados de TeamsOnly y los asistentes invitados pueden unirse a estas reuniones de Skype Empresarial Online con su cliente de Skype Empresarial. Sin embargo, después de que Microsoft quite la infraestructura de Skype Empresarial Online para un usuario determinado de TeamsOnly, ese usuario solo podrá unirse a reuniones de Skype Empresarial de forma anónima y las reuniones Skype Empresarial Online *que organice dicho usuario* ya no existirán. El organizador y los asistentes no podrán unirse a estas reuniones. Si los usuarios de TeamsOnly organizaciones tienen reuniones Skype Empresarial online restantes que han organizado, Microsoft recomienda que reprogramen estas reuniones como reuniones de Teams. Como alternativa, los administradores pueden usar el [Servicio de migración](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms#trigger-meeting-migration-manually-via-powershell-cmdlet) de reuniones para convertir estas reuniones en reuniones de Teams. En cualquier caso, complete estas acciones antes del 30 de junio de 2022.  


## <a name="how-microsoft-is-helping-customers-upgrade-to-teams"></a>Cómo ayuda Microsoft a los clientes a actualizar a Teams

Le recomendamos encarecidamente que empiece la actualización de Skype Empresarial En línea a Teams hoy mismo. Aproveche los recursos disponibles para ayudar a planear la implementación de Teams y actualizar desde Skype Empresarial:

- [Documentación de implementación y actualización de Teams](upgrade-start-here.md) : guía técnica gratuita para administradores de TI.

- [Talleres de planificación de actualizaciones de Teams: talleres interactivos](./upgrade-workshops-landing-page.yml) gratuitos de planificación de actualizaciones, donde recibirá orientación, procedimientos recomendados y recursos diseñados para ayudarle a planear e implementar la actualización a Teams.

- [Actualizaciones asistidas de Skype Empresarial Online a Microsoft Teams](upgrade-assisted.md): programa automatizado que le ayuda a actualizar Skype Empresarial usuarios en línea a Teams.

- [FastTrack para Microsoft 365](https://www.microsoft.com/fasttrack/microsoft-365) : asistencia de implementación de Teams disponible para planes válidos.

- [Aprendizaje en directo de Teams](./instructor-led-training-teams-landing-page.yml) : clases de aprendizaje en línea gratuitas diseñadas para poner en marcha su organización con Teams.

- [Teams Chalk Talks](./chalk-talks-landing-page.yml) : talleres en línea gratuitos para profesionales de TI y responsables de la toma de decisiones que describen las mejores prácticas para escenarios clave en Teams.

- [Partners de Microsoft](https://www.microsoft.com/solution-providers/home) : los proveedores de soluciones de Microsoft pueden ayudarle a aprovechar al máximo Teams.

- [Blog de Microsoft Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog) : noticias de Teams sobre nuevas características, recursos de adopción y uso, dispositivos de Teams e integración con otras aplicaciones empresariales.

Si es un cliente actual de Skype Empresarial Online, empiece a planear la actualización a Teams hoy mismo. Estamos encantados de que experimentes sus potentes capacidades de comunicación y colaboración, y nos comprometemos a ayudarte en el proceso.  Para obtener más información sobre la retirada de Skype Empresarial Online, vea [Preguntas más frecuentes: actualizar de Skype Empresarial a Microsoft Teams](FAQ-journey.yml).





