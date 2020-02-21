---
title: 'Lync Server 2013: amenazas comunes de seguridad en el entorno informático de hoy día'
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
ms.openlocfilehash: b9869f3c903aa7b16529ed72c499a1cb41254634
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190953"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="common-security-threats-in-modern-day-computing"></a>Amenazas de seguridad comunes en el entorno informático de hoy día

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-09-10_

Dado que Lync Server 2013 es un sistema de comunicaciones de clase empresarial, debe tener en cuenta los ataques de seguridad comunes que podrían afectar a su infraestructura y comunicaciones.

<div>

## <a name="compromised-key-attack"></a>Ataque de clave comprometida

Una clave es un número o código secreto que se usa para cifrar, descifrar o validar información secreta. Hay dos claves confidenciales en uso en la infraestructura de clave pública (PKI) que se deben tener en cuenta:.

  - La clave privada que tiene cada titular del certificado

  - La clave de sesión que se usa después de una identificación correcta y el intercambio de claves de sesión por parte de los socios de comunicación

Un ataque de clave comprometida se produce cuando el atacante determina la clave privada o la clave de sesión. Cuando el atacante logra determinar la clave, la usa para descifrar los datos cifrados sin que lo sepa el remitente de los datos.

Lync Server 2013 usa las características de PKI del sistema operativo Windows Server para proteger los datos clave usados para el cifrado de las conexiones de seguridad de la capa de transporte (TLS). Las claves usadas para el cifrado de medios se intercambian a través de conexiones TLS.

</div>

<div>

## <a name="network-denial-of-service-attack"></a>Ataque por denegación de servicio de la red

El *ataque por denegación de servicio* se produce cuando el atacante evita el uso normal de la red y la función de los usuarios válidos. Esto se realiza cuando el atacante inunda el servicio con solicitudes legítimas que saturan el uso del servicio por parte de usuarios legítimos. Mediante el uso de un ataque por denegación de servicio, el atacante puede hacer lo siguiente:

  - Enviar datos no válidos a las aplicaciones y los servicios que se ejecutan en la red que sufre el ataque para interrumpir su funcionamiento normal.

  - Enviar una gran cantidad de tráfico, lo que sobrecarga el sistema hasta que deja de responder o responde lentamente a las solicitudes legítimas.

  - Ocultar las pruebas de los ataques.

  - Impedir que los usuarios obtengan acceso a los recursos de la red.

</div>

<div>

## <a name="eavesdropping-sniffing-snooping"></a>Espionaje (espionaje, espionaje)

El *espionaje* puede producirse cuando un atacante obtiene acceso a la ruta de datos en una red y tiene la capacidad de supervisar y leer el tráfico. También se denomina *rastreo* o *supervisión*. Si el tráfico se produce como texto sin formato, el atacante puede leerlo cuando obtiene acceso a la ruta. Un ejemplo es un ataque que se realiza al controlar un enrutador de la ruta de acceso a los datos.

La recomendación y configuración predeterminadas para el tráfico dentro de Microsoft Lync Server 2013 es usar TLS mutua (MTLS) entre los servidores de confianza y TLS del cliente al servidor. Esta medida protectora haría muy difícil o imposible lograr un ataque en el período en el que se produce una conversación determinada. TLS autentica a todos los participantes y cifra todo el tráfico. Esto no impide la interceptación, pero el atacante no puede leer el tráfico a menos se interrumpa el cifrado.

El protocolo de retransmisión NAT (TURN) no exige que el tráfico se cifre y que la información que envía está protegida por la integridad del mensaje. Aunque está abierto a espionaje, la información que envía (es decir, las direcciones IP y el puerto) se puede extraer directamente con solo mirar las direcciones de origen y de destino de los paquetes. El servicio perimetral A/V garantiza que los datos sean válidos mediante la comprobación de la integridad del mensaje con la clave derivada de algunos elementos, incluida una contraseña de TORNEAdo, que nunca se envía en texto no cifrado. Si se usa el protocolo seguro en tiempo real (SRTP), también se cifra el tráfico de medios.

</div>

<div>

## <a name="identity-spoofing-ip-address-spoofing"></a>Suplantación de identidad (suplantación de dirección IP)

La *suplantación de identidad* se produce cuando el atacante determina y usa una dirección IP de una red, un equipo o un componente de red sin tener autorización para ello. En este tipo de ataque, el atacante actúa como si fuese la entidad que hubiera identificado la dirección IP en un caso normal. En el contexto de Microsoft Lync Server 2013, esta situación entra en juego solo si un administrador ha hecho lo siguiente:

  - Ha configurado conexiones compatibles únicamente con el Protocolo de control de transmisión (TCP) (lo cual no se recomienda porque las comunicaciones TCP no están cifradas).

  - Ha marcado las direcciones IP de esas conexiones como hosts de confianza.

Este es un problema menor para las conexiones TLS (Seguridad de la capa de transporte), puesto que TLS autentica todas las partes y cifra todo el tráfico. El uso de TLS evita que un atacante suplante las direcciones IP en una conexión concreta (por ejemplo, conexiones Mutual TLS). Pero un atacante todavía podría suplantar la dirección del servidor DNS que usa Lync Server 2013. No obstante, puesto que la autenticación en Lync se realiza con certificados, un atacante no tendrá un certificado válido necesario para suplantar a una de las partes de la comunicación.

</div>

<div>

