---
title: Plan híbrida conectar | Skype para la integración de Business Server 2019 Office 365
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Consideraciones de planeación para implementar la conectividad de híbrida entre Skype para Business Server y Skype para profesionales en línea o los equipos.
ms.openlocfilehash: ca6fce658443cd100cc03b14730dac722337733d
ms.sourcegitcommit: 716d39077784417c3545a91e501ae26ff56ebdf4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2019
ms.locfileid: "29348947"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-office-365"></a>Planeación de la conectividad híbrida entre Skype para Business Server y Office 365

## <a name="overview"></a>Información general

Lea este tema para obtener información sobre cómo planear la conectividad híbrida entre Skype para Business Server y los equipos o Skype para profesionales en línea. Configurar conectividad híbrida es el primer paso para mover el entorno local a la nube.

Si dispone de Skype local para los usuarios de negocios que también está usando los equipos (en paralelo), los usuarios no tienen la capacidad de interoperar con Skype para los usuarios de negocio de su cliente de los equipos, ni comunicarse con los usuarios de organizaciones federadas, desde sus Cliente de los equipos. Para obtener esta funcionalidad en los equipos, estos usuarios se deben mover de Skype para empresarial local a la nube, que requiere la configuración de Skype para modo híbrido de negocio. Además, para la mejor experiencia, estos usuarios deben en modo sólo los equipos, lo que asegura que todas las llamadas entrantes y charlas desde cualquier land de usuario en el cliente de los equipos del usuario.

Configurar conectividad híbrida y mover todos los usuarios a la nube también se requiere antes de retirar su Skype local para la implementación de la empresa.  Con conectividad híbrida configurar, puede elegir mover los usuarios a la nube en función de sus necesidades de negocio y programación. Con el enrutamiento directo, puede aprovechar la infraestructura de voz local mientras se mueve a la nube y una vez finalizada la migración.

En este tema se describe la infraestructura y los requisitos del sistema que necesitará para configurar la conectividad híbrida entre la existente local Skype para la implementación de Business Server y los equipos o Skype para profesionales en línea.

Una vez leído este tema y esté listo para configurar la conectividad híbrida, vea [Configurar la conectividad híbrida entre Skype para Business Server y Office 365](configure-hybrid-connectivity.md). Los temas de configuración proporcionan instrucciones paso a paso para la configuración de conectividad híbrida entre su implementación local y los equipos o Skype para el negocio en línea.

## <a name="about-shared-sip-address-space-functionality"></a>Acerca de las funciones Shared espacio de direcciones SIP

<a name="BKMK_Overview"> </a>

 Con conectividad híbrida configurar entre una implementación local de Skype para Business Server y los equipos o Skype para profesionales en línea, puede tener algunos usuarios alojarse en local y algunos usuarios alojados en línea.

Este tipo de configuración se basa en la funcionalidad de espacio de direcciones SIP compartida y, a veces se conoce como "dominio dividido--" lo que significa que los usuarios de un dominio, como contoso.com, se reparten entre el uso de Skype para Business Server en local y los equipos o Skype para la empresa En línea, como se muestra en el siguiente diagrama:

