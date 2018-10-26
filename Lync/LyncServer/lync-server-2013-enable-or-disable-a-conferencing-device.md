---
title: Habilitar o deshabilitar un dispositivo de conferencias
TOCTitle: Habilitar o deshabilitar un dispositivo de conferencias
ms:assetid: d5140e38-d015-4706-9bde-cf2fa748c36b
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ994070(v=OCS.15)
ms:contentKeyID: 52061774
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Habilitar o deshabilitar un dispositivo de conferencias

 

_**Última modificación del tema:** 2013-02-20_

Habilite y deshabilite un dispositivo de conferencia mediante los cmdlets **Enable-CsMeetingRoom** y **Disable-CsMeetingRoom**. Estos cmdlets se ejecutan desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.


> [!NOTE]
> Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.




## Habilitar el dispositivo de conferencia

  - Para habilitar un dispositivo de conferencia, use el cmdlet **Enable-CsMeetingRoom**. Al hacerlo, debe especificar a) una identidad de dispositivo de conferencia, b) el grupo de registradores donde se va a hospedar la cuenta de la sala y c) la dirección SIP que se va a asignar a dicha cuenta.
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

## Deshabilitar el dispositivo de conferencia

  - Para deshabilitar un dispositivo de conferencia, use el cmdlet **Disable-CsMeetingRoom**. Procure especificar la identidad del dispositivo de conferencia que se va a deshabilitar:
    
        Disable-CsMeetingRoom -Identity "sip:RedmondMeetingRoom@litwareinc.com"

Para ver detalles, consulte los temas de ayuda relativos a los cmdlets [Enable-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Enable-CsMeetingRoom) y [Disable-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Disable-CsMeetingRoom).

