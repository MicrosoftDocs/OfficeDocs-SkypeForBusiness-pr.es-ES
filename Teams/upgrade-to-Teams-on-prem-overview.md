---
title: 'Actualizar a Teams desde una implementación local de Skype Empresarial: Microsoft Teams'
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Actualización de Skype Empresarial a Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0fe5bb56979b9b4b430076602e76ece595b8661f
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578403"
---
# <a name="upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a>Actualizar de Skype Empresarial a Teams para &mdash; administradores de TI

## <a name="overview"></a>Información general

Al actualizar de Skype Empresarial a Teams, algunas organizaciones requieren una implementación progresiva que sea planeada y administrada por sus departamentos de TI. Los artículos de esta sección se aplican principalmente a los administradores de TI de grandes organizaciones. Normalmente, estas organizaciones son locales, pero también pueden ser grandes organizaciones de Skype Empresarial Online. Antes de leer estos artículos, asegúrese de leer [Introducción a](upgrade-start-here.md) la actualización de Teams y al marco de trabajo de [actualización.](upgrade-framework.md)


En los artículos siguientes se le guiará por el proceso de actualización para su organización: 

- [Métodos de actualización](upgrade-to-teams-on-prem-upgrade-methods.md)
- [Herramientas para administrar la actualización](upgrade-to-teams-on-prem-tools.md)
- [Consideraciones adicionales para las organizaciones con Skype Empresarial local](upgrade-to-teams-on-prem-considerations.md)
- [Implementar la actualización](upgrade-to-teams-on-prem-implement.md)
- [Consideraciones de la red telefónica conmutada (RTC)](upgrade-to-teams-on-prem-pstn-considerations.md)

Además, en los artículos siguientes se describen conceptos importantes de actualización y comportamientos de coexistencia:

- [Coexistencia de Teams y Skype Empresarial](upgrade-to-teams-on-prem-coexistence.md)
- [Modos de coexistencia - Referencia](migration-interop-guidance-for-teams-with-skype.md)
- [Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia](teams-client-experience-and-conformance-to-coexistence-modes.md)

>[!NOTE]
>En estos artículos se usan los términos Skype Empresarial Online, Skype Empresarial Server local y Skype Empresarial. El último término hace referencia a las versiones en línea y local.

Antes de empezar, tenga en cuenta que un usuario que se ha migrado a Teams ya no usa un cliente de Skype Empresarial, excepto para unirse a una reunión hospedada en Skype Empresarial.  Todos los chats y llamadas pasan al cliente de Teams del usuario, independientemente de si el remitente utiliza Teams o Skype Empresarial. Las nuevas reuniones organizadas por el usuario migrado se programarán como reuniones de Teams. Si el usuario intenta usar el cliente de Skype Empresarial, se bloquea el inicio de chats y llamadas.  Sin embargo, el usuario puede (y debe) seguir utilizando el cliente de Skype Empresarial para unirse a las reuniones de Skype Empresarial a las que está invitado. (Los clientes antiguos de Skype Empresarial que se enviaron antes de 2017 no respetan TeamsUpgradePolicy. Asegúrese de que está usando el cliente más reciente de Skype Empresarial).
 
Usted administra la transición de los usuarios a Teams usando el concepto de [modo,](migration-interop-guidance-for-teams-with-skype.md)que es una propiedad de [TeamsUpgradePolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps) Un usuario que se ha migrado a Teams como se describe anteriormente se encuentra en el modo "TeamsOnly".  En el caso de una organización que va a migrar a Teams, el objetivo final es pasar a todos los usuarios al modo TeamsOnly.

>[!NOTE]
>Los usuarios que tienen una cuenta de Skype Empresarial local no pueden ser TeamsOnly. Aunque estos usuarios pueden [usar Teams](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)en modo Islas, esto no proporciona el conjunto completo de funciones de Teams que están disponibles en el modo TeamsOnly. Para que estos usuarios se puedan usar TeamsOnly, deben moverse a la nube con las herramientas locales `Move-CsUser` de Skype Empresarial Server.

De acuerdo. Empecemos.  El primer paso es conocer los [métodos de actualización disponibles.](upgrade-to-teams-on-prem-upgrade-methods.md)







   

## <a name="related-links"></a>Vínculos relacionados

[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](migration-interop-guidance-for-teams-with-skype.md) 

[Configurar la conectividad híbrida entre Skype Empresarial Server y Microsoft 365 u Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover usuarios entre la implementación local y la nube](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configurar su coexistencia y la configuración de actualización](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Usar el servicio de migración de reuniones (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

