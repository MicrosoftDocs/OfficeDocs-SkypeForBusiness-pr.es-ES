---
title: Lync Server 2013 soporte de almacenamiento de archivos
description: Lync Server 2013 soporte de almacenamiento de archivos.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: File storage support
ms:assetid: ed66430d-3c19-4267-938c-956a51005073
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399073(v=OCS.15)
ms:contentKeyID: 48185743
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03b7c3379c6aad6283f6a55b991ebaec50044bda
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543376"
---
# <a name="file-storage-support-in-lync-server-2013"></a>Compatibilidad con el almacenamiento de archivos en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-16_

Lync Server 2013 usa el mismo almacén de archivos para todo el almacenamiento de archivos. La compatibilidad con el almacenamiento de archivos incluye lo siguiente:

  - Un recurso compartido de archivos en el almacenamiento de conexión directa (DAS) o en una red de área de almacenamiento (SAN), incluido el sistema de archivos distribuido (DFS), y en una matriz redundante de discos independientes (RAID) para los almacenes de archivos. Para obtener más información sobre los requisitos de almacenamiento, consulte [Technical Requirements for front end servers, Instant Messaging and Presence in Lync server 2013](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) , and [Hardware and software Requirements for the Director in Lync Server 2013](lync-server-2013-hardware-and-software-requirements-for-the-director.md) en la documentación referente a la planeación. Para obtener más información sobre DFS para el sistema operativo Windows Server 2008, vea la guía paso a paso de DFS para Windows Server 2008 en [https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835) .

  - Un clúster compartido para el recurso compartido de archivos. Si usa un clúster compartido, debe usar servidores de clústeres que ejecuten Windows Server 2008 o Windows Server 2008 R2. El uso de servidores de clústeres con una versión anterior de Windows puede provocar problemas de permisos que impiden que algunas características estén disponibles. Use el Administrador de clústeres para crear los recursos compartidos de archivos. Para obtener información detallada sobre cómo usar el administrador de clústeres, consulte el artículo 284838 de Microsoft Knowledge base, "cómo crear un recurso compartido de archivos de clústeres de servidores con Cluster.exe" en [https://go.microsoft.com/fwlink/p/?linkId=140899](https://go.microsoft.com/fwlink/p/?linkid=140899) .

</div>

<span> </span>

</div>

</div>

</div>

