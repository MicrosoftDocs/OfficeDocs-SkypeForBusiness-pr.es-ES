---
title: Actualizar Skype Empresarial local a Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Obtenga información sobre cómo actualizar su organización a Microsoft Teams desde una implementación local de Skype Empresarial.
ms.localizationpriority: medium
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
ms.openlocfilehash: c4b233978b9f9edf0aabbdfb8f9b24ff55a234cc
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681371"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a>Actualizar de Skype Empresarial local a Teams

![Diagrama de recorrido de la actualización, en el que se hace hincapié en la implementación y la implementación.](media/upgrade-banner-deployment.png "Fases del recorrido de la actualización, con énfasis en la fase de implementación e implementación")

Este artículo forma parte de la fase de implementación e implementación del recorrido de la actualización. Antes de continuar, confirma que has completado las siguientes actividades:

- [Ha incorporado a las partes interesadas del proyecto](upgrade-enlist-stakeholders.md)
- [Ha definido el ámbito del proyecto](./upgrade-define-project-scope.md)
- [Ha comprendido la coexistencia y la interoperabilidad de Skype Empresarial y Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Elige tu viaje de actualización](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparado para su entorno](./upgrade-prepare-environment.md)
- [Preparado para su organización](./upgrade-prepare-organization.md)
- [Se realizó un piloto](./pilot-essentials.md)

Si ha implementado Skype Empresarial Server o Microsoft Lync Server local y su organización quiere actualizar a Teams, siga las instrucciones de este artículo. Debe configurar la conectividad híbrida con su Microsoft 365 organización como se describe en Planear la [conectividad híbrida entre Skype Empresarial Server y Teams](/skypeforbusiness/hybrid/plan-hybrid-connectivity).

