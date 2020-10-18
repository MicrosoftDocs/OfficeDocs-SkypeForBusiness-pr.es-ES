---
title: 'Lync Server 2013: crear una directiva de correo de voz hospedado de nivel de sitio'
description: 'Lync Server 2013: crear una directiva de correo de voz hospedado en el nivel de sitio.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a site-level hosted voice mail policy
ms:assetid: 145892c8-a6ca-45fb-9e83-786f709dd775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398216(v=OCS.15)
ms:contentKeyID: 48183481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8cd578359a8d20562e8887b61b86d53332e6f8d8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578376"
---
# <a name="create-a-site-level-hosted-voice-mail-policy-in-lync-server-2013"></a>Crear una directiva de correo de voz hospedado de nivel de sitio en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-24_

Una directiva del *sitio* puede afectar a todos los usuarios del sitio en el que la directiva en cuestión está definida. En caso de que un usuario esté configurado para tener acceso a la mensajería unificada de Exchange hospedada y no tenga asignada una directiva específica de usuario, se aplicará la directiva del sitio y, si no hay una directiva del sitio implementada, se usará la directiva global.

Para obtener más información sobre cómo configurar directivas de sitio, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:

  - [New-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [Get-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-site-hosted-voice-mail-policy"></a>Para crear una directiva de correo de voz hospedado del sitio

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet New-CsHostedVoicemailPolicy para crear la directiva. Por ejemplo, ejecute lo siguiente:
    
        New-CsHostedVoicemailPolicy -Identity site:Redmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for the Redmond site." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    Con este ejemplo se crea una directiva de correo de voz hospedado con ámbito de sitio y se establecen los parámetros descritos a continuación:
    
      - **Identity** hace referencia a un identificador único de la directiva, en el que se incluye el ámbito. Para una directiva con ámbito de sitio, el valor del parámetro Identity debe especificarse en el formato `site:` *\<name\>* , por ejemplo, `site:Redmond` .
    
      - **Destination** especifica el nombre de dominio completo (FQDN) del servicio de mensajería unificada de Exchange hospedado. Este parámetro es opcional pero, si trata de habilitar a un usuario para el correo de voz hospedado y la directiva asignada al usuario no tiene ningún valor de Destination, no podrá habilitarlo.
    
      - **Description** ofrece información descriptiva opcional acerca de la directiva.
    
      - **Organization** especifica una lista separada por comas de los inquilinos de Exchange que alojan a los usuarios de Lync Server 2013. Cada arrendatario se debe especificar como el FQDN del arrendatario en cuestión en el servicio de mensajería unificada de Exchange hospedado.

</div>

</div>

<span> </span>

</div>

</div>

</div>

