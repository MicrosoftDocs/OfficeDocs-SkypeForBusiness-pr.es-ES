---
title: Configurar el escape de correo de voz en Skype Empresarial
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: 'Summary: Learn how to configure voice mail escape in Skype for Business Server by using the Skype for Business Server Management Shell.'
ms.openlocfilehash: c74142cf3b0f6c9d5a871e116d8e163a095ad3cd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106376"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a>Configurar el escape de correo de voz en Skype Empresarial

**Resumen:** Obtenga información sobre cómo configurar el escape de correo de voz en Skype Empresarial Server mediante el Shell de administración de Skype Empresarial Server.

Cuando un usuario configura la llamada simultánea a un teléfono móvil, un autor de la llamada normalmente se enruta al correo de voz personal del usuario si el teléfono móvil está apagado, sin batería o fuera del intervalo. Con Skype Empresarial Server, los usuarios pueden optar por que las llamadas relacionadas con la empresa se enruten a su sistema de correo de voz corporativo. En concreto, se puede configurar un temporizador y, si el correo de voz del operador responde a la llamada dentro del intervalo de tiempo definido, Skype Empresarial Server se desconectará del sistema de correo de voz del operador (y del correo de voz personal del usuario), mientras que los puntos de conexión restantes del usuario en el sistema corporativo seguirán sonando. De este modo, el autor de la llamada se enruta automáticamente al correo de voz corporativo del usuario.

Esta configuración se realiza mediante el cmdlet del Shell de administración de Skype Empresarial Server, **Set-CsVoicePolicy**, en el nivel de directiva de voz, con los parámetros siguientes.

### <a name="to-configure-voice-mail-escape"></a>Para configurar el escape de correo de voz

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en Inicio **,** en Todos los programas **,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración **de Skype Empresarial Server**.

2. Especificar los siguientes parámetros en **Set-CsVoicePolicy**:

   - **EnableVoicemailEscapeTimer**: habilita o deshabilita el temporizador de escape.

   - **PSTNVoicemailEscapeTimer**: especifica el valor de tiempo de espera en milisegundos. El valor predeterminado es 1500 milisegundos y puede variar de 0 a 8000 milisegundos.

## <a name="example"></a>Ejemplo

```powershell
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a>Vea también

[Configuración de directivas de voz y registros de uso de RTC para autorizar características y privilegios de llamada](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges)