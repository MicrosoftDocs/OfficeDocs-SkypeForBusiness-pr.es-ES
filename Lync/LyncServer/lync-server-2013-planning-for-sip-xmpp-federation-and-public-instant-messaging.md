---
title: Planear el SIP, la Federación de XMPP y la mensajería instantánea pública
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for SIP, XMPP federation, and public instant messaging
ms:assetid: 3b234d92-b9ff-4b1d-910e-084c6f17e751
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204825(v=OCS.15)
ms:contentKeyID: 48183918
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88aa8c6f3f2f11b303a7e25eed96d5f0d7243cb4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824151"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Planificación de SIP, Federación XMPP y mensajería instantánea pública en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-10-28_

Los servidores perimetrales se pueden configurar para permitir a los usuarios externos y internos el acceso a los contactos de las organizaciones o servicios asociados. Las federaciones, ya que estos acuerdos de socio son conocidos, pueden proporcionar cualquiera de los siguientes elementos o todos ellos a los contactos de su organización en la Federación de Partners o los contactos de la Federación del Partner con usted:

  - Mensajería instantánea y presencia

  - Colaboración y conferencias, por ejemplo: conferencias web

  - Audioconferencias, videoconferencias o ambos

En algunos casos, la comunicación, por ejemplo, la mensajería instantánea (mi) y la presencia entre un contacto de Microsoft Lync Server 2013 y el protocolo de presencia y mensajería extensible (XMPP), solo es compatible con usted y el contacto en el equipo federado. servidor. En otros casos, como un servidor de Lync, Lync Server 2010 a la Federación de Lync Server 2013, se puede invitar a varios participantes a participar en la conversación.

<div>

## <a name="lync-server-and-office-communications-server-federation"></a>Federación de Lync Server y Office Communications Server

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

</div>

<div>

## <a name="public-instant-messaging-connectivity"></a>Conectividad de mensajería instantánea pública

La conectividad de mensajería instantánea pública es una clase de Federación y está configurada para permitir a los usuarios internos y externos de Lync Server 2013 agregar contactos de cualquiera de las siguientes opciones:

  - Contactos de Messenger

  - Yahoo\! contactos

  - Contactos de America Online (AOL)

<div>


> [!IMPORTANT]
> <UL>
> <LI>
> <P>A partir del 1 de septiembre de 2012, la licencia de suscripción de usuario de la conectividad de mensajería instantánea pública de Microsoft Lync (PIC USL) ya no está disponible para la compra de contratos nuevos o de renovación. Los clientes con licencias activas podrán seguir federando a Yahoo! Messenger hasta la fecha de cierre del servicio (la fecha exacta aún se debe decidir, pero no antes del 2013 de junio).</P>
> <LI>
> <P>El PIC USL es una licencia por usuario y por mes de suscripción que es necesaria para que Lync Server o Office Communications Server se federe con Yahoo! Mensajería. La capacidad de Microsoft para proporcionar este servicio está supeditada al soporte de Yahoo!, el contrato subyacente para el cual no se renovará.</P>
> <LI>
> <P>Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo. La Federación con Windows Live Messenger no requiere licencias adicionales para usuarios y dispositivos más allá de la CAL de Lync Standard. La Federación de Skype se agrega a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas a través de la mensajería instantánea y la voz.</P></LI></UL>



</div>

Esta clase de Federación requiere las siguientes consideraciones de planeación:

  - Los usuarios de Windows Live Messenger pueden tener una comunicación visual o de audio de punto a punto con los usuarios de Lync Server 2013, además de la mensajería instantánea. Los servidores perimetrales deben cumplir con requisitos de puerto y protocolo específicos. Para obtener más información, consulte [determinar el firewall externo a/V y los requisitos de puerto para Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).

  - La mensajería instantánea de Yahoo no tiene requisitos únicos, excepto los que normalmente se usan en la planificación y la implementación del servidor perimetral típico que proporciona la Federación.

  - America Online requiere que el certificado del servidor perimetral asignado al servicio perimetral de acceso tenga un uso mejorado de clave (EKU) de cliente.

</div>

<div>

## <a name="extensible-messaging-and-presence-protocol-xmpp-federation"></a>Federación de protocolo de presencia y mensajería extensible (XMPP)

Las versiones anteriores de Lync Server y Office Communications Server proporcionaban una puerta de enlace de protocolo de presencia y mensajería extensible (XMPP) que se podría implementar como una función de servidor independiente para permitir la Federación con implementaciones de XMPP. En Microsoft Lync Server 2013, la funcionalidad de XMPP puede implementarse como una característica. La funcionalidad XMPP se instala en dos partes: un proxy XMPP que se ejecuta en el servidor perimetral y la puerta de enlace XMPP que se ejecuta en los servidores front-end.

La implementación y configuración de XMPP se trata en [implementar el acceso de usuarios externos en Lync Server 2013](lync-server-2013-deploying-external-user-access.md) se planea la compatibilidad de XMPP en la organización mediante la definición de reglas de puerto y protocolo en el firewall, la configuración de certificados y la adición de DNS PTR. En los temas siguientes de esta sección se resume la información necesaria para planear correctamente la Federación XMPP para su implementación.

<div>


> [!IMPORTANT]
> La capacidad XMPP de Lync Server 2013 está probada y es compatible con Microsoft para la federación de mensajería instantánea con Google Talk. Para otros sistemas XMPP, póngase en contacto con el proveedor para comprobar que son compatibles con la federación con Lync Server 2013 y para cualquier recomendación sobre implementación o solución de problemas.



</div>

<div>


> [!IMPORTANT]
> La Federación de XMPP no es compatible con los usuarios que están alojados en dispositivos de sucursales con las que es posible. Esto se aplica a la información de presencia y a intercambiar mensajes INSTANTÁNEos.



</div>

</div>

<div id="sectionSection3" class="section">

En los siguientes temas se incluyen instrucciones para definir certificados, puertos de firewall y entradas DNS para los tipos de escenarios de Federación admitidos.

  - <span></span>  
    [Resumen del certificado: SIP, Federación XMPP y mensajería instantánea pública en Lync Server 2013](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [Resumen de puertos: SIP, Federación XMPP y mensajería instantánea pública en Lync Server 2013](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [Resumen DNS: SIP, Federación XMPP y mensajería instantánea pública en Lync Server 2013](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

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

