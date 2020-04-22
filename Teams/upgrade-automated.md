---
title: Actualizaciones automatizadas | Actualización de Skype empresarial a teams
author: serdarsoysal
ms.author: billkau
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: Información general sobre actualizaciones automatizadas de Skype empresarial a equipos
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
# <a name="automated-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>Actualizaciones automáticas de Skype empresarial online a Microsoft Teams

Microsoft ofrece actualizaciones automatizadas para que los equipos ayuden a las pequeñas empresas a tomar la transición correctamente desde Skype empresarial online antes del 31 de julio de 2021 jubilación del servicio. La actualización automática reduce el número de tareas técnicas necesarias para los clientes y permite un mayor enfoque en la preparación de la organización, el conocimiento del usuario y la formación de equipos.

Una actualización correcta de Skype empresarial a Microsoft Teams requiere la planificación de la disponibilidad técnica y del usuario. Cuando esté listo para empezar, Microsoft ofrece un plan de [acción de actualización](upgrade-basic.md) que incluye las actividades principales recomendadas y los recursos asociados para implementar un movimiento exitoso de Skype empresarial a teams.

## <a name="notifications-for-scheduled-customers"></a>Notificaciones para clientes programados

Los clientes de Skype empresarial online aptos para actualizaciones automatizadas de Teams recibirán una serie de notificaciones de actualización que comenzarán 30 días antes de la fecha de actualización programada. Estas notificaciones se entregarán como *plan para* las publicaciones de cambios en el centro de mensajes del administrador, actualizar los correos electrónicos al administrador global y los indicadores de la aplicación a los usuarios finales.

Estas notificaciones comunicarán la fecha programada de la actualización automática, un vínculo a recursos de actualización y formación para ayudar a impulsar la adopción y el uso de Teams, y ofrecerá a los clientes la opción de posponer su actualización automática en 30 días adicionales, ya que no están listos para su actualización por la fecha programada.

## <a name="the-automated-upgrade-experience"></a>La experiencia de actualización automática

Las actualizaciones automáticas se ejecutan en la fecha de actualización programada, que se comunica en las notificaciones de correo electrónico, centro de mensajes y el portal de administración de equipos. La actualización durará aproximadamente 15 minutos, por lo que los usuarios finales seguirán teniendo acceso a la funcionalidad de Skype empresarial online. Una vez que se haya completado la actualización y los usuarios hayan cerrado la sesión de Skype empresarial online, los usuarios solo podrán usar Teams para mensajería, reuniones y llamadas.

## <a name="the-post-upgrade-experience"></a>La experiencia posterior a la actualización

Una vez completada la actualización automática, el **modo de coexistencia** se establece en solo equipos y Microsoft solo puede cambiarse a otro modo de coexistencia. Los administradores deben revisar las [consideraciones del modo solo para equipos](teams-only-mode-considerations.md) antes de la actualización. La tabla siguiente proporciona información general de alto nivel sobre la experiencia de usuario de Teams.


|  |  |
|---------|---------|
|**Conversaciones y llamadas**     | <UL><LI>Todas las llamadas y chats se inician y reciben en Teams<LI>Los usuarios pueden interoperar (chat/llamar) con cualquier usuario de Skype empresarial<LI>Los usuarios no pueden comunicarse con los usuarios que usan Skype para el consumidor<LI>Los usuarios se redirigen a teams si intentan iniciar sesión en Skype empresarial      </UL>  |
|**Reuniones**     |  <UL><LI>Los usuarios programan todas las reuniones nuevas en Teams (complemento reemplazado)    </UL>   |
|**Datos migrados**     |<UL><LI>Los contactos existentes de Skype empresarial, incluidos los federados (pero no las listas de distribución)<LI>Las reuniones de Skype empresarial existentes (locales y en línea) se convierten en reuniones de Teams</UL>         |

## <a name="postponing-your-automated-upgrade"></a>Posponer la actualización automática

Las transiciones exitosas de Skype empresarial online a Microsoft Teams requieren una planificación técnica y la preparación del usuario para garantizar que su organización esté preparada para aprovechar las ventajas de la funcionalidad ampliada y el rendimiento de Teams. Sin embargo, mientras planea la actualización, es posible que su organización aún no esté lista para actualizarse a teams en este momento.

Si recibe una notificación acerca de la actualización automática programada a teams y desea posponerla a una fecha posterior, es posible que el administrador global inicie sesión en el portal de administración de Teams y haga clic en el botón *posponer* . Al hacerlo, la fecha de actualización automática se expondrá 30 días. Cuando actualice el portal de administración de equipos después de posponer, verá una notificación que incluye la nueva fecha de actualización automática.

## <a name="requests-to-downgrade-to-skype-for-business"></a>Solicitudes para cambiar de versión de Skype empresarial

Permitimos la descalificación de una sola vez de Teams a SfBO, para permitir que los inquilinos puedan prepararse aún más para la actualización a teams. Los inquilinos que han degradado se volverán a participar en la actualización automática 60 días desde la fecha de descenso de la suscripción.

## <a name="related-content"></a>Contenido relacionado

- [Introducción a su actualización de Microsoft Teams](upgrade-start-here.md)
- [Retirada de Skype Empresarial Online](skype-for-business-online-retirement.md)
- [Get-CsTeamsUpgradeStatus](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps)
- [Consideraciones del modo Teams solo](teams-only-mode-considerations.md)

