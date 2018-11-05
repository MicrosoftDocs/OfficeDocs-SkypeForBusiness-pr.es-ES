---
title: Crear o modificar un objeto de contacto de dispositivo de conferencias
TOCTitle: Crear o modificar un objeto de contacto de dispositivo de conferencias
ms:assetid: 62ed64be-379c-417d-9453-511881cf5604
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ994035(v=OCS.15)
ms:contentKeyID: 52061650
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Crear o modificar un objeto de contacto de dispositivo de conferencias

 

_**Última modificación del tema:** 2013-10-02_

Para crear un objeto de sala de conferencias, primero cree una cuenta de usuario de Active Directory para representar el dispositivo. A continuación, use el cmdlet **Enable-CsMeetingRoom** para habilitar dicha cuenta para que funcione como un dispositivo de conferencias. Si necesita cambiar las propiedades de un dispositivo de conferencias existente, use el cmdlet **Set-CsMeetingRoom**.

Estos cmdlets se pueden ejecutar desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.


> [!NOTE]
> Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.




## Creación de un dispositivo de conferencias

  - Una vez creada la cuenta de usuario de Active Directory que representa el nuevo dispositivo de conferencias, habilítela mediante el cmdlet **Enable-CsMeetingRoom**. Asegúrese de incluir a) la identidad del dispositivo de conferencias, b) el grupo de registradores donde se alojará la cuenta de sala y c) la dirección SIP que se asignará a dicha cuenta. Por ejemplo:
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

## Modificación de un dispositivo de conferencias

  - Para modificar los valores de propiedad de un dispositivo de conferencias existente, use el cmdlet **Set-CsMeetingRoom**. Por ejemplo, el siguiente comando actualiza el número de teléfono (LineUri) asociado con un dispositivo de conferencias:
    
        Set-CsMeetingRoom -Identity "Redmond Conferencing device" -LineUri "tel:+12065551219"

Para obtener detalles, consulte los temas de Ayuda acerca de los cmdlets [Enable-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Enable-CsMeetingRoom) y [Set-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsMeetingRoom).

