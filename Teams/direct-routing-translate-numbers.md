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
description: Aprenda a configurar el enrutamiento directo de Microsoft Phone System.
ms.openlocfilehash: 2b675948153589c73fa545a95ac785b716b55265
ms.sourcegitcommit: 0289062510f0791906dab2791c5db8acb1cf849a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2020
ms.locfileid: "42158027"
---
# <a name="translate-phone-numbers-to-an-alternate-format"></a>Traducir números de teléfono a un formato alternativo

En este artículo se describe cómo traducir números de llamadas salientes y entrantes a un formato alternativo.  Este es el paso 4 de los pasos siguientes para configurar el enrutamiento directo:

- Paso 1. [Conectar el SBC con Microsoft Phone System y validar la conexión](direct-routing-connect-the-sbc.md) 
- Paso 2. [Habilitar a los usuarios para el enrutamiento directo, la voz y el buzón de voz](direct-routing-enable-users.md)   
- Paso 3. [Configurar el enrutamiento de voz](direct-routing-voice-routing.md)
- **Paso 4. Traducir números a un formato alternativo** (este artículo)

Para obtener información sobre todos los pasos necesarios para configurar el enrutamiento directo, consulte [configurar el enrutamiento directo](direct-routing-configure.md).

En ocasiones, es posible que los administradores de inquilinos deseen cambiar el número de llamadas salientes y/o entrantes en función de los patrones creados para garantizar la interoperabilidad con controladores de borde de sesión (SBCs). En este artículo se describe cómo puede especificar una directiva de reglas de traducción de números para traducir los números a un formato alternativo. 

Puede usar la Directiva de reglas de traducción de números para traducir números para lo siguiente:

- Llamadas entrantes: llamadas de un punto final de la RTC (llamador) a un cliente de equipos (destinatario)
- Llamadas salientes: llamadas de un cliente de Teams (llamador) a un punto final de RTC (destinatario)

La Directiva se aplica en el nivel de SBC. Puede asignar varias reglas de traducción a un SBC, que se aplican en el orden en que aparecen cuando las lista en PowerShell. También puede cambiar el orden de las reglas en la Directiva.

Para crear, modificar, ver y eliminar reglas de manipulación de números, use los cmdlets [New-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/new-csteamstranslationrule), [set-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/set-csteamstranslationrule), [Get-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/get-csteamstranslationrule)y [Remove-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/remove-csteamstranslationrule) .

Para asignar, configurar y enumerar reglas de manipulación de números en SBCs, use los cmdlets [New-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) y [set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) junto con InboundTeamsNumberTranslationRules, InboundPSTNNumberTranslationRules, OutboundTeamsNumberTranslationRules, OutboundPSTNNumberTranslationRules, InboundTeamsNumberTranslationRulesList, InboundPSTNNumberTranslationRulesList, OutboundTeamsNumberTranslationRulesList y OutboundPSTNNumberTranslationRulesList los.


## <a name="example-sbc-configuration"></a>Ejemplo de configuración de SBC

Para este escenario, el ```New-CsOnlinePSTNGateway``` cmdlet se ejecuta para crear la siguiente configuración de SBC:

```PowerShell
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignalingPort 5061 –InboundTeamsNumberTranslationRulesList ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRulesList ‘AddPlus1’ -OnboundPSTNNumberTranslationRulesList ‘AddSeattleAreaCode’,  -OutboundTeamsNumberTranslationRulesList ‘StripPlus1’
```

Las reglas de traducción asignadas a SBC se resumen en la tabla siguiente:

|Nombre  |Patrón |Traducción  |
|---------|---------|---------|
|AddPlus1     |^ (\d{10}) $          |+1$1          |
|AddE164SeattleAreaCode      |^ (\d{4}) $          | + 1206555 $1         |
|AddSeattleAreaCode    |^ (\d{4}) $          | 425555 $1         |
|StripPlus1    |^ + 1 (\d{10}) $          | $1         |

En los siguientes ejemplos, hay dos usuarios, Alice y Bob. Alicia es un usuario de equipos cuyo número es + 1 206 555 0100. Bob es un usuario de la RTC cuyo número es + 1 425 555 0100.

## <a name="example-1-inbound-call-to-a-ten-digit-number"></a>Ejemplo 1: llamada entrante a un número de diez dígitos

Bob llama a Alice a través de un número de diez dígitos que no sea el E. 164. Bob marca 2065550100 para comunicarse con Alice.
SBC usa 2065550100 en el RequestURI y en los encabezados y 4255550100 en el encabezado de.


