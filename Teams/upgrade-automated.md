---
title: Actualizaciones automatizadas| Actualización de Skype Empresarial a Teams
author: serdarsoysal
ms.author: billkau
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: Información general sobre las actualizaciones automatizadas de Skype Empresarial a Teams
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
ms.openlocfilehash: cb3fef455e4031c61b6769e114d9cbd1d8bd3805
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120551"
---
# <a name="automated-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>Actualizaciones automatizadas de Skype Empresarial Online a Microsoft Teams

Microsoft ofrece actualizaciones automatizadas a Teams para ayudar a pequeñas empresas a realizar la transición correcta desde Skype Empresarial Online antes de la retirada del servicio del 31 de julio de 2021. La actualización automatizada reduce el número de tareas técnicas necesarias para los clientes y permite centrarse más en la preparación de la organización, el conocimiento de los usuarios y el aprendizaje de Teams.

Una actualización correcta de Skype Empresarial a Microsoft Teams requiere la planificación de la preparación técnica y del usuario. Cuando esté listo para empezar, Microsoft ofrece un [plan](upgrade-basic.md) de acción de actualización con actividades recomendadas principales y recursos asociados para implementar un movimiento exitoso de Skype Empresarial a Teams.

## <a name="notifications-for-scheduled-customers"></a>Notificaciones para clientes programados

Los clientes de Skype Empresarial Online aptos para las actualizaciones automatizadas de Teams recibirán una serie de notificaciones de actualización a partir de 30 días antes de la fecha de actualización programada. Estas notificaciones se entregarán como publicaciones de *Plan de* cambio en el Centro de mensajes de administración, actualizar correos electrónicos al administrador global y marcas desde la aplicación a los usuarios finales.

Estas notificaciones comunicarán la fecha programada de la actualización automatizada, se vincularán a recursos de actualización y aprendizaje para ayudar a impulsar la adopción y el uso de Teams, y ofrecerán a los clientes la opción de posponer la actualización automatizada 30 días adicionales en caso de que no estén listos para actualizar en la fecha programada.

## <a name="the-automated-upgrade-experience"></a>La experiencia de actualización automatizada

Las actualizaciones automatizadas se ejecutan en la fecha de actualización programada que se comunica en los correos electrónicos de notificación, el Centro de mensajes, así como en el portal de administración de Teams. La actualización llevará aproximadamente 15 minutos durante los cuales los usuarios finales seguirán teniendo acceso a la funcionalidad de Skype Empresarial Online. Una vez completada la actualización y los usuarios cierran sesión en Skype Empresarial Online, los usuarios solo podrán usar Teams para mensajería, reuniones y llamadas.

## <a name="the-post-upgrade-experience"></a>La experiencia posterior a la actualización

Cuando se complete la  actualización automatizada, el modo coexistencia se establece en Solo Teams y Solo Microsoft puede cambiar a otro modo de coexistencia. Los administradores deben revisar [las consideraciones del modo Solo teams](teams-only-mode-considerations.md) antes de la actualización. La tabla siguiente proporciona una descripción general de alto nivel de la experiencia de usuario solo de Teams.


|  |  |
|---------|---------|
|**Chat y llamadas**     | <UL><LI>Todas las llamadas y chats se inician y se reciben en Teams<LI>Los usuarios pueden interoperar (chat o llamada) con cualquier usuario de Skype Empresarial<LI>Los usuarios no pueden comunicarse con los usuarios que usan Skype para consumidores<LI>Los usuarios se redirigen a Teams si intentan iniciar sesión en Skype Empresarial      </UL>  |
|**Reuniones**     |  <UL><LI>Los usuarios programan todas las reuniones nuevas en Teams (complemento reemplazado)    </UL>   |
|**Datos migrados**     |<UL><LI>Contactos existentes de Skype Empresarial, incluidos federados (pero sin listas de distribución)<LI>Las reuniones existentes de Skype Empresarial (tanto locales como en línea) se convierten en reuniones de Teams</UL>         |

## <a name="postponing-your-automated-upgrade"></a>Posponer la actualización automatizada

Las transiciones correctas de Skype Empresarial Online a Microsoft Teams requieren planificación técnica y preparación del usuario para asegurarse de que su organización está preparada para aprovechar la funcionalidad y el rendimiento expandido de Teams. Sin embargo, a medida que planee la actualización, es posible que encuentre que su organización aún no está lista para actualizar a Teams en este momento.

Si recibe una notificación sobre la actualización automatizada programada a Teams y desea posponerla a una fecha posterior, el administrador global puede iniciar sesión en el portal de administración de Teams y hacer clic en el botón *Posponer.* Al hacerlo, se mostrará la fecha de actualización automatizada de 30 días. Al actualizar el portal de administración de Teams después de posponer, verá una notificación que incluye la nueva fecha de actualización automatizada.

## <a name="requests-to-downgrade-to-skype-for-business"></a>Solicitudes para cambiar a Skype Empresarial

Permitimos las degradaciones de una sola vez de Teams a SfBO, para permitir que los inquilinos se preparen aún más para su actualización a Teams. Los inquilinos que se han degradado se volverán a comprometer para la actualización automatizada 60 días a partir de su fecha de degradación.

## <a name="related-content"></a>Contenido relacionado

- [Introducción a su actualización de Microsoft Teams](upgrade-start-here.md)
- [Retirada de Skype Empresarial Online](skype-for-business-online-retirement.md)
- [Get-CsTeamsUpgradeStatus](/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps)
- [Consideraciones del modo Teams solo](teams-only-mode-considerations.md)