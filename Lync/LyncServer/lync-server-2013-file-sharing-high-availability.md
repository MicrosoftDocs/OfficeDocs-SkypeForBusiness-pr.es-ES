---
title: 'Lync Server 2013: alta disponibilidad del uso compartido de archivos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: File sharing high availability
ms:assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205203(v=OCS.15)
ms:contentKeyID: 48185238
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f67fc8cfffc0b5dbecaf6da212b3a8e5414b18ef
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735240"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="file-sharing-high-availability-in-lync-server-2013"></a><span data-ttu-id="6ae17-102">Alta disponibilidad del uso compartido de archivos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ae17-102">File sharing high availability in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ae17-103">_**Última modificación del tema:** 2012-03-30_</span><span class="sxs-lookup"><span data-stu-id="6ae17-103">_**Topic Last Modified:** 2012-03-30_</span></span>

<span data-ttu-id="6ae17-104">Para garantizar la alta disponibilidad del uso compartido de archivos de Lync Server en un solo centro de datos, puede usar el sistema de archivos distribuido (DFS).</span><span class="sxs-lookup"><span data-stu-id="6ae17-104">To ensure high availability for Lync Server file sharing within a single data center, you can use the Distributed File System (DFS).</span></span> <span data-ttu-id="6ae17-105">DFS admite la conmutación por error de un servidor de archivos a otro dentro del mismo centro de datos.</span><span class="sxs-lookup"><span data-stu-id="6ae17-105">DFS supports failover from one file server to another within the same data center.</span></span> <span data-ttu-id="6ae17-106">Para una implementación de gran escala, te recomendamos usar servidores de archivos dedicados que se emparejan con DFS.</span><span class="sxs-lookup"><span data-stu-id="6ae17-106">For a large scale deployment, we recommend that you use dedicated file servers that are paired using DFS.</span></span>

<span data-ttu-id="6ae17-107">Según el tamaño de la red y la cantidad de resistencia que desee, puede usar un par de servidores para hospedar todos los recursos compartidos de archivos en un sitio o usar un par por grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="6ae17-107">Depending on your network's size, and the amount of resiliency you want, you can use one pair of servers to host all file shares in a site, or use one pair per Front End pool.</span></span>

<span data-ttu-id="6ae17-108">DFS es un mecanismo de replicación de archivos de mejor esfuerzo, sin ningún compromiso de objetivo de tiempo de recuperación (RTO) ni de objetivo de punto de recuperación (RPO) publicado.</span><span class="sxs-lookup"><span data-stu-id="6ae17-108">DFS is a best effort file replication mechanism, with no published recovery time objective (RTO) or recovery point objective (RPO) commitment.</span></span> <span data-ttu-id="6ae17-109">La conmutación por error entre los servidores DFS debe completarse rápidamente, pero el retraso de replicación de datos puede evitar que los usuarios puedan continuar trabajando en curso cuando se produzca la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="6ae17-109">The failover between the DFS servers should be completed quickly, but data replication delay may prevent users from being able to continue work in progress when the failover happens.</span></span>

<span data-ttu-id="6ae17-110">Si utiliza DFS y el almacén de datos en el recurso compartido es esencial, debe realizar una copia de seguridad de los recursos compartidos de archivos con frecuencia, como cada 4 a 8 horas.</span><span class="sxs-lookup"><span data-stu-id="6ae17-110">If you use DFS and data store on the fileshare is critical, you should back up the file shares frequently, such as every 4 to 8 hours.</span></span> <span data-ttu-id="6ae17-111">Si un recurso compartido de archivos deja de estar operativo y la replicación no está actualizada, puede usar la copia de seguridad para restaurar el contenido del servidor que ha fallado en el otro servidor que está emparejado con el servidor que ahora no está disponible.</span><span class="sxs-lookup"><span data-stu-id="6ae17-111">When one file share goes down and replication is not up to date, you can use the backup to restore the content on the failed server to the other server that is paired with the server that is now unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

