---
title: Plan SIP Gateway
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
description: Obtenga más información sobre SIP Gateway, como requisitos y ventajas.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 817f3dc7ce7f0b6f407607417c0cadb92b65e943
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2022
ms.locfileid: "63514755"
---
# <a name="plan-for-sip-gateway"></a>Plan para SIP Gateway

SIP Gateway permite a su organización usar cualquier dispositivo SIP compatible con Microsoft Teams para conservar sus inversiones en dispositivos SIP. Ahora puede iniciar sesión en Teams con sus credenciales corporativas y realizar y recibir llamadas con un dispositivo SIP compatible. Los dispositivos compatibles Skype Empresarial teléfonos IP con firmware SIP estándar, teléfonos IP de Cisco con firmware SIP multiplataforma o dispositivos SIP de proveedores como Poly, Yealink y AudioCodes. Para obtener información sobre cómo configurar los dispositivos SIP para SIP Gateway, vea [Configurar SIP Gateway](sip-gateway-configure.md).

## <a name="benefits-of-sip-gateway"></a>Ventajas de SIP Gateway

SIP Gateway conecta dispositivos SIP compatibles con Teams para ayudar a los usuarios a migrar sin problemas a Teams telefonía. Con SIP Gateway, los usuarios pueden hacer lo siguiente:

- **Realizar llamadas:** Los usuarios de dispositivos SIP pueden realizar llamadas a la red telefónica conmutada (RTC), a otros dispositivos SIP y a Teams y Skype Empresarial usuarios. Los usuarios de dispositivo SIP solo pueden llamar a usuarios que tengan números de teléfono.
- **Recibir llamadas:** Los usuarios de dispositivo SIP pueden recibir una llamada desde la RTC, desde Teams o Skype Empresarial usuarios que tienen dispositivos SIP, y desde Teams y Skype Empresarial aplicaciones cliente. El dispositivo SIP actúa como punto de conexión Teams usuario. Las llamadas entrantes también se bifurcarán en el dispositivo SIP del usuario.
- **Varias llamadas simultáneas:** Un usuario de dispositivo SIP en una llamada puede poner la llamada en espera para realizar o recibir otras llamadas. Un usuario de dispositivo SIP también puede realizar dos llamadas.
- **No molestar:** Un usuario de dispositivo SIP puede establecer no molestar en el dispositivo para que el dispositivo no suene a las llamadas entrantes. Esto no tiene ningún impacto en el estado del usuario en todos los demás puntos de conexión Teams usuario.
- **Mantener/reanudar y silenciar/activar:** Un usuario de dispositivo SIP puede retener y reanudar o silenciar y activar una llamada usando las características para esas acciones en el dispositivo.
- **Correo de voz:** Los usuarios de dispositivos SIP pueden escuchar los mensajes de voz almacenados electrónicamente que los autores de llamadas dejan para ellos.
- **Indicador de mensaje en espera:** Los usuarios de dispositivos SIP pueden recibir notificaciones que les alertan cuando tengan mensajes de correo de voz nuevos.
- **Iniciar y cerrar sesión:** Los usuarios de dispositivos SIP pueden iniciar sesión y cerrar sesión Teams en el dispositivo.
- **Multifrecuencia de tono doble:** Los usuarios del dispositivo SIP pueden presionar las teclas numéricas para proporcionar información durante las llamadas de respuesta de voz interactivas.
- **Teams reuniones: un** usuario de dispositivo SIP puede unirse a una reunión de Teams marcando el número de acceso a la reunión. Los participantes de la reunión pueden agregar un usuario de dispositivo SIP a la reunión marcando al número de teléfono del usuario o simplemente agregando un participante haciendo clic en "Solicitar unirse" también alertará al dispositivo SIP del usuario. Los usuarios invitados de otra organización pueden agregarse a una reunión de Teams un participante que llame al número de un usuario invitado para incluirlo.
- **Transferencias de llamadas:** Los usuarios de dispositivos SIP pueden transferir llamadas. SIP Gateway admite tanto las transferencias ciegas como las consultas.
- **Reenvío de llamadas local:** Un usuario de dispositivo SIP puede establecer reglas de reenvío (siempre, con tiempo de espera y ocupado) para el dispositivo. Si el dispositivo está conectado a la puerta de enlace SIP, la llamada se redirigirá a la dirección de destino en función de la regla que establezca el usuario del dispositivo. Para que el reenvío de llamadas local funcione, el administrador debe establecer el `AllowCallRedirect` atributo en `Enabled``Set-CsTeamsCallingPolicy` . 


## <a name="requirements-to-use-sip-gateway"></a>Requisitos para usar SIP Gateway

Teams usuarios deben tener un número de teléfono con las llamadas RTC habilitadas para usar SIP Gateway.

### <a name="hardware-software-and-licenses"></a>Hardware, software y licencias

Si tiene un dispositivo 3PIP o SIP, debe tener: 
- Una licencia para Sistema telefónico (a través de E5 o una licencia independiente)
- Habilitación RTC (es decir, un número de teléfono) a través de un plan de llamadas Microsoft Teams, enrutamiento directo u operador Conectar
- Una licencia de área Teléfono para cualquier dispositivo de área común

## <a name="compatible-devices"></a>Dispositivos compatibles

|Proveedor    |Modelo      |Versión de firmware mínima|Versión de firmware aprobada|Notas|Vínculos|
|----------|-----------|------------|-----------|------------|------------|
|**Cisco** |           |            |           |Los dispositivos que ejecutan firmware empresarial deben convertirse en firmware multiplataforma. Lea la guía a la derecha para obtener información sobre cómo hacerlo.|[Guía de conversión de firmware de Cisco](https://www.cisco.com/c/en/us/products/collateral/collaboration-endpoints/unified-ip-phone-7800-series/guide-c07-742786.html)|
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
|**Poly**  |           |            |           |El dispositivo reiniciará automáticamente e instalará el firmware seleccionado.|   |
|          |Trio 8500  |5.9.5.3182  |7.1.1.0997 |   |   |
|          |Trío 8800  |5.9.5.3182  |7.1.1.0997 |   |   |
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
|**AudioCodes**|       |            |           |Algunos dispositivos SIP de AudioCodes necesitan una configuración de dirección URL de aprovisionamiento. Descargue e instale archivos de actualización para los dispositivos AudioCodes afectados a la derecha. |[Archivos descargables para dispositivos afectados en AudioCodes](https://audiocodes.sharefile.com/share/view/sc9cdf17f9ec45d09/fo7914a2-4f3a-4000-8957-47bd6f35a3a5)|
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
> Para algunos dispositivos, la versión mínima de firmware es mayor que la versión de firmware aprobada. Esto se debe a que la versión 3.X es Skype Empresarial versión. Actualizamos la versión SIP que es 2.X.
