---
title: "Conf. de la redirection vers la messagerie vocale dans Lync Server 2013"
TOCTitle: "Conf. de la redirection vers la messagerie vocale dans Lync Server 2013"
ms:assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688157(v=OCS.15)
ms:contentKeyID: 49889508
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de escape en correo de voz en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-22_

Cuando un usuario configura llamadas simultáneas a un teléfono móvil, normalmente se enrutará al autor de la llamada al buzón de voz personal del usuario si el teléfono móvil está apagado, fuera de cobertura o se ha quedado sin batería. Con Microsoft Lync Server 2013, los usuarios pueden optar por que las llamadas de trabajo se enruten a su sistema de buzón de voz corporativo. Además, puede configurarse un temporizador de manera que, si la llamada la responde el buzón de voz del operador, dentro del intervalo de tiempo definido, Lync Server 2013 desconectará del sistema de buzón de voz del operador (y del buzón de voz personal del usuario), mientras que los extremos restantes del sistema corporativo del usuario seguirán sonando. De esta manera, se enrutará automáticamente al autor de la llamada al buzón de voz corporativo del usuario.

Esta configuración se lleva a cabo mediante el cmdlet Set-CsVoicePolicy del Shell de administración de Lync Server a nivel de la directiva de voz con los siguientes parámetros.

## Configurar escape de buzón de voz

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Especificar los siguientes parámetros en **Set-CsVoicePolicy**:
    
      - **EnableVoicemailEscapeTimer**: habilita o deshabilita el temporizador de escape.
    
      - **PSTNVoicemailEscapeTimer**: especifica el valor de tiempo de espera en milisegundos. El valor predeterminado es 1500 milisegundos y puede variar de 0 a 8000 milisegundos.

## Ejemplo

    Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
    
    Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500

## Vea también

#### Otros recursos

[Configurar directivas de voz y registros de uso de la RTC para autorizar características y privilegios de llamada en Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)

