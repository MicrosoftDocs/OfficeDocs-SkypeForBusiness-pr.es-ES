---
title: Planear la conexión híbrida | Skype empresarial Server 2019 y Microsoft 365 o Office 365 Integration
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
description: Consideraciones de planeación para implementar la conectividad híbrida entre Skype empresarial Server y Skype empresarial online o Teams.
ms.openlocfilehash: 3a7df5ef36a7d0e6bf58c1784edb0bbe0baa9409
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221280"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-microsoft-365-or-office-365"></a>Planeación de la conectividad híbrida entre Skype empresarial Server y Microsoft 365 u Office 365

## <a name="overview"></a>Información general

Lea este tema para obtener información sobre cómo planear la conectividad híbrida entre Skype empresarial Server y Microsoft Teams o Skype empresarial online. Configurar la conectividad híbrida es el primer paso para trasladar el entorno local a la nube.

Si tiene usuarios locales de Skype Empresarial que también usan Teams (en paralelo), estos usuarios no pueden interoperar con los usuarios de Skype Empresarial desde el cliente de Teams, ni comunicarse con los usuarios de las organizaciones federadas desde el cliente de Teams. Para obtener esta funcionalidad en Teams, estos usuarios deben trasladarse de Skype Empresarial local a la nube, lo que requiere configurar el modo híbrido de Skype Empresarial. Además, para obtener la mejor experiencia, estos usuarios deben estar en modo de solo Teams, lo que garantiza todas las llamadas entrantes y chats de los usuarios que se encuentren en el cliente de Microsoft Teams del usuario.

También hay que configurar la conectividad híbrida y trasladar a todos los usuarios a la nube antes de que se retire la implementación de Skype Empresarial local.  Con la configuración de conectividad híbrida, puede mover a los usuarios a la nube según la programación y sus necesidades empresariales. Con el enrutamiento directo, puede aprovechar su infraestructura de voz local mientras se desplaza a la nube y después de que se complete la migración.

En este tema se describen los requisitos del sistema y de la infraestructura que necesitará para configurar la conectividad híbrida entre su implementación local existente de Skype empresarial Server y Microsoft Teams o Skype empresarial online.

Una vez que haya leído este tema y esté listo para configurar la conectividad híbrida, vea [configurar la conectividad híbrida entre Skype empresarial Server y Microsoft 365 u Office 365](configure-hybrid-connectivity.md). Los temas de configuración proporcionan instrucciones paso a paso para configurar la conectividad híbrida entre su implementación local y Microsoft Teams o Skype empresarial online.

## <a name="about-shared-sip-address-space-functionality"></a>Acerca de la funcionalidad del espacio de direcciones SIP compartido

<a name="BKMK_Overview"> </a>

 Con la conectividad híbrida configurada entre una implementación local de Skype empresarial Server y Microsoft Teams o Skype empresarial online, puede tener algunos usuarios hospedados de forma local y otros usuarios alojados en línea.

Este tipo de configuración se basa en la funcionalidad del espacio de direcciones SIP compartido y a veces se denomina "dominio dividido", es decir, los usuarios de un dominio, como contoso.com, se dividen entre el uso de Skype empresarial Server local y Microsoft Teams o Skype empresarial online, tal como se muestra en el siguiente diagrama:

