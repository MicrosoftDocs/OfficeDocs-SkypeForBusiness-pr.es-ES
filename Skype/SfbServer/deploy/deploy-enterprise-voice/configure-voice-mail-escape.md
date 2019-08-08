---
title: Configurar el escape del correo de voz en Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: 'Resumen: Aprenda a configurar el escape del correo de voz en Skype empresarial Server mediante el shell de administración de Skype empresarial Server.'
ms.openlocfilehash: c9a858ead9261944c162cb10fda63840f8de86d3
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233577"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a>Configurar el escape del correo de voz en Skype empresarial

**Resumen:** Obtenga información sobre cómo configurar el escape del correo de voz en Skype empresarial Server mediante el shell de administración de Skype empresarial Server.

Cuando un usuario configura la llamada simultánea a un teléfono móvil, normalmente se redirigirá al correo de voz personal del usuario si el teléfono móvil está apagado, agotado la batería o está fuera de alcance. Con Skype empresarial Server, los usuarios pueden optar por hacer que las llamadas relacionadas con el negocio se dirijan a su sistema de correo de voz empresarial. En concreto, se puede configurar un temporizador y, si el correo de voz del transportista responde a la llamada dentro del intervalo de tiempo definido, Skype empresarial Server se desconectará del sistema de correo de voz del transportista (y del correo de voz personal del usuario) mientras el usuario los puntos de conexión restantes en el sistema corporativo continúan sonando. De esta manera, la persona que llama se dirige automáticamente al correo de voz corporativo del usuario.

Esta configuración se realiza con el cmdlet del shell de administración de Skype empresarial, **set-CsVoicePolicy**, en el nivel de la Directiva de voz, con los siguientes parámetros.

### <a name="to-configure-voice-mail-escape"></a>Para configurar el escape de correo de voz

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.

2. Especifique los siguientes parámetros en **Set-CsVoicePolicy**:

   - **EnableVoicemailEscapeTimer**: habilita o deshabilita el temporizador de escape.

   - **PSTNVoicemailEscapeTimer**: especifica el valor de tiempo de espera en milisegundos. El valor predeterminado es 1500 milisegundos y puede variar de 0 a 8000 milisegundos.

## <a name="example"></a>Ejemplo

```
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a>Vea también

[Configuring Voice Policies and PSTN Usage Records to Authorize Calling Features and Privileges](https://technet.microsoft.com/library/63f22010-a3d7-4cbd-86e8-6fc0e13c2b84.aspx)

