---
title: Traducir números de teléfono para enrutamiento directo
ms.reviewer: filippse
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Aprende a configurar el enrutamiento directo de Microsoft Phone System.
ms.openlocfilehash: ac6dbd46d525232235d957b7d47f1fe108e3e4a3
ms.sourcegitcommit: eb0e754d7e2877f686021d3ab75b6d8d44db3a95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2023
ms.locfileid: "69727772"
---
# <a name="translate-phone-numbers-to-an-alternate-format"></a>Traducir números de teléfono a un formato alternativo

En este artículo se describe cómo traducir números para llamadas entrantes y salientes a un formato alternativo. Este es el paso 4 de los siguientes pasos para configurar el enrutamiento directo:

- Paso 1. [Conecta el SBC con Microsoft Phone System y valida la conexión](direct-routing-connect-the-sbc.md) 
- Paso 2. [Habilitar a los usuarios para el enrutamiento directo, la voz y el correo de voz](direct-routing-enable-users.md)   
- Paso 3. [Configurar el enrutamiento de voz](direct-routing-voice-routing.md)
- **Paso 4. Traducir números a un formato alternativo**   (este artículo)

Para obtener información sobre todos los pasos necesarios para configurar el enrutamiento directo, consulte [Configurar enrutamiento directo](direct-routing-configure.md).

A veces, es posible que los administradores de inquilinos quieran cambiar el número de llamadas entrantes o salientes en función de los patrones que crearon para garantizar la interoperabilidad con los controladores de borde de sesión (SCS). En este artículo se describe cómo puede especificar una directiva de reglas de traducción de números para traducir números a un formato alternativo. 

Puede usar la directiva Reglas de traducción de números para traducir números para lo siguiente:

- Llamadas entrantes: llamadas desde un punto de conexión RTC (autor de la llamada) a un cliente de Teams (destinatario de la llamada)
- Llamadas salientes: llamadas desde un cliente de Teams (autor de la llamada) a un punto de conexión RTC (destinatario de la llamada)

La directiva se aplica en el nivel SBC. Puede asignar varias reglas de traducción a un SBC, que se aplican en el orden en que aparecen al enumerarlas en PowerShell. También puede cambiar el orden de las reglas de la directiva.

Para crear, modificar, ver y eliminar reglas de manipulación de números, use los [cmdlets New-CsTeamsTranslationRule](/powershell/module/skype/new-csteamstranslationrule), [Set-CsTeamsTranslationRule](/powershell/module/skype/set-csteamstranslationrule), [Get-CsTeamsTranslationRule](/powershell/module/skype/get-csteamstranslationrule) y [Remove-CsTeamsTranslationRule](/powershell/module/skype/remove-csteamstranslationrule) .

Para asignar, configurar y enumerar reglas de manipulación de números en sbcs, use los cmdlets [New-CSOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) y [Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway) junto con los parámetros InboundTeamsNumberTranslationRules, InboundPSTNNumberTranslationRules, OutboundTeamsNumberTranslationRules y OutboundPSTNNumberTranslationRules.

> [!NOTE]
> El número máximo total de reglas de traducción es 400, la longitud máxima del nombre del parámetro de traducción es de 100 símbolos, la longitud máxima del patrón de parámetros de traducción es de 1024 símbolos y la longitud máxima de traducción de los parámetros de traducción es de 256 símbolos.


## <a name="example-sbc-configuration"></a>Configuración de SBC de ejemplo

Para este escenario, se ejecuta el cmdlet de New-CsOnlinePSTNGateway para crear la siguiente configuración de SBC:

```PowerShell
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignalingPort 5061 –InboundTeamsNumberTranslationRules ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRules ‘AddPlus1’ -OutboundPSTNNumberTranslationRules ‘AddSeattleAreaCode’,‘StripPlus1’  -OutboundTeamsNumberTranslationRules ‘StripPlus1’
```

Las reglas de traducción asignadas a la SBC se resumen en la tabla siguiente:

|Nombre  |Patrón |Traducción  |
|---------|---------|---------|
|AddPlus1     |^(\d{10})$          |+1$1          |
|AddE164SeattleAreaCode      |^(\d{4})$          | +1206555$1         |
|AddSeattleAreaCode    |^(\d{4})$          | 425555$1         |
|StripPlus1    |^\+1(\d{10})$          | $1         |

En los ejemplos siguientes, hay dos usuarios: Alice y Bob. Alice es un usuario de Teams cuyo número es +1 206 555 0100. Bob es un usuario de RTC cuyo número es +1 425 555 0100.

