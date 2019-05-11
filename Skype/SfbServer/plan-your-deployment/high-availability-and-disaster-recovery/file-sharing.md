---
title: Archivo de uso compartido de alta disponibilidad en Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
description: Obtenga información sobre cómo asegurar una alta disponibilidad de los recursos compartidos de archivos en Skype para Business Server, el uso de DFS.
ms.openlocfilehash: 90d67622c1c1fbd9567df69187519be63e812ac8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910217"
---
# <a name="file-sharing-high-availability-in-skype-for-business-server"></a><span data-ttu-id="861d5-103">Archivo de uso compartido de alta disponibilidad en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="861d5-103">File sharing high availability in Skype for Business Server</span></span>
 
<span data-ttu-id="861d5-104">Obtenga información sobre cómo asegurar una alta disponibilidad de los recursos compartidos de archivos en Skype para Business Server, el uso de DFS.</span><span class="sxs-lookup"><span data-stu-id="861d5-104">Learn about ensuring high availability of your file shares in Skype for Business Server, using DFS.</span></span>
  
<span data-ttu-id="861d5-105">Para asegurar una alta disponibilidad para compartir archivos en su Skype para la implementación de Business Server, puede usar el sistema de archivos distribuido (DFS).</span><span class="sxs-lookup"><span data-stu-id="861d5-105">To ensure high availability for file sharing in your Skype for Business Server deployment, you can use the Distributed File System (DFS).</span></span> <span data-ttu-id="861d5-106">DFS admite la conmutación por error de un servidor de archivos a otro dentro del mismo centro de datos.</span><span class="sxs-lookup"><span data-stu-id="861d5-106">DFS supports failover from one file server to another within the same data center.</span></span> <span data-ttu-id="861d5-107">Para una implementación de gran escala, te recomendamos usar servidores de archivos dedicados que se emparejan con DFS.</span><span class="sxs-lookup"><span data-stu-id="861d5-107">For a large scale deployment, we recommend that you use dedicated file servers that are paired using DFS.</span></span> <span data-ttu-id="861d5-108">Para obtener más información acerca de DFS en Windows Server 2012, consulte [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384).</span><span class="sxs-lookup"><span data-stu-id="861d5-108">For more information on DFS in Windows Server 2012, see [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384).</span></span> <span data-ttu-id="861d5-109">Para obtener información acerca de DFS en Windows Server 2008, consulte [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385).</span><span class="sxs-lookup"><span data-stu-id="861d5-109">For information on DFS on Windows Server 2008, see [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385).</span></span>
  
<span data-ttu-id="861d5-110">Dependiendo del tamaño de su red y la cantidad de resistencia que desee, puede usar un par de servidores para hospedar todos los recursos compartidos de archivos en un sitio o usar un par por grupo de servidores Front-End.</span><span class="sxs-lookup"><span data-stu-id="861d5-110">Depending on your network's size, and the amount of resiliency you want, you can use one pair of servers to host all file shares in a site, or use one pair per Front End pool.</span></span>
  
<span data-ttu-id="861d5-111">DFS es un mecanismo de replicación de archivos de mejor esfuerzo, sin ningún compromiso de objetivo de tiempo de recuperación (RTO) ni de objetivo de punto de recuperación (RPO) publicado.</span><span class="sxs-lookup"><span data-stu-id="861d5-111">DFS is a best effort file replication mechanism, with no published recovery time objective (RTO) or recovery point objective (RPO) commitment.</span></span> <span data-ttu-id="861d5-112">Una conmutación por error entre servidores DFS debe realizarse rápidamente, pero el retraso de replicación de datos puede impedir que los usuarios puedan continuar el trabajo en curso cuando se produce la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="861d5-112">A failover between DFS servers should be completed quickly, but data replication delay may prevent users from being able to continue work in progress when the failover happens.</span></span>
  
<span data-ttu-id="861d5-p103">Si usa DFS y el almacén de datos en el recurso compartido de archivos es crítico, necesita realizar una copia de seguridad de los recursos compartidos de archivos con frecuencia, por ejemplo cada 4 u 8 horas. Si un recurso compartido de archivos deja de estar operativo y la replicación no está actualizada, puede usar la copia de seguridad para restaurar el contenido del servidor que ha fallado en el otro servidor que está emparejado con el servidor que ahora no está disponible.</span><span class="sxs-lookup"><span data-stu-id="861d5-p103">If you use DFS and the data store on the fileshare is critical, you should back up the file shares frequently, such as every 4 to 8 hours. When one file share goes down and replication is not up to date, you can use the backup to restore the content on the failed server to the other server that is paired with the server that is now unavailable.</span></span>
  

