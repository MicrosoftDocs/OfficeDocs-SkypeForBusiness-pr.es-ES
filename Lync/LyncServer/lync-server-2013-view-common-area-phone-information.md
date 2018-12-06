---
title: Ver la información del teléfono de área común
TOCTitle: Ver la información del teléfono de área común
ms:assetid: e652240c-6a3f-4be7-a083-32f24c08e655
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ994081(v=OCS.15)
ms:contentKeyID: 52061898
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ver la información del teléfono de área común

 

_**Última modificación del tema:** 2013-02-20_

La información sobre los teléfonos de área común configurados para su uso en la organización se puede consultar mediante el cmdlet **Get-CsCommonAreaPhone**. Cuando se usa sin parámetros, este cmdlet devuelve información sobre todos los teléfonos de área común. Los parámetros opcionales permiten filtrar información de distintas maneras; así, por ejemplo, puede obtener todos los teléfonos de área común que tienen objetos de contacto en una unidad organizativa (OU) especificada o todos los objetos de contacto que se encuentran en un edificio determinado. Para ver detalles sobre los parámetros de **Get-CsCommonAreaPhone**, vea [Get-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCommonAreaPhone).

Ejecute **Get-CsCommonAreaPhone** desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.


## Ver información sobre todos los teléfonos de área común

  - Para ver información sobre todos los teléfonos de área común, escriba el siguiente comando en el Shell de administración de Lync Server y, a continuación, presione ENTRAR:
    
        Get-CsCommonAreaPhone
    
    Obtendrá información parecida a esta:
    
        Identity           : CN=Building 14 Lobby,OU=Redmond,
                             DC=litwareinc,DC=com
        RegistrarPool      : atl-cs-001.litwareinc.com
        Enabled            : True
        SipAddress         : sip:4714e34b-9781-421d-b07a-
                             52056b5b4a56@litwareinc.com
        ClientPolicy       :
        PinPolicy          :
        VoicePolicy        :
        MobilityPolicy     :
        GroupChatPolicy    :
        ConferencingPolicy :
        LineURI            : tel:+14255550712
        DisplayNumber      : 1-425-555-0712
        DisplayName        : Building 14 Lobby
        Description        :
        ExUmEnabled        : False

Para más información detallada, vea el tema de ayuda relativo al cmdlet [Get-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCommonAreaPhone).

