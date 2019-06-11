---
title: 'Lync Server 2013: Configuración de la mensajería unificada en Microsoft Exchange Server para trabajar con Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Unified Messaging on Microsoft Exchange Server to work with Lync Server 2013
ms:assetid: 058da9c4-23af-4ddb-9f63-70133a8aafc6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398106(v=OCS.15)
ms:contentKeyID: 48183289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 461d822862e837879f1feb2d3f980b816aae5280
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-unified-messaging-on-microsoft-exchange-server-to-work-with-lync-server-2013"></a>Configuración de la mensajería unificada en Microsoft Exchange Server para trabajar con Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-11_

<div>


> [!IMPORTANT]  
> Si desea usar la mensajería unificada de Exchange (UM) para proporcionar contestador automático, Outlook Voice Access o los servicios de operador automático para usuarios de Enterprise Voice, consulte <A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">planificación de la integración de mensajería unificada de Exchange en Lync Server 2013</A> en la planificación documentación y, a continuación, siga las instrucciones de esta sección.



</div>

Para configurar la mensajería unificada de Exchange para que funcione con la telefonía IP empresarial, tendrá que realizar las siguientes tareas:

  - Configurar certificados en el servidor que ejecuta los servicios de mensajería unificada (UM) de Exchange
    
    <div>
    

    > [!NOTE]  
    > Agregar todos los servidores de acceso de cliente y de buzón a todos los planes de marcado URI SIP de mensajería unificada. Si no es así, el enrutamiento de llamadas salientes no funciona según lo esperado.

    
    </div>

  - Cree uno o varios planes de marcado URI SIP de MU, junto con los números de teléfono de acceso del suscriptor, según sea necesario y, a continuación, cree los planes de marcado de Lync Server correspondientes.

  - Use el script **ExchUCUtil. PS1** para:
    
      - Crear puertas de enlace IP de MU.
    
      - Crear grupos de extensiones de mensajería unificada.
    
      - Otorgue a Lync Server 2013 permiso para leer objetos de servicios de dominio de Active Directory de MU.

  - Crear un objeto de operador automático de mensajería unificada.

  - Crear un objeto de acceso de suscriptor.

  - Crear un URI de SIP para cada usuario y asociar a los usuarios con un plan de marcado URI SIP de mensajería unificada.

<div>

## <a name="requirements-and-recommendations"></a>Requisitos y recomendaciones

Antes de empezar, en la documentación de esta sección se supone que ha implementado los siguientes roles de Exchange 2013: acceso de cliente y buzón de correo. En Microsoft Exchange Server 2013, la mensajería unificada de Exchange se ejecuta como un servicio en estos servidores.

Para obtener más información sobre la implementación de Exchange 2013, consulte la biblioteca de TechNet de Exchange 2013 en[http://go.microsoft.com/fwlink/p/?LinkId=266637](http://go.microsoft.com/fwlink/p/?linkid=266637)

Además, tenga en cuenta lo siguiente:

  - Si la mensajería unificada de Exchange se instala en varios bosques, los pasos de integración del servidor de Exchange deben realizarse para cada bosque de MU. Además, cada bosque de MU debe estar configurado para confiar en el bosque en el que se implementa Lync Server 2013, y el bosque en el que se implementa Lync Server 2013 debe estar configurado para confiar en cada bosque de MU.

  - Los pasos de integración se realizan en las funciones de Exchange Server donde se ejecutan los servicios de mensajería unificada y en el servidor que ejecuta Lync Server 2013. Debe realizar los pasos de integración de mensajería unificada de Exchange Server antes de realizar los pasos de integración de Lync Server 2013.
    
    <div>
    

    > [!NOTE]  
    > Para ver qué pasos de integración se realizan en qué servidores y con qué roles de administrador, vea <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">proceso de implementación para integrar mensajería unificada local y Lync Server 2013</A>.

    
    </div>

Las siguientes herramientas deben estar disponibles en cada servidor que ejecute la mensajería unificada de Exchange:

  - Shell de administración de Exchange

  - El script **ExchUCUtil. PS1**, que realiza las siguientes tareas:
    
      - Crea una puerta de enlace IP de MU para cada servidor de Lync 2013.
    
      - Crea un grupo de captura para cada puerta de enlace. El identificador piloto de cada grupo de captura especifica el plan de marcado URI SIP de MU usado por el grupo de servidores front-end o el servidor Standard Edition asociado a la puerta de enlace.
    
      - Concede el permiso 2013 de Lync Server para leer objetos de mensajería unificada de Exchange en servicios de dominio de Active Directory.

</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Configurar certificados en el servidor que ejecuta la mensajería unificada de Microsoft Exchange Server](lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md)

  - [Configurar la mensajería unificada en Microsoft Exchange para Lync Server 2013](lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

