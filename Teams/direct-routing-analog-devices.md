---
title: 'Enrutamiento directo: conectar dispositivos analógicos'
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
description: Lea este artículo para obtener información sobre cómo usar dispositivos analógicos con enrutamiento directo de Microsoft Phone System.
ms.openlocfilehash: 855bf0dd21659c43037b6171f523983d67c4e755
ms.sourcegitcommit: 1889ca28b9cb952b13c84efa3588957a327f9702
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841491"
---
# <a name="how-to-use-analog-devices-with-phone-system-direct-routing"></a>Cómo usar dispositivos analógicos con enrutamiento directo de sistema telefónico

En este artículo se describe cómo usar dispositivos analógicos con enrutamiento directo de sistema telefónico. Para conectar dispositivos analógicos a enrutamiento directo, debe usar un adaptador de telefonía analógica (ATA) y este adaptador debe ser compatible con el proveedor certificado del controlador de borde de sesión (SBC). 

Cuando un usuario realiza una llamada desde un dispositivo analógico, la señalización y los medios fluyen a través del adaptador de telefonía analógica (ATA) al SBC.  La SBC envía la llamada a un punto de conexión de Microsoft Teams o a la red telefónica conmutada (RTC) pública basándose en la tabla de enrutamiento interna.  Cuando un dispositivo realiza una llamada, la ruta que toma depende de las directivas de enrutamiento creadas para el dispositivo.

En el siguiente diagrama, el enrutamiento directo está configurado para que cualquier llamada de Teams hacia y desde los números entre +1425 4XX XX XX y +1425 5XX XX XX debe tomar la ruta roja (línea de puntos) y cualquier llamada RTC a y desde los números entre +1425 4XX XX y cualquier otro número excepto el intervalo de números +1425 5XX XX debe tomar la ruta azul (línea sólida). 

> [!div class="mx-imgBorder"]
> ![Diagrama que muestra la configuración de enrutamiento directo](media/direct-routing-analog-device.png)

## <a name="example--how-to-configure-the-use-of-analog-devices-with-direct-routing"></a>Ejemplo: Cómo configurar el uso de dispositivos analógicos con enrutamiento directo

Para configurar el uso de dispositivos analógicos con enrutamiento directo, debe conectar el adaptador de telefonía analógica a SBC y configurar el SBC para que funcione con enrutamiento directo. 

Este ejemplo le guiará por los pasos siguientes:

1. Conecte el SBC al enrutamiento directo.
2. Cree el uso de RTC.
3. Cree una ruta de voz y asociarla con el uso de RTC.
4. Asigne la ruta de voz al uso de RTC.
5. Habilite el usuario en línea.
6. Asigne la directiva de ruta de voz al usuario.
7. Crea una ruta de voz para un dispositivo analógico.

Para obtener información sobre cómo conectar un ATA a un SBC y configurarlo, consulte la guía de configuración del fabricante de SBC:

- [Documentación de configuración de AudioCodes](https://www.audiocodes.com/media/14278/connecting-audiocodes-sbc-with-analog-device-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf)

- [Documentación de configuración de la cinta de opciones](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)
- [Documentación de configuración de Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams)

## <a name="step-1--connect-the-sbc-to-direct-routing"></a>Paso 1.  Conectar el SBC al enrutamiento directo

El comando siguiente configura la conexión SBC de la siguiente manera:

- FqdN sbc.contoso.com
- Puerto de señalización 5068
- Modo de omisión de medios
- Información del historial de llamadas reenviada a la SBC:
- Encabezado P-Eded-Identity (PAI) reenviado junto con la llamada 

```powershell
PS C:\> New-CsOnlinePSTNGateway -FQDN sbc.contoso.com -SIPSignalingPort 5068 -ForwardCallHistory $true -ForwardPAI $true -MediaBypass $true -Enabled $true 
```

## <a name="step-2--create-the-pstn-usage"></a>Paso 2: Crear el uso de RTC 

El comando siguiente crea un uso de RTC vacío. Los usos de RTC en línea son valores de cadena que se usan para la autorización de llamadas. Un uso de RTC en línea vincula una directiva de voz en línea a una ruta. Este ejemplo agrega la cadena "Interoperabilidad" a la lista actual de usos de RTC disponibles. 

```powershell
PS C:\> Set-CsOnlinePstnUsage -Identity global -Usage @{add="Interop"} 
```

## <a name="step-3--create-a-voice-route-and-associate-it-with-the-pstn-usage"></a>Paso 3: Crear una ruta de voz y asociarla al uso de RTC:

Este comando crea una nueva ruta de voz en línea con la identidad "interoperabilidad analógica" para el intervalo de números +1425 XXX XX XX.  La ruta de voz se aplica a una lista de puertas de enlace en línea sbc.contoso.com y asocia la ruta con el uso de RTC en línea "Interoperabilidad". Una ruta de voz incluye una expresión regular que identifica qué números de teléfono se enrutarán a través de una ruta de voz determinada:

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(425)(\d{7}])$" -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="step-4-assign-the-voice-route-to-the-pstn-usage"></a>Paso 4: Asignar la ruta de voz al uso de RTC:

