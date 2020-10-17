---
title: 'Lync Server 2013: componentes que usa la aplicación de anuncio'
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
ms.openlocfilehash: 84fb2d57e03965acff9d647854b86d7a5a528246
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517717"
---
# <a name="components-used-by-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="c651e-102">Componentes usados por la aplicación de anuncio en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c651e-102">Components used by the Announcement application in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c651e-103">_**Última modificación del tema:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="c651e-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="c651e-104">En Lync Server 2013, la aplicación de anuncio es un componente de la aplicación de grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="c651e-104">In Lync Server 2013, the Announcement application is a component of the Response Group application.</span></span> <span data-ttu-id="c651e-105">Al implementar la telefonía IP empresarial, la aplicación del anuncio se instala y se activa automáticamente junto con la aplicación grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="c651e-105">When you deploy Enterprise Voice, the Announcement application is automatically installed and activated along with the Response Group application.</span></span> <span data-ttu-id="c651e-106">En esta sección se describen los componentes que admiten la aplicación de anuncio.</span><span class="sxs-lookup"><span data-stu-id="c651e-106">This section describes the components that support the Announcement application.</span></span>

<div>

## <a name="announcement-application-components"></a><span data-ttu-id="c651e-107">Componentes de la aplicación de anuncio</span><span class="sxs-lookup"><span data-stu-id="c651e-107">Announcement Application Components</span></span>

<span data-ttu-id="c651e-108">Los siguientes componentes de Lync Server admiten la aplicación de anuncio:</span><span class="sxs-lookup"><span data-stu-id="c651e-108">The following Lync Server components support the Announcement application:</span></span>

  - <span data-ttu-id="c651e-109">**Servicio**     de aplicación El servicio de aplicación proporciona una plataforma para implementar, hospedar y administrar las aplicaciones de comunicaciones unificadas.</span><span class="sxs-lookup"><span data-stu-id="c651e-109">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications.</span></span> <span data-ttu-id="c651e-110">El servicio de aplicación se instala automáticamente en todos los servidores front-end de un grupo de servidores front-end y en cada servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="c651e-110">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="c651e-111">Aplicación de grupo de **respuesta**     La aplicación de grupo de respuesta es una de las aplicaciones de comunicaciones unificadas que se hospedan en el servicio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="c651e-111">**Response Group application**   The Response Group application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="c651e-112">Cuando se configura un intervalo de números de teléfono sin asignar para redirigir a un anuncio, se requiere la aplicación de grupo de respuesta para enrutar las llamadas realizadas al número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="c651e-112">When an unassigned phone number range is configured to route to an announcement, the Response Group application is required to route the calls made to the phone number.</span></span> <span data-ttu-id="c651e-113">(La aplicación grupo de respuesta no es necesaria si todos los intervalos están configurados para enrutar a la mensajería unificada de Exchange).</span><span class="sxs-lookup"><span data-stu-id="c651e-113">(Response Group application is not required if all the ranges are configured to route to Exchange Unified Messaging (UM).)</span></span>

  - <span data-ttu-id="c651e-114">**Archivos**     de audio Los archivos de audio se usan para los anuncios.</span><span class="sxs-lookup"><span data-stu-id="c651e-114">**Audio files**   Audio files are used for the announcements.</span></span>

  - <span data-ttu-id="c651e-115">**Almacén**     de archivos La aplicación de anuncio usa el almacén de archivos para almacenar sus archivos de audio.</span><span class="sxs-lookup"><span data-stu-id="c651e-115">**File Store**   The Announcement application uses File Store to store its audio files.</span></span>

  - <span data-ttu-id="c651e-116">Panel de control de **Lync Server**     Puede usar el panel de control de Lync Server para configurar la tabla de números sin asignar.</span><span class="sxs-lookup"><span data-stu-id="c651e-116">**Lync Server Control Panel**   You can use Lync Server Control Panel to configure the unassigned number table.</span></span>

  - <span data-ttu-id="c651e-117">Shell de administración de **Lync Server**     Puede usar los cmdlets del shell de administración de Lync Server para configurar las opciones de anuncio y la tabla de números sin asignar.</span><span class="sxs-lookup"><span data-stu-id="c651e-117">**Lync Server Management Shell**   You can use Lync Server Management Shell cmdlets to configure Announcement settings and the unassigned number table.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

