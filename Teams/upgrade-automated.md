---
title: Actualizaciones automatizadas| Actualización de Skype Empresarial a Teams
author: serdarsoysal
ms.author: billkau
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: Información general sobre actualizaciones automatizadas de Skype Empresarial a Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b42785d4f8d765e7d9600c2e195e48d7ec60d8ba
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780659"
---
# <a name="automated-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>Actualizaciones automatizadas de Skype Empresarial Online a Microsoft Teams

Microsoft ofrece actualizaciones automatizadas de Teams para ayudar a las pequeñas empresas a realizar la transición correcta de Skype Empresarial Online antes de la retirada del servicio del 31 de julio de 2021. La actualización automatizada reduce el número de tareas técnicas necesarias para los clientes y permite centrarse más en la preparación organizativa, el conocimiento del usuario y la formación de Teams.

Una actualización correcta de Skype Empresarial a Microsoft Teams requiere un planeamiento de la preparación técnica y del usuario. Cuando esté listo para empezar, Microsoft ofrece un [plan](upgrade-basic.md) de acción de actualización que incluye las principales actividades recomendadas y recursos asociados para implementar un cambio exitoso de Skype Empresarial a Teams.

## <a name="notifications-for-scheduled-customers"></a>Notificaciones para clientes programados

Los clientes de Skype Empresarial Online aptos para actualizaciones automatizadas en Teams recibirán una serie de notificaciones de actualización que comienzan 30 días antes de su fecha de actualización programada. Estas notificaciones se entregarán como publicaciones de *Plan* para cambios en el Centro de mensajes de administración, actualizar correos electrónicos al administrador global y marcas desde la aplicación a los usuarios finales.

Estas notificaciones comunicarán la fecha programada de la actualización automatizada, se vincularán a recursos de actualización y formación para impulsar la adopción y el uso de Teams y ofrecerán a los clientes la opción de posponer la actualización automatizada 30 días adicionales en caso de que no estén listos para la actualización en su fecha programada.

## <a name="the-automated-upgrade-experience"></a>La experiencia de actualización automatizada

Las actualizaciones automatizadas se ejecutan en la fecha de actualización programada que se comunica en los correos electrónicos de notificación, el Centro de mensajes, así como en el Portal de administración de Teams. La actualización llevará aproximadamente 15 minutos, mientras que los usuarios finales seguirán teniendo acceso a la funcionalidad de Skype Empresarial Online. Una vez completada la actualización y el cierre de sesión de los usuarios de Skype Empresarial Online, los usuarios solo podrán usar Teams para mensajería, reuniones y llamadas.

## <a name="the-post-upgrade-experience"></a>La experiencia posterior a la actualización

Cuando se completa la  actualización automatizada, Microsoft establece el modo de coexistencia en Solo equipos y Microsoft solo puede cambiar a un modo de coexistencia diferente. Los administradores deben [revisar las consideraciones del modo Teams solo](teams-only-mode-considerations.md) antes de actualizar. La tabla siguiente proporciona información general de alto nivel sobre la experiencia del usuario solo de Teams.


|  |  |
|---------|---------|
|**Chat y llamadas**     | <UL><LI>Todas las llamadas y chats se inician y se reciben en Teams<LI>Los usuarios pueden interoperar (chat/llamada) con cualquier usuario de Skype Empresarial<LI>Los usuarios no pueden comunicarse con los usuarios que usan Skype para consumidores<LI>Los usuarios se redirigen a Teams si intentan iniciar sesión en Skype Empresarial.      </UL>  |
|**Reuniones**     |  <UL><LI>Los usuarios programan todas las reuniones nuevas en Teams (se reemplaza el complemento)    </UL>   |
|**Datos migrados**     |<UL><LI>Contactos existentes de Skype Empresarial, incluidos federados (pero sin listas de distribución)<LI>Las reuniones existentes de Skype Empresarial (locales y en línea) se convierten en reuniones de Teams</UL>         |

## <a name="postponing-your-automated-upgrade"></a>Posponer la actualización automatizada

Las transiciones correctas de Skype Empresarial Online a Microsoft Teams requieren planificación técnica y preparación del usuario para asegurarse de que su organización está preparada para aprovechar las ventajas de la funcionalidad ampliada y el rendimiento de Teams. Sin embargo, a medida que planea la actualización, es posible que su organización aún no esté lista para actualizar a Teams en este momento.

Si recibe una notificación sobre la actualización automatizada programada para Teams y desea posponerla a una fecha posterior, el administrador global puede iniciar sesión en el portal de administración de Teams y hacer clic en el botón *Posponer.* Si lo hace, se actualizará la fecha de actualización automatizada 30 días. Al actualizar el Portal de administración de Teams después de posponer, verá una notificación que incluye la nueva fecha de actualización automatizada.

## <a name="requests-to-downgrade-to-skype-for-business"></a>Solicitudes para cambiar a una versión anterior a Skype Empresarial

Permitimos que los inquilinos puedan cambiar a una versión anterior de Teams a SfBO para que los inquilinos puedan prepararse aún más para su actualización a Teams. Los inquilinos que se han degradado se volverán a comprometer para la actualización automatizada 60 días a partir de su fecha de cambio a una versión anterior.

## <a name="related-content"></a>Contenido relacionado

- [Introducción a su actualización de Microsoft Teams](upgrade-start-here.md)
- [Retirada de Skype Empresarial Online](skype-for-business-online-retirement.md)
- [Get-CsTeamsUpgradeStatus](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps)
- [Consideraciones del modo Teams solo](teams-only-mode-considerations.md)

