---
title: Amenazas de seguridad comunes en la informática moderna
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/22/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 56d22197-e8e2-46b8-b3a3-507bd663700e
description: Como Skype Empresarial Server es un sistema de comunicaciones de clase empresarial, debe tener en cuenta los ataques de seguridad comunes que pueden afectar a su infraestructura y comunicaciones.
ms.openlocfilehash: d2eff9346c1c2d00af9fb0789f652dfe072702f0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832230"
---
# <a name="common-security-threats-in-modern-day-computing"></a>Amenazas de seguridad comunes en la informática moderna
 
Como Skype Empresarial Server es un sistema de comunicaciones de clase empresarial, debe tener en cuenta los ataques de seguridad comunes que pueden afectar a su infraestructura y comunicaciones.
  
## <a name="compromised-key-attack"></a>Ataque de clave comprometida

Una clave es un número o código secreto que se usa para cifrar, descifrar o validar información secreta. Hay dos claves confidenciales en uso en la infraestructura de clave pública (PKI) que se deben tener en cuenta: 
  
- La clave privada que tiene cada titular de certificado
    
- La clave de sesión que se usa después de un intercambio de claves de sesión y de identificación correctos por parte de los socios que se comunican
    
Un ataque de clave comprometida se produce cuando el atacante determina la clave privada o la clave de sesión. Cuando el atacante logra determinar la clave, la usa para descifrar los datos cifrados sin que lo sepa el remitente de los datos.
  
Skype Empresarial Server usa las características de PKI del sistema operativo Windows Server para proteger los datos clave usados para el cifrado de las conexiones de Seguridad de la capa de transporte (TLS). Las claves usadas para el cifrado de medios se intercambian a través de conexiones TLS.
  
## <a name="network-denial-of-service-attack"></a>Ataque por denegación de servicio de la red

El ataque por denegación de servicio se produce cuando el atacante impide el uso y el funcionamiento normales de la red por parte de los usuarios válidos. Esto se hace cuando el atacante inunda el servicio con solicitudes legítimas que saturan el uso del servicio por parte de usuarios legítimos. Al usar un ataque por denegación de servicio, el atacante puede hacer lo siguiente:
  
- Enviar datos no válidos a las aplicaciones y los servicios que se ejecutan en la red que sufre el ataque para interrumpir su funcionamiento normal.
    
- Enviar una gran cantidad de tráfico, lo que sobrecarga el sistema hasta que deja de responder o responde lentamente a las solicitudes legítimas.
    
- Ocultar las pruebas de los ataques.
    
- Impedir que los usuarios obtengan acceso a los recursos de la red.
    
## <a name="eavesdropping-sniffing-snooping"></a>Interceptación (esnifación, espionaje)

La interceptación se produce cuando un atacante obtiene acceso a la ruta de datos en una red y puede supervisar y leer el tráfico. Este tipo de ataque también se denomina rastreo o espionaje. Si el tráfico se produce como texto sin formato, el atacante puede leerlo cuando obtiene acceso a la ruta. Un ejemplo es un ataque que se realiza al controlar un enrutador de la ruta de acceso a los datos. 
  
La recomendación y configuración predeterminadas para el tráfico dentro de Skype Empresarial Server es usar tls mutua (MTLS) entre servidores de confianza y TLS de cliente a servidor. Esta medida de protección haría que un ataque sea muy difícil o imposible de lograr en el período de tiempo en que se produce una conversación determinada. TLS autentica a todos los participantes y cifra todo el tráfico. Esto no impide la interceptación, pero el atacante no puede leer el tráfico a menos se interrumpa el cifrado.
  
El protocolo Nat de retransmisión (TURN) de traversal no exige cifrar el tráfico y la información que envía está protegida por la integridad del mensaje. Aunque está abierto a interceptaciones, la información que envía (es decir, las direcciones IP y el puerto) se puede extraer directamente simplemente mirando las direcciones de origen y destino de los paquetes. El servicio perimetral A/V garantiza que los datos son válidos comprobando la integridad del mensaje mediante la clave derivada de algunos elementos, incluida una contraseña TURN, que nunca se envía en texto no cifrado. Si se usa el Protocolo seguro en tiempo real (SRTP), el tráfico de medios también se cifra.
  
