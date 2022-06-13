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
ms.openlocfilehash: a715e913966040c5406901403b90d5a6a421e2e4
ms.sourcegitcommit: 91cfb1a9c527d605300580c3acad63834ee54682
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/13/2022
ms.locfileid: "66045879"
---
# <a name="plan-for-sip-gateway"></a>Planear la puerta de enlace SIP

Sip Gateway permite a su organización usar cualquier dispositivo SIP compatible con Microsoft Teams para conservar sus inversiones en dispositivos SIP. Ahora puede iniciar sesión en Teams con sus credenciales corporativas y realizar y recibir llamadas con un dispositivo SIP compatible. Los dispositivos compatibles pueden ser Skype Empresarial teléfonos IP con firmware SIP estándar, teléfonos IP Cisco con firmware SIP multiplataforma o dispositivos SIP de proveedores como Poly, Yealink y AudioCodes. Para obtener información sobre cómo configurar los dispositivos SIP para puerta de enlace SIP, consulte [Configurar puerta de enlace SIP](sip-gateway-configure.md).

## <a name="benefits-of-sip-gateway"></a>Ventajas de la puerta de enlace SIP

Sip Gateway conecta dispositivos SIP compatibles a Teams para ayudar a los usuarios a migrar sin problemas a Teams telefonía. Con puerta de enlace SIP, los usuarios pueden hacer lo siguiente:

- **Realizar llamadas:** Los usuarios de dispositivos SIP pueden realizar llamadas a la red telefónica conmutada (RTC), a otros dispositivos SIP y a usuarios de Teams y Skype Empresarial. Los usuarios de dispositivos SIP solo pueden llamar a usuarios con números de teléfono.
- **Recibir llamadas:** Los usuarios de dispositivos SIP pueden recibir una llamada de RTC, de usuarios de Teams o Skype Empresarial que tengan dispositivos SIP, así como de aplicaciones cliente de Teams y Skype Empresarial. El dispositivo SIP actúa como un punto de conexión Teams. Las llamadas entrantes también se bifurcarán en el dispositivo SIP del usuario.
- **Varias llamadas simultáneas:** Un usuario de un dispositivo SIP en una llamada puede poner la llamada en espera para realizar o recibir otras llamadas. Un usuario de dispositivo SIP también puede conferenciar dos llamadas.
- **No molestar:** Un usuario de dispositivo SIP puede establecer No molestar en el dispositivo para que el dispositivo no suene para las llamadas entrantes. Esto no tiene ningún impacto en el estado del usuario en todos los demás puntos de conexión de Teams.
- **Mantener/Reanudar y Silenciar/Reactivar audio:** Un usuario de dispositivo SIP puede retener y reanudar o silenciar y reactivar el audio de una llamada mediante las características de esas acciones en el dispositivo.
- **Mensaje de voz:** Los usuarios de dispositivos SIP pueden escuchar los mensajes de voz almacenados electrónicamente que los autores de llamadas dejan para ellos.
- **Indicador de mensaje en espera:** Los usuarios de dispositivos SIP pueden recibir notificaciones que les alertan cuando tienen nuevos mensajes de correo de voz.
- **Inicio y cierre de sesión:** Los usuarios de dispositivos SIP pueden iniciar y cerrar sesión en Teams en el dispositivo.
- **Multifrecuencia de tono dual:** Los usuarios de dispositivos SIP pueden presionar las teclas numéricas para proporcionar entrada durante las llamadas interactivas de respuesta de voz.
- **Teams reuniones:** un usuario de dispositivo SIP puede unirse a una reunión de Teams marcando el número de acceso a la reunión. Los participantes de la reunión pueden agregar un usuario de dispositivo SIP a la reunión llamando al número de teléfono del usuario o simplemente agregando un participante haciendo clic en "Solicitar unirse" también avisará al dispositivo SIP del usuario. Los usuarios invitados de otra organización pueden agregarlos a una reunión de Teams un participante que llama al número de un usuario invitado para incluirlo.
- **Transferencias de llamadas:** Los usuarios de dispositivos SIP pueden transferir llamadas. Sip Gateway admite transferencias ciegas y consultivas.
- **Desvío de llamadas local:** Un usuario de dispositivo SIP puede establecer reglas de reenvío (siempre, en tiempo de espera y ocupado) para el dispositivo. Si el dispositivo está conectado a la puerta de enlace SIP, la llamada se redirigirá a la dirección de destino en función de la regla que establezca el usuario del dispositivo. Para que el desvío de llamadas local funcione, el administrador debe establecer el `AllowCallRedirect` atributo en `Set-CsTeamsCallingPolicy` `Enabled`.

