---
title: Configurar escape de buzón de voz en Skype Empresarial 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: 'Resumen: Obtenga información sobre cómo configurar escape de correo de voz de Skype para Business Server 2015 mediante el Skype para Shell de administración de servidor empresarial.'
ms.openlocfilehash: 2f8cf7549fd91c8153803a42f5dfb3b78a311e56
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568293"
---
# <a name="configure-voice-mail-escape-in-skype-for-business-2015"></a>Configurar escape de buzón de voz en Skype Empresarial 2015
 
**Resumen:** Obtenga información sobre cómo configurar escape de correo de voz de Skype para Business Server 2015 mediante el Skype para Shell de administración de servidor empresarial.
  
Cuando un usuario configura las llamadas simultáneas a un teléfono móvil, un autor de la llamada normalmente se enrutan al correo de voz personal del usuario si el teléfono móvil está desactivado, fuera de la energía de la batería o fuera del intervalo. Con Skype para Business Server, los usuarios pueden optar por hacer relacionados con el negocio llamadas enrutadas a su sistema de correo de voz corporativo. Específicamente, puede configurarse un temporizador, y si la llamada se ha atendido por correo de voz del proveedor dentro del intervalo de tiempo definido, Skype para Business Server se desconectará del sistema de correo de voz del proveedor (y correo de voz personal del usuario), mientras el usuario los extremos restantes en el sistema corporativo continuarán llamar a. De este modo, el autor de la llamada se enruta automáticamente al correo de voz corporativa del usuario.
  
Esta configuración se realiza mediante la Skype para cmdlet del Shell de administración de servidor empresarial, **Set-CsVoicePolicy**, en el nivel de directiva de voz, con los siguientes parámetros.
  
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

[Configuración de directivas de voz y registros de uso de RTC para autorizar privilegios y características de llamada](http://technet.microsoft.com/library/63f22010-a3d7-4cbd-86e8-6fc0e13c2b84.aspx)