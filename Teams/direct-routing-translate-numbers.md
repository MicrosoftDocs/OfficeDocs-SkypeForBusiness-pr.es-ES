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
description: Obtenga información sobre cómo configurar Teléfono Microsoft system direct routing.
ms.openlocfilehash: 03abeed954a7760c7c53142380a8ca558c5b3761
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096380"
---
# <a name="translate-phone-numbers-to-an-alternate-format"></a>Traducir números de teléfono a un formato alternativo

En este artículo se describe cómo traducir números para llamadas salientes y entrantes a un formato alternativo.  Este es el paso 4 de los siguientes pasos para configurar enrutamiento directo:

- Paso 1. [Conectar el SBC con Teléfono Microsoft y validar la conexión](direct-routing-connect-the-sbc.md) 
- Paso 2. [Habilitar usuarios para enrutamiento directo, voz y correo de voz](direct-routing-enable-users.md)   
- Paso 3. [Configurar el enrutamiento de voz](direct-routing-voice-routing.md)
- **Paso 4. Traducir números a un formato alternativo**   (este artículo)

Para obtener información sobre todos los pasos necesarios para configurar el enrutamiento directo, vea [Configurar enrutamiento directo.](direct-routing-configure.md)

A veces, es posible que los administradores de inquilinos quieran cambiar el número de las llamadas salientes y/o entrantes en función de los patrones que crearon para garantizar la interoperabilidad con los controladores de borde de sesión (SBC). En este artículo se describe cómo puede especificar una directiva reglas de traducción de números para traducir números a un formato alternativo. 

Puede usar la directiva Reglas de traducción de números para traducir números para lo siguiente:

- Llamadas entrantes: Llamadas desde un punto de conexión RTC (autor de la llamada) a un cliente Teams (destinatario)
- Llamadas salientes: llamadas de un cliente Teams (autor de la llamada) a un punto de conexión RTC (destinatario)

La directiva se aplica en el nivel SBC. Puede asignar varias reglas de traducción a un SBC, que se aplican en el orden en que aparecen al enumerarlos en PowerShell. También puede cambiar el orden de las reglas de la directiva.

Para crear, modificar, ver y eliminar reglas de manipulación de números, use los [cmdlets New-CsTeamsTranslationRule](/powershell/module/skype/new-csteamstranslationrule), [Set-CsTeamsTranslationRule,](/powershell/module/skype/set-csteamstranslationrule) [Get-CsTeamsTranslationRule](/powershell/module/skype/get-csteamstranslationrule)y [Remove-CsTeamsTranslationRule.](/powershell/module/skype/remove-csteamstranslationrule)

Para asignar, configurar y enumerar reglas de manipulación de números en SBC, use los cmdlets [New-CSOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) y [Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway) junto con inboundTeamsNumberTranslationRules, Parámetros InboundPSTNNumberTranslationRules, OutboundTeamsNumberTranslationRules, OutboundPSTNNumberTranslationRules, InboundTeamsNumberTranslationRules, InboundPSTNNumberTranslationRules, OutboundTeamsNumberTranslationRules y OutboundPSTNNumberTranslationRules.

> [!NOTE]
> El número total máximo de reglas de traducción es 400, la longitud máxima del nombre del parámetro de traducción es de 100 símbolos, la longitud máxima del patrón de parámetros de traducción es de 1024 símbolos y la longitud máxima de traducción de parámetros de traducción es de 256 símbolos.


## <a name="example-sbc-configuration"></a>Ejemplo de configuración de SBC

En este escenario, el ```New-CsOnlinePSTNGateway``` cmdlet se ejecuta para crear la siguiente configuración de SBC:

```PowerShell
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignalingPort 5061 –InboundTeamsNumberTranslationRules ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRules ‘AddPlus1’ -OutboundPSTNNumberTranslationRules ‘AddSeattleAreaCode’,  -OutboundTeamsNumberTranslationRules ‘StripPlus1’
```

Las reglas de traducción asignadas al SBC se resumen en la tabla siguiente:

|Nombre  |Patrón |Traducción  |
|---------|---------|---------|
|AddPlus1     |^(\d {10} )$          |+1$1          |
|AddE164SeattleAreaCode      |^(\d {4} )$          | +1206555$1         |
|AddSeattleAreaCode    |^(\d {4} )$          | 425555$1         |
|StripPlus1    |^+1(\d {10} )$          | $1         |

En los ejemplos siguientes, hay dos usuarios, Alicia y Bob. Alice es un Teams cuyo número es +1 206 555 0100. Bob es un usuario RTC cuyo número es +1 425 555 0100.

