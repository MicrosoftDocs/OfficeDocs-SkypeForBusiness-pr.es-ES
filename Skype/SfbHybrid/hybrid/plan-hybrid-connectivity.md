---
title: Planear la conectividad híbrida | Skype Empresarial Server y Teams
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
search.appverid: MET150
description: Planee implementar la conectividad híbrida entre Skype Empresarial Server y Teams mediante la configuración de Skype Empresarial modo híbrido.
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: a73b14a3642a216ff9cbbe919b586979aabf6a81
ms.sourcegitcommit: 15ec17eff4ad4c962d00b8683513f9b269d82917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2022
ms.locfileid: "66695053"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-teams"></a>Planeamiento de la conectividad híbrida entre Skype Empresarial Server y Teams

> [!Important]
> Aunque Skype Empresarial Online se ha retirado desde 2021, los productos locales Skype Empresarial Server 2019, Skype Empresarial Server 2015 y Lync Server 2013 siguen siendo compatibles. Además, Microsoft admite entornos híbridos entre estos productos locales y Microsoft Teams. Esto permite a las organizaciones con estas implementaciones locales migrar sus usuarios a TeamsOnly.  Por último, ya no se admite Cloud Connector Edition de Skype Empresarial Server. Los clientes que requieren conectividad RTC local deben usar [enrutamiento directo](/MicrosoftTeams/direct-routing-landing-page).


Lea este tema para obtener información sobre cómo planear la conectividad híbrida entre Skype Empresarial Server o Lync Server 2013 y Teams. La configuración de la conectividad híbrida es el primer paso para pasar del entorno local a un entorno solo de Microsoft Teams en la nube.

En una implementación local de Skype Empresarial Server, los usuarios de Skype Empresarial también pueden usar Teams, pero no todas las funciones de Teams están disponibles para dichos usuarios, siempre y cuando estén configurados para usar la implementación de Skype Empresarial Server local. Se dice que estos usuarios están "hospedados" en el entorno local y que cierta funcionalidad de Teams no está disponible mientras estos usuarios están hospedados en el entorno local, por ejemplo:

- Las llamadas federadas y los chats a través del cliente de Teams del usuario con usuarios de otras organizaciones no están disponibles
- Comunicación de interoperabilidad a través del cliente de Teams del usuario con otros usuarios de la organización que usan Skype Empresarial cliente.
- Funcionalidad de llamada RTC (si al usuario se le asigna una licencia del sistema telefónico).

Para obtener una funcionalidad completa de Teams, estos usuarios deben moverse de Skype Empresarial local a la nube, momento en el que el usuario se convierte en TeamsOnly. El acto de mover un usuario del entorno local a la nube establecerá el modo de coexistencia del usuario en TeamsOnly. Una vez que los usuarios se mueven a la nube y TeamsOnly, todos los chats y llamadas entrantes llegan a su cliente de Teams (a diferencia del uso en paralelo de Teams).  Para obtener más información, consulte [Coexistencia de Teams con Skype Empresarial y Guía](/microsoftteams/coexistence-chat-calls-presence) de [migración e interoperabilidad para organizaciones que usan Teams junto con Skype Empresarial](/microsoftteams/migration-interop-guidance-for-teams-with-skype).

Mover usuarios entre el entorno local y TeamsOnly en la nube requiere configurar Skype Empresarial modo híbrido. Además, antes de retirar la Skype Empresarial implementación local, mueva todos los usuarios del entorno local a la nube.   Con la configuración de conectividad híbrida, puede mover a los usuarios a la nube según la programación y sus necesidades empresariales.  Con el enrutamiento directo, puede aprovechar su infraestructura de voz local mientras se desplaza a la nube y después de que se complete la migración.

En este tema se describen los requisitos de infraestructura y sistema que necesitará para configurar la conectividad híbrida entre la implementación de Skype Empresarial Server local existente y Teams.

Una vez que haya leído este tema y esté listo para configurar la conectividad híbrida, consulte Configuración de la [conectividad híbrida entre Skype Empresarial Server y Teams](configure-hybrid-connectivity.md). Los temas de configuración proporcionan instrucciones paso a paso para configurar la conectividad híbrida entre la implementación local y Teams.


