---
title: Planeación de la conectividad híbrida
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Consideraciones de planeación para implementar la conectividad de híbrida entre Skype para Business Server y Skype para profesionales en línea o los equipos.
ms.openlocfilehash: 90ea0b5ee73cba718c81e5614b02b5332e223acf
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2018
ms.locfileid: "25030682"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-office-365"></a>Planeación de la conectividad híbrida entre Skype para Business Server y Office 365
[!INCLUDE [disclaimer](../disclaimer.md)]


## <a name="overview"></a>Información general

Lea este tema para obtener información sobre cómo planear la conectividad híbrida entre Skype para Business Server y Skype para profesionales en línea o los equipos. A la hora de implementar muchas soluciones híbridas de Skype Empresarial, el primer paso consiste en configurar la conectividad híbrida.

Soluciones híbridas permiten conservar algún control local mientras se aprovecha también los servicios en línea proporcionados en la nube de Microsoft. Con conectividad híbrida configurar y una variedad de servicios de nube disponibles para su online y los usuarios locales, puede elegir mover los usuarios a la nube en función de sus necesidades de negocio y programación.

Por ejemplo, es posible que elija obtener el control de llamadas a través del sistema de teléfono de Microsoft en la nube, conservando la conectividad de RTC local. También es posible que elija aprovechar las ventajas de los otros servicios en la nube, como correo de voz en la nube y el conector de datos de llamada.

En este tema se describe los requisitos de sistema e infraestructura que necesitará para configurar la conectividad híbrida entre su Skype local existente para la implementación de Business Server--con los usuarios que se crearon en el local de Active Directory--y Skype para los negocios en línea o los equipos.

Una vez leído este tema y esté listo para configurar la conectividad híbrida, vea [Configurar la conectividad híbrida entre Skype para Business Server y Office 365](configure-hybrid-connectivity.md). Los temas de configuración proporcionan instrucciones paso a paso para la configuración de conectividad híbrida entre su implementación local y Skype para el negocio en línea.

