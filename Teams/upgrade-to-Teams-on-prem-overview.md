---
title: Actualizar a teams desde una implementación local de Skype empresarial-Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/22/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Actualización de Skype Empresarial a Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: aa87941300f87abb320ddad7e8bc1311c62addf0
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940580"
---
# <a name="upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a>Actualizar de Skype empresarial a teams &mdash; para administradores de ti

## <a name="overview"></a>Información general

Al actualizar de Skype empresarial a Teams, algunas organizaciones necesitan un lanzamiento progresivo planificado y administrado por sus departamentos de ti. Los artículos de esta sección se aplican principalmente a los administradores de TI de organizaciones grandes. Estas organizaciones suelen ser locales, pero también pueden ser grandes organizaciones de Skype empresarial online. Antes de leer estos artículos, Lea Introducción a [la actualización de equipos](upgrade-start-here.md) y [acerca del marco de actualización](upgrade-framework.md).


Los siguientes artículos le guiarán a través del proceso de actualización de su organización: 

- [Métodos de actualización](upgrade-to-teams-on-prem-upgrade-methods.md)
- [Herramientas para administrar la actualización](upgrade-to-teams-on-prem-tools.md)
- [Consideraciones adicionales para las organizaciones con Skype empresarial local](upgrade-to-teams-on-prem-considerations.md)
- [Implementar la actualización](upgrade-to-teams-on-prem-implement.md)
- [Consideraciones sobre la red telefónica pública conmutada (RTC)](upgrade-to-teams-on-prem-pstn-considerations.md)

Además, los artículos siguientes describen los conceptos de actualización importantes y los comportamientos de coexistencia:

- [Coexistencia de Teams y Skype empresarial](upgrade-to-teams-on-prem-coexistence.md)
- [Modos de coexistencia: referencia](migration-interop-guidance-for-teams-with-skype.md)
- [Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia](teams-client-experience-and-conformance-to-coexistence-modes.md)

>[!NOTE]
>En estos artículos se usan los términos Skype empresarial online, Skype empresarial Server local y Skype empresarial. El último término se refiere a versiones locales y en línea.

Antes de empezar, tenga en cuenta que un usuario que se ha migrado a teams ya no usa un cliente de Skype empresarial, excepto para unirse a una reunión hospedada en Skype empresarial.  Todos los chats y llamadas pasan al cliente de Teams del usuario, independientemente de si el remitente utiliza Teams o Skype Empresarial. Todas las reuniones nuevas organizadas por el usuario migrado se programarán como reuniones de Teams. Si el usuario intenta usar el cliente de Skype empresarial, la iniciación de chats y llamadas estará bloqueada.  Sin embargo, el usuario puede (y debe) seguir usando el cliente de Skype empresarial para unirse a las reuniones de Skype empresarial a las que está invitado. (Los antiguos clientes de Skype empresarial que se entregaron antes 2017 no son compatibles con TeamsUpgradePolicy. Asegúrese de estar usando el último cliente de Skype empresarial.)
 
Puede administrar la transición de su usuario a teams mediante el concepto de [modo](migration-interop-guidance-for-teams-with-skype.md), que es una propiedad de [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps). Un usuario que se ha migrado a Teams, como se describe anteriormente, está en modo "TeamsOnly".  En el caso de una organización que va a migrar a Teams, el objetivo final es pasar a todos los usuarios al modo TeamsOnly.

Vale. Comencemos.  El primer paso es comprender los [métodos de actualización disponibles](upgrade-to-teams-on-prem-upgrade-methods.md).







   

## <a name="related-links"></a>Vínculos relacionados

[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](migration-interop-guidance-for-teams-with-skype.md) 

[Configurar la conectividad híbrida entre Skype empresarial Server y Microsoft 365 u Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover usuarios entre la implementación local y la nube](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configurar su coexistencia y la configuración de actualización](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Usar el servicio de migración de reuniones (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

