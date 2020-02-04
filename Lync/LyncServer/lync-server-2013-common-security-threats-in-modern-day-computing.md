---
title: 'Lync Server 2013: amenazas de seguridad comunes en los equipos informáticos modernos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Common security threats in modern day computing
ms:assetid: 56d22197-e8e2-46b8-b3a3-507bd663700e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn433220(v=OCS.15)
ms:contentKeyID: 56708403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99e17f9f6dbba30697c72fecf77fbff4bfbdc003
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742760"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="common-security-threats-in-modern-day-computing"></a>Amenazas de seguridad comunes en la informática moderna

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-09-10_

Puesto que Lync Server 2013 es un sistema de comunicaciones de clase empresarial, debe tener en cuenta los ataques de seguridad comunes que podrían afectar a su infraestructura y sus comunicaciones.

<div>

## <a name="compromised-key-attack"></a>Ataque de clave comprometida

Una clave es un código o número secreto que se usa para cifrar, descifrar o comprobar información secreta. Hay dos claves confidenciales en uso en la infraestructura de claves públicas (PKI) que deben tenerse en cuenta:

  - La clave privada que tiene cada titular de un certificado

  - La clave de sesión que se utiliza después de realizarse correctamente la identificación y el intercambio de las claves de sesión por parte de las entidades de comunicación

Un ataque de clave comprometida se produce cuando el atacante consigue la clave privada o de sesión. Cuando el atacante consigue la clave, puede usarla para descifrar datos cifrados sin que el remitente lo sepa.

Lync Server 2013 usa las características de PKI del sistema operativo Windows Server para proteger los datos clave usados para el cifrado de las conexiones de seguridad de la capa de transporte (TLS). Las claves que se usan para cifrar medios se intercambian en las conexiones TLS.

</div>

<div>

## <a name="network-denial-of-service-attack"></a>Ataque por denegación de servicio de la red

El *ataque por denegación de servicio* se produce cuando el atacante impide que los usuarios válidos usen la red de forma normal. Esto se realiza cuando el atacante inunda el servicio con solicitudes legítimas que sobrepasan el uso del servicio por parte de los usuarios legítimos. Con un ataque por denegación de servicio, el atacante puede hacer lo siguiente:

  - Enviar datos no válidos a las aplicaciones y los servicios que se ejecutan en la red que sufre el ataque para interrumpir su funcionamiento normal.

  - Enviar una gran cantidad de tráfico, lo que sobrecarga el sistema hasta que deja de responder o responde lentamente a las solicitudes legítimas.

  - Ocultar las pruebas de los ataques.

  - Impedir que los usuarios obtengan acceso a los recursos de la red.

</div>

<div>

## <a name="eavesdropping-sniffing-snooping"></a>Interceptación (rastreo o espionaje)

La *interceptación* se produce cuando un atacante obtiene acceso a la ruta de datos en una red y puede supervisar y leer el tráfico. Este tipo de ataque también se denomina *rastreo* o *espionaje*. Si el tráfico se produce como texto sin formato, el atacante puede leerlo cuando obtiene acceso a la ruta. Un ejemplo es un ataque que se realiza al controlar un enrutador de la ruta de acceso a los datos.

La recomendación predeterminada y la configuración para el tráfico dentro de Microsoft Lync Server 2013 es usar TLS Mutual (MTLS) entre los servidores de confianza y TLS del cliente al servidor. Esta medida de protección haría extremadamente difícil o imposible de realizar un ataque en el período en que tiene lugar conversación concreta. TLS autentica a todos los participantes y cifra todo el tráfico. Esto no impide la interceptación, pero el atacante no puede leer el tráfico a menos se interrumpa el cifrado.

