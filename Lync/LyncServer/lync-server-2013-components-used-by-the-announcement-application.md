---
title: 'Lync Server 2013: componentes que usa la aplicación de anuncio'
description: 'Lync Server 2013: componentes que usa la aplicación de anuncio.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by the Announcement application
ms:assetid: 7b1a0281-cf31-459d-a734-5f10a129089c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398608(v=OCS.15)
ms:contentKeyID: 48184595
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e5338ad097c814d5c6435bd89dbf7cfa8680feb8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577696"
---
# <a name="components-used-by-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="5262e-103">Componentes usados por la aplicación de anuncio en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5262e-103">Components used by the Announcement application in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5262e-104">_**Última modificación del tema:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="5262e-104">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="5262e-105">En Lync Server 2013, la aplicación de anuncio es un componente de la aplicación de grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="5262e-105">In Lync Server 2013, the Announcement application is a component of the Response Group application.</span></span> <span data-ttu-id="5262e-106">Al implementar la telefonía IP empresarial, la aplicación del anuncio se instala y se activa automáticamente junto con la aplicación grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="5262e-106">When you deploy Enterprise Voice, the Announcement application is automatically installed and activated along with the Response Group application.</span></span> <span data-ttu-id="5262e-107">En esta sección se describen los componentes que admiten la aplicación de anuncio.</span><span class="sxs-lookup"><span data-stu-id="5262e-107">This section describes the components that support the Announcement application.</span></span>

<div>

## <a name="announcement-application-components"></a><span data-ttu-id="5262e-108">Componentes de la aplicación de anuncio</span><span class="sxs-lookup"><span data-stu-id="5262e-108">Announcement Application Components</span></span>

<span data-ttu-id="5262e-109">Los siguientes componentes de Lync Server admiten la aplicación de anuncio:</span><span class="sxs-lookup"><span data-stu-id="5262e-109">The following Lync Server components support the Announcement application:</span></span>

  - <span data-ttu-id="5262e-110">**Servicio**     de aplicación El servicio de aplicación proporciona una plataforma para implementar, hospedar y administrar las aplicaciones de comunicaciones unificadas.</span><span class="sxs-lookup"><span data-stu-id="5262e-110">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications.</span></span> <span data-ttu-id="5262e-111">El servicio de aplicación se instala automáticamente en todos los servidores front-end de un grupo de servidores front-end y en cada servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="5262e-111">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="5262e-112">Aplicación de grupo de **respuesta**     La aplicación de grupo de respuesta es una de las aplicaciones de comunicaciones unificadas que se hospedan en el servicio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="5262e-112">**Response Group application**   The Response Group application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="5262e-113">Cuando se configura un intervalo de números de teléfono sin asignar para redirigir a un anuncio, se requiere la aplicación de grupo de respuesta para enrutar las llamadas realizadas al número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="5262e-113">When an unassigned phone number range is configured to route to an announcement, the Response Group application is required to route the calls made to the phone number.</span></span> <span data-ttu-id="5262e-114">(La aplicación grupo de respuesta no es necesaria si todos los intervalos están configurados para enrutar a la mensajería unificada de Exchange).</span><span class="sxs-lookup"><span data-stu-id="5262e-114">(Response Group application is not required if all the ranges are configured to route to Exchange Unified Messaging (UM).)</span></span>

  - <span data-ttu-id="5262e-115">**Archivos**     de audio Los archivos de audio se usan para los anuncios.</span><span class="sxs-lookup"><span data-stu-id="5262e-115">**Audio files**   Audio files are used for the announcements.</span></span>

  - <span data-ttu-id="5262e-116">**Almacén**     de archivos La aplicación de anuncio usa el almacén de archivos para almacenar sus archivos de audio.</span><span class="sxs-lookup"><span data-stu-id="5262e-116">**File Store**   The Announcement application uses File Store to store its audio files.</span></span>

  - <span data-ttu-id="5262e-117">Panel de control de **Lync Server**     Puede usar el panel de control de Lync Server para configurar la tabla de números sin asignar.</span><span class="sxs-lookup"><span data-stu-id="5262e-117">**Lync Server Control Panel**   You can use Lync Server Control Panel to configure the unassigned number table.</span></span>

  - <span data-ttu-id="5262e-118">Shell de administración de **Lync Server**     Puede usar los cmdlets del shell de administración de Lync Server para configurar las opciones de anuncio y la tabla de números sin asignar.</span><span class="sxs-lookup"><span data-stu-id="5262e-118">**Lync Server Management Shell**   You can use Lync Server Management Shell cmdlets to configure Announcement settings and the unassigned number table.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

