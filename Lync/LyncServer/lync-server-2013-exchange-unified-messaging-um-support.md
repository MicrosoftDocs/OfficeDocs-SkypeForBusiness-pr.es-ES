---
title: 'Lync Server 2013: compatibilidad con mensajería unificada (MU) de Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exchange Unified Messaging (UM) support
ms:assetid: 0da62b8d-7416-4fb8-a405-381ca805c53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398179(v=OCS.15)
ms:contentKeyID: 48183405
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22c65581d76d1622da6b64e0ccaa4e028e276d5c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202396"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="exchange-unified-messaging-um-support-in-lync-server-2013"></a>Compatibilidad con mensajería unificada (MU) de Exchange en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

Lync Server 2013 admite la integración con la mensajería unificada (UM) de Exchange para combinar la mensajería de voz y la mensajería de correo electrónico en una única infraestructura de mensajería. En Exchange 2013, la mensajería unificada de Exchange consta del servicio MU de Exchange, que se instala y se ejecuta en el servidor de buzones de correo, y el enrutador de llamadas de mensajería unificada, que se instala y se ejecuta en el servidor de acceso de cliente. Para las implementaciones de Lync Server 2013 Enterprise Voice, la mensajería UNIFICAda de Exchange combina la mensajería de voz y la mensajería de correo electrónico en un solo almacén al que se puede tener acceso desde un teléfono (es decir, Outlook Voice Access) o un equipo. La mensajería unificada de Exchange y Lync Server 2013 funcionan de forma conjunta para proporcionar servicios de contestador automático, Outlook Voice Access y operador automático a los usuarios de telefonía IP empresarial.

Además de la compatibilidad para la integración con implementaciones locales de mensajería unificada de Exchange, Lync Server 2013 admite la integración con la mensajería unificada de Exchange hospedada. Esto le permite proporcionar mensajería de voz a sus usuarios si los migra, en su totalidad o en parte, a un proveedor de servicios de Exchange hospedado como Microsoft Exchange Online

Lync Server 2013 admite las siguientes versiones:

  - Microsoft Exchange 2013

  - Microsoft Exchange Server 2010 (obligatorio) o con el último Service Pack (recomendado)

  - Microsoft Exchange Server 2007 con Service Pack 1 (SP1) (obligatorio) o el último Service Pack (recomendado)

No puede combinar mensajería unificada de Exchange con Lync Server 2013 o una base de datos de Lync Server 2013. Puede instalar la mensajería unificada de Exchange y Lync Server 2013 en bosques independientes.

<div>


> [!NOTE]  
> Es posible que no se requiera la mensajería unificada de Exchange para implementaciones de Enterprise Voice que tengan implementado un sistema PBX, ya que el sistema PBX puede continuar proporcionando correo de voz y servicios relacionados a todos los usuarios. Si finalmente retira la PBX (por ejemplo, si implementa un enlace troncal SIP para la conectividad de red telefónica conmutada (RTC)), debe volver a configurar la mensajería unificada de Exchange para proporcionar correo de voz a los usuarios que usaron previamente el sistema de correo de voz PBX.



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

