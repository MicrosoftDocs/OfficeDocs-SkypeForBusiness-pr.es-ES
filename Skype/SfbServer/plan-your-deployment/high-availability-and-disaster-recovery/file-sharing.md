---
title: Alta disponibilidad de uso compartido de archivos en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
description: Obtenga información sobre cómo garantizar la alta disponibilidad de los recursos compartidos de archivos en Skype Empresarial Server mediante DFS.
ms.openlocfilehash: f47d8207969063472af23d898ef8a52c2383df0d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093098"
---
# <a name="file-sharing-high-availability-in-skype-for-business-server"></a><span data-ttu-id="cdb7f-103">Alta disponibilidad de uso compartido de archivos en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="cdb7f-103">File sharing high availability in Skype for Business Server</span></span>
 
<span data-ttu-id="cdb7f-104">Obtenga información sobre cómo garantizar la alta disponibilidad de los recursos compartidos de archivos en Skype Empresarial Server mediante DFS.</span><span class="sxs-lookup"><span data-stu-id="cdb7f-104">Learn about ensuring high availability of your file shares in Skype for Business Server, using DFS.</span></span>
  
<span data-ttu-id="cdb7f-105">Para garantizar la alta disponibilidad para el uso compartido de archivos en la implementación de Skype Empresarial Server, puede usar el Sistema de archivos distribuido (DFS).</span><span class="sxs-lookup"><span data-stu-id="cdb7f-105">To ensure high availability for file sharing in your Skype for Business Server deployment, you can use the Distributed File System (DFS).</span></span> <span data-ttu-id="cdb7f-106">DFS admite la conmutación por error de un servidor de archivos a otro del mismo centro de datos.</span><span class="sxs-lookup"><span data-stu-id="cdb7f-106">DFS supports failover from one file server to another within the same data center.</span></span> <span data-ttu-id="cdb7f-107">Para una implementación a gran escala, recomendamos que use servidores de archivos dedicados que se emparejen mediante DFS.</span><span class="sxs-lookup"><span data-stu-id="cdb7f-107">For a large scale deployment, we recommend that you use dedicated file servers that are paired using DFS.</span></span> <span data-ttu-id="cdb7f-108">Para obtener más información sobre DFS en Windows Server 2012, consulta [https://go.microsoft.com/fwlink/?LinkId=524384](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj127250(v=ws.11)) .</span><span class="sxs-lookup"><span data-stu-id="cdb7f-108">For more information on DFS in Windows Server 2012, see [https://go.microsoft.com/fwlink/?LinkId=524384](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj127250(v=ws.11)).</span></span> <span data-ttu-id="cdb7f-109">Para obtener información sobre DFS en Windows Server 2008, consulta [https://go.microsoft.com/fwlink/p/?LinkId=524385](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753479(v=ws.10)) .</span><span class="sxs-lookup"><span data-stu-id="cdb7f-109">For information on DFS on Windows Server 2008, see [https://go.microsoft.com/fwlink/p/?LinkId=524385](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753479(v=ws.10)).</span></span>
  
<span data-ttu-id="cdb7f-110">En función del tamaño de la red y de la cantidad de resistencia que desee, puede usar un par de servidores para hospedar todos los recursos compartidos de archivos de un sitio o usar un par por grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="cdb7f-110">Depending on your network's size, and the amount of resiliency you want, you can use one pair of servers to host all file shares in a site, or use one pair per Front End pool.</span></span>
  
<span data-ttu-id="cdb7f-111">DFS es un mecanismo de replicación de archivos de tipo “mejor esfuerzo” (best effort), sin ningún compromiso de objetivo de tiempo de recuperación (RTO) ni de objetivo de punto de recuperación (RPO) publicado.</span><span class="sxs-lookup"><span data-stu-id="cdb7f-111">DFS is a best effort file replication mechanism, with no published recovery time objective (RTO) or recovery point objective (RPO) commitment.</span></span> <span data-ttu-id="cdb7f-112">Una conmutación por error entre servidores DFS debe completarse rápidamente, pero el retraso de replicación de datos puede impedir que los usuarios puedan continuar trabajando en curso cuando se produzca la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="cdb7f-112">A failover between DFS servers should be completed quickly, but data replication delay may prevent users from being able to continue work in progress when the failover happens.</span></span>
  
<span data-ttu-id="cdb7f-113">Si usa DFS y el almacén de datos en el archivo compartido es fundamental, debe hacer una copia de seguridad de los recursos compartidos de archivos con frecuencia, como cada 4 a 8 horas.</span><span class="sxs-lookup"><span data-stu-id="cdb7f-113">If you use DFS and the data store on the fileshare is critical, you should back up the file shares frequently, such as every 4 to 8 hours.</span></span> <span data-ttu-id="cdb7f-114">Si un recurso compartido de archivos deja de estar operativo y la replicación no está actualizada, puede usar la copia de seguridad para restaurar el contenido del servidor que ha fallado en el otro servidor que está emparejado con el servidor que ahora no está disponible.</span><span class="sxs-lookup"><span data-stu-id="cdb7f-114">When one file share goes down and replication is not up to date, you can use the backup to restore the content on the failed server to the other server that is paired with the server that is now unavailable.</span></span>
