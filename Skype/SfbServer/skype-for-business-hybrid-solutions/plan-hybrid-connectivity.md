---
title: Planificar la conectividad híbrida entre Skype Empresarial Server y Skype Empresarial Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/23/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: f8b3d240-bc2e-42c9-acf8-d532d641a14c
description: 'Resumen: lea este tema para aprender a planificar la conectividad híbrida entre Skype Empresarial Server y Skype Empresarial Online.  A la hora de implementar muchas soluciones híbridas de Skype Empresarial, el primer paso consiste en configurar la conectividad híbrida.'
ms.openlocfilehash: d3fe994535197209a8d35c10144e45badb4391a8
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2018
ms.locfileid: "26294089"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-skype-for-business-online"></a>Planificar la conectividad híbrida entre Skype Empresarial Server y Skype Empresarial Online

**Resumen:** lea este tema para aprender a planificar la conectividad híbrida entre Skype Empresarial Server y Skype Empresarial Online.  A la hora de implementar muchas soluciones híbridas de Skype Empresarial, el primer paso consiste en configurar la conectividad híbrida.

Este tema proporciona una visión general y describe la infraestructura y los requisitos del sistema que necesitará para configurar la conectividad híbrida entre la existente local Skype para la implementación de Business Server — con los usuarios que se crearon en sus instalaciones Active Directory y Skype para la empresa en línea.

Este tema incluye las secciones siguientes:

- [Overview](plan-hybrid-connectivity.md#BKMK_Overview)

- [Requisitos de infraestructura](plan-hybrid-connectivity.md#BKMK_Infrastructure)

- [Compatibilidad de bosques múltiples](plan-hybrid-connectivity.md#BKMK_MultiForest)

- [Coexistencia de Exchange](plan-hybrid-connectivity.md#BKMK_Exchange)

- [Credenciales de administrador](plan-hybrid-connectivity.md#BKMK_Credentials)

- [PowerShell de Skype Empresarial Online](plan-hybrid-connectivity.md#BKMK_PowerShell)

- [Compatibilidad de clientes de Skype Empresarial](plan-hybrid-connectivity.md#BKMK_ClientSupport)

- [Requisitos de topología](plan-hybrid-connectivity.md#BKMK_Topology)

- [Requisitos para las listas de permitidos/bloqueados de la federación](plan-hybrid-connectivity.md#BKMK_Federation)

- [Configuración de DNS](plan-hybrid-connectivity.md#BKMK_DNS)

- [Consideraciones sobre el firewall](plan-hybrid-connectivity.md#BKMK_Firewall)

- [Requisitos de puerto y protocolo](plan-hybrid-connectivity.md#BKMK_Ports)

- [Cuentas de usuarios y datos](plan-hybrid-connectivity.md#BKMK_UserAccounts)

- [Directivas de usuario y características](plan-hybrid-connectivity.md#BKMK_UserPolicies)

Una vez que haya leído este tema y esté listo para implementar, consulte [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](deploy-hybrid-connectivity/deploy-hybrid-connectivity.md). Los temas sobre la implementación proporcionan instrucciones detalladas sobre la configuración de la conectividad híbrida entre su implementación local y Skype Empresarial Online.

(Para obtener información acerca de cómo configurar su Lync Server 2013 o implementación de Lync Server 2010 para entornos híbridos, vea [Lync Server 2013 hybrid](https://go.microsoft.com/fwlink/p/?LinkId=617360)).

## <a name="overview"></a>Información general
<a name="BKMK_Overview"> </a>

Con las soluciones híbridas podrá transferir a sus usuarios a la nube en función de su programación y la necesidad de su negocio. Este tema se centra en la conectividad híbrida entre una implementación local de Skype Empresarial Server y Skype Empresarial Online. Esta conectividad le permite tener a algunos usuarios alojados en local y a otros en línea.

Este tipo de implementación a veces se conoce como "dominio dividido": los usuarios de significado de un dominio, como contoso.com, se reparten entre con Skype para Business Server local y Skype para profesionales en línea de la siguiente manera:

- Los usuarios que están alojados en local interactúan con los servidores de Skype Empresarial local.

- Los usuarios que están alojados en línea interactúan con los servicios en línea de Skype Empresarial.

- Los usuarios de ambos entornos pueden colaborar entre sí al usar la mensajería instantánea, participar en llamadas de conferencia, llamadas de VoIP, etc.

- Azure Active Directory Connect se utiliza para sincronizar su directorio local con Office 365.

Active Directory local es autoritativo, lo que significa que debe hacer lo siguiente para garantizar que los usuarios locales y en línea se puedan detectar entre sí:

- Todos los usuarios deben crearse en el Active Directory local en primer lugar y, a continuación, se sincronizan con Azure AD.

- Si los usuarios están alojados en local para Skype Empresarial, tendrá que habilitarles para Skype Empresarial local.

- Si los usuarios están alojados en local, pero quiere beneficiarse de algunas características en línea (como la Difusión de reunión de Skype), tendrá que asignarles una licencia de Skype Empresarial Online (plan 2).

- Si los usuarios están alojados en Skype Empresarial Online, cuando la cuenta esté sincronizada con Azure AD, tendrá que asignarles una licencia de Skype Empresarial Online (plan 2).

- Una vez que a los usuarios de Skype Empresarial Online se les ha asignado una licencia, tendrá que habilitarles para Skype Empresarial o para la telefonía IP empresarial local. Para obtener más información, vea [Habilitar a los usuarios para Enterprise Voice en local](plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises.md). Para más información sobre los requisitos de voz híbrida, vea [Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server](plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity.md).

Recibirá más información sobre la configuración de Active Directory en las secciones que siguen. Sin embargo, primero hay que ver un resumen de la terminología y los acrónimos que se usan en los diagramas siguientes, así como en muchos de los temas sobre conectividad híbrida:

- RTC: red telefónica conmutada

- PBX: sistema telefónico de central de conmutación

- Sistema telefónico: oferta de sistema telefónico de PBX en la nube de Microsoft

- Tronco - línea de telefonía que conecta la PBX a la RTC: un tronco podría usar el protocolo de inicio de sesión (SIP) — A voz a través del protocolo de Internet (VoIP), o la tecnología más antigua de multiplexación por división de tiempo (TDM)

- SBC: controlador de borde de sesión. Dispositivo que sirve como firewall y enrutador en redes telefónicas. Por ejemplo, proporciona seguridad, conectividad, interoperabilidad y calidad de servicios.

- Puerta de enlace RTC: un dispositivo que actúa como enrutador en redes telefónicas, capaz de hacer la mayoría de las cosas que hace un SBC, excepto la seguridad y el cruce de NAT.

El siguiente diagrama muestra una Skype para la configuración híbrida de negocio "dominio dividido". Los usuarios A y los usuarios B se alojan en línea pero los usuarios locales pueden detectarlos; los usuarios C y D se alojan en local, pero los usuarios en línea los pueden detectar.

![Conectividad híbrida de SfB: dominio dividido](../media/c4fc9311-1930-4a58-877f-3c1524dfab5c.png)

Es posible que también conozca el término "voz híbrida". Hace referencia a los troncos de voz locales que suministra funciones a los usuarios alojados en la nube. La voz híbrida proporciona migración a la nube a la vez que conserva la configuración de voz local. Si ya cuenta con una implementación de Skype Empresarial Server, el primer paso para habilitar la voz híbrida consiste en configurar un entorno de dominios divididos.

Por ejemplo, supongamos que su compañía tiene un campo móvil grandes organización que requiere PBX mínima voz pero extensa teléfono inteligente que se utilice. Podría elegir transferir a estos usuarios a la nube para beneficiarse del Sistema telefónico de Office 365 (PBX en la nube) de Microsoft. Si su compañía tiene también un centro de llamadas de gran tamaño local que requiere el software de avanzada, complejo centro de contacto como parte de su PBX local, es posible que elija dejar estos usuarios local. Los usuarios que están alojados en línea y en local tienen conectividad RTC a través de su implementación local.

En el siguiente diagrama se muestra una implementación de voz híbrida de Skype Empresarial:

![Dominio dividido de SfB con PBX en la nube](../media/5e755772-269e-45ce-8b48-2e06ababfe6c.png)

Para obtener más información acerca de cómo configurar una solución híbrida de voz con su Skype para la implementación de servidor empresarial, vea [Planear el sistema de teléfono en Office 365 con conectividad de RTC local en Skype para Business Server](plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity.md).

También puede configurar las implementaciones híbridas para la integración con Exchange y SharePoint local o con aplicaciones de Microsoft Office 365, incluido Exchange Online y SharePoint Online. También puede configurar una solución de voz híbrida que no requiera una implementación completa de Skype Empresarial Server mediante Cloud Connector Edition. Para obtener más información acerca de todos los Skype para soluciones híbridas de negocio y planear la migración a la nube, vea [Skype para soluciones híbridas de negocio](skype-for-business-hybrid-solutions.md).

## <a name="infrastructure-requirements"></a>Requisitos de infraestructura
<a name="BKMK_Infrastructure"> </a>

Para implementar una conectividad híbrida entre Skype Empresarial Server y Skype Empresarial Online, debe configurar lo siguiente en su entorno:

- Una única implementación local de Skype para Business Server o Lync Server que se haya implementado en una topología admitida. En este tema, vea [requisitos de la topología](plan-hybrid-connectivity.md#BKMK_Topology) .

    > [!NOTE]
    > Todos los dominios SIP que existe en el entorno local también deben existir en su inquilino de Office 365 y viceversa. No puede tener algunos dominios SIP en línea sólo algunos dominios locales y en sólo. De lo contrario, presencia, mensajería instantánea y otras características no funcionarán correctamente.

- Un inquilino de Microsoft Office 365 con Skype para profesionales Online habilitado.

    > [!NOTE]
    > Solo puede usar un inquilino para una configuración híbrida con su implementación local.

- Skype para las herramientas administrativas de Business Server 2015. (Si está utilizando Lync Server 2013 o Lync Server 2010, puede usar las herramientas administrativas de Lync Server 2013. Para más información, consulte [Lync Server 2013 híbrido](https://go.microsoft.com/fwlink/p/?LinkId=617360)).

- Azure Active Directory Connect para sincronizar su directorio local con Office 365. Para más información, vea [Conexión de Active Directory con Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions).

    Para admitir el inicio de sesión único con Office 365 y que los usuarios puedan usar las mismas credenciales para iniciar sesión que se usan en local, puede usar las características de sincronizar contraseñas de Azure Active Directory (AAD) Connect. También puede usar los Servicios de federación de Active Directory (AD FS) para el inicio de sesión único con Office 365. 

- Una federación habilitada entre su implementación de Skype Empresarial local y su inquilino de Office 365. Federación permite a los usuarios en su implementación local para comunicarse con usuarios de Office 365 en su organización. Para más información, vea [Configure federation with Skype for Business Online](deploy-hybrid-connectivity/configure-federation-with-skype-for-business-online.md).

- Un espacio de dirección de protocolo de inicio de sesión (SIP) compartido. Una dirección SIP es un identificador único para cada usuario de una red, parecido a un número de teléfono o a una dirección de correo electrónico. Antes de intentar mover usuarios de local a Skype para profesionales en línea, debe configurar el inquilino de Office 365 para compartir el espacio de direcciones de protocolo de inicio de sesión (SIP) compartidos con la implementación local. Para más información, vea [Configure federation with Skype for Business Online](deploy-hybrid-connectivity/configure-federation-with-skype-for-business-online.md).

## <a name="multi-forest-support"></a>Compatibilidad de bosques múltiples
<a name="BKMK_MultiForest"> </a>

Los usuarios pueden acceder a la funcionalidad de Skype Empresarial en otro bosque si se cumplen los siguientes requisitos:

- Los usuarios están correctamente sincronizados en el bosque que aloja a Skype Empresarial: en configuraciones híbridas, esto significa que los usuarios deben estar sincronizados como objetos de usuarios deshabilitados.

- El bosque que aloja a Skype Empresarial debe confiar en el bosque que contiene a los usuarios.

Para obtener información detallada en escenarios híbridos de varios bosques, vea [Configure un entorno de varios bosque para entornos híbridos Skype para la empresa](deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md).

## <a name="exchange-co-existence"></a>Coexistencia de Exchange
<a name="BKMK_Exchange"> </a>

Para admitir la coexistencia con Exchange, tenga lo siguiente en cuenta:

- El procedimiento recomendado consiste en mover el buzón del usuario a Exchange Online antes de pasar página principal Skype del usuario para la empresa.

- Los usuarios con buzones de correo de Exchange son compatibles con las siguientes limitaciones conocidas:

  - Inicio de sesión de cliente: los usuarios pueden necesitar iniciar sesión dos veces durante el inicio de sesión de cliente de SfB.

  - Historial de conversaciones de lado servidor, archivado, almacén de contactos unificados, fotografías HighRes requiere Exchange 2013 o posterior, y debe habilitar el servidor de OAuth para la comunicación entre el servidor. Para obtener más información, vea [Administrar la autenticación de servidor a servidor (OAuth) y las aplicaciones asociadas en Skype para Business Server 2015](https://technet.microsoft.com/en-us/library/jj204817.aspx).

Para obtener información detallada sobre la coexistencia con Exchange Server, incluidos los criterios y las limitaciones de la compatibilidad en distintas combinaciones de implementaciones locales y en línea, vea [Compatibilidad con la característica](../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) en [Plan to integrate Skype for Business and Exchange](../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).

## <a name="administrator-credentials"></a>Credenciales de administrador
<a name="BKMK_Credentials"> </a>

Cuando se le pregunte para proporcionar sus credenciales de administrador, puede usar el nombre de usuario y la contraseña para la cuenta de administrador para el inquilino de Office 365. También va a usar estas credenciales al configurar Azure Active Directory para la federación, la sincronización de directorios, el inicio de sesión único y mover a los usuarios a Skype para profesionales en línea.

## <a name="skype-for-business-online-powershell"></a>PowerShell de Skype Empresarial Online
<a name="BKMK_PowerShell"> </a>

Ahora, los administradores tienen la capacidad de usar Windows PowerShell para administrar Skype para profesionales en línea y su Skype para las cuentas de usuario en línea de negocio. Para ello, primero debe descargar e instalar el Skype para profesionales de módulo de conector en línea desde Microsoft Download Center. Para obtener más información acerca de cómo descargar, instalar y utilizar el Skype para el módulo del conector de negocio en línea y para obtener información detallada sobre el uso de Windows PowerShell para administrar Skype para en línea de negocio, consulte [Using Windows PowerShell para administrar Skype para la empresa Online](https://technet.microsoft.com/library/dn362831.aspx).

## <a name="skype-for-business-client-support"></a>Compatibilidad de clientes de Skype Empresarial
<a name="BKMK_ClientSupport"> </a>

Hay algunas diferencias en las características compatibles con los clientes, así como en las disponibles en entornos locales y en línea. Los clientes siguientes son compatibles con Skype para profesionales en línea en una implementación híbrida:

- Skype for Business

- Lync 2013

- Lync 2010

- Aplicación de la Tienda Windows de Lync

- Lync Web App

- Lync Mobile

- Lync para Mac 2011

- Sistema de salas de Lync y Skype para sistema de salas de negocio

- Lync Basic 2013

- Microsoft Surface Hub

Antes de decidir donde desea que usuarios particulares en su organización, debe revisar la [comparación de características de cliente de escritorio de Skype para la empresa](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) para determinar la compatibilidad de cliente para las distintas configuraciones de Skype para Business Server. Vea también:

- [Planificar los clientes y los dispositivos](../plan-your-deployment/clients-and-devices/clients-and-devices.md)

- [Comparación de características de cliente móvil de Skype para la empresa](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)

## <a name="topology-requirements"></a>Requisitos de topología
<a name="BKMK_Topology"> </a>

Para configurar la implementación para la implementación híbrida con Skype para profesionales en línea, debe tener una de las siguientes topologías admitidas:

- Un Skype para la implementación de Business Server 2015 con todos los servidores que ejecutan Skype para Business Server 2015.

- Una implementación de Lync Server 2013 con todos los servidores que ejecutan Lync Server 2013.

    Para la conectividad de voz híbrida, el servidor perimetral que está designado como servidor perimetral de federación debe ser Skype Empresarial 2015; el servidor perimetral también requiere un servidor back-end en Skype Empresarial Server. Podría tener un grupo de servidores sin usuarios en él.

- Una implementación de Lync Server 2010 con todos los servidores que ejecutan Lync Server 2010 con las últimas actualizaciones acumulativas.

  - Deben ejecutar a la federación de servidor perimetral y el servidor del próximo salto de la federación de servidor perimetral de Lync Server 2010 con las últimas actualizaciones acumulativas.

  - El Skype para Business Server 2015 o las herramientas administrativas de Lync Server 2013 debe estar instalado en al menos un servidor o estación de trabajo de administración.

- Lync Server 2013 y Skype para la implementación de Business Server 2015 con las siguientes funciones de servidor en al menos un sitio que ejecuta Skype para Business Server 2015 mixto:

  - Al menos un grupo de servidores Enterprise o un servidor Standard Edition 

  - El grupo de directores asociado con la federación SIP, si existe

  - El grupo de servidores perimetrales asociado con la federación SIP

- Lync Server 2010 y Skype para la implementación de Business Server 2015 con las siguientes funciones de servidor en al menos un sitio que ejecuta Skype para Business Server 2015 mixto:

  - Al menos un grupo de servidores Enterprise o un servidor Standard Edition 

  - El grupo de directores asociado con la federación SIP, si existe

  - El grupo de servidores perimetrales asociado con la federación SIP para el sitio

- Una implementación mixta de Lync Server 2010 y Lync Server 2013 con las siguientes funciones de servidor en al menos un sitio que ejecutan Lync Server 2013:

  - Al menos un grupo de servidores Enterprise o un servidor Standard Edition en el sitio

  - El grupo de directores asociado con la federación SIP, si existe en el sitio

  - El grupo de servidores perimetrales asociado con la federación SIP para el sitio

## <a name="federation-allowedblocked-lists-requirements"></a>Requisitos para las listas de permitidos/bloqueados de la federación
<a name="BKMK_Federation"> </a>

La lista de dominios permitidos incluye los dominios que tienen configurado un nombre de dominio completo (FQDN) del perímetro de asociado. En ocasiones, estos se conocen como socios federados de socio permitido servidores ordirect. Debe estar familiarizado con la diferencia entre la federación abierta y federación cerrado, conocida como lista de dominio de socio de socio detección andallowed, respectivamente, en las implementaciones locales.

Los requisitos siguientes necesitan cumplirse para configurar correctamente una implementación híbrida:

- La coincidencia de dominios necesita configurarse de la misma manera para la implementación local y para el inquilino de Office 365. Si la detección de asociado está habilitada en la implementación local, configure una federación abierta para el inquilino en línea. Si, por el contrario, la detección de asociado no está habilitada, configure una federación cerrada para el inquilino en línea.

- La lista de dominios bloqueados de la implementación local necesita coincidir exactamente con la lista de dominios bloqueados del inquilino en línea.

- La lista de dominios permitidos de la implementación local necesita coincidir exactamente con la lista de dominios permitidos del inquilino en línea.

- Federación debe estar habilitada para las comunicaciones externas para el inquilino en línea, que se configura mediante el Skype para el Panel de Control en línea de negocio.

## <a name="dns-settings"></a>Configuración de DNS
<a name="BKMK_DNS"> </a>

Al crear registros DNS para implementaciones híbridas, todos los Skype para los registros DNS externos empresariales debe apuntar a la infraestructura local. Para obtener detalles sobre los registros DNS necesarios, consulte [requisitos de DNS para Skype para Business Server 2015](../plan-your-deployment/network-requirements/dns.md).

Además, debe asegurarse de que la resolución DNS que se describe en la siguiente tabla funciona en su implementación local:

|Registro DNS  <br/> |Lo puede resolver  <br/> |Requisito de DNS  <br/> |
|:-----|:-----|:-----|
|Registro SRV de DNS para _sipfederationtls._tcp. \<sipdomain.com\> para todos los dominios SIP resolución a IP(s) externo del servidor perimetral de acceso de compatibles  <br/> |Servidores perimetrales  <br/> |Habilite la comunicación federada en una configuración híbrida. El servidor perimetral tiene que saber hacia dónde redirigir el tráfico federado para el dominio SIP que se divide entre las formas local y en línea.  <br/> Debe usar estrictamente la coincidencia de los nombres DNS entre el dominio del nombre de usuario y el registro SRV.  <br/> |
|Registros DNS A para el FQDN del servicio de conferencia web perimetral, por ejemplo, webcon.contoso.com que se resuelvan en direcciones IP externas de servidor perimetral de conferencia web  <br/> |Red corporativa interna conectado a los equipos de los usuarios  <br/> |Habilite los usuarios en línea para que puedan presentar y visualizar contenido en las reuniones hospedadas de forma local. El contenido incluye archivos de PowerPoint, pizarras, sondeos y notas compartidas.   <br/> |

Según el modo en que DNS esté configurado en su organización, es probable que deba agregar estos registros a la zona DNS hospedada interna para que los dominios SIP correspondientes proporcionen una resolución DNS interna para estos registros.

[!NOTE] _sipfederationtls._tcp. \<sipdomain.com\> solución del registro SRV desde el servidor perimetral es necesario para la configuración híbrida. Si el servidor perimetral no se puede resolver estos registros, los usuarios locales no podrán ver el estado de presencia o comunicarse con usuarios en línea.

## <a name="firewall-considerations"></a>Consideraciones sobre el firewall
<a name="BKMK_Firewall"> </a>

Los equipos de la red necesitan poder efectuar búsquedas estándar de DNS en Internet. Si estos equipos acceden a sitios de Internet estándar, la red cumplirá este requisito.

Según la ubicación de su centro de datos de Microsoft Online Services, también debe configurar los dispositivos de firewall de red para que acepte conexiones basadas en nombres de dominio de comodín (por ejemplo, todo el tráfico de \*. outlook.com). Si los servidores de seguridad de su organización no admiten configuraciones de nombre de caracteres comodín, tendrá que determinar manualmente los intervalos de direcciones IP que le gustaría usar para permitir y los puertos especificados.

Si desea más información, consulte [URL de Office 365 e intervalos de direcciones IP](https://go.microsoft.com/fwlink/p/?LinkId=252942).

## <a name="port-and-protocol-requirements"></a>Requisitos de puerto y protocolo
<a name="BKMK_Ports"> </a>

Además de los requisitos de puerto para la comunicación interna, debe configurar también los puertos siguientes para permitir la conectividad híbrida:


|**Protocolo**|**TCP o UDP**|**IP de origen**|**IP de destino**|**Puerto de origen**|**Puerto de destino**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|SIP (MTLS)  <br/> |TCP  <br/> |Perímetro de acceso  <br/> |Office 365  <br/> |Cualquiera  <br/> |5061  <br/> |Señalización  <br/> |
|SIP (MTLS)  <br/> |TCP  <br/> |Office 365  <br/> |Perímetro de acceso  <br/> |Cualquiera  <br/> |5061  <br/> |Señalización  <br/> |
|STUN  <br/> |TCP  <br/> |Servidor perimetral A/V  <br/> |Office 365  <br/> |50.000-59.999  <br/> |443  <br/> |Abierto para sesiones de uso compartido de aplicaciones, vídeo y audio  <br/> |
|STUN  <br/> |TCP  <br/> |Office 365  <br/> |Servidor perimetral A/V  <br/> |50.000-59.999  <br/> |443  <br/> |Abierto para sesiones de uso compartido de aplicaciones, vídeo y audio  <br/> |
|STUN  <br/> |UDP  <br/> |Servidor perimetral A/V  <br/> |Office 365  <br/> |3478  <br/> |3478  <br/> |Abierto para sesiones de vídeo y audio  <br/> |
|STUN  <br/> |UDP  <br/> |Office 365  <br/> |Servidor perimetral A/V  <br/> |3478  <br/> |3478  <br/> |Abierto para sesiones de vídeo y audio  <br/> |

Para obtener más información acerca de puerto y firewall para servidor perimetral de planeación, vea [requisitos de entorno de servidor perimetral de Skype para Business Server 2015](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md). Consulte también [Port and protocol requirements for servers](../plan-your-deployment/network-requirements/ports-and-protocols.md) y el [diagrama de cargas de trabajo de protocolos](https://go.microsoft.com/fwlink/p/?LinkId=550989).

## <a name="user-accounts-and-data"></a>Cuentas de usuarios y datos
<a name="BKMK_UserAccounts"> </a>

En una implementación híbrida, cualquier usuario que se desea particular en línea, primero debe crearse en la implementación local, por lo que se crea la cuenta de usuario en servicios de dominio de Active Directory. A continuación, puede mover el usuario a Skype para profesionales en línea, que se va a mover la lista de contactos del usuario.

Al sincronizar las cuentas de usuario entre su implementación local y el inquilino en línea con AAD conectarse, debe sincronizar las cuentas de AD para todos los Skype para los usuarios empresariales o de Lync en su organización, incluso si los usuarios no se mueven a en línea. Si no sincroniza todos los usuarios, puede que la comunicación entre los usuarios locales y en línea de su organización no funcione como es de esperar.

> [!IMPORTANT]
> Administración de todos los usuarios, incluidos usuario se mueve entre local y Skype para en línea de negocio, deben realizarse con la última versión instalada de las herramientas administrativas. Las herramientas administrativas de deben instalarse en un servidor independiente que se conectan acceso a la implementación existente de local y a Internet. El cmdlet para mover usuarios desde su implementación local a Skype para Online de negocio, [Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser?view=skype-ps), se debe ejecutar desde las herramientas administrativas de conectado a su implementación local. Para obtener más información sobre cómo mover usuarios, consulte [mover usuarios de local a Skype para profesionales en línea](deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online.md).

> [!IMPORTANT]
> Si el usuario se creó con el portal en línea de Office 365, la cuenta de usuario no se sincronizará con la implementación local de Active Directory de modo que el usuario no existirá en ella. Si ya tiene usuarios creados en su inquilino en línea y desea realizar una configuración híbrida con una implementación local, vea Mover usuarios a Skype Empresarial Online.

> [!NOTE]
> Si se encuentra un Skype para cliente empresarial en línea que tiene los usuarios habilitados para Skype para profesionales en línea que no han sido habilitados en una implementación local, consulte [mover usuarios de Skype para empresarial en línea para local](deploy-hybrid-connectivity/move-users-from-skype-for-business-online-to-on-premises.md).

También necesita tener en cuenta los siguientes problemas relacionados con el usuario al planear una implementación híbrida.

- **Contactos de usuario** El límite para los contactos de los usuarios de Lync Online es 250. Cuando se mueve la cuenta a Lync Online, se quitarán todos los contactos más allá de ese número de lista de contactos del usuario.

- **Mensajería instantánea y presencia** Se migran las listas de contactos de usuarios, grupos y listas de control de acceso (ACL) con la cuenta de usuario.

- **Datos de conferencia, el contenido de la reunión y las reuniones programadas** Este contenido no se migra con la cuenta de usuario. Los usuarios necesitan reprogramar reuniones una vez que estas cuentas migran a Lync Online.

## <a name="user-policies-and-features"></a>Directivas de usuario y características
<a name="BKMK_UserPolicies"> </a>

- En un entorno híbrido, se puede habilitar a los usuarios para mensajería instantánea y conferencias (reuniones) en modo local o en línea, pero no en ambos a la vez.

- **Soporte de cliente** Algunos usuarios pueden requerir una nueva versión de cliente cuando se mueven a Skype para profesionales en línea. Para Office Communications Server 2007 R2, deben mover los usuarios a un Skype para un grupo de servidores Business Server o Lync Server 2013 antes de la migración a Skype para profesionales en línea.

- **Local las directivas y configuración (que no sean de usuario)** En línea y local las directivas requieren una configuración independiente. No se pueden establecer directivas globales para aplicarlas a ambas.


