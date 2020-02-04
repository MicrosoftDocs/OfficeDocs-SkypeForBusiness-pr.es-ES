---
title: 'Lync Server 2013: Habilitar a los usuarios para el correo de voz hospedado'
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
ms.openlocfilehash: 8e0ce9ee4da6ee0a36e5e5f0028371aab8af523f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736010"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-hosted-voice-mail-in-lync-server-2013"></a>Habilitar a los usuarios para el correo de voz hospedado en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-24_

Siga el procedimiento para habilitar a los usuarios de Lync Server 2013 para el correo de voz en un servicio de mensajería unificada (UM) hospedada de Exchange.

Para obtener más información, vea [Administración de usuarios de Exchange hospedado en Lync Server 2013](lync-server-2013-hosted-exchange-user-management.md) en la documentación de planeación.

Para obtener más información sobre el cmdlet [set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) , consulte la documentación del shell de administración de Lync Server.

<div>


> [!IMPORTANT]  
> Para que un usuario de Lync Server 2013 pueda estar habilitado para el correo de voz hospedado, debe implementarse una directiva de correo de voz hospedada que se aplique a su cuenta de usuario. Para obtener más información, consulte <A href="lync-server-2013-hosted-voice-mail-policies.md">directivas de correo de voz hospedado en Lync Server 2013</A>.



</div>

<div>

## <a name="to-enable-users-for-hosted-voice-mail"></a>Para habilitar a los usuarios para el correo de voz hospedado

1.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet Set-CsUser para configurar la cuenta de usuario para el correo de voz hospedado. Por ejemplo, ejecute lo siguiente:
    
        Set-CsUser -HostedVoiceMail $True -Identity "contoso\kenmyer"
    
    En el ejemplo anterior se definen los parámetros siguientes:
    
      - **HostedVoiceMail** permite enrutar las llamadas de correo de voz de un usuario a la mensajería unificada de Exchange hospedada. También indica a Microsoft Lync 2013 que ilumine el indicador "llamar al correo de voz".
    
      - **Identity** especifica la cuenta de usuario que se va a modificar. El valor de identidad puede especificarse con cualquiera de los siguientes formatos:
        
          - Dirección SIP del usuario
        
          - Nombre principal de usuario de Active Directory del usuario
        
          - Nombre de inicio de\\sesión de dominio del usuario (por\\ejemplo, contoso kenmyer)
        
          - El nombre para mostrar de los servicios de dominio de Active Directory del usuario (por ejemplo, Ken Myer). Si usa el nombre para mostrar como valor de identidad, puede usar el carácter comodín asterisco\*(). Por ejemplo, la identidad "\* Smith" devuelve todos los usuarios que tienen un nombre para mostrar que termina con el valor de cadena "Smith".
        
        <div>
        

        > [!NOTE]  
        > El nombre de cuenta SAM del usuario de Active Directory no se puede usar como valor de identidad porque el nombre de cuenta SAM no es necesariamente único en el bosque.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

