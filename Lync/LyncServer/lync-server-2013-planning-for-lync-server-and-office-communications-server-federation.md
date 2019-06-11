---
title: Planeación de la Federación de Lync Server y Office Communications Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for Lync Server and Office Communications Server federation
ms:assetid: c9eaf06b-054f-41a4-ad0c-499400d6c4c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205335(v=OCS.15)
ms:contentKeyID: 48185640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c683092b61d278d380ad68cef86795d496498fbf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824788"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-and-office-communications-server-federation"></a>Planificación de la Federación de Lync Server 2013 y Office Communications Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-13_

La Federación entre Microsoft Lync Server 2013, Lync Server 2010 y Office Communications Server admite comunicaciones de punto a punto y de varias personas. Las conversaciones de punto a punto se pueden remitir a conversaciones de varios participantes, lo que permite las reuniones ad hoc. Las reuniones (conferencias web o conferencias de audio y vídeo) se pueden programar para incluir contactos dentro de su organización, así como contactos en socios con los que se federe.

La Federación apareció por primera vez en Microsoft Office Live Communications Server 2005 y admitía un tipo de Federación, la Federación directa. La Federación directa requirió conocer el dominio del Protocolo de inicio de sesión (SIP) del socio de Federación y el nombre de dominio completo (FQDN) del servidor perimetral del socio. Live Communications Server 2005 con SP1 introdujo tipos de Federación adicionales, todos los cuales requerían que el socio federado publique los registros SRV del sistema de nombres de dominio (DNS) para ubicar su servidor perimetral. La terminología de esa versión era:

  - *Abrir Federación mejorada*: aceptar cualquier nombre de dominio SIP y usar DNS SRV para ubicar el servidor perimetral asociado

  - *Federación mejorada*: configure el nombre de dominio SIP del socio como un asociado de Federación de su organización y use DNS SRV para buscar el servidor perimetral asociado

  - *Federación directa*: configurar el nombre de dominio SIP del socio y el FQDN al servidor perimetral del socio

  - *Lista*de permitidos del servidor: aceptar cualquier dominio, usar DNS SRV para buscar el servidor perimetral de un proveedor de hospedaje o un proveedor de conectividad de mensajería instantánea pública (mi)

Microsoft Office Communications Server 2007 introdujo nombres actualizados para los tipos de Federación para definir mejor lo que hace realmente cada tipo de Federación:

  - Abrir la Federación mejorada se conocía como *dominio de socio descubierto*

  - La Federación mejorada se conocía como *dominio asociado permitido*

  - La Federación directa se conocía como *servidor asociado permitido*

  - La lista de permitidos del servidor se conocía como *proveedor de hospedaje* y *proveedor de mensajería instantánea pública*

Microsoft Lync Server 2010 introdujo una definición más estrecha de proveedor de hospedaje de acuerdo con Microsoft Lync Online 2010 y Microsoft Office 365, y también lo hizo según la misma lista permitida definida por el tipo de Federación de dominios de socio autorizado.

