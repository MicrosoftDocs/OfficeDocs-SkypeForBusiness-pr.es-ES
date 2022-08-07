---
title: Planear puerta de enlace SIP
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/30/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Obtenga más información sobre la puerta de enlace SIP, como los requisitos y ventajas.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: adcaee64e2a95d41229afe580624c6798547cb85
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271705"
---
# <a name="plan-for-sip-gateway"></a>Planear la puerta de enlace SIP

Sip Gateway permite a su organización usar cualquier dispositivo SIP compatible con Microsoft Teams para conservar sus inversiones en dispositivos SIP. Ahora puede iniciar sesión en Teams con sus credenciales corporativas y realizar y recibir llamadas con un dispositivo SIP compatible. Los dispositivos compatibles se pueden Skype for Business teléfonos IP con firmware SIP estándar, teléfonos IP Cisco con firmware SIP multiplataforma o dispositivos SIP de proveedores como Poly, Yealink y AudioCodes. Para obtener información sobre cómo configurar los dispositivos SIP para puerta de enlace SIP, consulte [Configurar puerta de enlace SIP](sip-gateway-configure.md).

## <a name="benefits-of-sip-gateway"></a>Ventajas de la puerta de enlace SIP

SIP Gateway conecta dispositivos SIP compatibles a Teams para ayudar a los usuarios a migrar sin problemas a la telefonía de Teams. Con puerta de enlace SIP, los usuarios pueden hacer lo siguiente:

- **Realizar llamadas:** Los usuarios de dispositivos SIP pueden realizar llamadas a la red telefónica conmutada (RTC), a otros dispositivos SIP y a teams y usuarios de Skype for Business. Los usuarios de dispositivos SIP solo pueden llamar a usuarios con números de teléfono.
- **Recibir llamadas:** Los usuarios de dispositivos SIP pueden recibir una llamada desde RTC, desde Teams o Skype for Business usuarios que tengan dispositivos SIP, y desde Teams y Skype for Business aplicaciones cliente. El dispositivo SIP actúa como punto de conexión de Teams. Las llamadas entrantes también se bifurcarán en el dispositivo SIP del usuario.
- **Varias llamadas simultáneas:** Un usuario de un dispositivo SIP en una llamada puede poner la llamada en espera para realizar o recibir otras llamadas. Un usuario de dispositivo SIP también puede conferenciar dos llamadas.
- **No molestar:** Un usuario de dispositivo SIP puede establecer No molestar en el dispositivo para que el dispositivo no suene para las llamadas entrantes. Esto no afecta al estado del usuario en el resto de los puntos de conexión de Teams.
- **Mantener/Reanudar y Silenciar/Reactivar audio:** Un usuario de dispositivo SIP puede retener y reanudar o silenciar y reactivar el audio de una llamada mediante las características de esas acciones en el dispositivo.
- **Mensaje de voz:** Los usuarios de dispositivos SIP pueden escuchar los mensajes de voz almacenados electrónicamente que los autores de llamadas dejan para ellos.
- **Indicador de mensaje en espera:** Los usuarios de dispositivos SIP pueden recibir notificaciones que les alertan cuando tienen nuevos mensajes de correo de voz.
- **Inicio y cierre de sesión:** Los usuarios de dispositivos SIP pueden iniciar y cerrar sesión en Teams en el dispositivo.
- **Multifrecuencia de tono dual:** Los usuarios de dispositivos SIP pueden presionar las teclas numéricas para proporcionar entrada durante las llamadas interactivas de respuesta de voz.
- **Reuniones de Teams:** Un usuario de dispositivo SIP puede unirse a una reunión de Teams marcando el número de acceso a la reunión. Los participantes de la reunión pueden agregar un usuario de dispositivo SIP a la reunión llamando al número de teléfono del usuario o simplemente agregando un participante haciendo clic en "Solicitar unirse" también avisará al dispositivo SIP del usuario. Los usuarios invitados de otra organización pueden ser agregados a una reunión de Teams por un participante que llama al número de un usuario invitado para incluirlo.
- **Transferencias de llamadas:** Los usuarios de dispositivos SIP pueden transferir llamadas. Sip Gateway admite transferencias ciegas y consultivas.
- **Desvío de llamadas local:** Un usuario de dispositivo SIP puede establecer reglas de reenvío (siempre, en tiempo de espera y ocupado) para el dispositivo. Si el dispositivo está conectado a la puerta de enlace SIP, la llamada se redirigirá a la dirección de destino en función de la regla que establezca el usuario del dispositivo. Para que el desvío de llamadas local funcione, el administrador debe establecer el `AllowCallRedirect` atributo en `Set-CsTeamsCallingPolicy` `Enabled`.
- **Dispositivos obsoletos fuera del tablero:** Sip Gateway admite el apagado automático de dispositivos obsoletos aprovisionados para un espacio empresarial. Los dispositivos emparejados (con sesión iniciada) se desconectarán si no están conectados durante 30 días y los dispositivos desemparejos (cerrados) después de 14 días. Un dispositivo offboarded se puede volver a incorporar después de un restablecimiento de fábrica.