## <a name="requirements-to-use-sip-gateway"></a>Requisitos para usar puerta de enlace SIP

Teams usuarios deben tener un número de teléfono con llamadas RTC habilitadas para usar la puerta de enlace SIP.

### <a name="hardware-software-and-licenses"></a>Hardware, software y licencias

Si tiene un dispositivo SIP o 3PIP, debe tener:

- Una licencia para Sistema telefónico (a través de E5 o una licencia independiente)
- Habilitación de RTC (es decir, un número de teléfono) a través de un plan de llamadas de Microsoft Teams, enrutamiento directo o Conexión con operador
- Una licencia de área común Teléfono para los dispositivos de área común

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
|          |VVX150     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX201     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX250     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX300     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX301     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX310     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX311     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX350     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX400     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX401     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX410     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX411     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX450     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX500     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX501     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX600     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX601     |5.9.5       |6.3.1.8427 |   |   |
|**Yealink**|          |            |           |   |[Soporte técnico de Yealink](https://support.yealink.com/)|
|          |T40P       |83          |54.84.0.125|   |   |
|          |T41S       |83          |66.85.0.5  |   |   |
|          |T41S       |83          |66.85.0.5  |   |   |
|          |T41S       |83          |66.85.0.5  |   |   |
|          |T42G       |83          |29.83.0.130|   |   |
|          |T42S       |83          |66.85.0.5  |   |   |
|          |T42U       |83          |108.86.0.20|   |   |
|          |T43U       |83          |108.86.0.20|   |   |
|          |T46S       |83          |66.85.0.5  |   |   |
|          |T46U       |83          |108.86.0.20|   |   |
|          |T48S       |83          |66.85.0.5  |   |   |
|          |T48G       |83          |35.83.0.130|   |   |
|          |T48U       |83          |108.86.0.20|   |   |
|          |T53        |83          |96.85.0.5  |   |   |
|          |T53W       |83          |96.85.0.5  |   |   |
|          |T54W       |83          |96.85.0.5  |   |   |
|          |T57W       |83          |96.85.0.5  |   |   |
|          |T21P       |83          |52.84.0.140|   |   |
|          |T23G       |83          |44.84.0.140|   |   |
|          |T27G       |83          |69.85.0.5  |   |   |
|          |T29G       |83          |46.83.0.130|   |   |
|          |T30        |83          |124.85.0.40|   |   |
|          |T30P       |83          |124.85.0.40|   |   |
|          |T31G       |83          |124.85.0.40|   |   |
|          |T33G       |83          |124.85.0.40|   |   |
|          |T40G       |83          |76.84.0.125|   |   |
|          |T41P       |83          |36.83.0.120|   |   |
|          |T46G       |83          |28.83.0.130|   |   |
|**AudioCodes**|       |            |           |Algunos dispositivos SIP de AudioCodes necesitan una configuración de url de aprovisionamiento. Descarga e instala archivos de actualización para los dispositivos AudioCodes afectados a la derecha. |[Archivos descargables para dispositivos afectados en AudioCodes](https://audiocodes.sharefile.com/share/view/sc9cdf17f9ec45d09/fo7914a2-4f3a-4000-8957-47bd6f35a3a5)|
|          |405         |2.2.8      |2.2.16.570 |   |   |
|          |405HD       |3.2.1      |2.2.16.570 |   |   |
|          |420HD       |3.2.1      |2.2.16.570 |   |   |
|          |430HD       |3.2.1      |2.2.16.570 |   |   |
|          |440HD       |3.2.1      |2.2.16.570 |   |   |
|          |450HD       |3.2.1      |3.4.6.687  |   |   |
|          |C450HD      |3.2.1      |3.4.6.687  |   |   |
|          |445HD       |3.2.1      |3.4.6.687  |   |   |
|          |RX50        |3.2.1      |3.4.6.687  |   |   |

> [!NOTE]
> Para algunos dispositivos, la versión mínima de firmware es mayor que la versión de firmware aprobada. Esto se debe a que la versión 3.X es la versión Skype Empresarial. Actualizamos la versión SIP que es 2.X.
