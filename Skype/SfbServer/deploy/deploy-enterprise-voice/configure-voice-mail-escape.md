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
description: 'Resumen: obtenga información sobre cómo configurar el escape de correo de voz en Skype Empresarial Server mediante el Shell de administración de Skype Empresarial Server.'
ms.openlocfilehash: c6326360a0e49715feb7e9f9c3c123ec42b9c330
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824930"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a>Configurar el escape de correo de voz en Skype Empresarial

**Resumen:** Obtenga información sobre cómo configurar el escape de correo de voz en Skype Empresarial Server mediante el Shell de administración de Skype Empresarial Server.

Cuando un usuario configura llamadas simultáneas a un teléfono móvil, el autor de la llamada normalmente se enruta al correo de voz personal del usuario si el teléfono móvil está apagado, sin batería o fuera del alcance. Con Skype Empresarial Server, los usuarios pueden optar por que las llamadas relacionadas con la empresa se enruten a su sistema de correo de voz corporativo. Específicamente, se puede configurar un temporizador y, si el correo de voz del operador responde a la llamada dentro del intervalo de tiempo definido, Skype Empresarial Server se desconectará del sistema de correo de voz del operador (y del correo de voz personal del usuario), mientras que los extremos restantes del usuario en el sistema corporativo seguirán sonando. De este modo, el autor de la llamada se enruta automáticamente al correo de voz corporativo del usuario.

Esta configuración se realiza con el cmdlet del Shell de administración de Skype Empresarial Server, **Set-CsVoicePolicy,** en el nivel de directiva de voz, con los siguientes parámetros.

### <a name="to-configure-voice-mail-escape"></a>Para configurar el escape de correo de voz

1. Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**

2. Especificar los siguientes parámetros en **Set-CsVoicePolicy**:

   - **EnableVoicemailEscapeTimer**: habilita o deshabilita el temporizador de escape.

   - **PSTNVoicemailEscapeTimer**: especifica el valor de tiempo de espera en milisegundos. El valor predeterminado es 1500 milisegundos y puede variar de 0 a 8000 milisegundos.

## <a name="example"></a>Ejemplo

```powershell
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a>Vea también

[Configuración de directivas de voz y registros de uso de RTC para autorizar características y privilegios de llamada](https://technet.microsoft.com/library/63f22010-a3d7-4cbd-86e8-6fc0e13c2b84.aspx)

