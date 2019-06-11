---
title: 'Lync Server 2013: crear una directiva de correo de voz hospedado por usuario'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a per-user hosted voice mail policy
ms:assetid: 39018a7c-e0c3-46a2-be4e-05604ec67a50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425867(v=OCS.15)
ms:contentKeyID: 48183902
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d09638c28c1cbd2b068972aff169376508325885
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842077"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a>Crear una directiva de correo de voz hospedada por usuario en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-24_

Una directiva *por usuario* solo puede afectar a usuarios individuales, grupos y objetos de contacto. Para implementar una directiva por usuario, debe asignarla explícitamente a uno o más usuarios, grupos o objetos de contacto. Para obtener más información, vea [asignar una directiva de correo de voz hospedado por usuario en Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md).

Para obtener más información sobre cómo trabajar con directivas de correo de voz hospedado por usuario, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:

  - [Nuevo: CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [Get-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-per-user-hosted-voice-mail-policy"></a>Para crear una directiva de correo de voz hospedado por usuario

1.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet New-CsHostedVoicemailPolicy para crear la Directiva. Por ejemplo, ejecute lo siguiente:
    
        New-CsHostedVoicemailPolicy -Identity ExRedmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for Redmond users." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    En el ejemplo anterior se crea una directiva de correo de voz hospedada con ámbito por usuario y se establecen los siguientes parámetros:
    
      - **Identity** especifica un identificador único para la Directiva, que incluye el ámbito. Para una directiva con ámbito por usuario, este valor de parámetro se especifica como una cadena simple, por ejemplo, en mi Redmond.
    
      - **Destino** especifica el nombre de dominio completo (FQDN) del servicio de mensajería unificada de Exchange hospedado. Este parámetro es opcional, pero si intenta habilitar un usuario para el correo de voz hospedado y la directiva asignada al usuario no tiene un valor de destino, se producirá un error de habilitar.
    
      - **Descripción** proporciona información descriptiva opcional sobre la Directiva.
    
      - **Organización** especifica una lista separada por comas de los inquilinos de Exchange que alojan los usuarios de Lync Server 2013. Cada inquilino debe especificarse como el FQDN de ese inquilino en el servicio de mensajería unificada de Exchange hospedado.

</div>

<div>

## <a name="see-also"></a>Vea también


[Asignar una directiva de correo de voz hospedado por usuario en Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