Antes de empezar, también debe revisar [Consideraciones importantes para organizaciones con Skype Empresarial Server local](#important-considerations-for-organizations-with-skype-for-business-server-on-premises) más adelante en este artículo.

> [!IMPORTANT]
> Skype Empresarial Online se retiró el 31 de julio de 2021. Para aprovechar al máximo las ventajas y asegurarse de que su organización dispone del tiempo adecuado para implementar la actualización, le recomendamos que comience ahora su viaje hacia Microsoft Teams. Recuerde que una actualización correcta alinea la preparación técnica y de usuario, por lo que debe asegurarse de aprovechar esta guía mientras se desplaza a Microsoft Teams.

## <a name="step-1-configure-hybrid-connectivity"></a>Paso 1: Configurar la conectividad híbrida

El requisito previo clave para actualizar los usuarios locales a Teams es configurar la conectividad híbrida para la implementación local de Skype Empresarial Server.

Para empezar, lea [Planear la conectividad híbrida](/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=%2fSkypeForBusiness%2fsfbhybridtoc%2ftoc.json) y, después, siga las tareas descritas en [Configurar la conectividad híbrida](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).

## <a name="step-2-set-transitional-coexistence-mode-optional"></a>Paso 2: Establecer el modo de coexistencia transicional (opcional)

La coexistencia y la interoperabilidad entre Skype Empresarial y Teams clientes y usuarios se definen por [modos de coexistencia](migration-interop-guidance-for-teams-with-skype.md). Las organizaciones híbridas están de forma predeterminada en el modo islas. El modo islas permite a los usuarios usar tanto Teams como Skype Empresarial clientes en paralelo. Opcionalmente, las organizaciones pueden usar otros modos de coexistencia para proporcionar una experiencia predecible para los usuarios finales a medida que las organizaciones pasan de Skype Empresarial a Teams. Sea cual sea el modo que use una organización para sus usuarios locales, cuando esos usuarios se mueven de local a la nube, se convierten en TeamsOnly (y no pueden tener ningún otro modo).  Siempre que los usuarios sigan usando Skype Empresarial Server, se les puede asignar cualquier modo que no sea TeamsOnly. Si es necesario, los usuarios de TeamsOnly pueden volver a la instalación local, lo que provocaría que reciban la política global del inquilino de TeamsUpgradePolicy.

Cuando un usuario se encuentra en cualquiera de los modos Skype Empresarial, todos los chats y llamadas entrantes se enrutan al cliente Skype Empresarial del usuario. Para evitar confusiones del usuario final y asegurarse de que el enrutamiento, las llamadas y la funcionalidad de chat correctos en el cliente de Teams se *deshabilitan para un usuario al que se le asigna cualquiera de los modos de Skype Empresarial*. La programación de reuniones en Teams se deshabilita cuando los usuarios se encuentran en los modos SfBOnly o SfBWithTeamsCollab y *se habilitan* cuando un usuario está en el modo SfBWithTeamsCollabAndMeetings.

Dependiendo de sus requisitos, puede asignar el modo de coexistencia adecuado en función de la ruta de actualización que haya elegido su organización. Para obtener más información, consulte [Guía de migración e interoperabilidad para organizaciones que usan Teams junto con Skype Empresarial](migration-interop-guidance-for-teams-with-skype.md) y Establecer la [configuración de coexistencia y actualización](./setting-your-coexistence-and-upgrade-settings.md).

## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>Paso 3: Mover usuarios de Skype Empresarial local a Solo Teams

Microsoft ha simplificado recientemente el proceso para mover usuarios a TeamsOnly. Este proceso es ahora un solo paso, independientemente de la versión de Skype Empresarial Server o Lync Server 2013 que esté usando. Para obtener más información, vea [Mover usuarios entre el entorno local y la nube](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) y [Mover usuarios de un entorno local a Teams](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams).

## <a name="step-4-complete-your-migration-to-the-cloud-by-disabling-hybrid-and-decommissioning-on-premises-skype-for-business"></a>Paso 4: Complete la migración a la nube deshabilitando la implementación híbrida y la retirada local Skype Empresarial

Después de mover todos los usuarios del entorno local a la nube, puede retirar la implementación local Skype Empresarial. Para obtener más información, vea [Retirar el entorno de Skype Empresarial local](/skypeforbusiness/hybrid/decommission-on-prem-overview).

## <a name="phone-system-and-pstn-connectivity-options"></a>Sistema telefónico y las opciones de conectividad con RTC

Sistema telefónico con Teams se admite después de que el usuario esté en modo TeamsOnly. (Si el usuario está en modo Islas, Sistema telefónico solo se admite con Skype Empresarial).

### <a name="pstn-connectivity-options"></a>Opciones de conectividad con RTC

Al considerar las opciones de conectividad de la red telefónica conmutada (RTC), existen dos escenarios posibles al pasar de Skype Empresarial local al modo Solo equipos:

- Un usuario en Skype Empresarial local con Telefonía IP empresarial, que pasará a estar conectado y usando un plan de llamadas de Microsoft. Migrar este usuario a Teams requiere mover la cuenta Skype Empresarial local del usuario a la nube y coordinar que mueva con A) el puerto del número de teléfono de ese usuario a un plan de llamadas de Microsoft o B) asignando un nuevo número de suscriptor de las regiones disponibles.  Para obtener más información, consulte [De Skype Empresarial Server local, con Telefonía IP empresarial, a Microsoft Calling Plan](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan).

- Un usuario en Skype Empresarial local con Telefonía IP empresarial, que se moverá a en línea y mantendrá la conectividad con RTC local. Migrar este usuario a Teams requiere mover la cuenta de Skype Empresarial local del usuario a la nube y coordinarlo con la migración del usuario a Enrutamiento directo. Para obtener más información, vea [Desde Skype Empresarial Server local, con Telefonía IP empresarial, hasta Enrutamiento directo](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing).

## <a name="important-considerations-for-organizations-with-skype-for-business-server-on-premises"></a>Consideraciones importantes para las organizaciones con Skype Empresarial Server local

- Configurar Skype Empresarial implementación híbrida es un requisito previo para migrar al modo TeamsOnly. Es posible que los usuarios locales Skype Empresarial Server usen Teams en el modo Islas sin híbrido. Sin embargo, no se puede realizar la transición al modo TeamsOnly sin mover el usuario a la nube mediante [Move-CsUser](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud), para el que se requiere conectividad híbrida. Para obtener más información, vea [Configurar la conectividad híbrida](/skypeforbusiness/hybrid/configure-hybrid-connectivity). La próxima retirada de Skype Empresarial Online no cambiará este requisito. Para que las organizaciones pasen de Skype Empresarial Server a Teams, deben configurar la implementación híbrida con el mismo conjunto de herramientas, *exactamente como antes de la retirada*.

