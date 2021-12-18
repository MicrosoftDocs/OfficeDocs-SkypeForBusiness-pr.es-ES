---
title: Actualizar Skype Empresarial local a Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Obtenga información sobre cómo actualizar su organización Microsoft Teams desde una Skype Empresarial implementación local.
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
ms.openlocfilehash: b13722c85a7cd051e695f81a62cb2533b5cf35f2
ms.sourcegitcommit: b0bb7db41856ee377dbe4ca8c9dff56385bf120d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2021
ms.locfileid: "61563749"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a>Actualizar de Skype Empresarial local a Teams

![Diagrama de viaje de actualización, haciendo hincapié en implementación e implementación.](media/upgrade-banner-deployment.png "Fases del viaje de actualización, con énfasis en la fase implementación e implementación")

Este artículo forma parte de la fase de implementación e implementación del viaje de actualización. Antes de continuar, confirme que ha completado las siguientes actividades:

-   [Ha incorporado a las partes interesadas del proyecto](upgrade-enlist-stakeholders.md)
-   [Ha definido el ámbito del proyecto](./upgrade-define-project-scope.md)
-   [Ha comprendido la coexistencia y la interoperabilidad de Skype Empresarial y Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
-   [Elegido el viaje de actualización](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [Preparado el entorno](./upgrade-prepare-environment.md)
-   [Preparar la organización](./upgrade-prepare-organization.md)
-   [Llevó a cabo un piloto](./pilot-essentials.md)

Si ha implementado Skype Empresarial Server Microsoft Lync local y su organización desea actualizar a Teams, siga las instrucciones de este artículo. Debe configurar la conectividad híbrida con su organización Microsoft 365 o Office 365 y determinar los requisitos de coexistencia si mueve a los usuarios Teams fases.

Antes de empezar, los profesionales de [](#important-considerations-for-organizations-with-skype-for-business-server-on-premises) TI y los administradores deben revisar las consideraciones importantes para las organizaciones con Skype Empresarial Server locales más adelante en este artículo.

> [!IMPORTANT]
> Skype Empresarial Online se retiró el 31 de julio de 2021. Para aprovechar al máximo las ventajas y asegurarse de que su organización dispone del tiempo adecuado para implementar la actualización, le recomendamos que comience ahora su viaje hacia Microsoft Teams. Recuerde que una actualización correcta alinea la preparación técnica y del usuario, por lo que asegúrese de aprovechar estas instrucciones a medida que vaya navegando hasta Microsoft Teams.

## <a name="step-1-configure-hybrid-connectivity"></a>Paso 1: Configurar la conectividad híbrida 

El requisito previo clave para actualizar los usuarios locales a Teams es configurar la conectividad híbrida para su Skype Empresarial Server implementación local. 

Empiece leyendo [Planear conectividad híbrida](/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=%2fSkypeForBusiness%2fsfbhybridtoc%2ftoc.json)y, a continuación, siga las tareas descritas en Configurar conectividad [híbrida.](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)


## <a name="step-2-set-transitional-coexistence-mode-optional"></a>Paso 2: Establecer el modo de coexistencia de transición (opcional)

La coexistencia y la interoperabilidad entre Skype Empresarial y Teams clientes y usuarios se definen mediante Teams de actualización.  Las organizaciones híbridas, así como cualquier organización creada antes del 3 de septiembre de 2019, están de forma predeterminada en el modo Islas. El modo Islas permite a los usuarios usar Teams y Skype Empresarial clientes en paralelo. Para una organización que se mueve a Teams, el modo TeamsOnly es el destino final para cada usuario, aunque no todos los usuarios deben tener asignado TeamsOnly (o cualquier otro modo) al mismo tiempo.

Antes de que los usuarios lleguen al modo TeamsOnly, las organizaciones pueden usar opcionalmente cualquiera de los modos de coexistencia de Skype Empresarial para garantizar una comunicación predecible entre los usuarios que están en modo TeamsOnly y los usuarios que aún no lo están.  El propósito de los modos de coexistencia Skype Empresarial (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) es proporcionar una experiencia sencilla y predecible para los usuarios finales a medida que las organizaciones transición de Skype Empresarial a Teams. Se puede asignar a un usuario Skype Empresarial Server local cualquier modo que no sea TeamsOnly. Una vez que un usuario se mueve a la nube, son TeamsOnly.  No se puede asignar a los usuarios solo en la nube un modo distinto de TeamsOnly. (Sin embargo, se pueden volver a mover a las instalaciones locales, lo que daría como resultado que reciban la directiva global del inquilino de TeamsUpgradePolicy).

Cuando un usuario está en cualquiera de los modos Skype Empresarial, todos los chats y llamadas entrantes se enruta al cliente Skype Empresarial usuario. Para evitar confusiones entre usuarios finales y garantizar el enrutamiento adecuado, las llamadas y la funcionalidad de chat en el cliente de Teams está deshabilitada cuando un usuario está en cualquiera de los Skype Empresarial modos. De forma similar, la programación de reuniones en Teams se deshabilita explícitamente cuando los usuarios están en los modos SfBOnly o SfBWithTeamsCollab y se habilita explícitamente cuando un usuario está en el modo SfBWithTeamsCollabAndMeetings.

Según sus requisitos, puede asignar el modo de coexistencia adecuado en función de la ruta de actualización que haya elegido su organización. Para obtener más información, vea Instrucciones de migración e interoperabilidad para organizaciones que usan Teams junto con [Skype Empresarial](migration-interop-guidance-for-teams-with-skype.md) y Establecer la configuración de coexistencia [y actualización.](./setting-your-coexistence-and-upgrade-settings.md)


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>Paso 3: Mover usuarios de Skype Empresarial local a Teams solo

Microsoft ha simplificado recientemente el proceso para mover usuarios a TeamsOnly. Este proceso es ahora un solo paso, independientemente de la versión de Skype Empresarial Server o Lync Server 2013 que esté usando. Para obtener más información, vea [Mover usuarios](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) entre locales y la nube y Mover usuarios de local a [Teams](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams). 

## <a name="step-4-disable-hybrid-to-complete-your-migration-to-the-cloud"></a>Paso 4: Deshabilitar la implementación híbrida para completar la migración a la nube

Después de mover todos los usuarios de local a la nube, puede retirar la implementación local Skype Empresarial implementación. Para obtener más información, vea [Deshabilitar la implementación híbrida para completar la migración a la nube.](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)


## <a name="phone-system-and-pstn-connectivity-options"></a>Sistema telefónico y las opciones de conectividad RTC

Sistema telefónico con Teams es compatible después de que el usuario esté en modo TeamsOnly. (Si el usuario está en modo Islas, Sistema telefónico solo es compatible con Skype Empresarial). 

### <a name="pstn-connectivity-options"></a>Opciones de conectividad RTC

Al considerar las opciones de conectividad de red telefónica conmutada (RTC), hay dos escenarios posibles al pasar de Skype Empresarial local al modo TeamsOnly:

- Un usuario de Skype Empresarial local con Telefonía IP empresarial, que se trasladará a internet y usará un plan de Microsoft Calling. Migrar este usuario a Teams requiere mover la cuenta de Skype Empresarial local del usuario Skype Empresarial la nube y coordinar que se muevan con cualquiera de las dos A) el puerto del número de teléfono de ese usuario a un Plan de llamadas de Microsoft o B) asignando un nuevo número de suscriptor de las regiones disponibles.  Para obtener más información, vea De Skype Empresarial Server local, con [Telefonía IP empresarial, a Microsoft Calling Plan](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan).

- Un usuario de Skype Empresarial local con Telefonía IP empresarial, que pasará a estar conectado y mantendrá la conectividad RTC local. Migrar este usuario Teams requiere mover la cuenta de Skype Empresarial local del usuario Skype Empresarial la nube y coordinar ese movimiento con la migración del usuario a Enrutamiento directo. Para obtener más información, vea De Skype Empresarial Server local, con [Telefonía IP empresarial, a Enrutamiento directo.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)


## <a name="important-considerations-for-organizations-with-skype-for-business-server-on-premises"></a>Consideraciones importantes para organizaciones con Skype Empresarial Server locales

- En los artículos siguientes se describen conceptos de actualización importantes y comportamientos de coexistencia:
    - [Coexistencia de Teams y Skype Empresarial](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
    - [Modos de coexistencia: referencia](migration-interop-guidance-for-teams-with-skype.md)
    - [Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia](teams-client-experience-and-conformance-to-coexistence-modes.md)

- Configurar Skype Empresarial híbrido es un requisito previo para migrar al modo TeamsOnly. Aunque es posible que los usuarios de Skype Empresarial Server locales usen Teams en modo islas sin híbrido, la transición al modo TeamsOnly no se puede realizar sin mover el usuario a la nube con [Move-CsUser,](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)para el que se requiere conectividad híbrida. Para obtener más información, vea [Configurar la conectividad híbrida.](/skypeforbusiness/hybrid/configure-hybrid-connectivity) Además, la próxima retirada de Skype Empresarial Online no cambiará este requisito. Para que las organizaciones se muevan de Skype Empresarial Server a Teams, deben configurar y configurar la implementación híbrida con el mismo conjunto de herramientas, exactamente igual que antes de *la retirada.*

- Para mover un usuario local a la nube, use las herramientas de administración `Move-CsUser` locales. Ya no es necesario especificar el cambio para mover usuarios directamente desde local `-MoveToTeams` a TeamsOnly. Al mover un usuario de local a la nube con , ahora los usuarios se asignan automáticamente al modo TeamsOnly y sus reuniones desde locales se convierten automáticamente en reuniones de Teams, igual que si el modificador se especifica `Move-CsUser` `-MoveToTeams switch had been specified` realmente.

- Si su organización tiene Skype Empresarial Server y no ha configurado la conectividad híbrida, pero todavía desea usar Teams, para administrar una funcionalidad Teams debe usar una cuenta administrativa que tenga un dominio .onmicrosoft.com. Sin conectividad híbrida, las herramientas administrativas no reconocerán los dominios locales. 

- Teams usuarios que tienen una cuenta de Skype Empresarial local (es decir, aún no se han movido a la nube mediante Move-CsUser) no pueden interoperar con ningún usuario de Skype Empresarial, ni pueden federar con usuarios externos. Esta funcionalidad solo está disponible una vez que los usuarios se mueven a la nube y son usuarios de TeamsOnly. 

- Si tiene usuarios con cuentas Skype Empresarial locales o si todavía tiene un registro DNS de detección de lync para una implementación local, no puede asignar el modo TeamsOnly en el nivel de inquilino. Primero debe mover todos los usuarios con cuentas de Skype Empresarial locales Skype Empresarial a la nube y, a continuación, siga los pasos descritos en Deshabilitar la implementación híbrida para completar la migración a la nube, que incluye la eliminación de entradas `Move-CsUser` DNS. [](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)  `Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`no funcionará en el nivel de inquilino si se detecta un registro DNS de detección de lync que apunta a una ubicación que no sea Office 365.

- Debe asegurarse de que los usuarios están sincronizados correctamente en Azure AD con los atributos Skype Empresarial datos. Estos atributos son todos prefijos con "msRTCSIP-". Si los usuarios no están sincronizados correctamente Azure AD, las herramientas de administración de Teams no podrán administrar estos usuarios. (Por ejemplo, no podrá asignar directivas de Teams a los usuarios locales a menos que sincronice correctamente estos atributos). Para obtener más información, [vea Configurar Azure AD Conectar para Teams y Skype Empresarial](/SkypeForBusiness/hybrid/configure-azure-ad-connect).

- Para crear un nuevo TeamsOnly en una organización híbrida, primero debe habilitar el usuario en Skype Empresarial Server local *y, después,* mover el usuario de local a la nube con Move-CsUser.  La creación del usuario en el entorno local garantiza primero que cualquier otro usuario local que Skype Empresarial pueda dirigirse al usuario recién creado. Una *vez que* todos los usuarios se han movido en línea, ya no es necesario habilitar primero a los usuarios en el entorno local.

- Si desea mostrar notificaciones en el cliente Skype Empresarial para usuarios locales, debe usar TeamsUpgradePolicy en el conjunto de herramientas local. Solo el parámetro NotifySfbUsers es relevante para los usuarios locales.  Los usuarios locales reciben su modo desde las instancias en línea de TeamsUpgradePolicy. Vea las notas de [Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps). 

>[!NOTE]
> Los nuevos inquilinos creados después del 3 de septiembre de 2019 se crean como inquilinos de TeamsOnly a menos que la organización ya tenga una implementación local de Skype Empresarial Server. Microsoft usa registros DNS para identificar las organizaciones Skype Empresarial Server local. Si su organización tiene Skype Empresarial Server local sin entradas DNS públicas, tendrá que llamar al soporte técnico de Microsoft para que el nuevo inquilino se haya degradado. 

## <a name="related-links"></a>Vínculos relacionados

[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](migration-interop-guidance-for-teams-with-skype.md) 

[Configurar la conectividad híbrida entre Skype Empresarial Server y Microsoft 365 o Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover usuarios entre la implementación local y la nube](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configurar su coexistencia y la configuración de actualización](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Usar el servicio de migración de reuniones (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
