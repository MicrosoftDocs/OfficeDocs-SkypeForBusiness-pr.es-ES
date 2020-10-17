---
title: Planeación de SIP, la Federación XMPP y la mensajería instantánea pública
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for SIP, XMPP federation, and public instant messaging
ms:assetid: 3b234d92-b9ff-4b1d-910e-084c6f17e751
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204825(v=OCS.15)
ms:contentKeyID: 48183918
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f213b584d62a9a40810de2a05676b6d0737258e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513467"
---
# <a name="planning-for-sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Planeación de SIP, la Federación XMPP y la mensajería instantánea pública en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-10-28_

Los servidores perimetrales se pueden configurar para permitir que los usuarios internos y externos tengan acceso a contactos de organizaciones o servicios asociados. Las federaciones, como se conocen estos acuerdos de socios, pueden proporcionar algunas o todas de las siguientes opciones a los contactos de su organización en la federación asociada o a los contactos de la federación asociada a los suyos:

  - Mensajería instantánea y presencia

  - Colaboración y conferencias, por ejemplo: conferencias web

  - Conferencias de audio, conferencias de vídeo o ambas

En algunos casos, la comunicación, por ejemplo, la mensajería instantánea (mi) y la presencia entre un contacto de Microsoft Lync Server 2013 y el protocolo extensible de mensajería y presencia (XMPP), es solo de punto a punto y solo admite usted y el contacto en el socio federado. En otros casos, como un Lync Server, Lync Server 2010 a Lync Server 2013 Federation, se puede invitar a varios participantes a unirse a la conversación.

<div>

## <a name="lync-server-and-office-communications-server-federation"></a>Federación de Lync Server y Office Communications Server

La Federación entre Microsoft Lync Server 2013, Lync Server 2010 y Office Communications Server admite comunicaciones de punto a punto y de varios participantes. Las conversaciones de punto a punto se pueden escalar a conversaciones entre varias personas, lo que permite las reuniones ad hoc. Las reuniones, las conferencias web o las conferencias de audio y vídeo se pueden programar para que incluyan contactos dentro de la organización, así como contactos en socios con los que haya establecido una relación de federación.

La Federación apareció por primera vez en Microsoft Office Live Communications Server 2005 y admitía un tipo de Federación, la Federación directa. La Federación directa requirió conocer el dominio de protocolo de inicio de sesión (SIP) del socio de Federación y el nombre de dominio completo (FQDN) del servidor perimetral del asociado. Live Communications Server 2005 con SP1 incorporó tipos de Federación adicionales, todos los cuales requerían que el socio federado publicara los registros SRV del sistema de nombres de dominio (DNS) para localizar su servidor perimetral. La terminología de aquella versión era:

  - *Federación ampliada abierta*: acepte cualquier nombre de dominio SIP y use DNS SRV para ubicar el servidor perimetral del asociado

  - *Federación mejorada*: configure el nombre de dominio SIP del asociado como asociado de Federación de su organización y use DNS SRV para buscar el servidor perimetral asociado

  - *Federación directa*: configure el nombre de dominio SIP del socio y el FQDN en el servidor perimetral del asociado

  - *Lista de permitidos del servidor*: aceptar cualquier dominio, usar DNS SRV para buscar el servidor perimetral de un proveedor de hospedaje o un proveedor de conectividad de mensajería instantánea (mi) pública

Microsoft Office Communications Server 2007 ha introducido un nombre actualizado para los tipos de Federación a fin de definir mejor el tipo de Federación que se ha realizado realmente:

  - La federación mejorada abierta se denominó *dominio de socio detectado*.

  - La federación mejorada se denominó *dominio de socio permitido*.

  - La federación directa se denominó *servidor de socio permitido*.

  - La lista de permisos del servidor se denominó *proveedor de hospedaje* y *proveedor de MI público*.

Microsoft Lync Server 2010 ha introducido una definición más estrecha del proveedor de hospedaje de acuerdo con Microsoft Lync Online 2010 y Microsoft Office 365, y también lo ha sujeto a la misma lista permitida definida por el tipo de Federación de dominio de socio permitido.

