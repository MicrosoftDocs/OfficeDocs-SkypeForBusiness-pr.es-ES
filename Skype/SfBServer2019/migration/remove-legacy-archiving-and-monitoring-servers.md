---
title: Quitar los servidores de archivado y supervisión heredados
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Si la implementación heredada contenía un servidor de archivado o un servidor de supervisión, después de migrar a Skype empresarial Server 2019, estos servidores pueden quitarse del entorno heredado siempre que todos los usuarios se hayan quitado de los grupos de servidores heredados restantes. Puede quitar el servidor de archivado o de supervisión en cualquier secuencia. El requisito clave es quitar a todos los usuarios de todos los grupos de servidores heredados restantes.
ms.openlocfilehash: f5f4da7f7ebf5772bc930d1f92ea3feb590465fd
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752172"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="5213a-105">Quitar los servidores de archivado y supervisión heredados</span><span class="sxs-lookup"><span data-stu-id="5213a-105">Remove legacy Archiving and Monitoring servers</span></span>

<span data-ttu-id="5213a-106">Si la implementación heredada contenía un servidor de archivado o un servidor de supervisión, después de migrar a Skype empresarial Server 2019, estos servidores pueden quitarse del entorno heredado, siempre que todos los usuarios se hayan quitado de los grupos de servidores heredados restantes.</span><span class="sxs-lookup"><span data-stu-id="5213a-106">If your legacy deployment contained an Archiving Server or a Monitoring Server, after migrating to Skype for Business Server 2019, those servers can be removed from the legacy environment, provided all users have been removed from any remaining legacy pools.</span></span> <span data-ttu-id="5213a-107">Puede quitar el servidor de archivado o de supervisión en cualquier secuencia.</span><span class="sxs-lookup"><span data-stu-id="5213a-107">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="5213a-108">El requisito clave es quitar a todos los usuarios de todos los grupos de servidores heredados restantes.</span><span class="sxs-lookup"><span data-stu-id="5213a-108">The key requirement is that all users have been removed from any remaining legacy pools.</span></span>
  
<span data-ttu-id="5213a-109">Puede mover usuarios a Skype empresarial Server 2019 siguiendo los procedimientos descritos en [Phase 4: Move test users to the Pilot Pool](phase-4-move-test-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="5213a-109">You can move users to Skype for Business Server 2019 by following the procedures outlined in [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
<span data-ttu-id="5213a-110">Una vez que haya confirmado que todos los usuarios se han quitado de los grupos de servidores restantes, decommision y quite los roles.</span><span class="sxs-lookup"><span data-stu-id="5213a-110">After you have confirmed that all users have been removed from any remaining pools, decommision the server and remove roles.</span></span> <span data-ttu-id="5213a-111">Un ejemplo de fecha, pero relevante, es "desinstalar Microsoft Lync Server y quitar roles de servidor", que se puede descargar en [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227) .</span><span class="sxs-lookup"><span data-stu-id="5213a-111">A dated, but relevant, example is "Uninstalling Microsoft Lync Server and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span>
  

