---
title: 'Lync Server 2013: Compatibilidad con el almacenamiento de archivos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: File storage support
ms:assetid: ed66430d-3c19-4267-938c-956a51005073
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399073(v=OCS.15)
ms:contentKeyID: 48185743
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3025534aecb45f230e986016e839af07fe1406cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835152"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="file-storage-support-in-lync-server-2013"></a>Compatibilidad con el almacenamiento de archivos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-16_

Lync Server 2013 usa el mismo almacén de archivos para todo el almacenamiento de archivos. La compatibilidad con el almacenamiento de archivos incluye lo siguiente:

  - Un recurso compartido de archivos en almacenamiento de conexión directa (DAS) o en una red de área de almacenamiento (SAN), incluido el sistema de archivos distribuido (DFS), y en una matriz redundante de discos independientes (RAID) para los almacenes de archivos. Para obtener más información sobre los requisitos de almacenamiento, consulte [requisitos técnicos para servidores front-end, mensajería instantánea y presencia en Lync server 2013](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) y [requisitos de hardware y software para el director de Lync Server 2013](lync-server-2013-hardware-and-software-requirements-for-the-director.md) en la planificación documentación. Para obtener más información sobre DFS para el sistema operativo Windows Server 2008, consulte la guía paso a paso de DFS para Windows Server [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835)2008 en.

  - Un clúster compartido para el recurso compartido de archivos. Si usa un clúster compartido, debe usar servidores de clústeres que ejecuten Windows Server 2008 o Windows Server 2008 R2. El uso de servidores de clústeres con una versión anterior de Windows puede provocar problemas de permisos que impidan que algunas características estén disponibles. Use el administrador de clústeres para crear los archivos compartidos. Para obtener detalles sobre el uso del administrador de clústeres, consulte el artículo 284838 de Microsoft Knowledge base, "cómo crear un recurso compartido de archivos de [http://go.microsoft.com/fwlink/p/?linkId=140899](http://go.microsoft.com/fwlink/p/?linkid=140899)clústeres de servidores con cluster. exe" en.

</div>

<span> </span>

</div>

</div>

</div>