![Conectividad híbrida de SfB: dominio dividido](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

Cuando se configura el espacio de direcciones SIP compartido:

- Azure Active Directory conectar se usa para sincronizar el directorio local con Office 365.
- Los usuarios que están hospedados en local interactúan con Skype local para servidores empresariales.
- Los usuarios que están hospedados en línea pueden interactuar con Skype para los servicios en línea de negocio o los equipos.
- Los usuarios de ambos entornos pueden comunicarse entre sí.
- Active Directory local está autorizado. Todos los usuarios deben crearse en el Active Directory local en primer lugar y, a continuación, se sincronizan con Azure AD. Incluso si piensa para que el usuario a estar alojado en línea, debe crear primero el usuario en el entorno local y, a continuación, mover el usuario a en línea para asegurarse de que el usuario es reconocible por los usuarios locales.

Antes de que un usuario se puede mover en línea, el usuario debe estar asignado un Skype para licencia empresarial Online (Plan 2). Si el usuario va a utilizar los equipos, el usuario también debe tener una licencia de los equipos (y la Skype para licencia de negocio debe permanecer habilitado). Si desean que los usuarios aprovechar las características en línea adicionales, como conferencias de Audio o el sistema de teléfono, necesita asignarlas la licencia correspondiente en Office 365.

## <a name="infrastructure-requirements"></a>Requisitos de infraestructura

<a name="BKMK_Infrastructure"> </a>

Para implementar la conectividad híbrida entre su entorno local y los servicios de comunicación de Office 365, debe cumplir los siguientes requisitos de infraestructura:

- Una única implementación local de Skype para Business Server o Lync Server que se haya implementado en una topología admitida. En este tema, vea [requisitos de la topología](plan-hybrid-connectivity.md#BKMK_Topology) .
- Un inquilino de Microsoft Office 365 con Skype para profesionales Online habilitado.
    > [!NOTE]
    > Solo puede usar un inquilino para una configuración híbrida con su implementación local.
- Azure Active Directory Connect para sincronizar su directorio local con Office 365. Para obtener más información, vea [Azure Connect AD: permisos y cuentas de](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions).
- Skype para herramientas administrativas de Business Server.  Son necesarios para mover usuarios de local a la nube. Estas herramientas deben estar instaladas en un servidor con acceso a la implementación local e internet.
- Herramientas administrativas en línea.  Puede usar los equipos y la Skype para el centro de administración de negocio o Windows PowerShell para administrar los equipos y Skype para profesionales en línea. Para usar PowerShell para administrar los equipos o Skype para profesionales en línea, descargue e instale el Skype para Business Connector en línea.
- Espacio de direcciones SIP compartido debe estar habilitada y la implementación local debe configurarse para usar Office 365 como un proveedor de hospedaje. Para obtener más información acerca de los pasos necesarios para configurar la conectividad híbrida, vea [Configurar la conectividad de híbrida](configure-hybrid-connectivity.md).

Después de configurar la conectividad híbrida, puede mover los usuarios a los equipos o Skype para profesionales en línea. Para obtener más información, vea [mover usuarios de local a los equipos](move-users-from-on-premises-to-teams.md) y [mover los usuarios de local a Skype para profesionales en línea](move-users-from-on-premises-to-skype-for-business-online.md).

## <a name="server-version-requirements"></a>Requisitos de la versión de servidor

<a name="BKMK_Topology"> </a>

Para configurar la implementación para la implementación híbrida con **los equipos o Skype para profesionales en línea**, debe tener una de las siguientes topologías admitidas:

- Un Skype para la implementación de Business Server 2019 con todos los servidores que ejecutan Skype para Business Server 2019.
- Un Skype para la implementación de Business Server 2015 con todos los servidores que ejecutan Skype para Business Server 2015.
- Una implementación de Lync Server 2013 con todos los servidores que ejecutan Lync Server 2013.  Sin embargo, si se requiere conectividad de voz híbrida, debe usar una topología mixta versión tal y como se indica a continuación.
- Una implementación con máximo de 2 diferentes versiones de servidor enumerados a continuación:
  - Skype para Business Server 2015 y Skype para Business Server 2019
  - Lync Server 2013 y Skype para Business Server 2019
  - Lync Server 2013 y Skype para Business Server 2015

*Si se desea utilizar voz híbrida en cualquier topología*, debe ejecutar tanto el servidor perimetral que se designa como el borde de federación, así como el grupo asociado con la federación SIP Skype para 2015 empresarial o posterior. Los usuarios pueden permanecer en un grupo de servidores de Lync 2013, si lo hay. Para obtener más detalles, vea [Planear el sistema de teléfono con conectividad RTC en Skype para Business Server](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity).

Las siguientes topologías que incluyen **Lync Server 2010 son compatibles con Skype para empresarial en línea** para la mensajería instantánea y reuniones.  Topologías que incluyen **Lync Server 2010 no se admiten para voz híbrida ni los equipos**.

- Un Lync Server 2010 y Skype para la implementación empresarial Server 2015 mixto
- Una implementación de Lync Server 2010 y Lync Server 2013 mixta
- Una implementación de Lync Server 2010 con todos los servidores que ejecutan Lync Server 2010 con las últimas actualizaciones acumulativas.

Deben ejecutar a la federación de servidor perimetral y el servidor del próximo salto de la federación de servidor perimetral de Lync Server 2010 con las últimas actualizaciones acumulativas. El Skype para Business Server 2015 o las herramientas administrativas de Lync Server 2013 debe estar instalado en al menos un servidor o estación de trabajo de administración.

## <a name="multi-forest-support"></a>Compatibilidad de bosques múltiples

<a name="BKMK_MultiForest"> </a>

Microsoft admite los siguientes tipos de escenarios híbridos de varios bosques:

- **Topología de bosque de recursos.** En este tipo de topología, hay un bosque que hospeda Skype para Business Server (el bosque de recursos) y hay uno o más bosques adicionales que identidades de cuenta de host, que obtener acceso a la Skype para Business Server en el bosque de recursos. En general, los usuarios pueden tener acceso a Skype para la funcionalidad de negocio en otro bosque si se cumplen los siguientes requisitos:
  - Los usuarios se sincronizan correctamente en el bosque que hospeda Skype para la empresa. En configuraciones híbridas, esto significa que los usuarios deben sincronizarse como objetos de usuario deshabilitados.
  - El bosque que aloja a Skype Empresarial debe confiar en el bosque que contiene a los usuarios.
    Para obtener información detallada en escenarios híbridos de bosque de recursos, vea [implementar una topología de bosque de recursos para la implementación híbrida Skype para la empresa](configure-a-multi-forest-environment-for-hybrid.md).
- **Varias implementaciones de Skype para Business Server en varios bosques.** Esta configuración puede surgir como resultado de fusiones y adquisiciones escenarios, así como en las empresas más complejas.  Consolidación de todos los usuarios de local a la nube en un único inquilino de Office 365 se puede lograr para las organizaciones con varios Skype para las implementaciones empresariales, siempre que se cumplan los requisitos de la claves siguientes:

  - Debe haber como máximo un inquilino de Office 365 implicados. No se admite la consolidación en escenarios con más de un inquilino de Office 365.
  - En cualquier momento dado, sólo un local puede ser Skype para el bosque de negocio en modo híbrido (espacio de direcciones SIP compartido). Todos los demás Skype local para bosques de negocio debe permanecer totalmente local (y supuestamente federados con cada una de las demás). Tenga en cuenta que pueden sincronizar estas otras organizaciones local a AAD si así lo desea con la [nueva funcionalidad para deshabilitar los dominios SIP en línea](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain) disponible a partir de diciembre de 2018.

    Los clientes con las implementaciones de Skype para la empresa en varios bosques totalmente deben migrar cada Skype para el bosque de negocio individualmente en el inquilino de Office 365 con la funcionalidad de dominio de dividido (Shared espacio de direcciones SIP) y, a continuación, deshabilitar híbrida con la implementación local, antes de pasar a migrar el siguiente local Skype para la implementación de la empresa. Además, antes de que se está migrando a la nube, los usuarios locales permanecen en un estado federado con todos los usuarios que no se representan en el mismo directorio del usuario local. Para obtener más detalles, consulte [en la nube de la consolidación de los equipos y Skype para la empresa](cloud-consolidation.md).

## <a name="federation-requirements"></a>Requisitos de la federación

<a name="BKMK_Federation"> </a>

Al configurar híbrida, debe asegurarse de que sus entornos en línea y local pueden federar con cada una de las demás.  El entorno en línea tiene federación abierta de forma predeterminada; a menudo, el entorno local ha cerrado la federación de forma predeterminada.  

Los requisitos siguientes necesitan cumplirse para configurar correctamente una implementación híbrida:

- La coincidencia de dominios necesita configurarse de la misma manera para la implementación local y para el inquilino de Office 365. Si la detección de asociado está habilitada en la implementación local, configure una federación abierta para el inquilino en línea. Si, por el contrario, la detección de asociado no está habilitada, configure una federación cerrada para el inquilino en línea.
- La lista de dominios bloqueados de la implementación local necesita coincidir exactamente con la lista de dominios bloqueados del inquilino en línea.
- La lista de dominios permitidos de la implementación local necesita coincidir exactamente con la lista de dominios permitidos del inquilino en línea.
- Federación debe estar habilitada para las comunicaciones externas para el inquilino en línea.

## <a name="network-considerations"></a>Consideraciones sobre la red

Las secciones siguientes describen las consideraciones para:

- Configuración de DNS
- Consideraciones sobre el firewall

### <a name="dns-settings"></a>Configuración de DNS

<a name="BKMK_DNS"> </a>

Al crear registros DNS para implementaciones híbridas, todos los Skype para los registros DNS externos empresariales debe apuntar a la infraestructura local. Para obtener detalles sobre los registros DNS necesarios, consulte [requisitos de DNS para Skype para Business Server](../../sfbserver/plan-your-deployment/network-requirements/dns.md).

Además, debe asegurarse de que la resolución DNS que se describen en la siguiente tabla funciona en su implementación local. (Si ya ha configurado la federación para local, a continuación, lo más probable es que ya tiene estos.)

|Registro DNS  <br/> |Lo puede resolver  <br/> |Requisito de DNS  <br/> |
|:-----|:-----|:-----|
|Registro SRV de DNS para _sipfederationtls._tcp. \<sipdomain.com\> para todos los dominios SIP resolución a IP(s) externo del servidor perimetral de acceso de compatibles  <br/> |Servidores perimetrales  <br/> |Habilite la comunicación federada en una configuración híbrida. El servidor perimetral tiene que saber hacia dónde redirigir el tráfico federado para el dominio SIP que se divide entre las formas local y en línea.  <br/> Debe usar estrictamente la coincidencia de los nombres DNS entre el dominio del nombre de usuario y el registro SRV.  <br/> |
|Registros DNS A para el FQDN del servicio de conferencia web perimetral, por ejemplo, webcon.contoso.com que se resuelvan en direcciones IP externas de servidor perimetral de conferencia web  <br/> |Red corporativa interna conectado a los equipos de los usuarios  <br/> |Habilite los usuarios en línea para que puedan presentar y visualizar contenido en las reuniones hospedadas de forma local. El contenido incluye archivos de PowerPoint, pizarras, sondeos y notas compartidas.   <br/> |

Según el modo en que DNS esté configurado en su organización, es probable que deba agregar estos registros a la zona DNS hospedada interna para que los dominios SIP correspondientes proporcionen una resolución DNS interna para estos registros.

### <a name="firewall-considerations"></a>Consideraciones sobre el firewall

<a name="BKMK_Firewall"> </a>

Los equipos de la red necesitan poder efectuar búsquedas estándar de DNS en Internet. Si estos equipos acceden a sitios de Internet estándar, la red cumplirá este requisito.

Según la ubicación de su centro de datos de Microsoft Online Services, también debe configurar los dispositivos de firewall de red para que acepte conexiones basadas en nombres de dominio de comodín (por ejemplo, todo el tráfico de \*. outlook.com). Si los servidores de seguridad de su organización no admiten configuraciones de nombre de caracteres comodín, tendrá que determinar manualmente los intervalos de direcciones IP que le gustaría usar para permitir y los puertos especificados.

Para obtener más información, incluidos los detalles acerca de los puertos y los requisitos de protocolo, vea [las direcciones URL de Office 365 y los intervalos de direcciones IP](https://go.microsoft.com/fwlink/p/?LinkId=252942).
