---
title: 'Lync Server 2013: modificar la Directiva de correo de voz hospedado global'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify the global hosted voice mail policy
ms:assetid: f059b3ce-a7d8-4ea9-b10b-0052222ec2ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412994(v=OCS.15)
ms:contentKeyID: 48185757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4759fd0cfe4f8a4c55905b265c2418354a6a6dae
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826797"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-global-hosted-voice-mail-policy-in-lync-server-2013"></a>Modificar la Directiva de correo de voz hospedado global en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-24_

La Directiva de correo de voz hospedado *global* se instala con Lync Server 2013. Puede modificarla para satisfacer sus necesidades, pero no puede cambiarle el nombre ni eliminarla. Para modificar la directiva global, use el cmdlet Set-CsHostedVoicemailPolicy para establecer los parámetros en los valores adecuados para su implementación específica.

Para obtener más información sobre el cmdlet [set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy) , consulte la documentación del shell de administración de Lync Server.

<div>

## <a name="to-modify-the-global-hosted-voice-mail-policy"></a>Para modificar la Directiva de correo de voz hospedado global

1.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet Set-CsHostedVoicemailPolicy para establecer los parámetros de directiva global de su entorno. Por ejemplo, ejecute lo siguiente:
    
        Set-CsHostedVoicemailPolicy -Destination ExUM.fabrikam.com -Organization "corp1.litwareinc.com"
    
    Debido a que este comando no especifica el parámetro de identidad de la Directiva, la interfaz de línea de comandos de Windows PowerShell establece los siguientes valores en la Directiva de correo de voz hospedado global:
    
      - **Destino** especifica el nombre de dominio completo (FQDN) del servicio de mensajería unificada de Exchange hospedado. Este parámetro es opcional, pero si intenta habilitar un usuario para el correo de voz hospedado y la directiva asignada al usuario no tiene un valor de destino, se producirá un error de habilitar.
    
      - **Organización** especifica una lista separada por comas de los inquilinos de Exchange que alojan usuarios de Lync Server. Cada inquilino debe especificarse como el FQDN de ese inquilino en el servicio de mensajería unificada de Exchange hospedado.
    
    <div>
    

    > [!NOTE]  
    > En el cmdlet de ejemplo anterior, el valor "corp1.litwareinc.com" reemplaza cualquier valor que ya pudiera estar presente en el parámetro de organización. Por ejemplo, si la directiva ya contiene una lista de organizaciones separadas por comas, se reemplazaría la lista completa. Si desea agregar una organización a la lista en lugar de reemplazar toda la lista, ejecute un comando similar al siguiente.

    
    </div>
    
        $a = Get-CsHostedVoicemailPolicy
        $a.Organization += ",corp3.litwareinc.com"
        Set-CsHostedVoicemailPolicy -Organization $a.Organization

</div>

</div>

<span> </span>

</div>

</div>

</div>

