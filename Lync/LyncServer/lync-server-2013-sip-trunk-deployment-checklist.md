---
title: 'Lync Server 2013: Lista de comprobación de la implementación del enlace troncal SIP'
TOCTitle: Lista de comprobaciones para la implementación del enlace troncal SIP
ms:assetid: 94f4f03e-19d5-4198-92be-e4076dbb959a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398755(v=OCS.15)
ms:contentKeyID: 48276051
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lista de comprobaciones para la implementación del enlace troncal SIP para Lync Server 2013

 

_**Última modificación del tema:** 2012-09-21_

Para poder implementar un tronco SIP, primero debe intercambiar alguna información de conexión básica con su proveedor de servicios relacionada con sus respectivos extremos de tronco SIP.

Obtenga la información siguiente de cada una de las puertas de enlace del proveedor de servicios de telefonía por Internet a las que se vaya a conectar:

  - Dirección IP

  - Nombre de dominio completo (FQDN)


> [!NOTE]
> Es posible que el proveedor de servicios le pida que se conecte a más de una puerta de enlace del proveedor de servicios de telefonía por Internet. En dicho caso, deberá configurar una conexión entre cada puerta de enlace del proveedor de servicios de telefonía por Internet y cada Servidor de mediación del grupo de servidores.



La información que facilita al proveedor de servicios depende del tipo de conexión del tronco SIP:

  - En el caso de conexiones de red privadas o de conmutación multiprotocolo mediante etiquetas (MPLS, Multiprotocol Label Switching) facilite al proveedor de servicios de telefonía por Internet la dirección IP enrutable públicamente del enrutador de su red perimetral (también conocida como extranet o subred filtrada). Compruebe que la puerta de enlace o el controlador de borde de sesión (SBC) del proveedor de servicios de telefonía por Internet pueda obtener acceso a esta dirección. Asimismo, facilítele el FQDN del Servidor de mediación.

  - Para conexiones de red privada virtual (VPN), facilítele también la dirección IP del servidor VPN.

## Consideraciones de certificados

Para determinar si necesita un certificado para el enlace troncal SIP, infórmese con su proveedor de servicios de telefonía por Internet acerca de la compatibilidad con protocolos:

1.  Si solo admite el protocolo de control de transmisión (TCP), no necesita ningún certificado.

2.  Si admite el protocolo de seguridad de la capa de transporte (TLS), el proveedor de servicios de telefonía por Internet deberá proporcionarle un certificado.


> [!NOTE]
> El protocolo SIP trabaja junto con el protocolo de transporte en tiempo real (RTP) o el protocolo de transporte seguro en tiempo real (SRTP), que son los encargados de administrar los datos de voz reales en las llamadas del protocolo de Voz sobre Protocolo de Internet (VoIP).



## Proceso de implementación

Para implementar la parte de Lync Server de la conexión del tronco SIP, siga estos pasos:

1.  Mediante Lync Server  Generador de topologías, cree y configure la topología de dominio SIP. Para obtener más detalles, consulte [Definir y configurar una topología en Topology Builder para Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) en la documentación sobre implementación.

2.  Mediante el Panel de control de Lync Server, configure el enrutamiento de voz para el nuevo dominio SIP. Para obtener más detalles, consulte [Configuración de troncos en Lync Server 2013](lync-server-2013-configuring-trunks.md) en la documentación sobre implementación.

3.  Pruebe la conectividad con el cmdlet **Test-CsPstnOutboundCall**. Para más detalles, consulte la documentación sobre el Shell de administración de Lync Server o la Ayuda del Shell de administración de Lync Server.

