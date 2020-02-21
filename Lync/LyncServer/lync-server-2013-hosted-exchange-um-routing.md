---
title: 'Lync Server 2013: enrutamiento de mensajería unificada de Exchange hospedado'
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
ms.openlocfilehash: bace74b58c706ef58d05e54e31d2f79ab587ba64
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198642"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-um-routing-in-lync-server-2013"></a>Enrutamiento de mensajería unificada de Exchange hospedado en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-01_

La aplicación de enrutamiento de mensajería unificada de Exchange se ejecuta en el servidor front-end para enrutar las llamadas, ya sea para una implementación local de mensajería unificada de Microsoft Exchange Server (MU) o para el servicio de mensajería unificada de Exchange hospedado.

<div>

## <a name="the-exum-routing-application"></a>La aplicación ExUM Routing

La aplicación Lync Server 2013 Exchange UM Routing usa información de la configuración de la cuenta de usuario y de los parámetros de la Directiva de correo de voz hospedado para determinar cómo enrutar las llamadas para la mensajería de voz hospedada, tal como se muestra en el siguiente diagrama.

**Ejemplo de implementación combinada del enrutamiento UM de Exchange**

![Implementación local de mensajería unificada de Lync Server Exchange](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "Implementación local de mensajería unificada de Lync Server Exchange")

El enrutamiento de mensajería unificada de Exchange se puede configurar para enrutar llamadas a los usuarios que están habilitados para la mensajería unificada de Exchange local, a los usuarios que están habilitados para la mensajería unificada de Exchange hospedada o a una combinación de los dos.

Por ejemplo, supongamos que el buzón de correo de la compañía y el servicio de mensajería unificada de Exchange están hospedados en una implementación local de Exchange.

  - La información de dirección proxy de la cuenta de usuario de Roy proporciona la información que la aplicación de enrutamiento de ExUM usa para enrutar las llamadas a un servidor de mensajería unificada de Exchange local.

El buzón de Alice y el servicio de mensajería unificada de Exchange se encuentran en el centro de datos de un proveedor de servicios de Exchange hospedado. El enrutamiento de sus llamadas de mensajería unificada de Exchange se configura de la siguiente manera:

  - Los valores establecidos en el atributo msExchUCVoiceMailSettings de la cuenta de usuario de Alicia le dice a la aplicación ExUM Routing que compruebe los detalles de enrutamiento en una directiva de correo de voz hospedado.
    
    <div>
    

    > [!NOTE]  
    > El valor del atributo msExchUCVoiceMailSettings puede establecerse por el proveedor de servicios de Exchange o el administrador de Lync Server 2013. En el ejemplo que se muestra en el diagrama anterior, el administrador de Lync Server 2013 estableció el valor (CsHostedVoiceMail = 1) para habilitar el correo de voz hospedado en Alicia. Para obtener más información sobre este atributo, consulte <A href="lync-server-2013-hosted-exchange-user-management.md">Hosted Exchange User Management in Lync Server 2013</A>.

    
    </div>

  - La directiva de correo de voz hospedado que se ha asignado a la cuenta de usuario de Alicia proporciona la siguiente información de enrutamiento:
    
      - Destination es el proveedor de servicios de mensajería unificada de Exchange hospedado (LS. ExUm. \<hostedExchangeServer\>. com en este ejemplo).
    
      - Las organizaciones se identifican por los identificadores de inquilino, que son los FQDN de enrutamiento de los mensajes SIP para los inquilinos de Exchange Server que se encuentran en LS. ExUm. \<hostedExchangeServer\>. com (Corp.contoso.com y Corp.litwareinc.com en este ejemplo).
        
        <div>
        

        > [!NOTE]  
        > El FQDN para Exchange Online es exap.um.outlook.com.

        
        </div>
        
        Para obtener más información, consulte [directivas de correo de voz hospedado en Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md).

<div>


> [!NOTE]  
> Si tanto el atributo msExchUCVoiceMailSettings como la configuración de la dirección proxy de mensajería unificada están presentes en una cuenta de usuario, el atributo msExchUCVoiceMailSettings tendrá prioridad.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