## <a name="example-1-inbound-call-to-a-ten-digit-number"></a>Ejemplo 1: Llamada entrante a un número de diez dígitos

Bob llama a Alice con un número de diez dígitos que no es E.164. Bob marca 2065550100 llegar a Alice.
SBC usa 2065550100 en los encabezados RequestURI y To y 4255550100 en el encabezado De.


|Rúbrica  |Texto original en |Encabezado traducido |Parámetro y regla aplicados  |
|---------|---------|---------|---------|
|RequestURI  |INVITAR a sip:2065550100@sbc.contoso.com|INVITAR a sip:+12065550100@sbc.contoso.com|InboundTeamsNumberTranslationRules 'AddPlus1'|
|PARA    |PARA: \<sip:2065550100@sbc.contoso.com>|PARA: \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddPlus1'|
|DE   |DE: \<sip:4255550100@sbc.contoso.com>|DE: \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranslationRules 'AddPlus1'|

## <a name="example-2-inbound-call-to-a-four-digit-number"></a>Ejemplo 2: Llamada entrante a un número de cuatro dígitos

Bob llama a Alice con un número de cuatro dígitos. Bob marca 0100 para llegar a Alice.
SBC usa 0100 en los encabezados RequestURI y To y 4255550100 en el encabezado De.


|Rúbrica  |Texto original en |Encabezado traducido |Parámetro y regla aplicados  |
|---------|---------|---------|---------|
|RequestURI  |INVITAR a sip:0100@sbc.contoso.com          |INVITAR a sip:+12065550100@sbc.contoso.com           |InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'        |
|PARA    |PARA: \<sip:0100@sbc.contoso.com>|PARA: \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'         |
|DE   |DE: \<sip:4255550100@sbc.contoso.com>|DE: \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranlationRules 'AddPlus1'        |

## <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a>Ejemplo 3: Llamada saliente con un número que no es E.164 de diez dígitos

Alice llama a Bob con un número de diez dígitos. Alice marca 425 555 0100 para llegar a Bob.
SBC está configurado para usar números de diez dígitos que no sean E.164 tanto para Teams como para usuarios de RTC.

En este escenario, un plan de marcado traduce el número antes de enviarlo a la interfaz de enrutamiento directo. Cuando Alice escribe 425 555 0100 en el cliente de Teams, el número se traduce a +14255550100 por el plan de marcado del país. Los números resultantes son una normalización acumulativa de las reglas del plan de marcado y las reglas de traducción de Teams. Las reglas de traducción de Teams quitan el "+1" que agregó el plan de marcado.


|Rúbrica  |Texto original en |Encabezado traducido |Parámetro y regla aplicados  |
|---------|---------|---------|---------|
|RequestURI  |INVITAR a sip:+14255550100@sbc.contoso.com          |INVITAR a sip:4255550100@sbc.contoso.com       |OutboundPSTNNumberTranlationRules 'StripPlus1'         |
|PARA    |PARA: \<sip:+14255550100@sbc.contoso.com>|PARA: \<sip:4255555555@sbc.contoso.com>|OutboundPSTNNumberTranlationRules 'StripPlus1'       |
|DE   |DE: \<sip:+12065550100@sbc.contoso.com>|DE: \<sip:2065550100@sbc.contoso.com>|OutboundTeamsNumberTranlationRules 'StripPlus1'         |

## <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a>Ejemplo 4: Llamada saliente con un número que no es E.164 de cuatro dígitos

Alice llama a Bob con un número de cuatro dígitos. Alice usa 0100 para ponerse en contacto con Bob desde Llamadas o mediante un contacto.
SBC está configurado para usar números que no sean E.164 de cuatro dígitos para los usuarios de Teams y números de diez dígitos para usuarios de RTC. El plan de marcado no se aplica en este escenario.


|Rúbrica  |Texto original en |Encabezado traducido |Parámetro y regla aplicados  |
|---------|---------|---------|---------|
|RequestURI  |INVITAR a sip:0100@sbc.contoso.com           |INVITAR a sip:4255550100@sbc.contoso.com       |InboundTeamsNumberTranlationRules 'AddSeattleAreaCode'         |
|PARA    |PARA: \<sip:0100@sbc.contoso.com>|PARA: \<sip:4255555555@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'       |
|DE   |DE: \<sip:+12065550100@sbc.contoso.com>|DE: \<sip:2065550100@sbc.contoso.com>| InboundPSTNNumberTranlationRules 'StripPlus1' |

## <a name="see-also"></a>Vea también

[Planear el enrutamiento directo](direct-routing-plan.md)

[Configurar el enrutamiento directo](direct-routing-configure.md)
