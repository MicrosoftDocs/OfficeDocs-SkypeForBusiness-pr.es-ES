---
title: Amenazas de seguridad comunes en la informática moderna
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Como Skype empresarial Server es un sistema de comunicaciones de clase empresarial, debe tener en cuenta los ataques de seguridad comunes que podrían afectar a su infraestructura y sus comunicaciones.
ms.openlocfilehash: 58141a735858d840acbd57e8039aa1c132dbeb8c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815678"
---
# <a name="common-security-threats-in-modern-day-computing"></a>Amenazas de seguridad comunes en la informática moderna
 
Como Skype empresarial Server es un sistema de comunicaciones de clase empresarial, debe tener en cuenta los ataques de seguridad comunes que podrían afectar a su infraestructura y sus comunicaciones.
  
## <a name="compromised-key-attack"></a>Ataque de clave comprometida

Una clave es un código o número secreto que se usa para cifrar, descifrar o comprobar información secreta. En la infraestructura de clave pública (PKI) se debe tener en cuenta dos teclas confidenciales: 
  
- La clave privada que tiene cada titular de un certificado
    
- La clave de sesión que se utiliza después de realizarse correctamente la identificación y el intercambio de las claves de sesión por parte de las entidades de comunicación
    
Un ataque de clave comprometida se produce cuando el atacante consigue la clave privada o de sesión. Cuando el atacante consigue la clave, puede usarla para descifrar datos cifrados sin que el remitente lo sepa.
  
Skype empresarial Server usa las características de PKI del sistema operativo Windows Server para proteger los datos clave usados para el cifrado de las conexiones de seguridad de la capa de transporte (TLS). Las claves que se usan para cifrar medios se intercambian en las conexiones TLS.
  
## <a name="network-denial-of-service-attack"></a>Ataque por denegación de servicio de la red

El ataque por denegación de servicio se produce cuando el atacante impide que los usuarios válidos usen la red de forma normal. Esto se realiza cuando el atacante inunda el servicio con solicitudes legítimas que sobrepasan el uso del servicio por parte de los usuarios legítimos. Con un ataque por denegación de servicio, el atacante puede hacer lo siguiente:
  
- Enviar datos no válidos a las aplicaciones y los servicios que se ejecutan en la red que sufre el ataque para interrumpir su funcionamiento normal.
    
- Enviar una gran cantidad de tráfico, lo que sobrecarga el sistema hasta que deja de responder o responde lentamente a las solicitudes legítimas.
    
- Ocultar las pruebas de los ataques.
    
- Impedir que los usuarios obtengan acceso a los recursos de la red.
    
## <a name="eavesdropping-sniffing-snooping"></a>Interceptación (rastreo o espionaje)

La interceptación se produce cuando un atacante obtiene acceso a la ruta de datos en una red y puede supervisar y leer el tráfico. Este tipo de ataque también se denomina rastreo o espionaje. Si el tráfico se produce como texto sin formato, el atacante puede leerlo cuando obtiene acceso a la ruta. Un ejemplo es un ataque que se realiza al controlar un enrutador de la ruta de acceso a los datos. 
  
La recomendación predeterminada y la configuración de tráfico de Skype empresarial Server es usar TLS Mutual (MTLS) entre los servidores de confianza y TLS del cliente al servidor. Esta medida de protección haría extremadamente difícil o imposible de realizar un ataque en el período en que tiene lugar conversación concreta. TLS autentica a todos los participantes y cifra todo el tráfico. Esto no impide la interceptación, pero el atacante no puede leer el tráfico a menos se interrumpa el cifrado.
  
El protocolo NAT transversal con relé (TURN) no impone el cifrado del tráfico, y la información que envía está protegida por la integridad del mensaje. Si bien este protocolo está abierto a la interceptación, la información que envía (es decir, direcciones IP y puerto) se puede extraer directamente examinando simplemente las direcciones de origen y de destino de los paquetes. El servicio perimetral A/V se asegura de que los datos son válidos comprobando la integridad del mensaje mediante la clave derivada de algunos elementos, como una contraseña TURN, la cual no se envía nunca en texto no cifrado. Si se utiliza Protocolo en tiempo real seguro (SRTP), también se cifra el tráfico de medios.
  