## <a name="identity-spoofing-ip-address-and-caller-id-spoofing"></a>Suplantación de identidad (dirección IP y suplantación de identidad del identificador de llamada)

La suplantación de identidad se produce cuando el atacante determina y usa un número de teléfono de un usuario válido (identificador de llamada) o una dirección IP de un componente de red, equipo o red sin tener autorización para hacerlo. Un ataque correcto permite que el atacante funcione como si fuera la entidad identificada normalmente por el número de teléfono (id. de autor de la llamada) o la dirección IP.

En el contexto de Skype Empresarial Server, la suplantación de direcciones IP solo entra en juego si un administrador ha realizado las dos acciones siguientes:
  
- Ha configurado conexiones compatibles únicamente con el Protocolo de control de transmisión (TCP) (lo cual no se recomienda porque las comunicaciones TCP no están cifradas).
    
- Ha marcado las direcciones IP de esas conexiones como hosts de confianza.
    
Este es un problema menor para las conexiones TLS (Seguridad de la capa de transporte), puesto que TLS autentica todas las partes y cifra todo el tráfico. El uso de TLS evita que un atacante suplante las direcciones IP en una conexión concreta (por ejemplo, conexiones Mutual TLS). Pero un atacante aún podría suplantación de la dirección del servidor DNS que usa Skype Empresarial Server. Sin embargo, dado que la autenticación en Skype Empresarial se realiza con certificados, un atacante no tendría un certificado válido necesario para suplantación de identidad de una de las partes de la comunicación.

Por otro lado, la suplantación de identidad del autor de la llamada entra en juego cuando se ha establecido un tronco SIP entre un proveedor, una puerta de enlace RTC u otro sistema PBX y Skype Empresarial Server. En estos casos, Skype Empresarial Server no ofrece ninguna protección para evitar la suplantación de identidad del autor de la llamada. Esto significa que un usuario de Skype Empresarial puede recibir una llamada desde el tronco SIP con un identificador de llamada suplantado que muestra el número de teléfono o el nombre para mostrar (si se aplica la búsqueda inversa de números) de otro usuario de Skype Empresarial. La protección debe aplicarse en el lado del proveedor, en la puerta de enlace RTC o PBX.
  
## <a name="man-in-the-middle-attack"></a>Ataque de tipo "Man in the middle"

Un ataque de tipo "man in the middle" se produce cuando un atacante desvía la comunicación entre dos usuarios a través del equipo del atacante sin que los dos usuarios se comuniquen. El atacante puede supervisar y leer el tráfico antes de enviarlo al destinatario previsto. Sin darse cuenta, todos los usuarios que participan en la comunicación envían tráfico al atacante y reciben tráfico del mismo pensando que la comunicación se produce únicamente con el usuario previsto. Esto puede suceder si un atacante modifica los Servicios de dominio de Active Directory para agregar su servidor como un servidor de confianza o modifica el Sistema de nombres de dominio (DNS) para que los clientes se conecten al servidor a través del atacante. Un ataque de tipo "man in the middle" también puede producirse con tráfico de medios entre dos clientes. Sin embargo, en Skype Empresarial Server punto a punto de audio, vídeo y uso compartido de aplicaciones, las secuencias se cifran con SRTP, mediante claves criptográficas que se negocian entre los sistemas del mismo nivel que usan el Protocolo de inicio de sesión (SIP) a través de TLS. Los servidores como los de conversaciones en grupo utilizan HTTPS para mejorar la seguridad del tráfico web.
  
## <a name="rtp-replay-attack"></a>Ataque de reproducción RTP

Un ataque de reproducción tiene lugar cuando una transmisión de medios válida entre dos partes se intercepta y retransmite con fines malintencionados. SRTP, usado en conexión con un protocolo de señalización segura, protege las transmisiones de estos ataques al permitir que el receptor tenga un índice de los paquetes RTP ya recibidos y pueda comparar cada paquete nuevo con los que figuran en dicho índice.
  
