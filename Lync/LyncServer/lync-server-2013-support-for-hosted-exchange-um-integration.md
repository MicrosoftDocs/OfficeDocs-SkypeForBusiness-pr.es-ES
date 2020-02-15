---
title: Lync Server 2013 compatibilidad con la integración de mensajería unificada de Exchange hospedada
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Support for hosted Exchange UM integration
ms:assetid: c7573ec3-013c-48d9-b59b-2a5427e6da35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398821(v=OCS.15)
ms:contentKeyID: 48185376
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e0625d983f05e5b9b22bf5086d0689c117b2ecda
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038652"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="support-for-hosted-exchange-um-integration-in-lync-server-2013"></a>Compatibilidad con la integración de mensajería unificada de Exchange hospedada en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

La aplicación Lync Server 2013 ExUM de enrutamiento admite la integración con la mensajería unificada (MU) de Exchange en un entorno local, donde Lync Server 2013 y mensajería unificada de Exchange están instaladas localmente en su empresa o en con la mensajería unificada de Exchange hospedada por un proveedor de servicios, como se muestra en el siguiente diagrama.

![Implementación local de mensajería unificada de Lync Server Exchange](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "Implementación local de mensajería unificada de Lync Server Exchange")

Se admiten los siguientes modos:

  - **Modo local Lync**   Server 2013 y mensajería unificada de Exchange se implementan en los servidores locales de la empresa.

  - **Modo entre locales**   Lync Server 2013 se implementa en servidores locales de la empresa y la mensajería unificada de Exchange se hospeda en una instalación de un proveedor de servicios en línea, como un centro de datos de Microsoft Exchange Online.

  - **Modo mixto su**   implementación de Lync Server 2013 tiene algunos buzones de usuario alojados en servidores locales que ejecutan Microsoft Exchange Server dentro de su empresa y otros buzones en un centro de datos de servicio de Exchange hospedado.
    
    <div>
    

    > [!NOTE]  
    > El modo mixto se puede usar como solución transitoria durante la evaluación y la migración de paso a paso de usuarios a la mensajería unificada de Exchange hospedada o como una solución permanente si opta por mantener algunos servicios de mensajería unificada de Exchange de los usuarios de forma local después de migrar otros.

    
    </div>

Para integrar Lync Server 2013 con mensajería unificada de Exchange hospedada, debe configurar un *espacio de direcciones SIP compartido* (también denominado *dominio dividido*). En esta configuración, tanto Lync Server 2013 como el proveedor de servicios de mensajería unificada de Exchange hospedado por terceros pueden acceder al mismo espacio de direcciones de dominio SIP. Para obtener más información, consulte [arquitectura de integración de mensajería unificada de Exchange hospedada en Lync Server 2013](lync-server-2013-hosted-exchange-um-integration-architecture.md) en la documentación referente a la planeación.

</div>

<span> </span>

</div>

</div>

</div>

