---
title: Alta disponibilidad del uso compartido de archivos en Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
description: Obtenga información sobre cómo garantizar la alta disponibilidad de los recursos compartidos de archivos en Skype para Business Server, mediante DFS.
ms.openlocfilehash: f96e4aaca70c501425528b12207eeab01027c9a9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="file-sharing-high-availability-in-skype-for-business-server-2015"></a><span data-ttu-id="72a5c-103">Alta disponibilidad del uso compartido de archivos en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="72a5c-103">File sharing high availability in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="72a5c-104">Obtenga información sobre cómo garantizar la alta disponibilidad de los recursos compartidos de archivos en Skype para Business Server, mediante DFS.</span><span class="sxs-lookup"><span data-stu-id="72a5c-104">Learn about ensuring high availability of your file shares in Skype for Business Server, using DFS.</span></span>
  
<span data-ttu-id="72a5c-105">Para garantizar la alta disponibilidad para compartir archivos en tu Skype para la implementación de Business Server, puede utilizar el sistema de archivos distribuido (DFS).</span><span class="sxs-lookup"><span data-stu-id="72a5c-105">To ensure high availability for file sharing in your Skype for Business Server deployment, you can use the Distributed File System (DFS).</span></span> <span data-ttu-id="72a5c-106">DFS admite la conmutación por error de un servidor de archivos a otro dentro del mismo centro de datos.</span><span class="sxs-lookup"><span data-stu-id="72a5c-106">DFS supports failover from one file server to another within the same data center.</span></span> <span data-ttu-id="72a5c-107">Para una implementación de gran escala, te recomendamos usar servidores de archivos dedicados que se emparejan con DFS.</span><span class="sxs-lookup"><span data-stu-id="72a5c-107">For a large scale deployment, we recommend that you use dedicated file servers that are paired using DFS.</span></span> <span data-ttu-id="72a5c-108">Para obtener más información acerca de DFS en Windows Server 2012, consulte [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384).</span><span class="sxs-lookup"><span data-stu-id="72a5c-108">For more information on DFS in Windows Server 2012, see [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384).</span></span> <span data-ttu-id="72a5c-109">Para obtener información acerca de DFS en Windows Server 2008, consulte [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385).</span><span class="sxs-lookup"><span data-stu-id="72a5c-109">For information on DFS on Windows Server 2008, see [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385).</span></span>
  
<span data-ttu-id="72a5c-110">Dependiendo del tamaño de la red y la cantidad de resiliencia que desee, puede utilizar un par de servidores para alojar todos los recursos compartidos de archivos en un sitio o utilice un par por cada grupo de Front-End.</span><span class="sxs-lookup"><span data-stu-id="72a5c-110">Depending on your network's size, and the amount of resiliency you want, you can use one pair of servers to host all file shares in a site, or use one pair per Front End pool.</span></span>
  
<span data-ttu-id="72a5c-111">DFS es un mecanismo de replicación de archivos de mejor esfuerzo, sin ningún compromiso de objetivo de tiempo de recuperación (RTO) ni de objetivo de punto de recuperación (RPO) publicado.</span><span class="sxs-lookup"><span data-stu-id="72a5c-111">DFS is a best effort file replication mechanism, with no published recovery time objective (RTO) or recovery point objective (RPO) commitment.</span></span> <span data-ttu-id="72a5c-112">Una conmutación por error entre servidores DFS debe realizarse rápidamente, pero el retraso de la replicación de datos puede evitar que los usuarios tengan la posibilidad de continuar el trabajo en curso cuando se produce la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="72a5c-112">A failover between DFS servers should be completed quickly, but data replication delay may prevent users from being able to continue work in progress when the failover happens.</span></span>
  
<span data-ttu-id="72a5c-p103">Si usa DFS y el almacén de datos en el recurso compartido de archivos es crítico, necesita realizar una copia de seguridad de los recursos compartidos de archivos con frecuencia, por ejemplo cada 4 u 8 horas. Si un recurso compartido de archivos deja de estar operativo y la replicación no está actualizada, puede usar la copia de seguridad para restaurar el contenido del servidor que ha fallado en el otro servidor que está emparejado con el servidor que ahora no está disponible.</span><span class="sxs-lookup"><span data-stu-id="72a5c-p103">If you use DFS and the data store on the fileshare is critical, you should back up the file shares frequently, such as every 4 to 8 hours. When one file share goes down and replication is not up to date, you can use the backup to restore the content on the failed server to the other server that is paired with the server that is now unavailable.</span></span>
  

