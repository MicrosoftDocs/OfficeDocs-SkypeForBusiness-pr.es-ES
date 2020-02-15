---
title: 'Lync Server 2013: directrices para la integración de la mensajería unificada local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Guidelines for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 829ac017-6907-40f9-be22-787a28eae0ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398656(v=OCS.15)
ms:contentKeyID: 48184681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1be763250edf7222b900aef88665b3e360e8125c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006226"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="guidelines-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a>Directrices para la integración de la mensajería unificada local y Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-25_

A continuación, se ofrecen instrucciones y procedimientos recomendados que se deben tener en cuenta al implementar la telefonía IP empresarial:

<div>


> [!IMPORTANT]  
> La mensajería unificada (MU) de Exchange solo admite IPv6 si también usa UCMA 4.



</div>

  - Implemente un servidor Standard Edition de Lync Server 2013 o un grupo de servidores front-end. Para obtener más información acerca de la instalación, consulte [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) en la documentación sobre implementación.

  - Colabore con los administradores de Exchange para confirmar las tareas que realizará cada uno y así garantizar una integración correcta y homogénea.

  - Implemente los roles de servidor buzón de Exchange en cada bosque de mensajería unificada (MU) de Exchange en el que desee habilitar a los usuarios para la mensajería unificada de Exchange. Para obtener más información acerca de la instalación de los roles de servidor de Exchange, consulte la documentación de Microsoft Exchange Server 2013.
    
    <div>
    

    > [!IMPORTANT]  
    > Cuando se instala la mensajería unificada (UM) de Exchange, se configura para usar un certificado autofirmado.<BR>Sin embargo, el certificado autofirmado no permite que Lync Server 2013 y la mensajería unificada de Exchange confíen entre sí, por lo que es necesario solicitar un certificado independiente a una entidad de certificación en la que confían ambos servidores.

    
    </div>

  - Si Lync Server 2013 y mensajería unificada de Exchange están instalados en bosques distintos, configure cada bosque de Exchange para que confíe en el bosque de Lync Server 2013 y en el bosque de Lync Server 2013 para confiar en cada bosque de Exchange. Además, establezca la configuración de mensajería unificada de Exchange de los usuarios en los objetos de usuario del bosque de Lync Server 2013, normalmente mediante un script o una herramienta entre bosques, como Identity Lifecycle Manager (ILM).

  - Si es necesario, instale la Consola de administración de Exchange de modo que administre los servidores de mensajería unificada.

  - Obtenga números de teléfono válidos para Outlook Voice Access y el operador automático.

  - Si usa una versión de mensajería unificada de Exchange anterior a Microsoft Exchange Server 2010 Service Pack 1 (SP1), coordine los nombres de los planes de marcado de URI de SIP de mensajería unificada de Exchange y los planes de marcado de telefonía IP empresarial.

<div>

## <a name="deploying-redundant-exchange-um-servers"></a>Implementación de servidores redundantes de mensajería unificada de Exchange

<div>


> [!IMPORTANT]  
> Le recomendamos que implemente un mínimo de dos servidores en los que se ejecutan los servicios de mensajería unificada de Exchange para cada plan de marcado URI del SIP de mensajería unificada de Exchange que configure para su organización. Además de proporcionar capacidad ampliada, la implementación de servidores redundantes proporciona alta disponibilidad. En el caso de que se produzca un error en el servidor, Lync Server 2013 se puede configurar para que conmute por error a otro servidor.



</div>

Los siguientes ejemplos de configuraciones ofrecen resistencia a la mensajería unificada de Exchange.

**Ejemplo 1: resistencia de la mensajería unificada de Exchange**

![Ejemplo 1 de mensajería unificada de Exchange](images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "Ejemplo 1 de mensajería unificada de Exchange")

En el Ejemplo 1, los servidores de mensajería unificada de Exchange 1 y 2 están habilitados en el centro de datos de Tukwila, y los servidores de mensajería unificada de Exchange 3 y 4 están habilitados en el centro de datos de Dublín. En el caso de una interrupción de la mensajería unificada de Exchange en Tukwila, los registros A de sistema de nombres de dominio (DNS) para los servidores 1 y 2 deben configurarse para que apunten a los servidores 3 y 4, respectivamente. En el caso de una interrupción de la mensajería unificada de Exchange en Dublin, los registros A de DNS para los servidores 3 y 4 deben configurarse para que apunten a los servidores 1 y 2, respectivamente.

<div>


> [!NOTE]  
> En el Ejemplo 1, debe asignar también uno de los siguientes certificados a cada servidor de mensajería unificada de Exchange: 
> <UL>
> <LI>
> <P>Use un certificado con un carácter comodín en el Nombre alternativo de sujeto (SAN).</P>
> <LI>
> <P>Coloque el nombre de dominio completo (FQDN) de cada uno de los cuatro servidores de mensajería unificada de Exchange en el SAN.</P></LI></UL>



</div>

**Ejemplo 2: resistencia de la mensajería unificada de Exchange**

![Ejemplo 2 de mensajería unificada de Exchange](images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "Ejemplo 2 de mensajería unificada de Exchange")

En el Ejemplo 2, en condiciones normales de funcionamiento, los servidores de mensajería unificada de Exchange 1 y 2 están habilitados en el centro de datos de Tukwila, y los servidores de mensajería unificada de Exchange 3 y 4 están habilitados en el centro de datos de Dublín. Los cuatro servidores están incluidos en el plan de marcado URI del SIP de los usuarios de Tukwila; sin embargo, los servidores 3 y 4 están deshabilitados. En el caso de que se produzca una interrupción de la mensajería unificada de Exchange en Tukwila, por ejemplo, los servidores 1 y 2 de mensajería unificada de Exchange deben deshabilitarse y los servidores 3 y 4 de mensajería unificada de Exchange deben habilitarse para que el tráfico de mensajería unificada de Exchange de Tukwila se enrute a los servidores de Dublín.

Para obtener más información acerca de cómo habilitar o deshabilitar la mensajería unificada en Exchange 2013, consulte "integrar la mensajería unificada de Exchange 2013 con Lync Server" en [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372).

Para obtener más información acerca de cómo habilitar o deshabilitar la mensajería unificada en Microsoft Exchange Server 2010, consulte:

  - "Habilitar mensajería unificada en Exchange 2010" [http://go.microsoft.com/fwlink/p/?LinkId=204418](http://go.microsoft.com/fwlink/p/?linkid=204418)en.

  - "Deshabilitar la mensajería unificada en Exchange [http://go.microsoft.com/fwlink/p/?LinkId=204416](http://go.microsoft.com/fwlink/p/?linkid=204416)2010" en.

</div>

<div>

## <a name="see-also"></a>Vea también


[Proceso de implementación para la integración de la mensajería unificada local y Lync Server 2013](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

