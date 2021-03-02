---
title: Actualizar Skype Empresarial local a Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Obtenga información sobre cómo actualizar su organización a Microsoft Teams desde una implementación local de Skype Empresarial.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7bd7d2fad4e4c35a26bcbb435caba5898dd54534
ms.sourcegitcommit: 79b19b326ef40bf04af03021a7c6506fdd9417ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2021
ms.locfileid: "50397555"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a>Actualizar de Skype Empresarial local a Teams

![Diagrama de viaje de actualización, haciendo hincapié en la implementación y la implementación](media/upgrade-banner-deployment.png "Fases del viaje de actualización, con énfasis en la fase implementación e implementación")

Este artículo forma parte de la fase de implementación e implementación del viaje de actualización. Antes de continuar, confirme que ha completado las siguientes actividades:

-   [Ha incorporado a las partes interesadas del proyecto](upgrade-enlist-stakeholders.md)
-   [Ha definido el ámbito del proyecto](https://aka.ms/SkypetoTeams-Scope)
-   [Ha comprendido la coexistencia y la interoperabilidad de Skype Empresarial y Teams](https://aka.ms/SkypeToTeams-Coexist)
-   [Elegido el viaje de actualización](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [Preparado el entorno](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [Preparar la organización](https://aka.ms/SkypeToTeams-UserReadiness)
-   [Llevó a cabo un piloto](https://aka.ms/SkypeToTeams-Pilot)

Si ha implementado Skype Empresarial Server o Microsoft Lync local y su organización quiere actualizar a Teams, siga las instrucciones de este artículo. Debe configurar la conectividad híbrida con su organización de Microsoft 365 u Office 365 y determinar los requisitos de coexistencia si va a mover los usuarios a Teams por fases.

Antes de empezar, los profesionales de TI y los administradores deben revisar las consideraciones importantes para las organizaciones con [Skype Empresarial Server local](#important-considerations-for-organizations-with-skype-for-business-server-on-premises) más adelante en este artículo.

> [!IMPORTANT]
> Skype Empresarial Online se retirará el 31 de julio de 2021, momento a partir del cual ya no será posible obtener acceso a este soporte. Para aprovechar al máximo las ventajas y asegurarse de que su organización dispone del tiempo adecuado para implementar la actualización, le recomendamos que comience ahora su viaje hacia Microsoft Teams. Recuerde que una actualización correcta alinea la preparación técnica y del usuario, por lo que asegúrese de aprovechar las instrucciones aquí a medida que se desplaza a Microsoft Teams.

## <a name="step-1-configure-hybrid-connectivity"></a>Paso 1: Configurar la conectividad híbrida 

El requisito previo clave para actualizar los usuarios locales a Teams es configurar la conectividad híbrida para su implementación local de Skype Empresarial Server. 

Empiece leyendo [Planear conectividad híbrida](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) y, a continuación, siga las tareas descritas en Configurar conectividad [híbrida.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)


## <a name="step-2-set-transitional-coexistence-mode-optional"></a>Paso 2: Establecer el modo de coexistencia de transición (opcional)

Los modos de actualización de Teams definen la coexistencia y la interoperabilidad entre clientes y usuarios de Skype Empresarial y Teams.  De forma predeterminada, las organizaciones están en modo Islas, lo que permite a los usuarios usar los clientes de Teams y Skype Empresarial en paralelo.

Para una organización que se mueve a Teams, el modo TeamsOnly es el destino final para cada usuario, aunque no todos los usuarios deben tener asignado TeamsOnly (o cualquier otro modo) al mismo tiempo.

Antes de que los usuarios lleguen al modo TeamsOnly, las organizaciones pueden usar opcionalmente cualquiera de los modos de coexistencia de Skype Empresarial para garantizar una comunicación predecible entre los usuarios que están en modo TeamsOnly y los usuarios que aún no lo están.  El propósito de los modos de coexistencia de Skype Empresarial (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) es proporcionar una experiencia sencilla y predecible para los usuarios finales a medida que las organizaciones transición de Skype Empresarial a Teams. 

Cuando un usuario está en cualquiera de los modos de Skype Empresarial, todos los chats y llamadas entrantes se enruta al cliente de Skype Empresarial del usuario. Para evitar confusiones entre los usuarios finales y garantizar el enrutamiento adecuado, las llamadas y las funciones de chat en el cliente de Teams se deshabilitan cuando un usuario está en cualquiera de los modos de Skype Empresarial. De forma similar, la programación de reuniones en Teams se deshabilita explícitamente cuando los usuarios están en los modos SfBOnly o SfBWithTeamsCollab y se habilita explícitamente cuando un usuario está en el modo SfBWithTeamsCollabAndMeetings.

Según sus requisitos, puede asignar el modo de coexistencia adecuado en función de la ruta de actualización que haya elegido su organización. Para obtener más información, vea Instrucciones de migración e interoperabilidad para organizaciones que usan Teams junto con [Skype Empresarial](migration-interop-guidance-for-teams-with-skype.md) y Establecer la configuración de [coexistencia y actualización.](https://aka.ms/SkypeToTeams-SetCoexistence)


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>Paso 3: Mover usuarios de Skype Empresarial local a Teams Only

En última instancia, querrá mover los usuarios al modo TeamsOnly. Esto puede implicar uno o dos pasos dependiendo de su entorno local.  

Para obtener más información, vea [Mover usuarios](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) entre locales y la nube y Mover usuarios de local [a Teams.](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) 

## <a name="step-4-disable-hybrid-to-complete-your-migration-to-the-cloud"></a>Paso 4: Deshabilitar la implementación híbrida para completar la migración a la nube

Después de mover todos los usuarios de local a la nube, puede retirar la implementación local de Skype Empresarial. Para obtener más información, vea [Deshabilitar la implementación híbrida para completar la migración a la nube.](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)


## <a name="phone-system-and-pstn-connectivity-options"></a>Opciones de conectividad del sistema telefónico y RTC

Sistema telefónico con Teams es compatible después de que el usuario esté en modo TeamsOnly. (Si el usuario está en modo Islas, El sistema telefónico solo es compatible con Skype Empresarial). 

### <a name="pstn-connectivity-options"></a>Opciones de conectividad RTC

Al considerar las opciones de conectividad de red telefónica conmutada (RTC), hay dos escenarios posibles al pasar de Skype Empresarial local al modo TeamsOnly:

- Un usuario de Skype Empresarial local con Telefonía IP empresarial, que se trasladará a internet y usará un plan de Llamadas de Microsoft. Migrar este usuario a Teams requiere mover la cuenta local de Skype Empresarial a la nube y coordinar ese movimiento con cualquiera de los dos A) el puerto del número de teléfono de ese usuario a un plan de llamadas de Microsoft o B) asignando un nuevo número de suscriptor de las regiones disponibles.  Para obtener más información, vea Desde Skype Empresarial Server local, con [Telefonía IP empresarial, a Microsoft Calling Plan.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)

- Un usuario de Skype Empresarial local con Telefonía IP empresarial, que se trasladará a internet y mantendrá la conectividad RTC local. Migrar este usuario a Teams requiere mover la cuenta local de Skype Empresarial a la nube y coordinar ese movimiento con la migración del usuario a Enrutamiento directo. Para obtener más información, vea Desde Skype Empresarial Server local, con [Telefonía IP empresarial, a Enrutamiento directo.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)


## <a name="important-considerations-for-organizations-with-skype-for-business-server-on-premises"></a>Consideraciones importantes para las organizaciones con Skype Empresarial Server local

- En los artículos siguientes se describen conceptos de actualización importantes y comportamientos de coexistencia:
    - [Coexistencia de Teams y Skype Empresarial](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
    - [Modos de coexistencia: referencia](migration-interop-guidance-for-teams-with-skype.md)
    - [Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia](teams-client-experience-and-conformance-to-coexistence-modes.md)

- Configurar skype empresarial híbrido es un requisito previo para migrar al modo TeamsOnly. Aunque es posible usar Teams en modo islas sin híbrido, la transición al modo TeamsOnly no se puede realizar hasta que el usuario se mueva de Skype Empresarial local a Skype Empresarial Online (con [Move-CsUser).](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) Para obtener más información, vea [Configurar la conectividad híbrida.](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity)

- Si su organización tiene Skype Empresarial Server y no ha configurado la conectividad híbrida, pero todavía desea usar Teams, para administrar la funcionalidad de Teams, debe usar una cuenta administrativa que tenga un dominio .onmicrosoft.com. 

- Los usuarios de Teams que tienen una cuenta de Skype Empresarial local (es decir, aún no se han movido a la nube mediante Move-CsUser) no pueden interoperar con ningún usuario de Skype Empresarial ni pueden federar con usuarios externos. Esta funcionalidad solo está disponible una vez que los usuarios se mueven a la nube (ya sea en modo Islas o como usuarios de TeamsOnly). 

- Si tiene usuarios con cuentas de Skype Empresarial locales, no puede asignar el modo TeamsOnly en el nivel de inquilino. Primero debe mover todos los usuarios con cuentas locales de Skype Empresarial a la nube y, a continuación, deshabilitar la implementación híbrida para completar la migración `Move-CsUser` [a la nube.](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)  `Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams` no funcionará en el nivel de inquilino si se detecta un registro DNS de detección de lync que apunta a una ubicación que no sea Office 365.

- Debe asegurarse de que los usuarios estén sincronizados correctamente en Azure AD con los atributos correctos de Skype Empresarial. Estos atributos son todos prefijos con "msRTCSIP-". Si los usuarios no están sincronizados correctamente con Azure AD, las herramientas de administración de Teams no podrán administrar estos usuarios. (Por ejemplo, no podrá asignar directivas de Teams a usuarios locales a menos que sincronice correctamente estos atributos). Para obtener más información, vea [Configurar Azure AD Connect para Teams y Skype Empresarial.](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect)

- Para crear un nuevo usuario de TeamsOnly o Skype Empresarial Online en una organización híbrida, primero debe habilitar el usuario en *Skype Empresarial Server* local y, a continuación, mover el usuario de local a la nube con Move-CsUser.  La creación del usuario local garantiza primero que cualquier otro usuario local de Skype Empresarial pueda dirigirse al usuario recién creado. Una vez que todos los usuarios se han movido en línea, ya no es necesario habilitar primero a los usuarios en el entorno local.

- Cuando un usuario se mueve de local a la nube, las reuniones organizadas por ese usuario se migran a Skype Empresarial Online o Teams, dependiendo de si se especifica o no el modificador -MoveToTeams.

- Si desea mostrar notificaciones en el cliente de Skype Empresarial para usuarios locales, debe usar TeamsUpgradePolicy en el conjunto de herramientas local. Solo el parámetro NotifySfbUsers es relevante para los usuarios locales.  Los usuarios locales reciben su modo desde las instancias en línea de TeamsUpgradePolicy. Vea las notas de [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps). 

>[!NOTE]
> Los nuevos inquilinos creados después del 3 de septiembre de 2019 se crean como inquilinos de TeamsOnly a menos que la organización ya tenga una implementación local de Skype Empresarial Server. Microsoft usa registros DNS para identificar organizaciones locales de Skype Empresarial Server. Si su organización tiene Skype Empresarial Server local sin entradas DNS públicas, tendrá que llamar al soporte técnico de Microsoft para que el nuevo inquilino se haya degradado. 

## <a name="related-links"></a>Vínculos relacionados

[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](migration-interop-guidance-for-teams-with-skype.md) 

[Configurar la conectividad híbrida entre Skype Empresarial Server y Microsoft 365 u Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover usuarios entre la implementación local y la nube](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configurar su coexistencia y la configuración de actualización](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Usar el servicio de migración de reuniones (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)