El protocolo NAT transversal con relé (TURN) no impone el cifrado del tráfico, y la información que envía está protegida por la integridad del mensaje. Si bien este protocolo está abierto a la interceptación, la información que envía (es decir, direcciones IP y puerto) se puede extraer directamente examinando simplemente las direcciones de origen y de destino de los paquetes. El servicio perimetral A/V se asegura de que los datos son válidos comprobando la integridad del mensaje mediante la clave derivada de algunos elementos, como una contraseña TURN, la cual no se envía nunca en texto no cifrado. Si se utiliza Protocolo en tiempo real seguro (SRTP), también se cifra el tráfico de medios.

</div>

<div>

## <a name="identity-spoofing-ip-address-spoofing"></a>Suplantación de identidad (suplantación de dirección IP)

La *suplantación de identidad (spoofing)* se produce cuando el atacante identifica y usa una dirección IP de una red, un equipo o un componente de red sin tener autorización para ello. En este tipo de ataque, el atacante actúa como si fuese la entidad que hubiera identificado la dirección IP en un caso normal. En el contexto de Microsoft Lync Server 2013, esta situación entra en juego solo si un administrador ha realizado las siguientes acciones:

  - Ha configurado conexiones compatibles únicamente con el Protocolo de control de transmisión (TCP) (lo cual no se recomienda porque las comunicaciones TCP no están cifradas).

  - Ha marcado las direcciones IP de esas conexiones como hosts de confianza.

Este es un problema menor para las conexiones TLS (Seguridad de la capa de transporte), puesto que TLS autentica todas las partes y cifra todo el tráfico. El uso de TLS evita que un atacante suplante las direcciones IP en una conexión concreta (por ejemplo, conexiones Mutual TLS). Pero un atacante podría suplantar la dirección del servidor DNS que usa Lync Server 2013. Sin embargo, como la autenticación en Lync se realiza con certificados, un atacante no tendría un certificado válido necesario para suplantar a una de las partes de la comunicación.

</div>

<div>

## <a name="man-in-the-middle-attack"></a>Ataque de tipo "Man in the middle"

Un ataque de tipo "Man in the middle" se produce cuando un atacante desvía la comunicación entre dos usuarios a través del equipo del atacante sin que lo sepan esos dos usuarios. El atacante puede supervisar y leer el tráfico antes de enviarlo al destinatario previsto. Sin darse cuenta, todos los usuarios que participan en la comunicación envían tráfico al atacante y reciben tráfico del mismo pensando que la comunicación se produce únicamente con el usuario previsto. Esto puede suceder si un atacante modifica los Servicios de dominio de Active Directory para agregar su servidor como un servidor de confianza o modifica el Sistema de nombres de dominio (DNS) para que los clientes se conecten al servidor a través del atacante. Un ataque de tipo "Man in the middle" también puede producirse con tráfico multimedia entre dos clientes. Sin embargo, en Microsoft Lync Server 2013, el audio, el vídeo y el uso compartido de aplicaciones punto a punto se cifran con SRTP, usando claves criptográficas que se negocian entre los interlocutores que usan el protocolo de inicio de sesión (SIP) a través de TLS. Los servidores como los de conversaciones en grupo utilizan HTTPS para mejorar la seguridad del tráfico web.

</div>

<div>

## <a name="rtp-replay-attack"></a>Ataque de reproducción RTP

Un *ataque de reproducción* tiene lugar cuando una transmisión de medios válida entre dos partes se intercepta y retransmite con fines malintencionados. SRTP, usado en conexión con un protocolo de señalización segura, protege las transmisiones de estos ataques al permitir que el receptor tenga un índice de los paquetes RTP ya recibidos y pueda comparar cada paquete nuevo con los que figuran en dicho índice.

</div>

<div>

## <a name="spim"></a>Mensajes instantáneos no deseados