- Para mover un usuario local a la nube, use `Move-CsUser` las herramientas de administración local. Ya no necesita especificar el `-MoveToTeams` cambio para mover usuarios directamente de local a TeamsOnly. Se asigna automáticamente a los usuarios el modo TeamsOnly y sus reuniones locales se convierten automáticamente en Teams reuniones, independientemente de si se especifica el `-MoveToTeams` cambio.

- Si su organización tiene Skype Empresarial Server y no ha configurado la conectividad híbrida pero todavía desea usar Teams, para administrar Teams funcionalidad debe usar una cuenta administrativa que tenga un dominio .onmicrosoft.com. Sin conectividad híbrida, las herramientas administrativas no reconocerán los dominios locales.

- Teams usuarios que tienen una cuenta de Skype Empresarial local (es decir, que aún no se han movido a la nube mediante Move-CsUser) no pueden interoperar con ningún Skype Empresarial usuarios, ni pueden federar con usuarios externos. Esta funcionalidad solo está disponible una vez que los usuarios se mueven a la nube y son usuarios de TeamsOnly.

- Si tiene usuarios con Skype Empresarial cuentas locales o aún tiene un registro DNS de lyncdiscover para una implementación local, no puede asignar el modo TeamsOnly en el nivel de inquilino. Primero debe mover todos los usuarios con cuentas de Skype Empresarial locales a la nube con `Move-CsUser`. A continuación, siga los pasos descritos en [Deshabilitar la implementación híbrida para completar la migración a la nube](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid), que incluye la eliminación de entradas DNS. `Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`no funcionará en el nivel de inquilino si se detecta un registro DNS de lyncdiscover que apunta a una ubicación que no sea Office 365.

- Debe asegurarse de que los usuarios se sincronizan correctamente en Azure AD con los atributos de Skype Empresarial correctos. Estos atributos son todos prefijos con "msRTCSIP-". Si los usuarios no se sincronizan correctamente con Azure AD, las herramientas de administración de Teams no podrán administrarlos. (Por ejemplo, no podrá asignar directivas de Teams a usuarios locales a menos que sincronice correctamente estos atributos). Para obtener más información, vea [Configurar Conectar de Azure AD para Teams y Skype Empresarial](/SkypeForBusiness/hybrid/configure-azure-ad-connect).

- Para crear un nuevo TeamsOnly en una organización híbrida, *primero debe habilitar el usuario en Skype Empresarial Server local* y, a continuación, mover el usuario de local a la nube mediante Move-CsUser.  Crear primero el usuario local garantiza que cualquier otro usuario local restante Skype Empresarial pueda redirigir al usuario recién creado. Una vez que *todos* los usuarios se han movido en línea, ya no es necesario habilitar primero los usuarios en local.

- Si desea mostrar notificaciones en el cliente de Skype Empresarial para los usuarios locales, debe usar TeamsUpgradePolicy en el conjunto de herramientas local. Solo el parámetro NotifySfbUsers es relevante para los usuarios locales.  Los usuarios locales reciben su modo de las instancias en línea de TeamsUpgradePolicy. Vea las notas en [Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy).

> [!NOTE]
> Los nuevos inquilinos creados después del 3 de septiembre de 2019 se crean como inquilinos de TeamsOnly, a menos que la organización ya tenga una implementación local de Skype Empresarial Server. Microsoft usa registros DNS para identificar organizaciones Skype Empresarial Server locales. Para obtener más información, vea [Implicaciones DNS para organizaciones locales que se convierten en híbridas](/SkypeForBusiness/hybrid/configure-hybrid-connectivity#dns-implications-for-on-premises-organizations-that-become-hybrid).

- En los artículos siguientes se describen conceptos de actualización importantes y comportamientos de coexistencia:
  - [Coexistencia de Teams y Skype Empresarial](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
  - [Modos de coexistencia: referencia](migration-interop-guidance-for-teams-with-skype.md)
  - [Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="related-links"></a>Vínculos relacionados

[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](migration-interop-guidance-for-teams-with-skype.md)

[Configurar la conectividad híbrida entre Skype Empresarial Server y Microsoft 365 o Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover usuarios entre la implementación local y la nube](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configurar su coexistencia y la configuración de actualización](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)

[Usar el servicio de migración de reuniones (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
