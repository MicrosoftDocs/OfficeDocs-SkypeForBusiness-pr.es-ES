---
title: Traducir números de teléfono para enrutamiento directo
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Obtenga información sobre cómo configurar el enrutamiento directo de Microsoft Phone System.
ms.openlocfilehash: 7d48e9163dd5927cbeddf4a4104d2382e69e7e2b
ms.sourcegitcommit: f9daef3213a305676127cf5140af907e3b96d046
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2020
ms.locfileid: "48369165"
---
# <a name="translate-phone-numbers-to-an-alternate-format"></a>Traducir números de teléfono a un formato alternativo

En este artículo se describe cómo traducir los números de las llamadas entrantes y salientes a un formato alternativo.  Este es el paso 4 de los siguientes pasos para configurar el enrutamiento directo:

- Paso 1. [Conectar el SBC con Microsoft Phone System y validar la conexión](direct-routing-connect-the-sbc.md) 
- Paso 2. [Habilitar usuarios para enrutamiento directo, voz y correo de voz](direct-routing-enable-users.md)   
- Paso 3. [Configurar el enrutamiento de voz](direct-routing-voice-routing.md)
- **Paso 4. Traducir números a un formato alternativo**   (en este artículo)

Para obtener información sobre todos los pasos necesarios para configurar el enrutamiento directo, vea [Configurar enrutamiento directo.](direct-routing-configure.md)

A veces, es posible que los administradores de inquilinos quieran cambiar el número de llamadas salientes y/o entrantes en función de los patrones creados para garantizar la interoperabilidad con controlador de borde de sesión (SBCs). En este artículo se describe cómo especificar una directiva de reglas de traducción de números para traducir números a un formato alternativo. 

Puede usar la directiva Reglas de traducción de números para traducir números para lo siguiente:

- Llamadas entrantes: Llamadas desde un punto de conexión de RTC (autor de la llamada) a un cliente de Teams (destinatario de la llamada)
- Llamadas salientes: Llamadas desde un cliente de Teams (autor de la llamada) a un punto de conexión de RTC (destinatario)

La directiva se aplica en el nivel SBC. Puede asignar varias reglas de traducción a una SBC, que se aplican en el orden en que aparecen cuando las enumera en PowerShell. También puede cambiar el orden de las reglas de la directiva.

