---
title: 'Lync Server 2013: Compatibilidad de mensajería unificada (UM) de Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Exchange Unified Messaging (UM) support
ms:assetid: 0da62b8d-7416-4fb8-a405-381ca805c53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398179(v=OCS.15)
ms:contentKeyID: 48183405
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8c952ed8aa407e2a4cbc836372c9238d4888572
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835190"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exchange-unified-messaging-um-support-in-lync-server-2013"></a>Compatibilidad de mensajería unificada (UM) de Exchange en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

Lync Server 2013 admite la integración con mensajería unificada de Exchange (UM) para combinar la mensajería de voz y la mensajería de correo electrónico en una sola infraestructura de mensajería. En Exchange 2013, la mensajería unificada de Exchange consta del servicio MU de Exchange, que se instala y se ejecuta en el servidor de buzón de correo, y el enrutador de llamadas de mensajería unificada, que se instala y se ejecuta en el servidor de acceso de cliente. Para implementaciones de Lync Server 2013 Enterprise Voice, la mensajería UNIFICAda de Exchange combina la mensajería de voz y la mensajería de correo electrónico en un solo almacén accesible desde un teléfono (es decir, Outlook Voice Access) o un equipo. La mensajería unificada de Exchange y Lync Server 2013 funcionan de forma conjunta para proporcionar respuesta de llamada, Outlook Voice Access y los servicios de operador automático a los usuarios de telefonía IP empresarial.

Además de la compatibilidad para la integración con implementaciones locales de la mensajería unificada de Exchange, Lync Server 2013 admite la integración con mensajería unificada de Exchange hospedado. Esto le permite proporcionar mensajería de voz a los usuarios si migra algunos o todos a un proveedor de servicios de Exchange hospedado como Microsoft Exchange Online.

Lync Server 2013 admite las versiones siguientes:

  - Microsoft Exchange 2013

  - Microsoft Exchange Server 2010 (obligatorio) o con el Service Pack más reciente (recomendado)

  - Microsoft Exchange Server 2007 con Service Pack 1 (SP1) (obligatorio) o el Service Pack más reciente (recomendado)

No puede Collocate mensajería unificada de Exchange con Lync Server 2013 o una base de datos de Lync Server 2013. Puede instalar la mensajería unificada de Exchange y Lync Server 2013 en bosques diferentes.

<div>


> [!NOTE]  
> Es posible que no se necesite la mensajería unificada de Exchange para implementaciones de telefonía IP con una PBX implementada, porque la PBX puede seguir proporcionando correo de voz y servicios relacionados a todos los usuarios. Si finalmente retira el sistema PBX (por ejemplo, si implementa la configuración de troncal de SIP para conectividad de red telefónica conmutada (RTC)), debe volver a configurar la mensajería unificada de Exchange para proporcionar el correo de voz a los usuarios que antes usaban el sistema de correo de voz PBX.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Componentes y topologías para mensajería unificada local en Lync Server 2013](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [Compatibilidad con la integración de mensajería unificada de Exchange hospedada en Lync Server 2013](lync-server-2013-support-for-hosted-exchange-um-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

