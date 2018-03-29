---
title: Configurar escape de buzón de voz en Skype Empresarial 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: 'Resumen: Conozca cómo configurar escape del correo de voz de Skype para Business Server 2015 utilizando el Skype para el Shell de administración de servidor empresarial.'
ms.openlocfilehash: 07586f38127b2831ecdb2900f005ff43b4184292
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-voice-mail-escape-in-skype-for-business-2015"></a>Configurar escape de buzón de voz en Skype Empresarial 2015
 
**Resumen:** Aprenda a configurar escape del correo de voz de Skype para Business Server 2015 utilizando el Skype para el Shell de administración de servidor empresarial.
  
Cuando un usuario configura las llamadas simultáneas a un teléfono móvil, un llamador normalmente se enrutarán al correo de voz personal del usuario si el teléfono móvil está apagado, sin batería o fuera del intervalo. Con Skype para Business Server, los usuarios pueden optar por tener laboral llamadas enrutadas a su sistema de correo de voz corporativa. Específicamente, puede configurarse un temporizador, y si la llamada sea contestada por correo de voz del transportista en el intervalo de tiempo definido, Skype para Business Server se desconectará del sistema de correo de voz del transportista (y correo de voz personal del usuario), mientras el usuario los extremos restantes del sistema corporativo continuarán al anillo. De este modo, el autor de la llamada se enruta automáticamente al correo de voz corporativa del usuario.
  
Esta configuración se realiza mediante el Skype cmdlet del Shell de administración de servidor de Business, **Conjunto CsVoicePolicy**, en el nivel de directiva de voz, con los siguientes parámetros.
  
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

#### 

[Configuración de directivas de voz y los registros de uso PSTN para autorizar los privilegios y las funciones de llamada](http://technet.microsoft.com/library/63f22010-a3d7-4cbd-86e8-6fc0e13c2b84.aspx)

