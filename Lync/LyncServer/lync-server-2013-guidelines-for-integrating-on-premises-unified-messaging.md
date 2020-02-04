---
title: 'Lync Server 2013: Instrucciones para integrar mensajería unificada local y Lync Server'
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
ms.openlocfilehash: 3f3e57245f0a8edf5b545f9a67547e6be6f63399
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739620"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="guidelines-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a>Instrucciones para integrar mensajería unificada local y Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-25_

Los siguientes procedimientos recomendados e instrucciones debe tenerse en cuenta cuando implemente Telefonía IP empresarial:

<div>


> [!IMPORTANT]  
> La mensajería unificada de Exchange (UM) solo admite IPv6 si también usa UCMA 4.



</div>

  - Implementar un servidor de Lync Server 2013 Standard Edition o un grupo de servidores front-end. Para obtener más información acerca de la instalación, consulte [implementar Lync Server 2013](lync-server-2013-deploying-lync-server.md) en la documentación de implementación.

  - Colabore con los administradores de Exchange para confirmar las tareas que realizará cada uno y así garantizar una integración correcta y homogénea.

  - Implemente los roles de servidor de buzón de Exchange en cada bosque de mensajería unificada (UM) de Exchange donde desee habilitar usuarios para la mensajería unificada de Exchange. Para obtener más información sobre la instalación de los roles de servidor de Exchange, consulte la documentación de Microsoft Exchange Server 2013.
    
    <div>
    

    > [!IMPORTANT]  
    > Cuando se instala mensajería unificada de Exchange (UM), se configura para usar un certificado autofirmado.<BR>El certificado autofirmado, sin embargo, no permite que Lync Server 2013 y la mensajería unificada de Exchange confíen entre sí, razón por la cual es necesario solicitar un certificado independiente de una entidad emisora de certificados en la que confíen ambos servidores.

    
    </div>

  - Si Lync Server 2013 y mensajería unificada de Exchange se instalan en bosques diferentes, configure cada bosque de Exchange para que confíe en el bosque de Lync Server 2013 y en el bosque de Lync Server 2013 para confiar en cada uno de los bosques de Exchange. Además, establezca la configuración de mensajería unificada de los usuarios en los objetos de usuario del bosque de Lync Server 2013, generalmente usando una secuencia de comandos o una herramienta entre bosques, como Identity Lifecycle Manager (ILM).

  - Si es necesario, instale la Consola de administración de Exchange de modo que administre los servidores de mensajería unificada.

  - Obtenga números de teléfono válidos para Outlook Voice Access y el operador automático.

  - Si usa una versión de mensajería unificada de Exchange anterior a Microsoft Exchange Server 2010 Service Pack 1 (SP1), los nombres de coordenadas de los planes de marcado de URI del SIP de mensajería unificada de Exchange y los planes de marcado de voz de empresa.

<div>

## <a name="deploying-redundant-exchange-um-servers"></a>Implementación de servidores redundantes de mensajería unificada de Exchange

<div>


> [!IMPORTANT]  
> Se recomienda implementar un mínimo de dos servidores en los que se ejecuten los servicios de mensajería unificada de Exchange para cada plan de marcado de URI del SIP de Exchange que configure para su organización. Además de ofrecer más capacidad, implementar servidores redundantes también proporciona una alta disponibilidad. En el caso de que se produzca un error de servidor, Lync Server 2013 se puede configurar para que realice la conmutación por error a otro servidor.



</div>

Los siguientes ejemplos de configuraciones ofrecen resistencia a la mensajería unificada de Exchange.

**Ejemplo 1: Resistencia de la mensajería unificada de Exchange**

![Ejemplo 1 de Mensajería unificada de Exchange](images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "Ejemplo 1 de Mensajería unificada de Exchange")

En el Ejemplo 1, los servidores de mensajería unificada de Exchange 1 y 2 están habilitados en el centro de datos de Tukwila, y los servidores de mensajería unificada de Exchange 3 y 4 están habilitados en el centro de datos de Dublín. En el caso de que se produzca una interrupción de la mensajería unificada de Exchange en Tukwila, los registros de sistemas de nombre de dominio (DNS) A de los servidores 1 y 2 deben estar configurados para apuntar, respectivamente, a los servidores 3 y 4. En el caso de que se produzca una interrupción de la mensajería unificada de Exchange en Dublín, los registros DNS A de los servidores 3 y 4 deben estar configurados para apuntar, respectivamente, a los servidores 1 y 2.

<div>


> [!NOTE]  
> En el Ejemplo 1, debe asignar también uno de los siguientes certificados a cada servidor de mensajería unificada de Exchange: 
> <UL>
> <LI>
> <P>Use un certificado con un carácter comodín en el Nombre alternativo de sujeto (SAN).</P>
> <LI>
> <P>Ponga el nombre de dominio completo (FQDN) de cada uno de los cuatro servidores de mensajería unificada de Exchange en el SAN.</P></LI></UL>



</div>

**Ejemplo 2: Resistencia de la mensajería unificada de Exchange**

![Ejemplo 2 de Mensajería unificada de Exchange](images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "Ejemplo 2 de Mensajería unificada de Exchange")

En el Ejemplo 2, en condiciones normales de funcionamiento, los servidores de mensajería unificada de Exchange 1 y 2 están habilitados en el centro de datos de Tukwila, y los servidores de mensajería unificada de Exchange 3 y 4 están habilitados en el centro de datos de Dublín. Los cuatro servidores están incluidos en el plan de marcado URI del SIP de los usuarios de Tukwila; sin embargo, los servidores 3 y 4 están deshabilitados. En el caso de que se produzca una interrupción de la mensajería unificada de Exchange en Tukwila, por ejemplo, los servidores 1 y 2 de mensajería unificada de Exchange deben deshabilitarse y los servidores 3 y 4 de mensajería unificada de Exchange deben habilitarse para que el tráfico de mensajería unificada de Exchange de Tukwila se enrute a los servidores de Dublín.

Para obtener más información sobre cómo habilitar o deshabilitar la mensajería unificada en Exchange 2013, consulte "integrar la mensajería unificada [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372)de Exchange 2013 con Lync Server" en.

Para obtener más información sobre cómo habilitar o deshabilitar la mensajería unificada en Microsoft Exchange Server 2010, consulte:

  - "Habilitar mensajería unificada en Exchange 2010" [http://go.microsoft.com/fwlink/p/?LinkId=204418](http://go.microsoft.com/fwlink/p/?linkid=204418)en.

  - "Deshabilitar mensajería unificada en Exchange 2010 [http://go.microsoft.com/fwlink/p/?LinkId=204416](http://go.microsoft.com/fwlink/p/?linkid=204416)" en.

</div>

<div>

## <a name="see-also"></a>Vea también


[Proceso de implementación de la integración de la mensajería unificada local y Lync Server 2013](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

