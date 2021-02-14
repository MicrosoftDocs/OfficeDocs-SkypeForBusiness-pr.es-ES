---
title: Planear la conexión híbrida | Integración de Skype Empresarial Server 2019 y Microsoft 365 u Office 365
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
description: Planee implementar la conectividad híbrida entre Skype Empresarial Server y Teams o Skype Empresarial Online mediante la configuración del modo híbrido de Skype Empresarial.
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: 856172d5fba3df96b2456f0ceca1c661120e84e4
ms.sourcegitcommit: 43dc627e9fef31a2508f54acf741000551ff68b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2020
ms.locfileid: "48878586"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-microsoft-365-or-office-365"></a>Planear la conectividad híbrida entre Skype Empresarial Server y Microsoft 365 u Office 365

Lea este tema para obtener información sobre cómo planear la conectividad híbrida entre Skype Empresarial Server y Teams o Skype Empresarial Online. Configurar la conectividad híbrida es el primer paso para trasladar el entorno local a la nube.

Si tiene usuarios locales de Skype Empresarial que también usan Teams (en paralelo), estos usuarios no pueden interoperar con los usuarios de Skype Empresarial desde el cliente de Teams, ni comunicarse con los usuarios de las organizaciones federadas desde el cliente de Teams. Para obtener esta funcionalidad en Teams, estos usuarios deben trasladarse de Skype Empresarial local a la nube, lo que requiere configurar el modo híbrido de Skype Empresarial. Además, para obtener la mejor experiencia, estos usuarios deben estar en modo solo de Teams, lo que garantiza que todas las llamadas entrantes y chats de cualquier usuario aterrice en el cliente de Teams del usuario.

También hay que configurar la conectividad híbrida y trasladar a todos los usuarios a la nube antes de que se retire la implementación de Skype Empresarial local.  Con la configuración de conectividad híbrida, puede mover a los usuarios a la nube según la programación y sus necesidades empresariales. Con el enrutamiento directo, puede aprovechar su infraestructura de voz local mientras se desplaza a la nube y después de que se complete la migración.

En este tema se describen los requisitos del sistema y la infraestructura que necesitará para configurar la conectividad híbrida entre la implementación local de Skype Empresarial Server existente y Teams o Skype Empresarial Online.

Cuando haya leído este tema y esté listo para configurar la conectividad híbrida, consulte Configurar la conectividad híbrida entre Skype Empresarial Server y [Microsoft 365 u Office 365.](configure-hybrid-connectivity.md) Los temas de configuración proporcionan instrucciones paso a paso para configurar la conectividad híbrida entre su implementación local y Teams o Skype Empresarial Online.