Este comando crea una nueva directiva de enrutamiento de voz por usuario en línea con la identidad "AnalogInteropPolicy". Esta directiva tiene asignado un único uso de RTC en línea: "Interoperabilidad".

```powershell
PS C:\> New-CsOnlineVoiceRoutingPolicy -Identity "AnalogInteropPolicy" -Name "AnalogInteropPolicy" -OnlinePstnUsages "Interop"
```

## <a name="step-5-enable-the-online-user"></a>Paso 5: Habilitar el usuario en línea

Este comando modifica la cuenta de usuario con la identidad exampleuser@contoso.com. En este caso, la cuenta se modifica para habilitar Telefonía IP empresarial, la implementación de VoIP de Microsoft, con el correo de voz habilitado y asigna el número +14255000000 a este usuario.  Este comando debe ejecutarse para cada usuario de Teams (excepto los usuarios de dispositivos ATA) en el inquilino de la compañía.

```powershell
PS C:\> Set-CsUser -Identity "exampleuser@contoso.com" -EnterpriseVoiceEnabled $True -HostedVoiceMail $True -OnPremLineUri "tel:+14255000000"
```

## <a name="step-6-assign-the-voice-route-policy-to-a-user"></a>Paso 6: Asignar la directiva de ruta de voz a un usuario

Este comando asigna la directiva de enrutamiento de voz en línea por usuario AnalogInteropPolicy al usuario con la identidad exampleuser@contoso.com.  Este comando debe ejecutarse para cada usuario de Teams (excepto los usuarios de dispositivos ATA) en el inquilino de la compañía.

```powershell
PS C:\> Grant-CsOnlineVoiceRoutingPolicy -Identity "exampleuser@contoso.com" -PolicyName "AnalogInteropPolicy" 
```

## <a name="step-7--create-a-voice-route-for-an-analog-device"></a>Paso 7: Crear una ruta de voz para un dispositivo analógico

Este comando crea una ruta de voz en línea con la identidad "interoperabilidad analógica" para el intervalo de números +1425 4XX XX XX aplicable a una lista de puertas de enlace en línea sbc.contoso.com y la asocia con el uso de RTC en línea "Interoperabilidad".  Este comando debe ejecutarse para cada dispositivo analógico con un patrón de número de teléfono adecuado. Como alternativa, puede usarse un patrón de números adecuado para dispositivos analógicos al configurar la ruta de voz en línea durante uno de los pasos anteriores.

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(4254)(\d{6}])$"  -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="considerations"></a>Consideraciones

- A menos que se anote lo contrario, un dispositivo analógico es cualquier dispositivo que puede enviar dígitos DTMF para realizar una llamada. Por ejemplo, teléfonos analógicos, fax y pagers superiores.

- Los teléfonos analógicos conectados a una ATA no se pueden buscar en Teams. Los usuarios de Teams deben introducir manualmente el número de teléfono asociado al dispositivo para llamar a ese dispositivo.  
 

## <a name="see-also"></a>Consulte también

[Planear el enrutamiento directo](direct-routing-plan.md)

[Configurar el enrutamiento directo](direct-routing-configure.md)
