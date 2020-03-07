---
title: 'Enrutamiento directo: conexión de dispositivos analógicos'
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Lea este artículo para aprender a usar dispositivos analógicos con el enrutamiento directo de Microsoft Phone System.
ms.openlocfilehash: 45128b8806644e4399687787bcce251ccb807d85
ms.sourcegitcommit: a6425a536746e129ab8bda3984b5ae63fb316192
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2020
ms.locfileid: "42558520"
---
# <a name="how-to-use-analog-devices-with-phone-system-direct-routing"></a>Cómo usar dispositivos analógicos con enrutamiento directo de sistema telefónico

En este artículo se describe cómo usar dispositivos analógicos con enrutamiento directo del sistema telefónico. Para conectar dispositivos analógicos a enrutamiento directo, debe usar un adaptador de telefonía analógica (ATA) y este adaptador debe ser compatible con el proveedor de controlador de borde de sesión (SBC) certificado. 

Cuando un usuario realiza una llamada desde un dispositivo analógico, la señalización y el flujo de medios a través del adaptador de telefonía analógica (ATA) a SBC.  El SBC envía la llamada a un punto final de Microsoft Teams o a la red de telefonía pública conmutada (RTC) en función de la tabla de enrutamiento interna.  Cuando un dispositivo realiza una llamada, la ruta que toma depende de las directivas de enrutamiento creadas para el dispositivo.

En el siguiente diagrama, el enrutamiento directo está configurado de modo que cualquier equipo que llame a y desde los números entre + 1425 4XX XX XX y + 1425 5XX XX XX debe tomar la ruta roja (línea de puntos) y cualquier llamada RTC a y desde números comprendidos entre + 1425 4XX XX XX y cualquier otro número excepto  intervalo de números + 1425 5XX XX XX debe tomar la ruta azul (línea sólida). 

![Diagrama que muestra la configuración de enrutamiento directo](media/direct-routing-analog-device.png)

## <a name="example--how-to-configure-the-use-of-analog-devices-with-direct-routing"></a>Ejemplo: Cómo configurar el uso de dispositivos analógicos con enrutamiento directo

Para configurar el uso de dispositivos analógicos con enrutamiento directo, debe conectar el adaptador de telefonía analógica al SBC y configurar el SBC para que funcione con el enrutamiento directo. 

Este ejemplo le guía por los siguientes pasos:

1. Conecte el SBC al enrutamiento directo.
2. Crear el uso de RTC.
3. Crear una ruta de voz y asociarla con el uso de RTC.
4. Asigne la ruta de voz al uso de RTC.
5. Habilitar el usuario en línea.
6. Asigne la Directiva de la ruta de voz al usuario.
7. Crear una ruta de voz para un dispositivo analógico.

