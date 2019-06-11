---
title: 'Lync Server 2013: crear una directiva de correo de voz hospedado en el nivel de sitio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a site-level hosted voice mail policy
ms:assetid: 145892c8-a6ca-45fb-9e83-786f709dd775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398216(v=OCS.15)
ms:contentKeyID: 48183481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9df91e28eeba8bc9769e4fcbeff6ebba2b3746d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842076"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-site-level-hosted-voice-mail-policy-in-lync-server-2013"></a>Crear una directiva de correo de voz hospedado en el nivel de sitio en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-24_

Una directiva de *sitio* puede afectar a todos los usuarios alojados en el sitio para el que se define la Directiva. Si un usuario está configurado para el acceso a mensajería unificada de Exchange hospedado y no se le ha asignado una directiva por usuario, se aplicará la Directiva de sitio. Si no ha implementado una directiva de sitio, se aplica la directiva global.

Para obtener más información sobre cómo configurar directivas de sitio, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:

  - [Nuevo: CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [Get-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-site-hosted-voice-mail-policy"></a>Para crear una directiva de correo de voz hospedada en un sitio

1.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet New-CsHostedVoicemailPolicy para crear la Directiva. Por ejemplo, ejecute lo siguiente:
    
        New-CsHostedVoicemailPolicy -Identity site:Redmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for the Redmond site." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    En este ejemplo se crea una directiva de correo de voz hospedada con ámbito de sitio y se establecen los siguientes parámetros:
    
      - **Identity** especifica un identificador único para la Directiva, que incluye el ámbito. Para una directiva con ámbito de sitio, el valor del parámetro Identity debe especificarse en `site:` * \<el\>nombre*de formato, `site:Redmond`por ejemplo,.
    
      - **Destino** especifica el nombre de dominio completo (FQDN) del servicio de mensajería unificada de Exchange hospedado. Este parámetro es opcional, pero si intenta habilitar un usuario para el correo de voz hospedado y la directiva asignada al usuario no tiene un valor de destino, se producirá un error de habilitar.
    
      - **Descripción** proporciona información descriptiva opcional sobre la Directiva.
    
      - **Organización** especifica una lista separada por comas de los inquilinos de Exchange que alojan los usuarios de Lync Server 2013. Cada inquilino debe especificarse como el FQDN de ese inquilino en el servicio de mensajería unificada de Exchange hospedado.

</div>

</div>

<span> </span>

</div>

</div>

</div>

