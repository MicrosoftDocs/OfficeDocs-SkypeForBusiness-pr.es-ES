---
title: 'Lync Server 2013: ver información de teléfono de área común'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View common area phone information
ms:assetid: e652240c-6a3f-4be7-a083-32f24c08e655
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994081(v=OCS.15)
ms:contentKeyID: 51803992
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 900beb4f96fd71e0e6a4ded40d776f1e7d356529
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850123"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-common-area-phone-information-in-lync-server-2013"></a>Ver la información de los teléfonos comunes en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-20_

Puede ver información sobre los teléfonos de área común configurados para su uso en su organización mediante el cmdlet **Get-CsCommonAreaPhone** . Si se usa sin parámetros, este cmdlet devuelve información sobre todos los teléfonos de área común. Los parámetros opcionales proporcionan distintas formas de filtrar la información. Por ejemplo, puede devolver todos los teléfonos de área común que tengan objetos de contacto en una unidad organizativa determinada o todos los objetos de contactos que se encuentran en un edificio especificado. Para obtener más información sobre los parámetros **Get-CsCommonAreaPhone** , vea [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone).

Ejecute **Get-CsCommonAreaPhone** desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.

<div>


<div>

## <a name="viewing-information-about-all-your-common-area-phones"></a>Ver información sobre todos los teléfonos comunes de área

  - Para ver información sobre todos los teléfonos comunes de área, escriba el siguiente comando en el shell de administración de Lync Server y, a continuación, presione ENTRAR:
    
        Get-CsCommonAreaPhone
    
    Obtendrás información similar a la siguiente:
    
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

</div>

Para obtener más información, vea el tema de ayuda sobre el cmdlet [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

