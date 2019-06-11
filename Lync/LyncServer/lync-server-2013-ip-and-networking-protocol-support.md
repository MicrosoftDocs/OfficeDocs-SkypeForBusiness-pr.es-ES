---
title: 'Lync Server 2013: Compatibilidad con protocolo IP y de red'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IP and networking protocol support
ms:assetid: b0cffb10-3478-445c-89c7-8cb8b5027424
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412848(v=OCS.15)
ms:contentKeyID: 48185128
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a35395c9bb7eb8d90e5618ba6afde17defdbbcfd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834951"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ip-and-networking-protocol-support-in-lync-server-2013"></a>Compatibilidad con protocolo IP y de red en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

Lync Server 2013 admite los siguientes protocolos de IP y de red:

  - **Protocolos IP.**    Lync Server 2013 admite IP versión 4 (IPv4) o IP versión 6 (IPv6) para la red del servidor.
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 puede funcionar en una red con dos pilas IP habilitadas.

    
    </div>

  - **Protocolos de transporte SIP.**    De forma genérica, SIP puede usar al menos tres tipos de transporte: Protocolo de datagrama de usuario (UDP), protocolo de control de transmisión (TCP) y seguridad de nivel de transporte (TLS). En la configuración de transporte SIP predeterminada, TLS se ejecuta sobre TCP. TLS se usa dentro de la red de Lync Server 2013. En el extremo de la red, Lync Server 2013 puede interoperar sobre TCP. Lync Server 2013 no admite UDP para el transporte SIP porque no cumple con los estándares mínimos de seguridad, confiabilidad y escalabilidad de las comunicaciones empresariales. Para obtener más información, vea el artículo del blog de NextHop, "to UDP, o not to UDP, que es la [http://go.microsoft.com/fwlink/p/?linkId=185369](http://go.microsoft.com/fwlink/p/?linkid=185369)pregunta" en.
    
    <div>
    

    > [!NOTE]  
    > El contenido de los blogs y sus URL están sujetos a cambios sin previo aviso.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

