---
title: 'Lync Server 2013: Compatibilidad con la integración de mensajería unificada de Exchange hospedada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Support for hosted Exchange UM integration
ms:assetid: c7573ec3-013c-48d9-b59b-2a5427e6da35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398821(v=OCS.15)
ms:contentKeyID: 48185376
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56ba107c9a782acb15ccd8d57f82cf567f2b75e1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850558"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="support-for-hosted-exchange-um-integration-in-lync-server-2013"></a>Compatibilidad con la integración de mensajería unificada de Exchange hospedada en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

La aplicación de enrutamiento ExUM de Lync Server 2013 admite la integración con mensajería unificada de Exchange (UM) en un entorno local, donde Lync Server 2013 y MU están instalados de forma local en su empresa, o en con la mu de Exchange hospedada por un proveedor de servicios, como se muestra en el siguiente diagrama.

![Implementación de mensajería unificada de Exchange de Lync Server local] (images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "Implementación de mensajería unificada de Exchange de Lync Server local")

Se admiten los siguientes modos:

  - **El modo**   local de Lync Server 2013 y la mensajería unificada de Exchange se implementan en servidores locales de su empresa.

  - **Modo entre locales**   Lync Server 2013 se implementa en servidores locales de su empresa y la mensajería unificada de Exchange se hospeda en una instalación de un proveedor de servicios en línea, como un centro de datos de Microsoft Exchange Online.

  - **Modo mixto su**   implementación de Lync Server 2013 tiene algunos buzones de usuario alojados en servidores locales que ejecutan Microsoft Exchange Server dentro de su empresa y algunos buzones alojados en un centro de datos de servicio de Exchange hospedado.
    
    <div>
    

    > [!NOTE]  
    > El modo mixto se puede usar como solución transitoria durante la evaluación y stepwise la migración de los usuarios a la mensajería unificada de Exchange hospedada o como una solución permanente si opta por mantener locales los servicios de mensajería unificada de Exchange de los usuarios después de migrar otros usuarios.

    
    </div>

Para integrar Lync Server 2013 con mensajería unificada de Exchange hospedada, debe configurar un *espacio de direcciones SIP compartido* (también denominado *dominio dividido*). En esta configuración, tanto Lync Server 2013 como el proveedor de servicios de mensajería unificada de Exchange hospedado por terceros pueden acceder al mismo espacio de direcciones de dominio SIP. Para obtener más información, consulte [arquitectura de integración de mensajería unificada de Exchange hospedada en Lync Server 2013](lync-server-2013-hosted-exchange-um-integration-architecture.md) en la documentación de planeación.

</div>

<span> </span>

</div>

</div>

</div>