Para obtener información sobre cómo conectar un ATA a un SBC y configurar el SBC, consulte la guía de configuración del fabricante de SBC:
- [Documentación de configuración de AudioCodes](https://www.audiocodes.com/media/14278/connecting-audiocodes-sbc-with-analog-device-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf)
- [Documentación de configuración de la cinta](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)

## <a name="step-1--connect-the-sbc-to-direct-routing"></a>Paso 1.  Conectar la SBC al enrutamiento directo

El siguiente comando configura la conexión de SBC de la siguiente manera:

- FQDN sbc.contoso.com
- Puerto de señalización 5068
- Modo de omisión de medios
- Información del historial de llamadas desviada a la SBC-
- P-encabezado de identidad afirmado (PAI) desviado junto con la llamada 

```
PS C:\> New-CsOnlinePSTNGateway -FQDN sbc.contoso.com -SIPSignalingPort 5068 -ForwardCallHistory $true -ForwardPAI $true -MediaBypass $true -Enabled $true 
```

## <a name="step-2--create-the-pstn-usage"></a>Paso 2: crear el uso de RTC 

El comando siguiente crea un uso de RTC vacío. Los usos de RTC en línea son valores de cadena que se usan para la autorización de llamadas. Un uso de RTC en línea vincula una directiva de voz en línea a una ruta. Este ejemplo agrega la cadena "Interop" a la lista actual de usos de RTC disponibles. 

```
PS C:\> Set-CsOnlinePstnUsage -Identity global -Usage @{add="Interop"} 
```

## <a name="step-3--create-a-voice-route-and-associate-it-with-the-pstn-usage"></a>Paso 3: crear una ruta de voz y asociarla con el uso de RTC:

Este comando crea una nueva ruta de voz en línea con la identidad "interoperabilidad analógica" para el intervalo de números + 1425 XXX XX XX.  La ruta de voz es aplicable a una lista de puertas de enlace en línea sbc.contoso.com y asocia la ruta con el uso de RTC en línea "interoperabilidad". Una ruta de voz incluye una expresión regular que identifica qué números de teléfono se redirigirán a través de una ruta de voz determinada:

```
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(425)(\d{7}])$" -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "
```

## <a name="step-4-assign-the-voice-route-to-the-pstn-usage"></a>Paso 4: asignar la ruta de voz al uso de RTC:

Este comando crea una nueva Directiva de enrutamiento de voz por usuario en línea con la identidad "AnalogInteropPolicy". A esta Directiva se le asigna un único uso de RTC en línea: "interoperabilidad".

```
PS C:\> New-CsOnlineVoiceRoutingPolicy -Identity "AnalogInteropPolicy" -Name "AnalogInteropPolicy" -OnlinePstnUsages "Interop"
```

## <a name="step-5-enable-the-online-user"></a>Paso 5: habilitar el usuario en línea

Este comando modifica la cuenta de usuario con la identidad exampleuser@contoso.com. En este caso, la cuenta se modifica para habilitar telefonía IP empresarial, la implementación de VoIP de Microsoft, con el correo de voz habilitado y asigna el número + 14255000000 a este usuario.  Este comando debe ejecutarse para cada usuario de Teams (excepto los usuarios del dispositivo ATA) en el espacio empresarial de la empresa.

```
PS C:\> Set-CsUser -Identity "exampleuser@contoso.com" -EnterpriseVoiceEnabled $True -HostedVoiceMail $True -OnPremLineUri "tel:+14255000000"
```

## <a name="step-6-assign-the-voice-route-policy-to-a-user"></a>Paso 6: asignar la Directiva de la ruta de voz a un usuario

Este comando asigna la Directiva de enrutamiento de voz en línea de AnalogInteropPolicy al usuario con la identidad exampleuser@contoso.com.  Este comando debe ejecutarse para cada usuario de Teams (excepto los usuarios del dispositivo ATA) en el espacio empresarial de la empresa.

```
PS C:\> Grant-CsOnlineVoiceRoutingPolicy -Identity "exampleuser@contoso.com" -PolicyName "AnalogInteropPolicy" 
```

## <a name="step-7--create-a-voice-route-for-an-analog-device"></a>Paso 7: crear una ruta de voz para un dispositivo analógico

Este comando crea una ruta de voz en línea con la identidad "red de interoperabilidad analógica" para el intervalo de números + 1425 4XX XX XX aplicable a una lista de puertas de enlace en línea sbc.contoso.com y la asocia a la "interoperabilidad" de uso de RTC en línea.  Este comando debe ejecutarse para cada dispositivo analógico con el patrón de número de teléfono adecuado. Como alternativa, se puede usar un patrón de número adecuado para dispositivos analógicos al configurar la ruta de voz en línea durante uno de los pasos anteriores.

```
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(4254)(\d{6}])$"  -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="considerations"></a>Consideraciones

- A menos que tenga nota, un dispositivo analógico es cualquier dispositivo que pueda enviar dígitos de DTMF para realizar una llamada. Por ejemplo, teléfonos analógicos, máquinas de fax y buscapersonas.
- Los teléfonos analógicos conectados a un ATA no se pueden buscar desde Teams. Los usuarios de Teams deben introducir manualmente el número de teléfono asociado con el dispositivo para llamar a ese dispositivo.  
 

## <a name="see-also"></a>Vea también

[Planear el enrutamiento directo](direct-routing-plan.md)

[Configurar el enrutamiento directo](direct-routing-configure.md)