## <a name="identity-spoofing-ip-address-and-caller-id-spoofing"></a>Suplantación de identidad (dirección IP e imitación de la identificación de llamadas)

La suplantación de identidad se produce cuando el atacante determina y usa un número de teléfono de un usuario (identificador de llamada) válido o una dirección IP de una red, un equipo o un componente de red sin estar autorizado para hacerlo. Un ataque con éxito permite que el atacante opere como si el atacante es la entidad que normalmente se identifica con el número de teléfono (identificación de llamadas) o la dirección IP.

En el contexto de Skype empresarial Server, la suplantación de direcciones IP entra en juego solo si un administrador ha realizado las siguientes acciones:
  
- Ha configurado conexiones compatibles únicamente con el Protocolo de control de transmisión (TCP) (lo cual no se recomienda porque las comunicaciones TCP no están cifradas).
    
- Ha marcado las direcciones IP de esas conexiones como hosts de confianza.
    
Este es un problema menor para las conexiones TLS (Seguridad de la capa de transporte), puesto que TLS autentica todas las partes y cifra todo el tráfico. El uso de TLS evita que un atacante suplante las direcciones IP en una conexión concreta (por ejemplo, conexiones Mutual TLS). Pero un atacante podría suplantar la dirección del servidor DNS que usa Skype empresarial Server. Sin embargo, como la autenticación en Skype empresarial se realiza con certificados, un atacante no tendría un certificado válido necesario para suplantar a una de las partes de la comunicación.

Por otro lado, la imitación de la identificación de llamadas entra en juego cuando se ha establecido un enlace SIP entre un proveedor, una puerta de enlace PSTN u otro sistema PBX y Skype empresarial Server. En estos casos, Skype empresarial Server no ofrece ninguna protección para evitar la suplantación de identificación de llamadas. Esto significa que un usuario de Skype empresarial puede recibir una llamada desde el tronco del SIP con un identificador de llamada falsificado que muestra el número de teléfono o el nombre para mostrar (si se aplica la búsqueda de números invertidas) de otro usuario de Skype empresarial. La protección para ello debe aplicarse a la puerta de enlace del proveedor, RTC o PBX.
  
## <a name="man-in-the-middle-attack"></a>Ataque de tipo "Man in the middle"

Un ataque de intermediario se produce cuando un atacante redirige la comunicación entre dos usuarios a través del equipo del atacante sin el conocimiento de los dos usuarios que se comunican. El atacante puede supervisar y leer el tráfico antes de enviarlo al destinatario previsto. Sin darse cuenta, todos los usuarios que participan en la comunicación envían tráfico al atacante y reciben tráfico del mismo pensando que la comunicación se produce únicamente con el usuario previsto. Esto puede suceder si un atacante modifica los Servicios de dominio de Active Directory para agregar su servidor como un servidor de confianza o modifica el Sistema de nombres de dominio (DNS) para que los clientes se conecten al servidor a través del atacante. Un ataque de tipo "Man in the middle" también puede producirse con tráfico multimedia entre dos clientes. Sin embargo, en Skype para empresas, el audio, el vídeo y el uso compartido de aplicaciones punto a punto se cifran con SRTP, usando claves criptográficas que se negocian entre los interlocutores que usan el protocolo de inicio de sesión (SIP) a través de TLS. Los servidores como los de conversaciones en grupo utilizan HTTPS para mejorar la seguridad del tráfico web.
  
## <a name="rtp-replay-attack"></a>Ataque de reproducción RTP

Un ataque de reproducción tiene lugar cuando una transmisión de medios válida entre dos partes se intercepta y retransmite con fines malintencionados. SRTP, usado en conexión con un protocolo de señalización segura, protege las transmisiones de estos ataques al permitir que el receptor tenga un índice de los paquetes RTP ya recibidos y pueda comparar cada paquete nuevo con los que figuran en dicho índice.
  