> [!Important]
> Skype Empresarial Online se retirará el 31 de julio de 2021, tras lo cual el servicio ya no será accesible.  Además, ya no se admite la conectividad rtc entre su entorno local, ya sea a través de Skype Empresarial Server o Cloud Connector Edition y Skype Empresarial Online.  Obtenga información sobre cómo conectar la red de telefonía local a Teams mediante [enrutamiento directo.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

## <a name="about-shared-sip-address-space-functionality"></a>Acerca de la funcionalidad de espacio de direcciones SIP compartido

<a name="BKMK_Overview"> </a>

 Con la conectividad híbrida configurada entre una implementación local de Skype Empresarial Server y Teams o Skype Empresarial Online, puede tener algunos usuarios locales y algunos usuarios en línea.

Este tipo de configuración se basa en la funcionalidad de espacio de direcciones SIP compartida y, a veces, se conoce como "dominio dividido", lo que significa que los usuarios de un dominio, como contoso.com, se dividen entre usar Skype Empresarial Server local y Teams o Skype Empresarial Online, como se muestra en el siguiente diagrama:

![Conectividad híbrida de Skype Empresarial: dominio dividido](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

Cuando se configura el espacio de direcciones SIP compartido:

- Azure Active Directory Connect se usa para sincronizar el directorio local con Microsoft 365 u Office 365.
- Los usuarios que están internos interactúan con los servidores locales de Skype Empresarial.
- Los usuarios que están en línea pueden interactuar con los servicios de Skype Empresarial Online o Teams.
- Los usuarios de ambos entornos pueden comunicarse entre sí.
- Active Directory local es autoritativo. Todos los usuarios deben crearse primero en Active Directory local y, a continuación, sincronizarse con Azure AD. Incluso si desea que el usuario esté conectado, primero debe crear el usuario en el entorno local y, a continuación, mover el usuario a línea para asegurarse de que los usuarios locales puedan detectarlo.

Antes de que un usuario pueda moverse en línea, se le debe asignar una licencia de Skype Empresarial Online (Plan 2). Si el usuario va a usar Teams, también se le debe asignar una licencia de Teams (y la licencia de Skype Empresarial debe permanecer habilitada). Si los usuarios quieren aprovechar las características en línea adicionales, como Audioconferencia o Sistema telefónico, debe asignarles la licencia adecuada en Microsoft 365 u Office 365.

## <a name="hybrid-connectivity-infrastructure-requirements"></a>Requisitos de infraestructura de conectividad híbrida

<a name="BKMK_Infrastructure"> </a>

Para implementar la conectividad híbrida entre el entorno local y los servicios de comunicación de Microsoft 365 u Office 365, debe cumplir los siguientes requisitos de infraestructura:

- Una única implementación local de Skype Empresarial Server o Lync Server que se implementa en una topología compatible. Consulte [los requisitos de topología](plan-hybrid-connectivity.md#BKMK_Topology) en este tema.

- Una organización de Microsoft 365 u Office 365 con Skype Empresarial Online habilitado.
    > [!NOTE]
    > Solo puede usar un único inquilino para una configuración híbrida con la implementación local.
    
- Azure Active Directory Connect para sincronizar el directorio local con Microsoft 365 u Office 365. Para obtener más información, [vea Azure AD Connect: cuentas y permisos.](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions)

- Herramientas administrativas de Skype Empresarial Server. Estos son necesarios para mover usuarios de local a la nube. Estas herramientas deben instalarse en un servidor con acceso a la implementación local y a Internet.
- Herramientas administrativas en línea. Puede usar el Centro de administración de Teams o Windows PowerShell para administrar Teams y Skype Empresarial Online. Para usar PowerShell para administrar Teams o Skype Empresarial Online, descargue e instale el conector de Skype Empresarial Online.
- El espacio de direcciones SIP compartido debe estar habilitado y la implementación local debe configurarse para usar Microsoft 365 u Office 365 como proveedor de hospedaje. Para obtener más información acerca de los pasos necesarios para configurar la conectividad híbrida, vea [Configurar la conectividad híbrida.](configure-hybrid-connectivity.md)

Después de configurar la conectividad híbrida, puede mover usuarios a Teams o Skype Empresarial Online. Para obtener más información, vea [Mover usuarios de](move-users-from-on-premises-to-teams.md) local a Teams y Mover usuarios de local a Skype Empresarial [Online.](move-users-from-on-premises-to-skype-for-business-online.md)

## <a name="server-version-requirements"></a>Requisitos de versión del servidor

<a name="BKMK_Topology"> </a>

Para configurar la implementación híbrida con Teams o **Skype Empresarial Online,** debe tener una de las siguientes topologías admitidas:

- Una implementación de Skype Empresarial Server 2019 con todos los servidores que ejecuten Skype Empresarial Server 2019.
- Una implementación de Skype Empresarial Server 2015 con todos los servidores que ejecuten Skype Empresarial Server 2015.
- Una implementación de Lync Server 2013 con todos los servidores que ejecutan Lync Server 2013.  Sin embargo, si se requiere conectividad de voz híbrida, debe usar una topología de versión mixta como se indica a continuación.
- Una implementación con un máximo de 2 versiones de servidor diferentes, como se muestra a continuación:
  - Skype Empresarial Server 2015 y Skype Empresarial Server 2019
  - Lync Server 2013 y Skype Empresarial Server 2019
  - Lync Server 2013 y Skype Empresarial Server 2015

Si se desea una voz híbrida en cualquier *topología,* tanto el servidor perimetral designado como el servidor perimetral de federación como el grupo asociado con la federación SIP deben ejecutar Skype Empresarial 2015 o posterior. Los usuarios pueden permanecer en un grupo de Lync 2013 si existe alguno. Para obtener más información, consulte [Plan Phone System with PSTN Connectivity in Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity).

Las siguientes topologías que incluyen **Lync Server 2010** son compatibles con Skype Empresarial Online para mensajería instantánea y reuniones. Las topologías que **incluyen Lync Server 2010 no son** compatibles con la voz híbrida ni teams.

- Una implementación mixta de Lync Server 2010 y Skype Empresarial Server 2015
- Una implementación mixta de Lync Server 2010 y Lync Server 2013
- Una implementación de Lync Server 2010 con todos los servidores que ejecutan Lync Server 2010 con las últimas actualizaciones acumulativas.

El servidor perimetral de federación y el servidor del próximo salto del servidor perimetral de federación deben ejecutar Lync Server 2010 con las actualizaciones acumulativas más recientes. Las herramientas administrativas de Skype Empresarial Server 2015 o Lync Server 2013 deben instalarse en al menos un servidor o estación de trabajo de administración.

## <a name="multi-forest-support"></a>Compatibilidad con varios bosques

<a name="BKMK_MultiForest"> </a>

Microsoft admite los siguientes tipos de escenarios híbridos de varios bosques:

- **Topología de bosque de recursos.** En este tipo de topología, hay un bosque que hospeda Skype Empresarial Server (el bosque de recursos) y hay uno o más bosques adicionales que hospedan identidades de cuenta, que tienen acceso a Skype Empresarial Server en el bosque de recursos. En general, los usuarios pueden acceder a la funcionalidad de Skype Empresarial en otro bosque si se cumplen los siguientes requisitos:
  - Los usuarios se sincronizan correctamente en el bosque que hospeda Skype Empresarial. En las configuraciones híbridas, esto significa que los usuarios deben sincronizarse como objetos de usuario deshabilitados.
  - El bosque que hospeda Skype Empresarial debe confiar en el bosque que contiene los usuarios.
    Para obtener información detallada sobre los escenarios híbridos de bosque de recursos, consulte Implementar una topología de bosque de [recursos para Skype Empresarial híbrido.](configure-a-multi-forest-environment-for-hybrid.md)

- **Varias implementaciones de Skype Empresarial Server en varios bosques.** Esta configuración puede surgir como resultado de escenarios de fusión y adquisición, así como en empresas más complejas. La consolidación de todos los usuarios desde local a la nube en una sola organización de Microsoft 365 u Office 365 se puede lograr para cualquier organización con varias implementaciones de Skype Empresarial, siempre que se cumplen los siguientes requisitos clave:
  - Debe haber como máximo una organización de Microsoft 365 u Office 365 involucrada. No se admite la consolidación en escenarios con más de una organización.
  - En cualquier momento, solo un bosque local de Skype Empresarial puede estar en modo híbrido (espacio de direcciones SIP compartido). Todos los demás bosques locales de Skype Empresarial deben permanecer completamente locales (y presumiblemente federados entre sí). Tenga en cuenta que estas otras organizaciones locales pueden sincronizarse con AAD si lo desean con una nueva funcionalidad para deshabilitar los dominios [SIP](https://docs.microsoft.com/powershell/module/skype/disable-csonlinesipdomain) en línea disponibles a partir de diciembre de 2018.

    Los clientes con implementaciones de Skype Empresarial en varios bosques deben migrar por completo cada bosque de Skype Empresarial individualmente a la organización de Microsoft 365 u Office 365 mediante la funcionalidad de dominio dividido (espacio de direcciones SIP compartido) y, a continuación, deshabilitar la implementación híbrida con la implementación local, antes de pasar a migrar la siguiente implementación local de Skype Empresarial. Además, antes de migrar a la nube, los usuarios locales permanecen en un estado federado con los usuarios que no están representados en el directorio local del mismo usuario. Para obtener más información, consulte [Consolidación de la nube para Teams y Skype Empresarial.](cloud-consolidation.md)

## <a name="federation-requirements"></a>Requisitos de federación

<a name="BKMK_Federation"> </a>

Al configurar el modo híbrido de Skype Empresarial, debe asegurarse de que los entornos locales y en línea se puedan federar entre sí.  El entorno en línea tiene una federación abierta de forma predeterminada; El entorno local suele tener una federación cerrada de forma predeterminada.  

Se deben cumplir los siguientes requisitos para configurar correctamente una implementación híbrida:

- La coincidencia de dominios debe configurarse igual para su implementación local y su organización de Microsoft 365 u Office 365. Si la detección de asociados está habilitada en la implementación local, la federación abierta debe configurarse para la organización en línea. Si la detección de asociados no está habilitada, la federación cerrada debe configurarse para la organización en línea.
- La lista de dominios bloqueados en la implementación local debe coincidir exactamente con la lista de dominios bloqueados de su inquilino en línea.
- La lista de dominios permitidos en la implementación local debe coincidir exactamente con la lista de dominios permitidos de su inquilino en línea.
- La federación debe estar habilitada para las comunicaciones externas para el inquilino en línea.

## <a name="network-considerations"></a>Consideraciones relacionadas con la red

En las secciones siguientes se describen las consideraciones para:

- Configuración dns
- Consideraciones de firewall

### <a name="dns-settings-for-hybrid-deployments"></a>Configuración de DNS para implementaciones híbridas

<a name="BKMK_DNS"> </a>

Al crear registros DNS para implementaciones híbridas, todos los registros DNS externos de Skype Empresarial deben apuntar a la infraestructura local. Para obtener más información sobre los registros DNS necesarios, consulte los [requisitos dns para Skype Empresarial Server.](../../sfbserver/plan-your-deployment/network-requirements/dns.md)

Además, debe asegurarse de que la resolución DNS descrita en la tabla siguiente funciona en la implementación local. (Si ya configuró la federación para el entorno local, lo más probable es que ya los tenga).

|Registro DNS  <br/> |Se puede resolver mediante  <br/> |Requisito de DNS  <br/> |
|:-----|:-----|:-----|
|Registro SRV de DNS para _sipfederationtls._tcp.\<sipdomain.com\> para todos los dominios SIP compatibles que se resuelven en DIRECCIONES IP externas perimetrales de acceso  <br/> |Servidores perimetrales  <br/> |Habilitar la comunicación federada en una configuración híbrida. El servidor perimetral debe saber dónde enrutar el tráfico federado para el dominio SIP que se divide entre local y en línea.  <br/> Debe usar una coincidencia estricta de nombre DNS entre el dominio en el nombre de usuario y el registro SRV.  <br/> |
|Registros A de DNS para EL FQDN del servicio de conferencia web perimetral, por ejemplo, webcon.contoso.com a IP externas del servidor perimetral de conferencia web  <br/> |Equipos de usuarios conectados a la red corporativa interna  <br/> |Permitir a los usuarios en línea presentar o ver contenido en reuniones hospedadas localmente. El contenido incluye archivos de PowerPoint, pizarras, sondeos y notas compartidas.  <br/> |

En función de cómo se configure DNS en su organización, es posible que tenga que agregar estos registros a la zona DNS hospedada interna para los dominios SIP correspondientes para proporcionar resolución DNS interna a estos registros.

### <a name="firewall-considerations-for-hybrid-deployments"></a>Consideraciones de firewall para implementaciones híbridas

<a name="BKMK_Firewall"> </a>

Los equipos de la red deben ser capaces de realizar búsquedas de DNS de Internet estándar. Si estos equipos pueden tener acceso a sitios de Internet estándar, la red cumple este requisito.

Según la ubicación del centro de datos de Microsoft Online Services, también debe configurar los dispositivos de firewall de red para que acepten conexiones basadas en nombres de dominio comodín (por ejemplo, todo el tráfico de \* .outlook.com). Si los firewalls de su organización no admiten configuraciones de nombres comodín, tendrá que determinar manualmente los intervalos de direcciones IP que desea permitir y los puertos especificados.

Para obtener más información, incluidos los detalles sobre los puertos y los requisitos de protocolo, vea direcciones URL e intervalos de direcciones IP de [Microsoft 365 y Office 365.](https://go.microsoft.com/fwlink/p/?LinkId=252942)
