---
title: 'Lync Server 2013: habilitar usuarios para correo de voz hospedado'
description: 'Lync Server 2013: habilite a los usuarios para el correo de voz hospedado.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for hosted voice mail
ms:assetid: fa559f8f-ef99-43a1-b580-9e998b95efb8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413062(v=OCS.15)
ms:contentKeyID: 48185919
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3853a70d433c09029a02f2ca6256b5988defdcb2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572746"
---
# <a name="enable-users-for-hosted-voice-mail-in-lync-server-2013"></a>Habilitar a los usuarios para el correo de voz hospedado en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-24_

Siga el procedimiento para habilitar a los usuarios de Lync Server 2013 para el correo de voz en un servicio de mensajería unificada (UM) de Exchange hospedado.

Para obtener más información, consulte [Hosted Exchange User Management in Lync Server 2013](lync-server-2013-hosted-exchange-user-management.md) en la documentación referente a la planeación.

Para obtener más información sobre el cmdlet [set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) , consulte la documentación del shell de administración de Lync Server.

<div>


> [!IMPORTANT]  
> Antes de que un usuario de Lync Server 2013 pueda estar habilitado para el correo de voz hospedado, debe implementarse una directiva de correo de voz hospedada que se aplique a su cuenta de usuario. Para obtener más información, consulte <A href="lync-server-2013-hosted-voice-mail-policies.md">directivas de correo de voz hospedado en Lync Server 2013</A>.



</div>

<div>

## <a name="to-enable-users-for-hosted-voice-mail"></a>Para habilitar a los usuarios para correo de voz hospedado.

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet Set-CsUser para configurar la cuenta del usuario para correo de voz hospedado. Por ejemplo, ejecute lo siguiente:
    
        Set-CsUser -HostedVoiceMail $True -Identity "contoso\kenmyer"
    
    En el ejemplo anterior se definen los parámetros siguientes:
    
      - **HostedVoiceMail** permite que las llamadas de correo de voz de un usuario se enruten a una versión hospedada de mensajería instantánea de Exchange. También indica a Microsoft Lync 2013 que ilumine el indicador "llamar al correo de voz".
    
      - **Identity** especifica la cuenta de usuario que modificar. El valor de Identity puede especificarse con cualquiera de los formatos a continuación:
        
          - La dirección SIP del usuario
        
          - El nombre principal de usuario de Active Directory del usuario
        
          - El nombre de inicio de sesión del dominio del usuario \\ (por ejemplo, contoso \\ kenmyer)
        
          - El nombre para mostrar de Servicios de dominio de Active Directory (por ejemplo, Ken Myer). Si usa el Display-Name como valor de identidad, puede usar el \* carácter comodín asterisco (). Por ejemplo, la identidad " \* Smith" devuelve todos los usuarios que tienen una Display-Name que termina con el valor de cadena "Smith".
        
        <div>
        

        > [!NOTE]  
        > El nombre de cuenta SAM de Active Directory del usuario no se puede usar como valor de Identity porque puede que no sea único en el bosque.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

