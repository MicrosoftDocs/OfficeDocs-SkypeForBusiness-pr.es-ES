---
title: Asignar directivas a un teléfono de área común
TOCTitle: Asignar directivas a un teléfono de área común
ms:assetid: f0554fd1-b237-49b3-9eb4-26f4b91f5604
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ994082(v=OCS.15)
ms:contentKeyID: 52061965
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Asignar directivas a un teléfono de área común

 

_**Última modificación del tema:** 2013-02-20_

Tras crear la directiva para teléfonos de área común (vea [Crear una directiva de voz y configurar registros de uso de RTC en Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md) para más información), dicha directiva se puede asignar a un teléfono de área común mediante Windows PowerShell y el cmdlet del **Grant-Cs** adecuado. Estos cmdlets se pueden ejecutar desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).


## Asignar una directiva a un solo teléfono de área común

  - Con el siguiente comando se asigna la directiva de voz por usuario RedmondVoice al teléfono de área común con la identidad Building 14 Lobby.
    
        Grant-CsVoicePolicy -Identity "Building 14 Lobby" -PolicyName "RedmondVoicePolicy"

## Asignar una directiva a varios teléfonos de área común

  - En este ejemplo, la directiva de voz por usuario RedmondVoice se asigna a todos los teléfonos de área común configurados para usarse en la organización.
    
        Get-CsCommonAreaPhone | Grant-CsVoicePolicy  -PolicyName "RedmondVoicePolicy"

Para más información detallada, vea los temas de ayuda relativos a [Grant-CsVoicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsVoicePolicy).

## Vea también

#### Otros recursos

[Get-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCommonAreaPhone)

