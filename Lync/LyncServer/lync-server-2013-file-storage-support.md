---
title: 'Lync Server 2013: Compatibilidad con el almacenamiento de archivos'
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
ms.openlocfilehash: 000f3357c8b30b83a2d2cecf74bdbec44d867d96
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743410"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="file-storage-support-in-lync-server-2013"></a><span data-ttu-id="a8180-102">Compatibilidad con el almacenamiento de archivos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8180-102">File storage support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8180-103">_**Última modificación del tema:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="a8180-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="a8180-104">Lync Server 2013 usa el mismo almacén de archivos para todo el almacenamiento de archivos.</span><span class="sxs-lookup"><span data-stu-id="a8180-104">Lync Server 2013 uses the same file store for all file storage.</span></span> <span data-ttu-id="a8180-105">La compatibilidad con el almacenamiento de archivos incluye lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a8180-105">File storage support includes the following:</span></span>

  - <span data-ttu-id="a8180-106">Un recurso compartido de archivos en almacenamiento de conexión directa (DAS) o en una red de área de almacenamiento (SAN), incluido el sistema de archivos distribuido (DFS), y en una matriz redundante de discos independientes (RAID) para los almacenes de archivos.</span><span class="sxs-lookup"><span data-stu-id="a8180-106">A file share on either direct attached storage (DAS) or a storage area network (SAN), including Distributed File System (DFS), and on a redundant array of independent disks (RAID) for file stores.</span></span> <span data-ttu-id="a8180-107">Para obtener más información sobre los requisitos de almacenamiento, consulte [requisitos técnicos para servidores front-end, mensajería instantánea y presencia en Lync server 2013](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) y [requisitos de hardware y software para el director de Lync Server 2013](lync-server-2013-hardware-and-software-requirements-for-the-director.md) en la documentación de planificación.</span><span class="sxs-lookup"><span data-stu-id="a8180-107">For details about storage requirements, see [Technical requirements for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) and [Hardware and software requirements for the Director in Lync Server 2013](lync-server-2013-hardware-and-software-requirements-for-the-director.md) in the Planning documentation.</span></span> <span data-ttu-id="a8180-108">Para obtener más información sobre DFS para el sistema operativo Windows Server 2008, consulte la guía paso a paso de DFS para Windows Server [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835)2008 en.</span><span class="sxs-lookup"><span data-stu-id="a8180-108">For details about DFS for Windows Server 2008 operating system, see the DFS Step-by-Step Guide for Windows Server 2008 at [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835).</span></span>

  - <span data-ttu-id="a8180-109">Un clúster compartido para el recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="a8180-109">A shared cluster for the file share.</span></span> <span data-ttu-id="a8180-110">Si usa un clúster compartido, debe usar servidores de clústeres que ejecuten Windows Server 2008 o Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="a8180-110">If you use a shared cluster, you should use cluster servers running Windows Server 2008 or Windows Server 2008 R2.</span></span> <span data-ttu-id="a8180-111">El uso de servidores de clústeres con una versión anterior de Windows puede provocar problemas de permisos que impidan que algunas características estén disponibles.</span><span class="sxs-lookup"><span data-stu-id="a8180-111">Using cluster servers running an older version of Windows may result in permission issues that prevent some features from being available.</span></span> <span data-ttu-id="a8180-112">Use el administrador de clústeres para crear los archivos compartidos.</span><span class="sxs-lookup"><span data-stu-id="a8180-112">Use the Cluster Administrator to create the file shares.</span></span> <span data-ttu-id="a8180-113">Para obtener detalles sobre el uso del administrador de clústeres, consulte el artículo 284838 de Microsoft Knowledge base, "cómo crear un recurso compartido de archivos de [http://go.microsoft.com/fwlink/p/?linkId=140899](http://go.microsoft.com/fwlink/p/?linkid=140899)clústeres de servidores con cluster. exe" en.</span><span class="sxs-lookup"><span data-stu-id="a8180-113">For details about using the Cluster Administrator, see Microsoft Knowledge Base article 284838, "How to Create a Server Cluster File Share with Cluster.exe" at [http://go.microsoft.com/fwlink/p/?linkId=140899](http://go.microsoft.com/fwlink/p/?linkid=140899).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

