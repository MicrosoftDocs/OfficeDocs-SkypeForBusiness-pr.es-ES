---
title: 'Lync Server 2013: modificar la Directiva de correo de voz hospedado global'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the global hosted voice mail policy
ms:assetid: f059b3ce-a7d8-4ea9-b10b-0052222ec2ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412994(v=OCS.15)
ms:contentKeyID: 48185757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88d0e29981df18ed883d6c33fb810d86da09d255
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184803"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-the-global-hosted-voice-mail-policy-in-lync-server-2013"></a>Modifique la directiva global de correo de voz hospedado en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-24_

La Directiva de correo de voz hospedado *global* se instala con Lync Server 2013. Modifíquela para adaptarla a sus necesidades, aunque no puede cambiarle el nombre ni eliminarla. Para modificar la directiva global, use el cmdlet Set-CsHostedVoicemailPolicy para establecer los parámetros en los valores apropiados para su implementación específica.

Para obtener más información sobre el cmdlet [set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy) , consulte la documentación del shell de administración de Lync Server.

<div>

## <a name="to-modify-the-global-hosted-voice-mail-policy"></a>Para modificar la directiva global de correo de voz hospedado

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet Set-CsHostedVoicemailPolicy para establecer los parámetros de directiva global de su entorno. Por ejemplo, ejecute:
    
        Set-CsHostedVoicemailPolicy -Destination ExUM.fabrikam.com -Organization "corp1.litwareinc.com"
    
    Debido a que este comando no especifica el parámetro Identity de la Directiva, la interfaz de línea de comandos de Windows PowerShell establece los valores siguientes en la Directiva de correo de voz hospedado global:
    
      - **Destination** especifica el nombre de dominio completo (FQDN) del servicio de mensajería unificada de Exchange hospedado. Este parámetro es opcional pero, si trata de habilitar a un usuario para el correo de voz hospedado y la directiva asignada al usuario no tiene ningún valor de Destination, no podrá habilitarlo.
    
      - **Organization** especifica una lista separada por comas de los inquilinos de Exchange que alojan a los usuarios de Lync Server. Cada arrendatario se debe especificar como el FQDN del arrendatario en cuestión en el servicio de mensajería unificada de Exchange hospedado.
    
    <div>
    

    > [!NOTE]  
    > En el cmdlet de ejemplo anterior, el valor "corp1.litwareinc.com" reemplaza cualquier valor que ya esté presente en el parámetro Organization. Por ejemplo, si la directiva ya contiene una lista separada por comas de organizaciones, se reemplazará la lista completa. Si desea agregar una organización a la lista en lugar de reemplazar la lista completa, ejecute un comando similar al siguiente.

    
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