## <a name="implications-of-the-retirement-of-skype-for-business-online"></a>Implicaciones de la retirada de Skype Empresarial Online
Es importante recordar que antes y después de la retirada de Skype Empresarial Online, los usuarios hospedados en Skype Empresarial Server locales pueden usar Teams, pero no pueden ser TeamsOnly. (Los usuarios locales están en modo Islas de forma predeterminada y se les asigna cualquier modo que no sea TeamsOnly). Los usuarios solo pueden experimentar las ventajas completas de Teams, en particular la federación, la compatibilidad con RTC y la garantía de que todos los chats y llamadas entrantes llegan a Teams, una vez que están en el modo TeamsOnly. 

La retirada de Skype Empresarial Online no tiene ningún impacto en el ciclo de vida de soporte técnico existente de Skype Empresarial Server o Lync Server 2013.  Sin embargo, la retirada de Skype Empresarial Online influyó en ciertos aspectos de **la** *transición de los usuarios a la nube y se convirtió en TeamsOnly* en organizaciones con Skype Empresarial Server local o Lync Server 2013, incluidas las organizaciones híbridas existentes. El uso de híbrido como configuración de requisito previo para realizar la transición del entorno local a la nube (por ejemplo, TeamsOnly) permanece sin cambios.

Antes de la retirada de Skype Empresarial Online, las organizaciones híbridas podrían constar de tres tipos básicos de usuarios: 
- Usuarios locales (que pueden o no usar Teams, pero no en el modo solo teams) 
- Usuarios en línea con cualquier modo de coexistencia que no sea TeamsOnly
- Usuarios de TeamsOnly.

Sin embargo, después de la retirada de Skype Empresarial Online, las organizaciones híbridas solo pueden constar de dos tipos básicos de usuarios: 
- Usuarios locales (quién puede o no usar Teams, pero no en el modo TeamsOnly)
- Solo usuarios de Teams. 

Para que las organizaciones pasen de Skype Empresarial Server o Lync Server 2013 a Teams, deben configurar y configurar híbridos con el mismo conjunto de herramientas, *exactamente como antes de la retirada*. Al mover un usuario del entorno local a TeamsOnly, ya no es necesario especificar el `-MoveToTeams` modificador en `Move-CsUser`. Anteriormente, si no se especificaba este modificador, los usuarios pasaron de estar hospedados en Skype Empresarial Server local a Skype Empresarial En línea y su modo permaneció sin cambios. Sin embargo, dado que Skype Empresarial Online se ha retirado, el traslado de un usuario del entorno local a la nube con `Move-CsUser` asignará *automáticamente* el modo TeamsOnly e iniciará la conversión de sus reuniones desde el entorno local a las reuniones de Teams, independientemente de si se especifica el `-MoveToTeams` modificador. Esto también significa que las organizaciones con Lync Server 2013, que nunca han tenido el `MoveToTeams` cambio, pueden mover usuarios directamente a TeamsOnly desde el entorno local. 

Del mismo modo, si se crea un nuevo usuario directamente en Microsoft 365 en lugar de en el entorno local, ese usuario tendrá automáticamente el modo Solo teams independientemente del modo del inquilino. Tenga en cuenta que en una organización híbrida con al menos un usuario local, se deben crear nuevos usuarios en el Active Directory local (y luego sincronizarse con Microsoft 365), en lugar de crear directamente un usuario en Microsoft 365, para asegurarse de que los usuarios locales puedan enrutar al nuevo usuario *incluso si pretende que el nuevo usuario sea un usuario en la nube*. Una vez creados en el directorio local, estos nuevos usuarios deben estar habilitados para sip *en la* implementación local Skype Empresarial y, después, si lo desea, se mueven a la nube para convertirse en TeamsOnly. 

Los modos de coexistencia siguen existiendo después de la retirada de Skype Empresarial Online. Como antes, a los usuarios con cuentas hospedados en Skype Empresarial Server local se les puede asignar cualquier modo de coexistencia excepto TeamsOnly. Sin embargo, después de la retirada, los usuarios hospedados en línea solo pueden ser TeamsOnly. Ya no es posible asignar un modo distinto de TeamsOnly a un usuario hospedado en línea.