La habilitación de la Federación entre Microsoft Lync Server 2013, Lync Server 2010 y Office Communications Server usa los servidores perimetrales y los proxy inversos para aplicar las reglas y los dominios asociados permitidos que se definen. Desde el punto de vista de la planeación, la Federación con otros Lync Server, Office Communications Server requiere lo siguiente:

  - Habilite la federación en el Generador de topologías. Para obtener más información, consulte el tema de implementación [configurar la Federación SIP, la Federación XMPP y la mensajería instantánea pública en Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).

  - Determine sus requisitos para la detección de dominios federados:
    
      - <span></span>  
        Para la configuración manual de la Federación, debe tener el nombre de dominio completo (FQDN) del servidor perimetral y el nombre de dominio del asociado, o el nombre de dominio en línea, que se especifica en el panel de control de Lync Server, **Federación y acceso externo**, **dominios federados SIP**. Cree una**nueva** directiva o **edite** una directiva actual para permitir o bloquear dominios por FQDN.
        
        <div>
        

        > [!WARNING]
        > La configuración manual del servidor perimetral de un socio de Federación es propenso a errores en el caso de que el asociado cambie la dirección IP de su servidor perimetral.

        
        </div>
        
        <div>
        

        > [!NOTE]
        > Para los <STRONG>nuevos dominios federados SIP</STRONG>, debe proporcionar el <STRONG>nombre de dominio (o FQDN)</STRONG> para Microsoft Lync Online y microsoft 365 u Office 365. Para Microsoft Lync Server 2013, Lync Server 2010 y Office Communications Server, también debe proporcionar un <STRONG>servicio perimetral de acceso (FQDN)</STRONG> .

        
        </div>
    
      - <span></span>  
        Para la Federación de asociados detectados, donde los asociados pueden descubrir el servidor perimetral, se crea un registro SRV en el DNS externo \_ sipfederationtls. \_ tcp.contoso.com – que apunta al puerto 5061 y al registro host (A) del servidor perimetral
        
        <div>
        

        > [!IMPORTANT]
        > Si admite clientes móviles de Microsoft Lync en Windows Phone o Apple iPhone, iPad u otros dispositivos Apple y usa el servicio de notificaciones de inserción o el servicio de notificaciones de inserción, debe planear _sipfederationtls. _ TCP. &lt;&gt;Registros SRV de dominio SIP para cada dominio SIP que tenga clientes móviles de Lync. Android y Nokia Symbian Lync Mobile no usan la notificación de inserción y no están sujetos a este requisito.

        
        </div>

  - Configure las directivas de acceso de los usuarios externos para admitir los dominios federados.

  - Abra los puertos del firewall para el protocolo de inicio de sesión (SIP), las conferencias web y los audios y vídeos, con el fin de adaptar la federación o los contactos que está habilitando. Para obtener más información, consulte: [determinar los requisitos de puerto y de Firewall a/V externos para Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

La siguiente información le ayudará a definir el certificado, el puerto o el protocolo, y los requisitos de DNS para la Federación con Microsoft Lync Server 2013 y Lync Server 2010.

La planeación de certificados, requisitos de firewall y Puerto/protocolo y requisitos de DNS es, por lo general, un proceso directo de reenvío si ha planeado o implementado los servidores perimetrales de Microsoft Lync Server 2013. Como la Federación es una característica adicional que usa el servidor perimetral existente, los requisitos de planeación suelen cumplirse con la planeación y la implementación del servidor perimetral. Use las tablas siguientes para determinar si se cumplen los requisitos, y realizar los cambios en el puerto o el protocolo y en el DNS según convenga.

<div>


> [!IMPORTANT]
> Si tiene un grupo de servidores perimetrales y está federando a los asociados de Lync Server 2013 o Lync Server 2010, puede usar equilibradores de carga de DNS o equilibradores de carga de hardware en los lados orientados internos y externos de los servidores perimetrales. Si está federando con Office Communications Server 2007 o con Office Communications Server 2007 R2, el equilibrio de carga de hardware proporcionará compatibilidad con la conmutación por error en caso de que se produce un servidor perimetral. Office Communications Server 2007 y Office Communications Server 2007 R2 no tienen en cuenta el equilibrio de carga de DNS. Los servidores perimetrales asociados establecerán la comunicación con el primer servidor perimetral del grupo que responde. Si se produce un error en ese servidor perimetral, la comunicación no realiza la conmutación por error automáticamente.



</div>

Los requisitos de certificado se suelen cumplir mediante la planeación de certificados para el servidor perimetral elegido o el plan de servidor perimetral agrupado.

</div>

<div>

## <a name="public-instant-messaging-connectivity"></a>Conectividad de mensajería instantánea pública

La conectividad de mensajería instantánea pública es una clase de Federación y está configurada para permitir que los usuarios internos y externos de Lync Server 2013 puedan agregar contactos desde cualquiera de las siguientes opciones:

  - Contactos de Messenger

  - Toolbar\! contacts

  - Contactos de America Online (AOL)

<div>


> [!IMPORTANT]
> <UL>
> <LI>
> <P>A partir del 1 de septiembre de 2012, la licencia de suscripción de usuario de la conectividad de mensajería instantánea pública de Microsoft Lync (PIC USL) ya no está disponible para la compra de contratos nuevos o de renovación. Los clientes con licencias activas podrán seguir federando a Yahoo! Messenger hasta la fecha de cierre del servicio (la fecha exacta todavía debe decidirse, pero no antes del 2013 de junio).</P>
> <LI>
> <P>La capa de PIC es una licencia por usuario, por mes, que es necesaria para que Lync Server u Office Communications Server se federe con Yahoo! Service. La capacidad de Microsoft para proporcionar este servicio ha estado supeditada al soporte de Yahoo!, el acuerdo subyacente que no se renovará.</P>
> <LI>
> <P>Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo. La Federación con Windows Live Messenger no requiere licencias de usuario o de dispositivo adicionales aparte de la CAL de Lync Standard. La Federación de Skype se agregará a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas a través de mensajería instantánea y voz.</P></LI></UL>



</div>

Esta clase de federación requiere las siguientes consideraciones de planificación:

  - Los usuarios de Windows Live Messenger pueden tener comunicación de audio/visual de punto a punto con los usuarios de Lync Server 2013, además de la mensajería instantánea. Los servidores perimetrales deben cumplir unos requisitos de puerto y protocolo específicos. Para obtener más información, consulte [determinación de requisitos de firewall y de puerto a/V externos para Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).

  - La mensajería instantánea de Yahoo no tiene requisitos únicos, excepto los que se usan normalmente en la planeación y la implementación del servidor perimetral típico que proporciona la Federación.

  - America Online requiere que el certificado del servidor perimetral asignado al servicio perimetral de acceso tenga un uso mejorado de clave (EKU) de cliente.

</div>

<div>

## <a name="extensible-messaging-and-presence-protocol-xmpp-federation"></a>Federación de protocolo extensible de mensajería y presencia (XMPP)

Las versiones anteriores de Lync Server y Office Communications Server proporcionaban una puerta de enlace de protocolo extensible de mensajería y presencia (XMPP) que se podía implementar como una función de servidor independiente para permitir la Federación con las implementaciones de XMPP. En Microsoft Lync Server 2013, la funcionalidad de XMPP puede implementarse como una característica. La funcionalidad XMPP se instala en dos partes: un proxy XMPP que se ejecuta en el servidor perimetral y la puerta de enlace XMPP que se ejecuta en los servidores front-end.

La implementación y la configuración de XMPP se trata en [Deploying external User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) planea admitir XMPP en su organización mediante la definición de reglas de puerto y protocolo en el firewall, la configuración de certificados y la adición de registros DNS. En los siguientes temas de esta sección se resume la información necesaria para planear correctamente la Federación XMPP para la implementación.

<div>


> [!IMPORTANT]
> La capacidad XMPP de Lync Server 2013 se ha probado y es compatible con Microsoft para la Federación de mensajería instantánea con Google Talk. Para cualquier otro sistema XMPP, póngase en contacto con el proveedor de terceros para comprobar que admiten la Federación con Lync Server 2013 y para cualquier recomendación sobre implementación o solución de problemas.



</div>

<div>


> [!IMPORTANT]
> La Federación de XMPP no es compatible con los usuarios hospedados en aplicaciones de sucursal con funciones de supervivencia. Esto se aplica a ver la información de presencia y a intercambiar mensajes de mensajería instantánea.



</div>

</div>

<div id="sectionSection3" class="section">

En los siguientes temas se incluyen instrucciones para definir certificados, puertos de firewall y entradas DNS para los tipos de escenarios de Federación admitidos.

  - <span></span>  
    [Resumen de certificado: SIP, Federación XMPP y mensajería instantánea pública en Lync Server 2013](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [Resumen de Puerto-SIP, Federación XMPP y mensajería instantánea pública en Lync Server 2013](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [Resumen de DNS: SIP, Federación XMPP y mensajería instantánea pública en Lync Server 2013](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a>Consulte también


[Configurar directivas para controlar el acceso de usuarios federados en Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[Escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Determinación de los requisitos de los puertos y el Firewall de A/V externos para Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[Determinación de los requisitos de DNS para Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  


[Administrar la configuración perimetral de acceso para su organización en Lync Server 2013](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[Administrar dominios federados SIP para la organización en Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[Administrar proveedores federados SIP para la organización en Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