## <a name="example-1-inbound-call-to-a-ten-digit-number"></a>Ejemplo 1: Llamada entrante a un número de diez dígitos

Bob llama a Alicia con un número de diez dígitos que no es de E.164. Bob marca 2065550100 para llegar a Alicia.
SBC usa 2065550100 en los encabezados RequestURI y To y 4255550100 en el encabezado De.


|Encabezado  |Texto original en |Encabezado traducido |Parámetro y regla aplicados  |
|---------|---------|---------|---------|
|RequestURI  |Invitar sip:2065550100@sbc.contoso.com|Invitar sip:+12065550100@sbc.contoso.com|InboundTeamsNumberTranslationRules 'AddPlus1'|
|Para    |Para: \<sip:2065550100@sbc.contoso.com>|Para: \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddPlus1'|
|De   |De: \<sip:4255550100@sbc.contoso.com>|De: \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranslationRules 'AddPlus1'|

## <a name="example-2-inbound-call-to-a-four-digit-number"></a>Ejemplo 2: Llamada entrante a un número de cuatro dígitos

Bob llama a Alicia con un número de cuatro dígitos. Bob marca el 0100 para llegar a Alicia.
SBC usa 0100 en los encabezados RequestURI y To y 4255550100 en el encabezado De.


|Encabezado  |Texto original en |Encabezado traducido |Parámetro y regla aplicados  |
|---------|---------|---------|---------|
|RequestURI  |INVITAR sip:0100@sbc.contoso.com          |Invitar sip:+12065550100@sbc.contoso.com           |InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'        |
|Para    |Para: \<sip:0100@sbc.contoso.com>|Para: \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'         |
|De   |De: \<sip:4255550100@sbc.contoso.com>|De: \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranlationRules 'AddPlus1'        |

## <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a>Ejemplo 3: Llamada saliente con un número no E.164 de diez dígitos

Alicia llama a Bob con un número de diez dígitos. Alicia marca el 425 555 0100 para llegar a Bob.
SBC está configurado para usar números de diez dígitos que no son E.164 para los usuarios de Teams RTC.

En este escenario, un plan de marcado traduce el número antes de enviarlo a la interfaz de enrutamiento directo. Cuando Alicia escribe 425 555 0100 en el cliente de Teams, el número se traduce a +14255550100 por el plan de marcado de país. Los números resultantes son una normalización acumulativa de las reglas del plan de marcado y Teams de traducción. Las Teams de traducción elimina el "+1" que agregó el plan de marcado.


|Encabezado  |Texto original en |Encabezado traducido |Parámetro y regla aplicados  |
|---------|---------|---------|---------|
|RequestURI  |INVITAR sip:+14255550100@sbc.contoso.com          |Invitar sip:4255550100@sbc.contoso.com       |OutboundPSTNNumberTranlationRules 'StripPlus1'         |
|Para    |Para: \<sip:+14255550100@sbc.contoso.com>|Para: \<sip:4255555555@sbc.contoso.com>|OutboundPSTNNumberTranlationRules 'StripPlus1'       |
|De   |De: \<sip:+12065550100@sbc.contoso.com>|De: \<sip:2065550100@sbc.contoso.com>|OutboundTeamsNumberTranlationRules 'StripPlus1'         |

## <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a>Ejemplo 4: Llamada saliente con un número no E.164 de cuatro dígitos

Alicia llama a Bob con un número de cuatro dígitos. Alicia usa 0100 para ponerse en contacto con Bob desde llamadas o mediante un contacto.
SBC está configurado para usar números de cuatro dígitos distintos de E.164 para los usuarios Teams y números de diez dígitos para los usuarios RTC. El plan de marcado no se aplica en este escenario.


|Encabezado  |Texto original en |Encabezado traducido |Parámetro y regla aplicados  |
|---------|---------|---------|---------|
|RequestURI  |INVITAR sip:0100@sbc.contoso.com           |Invitar sip:4255550100@sbc.contoso.com       |InboundTeamsNumberTranlationRules 'AddSeattleAreaCode'         |
|Para    |Para: \<sip:0100@sbc.contoso.com>|Para: \<sip:4255555555@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'       |
|De   |De: \<sip:+12065550100@sbc.contoso.com>|De: \<sip:2065550100@sbc.contoso.com>| InboundPSTNNumberTranlationRules 'StripPlus1' |

## <a name="see-also"></a>Vea también

[Planear el enrutamiento directo](direct-routing-plan.md)

[Configurar el enrutamiento directo](direct-routing-configure.md)