|Encabezado  |Texto original en |Encabezado traducido |Parámetro y regla aplicados  |
|---------|---------|---------|---------|
|RequestURI  |INVITAr sip:2065550100@sbc.contoso.com|INVITAr sip:+12065550100@sbc.contoso.com|InboundTeamsNumberTranslationRulesList 'AddPlus1'|
|Para    |PARA: \<SIP:2065550100@sbc.contoso.com>|PARA: \<SIP:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddPlus1'|
|De   |DE: \<SIP:4255550100@sbc.contoso.com>|DE: \<SIP:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranslationRulesList 'AddPlus1'|

## <a name="example-2-inbound-call-to-a-four-digit-number"></a>Ejemplo 2: llamada entrante a un número de cuatro dígitos

Bob llama a Alice con un número de cuatro dígitos. Bob marca 0100 para comunicarse con Alice.
SBC usa 0100 en el RequestURI y en los encabezados y 4255550100 en el encabezado de.


|Encabezado  |Texto original en |Encabezado traducido |Parámetro y regla aplicados  |
|---------|---------|---------|---------|
|RequestURI  |INVITAr sip:0100@sbc.contoso.com          |INVITAr sip:+12065550100@sbc.contoso.com           |InboundTeamsNumberTranlationRulesList 'AddE164SeattleAreaCode'        |
|Para    |PARA: \<SIP:0100@sbc.contoso.com>|PARA: \<SIP:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddE164SeattleAreaCode'         |
|De   |DE: \<SIP:4255550100@sbc.contoso.com>|DE: \<SIP:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranlationRulesList 'AddPlus1'        |

## <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a>Ejemplo 3: llamada saliente con un número de diez dígitos que no es E. 164 número

Alicia llama a Bob con un número de diez dígitos. Alice marca 425 555 0100 para comunicarse con Bob.
SBC está configurado para usar números de diez dígitos no E. 164 para equipos y usuarios de la RTC.

En este escenario, un plan de marcado traduce el número antes de enviarlo a la interfaz de enrutamiento directo. Cuando Alice escribe 425 555 0100 en el cliente de Teams, el número se traduce a + 14255550100 por el plan de marcado de país. Los números resultantes son una normalización acumulativa de las reglas del plan de marcado y las reglas de traducción de equipos. Las reglas de traducción de Teams quitan el "+ 1" que agregó el plan de marcado.


|Encabezado  |Texto original en |Encabezado traducido |Parámetro y regla aplicados  |
|---------|---------|---------|---------|
|RequestURI  |INVITAr sip:+14255550100@sbc.contoso.com          |INVITAr sip:4255550100@sbc.contoso.com       |OutboundPSTNNumberTranlationRulesList 'StripPlus1'         |
|Para    |PARA: \<SIP:+14255550100@sbc.contoso.com>|PARA: \<SIP:4255555555@sbc.contoso.com>|OutboundPSTNNumberTranlationRulesList 'StripPlus1'       |
|De   |DE: \<SIP:+12065550100@sbc.contoso.com>|DE: \<SIP:2065550100@sbc.contoso.com>|OutboundTeamsNumberTranlationRulesList 'StripPlus1'         |

## <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a>Ejemplo 4: llamada saliente con un número de cuatro dígitos que no es E. 164 número

Alicia llama a Bob con un número de cuatro dígitos. Alice usa 0100 para comunicarte con Bob desde llamadas o con un contacto.
SBC está configurado para usar números de cuatro dígitos que no son E. 164 para los usuarios de Teams y números de 10 dígitos para usuarios de la RTC. El plan de marcado no se aplica en este escenario.


|Encabezado  |Texto original en |Encabezado traducido |Parámetro y regla aplicados  |
|---------|---------|---------|---------|
|RequestURI  |INVITAr sip:0100@sbc.contoso.com           |INVITAr sip:4255550100@sbc.contoso.com       |InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'         |
|Para    |PARA: \<SIP:0100@sbc.contoso.com>|PARA: \<SIP:4255555555@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'       |
|De   |DE: \<SIP:+12065550100@sbc.contoso.com>|DE: \<SIP:2065550100@sbc.contoso.com>| InboundPSTNNumberTranlationRulesList 'StripPlus1' |

## <a name="see-also"></a>Vea también

[Planear el enrutamiento directo](direct-routing-plan.md)

[Configurar el enrutamiento directo](direct-routing-configure.md)