## <a name="man-in-the-middle-attack"></a>Ataque de tipo "Man in the middle"

Un ataque de tipo "Man in the middle" se produce cuando un atacante desvía la comunicación entre dos usuarios a través del equipo del atacante sin que lo sepan esos dos usuarios. El atacante puede supervisar y leer el tráfico antes de enviarlo al destinatario previsto. Sin darse cuenta, todos los usuarios que participan en la comunicación envían tráfico al atacante y reciben tráfico del mismo pensando que la comunicación se produce únicamente con el usuario previsto. Esto puede suceder si un atacante modifica los Servicios de dominio de Active Directory para agregar su servidor como un servidor de confianza o modifica el Sistema de nombres de dominio (DNS) para que los clientes se conecten al servidor a través del atacante. Un ataque de tipo "Man in the Middle" también puede producirse con el tráfico de medios entre dos clientes. Sin embargo, en Microsoft Lync Server 2013 uso compartido de audio, vídeo y aplicaciones punto a punto, las secuencias se cifran con SRTP, usando claves criptográficas que se negocian entre los homólogos que usan el protocolo de inicio de sesión (SIP) a través de TLS. Los servidores como los de conversaciones en grupo utilizan HTTPS para mejorar la seguridad del tráfico web.

</div>

<div>

## <a name="rtp-replay-attack"></a>Ataque de reproducción RTP

Un *ataque de reproducción* se produce cuando se intercepta y retransmite una transmisión de medios válida entre dos partes con fines malintencionados. SRTP, usado en conexión con un protocolo de señalización segura, protege las transmisiones de estos ataques al permitir que el receptor tenga un índice de los paquetes RTP ya recibidos y pueda comparar cada paquete nuevo con los que figuran en dicho índice.

</div>

<div>

## <a name="spim"></a>Solicitado

*Spim* es mensajes instantáneos comerciales no solicitados o solicitudes de suscripción de presencia. Si bien estos mensajes por sí mismos no son un peligro para la seguridad de la red, son como mínimo molestos, pueden reducir la disponibilidad y la productividad de los recursos, y podrían llegar a poner en peligro la red. Un ejemplo de ello es el caso de usuarios que se envían solicitudes no deseadas entre sí. Los usuarios pueden bloquearse entre sí para evitarlo, pero con la federación, si se establece un ataque coordinado de este tipo, puede ser difícil de solucionar a menos que se deshabilite la federación para el asociado.

</div>

<div>

## <a name="viruses-and-worms"></a>Virus y gusanos

Un *virus* es una unidad de código cuyo propósito es reproducir unidades de código similares adicionales. Los virus necesitan un host (como un archivo, un correo electrónico o un programa) para poder funcionar. Un *gusano* es una unidad de código cuyo propósito es reproducir más unidades de código similares, pero no necesita un host. Los virus y los gusanos suelen aparecer principalmente durante las transferencias de archivo entre clientes o cuando otros usuarios envían direcciones URL. Si hay un virus en su equipo, podrá, por ejemplo, usar su identidad y enviar mensajes instantáneos en su nombre.

</div>

<div>

## <a name="personally-identifiable-information"></a>Información de identificación personal

Microsoft Lync Server 2013 tiene el potencial de divulgar información a través de una red pública que pueda estar vinculada a un individuo. Dicha información se puede desglosar en dos categorías:

  - **Datos de presencia mejorados** Los datos de presencia mejorados son información que un usuario puede elegir para compartir o no a través de un vínculo a un socio federado o con contactos dentro de una organización. Estos datos no se comparten con los usuarios de una red de mensajería instantánea pública. Las directivas de cliente y otras opciones de configuración del cliente pueden otorgar algún tipo de control al administrador del sistema. En Lync Server 2013, se puede configurar el modo de privacidad de presencia mejorada para un usuario individual para impedir que los usuarios de Lync que no se encuentran en la lista de contactos del usuario vean la información de presencia del usuario. El modo de privacidad de presencia mejorada no impide que los usuarios de Microsoft Office Communicator 2007 y Microsoft Office Communicator 2007 R2 vean la información de presencia de un usuario. Para obtener más información, consulte [what's New for clients in Lync server 2013](lync-server-2013-what-s-new-for-clients.md) en la documentación de introducción y [configuración del modo de privacidad de presencia mejorada en Lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md) en la documentación sobre implementación.

  - **Datos obligatorios** Los datos obligatorios son necesarios para el correcto funcionamiento del servidor o el cliente y no están bajo el control de la administración del cliente o del sistema. Se trata de información que es necesaria en un servidor o una red para el enrutamiento, el mantenimiento de estados y la señalización.

En las tablas siguientes se enumeran los datos que se exponen a través de una red pública.

### <a name="enhanced-presence-data"></a>Datos de presencia ampliada

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Datos que se han divulgado</th>
<th>Configuración posible</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Datos personales</p></td>
<td><p>Nombre, puesto, compañía, dirección de correo electrónico, zona horaria</p></td>
</tr>
<tr class="even">
<td><p>Números de teléfono</p></td>
<td><p>Trabajo, Móvil, Particular</p></td>
</tr>
<tr class="odd">
<td><p>Información de calendario</p></td>
<td><p>Información de disponibilidad, aviso de fuera de la oficina, detalles de la reunión (para los usuarios que tienen acceso a su calendario)</p></td>
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
<th>Datos que se han divulgado</th>
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

