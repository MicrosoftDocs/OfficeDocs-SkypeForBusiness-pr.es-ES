---
title: 'Lync Server 2013: configurar el escape de correo de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice mail escape
ms:assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688157(v=OCS.15)
ms:contentKeyID: 49733761
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 131b36b87a3d930662cdd863dd4ebc1d0d69163e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029953"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-mail-escape-in-lync-server-2013"></a>Configurar el escape de correo de voz en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-22_

Cuando un usuario configura llamadas simultáneas a un teléfono móvil, normalmente se enrutará al autor de la llamada al buzón de voz personal del usuario si el teléfono móvil está apagado, fuera de cobertura o se ha quedado sin batería. Con Lync Server 2013, los usuarios pueden optar por hacer que las llamadas relacionadas con la empresa se enruten a su sistema de correo de voz corporativo. En concreto, se puede configurar un temporizador y, si la llamada se responde por el correo de voz del transportista dentro del intervalo de tiempo definido, Lync Server se desconectará del sistema de correo de voz del operador (y del correo de voz personal del usuario), mientras que el resto del usuario los puntos de conexión del sistema corporativo continúan sonando. De esta manera, se enrutará automáticamente al autor de la llamada al buzón de voz corporativo del usuario.

Esta configuración se lleva a cabo mediante el cmdlet del shell de administración de Lync Server, **set-CsVoicePolicy**, en el nivel de la Directiva de voz, con los siguientes parámetros.

<div>

## <a name="to-configure-voice-mail-escape"></a>Para configurar el escape de correo de voz

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  Especificar los siguientes parámetros en **Set-CsVoicePolicy**:
    
      - **EnableVoicemailEscapeTimer**: habilita o deshabilita el temporizador de escape.
    
      - **PSTNVoicemailEscapeTimer**: especifica el valor de tiempo de espera en milisegundos. El valor predeterminado es 1500 milisegundos y puede variar de 0 a 8000 milisegundos.

</div>

<div>

## <a name="example"></a>Ejemplo

    Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
    
    Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500

</div>

<div>

## <a name="see-also"></a>Vea también


[Configurar directivas de voz y registros de uso de RTC para autorizar características y privilegios de llamada en Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

