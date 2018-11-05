---
title: Amenazas de seguridad más comunes en la informática actual
TOCTitle: Amenazas de seguridad más comunes en la informática actual
ms:assetid: 56d22197-e8e2-46b8-b3a3-507bd663700e
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn433220(v=OCS.15)
ms:contentKeyID: 56559135
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Amenazas de seguridad más comunes en la informática actual

 

_**Última modificación del tema:** 2015-03-09_

Como Lync Server 2013 es un sistema de comunicaciones de clase empresarial, debe conocer los ataques comunes a la seguridad que pueden afectar a su infraestructura y a la comunicación.

## Ataque de clave comprometida

Una clave es un número o código secreto que se usa para cifrar, descifrar o validar información secreta. Existen dos claves confidenciales en uso en la infraestructura de clave pública (PKI) que se deben tener en cuenta:

  - La clave privada que tienen los titulares de certificados

  - La clave de sesión que se usa tras una identificación correcta y un intercambio de claves de sesión entre los asociados que se comunican

Se produce un ataque de clave comprometida cuando el atacante averigua la clave privada o la clave de sesión. Cuando el atacante logra determinar la clave, la puede usar para descifrar los datos cifrados sin que lo sepa el remitente de los datos.

Lync Server 2013 usa las características de la PKI que hay en el sistema operativo de Windows Server para proteger los datos clave usados para cifrar las conexiones de Seguridad de la capa de transporte (TLS). Las claves usadas para el cifrado de medios se intercambian a través de conexiones TLS.

## Ataque por denegación de servicio de la red

Se produce un *ataque por denegación de servicio* cuando el atacante impide el uso y el funcionamiento normales de la red por parte de los usuarios válidos. Esto sucede cuando el atacante congestiona el servicio con solicitudes legítimas que saturan el servicio para que los usuarios legítimos no lo puedan usar. En un ataque por denegación de servicio, el atacante puede hacer lo siguiente:

  - Enviar datos no válidos a las aplicaciones y los servicios que se ejecutan en la red que sufre el ataque para interrumpir su funcionamiento normal.

  - Enviar una gran cantidad de tráfico, lo que sobrecarga el sistema hasta que deja de responder o empieza a responder lentamente a las solicitudes legítimas.

  - Ocultar las pruebas de los ataques.

  - Impedir que los usuarios accedan a los recursos de la red.

## Interceptación (rastreo o espionaje)

La *interceptación* se produce cuando un atacante logra acceder a la ruta de acceso de datos en una red y puede supervisar y leer el tráfico. Este tipo de ataque también se denomina *rastreo* o *espionaje*. Si el tráfico se transfiere como texto sin formato, el atacante puede leerlo cuando accede a la ruta de acceso. Un ejemplo es un ataque que se realiza al controlar un enrutador de la ruta de acceso a los datos.

La configuración y la recomendación predeterminadas para el tráfico transmitido dentro de Microsoft Lync Server 2013 es usar Mutual TLS (MTLS) entre servidores de confianza y TLS de cliente a servidor. Esta medida de protección haría muy difícil o imposible un ataque en el período de tiempo en el que se mantiene una conversación. La TLS autentica a todas las partes y cifra todo el tráfico. Esto no impide la interceptación, pero el atacante no puede leer el tráfico a menos que se interrumpa el cifrado.

El protocolo de cruce mediante retransmisión NAT (TURN) no impone el cifrado del tráfico y la información que envía está protegida por la integridad del mensaje. Si bien este protocolo está abierto a la interceptación, la información que envía (es decir, las direcciones IP y el puerto) se puede extraer directamente con solo mirar las direcciones de origen y de destino de los paquetes. El servicio perimetral A/V se asegura de que los datos sean válidos comprobando la integridad del mensaje con la clave derivada de algunos elementos, como una contraseña TURN, la cual no se envía nunca en texto no cifrado. Si se usa el protocolo seguro en tiempo real (SRTP), también se cifra el tráfico de medios.

## Suplantación de identidad (suplantación de dirección IP)

La *suplantación de identidad* se produce cuando el atacante identifica y usa una dirección IP de una red, un PC o un componente de red sin tener autorización para ello. En este tipo de ataque, el atacante actúa como si fuese la entidad que, normalmente, identifica la dirección IP. En el contexto de Microsoft Lync Server 2013, esta situación puede producirse únicamente si un administrador:

  - Ha configurado conexiones compatibles solo con el protocolo de control de transmisión (TCP) (lo cual no se recomienda porque las comunicaciones TCP no están cifradas).

  - Ha marcado las direcciones IP de esas conexiones como hosts de confianza.

Este es un problema menor para las conexiones TLS (seguridad de la capa de transporte), puesto que la TLS autentica a todas las partes y cifra todo el tráfico. El uso de TLS evita que un atacante suplante las direcciones IP en una conexión concreta (por ejemplo, conexiones Mutual TLS), pero no evita que suplante la dirección del servidor DNS que usar Lync Server 2013. No obstante, como la autenticación en Lync se hace con certificados, un atacante no tendría un certificado válido necesario para suplantar a una de las partes de la comunicación.