El término inglés "*spim*" hace referencia a los mensajes instantáneos comerciales no deseados o a las solicitudes de suscripción de presencia no deseadas. Si bien estos mensajes por sí mismos no son un peligro para la seguridad de la red, son como mínimo molestos, pueden reducir la disponibilidad y la productividad de los recursos, y podrían llegar a poner en peligro la red. Un ejemplo de ello es el caso de usuarios que se envían solicitudes no deseadas entre sí. Los usuarios pueden bloquearse entre sí para evitarlo, pero con la federación, si se establece un ataque coordinado de este tipo, puede ser difícil de solucionar a menos que se deshabilite la federación para el asociado.

</div>

<div>

## <a name="viruses-and-worms"></a>Virus y gusanos

Un *virus* es una unidad de código que tiene por objeto reproducir más unidades de código similares. Los virus necesitan un host, como un archivo, un correo electrónico o un programa, para poder funcionar. Un *gusano* es una unidad de código cuyo propósito es reproducir más unidades de código similares, pero no necesita un host. Los virus y los gusanos suelen aparecer principalmente durante las transferencias de archivo entre clientes o cuando otros usuarios envían direcciones URL. Si hay un virus en su equipo, podrá, por ejemplo, usar su identidad y enviar mensajes instantáneos en su nombre.

</div>

<div>

## <a name="personally-identifiable-information"></a>Información de identificación personal

Microsoft Lync Server 2013 tiene el potencial de divulgar información a través de una red pública que pueda vincularse a una persona. Dicha información se puede desglosar en dos categorías:

  - **Datos de presencia mejorados** Los datos de presencia mejorados son información que un usuario puede elegir para compartir o no a través de un vínculo a un socio federado o con los contactos de una organización. Estos datos no se comparten con los usuarios de una red de mensajería instantánea pública. Las directivas de cliente y otras opciones de configuración del cliente pueden otorgar algún tipo de control al administrador del sistema. En Lync Server 2013, el modo de privacidad de presencia mejorada se puede configurar para que un usuario individual Evite que los usuarios de Lync que no estén en la lista de contactos del usuario vean la información de presencia del usuario. El modo de privacidad de presencia mejorada no impide que los usuarios de  Microsoft Office Communicator 2007 y Microsoft Office Communicator 2007 R2 vean la información de presencia de un usuario. Para obtener más información, consulte [novedades para clientes en Lync server 2013](lync-server-2013-what-s-new-for-clients.md) en la documentación de introducción y [configuración del modo de privacidad de presencia mejorada en Lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md) en la documentación de implementación.

  - **Datos obligatorios** Los datos obligatorios son obligatorios para que el servidor o el cliente funcionen correctamente y no están bajo el control de la administración del cliente o del sistema. Se trata de información que es necesaria en un servidor o una red para el enrutamiento, el mantenimiento de estados y la señalización.

En las tablas siguientes, se muestran los datos que se exponen sobre una red pública.

### <a name="enhanced-presence-data"></a>Datos de presencia ampliada

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Datos que se divulgan</th>
<th>Posibles configuraciones</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Datos personales</p></td>
<td><p>Nombre, Puesto, Compañía, Dirección de correo electrónico, Zona horaria</p></td>
</tr>
<tr class="even">
<td><p>Números de teléfono</p></td>
<td><p>Trabajo, Móvil, Particular</p></td>
</tr>
<tr class="odd">
<td><p>Información de calendario</p></td>
<td><p>Información de disponibilidad, aviso de fuera de la oficina, detalles de las reuniones (para las personas con acceso a su calendario)</p></td>
</tr>
<tr class="even">
<td><p>Estado de presencia</p></td>
<td><p>Ausente, Disponible, No disponible, No molestar, No conectado</p></td>
</tr>
</tbody>
</table>


### <a name="mandatory-data"></a>Datos obligatorios

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Datos que se divulgan</th>
<th>Información de ejemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Dirección IP</p></td>
<td><p>Dirección real del equipo o dirección traducida</p></td>
</tr>
<tr class="even">
<td><p>URI del SIP</p></td>
<td><p>jeremylos@litwareinc.com</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