Habilitar la Federación entre Microsoft Lync Server 2013, Lync Server 2010 y Office Communications Server usa los servidores perimetrales y los proxy inversos para exigir las reglas y los dominios asociados permitidos que usted defina. Desde una perspectiva de planeación, la Federación con otro Lync Server, Office Communications Server requiere lo siguiente:

  - Habilitar la Federación en el generador de topología. Para obtener más información, vea el tema sobre la implementación de la [Federación SIP, la Federación XMPP y la mensajería instantánea pública en Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).

  - Determinar los requisitos para la detección de dominios federados:
    
      - <span></span>  
        Para la configuración manual de la Federación, debe tener el nombre de dominio completo (FQDN) del servidor perimetral y el nombre de dominio del asociado, o el nombre de dominio en línea, que se especifica en el panel de control de Lync Server, **Federación y acceso externo**, **SIP Dominios federados**. Cree una directiva **nueva** o **edite** una existente para permitir o bloquear dominios por FQDN.
        
        <div>
        

        > [!WARNING]
        > La configuración manual del servidor perimetral de un socio de Federación es propenso a fallar en el caso de que el socio cambie la dirección IP de su servidor perimetral.

        
        </div>
        
        <div>
        

        > [!NOTE]
        > Para los <STRONG>nuevos dominios federados de SIP</STRONG>, debe proporcionar el <STRONG>nombre de dominio (o FQDN)</STRONG> para Microsoft Lync Online, Microsoft Office 365. Para Microsoft Lync Server 2013, Lync Server 2010 y Office Communications Server, también debe proporcionar un <STRONG>servicio perimetral de acceso (FQDN)</STRONG> .

        
        </div>
    
      - <span></span>  
        Para la Federación de Partners detectada, donde los socios pueden descubrir su servidor perimetral, cree un registro SRV en su \_DNS externo-sipfederationtls. \_TCP.contoso.com, que apunta al puerto 5061 y al registro de host (A) de su servidor perimetral.
        
        <div>
        

        > [!IMPORTANT]
        > Si admite clientes móviles de Microsoft Lync en Windows Phone o Apple iPhone, iPad u otros dispositivos Apple y está usando el servicio de notificaciones Push o el servicio de notificaciones push, debe planear _sipfederationtls. _ TCP. &lt;Registros SRV&gt; de dominio SIP para cada dominio SIP que tenga clientes móviles de Lync. Android y Nokia Symbian Lync Mobile no usan la notificación de inserción y no están sujetos a este requisito.

        
        </div>

  - Configurar directivas de acceso de usuarios externos para admitir dominios federados

  - Abra puertos de Firewall para el protocolo de inicio de sesión (SIP), las conferencias web y el audio/vídeo para alojar la Federación o los contactos que está habilitando. Para obtener más información, consulte: [determinar el firewall externo a/V y los requisitos de puerto para Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

La siguiente información le ayudará a definir el certificado, el puerto/protocolo y los requisitos de DNS para la Federación con Microsoft Lync Server 2013 y Lync Server 2010.

Generalmente es un proceso de reenvío directo si ha planeado o implementado los servidores perimetrales de Microsoft Lync Server 2013, por lo general, en el planeamiento de certificados, Firewall y requisitos de Puerto/protocolo. Puesto que la Federación es una característica adicional que usa el servidor perimetral existente, los requisitos de planeación suelen cumplirse al planear e implementar el servidor perimetral. Debe usar las siguientes tablas para determinar que se cumplen sus requisitos y realizar cambios en el puerto, protocolo y DNS según corresponda.

<div>


> [!IMPORTANT]
> Si tiene un grupo de servidores de tecnología perimetral y se está federando con socios de Lync Server 2013 o Lync Server 2010, puede usar equilibrio de carga DNS o equilibradores de carga de hardware en los lados frontales internos y externos de los servidores perimetrales. Si va a federar con Office Communications Server 2007 o con Office Communications Server 2007 R2, el equilibrio de carga de hardware proporcionará compatibilidad con la conmutación por error en el caso de un servidor perimetral. Office Communications Server 2007 y Office Communications Server 2007 R2 no tienen en cuenta el equilibrio de carga de DNS. Los servidores perimetrales asociados establecerán comunicación con el primer servidor perimetral de su grupo que responda. Si se produce un error en ese servidor perimetral, la comunicación no se realiza automáticamente.



</div>

Los requisitos de certificados se suelen cumplir a través de la planificación de certificados para el servidor perimetral elegido o el plan del servidor perimetral agrupado.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Resumen del certificado: SIP, Federación XMPP y mensajería instantánea pública en Lync Server 2013](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [Resumen de puertos: SIP, Federación XMPP y mensajería instantánea pública en Lync Server 2013](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [Resumen DNS: SIP, Federación XMPP y mensajería instantánea pública en Lync Server 2013](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a>Vea también


[Configurar directivas para controlar el acceso de usuarios federados en Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[Escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Determinar los requisitos de los puertos y el firewall de A/V externos en Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[Determinar los requisitos DNS para Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  


[Administrar la configuración perimetral de acceso para su organización en Lync Server 2013](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[Administrar dominios federados SIP para la organización en Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[Administrar proveedores federados SIP para la organización en Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

