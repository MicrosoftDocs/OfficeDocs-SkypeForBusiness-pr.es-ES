---
title: 'Lync Server 2013: configuración de una ubicación de copia de seguridad'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up a backup location
ms:assetid: 006732eb-3d44-414d-8010-227a855caa93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202158(v=OCS.15)
ms:contentKeyID: 51541440
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a5c723f25abe6a5e12833b37b070c543b5db4ac
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182143"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-a-backup-location-for-lync-server-2013"></a><span data-ttu-id="43a04-102">Configuración de una ubicación de copia de seguridad para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43a04-102">Setting up a backup location for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43a04-103">_**Última modificación del tema:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="43a04-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="43a04-104">Antes de llevar a cabo la primera copia de seguridad de Lync Server, configure el hardware y el software que necesita para poder almacenar y mantener las copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="43a04-104">Before you take your first backup of Lync Server, set up the hardware and software that you need in order to store and maintain the backups.</span></span> <span data-ttu-id="43a04-105">Debe obtener acceso a los medios y el contenido, según corresponda, y proporcionar conectividad de red entre cada servidor que se incluirá en las copias de seguridad y los medios de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="43a04-105">You need to obtain access to the media and content, as appropriate, and provide network connectivity between each server to be backed up and the backup media.</span></span> <span data-ttu-id="43a04-106">Los medios y la ubicación que use deben definirse en su estrategia de copia de seguridad y restauración.</span><span class="sxs-lookup"><span data-stu-id="43a04-106">The media and location that you use should be defined in your backup and restoration strategy.</span></span> <span data-ttu-id="43a04-107">La ubicación que se usa para las copias de seguridad periódicas puede ser local o remota, pero debe ser segura y debe estar accesible para la copia de seguridad y la restauración.</span><span class="sxs-lookup"><span data-stu-id="43a04-107">The location that you use for regular backups can be local or remote, but it must be secure, and it must be accessible for both backup and restoration.</span></span> <span data-ttu-id="43a04-108">Se recomienda usar una ubicación remota para protegerse contra un evento catastrófico en el sitio primario.</span><span class="sxs-lookup"><span data-stu-id="43a04-108">We recommend using a remote location to protect against a catastrophic event at your primary site.</span></span>

<span data-ttu-id="43a04-109">Tras configurar y probar los componentes individuales, compruebe la accesibilidad a las copias de seguridad desde cada servidor.</span><span class="sxs-lookup"><span data-stu-id="43a04-109">After you set up and test the individual components, verify accessibility to the backups from each server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

