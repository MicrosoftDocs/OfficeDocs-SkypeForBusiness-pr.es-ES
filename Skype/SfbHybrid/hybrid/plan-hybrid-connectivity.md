---
title: Planeación de la conexión híbrida | Skype Empresarial Server 2019 y Teams
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Planee implementar la conectividad híbrida entre Skype Empresarial Server y Teams o Skype Empresarial Online mediante la configuración Skype Empresarial modo híbrido.
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: d8f1468d4278c905779a5cbb31e98bd4d0ffa6a4
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2021
ms.locfileid: "53509831"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-teams"></a>Planear la conectividad híbrida entre Skype Empresarial Server y Teams

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Lea este tema para obtener información sobre cómo planear la conectividad híbrida entre Skype Empresarial Server y Teams (o Skype Empresarial Online hasta el 31 de julio de 2021). Configurar la conectividad híbrida es el primer paso para trasladar el entorno local a la nube.

Si tiene usuarios locales de Skype Empresarial que también usan Teams (en paralelo), estos usuarios no pueden interoperar con los usuarios de Skype Empresarial desde el cliente de Teams, ni comunicarse con los usuarios de las organizaciones federadas desde el cliente de Teams. Para obtener esta funcionalidad en Teams, estos usuarios deben trasladarse de Skype Empresarial local a la nube, lo que requiere configurar el modo híbrido de Skype Empresarial. Además, para obtener la mejor experiencia, estos usuarios deben estar en modo de solo Teams, lo que garantiza que todas las llamadas entrantes y los chats de cualquier usuario aterrice en el cliente de Teams usuario.

También hay que configurar la conectividad híbrida y trasladar a todos los usuarios a la nube antes de que se retire la implementación de Skype Empresarial local.  Con la configuración de conectividad híbrida, puede mover a los usuarios a la nube según la programación y sus necesidades empresariales. Con el enrutamiento directo, puede aprovechar su infraestructura de voz local mientras se desplaza a la nube y después de que se complete la migración.

En este tema se describen los requisitos de infraestructura y sistema que necesitará para configurar la conectividad híbrida entre la implementación local Skype Empresarial Server y Teams o Skype Empresarial Online.

Después de leer este tema y estar listo para configurar la conectividad híbrida, vea [Configure hybrid connectivity between Skype Empresarial Server and Microsoft 365 or Office 365](configure-hybrid-connectivity.md). Los temas de configuración proporcionan instrucciones paso a paso para configurar la conectividad híbrida entre la implementación local y Teams o Skype Empresarial Online.

> [!Important]
> Skype Empresarial Online se retirará el 31 de julio de 2021 después de lo cual el servicio ya no será accesible.  Además, ya no se admite la conectividad RTC entre el entorno local mediante Skype Empresarial Server o Cloud Connector Edition y Skype Empresarial Online.  Obtenga información sobre cómo conectar la red de telefonía local a Teams mediante [enrutamiento directo](/MicrosoftTeams/direct-routing-landing-page).

## <a name="implications-of-the-upcoming-retirement-of-skype-for-business-online"></a>Implicaciones de la próxima retirada de Skype Empresarial Online
Es importante recordar que antes y después de la retirada de Skype Empresarial Online, los usuarios que se hospedaron en Skype Empresarial Server local pueden usar Teams, pero no pueden ser TeamsOnly. (De forma predeterminada, los usuarios están en modo Islas). Los usuarios solo pueden experimentar todas las ventajas de Teams, en particular la federación y la compatibilidad con RTC, una vez que estén en modo TeamsOnly. 

La próxima retirada de Skype Empresarial Online no tiene ningún impacto en el ciclo de vida de soporte técnico existente de Skype Empresarial Server o Lync Server 2013.  Sin embargo, la próxima retirada de Skype Empresarial Online afectará a ciertos apsects de cómo los clientes con Skype Empresarial Server local o Lync Server 2013, incluidas las organizaciones híbridas existentes, se transiciónn a la nube. Lo que no cambiará después de la retirada es que el uso de híbrido como medio para la transición de local a la nube permanece sin cambios.