## <a name="spim"></a>Mensajes instantáneos no deseados

El término inglés "spim" hace referencia a los mensajes instantáneos comerciales no deseados o a las solicitudes de suscripción de presencia no deseadas. Si bien estos mensajes por sí mismos no son un peligro para la seguridad de la red, son como mínimo molestos, pueden reducir la disponibilidad y la productividad de los recursos, y podrían llegar a poner en peligro la red. Un ejemplo de ello es el caso de usuarios que se envían solicitudes no deseadas entre sí. Los usuarios pueden bloquearse entre sí para evitarlo, pero con la federación, si se establece un ataque coordinado de este tipo, puede ser difícil de solucionar a menos que se deshabilite la federación para el asociado.
  
## <a name="viruses-and-worms"></a>Virus y gusanos

Un virus es una unidad de código que tiene por objeto reproducir más unidades de código similares. Los virus necesitan un host, como un archivo, un correo electrónico o un programa, para poder funcionar. Aworm es una unidad de código cuyo propósito es reproducir unidades de código similares, pero no necesita un host. Los virus y los gusanos suelen aparecer principalmente durante las transferencias de archivo entre clientes o cuando otros usuarios envían direcciones URL. Si hay un virus en su equipo, podrá, por ejemplo, usar su identidad y enviar mensajes instantáneos en su nombre.
  
## <a name="personally-identifiable-information"></a>Información de identificación personal

Skype empresarial Server tiene el potencial de divulgar información a través de una red pública que pueda vincularse a una persona. Dicha información se puede desglosar en dos categorías:
  
- **Datos de presencia mejorados** Los datos de presencia mejorados son información que un usuario puede elegir para compartir o no a través de un vínculo a un socio federado o con los contactos de una organización. Estos datos no se comparten con los usuarios de una red de mensajería instantánea pública. Las directivas de cliente y otras opciones de configuración del cliente pueden otorgar algún tipo de control al administrador del sistema. En Skype empresarial Server, el modo de privacidad de presencia mejorada se puede configurar para que un usuario individual impida que los usuarios de Skype empresarial que no estén en la lista de contactos del usuario vean la información de presencia del usuario. El modo de privacidad de presencia mejorada no impide que los usuarios de Microsoft Office Communicator 2007 y Microsoft Office Communicator 2007 R2 vean la información de presencia de un usuario. Para obtener más información sobre cómo implementar el cliente y la presencia, consulte [implementar clientes para Skype empresarial Server](../../deploy/deploy-clients/deploy-clients.md) y [planificar la mensajería instantánea y la presencia en Skype empresarial Server](../../plan-your-deployment/instant-messaging-and-presence.md).
    
- **Datos obligatorios** Los datos obligatorios son obligatorios para que el servidor o el cliente funcionen correctamente y no están bajo el control de la administración del cliente o del sistema. Se trata de información que es necesaria en un servidor o una red para el enrutamiento, el mantenimiento de estados y la señalización.
    
En las tablas siguientes, se muestran los datos que se exponen sobre una red pública.
  
**Datos de presencia ampliada**

|**Datos que se divulgan**|**Posibles configuraciones**|
|:-----|:-----|
|Datos personales  <br/> |Nombre, Puesto, Compañía, Dirección de correo electrónico, Zona horaria  <br/> |
|Números de teléfono  <br/> |Trabajo, Móvil, Particular  <br/> |
|Información de calendario  <br/> |Información de disponibilidad, aviso de fuera de la oficina, detalles de las reuniones (para las personas con acceso a su calendario)  <br/> |
|Estado de presencia  <br/> |Ausente, Disponible, No disponible, No molestar, No conectado  <br/> |
   
**Datos obligatorios**


| **Datos que se divulgan** | **Información de ejemplo**                            |
|:-------------------|:---------------------------------------------------|
| Dirección IP  <br/>  | Dirección real del equipo o dirección traducida  <br/> |
| URI del SIP  <br/>     | jeremylos@litwareinc.com  <br/>                    |

