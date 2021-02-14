---
title: 'Actualizar a Teams desde una implementación local de Skype Empresarial: Microsoft Teams'
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
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
ms.openlocfilehash: cf034969c2b6ca030eede72ff358a517fafe501f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533597"
---
# <a name="upgrade-considerations-for-organizations-with-skype-for-business-server-on-premises-mdash-for-it-administrators"></a>Consideraciones de actualización para organizaciones con Skype Empresarial Server local &mdash; para administradores de TI

En este artículo se describen consideraciones adicionales para las organizaciones con Skype Empresarial Server local. Este artículo es el cuarto de varios que describen los conceptos de actualización y la implementación para los administradores de TI.  

- [Información general](upgrade-to-teams-on-prem-overview.md)
- [Métodos de actualización](upgrade-to-teams-on-prem-upgrade-methods.md)
- [Herramientas para administrar la actualización](upgrade-to-teams-on-prem-tools.md)
- **Consideraciones adicionales para las organizaciones con Skype Empresarial local** (este artículo)
- [Implementación de la actualización](upgrade-to-teams-on-prem-implement.md)
- [Consideraciones de la red telefónica conmutada (RTC)](upgrade-to-teams-on-prem-pstn-considerations.md)

Además, en los artículos siguientes se describen conceptos importantes de actualización y comportamientos de coexistencia:

- [Coexistencia de Teams y Skype Empresarial](upgrade-to-teams-on-prem-coexistence.md)
- [Modos de coexistencia - Referencia](migration-interop-guidance-for-teams-with-skype.md)
- [Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia](teams-client-experience-and-conformance-to-coexistence-modes.md)



## <a name="considerations-for-organizations-with-skype-for-business-server-on-premises"></a>Consideraciones para las organizaciones con Skype Empresarial Server local

- Configurar la implementación híbrida de Skype Empresarial es un requisito previo para migrar al modo TeamsOnly. Aunque es posible usar Teams en modo de islas sin híbrido, no se puede realizar la transición al modo TeamsOnly hasta que el usuario se mueve de Skype Empresarial local a Skype Empresarial Online (mediante [Move-CsUser).](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) Para obtener más información, vea [Configurar conectividad híbrida.](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity)

- Si su organización tiene Skype Empresarial Server y no ha configurado la conectividad híbrida, pero desea seguir utilizando Teams, para administrar la funcionalidad de Teams, debe usar una cuenta administrativa que tenga un dominio .onmicrosoft.com. 

- Los usuarios de Teams que tienen una cuenta de Skype Empresarial local (es decir, aún no se han movido a la nube mediante Move-CsUser) no pueden interactuar con ningún usuario de Skype Empresarial, ni pueden federar con usuarios externos. Esta funcionalidad solo está disponible una vez que los usuarios se mueven a la nube (ya sea en modo islas o como usuarios de TeamsOnly). 

- Si tiene usuarios con cuentas de Skype Empresarial locales, no puede asignar el modo TeamsOnly en el nivel de inquilino. Primero debe mover todos los usuarios con cuentas locales de Skype Empresarial a la nube y, después, deshabilitar la implementación híbrida para completar la `Move-CsUser` [migración a la nube.](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)  `Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams` no funcionará en el nivel de inquilino si se detecta un registro DNS de lyncdiscover que apunta a una ubicación que no sea Office 365.

- Debe asegurarse de que los usuarios están sincronizados correctamente en Azure AD con los atributos correctos de Skype Empresarial. Estos atributos son todos prefijos con "msRTCSIP-". Si los usuarios no están sincronizados correctamente con Azure AD, las herramientas de administración de Teams no podrán administrarlos. (Por ejemplo, no podrá asignar directivas de Teams a los usuarios locales a menos que sincronice correctamente estos atributos). Para obtener más información, [consulte Configurar Azure AD Connect para Teams y Skype Empresarial.](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect)

- Para crear un nuevo usuario de TeamsOnly o Skype Empresarial Online en una organización híbrida, primero debe habilitar el usuario en Skype Empresarial *Server* local y, a continuación, mover el usuario de local a la nube mediante Move-CsUser.  Al crear el usuario local, primero se garantiza que el resto de usuarios locales de Skype Empresarial puedan enrutar al usuario recién creado. Una vez que todos los usuarios se han movido en línea, ya no es necesario habilitar primero los usuarios locales.

- Cuando se mueve un usuario de un sitio a la nube, las reuniones organizadas por ese usuario se migran a Skype Empresarial Online o Teams, dependiendo de si se especifica el modificador -MoveToTeams.

- Si desea mostrar las notificaciones en el cliente de Skype Empresarial para los usuarios locales, debe usar TeamsUpgradePolicy en el conjunto de herramientas local. Solo el parámetro NotifySfbUsers es relevante para los usuarios locales.  Los usuarios locales reciben su modo de las instancias en línea de TeamsUpgradePolicy. Vea las notas en [Grant-CsTeamsUpgradePolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps) 

>[!NOTE]
> Los nuevos inquilinos creados después del 3 de septiembre de 2019 se crean como inquilinos de TeamsOnly a menos que la organización ya tenga una implementación local de Skype Empresarial Server. Microsoft usa los registros DNS para identificar las organizaciones locales de Skype Empresarial Server. Si su organización tiene Skype Empresarial Server local sin entradas DNS públicas, deberá llamar al soporte técnico de Microsoft para que su nuevo inquilino se haya degradado. 













## <a name="related-links"></a>Vínculos relacionados

[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](migration-interop-guidance-for-teams-with-skype.md) 

[Configurar la conectividad híbrida entre Skype Empresarial Server y Microsoft 365 u Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover usuarios entre la implementación local y la nube](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configurar su coexistencia y la configuración de actualización](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Usar el servicio de migración de reuniones (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