Actualmente, y hasta la retirada de Skype Empresarial Online, las organizaciones híbridas pueden consistir en tres tipos básicos de usuarios: 
- Usuarios locales (que pueden o no usar Teams, pero no en modo Teams solo) 
- Usuarios en línea con cualquier modo de coexistencia distinto de TeamsOnly
- Usuarios de TeamsOnly.

Sin embargo, después de la retirada de Skype Empresarial Online, las organizaciones híbridas solo pueden consistir en dos tipos básicos de usuarios: 
- Usuarios locales (Quién o pueden usar Teams, pero no en modo TeamsOnly)
- Teams Solo usuarios. 

Para que las organizaciones pasen de Skype Empresarial Server o Lync Server 2013 a Teams, deben configurar y configurar híbridos con el mismo conjunto de *herramientas,* exactamente igual que antes de la retirada. Lo que ha cambiado es al mover un usuario de local a Teams, ya no es necesario especificar el cambio para mover usuarios directamente de local a `-MoveToTeams` `Move-CsUser` TeamsOnly. Anteriormente, si no se especificaba este modificador, los usuarios pasaron de hospedarse en Skype Empresarial Server local a Skype Empresarial Online y su modo permaneció sin cambios. En preparación para la retirada, al mover un usuario de local a la nube con , ahora los usuarios se asignan automáticamente al modo TeamsOnly y sus reuniones de locales se convierten automáticamente en reuniones de Teams, igual que si se hubiera especificado el modificador, independientemente de si el modificador se especifica `Move-CsUser` `-MoveToTeams` realmente. (Esto incluye las migraciones de Lync Server 2013, que nunca tuvieron el `MoveToTeams` modificador). 

Del mismo modo, si un nuevo usuario se crea directamente en Microsoft 365 en lugar de local, ese usuario tendrá automáticamente el modo solo Teams independientemente del modo del espacio empresarial. (Este comportamiento se implantará próximamente con la retirada). Tenga en cuenta que, en una organización híbrida, los nuevos usuarios deben crearse en Active Directory local (y, a continuación, sincronizarse en Microsoft 365), en lugar de crear directamente un usuario en Microsoft 365, para garantizar que los usuarios locales puedan enrutar al nuevo usuario.

Los modos de coexistencia seguirán existiendo después de la retirada de Skype Empresarial Online. Al igual que antes, a los usuarios con cuentas Skype Empresarial Server local se les puede asignar cualquier modo de coexistencia excepto TeamsOnly. Sin embargo, después de retirarse, los usuarios en línea solo pueden ser TeamsOnly (en contraste con el presente donde Skype Empresarial usuarios en línea pueden ser cualquier modo).  

> [!Important]
> - Las organizaciones híbridas existentes con usuarios que se encuentran en Skype Empresarial Online que no son TeamsOnly deben centrarse en actualizar estos usuarios al modo de solo Teams tan pronto como sea posible, pero no más tarde de la retirada el 31 de julio de 2021. Si su organización todavía tiene usuarios en Skype Empresarial Online que no son TeamsOnly, es posible que se programe una actualización asistido por Microsoft para realizar la transición de estos usuarios a TeamsOnly. Esto no afectará a los usuarios que se encuentran en Skype Empresarial Server local. Las notificaciones de programación se enviarán por adelantado a clientes híbridos con usuarios que se encuentran en Skype Empresarial Online antes de que estos usuarios que no sean de TeamsOnly se actualicen a Teams.
> - En preparación para la retirada de Skype Empresarial Online, pronto ya no será posible asignar un modo distinto de TeamsOnly a un usuario que esté conectado.

## <a name="about-shared-sip-address-space-functionality"></a>Acerca de la funcionalidad de espacio de direcciones SIP compartido

<a name="BKMK_Overview"> </a>

 Con la conectividad híbrida configurada entre una implementación local de Skype Empresarial Server y Teams o Skype Empresarial Online, puede tener algunos usuarios ubicados localmente y algunos usuarios en línea.

Este tipo de configuración se basa en la funcionalidad de espacio de direcciones SIP compartida y a veces se conoce como "dominio dividido", lo que significa que los usuarios de un dominio, como contoso.com, se dividen entre usar Skype Empresarial Server localmente y Teams o Skype Empresarial Online, como se muestra en el siguiente diagrama:

![Skype Empresarial Hybrid: dominio dividido](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

Cuando se configura el espacio de direcciones SIP compartido:

- Azure Active Directory Conectar se usa para sincronizar el directorio local con Microsoft 365 o Office 365.
- Los usuarios que se encuentran en una ubicación local interactúan con los servidores Skype Empresarial locales.
- Los usuarios que estén en línea pueden interactuar con Teams y, hasta el 31 de julio de 2021, Skype Empresarial Online en función de su modo de coexistencia.
- Los usuarios de ambos entornos pueden comunicarse entre sí.
- Active Directory local es autoritativo. Primero se deben crear todos los usuarios en Active Directory local y, a continuación, sincronizarse con Azure AD. Incluso si desea que el usuario esté en línea, primero debe crearlo en el entorno local y, a continuación, moverlo a línea para asegurarse de que los usuarios locales puedan detectarlo.

Para que un usuario pueda moverse en línea, se debe asignar al usuario una Teams licencia, así como Skype Empresarial online (plan 2). **La asignación de la Skype Empresarial online es necesaria incluso después de la retirada de Skype Empresarial Online.** Si los usuarios desean aprovechar las características en línea adicionales, como audioconferencia o Sistema telefónico, debe asignarles la licencia adecuada en Microsoft 365 o Office 365.

## <a name="hybrid-connectivity-infrastructure-requirements"></a>Requisitos de infraestructura de conectividad híbrida

<a name="BKMK_Infrastructure"> </a>

Para implementar la conectividad híbrida entre el entorno local y Microsoft 365 o Office 365 de comunicación, debe cumplir los siguientes requisitos de infraestructura:

- Una única implementación local de Skype Empresarial Server o Lync Server que se implementa en una topología compatible. Consulte [Requisitos de topología](plan-hybrid-connectivity.md#BKMK_Topology) en este tema.

- Una Microsoft 365 o Office 365 organización con Teams.
    > [!NOTE]
    > Solo puede usar un único espacio empresarial para una configuración híbrida con la implementación local.
    
- Azure Active Directory Conectar sincronizar el directorio local con Microsoft 365 o Office 365. Para obtener más información, vea [Azure AD Conectar: Cuentas y permisos](/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions).

- Skype Empresarial Server administrativas. Estos son necesarios para mover usuarios de local a la nube. Estas herramientas deben instalarse en un servidor con acceso a la implementación local y a Internet.
- Herramientas administrativas en línea. Puede usar el Centro de administración Teams o Windows PowerShell para administrar Teams y Skype Empresarial Online. Para usar PowerShell para administrar Teams o Skype Empresarial Online, descargue e instale el módulo Teams PowerShell. (El Skype Empresarial Online Connector se ha retirado).
- El espacio de direcciones SIP compartido debe estar habilitado y la implementación local debe configurarse para usar Microsoft 365 o Office 365 como proveedor de hospedaje. Para obtener más información acerca de los pasos necesarios para configurar la conectividad híbrida, vea [Configure hybrid connectivity](configure-hybrid-connectivity.md).

Después de configurar la conectividad híbrida, puede mover usuarios a Teams o Skype Empresarial Online. Para obtener más información, vea [Move users from on-premises to Teams](move-users-from-on-premises-to-teams.md) and Move users from on premises to Skype Empresarial [Online](move-users-from-on-premises-to-skype-for-business-online.md).

## <a name="server-version-requirements"></a>Requisitos de versión del servidor

<a name="BKMK_Topology"> </a>

Para configurar la implementación para híbrido con **Teams o Skype Empresarial Online,** debe tener una de las siguientes topologías admitidas:

- Una implementación de Skype Empresarial Server 2019 con todos los servidores que ejecuten Skype Empresarial Server 2019.
- Una implementación de Skype Empresarial Server 2015 con todos los servidores que ejecuten Skype Empresarial Server 2015.
- Una implementación de Lync Server 2013 con todos los servidores que ejecutan Lync Server 2013.  Sin embargo, si se requiere conectividad de voz híbrida, debe usar una topología de versión mixta como se indica a continuación.
- Una implementación con un máximo de 2 versiones de servidor diferentes, como se muestra a continuación:
  - Skype Empresarial Server 2015 y Skype Empresarial Server 2019
  - Lync Server 2013 y Skype Empresarial Server 2019
  - Lync Server 2013 y Skype Empresarial Server 2015

*Si se desea* una voz híbrida en cualquier topología, tanto el servidor perimetral designado como el servidor perimetral de federación como el grupo asociado a la federación SIP deben ejecutarse Skype Empresarial 2015 o posterior. Los usuarios pueden permanecer en un grupo de Lync 2013 si existe uno. Para obtener más información, [vea Plan Sistema telefónico with PSTN Connectivity in Skype Empresarial Server](../../SfbServer/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity.md).

Las siguientes topologías que incluyen **Lync Server 2010** se admiten con Skype Empresarial Online para mensajería instantánea y reuniones. Las topologías que **incluyen Lync Server 2010 no se** admiten para la voz híbrida ni para Teams .

- Una implementación mixta de Lync Server 2010 Skype Empresarial Server 2015
- Una implementación mixta de Lync Server 2010 y Lync Server 2013
- Una implementación de Lync Server 2010 con todos los servidores que ejecutan Lync Server 2010 con las actualizaciones acumulativas más recientes.

El servidor perimetral de federación y el servidor de próximo salto del servidor perimetral de federación deben ejecutar Lync Server 2010 con las actualizaciones acumulativas más recientes. Las Skype Empresarial Server 2015 o Lync Server 2013 Administrative Tools deben instalarse en al menos un servidor o estación de trabajo de administración.

## <a name="multi-forest-support"></a>Compatibilidad con varios bosques

<a name="BKMK_MultiForest"> </a>

Microsoft admite los siguientes tipos de escenarios híbridos de varios bosques:

- **Topología de bosque de recursos.** En este tipo de topología, hay un bosque que hospeda Skype Empresarial Server (el bosque de recursos) y hay uno o más bosques adicionales que hospedan identidades de cuenta, que tienen acceso a la Skype Empresarial Server en el bosque de recursos. En general, los usuarios pueden acceder Skype Empresarial funcionalidad de otro bosque si se cumplen los siguientes requisitos:
  - Los usuarios se sincronizan correctamente en el bosque que hospeda Skype Empresarial. En las configuraciones híbridas, esto significa que los usuarios deben sincronizarse como objetos de usuario deshabilitados.
  - El bosque que hospeda Skype Empresarial debe confiar en el bosque que contiene los usuarios.
    Para obtener información detallada sobre los escenarios híbridos del bosque de recursos, vea [Deploy a resource forest topology for hybrid Skype Empresarial](configure-a-multi-forest-environment-for-hybrid.md).

- **Varias implementaciones de Skype Empresarial Server en varios bosques.** Esta configuración puede surgir como resultado de escenarios de fusión y adquisición, así como en empresas más complejas. La consolidación de todos los usuarios locales a la nube en una única organización Microsoft 365 o Office 365 se puede lograr para cualquier organización con varias implementaciones de Skype Empresarial, siempre que se cumplen los siguientes requisitos clave:
  - Debe haber como máximo una Microsoft 365 o Office 365 organización implicada. No se admite la consolidación en escenarios con más de una organización.
  - En un momento dado, solo un bosque Skype Empresarial local puede estar en modo híbrido (espacio de direcciones SIP compartido). El resto de bosques Skype Empresarial locales deben permanecer completamente locales (y presumiblemente federados entre sí). Tenga en cuenta que estas otras organizaciones locales pueden sincronizarse con AAD si lo desean con nuevas funciones para deshabilitar los dominios [SIP](/powershell/module/skype/disable-csonlinesipdomain) en línea disponibles a partir de diciembre de 2018.

    Los clientes con implementaciones de Skype Empresarial en varios bosques deben migrar completamente cada bosque de Skype Empresarial individualmente a la organización de Microsoft 365 o Office 365 mediante la funcionalidad de dominio dividido (espacio de direcciones SIP compartido) y, a continuación, deshabilitar la implementación híbrida con la implementación local, antes de migrar la siguiente implementación Skype Empresarial local. Además, antes de migrarse a la nube, los usuarios locales permanecen en un estado federado con los usuarios que no están representados en el directorio local del mismo usuario. Para obtener más información, consulte [Consolidación de la nube para Teams y Skype Empresarial](cloud-consolidation.md).

## <a name="federation-requirements"></a>Requisitos de federación

<a name="BKMK_Federation"> </a>

Al configurar Skype Empresarial modo híbrido, debe asegurarse de que los entornos locales y en línea se puedan federar entre sí.  El entorno en línea tiene una federación abierta de forma predeterminada; el entorno local suele cerrar la federación de forma predeterminada.  

Se deben cumplir los siguientes requisitos para configurar correctamente una implementación híbrida:

- La coincidencia de dominios debe configurarse igual para la implementación local y para la Microsoft 365 o Office 365 organización. Si la detección de partners está habilitada en la implementación local, la federación abierta debe configurarse para la organización en línea. Si la detección de partners no está habilitada, la federación cerrada debe configurarse para la organización en línea.
- La lista dominios bloqueados en la implementación local debe coincidir exactamente con la lista dominios bloqueados para el inquilino en línea.
- La lista dominios permitidos en la implementación local debe coincidir exactamente con la lista dominios permitidos para el inquilino en línea.
- La federación debe estar habilitada para las comunicaciones externas del inquilino en línea.

## <a name="network-considerations"></a>Consideraciones relacionadas con la red

En las secciones siguientes se describen consideraciones para:

- Configuración dns
- Consideraciones de firewall

### <a name="dns-settings-for-hybrid-deployments"></a>Configuración de DNS para implementaciones híbridas

<a name="BKMK_DNS"> </a>

Al crear registros DNS para implementaciones híbridas, Skype Empresarial registros DNS externos deben apuntar a la infraestructura local. Para obtener información detallada sobre los registros DNS necesarios, consulte [los requisitos dns para Skype Empresarial Server](../../sfbserver/plan-your-deployment/network-requirements/dns.md).

Además, debe asegurarse de que la resolución DNS descrita en la siguiente tabla funciona en la implementación local. (Si ya configuró la federación para local, es muy probable que ya las tenga).

|Registro DNS  <br/> |Resolvable by  <br/> |Requisito de DNS  <br/> |
|:-----|:-----|:-----|
|Registro SRV dns para _sipfederationtls._tcp.\<sipdomain.com\> para todos los dominios SIP compatibles que se resuelven en IP externas perimetrales de acceso  <br/> |Servidores perimetrales  <br/> |Habilitar la comunicación federada en una configuración híbrida. El servidor perimetral debe saber dónde enrutar el tráfico federado para el dominio SIP dividido entre local y en línea.  <br/> Debe usar una coincidencia estricta del nombre DNS entre el dominio en el nombre de usuario y el registro SRV.  <br/> |
|Registros DNS A para EL FQDN del servicio de conferencia web perimetral, por ejemplo, webcon.contoso.com resolución en IP externas perimetrales de conferencia web  <br/> |Equipos de usuarios conectados a una red corporativa interna  <br/> |Permitir a los usuarios en línea presentar o ver contenido en reuniones hospedadas locales. El contenido PowerPoint archivos, pizarras, sondeos y notas compartidas.  <br/> |

En función de cómo se configure DNS en la organización, es posible que deba agregar estos registros a la zona DNS hospedada interna para los dominios SIP correspondientes para proporcionar una resolución de DNS interna a estos registros.

### <a name="firewall-considerations-for-hybrid-deployments"></a>Consideraciones de firewall para implementaciones híbridas

<a name="BKMK_Firewall"> </a>

Los equipos de la red deben ser capaces de realizar búsquedas de DNS de Internet estándar. Si estos equipos pueden tener acceso a sitios de Internet estándar, la red cumple este requisito.

Según la ubicación del centro de datos de Microsoft Online Services, también debe configurar los dispositivos de firewall de red para que acepten conexiones basadas en nombres de dominio comodín (por ejemplo, todo el tráfico de \* .outlook.com). Si los firewalls de su organización no admiten configuraciones de nombres comodín, tendrá que determinar manualmente los intervalos de direcciones IP que desea permitir y los puertos especificados.

Para obtener más información, incluidos los detalles sobre los puertos y los requisitos de protocolo, vea Microsoft 365 y Office 365 direcciones URL e [intervalos de direcciones IP](/microsoft-365/enterprise/urls-and-ip-address-ranges).