Para crear, modificar, ver y eliminar las reglas de manipulación de números, use los cmdlets [New-CsTeamsTranslationRule,](https://docs.microsoft.com/powershell/module/skype/new-csteamstranslationrule) [Set-CsTeamsTranslationRule,](https://docs.microsoft.com/powershell/module/skype/set-csteamstranslationrule) [Get-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/get-csteamstranslationrule)y [Remove-CsTeamsTranslationRule.](https://docs.microsoft.com/powershell/module/skype/remove-csteamstranslationrule)

Para asignar, configurar y enumerar reglas de manipulación de números en listas de listas (SBCs), use los cmdlets [New-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) y [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) junto con inboundTeamsNumberTranslationRules, InboundPSTNNumberTranslationRules, OutboundTeamsNumberTranslationRules, OutboundPSTNNumberTranslationRules, InboundTeamsNumberTranslationRules, InboundPSTNNumberTranslationRules, OutboundTeamsNumberTranslationRules y los parámetros OutboundPSTNNumberTranslationRules.

> [!NOTE]
> El número total máximo de reglas de traducción es 400, la longitud máxima del nombre del parámetro de traducción es de 100 símbolos, la longitud máxima del patrón de parámetros de traducción es de 1024 símbolos y la longitud máxima de los parámetros de traducción es de 256 símbolos.


## <a name="example-sbc-configuration"></a>Configuración SBC de ejemplo

Para este escenario, el ```New-CsOnlinePSTNGateway``` cmdlet se ejecuta para crear la siguiente configuración de SBC:

```PowerShell
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignalingPort 5061 –InboundTeamsNumberTranslationRules ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRules ‘AddPlus1’ -OutboundPSTNNumberTranslationRules ‘AddSeattleAreaCode’,  -OutboundTeamsNumberTranslationRules ‘StripPlus1’
```

Las reglas de traducción asignadas a la SBC se resumen en la tabla siguiente:

|Nombre  |Patrón |Traducción  |
|---------|---------|---------|
|AddPlus1     |^(\d {10} )$          |+1$1          |
|Adde164SeattleAreaCode      |^(\d {4} )$          | +1206555$1         |
|AddSeattleAreaCode    |^(\d {4} )$          | 425555$1         |
|StripPlus1    |^+1(\d {10} )$          | $1         |

En los ejemplos siguientes, hay dos usuarios, Van y Bob. Unos es un usuario de Teams cuyo número es +1 206 555 0100. Bob es un usuario de RTC cuyo número es +1 425 555 0100.

## <a name="example-1-inbound-call-to-a-ten-digit-number"></a>Ejemplo 1: Llamada entrante a un número de diez dígitos

Bob llama a Que con un número que no es E.164 de diez dígitos. Bob marca el 2065550100 para contactar con Ana.
SBC usa 2065550100 en los encabezados RequestURI y Para y 4255550100 en el encabezado De.


|Encabezado  |Texto original en |Encabezado traducido |Parámetro y regla aplicados  |
|---------|---------|---------|---------|
|RequestURI  |INVITAR a sip:2065550100@sbc.contoso.com|INVITAR a sip:+12065550100@sbc.contoso.com|InboundTeamsNumberTranslationRules 'AddPlus1'|
|Para    |Para: \<sip:2065550100@sbc.contoso.com>|Para: \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddPlus1'|
|De   |De: \<sip:4255550100@sbc.contoso.com>|De: \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranslationRules 'AddPlus1'|

## <a name="example-2-inbound-call-to-a-four-digit-number"></a>Ejemplo 2: Llamada entrante a un número de cuatro dígitos

Bob llama a Que con un número de cuatro dígitos. Bob marca el 0100 para llegar a Durante.
SBC usa 0100 en los encabezados RequestURI y To y 4255550100 en el encabezado De.


|Encabezado  |Texto original en |Encabezado traducido |Parámetro y regla aplicados  |
|---------|---------|---------|---------|
|RequestURI  |INVITAR a sip:0100@sbc.contoso.com          |INVITAR a sip:+12065550100@sbc.contoso.com           |InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'        |
|Para    |Para: \<sip:0100@sbc.contoso.com>|Para: \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'         |
|De   |De: \<sip:4255550100@sbc.contoso.com>|De: \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranlationRules 'AddPlus1'        |

## <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a>Ejemplo 3: Llamada saliente con un número que no es E.164 de diez dígitos

Bob llama a Bob con un número de diez dígitos. Alice dials 425 555 0100 to reach Bob.
SBC está configurado para usar números de diez dígitos que no son E.164 para los usuarios de Teams y RTC.

En este escenario, un plan de marcado traduce el número antes de enviarlo a la interfaz de enrutamiento directo. Cuando Total introduce 425 555 0100 en el cliente de Teams, el número se traduce a +14255550100 por el plan de marcado del país. Los números resultantes son una normalización acumulativa de las reglas del plan de marcado y las reglas de traducción de Teams. Las reglas de traducción de Teams quitan el "+1" que agregó el plan de marcado.


|Encabezado  |Texto original en |Encabezado traducido |Parámetro y regla aplicados  |
|---------|---------|---------|---------|
|RequestURI  |INVITAR a sip:+14255550100@sbc.contoso.com          |INVITAR a sip:4255550100@sbc.contoso.com       |OutboundPSTNNumberTranlationRules 'StripPlus1'         |
|Para    |Para: \<sip:+14255550100@sbc.contoso.com>|Para: \<sip:4255555555@sbc.contoso.com>|OutboundPSTNNumberTranlationRules 'StripPlus1'       |
|De   |De: \<sip:+12065550100@sbc.contoso.com>|De: \<sip:2065550100@sbc.contoso.com>|OutboundTeamsNumberTranlationRules 'StripPlus1'         |

## <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a>Ejemplo 4: Llamada saliente con un número que no es E.164 de cuatro dígitos

Que llama a Bob con un número de cuatro dígitos. Según usa 0100 para contactar con Bob desde llamadas o usando un contacto.
SBC está configurado para usar números de cuatro dígitos que no son E.164 para los usuarios de Teams y números de diez dígitos para los usuarios de RTC. El plan de marcado no se aplica en este escenario.


|Encabezado  |Texto original en |Encabezado traducido |Parámetro y regla aplicados  |
|---------|---------|---------|---------|
|RequestURI  |INVITAR a sip:0100@sbc.contoso.com           |INVITAR a sip:4255550100@sbc.contoso.com       |InboundTeamsNumberTranlationRules 'AddSeattleAreaCode'         |
|Para    |Para: \<sip:0100@sbc.contoso.com>|Para: \<sip:4255555555@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'       |
|De   |De: \<sip:+12065550100@sbc.contoso.com>|De: \<sip:2065550100@sbc.contoso.com>| InboundPSTNNumberTranlationRules 'StripPlus1' |

## <a name="see-also"></a>Consulte también

[Planear el enrutamiento directo](direct-routing-plan.md)

[Configurar el enrutamiento directo](direct-routing-configure.md)
