---
title: 'Lync Server 2013: componentes que usa el estacionamiento de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Call Park
ms:assetid: c7ffbee3-0ce1-48c0-bb56-af098b41d6d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398824(v=OCS.15)
ms:contentKeyID: 48185374
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b4a833736368fe6060dad4fbb62e6a528e91b6c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136487"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-used-by-call-park-in-lync-server-2013"></a><span data-ttu-id="fc18a-102">Componentes que usa el estacionamiento de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc18a-102">Components used by Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc18a-103">_**Última modificación del tema:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="fc18a-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="fc18a-104">La aplicación estacionamiento de llamadas se instala automáticamente al implementar la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="fc18a-104">The Call Park application is automatically installed when you deploy Enterprise Voice.</span></span> <span data-ttu-id="fc18a-105">Puede habilitar el estacionamiento de llamadas mediante la configuración de la Directiva de voz.</span><span class="sxs-lookup"><span data-stu-id="fc18a-105">You enable Call Park by configuring voice policy.</span></span> <span data-ttu-id="fc18a-106">Los siguientes componentes de Lync Server 2013 admiten la aplicación estacionamiento de llamadas:</span><span class="sxs-lookup"><span data-stu-id="fc18a-106">The following Lync Server 2013 components support the Call Park application:</span></span>

  - <span data-ttu-id="fc18a-107">\*\*\*\*   El servicio de aplicación de servicio de aplicación proporciona una plataforma para implementar, hospedar y administrar aplicaciones de comunicaciones unificadas, como la aplicación de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="fc18a-107">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as the Call Park application.</span></span> <span data-ttu-id="fc18a-108">El servicio de aplicación se instala automáticamente en todos los servidores front-end de un grupo de servidores front-end y en cada servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="fc18a-108">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="fc18a-109">**Aplicación estacionamiento de llamadas**   la aplicación de estacionamiento de llamadas es una de las aplicaciones de comunicaciones unificadas que se hospedan en el servicio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="fc18a-109">**Call Park application**   The Call Park application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="fc18a-110">Se incluye automáticamente al implementar la Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="fc18a-110">It is included automatically when you deploy Enterprise Voice.</span></span> <span data-ttu-id="fc18a-111">Los parques de estacionamiento de llamadas y recuperan llamadas y administran órbitas de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="fc18a-111">Call Park parks and retrieves calls and manages call park orbits.</span></span>

  - <span data-ttu-id="fc18a-112">**Música en espera-archivo**   si la música está habilitada, el archivo de música se reproduce mientras se estaciona una llamada.</span><span class="sxs-lookup"><span data-stu-id="fc18a-112">**Music-on hold-file**   If music in enabled, the music file is played while a call is parked.</span></span> <span data-ttu-id="fc18a-113">Se incluye un archivo de música predeterminado cuando se instala la aplicación de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="fc18a-113">A default music file is included when the Call Park application is installed.</span></span>

  - <span data-ttu-id="fc18a-114">**Almacén de archivos**   la aplicación estacionamiento de llamadas usa el almacén de archivos para guardar los archivos de audio personalizados.</span><span class="sxs-lookup"><span data-stu-id="fc18a-114">**File Store**   The Call Park application uses File Store to hold custom audio files.</span></span>

  - <span data-ttu-id="fc18a-115">**Panel de control de Lync Server**   puede usar el panel de control de Lync Server para configurar la tabla de órbitas de estacionamiento de llamadas y habilitar el estacionamiento de llamadas para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="fc18a-115">**Lync Server Control Panel**   You can use Lync Server Control Panel to configure the call park orbit table and to enable Call Park for users.</span></span>

  - <span data-ttu-id="fc18a-116">**Shell de administración de Lync Server**   toda la configuración de la aplicación estacionamiento de llamadas se puede realizar mediante los cmdlets del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fc18a-116">**Lync Server Management Shell**   All Call Park application configuration can be performed by using Lync Server Management Shell cmdlets.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