## Ataque de tipo "Man in the middle"

Un ataque de tipo "Man in the middle" se produce cuando un atacante redistribuye la comunicación entre dos usuarios a través del PC del atacante sin que lo sepan esos dos usuarios. El atacante puede supervisar y leer el tráfico antes de enviarlo al destinatario previsto. Sin darse cuenta, todos los usuarios que participan en la comunicación envían tráfico al atacante y reciben tráfico del él pensando que la comunicación se produce únicamente con el usuario previsto. Esto puede suceder si un atacante modifica los Servicios de dominio de Active Directory para agregar su servidor como servidor de confianza o modifica el Sistema de nombres de dominio (DNS) para que los clientes se conecten al servidor a través del atacante. Un ataque de tipo "Man in the middle" también puede producirse con tráfico multimedia entre dos clientes. Sin embargo, en Microsoft Lync Server 2013, las secuencias de audio, vídeo y uso compartido de aplicaciones punto a punto se cifran con SRTP usando claves criptográficas que se negocian entre los pares que usan el protocolo de inicio de sesión (SIP) sobre TLS. Servidores como los de chat en grupo usan HTTPS para mejorar la seguridad del tráfico web.

## Ataque de reproducción RTP

Un *ataque de reproducción* tiene lugar cuando una transmisión de medios válida entre dos partes se intercepta y retransmite con fines malintencionados. SRTP, usado con un protocolo de señalización segura, protege las transmisiones de estos ataques al permitir que el receptor tenga un índice de los paquetes RTP ya recibidos y pueda comparar cada paquete nuevo con los que figuran en dicho índice.

## Mensajes instantáneos no deseados

Los *mensajes instantáneos no deseados* son mensajes instantáneos comerciales no deseados o solicitudes de suscripción de presencia no deseadas. Si bien estos mensajes por sí mismos no son un peligro para la seguridad de la red, son, como mínimo, molestos, pueden reducir la disponibilidad y productividad de los recursos, y podrían llegar a afectar a la red. Un ejemplo de ello es el caso de usuarios que se envían solicitudes no deseadas entre sí. Los usuarios pueden bloquearse entre sí para evitarlo, pero con la federación, si se establece un ataque coordinado de este tipo, puede ser difícil de solucionar a menos que se deshabilite la federación para el asociado.

## Virus y gusanos

Un *virus* es una unidad de código que tiene por objeto reproducir más unidades de código similares. Los virus necesitan un host (como un archivo, un correo o un programa) para poder funcionar. Un *gusano* es, también, una unidad de código cuya finalidad es reproducir más unidades de código similares, pero no precisa de un host. Los virus y los gusanos suelen aparecer principalmente durante las transferencias de archivos entre clientes o cuando otros usuarios envían direcciones URL. Si hay un virus en su PC, podrá, por ejemplo, usar su identidad y enviar mensajes instantáneos en su nombre.

## Información de identificación personal

Microsoft Lync Server 2013 puede divulgar, a través de una red pública, información que se pueda asociar a una persona. Los tipos de información se pueden dividir en dos categorías:

  - **Datos de presencia mejorada:** los datos de presencia mejorada hacen referencia a la información que el usuario decide compartir o no con los asociados federados o los contactos dentro de una organización. Estos datos no se comparten con los usuarios de una red de mensajería instantánea pública. Las directivas de cliente y otras opciones de configuración del cliente pueden otorgar algún tipo de control al administrador del sistema. En Lync Server 2013, se puede configurar el modo de privacidad de presencia mejorada para un usuario concreto para evitar que los usuarios de Lync que no estén en la lista de contactos del usuario vean la información de presencia del usuario. El modo de privacidad de presencia mejorada no impide que los usuarios de Microsoft Office Communicator 2007 y Microsoft Office Communicator 2007 R2 vean la información de presencia de un usuario. Para más información, vea [Novedades para clientes en Lync Server 2013](lync-server-2013-what-s-new-for-clients.md) en la documentación de introducción y [Configurar el modo de privacidad de presencia mejorada](lync-server-2013-configuring-enhanced-presence-privacy-mode.md) en la documentación de implementación.

  - **Datos obligatorios:** los datos obligatorios son los que se requieren para el buen funcionamiento del servidor o cliente y NO están bajo el control de la administración del sistema ni del cliente. Se trata de información es necesaria en un servidor o una red para el enrutamiento, el mantenimiento de estados y la señalización.

Las tablas siguientes recogen los datos que se exponen a través de una red pública.

### Datos de presencia mejorada

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Datos divulgados</th>
<th>Posibles configuraciones</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Datos personales</p></td>
<td><p>Nombre, Puesto, Compañía, Dirección de correo, Zona horaria</p></td>
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


### Datos obligatorios

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Datos divulgados</th>
<th>Información de ejemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Dirección IP</p></td>
<td><p>Dirección real del PC o dirección traducida con NAT</p></td>
</tr>
<tr class="even">
<td><p>URI del SIP</p></td>
<td><p>jeremylos@litwareinc.com</p></td>
</tr>
</tbody>
</table>