## <a name="spim"></a>Spim

El término inglés "spim" hace referencia a los mensajes instantáneos comerciales no deseados o a las solicitudes de suscripción de presencia no deseadas. Si bien estos mensajes por sí mismos no son un peligro para la seguridad de la red, son como mínimo molestos, pueden reducir la disponibilidad y la productividad de los recursos, y podrían llegar a poner en peligro la red. Un ejemplo de ello es el caso de usuarios que se envían solicitudes no deseadas entre sí. Los usuarios pueden bloquearse entre sí para evitarlo, pero con la federación, si se establece un ataque coordinado de este tipo, puede ser difícil de solucionar a menos que se deshabilite la federación para el asociado.
  
## <a name="viruses-and-worms"></a>Virus y gusanos

Un virus es una unidad de código que tiene por objeto reproducir más unidades de código similares. Los virus necesitan un host (como un archivo, un correo electrónico o un programa) para poder funcionar. A talon es una unidad de código cuyo propósito es reproducir unidades de código adicionales y similares, pero no necesita un host. Los virus y los gusanos suelen aparecer principalmente durante las transferencias de archivo entre clientes o cuando otros usuarios envían direcciones URL. Si hay un virus en su equipo, podrá, por ejemplo, usar su identidad y enviar mensajes instantáneos en su nombre.
  
## <a name="personally-identifiable-information"></a>Información de identificación personal

Skype Empresarial Server puede revelar información a través de una red pública que pueda vincularse a una persona. Dicha información se puede desglosar en dos categorías:
  
- **Datos de presencia mejorada** Los datos de presencia mejorada son información que un usuario puede decidir compartir o no a través de un vínculo a un socio federado o con contactos dentro de una organización. Estos datos no se comparten con los usuarios de una red de mensajería instantánea pública. Las directivas de cliente y otras opciones de configuración del cliente pueden otorgar algún tipo de control al administrador del sistema. En Skype Empresarial Server, se puede configurar el modo de privacidad de presencia mejorada para un usuario individual con el fin de evitar que los usuarios de Skype Empresarial que no estén en la lista de contactos del usuario vean la información de presencia del usuario. El modo de privacidad de presencia mejorada no impide que los usuarios de Microsoft Office Communicator 2007 y Microsoft Office Communicator 2007 R2 vean la información de presencia de un usuario. Para obtener más información sobre cómo implementar el cliente y la presencia, consulte Implementar clientes para Skype Empresarial [Server](../../deploy/deploy-clients/deploy-clients.md) y Planear la mensajería instantánea y la presencia [en Skype Empresarial Server.](../../plan-your-deployment/instant-messaging-and-presence.md)
    
- **Datos obligatorios** Los datos obligatorios son necesarios para el correcto funcionamiento del servidor o del cliente y NO están bajo el control de la administración del cliente o del sistema. Se trata de información que es necesaria en un servidor o una red para el enrutamiento, el mantenimiento de estados y la señalización.
    
En las tablas siguientes se muestran los datos que se exponen a través de una red pública.
  
**Datos de presencia ampliada**

|**Datos divulgados**|**Configuración posible**|
|:-----|:-----|
|Datos personales  <br/> |Nombre, título, compañía, dirección de correo electrónico, zona horaria  <br/> |
|Números de teléfono  <br/> |Trabajo, Móvil, Particular  <br/> |
|Información de calendario  <br/> |Aviso de disponibilidad, fuera de la ciudad, detalles de la reunión (para aquellos que tienen acceso a su calendario)  <br/> |
|Estado de presencia  <br/> |Ausente, Disponible, No disponible, No molestar, No conectado  <br/> |
   
**Datos obligatorios**


| **Datos divulgados** | **Información de ejemplo**                            |
|:-------------------|:---------------------------------------------------|
| Dirección IP  <br/>  | Dirección real del equipo o dirección traducida  <br/> |
| URI del SIP  <br/>     | jeremylos@litwareinc.com  <br/>                    |