![Conectividad híbrida de SfB: dominio dividido](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

Cuando se configura el espacio de direcciones SIP compartido:

- Azure Active Directory Connect se usa para sincronizar su directorio local con Microsoft 365 u Office 365.
- Los usuarios hospedados en locales interactúan con los servidores locales de Skype empresarial.
- Los usuarios hospedados en línea pueden interactuar con Skype empresarial online o servicios de Microsoft Teams.
- Los usuarios de ambos entornos pueden comunicarse entre sí.
- La implementación local de Active Directory tiene autorización. Todos los usuarios deben crearse primero en Active Directory local y, a continuación, sincronizarse con Azure AD. Incluso si tiene previsto que el usuario se pueda hospedar en línea, primero debe crear el usuario en el entorno local y, a continuación, mover el usuario a en línea para asegurarse de que el usuario lo pueda detectar a los usuarios locales.

Para que un usuario pueda moverse en línea, el usuario debe tener asignada una licencia de Skype empresarial online (plan 2). Si el usuario va a usar Teams, el usuario también debe tener asignada una licencia de Teams (y la licencia de Skype empresarial debe permanecer habilitada). Si los usuarios quieren aprovechar las características en línea adicionales, como la audioconferencia o el sistema telefónico, debe asignarles la licencia correspondiente en Microsoft 365 u Office 365.

## <a name="infrastructure-requirements"></a>Requisitos previos de infraestructura

<a name="BKMK_Infrastructure"> </a>

Para implementar la conectividad híbrida entre su entorno local y los servicios de comunicación de Microsoft 365 u Office 365, debe cumplir con los siguientes requisitos de infraestructura:

- Una única implementación local de Skype empresarial Server o Lync Server que se implementa en una topología compatible. Vea [requisitos](plan-hybrid-connectivity.md#BKMK_Topology) de la topología en este tema.

- Una organización de Microsoft 365 u Office 365 con Skype empresarial online habilitado.
    > [!NOTE]
    > Solo puede usar un inquilino para una configuración híbrida con su implementación local.
    
- Azure Active Directory Connect para sincronizar su directorio local con Microsoft 365 u Office 365. Para obtener más información, consulte [Azure ad Connect: accounts and Permissions](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions).

- Herramientas administrativas de Skype empresarial Server.  Son necesarios para mover usuarios de local a la nube. Estas herramientas deben instalarse en un servidor con acceso a la implementación local e Internet.
- Herramientas administrativas en línea.  Puede usar tanto el centro de administración de Microsoft Teams como Windows PowerShell para administrar Teams y Skype empresarial online. Para usar PowerShell para administrar Teams o Skype empresarial online, descargue e instale el conector de Skype empresarial online.
- El espacio de direcciones SIP compartido debe estar habilitado y la implementación local debe estar configurada para usar Microsoft 365 u Office 365 como proveedor de hospedaje. Para obtener más información acerca de los pasos necesarios para configurar la conectividad híbrida, vea [Configure Hybrid Connectivity](configure-hybrid-connectivity.md).

Después de configurar la conectividad híbrida, puede mover usuarios a Microsoft Teams o Skype empresarial online. Para obtener más información, consulte [Move users on-premises to Teams](move-users-from-on-premises-to-teams.md) y [Move users on local to Skype for Business online](move-users-from-on-premises-to-skype-for-business-online.md).

## <a name="server-version-requirements"></a>Requisitos de la versión del servidor

<a name="BKMK_Topology"> </a>

Para configurar la implementación de en entornos híbridos con Microsoft **Teams o Skype empresarial online**, debe disponer de una de las siguientes topologías admitidas:

- Una implementación de Skype empresarial Server 2019 con todos los servidores que ejecutan Skype empresarial Server 2019.
- Una implementación de Skype empresarial Server 2015 con todos los servidores que ejecutan Skype empresarial Server 2015.
- Una implementación de Lync Server 2013 con todos los servidores que ejecutan Lync Server 2013.  Sin embargo, si se requiere conectividad de voz híbrida, debe usar una topología de versión mixta como se indica a continuación.
- Una implementación con un máximo de 2 versiones de servidor diferentes, como se indica a continuación:
  - Skype empresarial Server 2015 y Skype empresarial Server 2019
  - Lync Server 2013 y Skype empresarial Server 2019
  - Lync Server 2013 y Skype empresarial Server 2015

*Si se desea utilizar la voz híbrida en una topología*, tanto el servidor perimetral designado como el perímetro de la Federación como el grupo de servidores asociado con la Federación SIP deben ejecutar Skype empresarial 2015 o posterior. Los usuarios pueden permanecer en un grupo de servidores de Lync 2013 si existe alguno. Para obtener más información, consulte [plan Phone System with RTC Connectivity in Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity).

Las siguientes topologías, que incluyen **Lync Server 2010, son compatibles con Skype empresarial online** para la mensajería instantánea y las reuniones.  Las topologías que incluyen **Lync Server 2010 no son compatibles con la voz híbrida ni con los equipos**.

- Una implementación mixta de Lync Server 2010 y Skype empresarial Server 2015
- Una implementación mixta de Lync Server 2010 y Lync Server 2013
- Una implementación de Lync Server 2010 con todos los servidores que ejecutan Lync Server 2010 con las actualizaciones acumulativas más recientes.

El servidor perimetral de Federación y el servidor de próximo salto del servidor perimetral de Federación deben ejecutar Lync Server 2010 con las actualizaciones acumulativas más recientes. Las herramientas administrativas de Skype empresarial Server 2015 o Lync Server 2013 deben instalarse en al menos un servidor o una estación de trabajo de administración.

## <a name="multi-forest-support"></a>Compatibilidad con varios bosques

<a name="BKMK_MultiForest"> </a>

Microsoft admite los siguientes tipos de escenarios híbridos de varios bosques:

- **Topología de bosque de recursos.** En este tipo de topología, hay un bosque que hospeda Skype empresarial Server (el bosque de recursos) y hay uno o más bosques adicionales que hospedan identidades de cuentas, que tienen acceso a Skype empresarial Server en el bosque de recursos. En general, los usuarios pueden tener acceso a la funcionalidad de Skype empresarial en otro bosque si se cumplen los siguientes requisitos:
  - Los usuarios se sincronizan correctamente en el bosque que hospeda Skype empresarial. En las configuraciones híbridas, esto significa que los usuarios deben estar sincronizados como objetos de usuario deshabilitados.
  - El bosque que hospeda Skype empresarial debe confiar en el bosque que contiene los usuarios.
    Para obtener información detallada sobre los escenarios híbridos de bosque de recursos, vea [deploy a Resource Forest Topology for Hybrid Skype for Business](configure-a-multi-forest-environment-for-hybrid.md).

- **Varias implementaciones de Skype Empresarial Server en varios bosques.** Esta configuración puede producirse como resultado de los escenarios de fusión y adquisición, así como en empresas más complejas. Se puede consolidar a todos los usuarios de forma local en la nube en una sola organización de Microsoft 365 u Office 365 para cualquier organización con varias implementaciones de Skype empresarial, siempre que se cumplan los siguientes requisitos clave:
  - Debe haber una organización de Microsoft 365 u Office 365 como máximo implicado. No se admite la consolidación en escenarios con más de una organización.
  - En cualquier momento dado, solo un bosque de Skype empresarial local puede estar en modo híbrido (espacio de direcciones SIP compartido). Todos los demás bosques locales de Skype empresarial deben permanecer completamente locales (y supuestamente federados entre sí). Tenga en cuenta que estas organizaciones locales pueden sincronizarse con AAD si lo desea, con [nuevas funciones para deshabilitar los dominios SIP en línea](https://docs.microsoft.com/powershell/module/skype/disable-csonlinesipdomain) disponibles a partir de diciembre de 2018.

    Los clientes con implementaciones de Skype empresarial en varios bosques deben migrar completamente cada bosque de Skype empresarial a la organización de Microsoft 365 u Office 365 mediante la funcionalidad de dominio dividido (espacio de direcciones SIP compartido) y, a continuación, deshabilitar la implementación híbrida con la implementación local antes de continuar para migrar la siguiente implementación local de Skype empresarial. Además, antes de migrar a la nube, los usuarios locales permanecen en un estado federado con los usuarios que no están representados en el directorio local del mismo usuario. Para obtener más información, consulte [consolidación en la nube para Teams y Skype empresarial](cloud-consolidation.md).

## <a name="federation-requirements"></a>Requisitos de Federación

<a name="BKMK_Federation"> </a>

Al configurar una implementación híbrida, debe asegurarse de que los entornos locales y en línea puedan federarse entre sí.  El entorno en línea tiene una federación abierta de forma predeterminada; el entorno local suele tener la Federación cerrada de forma predeterminada.  

Se deben cumplir los siguientes requisitos para configurar correctamente una implementación híbrida:

- La coincidencia de dominios debe configurarse de la misma manera para la implementación local y la organización de Microsoft 365 u Office 365. Si la detección de asociados está habilitada en la implementación local, se debe configurar la Federación abierta para la organización en línea. Si la detección de asociados no está habilitada, la Federación cerrada debe estar configurada para la organización en línea.
- La lista de dominios bloqueados en la implementación local debe coincidir exactamente con la lista de dominios bloqueados del inquilino en línea.
- La lista de dominios permitidos de la implementación local debe coincidir exactamente con la lista de dominios permitidos del inquilino en línea.
- La Federación debe estar habilitada para las comunicaciones externas del inquilino en línea.

## <a name="network-considerations"></a>Consideraciones relacionadas con la red

En las secciones siguientes se describen las consideraciones para:

- Configuración de DNS
- Consideraciones sobre el Firewall

### <a name="dns-settings"></a>Configuración de DNS

<a name="BKMK_DNS"> </a>

Al crear registros DNS para implementaciones híbridas, todos los registros DNS externos de Skype empresarial deben apuntar a la infraestructura local. Para obtener más información sobre los registros DNS necesarios, consulte [DNS Requirements for Skype for Business Server](../../sfbserver/plan-your-deployment/network-requirements/dns.md).

Además, debe asegurarse de que la resolución DNS que se describe en la tabla siguiente funciona en su implementación local. (Si ya configuró la Federación para local, probablemente ya tenga estas).

|Registro DNS  <br/> |Resuelto por  <br/> |Requisito de DNS  <br/> |
|:-----|:-----|:-----|
|Registro SRV de DNS para _sipfederationtls. _tcp. \< sipdomain.com \> para todos los dominios SIP compatibles que se resuelven para obtener acceso a las IP externas perimetrales  <br/> |Servidor (es) perimetral  <br/> |Habilitar la comunicación federada en una configuración híbrida. El servidor perimetral tiene que saber dónde enrutar el tráfico federado para el dominio SIP que se divide entre las instalaciones locales y en línea.  <br/> Debe usar una coincidencia de nombres DNS estricta entre el dominio del nombre de usuario y el registro SRV.  <br/> |
|Registros A de DNS para el FQDN del servicio de conferencia web perimetral, por ejemplo, webcon.contoso.com para la resolución de direcciones IP externas del servidor perimetral de conferencia Web  <br/> |Equipos de usuarios conectados a la red corporativa interna  <br/> |Permitir que los usuarios en línea presenten o vean contenido en las reuniones hospedadas locales. El contenido incluye archivos de PowerPoint, pizarras, sondeos y notas compartidas.  <br/> |

En función de la configuración de DNS en la organización, es posible que deba agregar estos registros a la zona DNS hospedada interna para los dominios SIP correspondientes para proporcionar resolución DNS interna a estos registros.

### <a name="firewall-considerations"></a>Consideraciones sobre el Firewall

<a name="BKMK_Firewall"> </a>

Los equipos de la red deben ser capaces de realizar búsquedas de DNS de Internet estándar. Si estos equipos pueden tener acceso a sitios de Internet estándar, la red cumple este requisito.

En función de la ubicación del centro de datos de Microsoft Online Services, también debe configurar los dispositivos de Firewall de red para que acepten conexiones basadas en nombres de dominio comodín (por ejemplo, todo el tráfico de \* . Outlook.com). Si los firewalls de su organización no admiten configuraciones de nombre comodín, tendrá que determinar manualmente los intervalos de direcciones IP que desea permitir y los puertos especificados.

Para obtener más información, incluidos los detalles sobre los requisitos de protocolo y puertos, consulte [Microsoft 365 y Office 365 URL e intervalos de direcciones IP](https://go.microsoft.com/fwlink/p/?LinkId=252942).