> [!Important]
> Las organizaciones híbridas existentes con usuarios hospedados en Skype Empresarial Online que NO son TeamsOnly deben centrarse en actualizar estos usuarios al modo solo de Teams lo antes posible. Si su organización sigue teniendo usuarios hospedados en Skype Empresarial *Online* que no son TeamsOnly, se programará una actualización asistida por Microsoft para realizar la transición de estos usuarios a TeamsOnly. **Las actualizaciones asistidas por Microsoft no afectarán a los usuarios hospedados en Skype Empresarial Server local.** Las notificaciones de programación se enviarán de antemano a los clientes híbridos con usuarios hospedados en Skype Empresarial Online antes de que estos usuarios en línea que no sean de TeamsOnly se actualicen a Teams.

## <a name="about-shared-sip-address-space-functionality"></a>Acerca de la funcionalidad del espacio de direcciones SIP compartido

<a name="BKMK_Overview"> </a>

Con la conectividad híbrida configurada entre una implementación local de Skype Empresarial Server y Teams, puede tener algunos usuarios hospedados en el entorno local y algunos usuarios hospedados en línea.

Este tipo de configuración se basa en la funcionalidad del espacio de direcciones SIP compartido y, a veces, se conoce como "dominio dividido", lo que significa que los usuarios de un dominio, como contoso.com, se dividen entre el uso de Skype Empresarial Server local y Teams, como se muestra en el diagrama siguiente:

![Skype Empresarial Hybrid conectividad: división de dominio.](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

Cuando se configura el espacio de direcciones SIP compartido:

- Azure Active Directory Connect se usa para sincronizar el directorio local con Microsoft 365.
- Los usuarios hospedados en el entorno local interactúan con servidores de Skype Empresarial locales.
- Los usuarios hospedados en línea interactúan con Teams.
- Los usuarios de ambos entornos pueden comunicarse entre sí.
- El Active Directory local es autoritativo. Todos los usuarios deben crearse primero en la Active Directory local y, a continuación, sincronizarse con Azure AD. Incluso si pretende que el usuario esté hospedado en línea, primero debe crear el usuario en el entorno local y, a continuación, moverlo a línea para asegurarse de que los usuarios locales puedan detectarlo.

Antes de que un usuario se pueda mover en línea, se le debe asignar una licencia de Teams, así como Skype Empresarial En línea (plan 2). **Se requiere la asignación de la licencia de Skype Empresarial Online incluso después de la retirada de Skype Empresarial Online.** Si los usuarios quieren aprovechar las características en línea adicionales, como audioconferencia o sistema telefónico, debe asignarles la licencia adecuada en Microsoft 365.

## <a name="hybrid-connectivity-infrastructure-requirements"></a>Requisitos de infraestructura de conectividad híbrida

<a name="BKMK_Infrastructure"> </a>

Para implementar la conectividad híbrida entre el entorno local y los servicios de comunicación de Microsoft 365, debe cumplir los siguientes requisitos de infraestructura:

- Una única implementación local de Skype Empresarial Server o Lync Server que se implementa en una topología compatible. Consulte [Requisitos de topología](plan-hybrid-connectivity.md#BKMK_Topology) en este tema.

- Una organización de Microsoft 365 con Teams.
    > [!NOTE]
    > Solo puede usar un único inquilino para una configuración híbrida con la implementación local.
    
- Azure Active Directory Connect para sincronizar el directorio local con Microsoft 365. Para obtener más información, consulte [Azure AD Connect: Cuentas y permisos](/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions)

- Skype Empresarial Server herramientas administrativas. Estos son necesarios para mover usuarios del entorno local a la nube. Estas herramientas deben instalarse en un servidor con acceso tanto a la implementación local como a Internet.
- Herramientas administrativas en línea. Puede usar el Centro de administración de Teams o Windows PowerShell para administrar Teams. Para usar PowerShell para administrar Teams, descargue e instale el módulo de PowerShell de Teams. (Se ha retirado el conector Skype Empresarial Online).
- El espacio de direcciones SIP compartido debe estar habilitado y la implementación local debe configurarse para usar Microsoft 365 como proveedor de hospedaje. Para obtener más información sobre los pasos necesarios para configurar la conectividad híbrida, consulte [Configuración de la conectividad híbrida](configure-hybrid-connectivity.md).

Después de configurar la conectividad híbrida, puede mover usuarios a Teams. Para obtener más información, consulte [Traslado de usuarios del entorno local a Teams](move-users-from-on-premises-to-teams.md).

## <a name="server-version-requirements"></a>Requisitos de versión del servidor

<a name="BKMK_Topology"> </a>

Para configurar la implementación híbrida con **Teams**, debe tener una de las siguientes topologías admitidas:

- Una implementación de Skype Empresarial Server 2019 con todos los servidores que ejecuten Skype Empresarial Server 2019.
- Una implementación de Skype Empresarial Server 2015 con todos los servidores que ejecuten Skype Empresarial Server 2015.
- Una implementación de Lync Server 2013 donde todos los servidores ejecuten Lync Server 2013.  Sin embargo, si se requiere conectividad de voz híbrida, debe usar una topología de versión mixta como se indica a continuación.
- Una implementación con un máximo de 2 versiones de servidor diferentes, como se muestra a continuación:
  - Skype Empresarial Server 2015 y Skype Empresarial Server 2019
  - Lync Server 2013 y Skype Empresarial Server 2019
  - Lync Server 2013 y Skype Empresarial Server 2015
- A partir del 31 de julio de 2022, para mover usuarios entre una implementación local y la nube, debe usar las siguientes versiones mínimas de Skype Empresarial Server o Lync Server:
</br>

|Producto local|Versión mínima necesaria|Compilación mínima necesaria|
|---|---|---|
|Skype Empresarial Server 2019| CU6 |7.0.2046.385|
|Skype Empresarial Server 2015| CU12|6.0.9319.619|
|Lync Server 2013| CU10 con revisión 7|5.0.8308.1182|

</br>

> [!NOTE] 
> Lync Server 2010 no es compatible con Teams.


## <a name="multi-forest-support"></a>Compatibilidad con varios bosques

<a name="BKMK_MultiForest"> </a>

Microsoft admite los siguientes tipos de escenarios híbridos de varios bosques:

- **Topología de bosque de recursos.** En este tipo de topología, hay un bosque que hospeda Skype Empresarial Server (el bosque de recursos) y hay uno o más bosques adicionales que hospedan identidades de cuenta, que acceden a la Skype Empresarial Server en el bosque de recursos. En general, los usuarios pueden acceder a la funcionalidad de Skype Empresarial en otro bosque si se cumplen los siguientes requisitos:
  - Los usuarios se sincronizan correctamente en el bosque que hospeda a Skype Empresarial. En las configuraciones híbridas, esto significa que los usuarios deben sincronizarse como objetos de usuario deshabilitados.
  - El bosque que hospeda a Skype Empresarial debe confiar en el bosque que contiene los usuarios.
    Para obtener más información sobre los escenarios híbridos del bosque de recursos, consulte [Implementación de una topología de bosque de recursos para Skype Empresarial híbridas](configure-a-multi-forest-environment-for-hybrid.md).

- **Varias implementaciones de Skype Empresarial Server en varios bosques.** Esta configuración puede surgir como resultado de escenarios de fusión y adquisición, así como en empresas más complejas. La consolidación de todos los usuarios del entorno local a la nube en una sola organización de Microsoft 365 se puede lograr para cualquier organización con varias implementaciones de Skype Empresarial, siempre que se cumplan los siguientes requisitos clave:
  - Debe haber como máximo una organización de Microsoft 365 implicada. No se admite la consolidación en escenarios con más de una organización.
  - En todo momento, solo puede haber un bosque local de Skype Empresarial en modo híbrido (espacio de direcciones SIP compartido). Todos los demás bosques de Skype Empresarial locales deben permanecer totalmente locales (y probablemente federados entre sí). Tenga en cuenta que estas otras organizaciones locales pueden sincronizarse con AAD si lo desea con [una nueva funcionalidad para deshabilitar los dominios SIP en línea disponibles a](/powershell/module/skype/disable-csonlinesipdomain) partir de diciembre de 2018.

    Los clientes con implementaciones de Skype Empresarial en varios bosques deben migrar completamente cada bosque de Skype Empresarial individualmente a la organización de Microsoft 365 mediante la funcionalidad de dominio dividido (espacio de direcciones SIP compartido). Una vez completada la migración del bosque, los clientes deben deshabilitar la implementación híbrida con la implementación local antes de migrar la siguiente implementación local Skype Empresarial. Además, antes de migrarse a la nube, los usuarios locales permanecen en un estado federado con los usuarios que no están representados en el directorio local del mismo usuario. Para obtener más información, consulte [Consolidación de la nube para Teams y Skype Empresarial](cloud-consolidation.md).

## <a name="federation-requirements"></a>Requisitos de federación

<a name="BKMK_Federation"> </a>

Al configurar Skype Empresarial modo híbrido, debe asegurarse de que los entornos locales y en línea pueden federarse entre sí.  El entorno en línea tiene federación abierta de forma predeterminada; el entorno local suele tener una federación cerrada de forma predeterminada.  

Se deben cumplir los siguientes requisitos para configurar correctamente una implementación híbrida:

- La coincidencia de dominios debe configurarse igual para la implementación local y la organización de Microsoft 365. Si la detección de asociados está habilitada en la implementación local, la federación abierta debe configurarse para la organización en línea. Si la detección de asociados no está habilitada, se debe configurar la federación cerrada para la organización en línea.
- La lista Dominios bloqueados de la implementación local debe coincidir exactamente con la lista Dominios bloqueados para el inquilino en línea.
- La lista Dominios permitidos de la implementación local debe coincidir exactamente con la lista Dominios permitidos del inquilino en línea.
- La federación debe estar habilitada para las comunicaciones externas para el inquilino en línea.

## <a name="network-considerations"></a>Consideraciones relacionadas con la red

En las secciones siguientes se describen las consideraciones para:

- Configuración de DNS
- Consideraciones de firewall

### <a name="dns-settings-for-hybrid-deployments"></a>Configuración de DNS para implementaciones híbridas

<a name="BKMK_DNS"> </a>

Al crear registros DNS para implementaciones híbridas, todos los registros DNS externos de Skype Empresarial deben apuntar a la infraestructura local. Para obtener más información sobre los registros DNS necesarios, consulte [Requisitos de DNS para Skype Empresarial Server](../../sfbserver/plan-your-deployment/network-requirements/dns.md).

Además, debe asegurarse de que la resolución DNS descrita en la tabla siguiente funciona en la implementación local. (Si ya ha configurado la federación para entornos locales, lo más probable es que ya los tenga).

|Registro DNS  <br/> |Resuelto por  <br/> |Requisito de DNS  <br/> |
|:-----|:-----|:-----|
|Registro SRV de DNS para _sipfederationtls._tcp.\<sipdomain.com\> para todos los dominios SIP admitidos que se resuelven en direcciones IP externas de Access Edge  <br/> |Servidor(es) perimetral(es)  <br/> |Habilite la comunicación federada en una configuración híbrida. El servidor perimetral debe saber dónde enrutar el tráfico federado para el dominio SIP que se divide entre local y en línea.  <br/> Debe usar la coincidencia estricta de nombres DNS entre el dominio en el nombre de usuario y el registro SRV.  <br/> |
|Registros A de DNS para el FQDN del servicio de conferencia web perimetral, por ejemplo, webcon.contoso.com resolver en direcciones IP externas perimetrales de conferencia web  <br/> |Equipos de usuarios conectados a la red corporativa interna  <br/> |Permitir a los usuarios en línea presentar o ver contenido en reuniones hospedadas locales. El contenido incluye archivos PowerPoint, pizarras, sondeos y notas compartidas.  <br/> |

Dependiendo de cómo esté configurado el DNS en su organización, es posible que tenga que añadir estos registros a la zona DNS interna hospedada para el(los) dominio(s) SIP correspondiente(s) para proporcionar una resolución DNS interna a estos registros.

### <a name="firewall-considerations-for-hybrid-deployments"></a>Consideraciones de firewall para implementaciones híbridas

<a name="BKMK_Firewall"> </a>

Los equipos de la red deben ser capaces de realizar búsquedas de DNS de Internet estándar. Si estos equipos pueden tener acceso a sitios de Internet estándar, la red cumple este requisito.

En función de la ubicación del centro de datos de Microsoft Online Services, también debe configurar los dispositivos de firewall de red para aceptar conexiones basadas en nombres de dominio comodín (por ejemplo, todo el tráfico de \*.outlook.com). Si los firewalls de su organización no admiten configuraciones de nombres comodín, tendrá que determinar manualmente los intervalos de direcciones IP que desea permitir y los puertos especificados.

Para obtener más información, incluidos los detalles sobre los puertos y los requisitos de protocolo, consulte [Direcciones URL y intervalos de direcciones IP de Microsoft 365](/microsoft-365/enterprise/urls-and-ip-address-ranges).
