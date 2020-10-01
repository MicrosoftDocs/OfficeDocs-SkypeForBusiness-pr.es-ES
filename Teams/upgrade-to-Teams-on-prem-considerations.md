---
title: Actualizar a teams desde una implementación local de Skype empresarial-Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/20
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
ms.openlocfilehash: 8c359b39707b57a653f35e75497672d306209ccd
ms.sourcegitcommit: 739ffd5893abf6d181877d1110f9dc8230b3bfd2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328219"
---
# <a name="upgrade-considerations-for-organizations-with-skype-for-business-server-on-premises-mdash-for-it-administrators"></a>Consideraciones de actualización para organizaciones con Skype empresarial Server local &mdash; para administradores de ti

En este artículo se describen algunas consideraciones adicionales para las organizaciones con Skype empresarial Server local. Este artículo es el cuarto de varios que describen los conceptos de actualización y la implementación para administradores de ti.  

- [Información general](upgrade-to-teams-on-prem-overview.md)
- [Métodos de actualización](upgrade-to-teams-on-prem-upgrade-methods.md)
- [Herramientas para administrar la actualización](upgrade-to-teams-on-prem-tools.md)
- **Consideraciones adicionales para las organizaciones con Skype empresarial local** (este artículo)
- [Implementación de la actualización](upgrade-to-teams-on-prem-implement.md)
- [Consideraciones sobre la red telefónica pública conmutada (RTC)](upgrade-to-teams-on-prem-pstn-considerations.md)

Además, los artículos siguientes describen los conceptos de actualización importantes y los comportamientos de coexistencia:

- [Coexistencia de Teams y Skype empresarial](upgrade-to-teams-on-prem-coexistence.md)
- [Modos de coexistencia: referencia](migration-interop-guidance-for-teams-with-skype.md)
- [Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia](teams-client-experience-and-conformance-to-coexistence-modes.md)



## <a name="considerations-for-organizations-with-skype-for-business-server-on-premises"></a>Consideraciones para las organizaciones con Skype empresarial Server local

- La configuración del entorno híbrido de Skype empresarial es un requisito previo para migrar al modo TeamsOnly. Aunque es posible usar equipos en el modo islas sin entornos híbridos, no se puede realizar la transición al modo TeamsOnly hasta que el usuario pase de Skype empresarial local a Skype empresarial online (mediante [Move-CsUser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)). Para obtener más información, vea [configurar la conectividad híbrida](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity).

- Si su organización tiene Skype empresarial Server y no ha configurado la conectividad híbrida, pero aún desea usar Teams para administrar la funcionalidad de Teams, debe usar una cuenta administrativa que tenga un dominio. onmicrosoft.com. 

- Los usuarios de equipos que tienen una cuenta de Skype empresarial local (es decir, que aún no se han movido a la nube mediante Move-CsUser) no pueden interoperar con ningún usuario de Skype empresarial ni pueden federarse a usuarios externos. Esta función solo está disponible cuando los usuarios se mueven a la nube (ya sea en modo islas o como usuarios de TeamsOnly). 

- Si tiene usuarios con cuentas de Skype empresarial en local, no puede asignar el modo TeamsOnly en el nivel de espacio empresarial. Primero debe mover a la nube todos los usuarios que tengan cuentas locales de Skype empresarial `Move-CsUser` y, a continuación, [deshabilitar la implementación híbrida para completar la migración a la nube](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid).  `Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams` no funcionará en el nivel de inquilino si se detecta un registro DNS lyncdiscover que señala a una ubicación distinta de Office 365.

- Debe asegurarse de que los usuarios estén sincronizados correctamente en Azure AD con los atributos correctos de Skype empresarial. Estos atributos son todos los prefijos con "msRTCSIP-". Si los usuarios no se sincronizan correctamente con Azure AD, las herramientas de administración de Teams no podrán administrar estos usuarios. (Por ejemplo, no podrá asignar directivas de Teams a usuarios locales, a menos que esté sincronizando estos atributos correctamente). Para obtener más información, vea [configurar Azure ad Connect para Teams y Skype empresarial](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect).

- Para crear un nuevo usuario de TeamsOnly o de Skype empresarial online en una organización híbrida, *primero debe habilitar el usuario en Skype empresarial Server local*y, después, mover el usuario de local a la nube con Move-CsUser.  La creación del usuario en local primero garantiza que todos los demás usuarios locales de Skype empresarial podrán enrutar al usuario recién creado. Una vez que todos los usuarios se han movido a Internet, ya no es necesario que habilite primero los usuarios en local.

- Cuando un usuario se mueve de local a la nube, las reuniones organizadas por ese usuario se migran a Skype empresarial online o Teams, en función de si se especifica o no el modificador-MoveToTeams.

- Si desea mostrar las notificaciones en el cliente de Skype empresarial para los usuarios locales, debe usar TeamsUpgradePolicy en el conjunto de herramientas local. Solo el parámetro NotifySfbUsers es relevante para los usuarios locales.  Los usuarios locales obtienen su modo de las instancias en línea de TeamsUpgradePolicy. Consulte las notas en [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps). 

>[!NOTE]
> Los nuevos inquilinos creados después del 3 de septiembre de 2019 se crean como inquilinos de TeamsOnly, a menos que la organización ya tenga una implementación local de Skype empresarial Server. Microsoft usa los registros DNS para identificar las organizaciones locales de Skype empresarial Server. Si su organización tiene Skype empresarial Server local sin entradas DNS públicas, tendrá que llamar al servicio de soporte técnico de Microsoft para descalificar el nuevo inquilino. 













## <a name="related-links"></a>Vínculos relacionados

[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](migration-interop-guidance-for-teams-with-skype.md) 

[Configurar la conectividad híbrida entre Skype empresarial Server y Microsoft 365 u Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover usuarios entre la implementación local y la nube](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configurar su coexistencia y la configuración de actualización](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Usar el servicio de migración de reuniones (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