## <a name="requirements-to-use-sip-gateway"></a>Requisitos para usar puerta de enlace SIP

Los usuarios de Teams deben tener un número de teléfono con las llamadas RTC habilitadas para usar la puerta de enlace SIP.

> [!NOTE]
> Sip Gateway no está disponible para entornos gubernamentales (GCC, GCC High y DoD).

### <a name="hardware-software-and-licenses"></a>Hardware, software y licencias

Si tiene un dispositivo SIP o 3PIP, debe tener:

- Una licencia de Phone System (a través de E5 o una licencia independiente)
- Habilitación de RTC (es decir, un número de teléfono) a través de un plan de llamadas de Microsoft Teams, enrutamiento directo o conexión de operadores
- Una licencia de Teléfono de área común para cualquier dispositivo de área común

## <a name="compatible-devices"></a>Dispositivos compatibles

|Proveedor    |Modelo      |Versión mínima de firmware|Versión de firmware aprobada|Notas|Vínculos|
|----------|-----------|------------|-----------|------------|------------|
|**Cisco** |           |            |           |Los dispositivos que ejecutan el firmware de empresa deben convertirse en firmware de multiplataforma. Lee la guía de la derecha para saber cómo hacerlo.|[Guía de conversión de firmware de Cisco](https://www.cisco.com/c/en/us/products/collateral/collaboration-endpoints/unified-ip-phone-7800-series/guide-c07-742786.html)|
|          |8832       |11.3.5MPP   |11.3.5MPP  |   |   |
|          |6821       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |7811       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |7821       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |7841       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |7861       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |8811       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |8841       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |8845       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |8851       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |8861       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |8865       |11.1.1MPP   |11-3-3MPP  |   |   |
|**Polivinílico**  |           |            |           |El dispositivo se reiniciará automáticamente e instalará el firmware seleccionado.|   |
|          |Trio 8500  |5.9.5.3182  |7.1.1.0997 |   |   |
|          |Trio 8800  |5.9.5.3182  |7.1.1.0997 |   |   |
|          |VVX150<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX201<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX250<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX300     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX301<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX310     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX311<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX350<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX400     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX401<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX410     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX411<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX450<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX500     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX501<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX600     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX601<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |Rove B2    |8.0.3.0009  |8.0.3.0009 |   |   |
|          |Rove B4    |8.0.3.0009  |8.0.3.0009 |   |   |
|          |Rove 30    |8.0.3.0009  |8.0.3.0009 |   |   |
|          |Rove 40    |8.0.3.0009  |8.0.3.0009 |   |   |
|**Yealink**|          |            |           |   |[Soporte técnico de Yealink](https://support.yealink.com/)|
|          |T40P       |83          |54.84.0.125|   |   |
|          |T41S       |83          |66.85.0.5  |   |   |
|          |T41S       |83          |66.85.0.5  |   |   |
|          |T41S       |83          |66.85.0.5  |   |   |
|          |T42G       |83          |29.83.0.130|   |   |
|          |T42S       |83          |66.85.0.5  |   |   |
|          |T42U<sup>1</sup>      |83          |108.86.0.20|   |   |
|          |T43U<sup>1</sup>      |83          |108.86.0.20|   |   |
|          |T46S       |83          |66.85.0.5  |   |   |
|          |T46U<sup>1</sup>      |83          |108.86.0.20|   |   |
|          |T48S       |83          |66.85.0.5  |   |   |
|          |T48G       |83          |35.83.0.130|   |   |
|          |T48U<sup>1</sup>      |83          |108.86.0.20|   |   |
|          |T53        |83          |96.85.0.5  |   |   |
|          |T53W       |83          |96.85.0.5  |   |   |
|          |T54W       |83          |96.85.0.5  |   |   |
|          |T57W       |83          |96.85.0.5  |   |   |
|          |T21P       |83          |52.84.0.140|   |   |
|          |T21P_E2    |83          |52.84.0.140|   |   |
|          |T23G       |83          |44.84.0.140|   |   |
|          |T27G       |83          |69.85.0.5  |   |   |
|          |T29G       |83          |46.83.0.130|   |   |
|          |T30        |83          |124.85.0.40|   |   |
|          |T30P       |83          |124.85.0.40|   |   |
|          |T31G       |83          |124.85.0.40|   |   |
|          |T31P       |83          |124.85.0.40|   |   |
|          |T33G       |83          |124.85.0.40|   |   |
|          |T40G       |83          |76.84.0.125|   |   |
|          |T41P       |83          |36.83.0.120|   |   |
|          |T46G       |83          |28.83.0.130|   |   |
|**AudioCodes**|       |            |           |Algunos dispositivos SIP de AudioCodes necesitan una configuración de url de aprovisionamiento. Descarga e instala archivos de actualización para los dispositivos AudioCodes afectados a la derecha. |[Archivos descargables para dispositivos afectados en AudioCodes](https://audiocodes.sharefile.com/share/view/sc9cdf17f9ec45d09/fo7914a2-4f3a-4000-8957-47bd6f35a3a5)|
|          |405<sup>1</sup>        |2.2.8      |2.2.16.570 |   |   |
|          |405HD<sup>1</sup>      |3.2.1      |2.2.16.570 |   |   |
|          |420HD<sup>1</sup>      |3.2.1      |2.2.16.570 |   |   |
|          |430HD<sup>1</sup>      |3.2.1      |2.2.16.570 |   |   |
|          |440HD<sup>1</sup>      |3.2.1      |2.2.16.570 |   |   |
|          |450HD<sup>1</sup>      |3.2.1      |3.4.6.687  |   |   |
|          |C450HD<sup>1</sup>     |3.2.1      |3.4.6.687  |   |   |
|          |445HD<sup>1</sup>      |3.2.1      |3.4.6.687  |   |   |
|          |RX50<sup>1</sup>       |3.2.1      |3.4.6.687  |   |   |
|**Spectralink**|       |           |           |   |[Soporte técnico de Spectralink](https://support.spectralink.com)|
|          |7202        |PCS22B     |PCS22B     |Auricular |   |
|          |7212        |PCS22B     |PCS22B     |Auricular |   |
|          |7502        |PCS22B     |PCS22B     |Auricular |   |
|          |7522        |PCS22B     |PCS22B     |Auricular |   |
|          |7532        |PCS22B     |PCS22B     |Auricular |   |
|          |7622        |PCS22B     |PCS22B     |Auricular |   |
|          |7642        |PCS22B     |PCS22B     |Auricular |   |
|          |7722        |PCS22B     |PCS22B     |Auricular |   |
|          |7742        |PCS22B     |PCS22B     |Auricular |   |
|          |IP-DECT Server 200 |PCS22Ab |PCS22Ab |Servidor IP-DECT |   |
|          |IP-DECT Server 400 |PCS22Ab |PCS22Ab |Servidor IP-DECT |   |
|          |IP-DECT Server 6500 |PCS22Ab |PCS22Ab |Servidor IP-DECT |   |
|          |Virtual IP-DECT Server One |PCS22Ab |PCS22Ab |Servidor IP-DECT |   |
|          |Estación base IP-DECT |PCS22Ab |PCS22Ab |Servidor IP-DECT |   |

<sup>1</sup> El dispositivo admite llamadas de emergencia dinámicas (E911) con puerta de enlace SIP.

> [!NOTE]
> Los clientes pueden utilizar AudioCodes OVOC y Poly Lens para administrar la configuración del lado del dispositivo de sus dispositivos de la serie AudioCodes 400 y Poly VVX/Trio respectivamente.

> [!NOTE]
> Los dispositivos Spectralink reciben actualizaciones de firmware en el aire de los servidores IP-DECT de Spectralink.

> [!NOTE]
> Para consultas de soporte técnico, los clientes que usen sistemas IP-DECT con Puerta de enlace SIP de Teams deben ponerse en contacto con el fabricante de DECT o con sus socios del canal de implementación.

> [!NOTE]
> Para algunos dispositivos, la versión mínima de firmware es mayor que la versión de firmware aprobada. Esto se debe a que la versión 3.X es la versión Skype for Business. Actualizamos la versión SIP que es 2.X.