(Para obtener información acerca de cómo configurar su Lync Server 2013 o implementación de Lync Server 2010 para entornos híbridos, vea [Lync Server 2013 hybrid](https://go.microsoft.com/fwlink/p/?LinkId=617360)).

## <a name="split-domain-functionality"></a>Dividir la funcionalidad de dominio
<a name="BKMK_Overview"> </a>

 Con conectividad híbrida configurar entre una implementación local de Skype para Business Server y Skype para profesionales en línea o equipos, puede tener algunos usuarios alojarse en local y algunos usuarios alojados en línea.

Este tipo de configuración a veces se conoce como "dominio dividido--" lo que significa que los usuarios de un dominio, como contoso.com, se reparten entre el uso de Skype para Business Server local y Skype para profesionales en línea o equipos, tal como se muestra en el siguiente diagrama:

![Conectividad híbrida de SfB: dominio dividido](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

Con un entorno de dominio dividido:

- Los usuarios que están hospedados en local interactúan con Skype local para servidores empresariales. También es posible que tienen acceso a servicios en línea, como correo de voz en la nube.

- Los usuarios que están hospedados en línea pueden interactuar con Skype para servicios en línea de negocio o los equipos.

- Los usuarios de ambos entornos pueden colaborar entre sí mediante el uso de mensajería instantánea, que participan en las llamadas de conferencia o llamadas VoIP y así sucesivamente.

- Azure Active Directory conectar se usa para sincronizar el directorio local con Office 365.

Active Directory local es autoritativo, lo que significa que debe hacer lo siguiente para garantizar que los usuarios locales y en línea se puedan detectar entre sí:

- Todos los usuarios deben crearse en el Active Directory local en primer lugar y, a continuación, se sincronizan con Azure AD.

- Los usuarios que se mueven a la nube deben tener puede ser un Skype para licencia empresarial Plan 2 o equipos.

- Si desean que los usuarios aprovechar otras características en línea, como la difusión de reunión de Skype o correo de voz en la nube, necesita asignarlas la licencia correspondiente en Office 365.

- Una vez que a los usuarios de Skype Empresarial Online se les ha asignado una licencia, tendrá que habilitarles para Skype Empresarial o para la telefonía IP empresarial local. Para obtener más información, vea [Habilitar a los usuarios para Enterprise Voice en local](../../sfbserver/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises.md). Para obtener más información acerca de los requisitos de voz híbrida, vea [Planear el sistema de teléfono en Office 365 con conectividad de RTC local en Skype para Business Server](../../sfbserver/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity.md).


## <a name="infrastructure-requirements"></a>Requisitos de infraestructura
<a name="BKMK_Infrastructure"> </a>

Para implementar la conectividad híbrida entre su entorno local y los servicios de comunicación de Office 365, debe cumplir los siguientes requisitos de infraestructura.

- Una única implementación local de Skype para Business Server o Lync Server que se haya implementado en una topología admitida. En este tema, vea [requisitos de la topología](plan-hybrid-connectivity.md#BKMK_Topology) .

- Un inquilino de Microsoft Office 365 con Skype para profesionales Online habilitado.

    > [!NOTE]
    > Solo puede usar un inquilino para una configuración híbrida con su implementación local.

- Skype para herramientas administrativas de Business Server. (Si está utilizando Lync Server 2013 o Lync Server 2010, puede usar las herramientas administrativas de Lync Server 2013. Para obtener más información, vea [Lync Server 2013 hybrid](https://go.microsoft.com/fwlink/p/?LinkId=617360)).

- Azure Active Directory Connect para sincronizar su directorio local con Office 365. Para obtener más información, vea [Azure Connect AD: permisos y cuentas de](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions).

    Para admitir el inicio de sesión único con Office 365 y que los usuarios puedan usar las mismas credenciales para iniciar sesión que se usan en local, puede usar las características de sincronizar contraseñas de Azure Active Directory (AAD) Connect. También puede usar los Servicios de federación de Active Directory (AD FS) para el inicio de sesión único con Office 365.

Para configurar la conectividad híbrida, también tendrá que configurar la federación entre los entornos en línea y local y configurar su Skype para inquilino empresarial en línea para un espacio de direcciones compartido de protocolo de inicio de sesión (SIP). Para obtener más información acerca de los pasos necesarios para configurar la conectividad híbrida, vea [Configurar la conectividad de híbrida](configure-hybrid-connectivity.md).

Después de configurar la conectividad híbrida, puede mover los usuarios a Skype para profesionales en línea o los equipos. Para obtener más información, vea [mover usuarios de local a Skype para profesionales en línea](move-users-from-on-premises-to-skype-for-business-online.md) y [mover los usuarios de local a los equipos](move-users-from-on-premises-to-teams.md).

## <a name="multi-forest-support"></a>Compatibilidad de bosques múltiples
<a name="BKMK_MultiForest"> </a>

Los usuarios pueden acceder a la funcionalidad de Skype Empresarial en otro bosque si se cumplen los siguientes requisitos:

- Los usuarios están correctamente sincronizados en el bosque que aloja a Skype Empresarial: en configuraciones híbridas, esto significa que los usuarios deben estar sincronizados como objetos de usuarios deshabilitados.

- El bosque que aloja a Skype Empresarial debe confiar en el bosque que contiene a los usuarios.

Para obtener información detallada en escenarios híbridos de varios bosques, vea [Configure un entorno de varios bosque para entornos híbridos Skype para la empresa](configure-a-multi-forest-environment-for-hybrid.md).

## <a name="administrator-credentials"></a>Credenciales de administrador
<a name="BKMK_Credentials"> </a>

Cuando se le pregunte para proporcionar sus credenciales de administrador, puede usar el nombre de usuario y la contraseña para la cuenta de administrador para el inquilino de Office 365. También va a usar estas credenciales al configurar Azure Active Directory para la federación, la sincronización de directorios, el inicio de sesión único y mover a los usuarios a Skype para profesionales en línea.

## <a name="skype-for-business-online-powershell"></a>PowerShell de Skype Empresarial Online
<a name="BKMK_PowerShell"> </a>

Ahora, los administradores tienen la capacidad de usar Windows PowerShell para administrar Skype para profesionales en línea y su Skype para las cuentas de usuario en línea de negocio. Para ello, primero debe descargar e instalar el Skype para profesionales de módulo de conector en línea desde Microsoft Download Center. Para obtener más información en descargar, instalar y usar el Skype para el módulo del conector de negocio en línea y para obtener información detallada sobre el uso de Windows PowerShell para administrar Skype para profesionales en línea, vea [Configurar el equipo de Windows PowerShell](https://technet.microsoft.com/library/dn362831.aspx).

## <a name="skype-for-business-client-support"></a>Compatibilidad de clientes de Skype Empresarial
<a name="BKMK_ClientSupport"> </a>

Hay algunas diferencias en las características compatibles con los clientes, así como en las disponibles en entornos locales y en línea. Los clientes siguientes son compatibles con Skype para profesionales en línea en una implementación híbrida:

- Skype Empresarial

- Lync 2013

- Lync 2010

- Aplicación de la Tienda Windows de Lync

- Lync Web App

- Lync Mobile

- Lync para Mac 2011

- Sistema de salas de Lync y Skype para sistema de salas de negocio

- Lync Basic 2013

- Microsoft Surface Hub

Antes de decidir donde desea que usuarios particulares en su organización, debe revisar la [comparación de características de cliente de escritorio de Skype para la empresa](../../sfbserver/plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) para determinar la compatibilidad de cliente para las distintas configuraciones de Skype para Business Server. Vea también:

- [Planificar los clientes y los dispositivos](../../sfbserver/plan-your-deployment/clients-and-devices/clients-and-devices.md)

- [Comparación de características de cliente móvil de Skype para la empresa](../../sfbserver/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)

## <a name="topology-requirements"></a>Requisitos de topología
<a name="BKMK_Topology"> </a>

Para configurar la implementación para la implementación híbrida con Skype para profesionales en línea, debe tener una de las siguientes topologías admitidas:

- Un Skype para la implementación de Business Server 2015 con todos los servidores que ejecutan Skype para Business Server 2015.

- Una implementación de Lync Server 2013 con todos los servidores que ejecutan Lync Server 2013.

    Para la conectividad de voz híbrida, el servidor perimetral que se designa como federación perimetral debe ser Skype para profesionales de 2015; el borde también requiere una Skype para Business Server back-end. Podría tener un grupo de servidores sin usuarios en él.

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

La lista de dominios permitidos incluye los dominios que tienen configurado un nombre de dominio completo (FQDN) del perímetro de asociado. En ocasiones, se conocen como servidores de asociado permitidos o asociados directos de federación. Familiarícese con la diferencia entre las federaciones abiertas y cerradas, conocidas respectivamente como detección de asociado o lista de dominios de asociado permitidos en las implementaciones locales.

Los requisitos siguientes necesitan cumplirse para configurar correctamente una implementación híbrida:

- La coincidencia de dominios necesita configurarse de la misma manera para la implementación local y para el inquilino de Office 365. Si la detección de asociado está habilitada en la implementación local, configure una federación abierta para el inquilino en línea. Si, por el contrario, la detección de asociado no está habilitada, configure una federación cerrada para el inquilino en línea.

- La lista de dominios bloqueados de la implementación local necesita coincidir exactamente con la lista de dominios bloqueados del inquilino en línea.

- La lista de dominios permitidos de la implementación local necesita coincidir exactamente con la lista de dominios permitidos del inquilino en línea.

- Federación debe estar habilitada para las comunicaciones externas para el inquilino en línea, que se configura mediante el Skype para el Panel de Control en línea de negocio.

## <a name="dns-settings"></a>Configuración de DNS
<a name="BKMK_DNS"> </a>

Al crear registros DNS para implementaciones híbridas, todos los Skype para los registros DNS externos empresariales debe apuntar a la infraestructura local. Para obtener detalles sobre los registros DNS necesarios, consulte [requisitos de DNS para Skype para Business Server](../../sfbserver/plan-your-deployment/network-requirements/dns.md).

Además, debe asegurarse de que la resolución DNS que se describen en la siguiente tabla funciona en su implementación local:

|Registro DNS  <br/> |Lo puede resolver  <br/> |Requisito de DNS  <br/> |
|:-----|:-----|:-----|
|Registro SRV de DNS para _sipfederationtls._tcp. \<sipdomain.com\> para todos los dominios SIP resolución a IP(s) externo del servidor perimetral de acceso de compatibles  <br/> |Servidores perimetrales  <br/> |Habilite la comunicación federada en una configuración híbrida. El servidor perimetral tiene que saber hacia dónde redirigir el tráfico federado para el dominio SIP que se divide entre las formas local y en línea.  <br/> Debe usar estrictamente la coincidencia de los nombres DNS entre el dominio del nombre de usuario y el registro SRV.  <br/> |
|Registros DNS A para el FQDN del servicio de conferencia web perimetral, por ejemplo, webcon.contoso.com que se resuelvan en direcciones IP externas de servidor perimetral de conferencia web  <br/> |Red corporativa interna conectado a los equipos de los usuarios  <br/> |Habilite los usuarios en línea para que puedan presentar y visualizar contenido en las reuniones hospedadas de forma local. El contenido incluye archivos de PowerPoint, pizarras, sondeos y notas compartidas.   <br/> |

Según el modo en que DNS esté configurado en su organización, es probable que deba agregar estos registros a la zona DNS hospedada interna para que los dominios SIP correspondientes proporcionen una resolución DNS interna para estos registros.

## <a name="firewall-considerations"></a>Consideraciones sobre el firewall
<a name="BKMK_Firewall"> </a>

Los equipos de la red necesitan poder efectuar búsquedas estándar de DNS en Internet. Si estos equipos acceden a sitios de Internet estándar, la red cumplirá este requisito.

Según la ubicación de su centro de datos de Microsoft Online Services, también debe configurar los dispositivos de firewall de red para que acepte conexiones basadas en nombres de dominio de comodín (por ejemplo, todo el tráfico de \*. outlook.com). Si los servidores de seguridad de su organización no admiten configuraciones de nombre de caracteres comodín, tendrá que determinar manualmente los intervalos de direcciones IP que le gustaría usar para permitir y los puertos especificados.

Para obtener más información, vea [las direcciones URL de Office 365 y los intervalos de direcciones IP](https://go.microsoft.com/fwlink/p/?LinkId=252942).

## <a name="port-and-protocol-requirements"></a>Requisitos de puerto y protocolo
<a name="BKMK_Ports"> </a>

Además de los requisitos de puerto para la comunicación interna, debe configurar también los puertos siguientes para permitir la conectividad híbrida:


|**Protocolo**|**TCP o UDP**|**IP de origen**|**IP de destino**|**Puerto de origen**|**Puerto de destino**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|SIP (MTLS)  <br/> |TCP  <br/> |Perímetro de acceso  <br/> |Office 365  <br/> |Cualquiera  <br/> |5061  <br/> |Señalización  <br/> |
|SIP (MTLS)  <br/> |TCP  <br/> |Office 365  <br/> |Perímetro de acceso  <br/> |Cualquiera  <br/> |5061  <br/> |Señalización  <br/> |
|STUN  <br/> |TCP  <br/> |Servidor perimetral A/V  <br/> |Office 365  <br/> |50.000-59.999  <br/> |443, 50.000-59.999  <br/> |Abierto para sesiones de uso compartido de aplicaciones, vídeo y audio  <br/> |
|STUN  <br/> |TCP  <br/> |Office 365  <br/> |Servidor perimetral A/V  <br/> |443  <br/> |50.000-59.999  <br/> |Abierto para sesiones de uso compartido de aplicaciones, vídeo y audio  <br/> |
|STUN  <br/> |UDP  <br/> |Servidor perimetral A/V  <br/> |Office 365  <br/> |3478  <br/> |3478  <br/> |Abierto para sesiones de vídeo y audio  <br/> |
|STUN  <br/> |UDP  <br/> |Office 365  <br/> |Servidor perimetral A/V  <br/> |3478  <br/> |3478  <br/> |Abierto para sesiones de vídeo y audio  <br/> |

Para obtener más información acerca de puerto y firewall para servidor perimetral de planeación, vea [requisitos de entorno de servidor perimetral de Skype para Business Server](../../sfbserver/plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md). Consulte también [los requisitos de puerto y protocolo para los servidores](../../sfbserver/plan-your-deployment/network-requirements/ports-and-protocols.md) y el [diagrama de cargas de trabajo de protocolo](https://go.microsoft.com/fwlink/p/?LinkId=550989).

## <a name="user-accounts-and-data"></a>Cuentas de usuarios y datos
<a name="BKMK_UserAccounts"> </a>

En una implementación híbrida, cualquier usuario que desea particular en línea, primero debe crearse en la implementación local, por lo que se crea la cuenta de usuario en servicios de dominio de Active Directory. A continuación, puede mover el usuario a Skype para profesionales en línea, que se va a mover la lista de contactos del usuario.

Al sincronizar las cuentas de usuario entre su implementación local y el inquilino en línea con AAD conectarse, debe sincronizar las cuentas de AD para todos los Skype para los usuarios empresariales o de Lync en su organización, incluso si los usuarios no se mueven a en línea. Si no sincroniza todos los usuarios, puede que la comunicación entre los usuarios locales y en línea de su organización no funcione como es de esperar.

> [!IMPORTANT]
> Administración de todos los usuarios, incluidos usuario se mueve entre local y Skype para en línea de negocio, deben realizarse con la última versión instalada de las herramientas administrativas. Las herramientas administrativas de deben instalarse en un servidor independiente que se conectan acceso a la implementación existente de local y a Internet. El cmdlet para mover usuarios desde su implementación local a Skype para Online de negocio, [Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser?view=skype-ps), se debe ejecutar desde las herramientas administrativas de conectado a su implementación local. Para obtener más información sobre cómo mover usuarios, consulte [mover usuarios de local a Skype para profesionales en línea](move-users-from-on-premises-to-skype-for-business-online.md).

También debe tener en cuenta los siguientes problemas relacionados con el usuario al planear una implementación híbrida:

- **Contactos de usuario** El límite para los contactos de los usuarios de Lync Online es 250. Cuando se mueve la cuenta a Lync Online, se quitarán todos los contactos más allá de ese número de lista de contactos del usuario.

- **Mensajería instantánea y presencia** Se migran las listas de contactos de usuarios, grupos y listas de control de acceso (ACL) con la cuenta de usuario.

- **Datos de conferencia, el contenido de la reunión y las reuniones programadas** Este contenido no se migra con la cuenta de usuario. Los usuarios necesitan reprogramar reuniones una vez que estas cuentas migran a Lync Online.

## <a name="user-policies-and-features"></a>Directivas de usuario y características
<a name="BKMK_UserPolicies"> </a>

- En un entorno híbrido, se puede habilitar a los usuarios para mensajería instantánea y conferencias (reuniones) en modo local o en línea, pero no en ambos a la vez.

- **Soporte de cliente** Algunos usuarios pueden requerir una nueva versión de cliente cuando se mueven a Skype para profesionales en línea. Para Office Communications Server 2007 R2, deben mover los usuarios a un Skype para un grupo de servidores Business Server o Lync Server 2013 antes de la migración a Skype para profesionales en línea.

- **Local las directivas y configuración (que no sean de usuario)** En línea y local las directivas requieren una configuración independiente. No se pueden establecer directivas globales para aplicarlas a ambas.
