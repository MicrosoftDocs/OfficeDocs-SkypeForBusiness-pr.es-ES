---
title: 'Lync Server 2013: Enrutamiento de mensajería unificada de Exchange hospedada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange UM routing
ms:assetid: 6c90dc8b-6aef-4ce8-b483-37c7b5a553c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398512(v=OCS.15)
ms:contentKeyID: 48184422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e04198813f7bb0647671dbb23e12889b108ee846
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739010"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-um-routing-in-lync-server-2013"></a>Enrutamiento de mensajería unificada de Exchange hospedada en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-01_

La aplicación de enrutamiento de mensajería unificada de Exchange se ejecuta en el servidor front-end para enrutar llamadas, ya sea a una implementación local de mensajería unificada (UM) de Microsoft Exchange Server o a un servicio de mensajería unificada de Exchange hospedado.

<div>

## <a name="the-exum-routing-application"></a>La aplicación de enrutamiento ExUM

La aplicación Lync Server 2013 Exchange UM Routing usa información de la configuración de la cuenta de usuario y de los parámetros de la Directiva de voz hospedada para determinar cómo enrutar las llamadas para la mensajería de voz hospedada, como se muestra en el siguiente diagrama.

**Ejemplo de implementación mixta enrutamiento de mensajería unificada de Exchange**

![Implementación de mensajería unificada de Exchange de Lync Server local](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "Implementación de mensajería unificada de Exchange de Lync Server local")

El enrutamiento de MU de Exchange se puede configurar para que enrute las llamadas a los usuarios que están habilitados para la mensajería unificada de Exchange local para los usuarios que están habilitados para la mensajería unificada de Exchange hospedada o para una combinación de ambas.

Por ejemplo, supongamos que el buzón de la compañía y el servicio MU de Exchange están alojados en una implementación de Exchange local.

  - La información de dirección del proxy de la cuenta de usuario de Roy proporciona la información que la aplicación de enrutamiento de ExUM usa para enrutar las llamadas a un servidor local de mensajería unificada de Exchange.

El buzón de Alice y el servicio MU de Exchange se encuentran en el centro de datos de un proveedor de servicios de Exchange hospedado. El enrutamiento de las llamadas de mensajería unificada de Exchange es el siguiente:

  - Los valores establecidos en el atributo msExchUCVoiceMailSettings de la cuenta de usuario de Alice indican a la aplicación de enrutamiento de ExUM que compruebe los detalles de enrutamiento en una directiva de correo de voz hospedado.
    
    <div>
    

    > [!NOTE]  
    > El valor del atributo msExchUCVoiceMailSettings puede ser establecido por el proveedor de servicios de Exchange o el administrador de Lync Server 2013. En el ejemplo que se muestra en el diagrama anterior, el administrador de Lync Server 2013 estableció el valor (CsHostedVoiceMail = 1) para habilitar el correo de voz hospedado para Alice. Para obtener más información sobre este atributo, consulte <A href="lync-server-2013-hosted-exchange-user-management.md">Administración de usuarios de Exchange hospedado en Lync Server 2013</A>.

    
    </div>

  - La Directiva de correo de voz hospedada que se asigna a la cuenta de usuario de Alice proporciona detalles de enrutamiento:
    
      - Destino es el proveedor de servicios de mensajería unificada de Exchange hospedado (LS. ExUm. \<hostedExchangeServer\>. com en este ejemplo).
    
      - Las organizaciones se identifican por los identificadores de inquilino, que son los FQDN de enrutamiento de los mensajes SIP para los inquilinos de Exchange Server que se encuentran en LS. ExUm. \<hostedExchangeServer\>. com (Corp.contoso.com y Corp.litwareinc.com en este ejemplo).
        
        <div>
        

        > [!NOTE]  
        > El FQDN de Exchange Online es exap.um.outlook.com.

        
        </div>
        
        Para obtener más información, consulte [directivas de correo de voz hospedado en Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md).

<div>


> [!NOTE]  
> Si el atributo msExchUCVoiceMailSettings y la configuración de la dirección proxy de UM están presentes en una cuenta de usuario, el atributo msExchUCVoiceMailSettings tiene prioridad.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

