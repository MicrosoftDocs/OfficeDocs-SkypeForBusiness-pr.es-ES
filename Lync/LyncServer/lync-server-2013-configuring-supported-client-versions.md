---
title: 'Lync Server 2013: configuración de versiones de cliente compatibles'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring supported client versions
ms:assetid: aebf7b48-9aa2-4a06-adc5-0c9d11b6358d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412832(v=OCS.15)
ms:contentKeyID: 48185137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a262cab2145013d83cdae573d98b5db17e0e890
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734780"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-supported-client-versions-in-lync-server-2013"></a><span data-ttu-id="7638d-102">Configuración de las versiones de cliente compatibles en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7638d-102">Configuring supported client versions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7638d-103">_**Última modificación del tema:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="7638d-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="7638d-104">En Lync Server 2013, puede configurar directivas de versión de cliente para especificar las versiones de clientes que son compatibles con su entorno.</span><span class="sxs-lookup"><span data-stu-id="7638d-104">In Lync Server 2013, you can set up client version policies to specify the versions of clients that are supported in your environment.</span></span> <span data-ttu-id="7638d-105">Además, puede usar la configuración de la versión de cliente global para especificar una acción predeterminada para clientes que aún no tienen una directiva de versión definida y, por lo tanto, no se admiten o restringen explícitamente.</span><span class="sxs-lookup"><span data-stu-id="7638d-105">Additionally, you can use the global client version configuration to specify a default action for clients that do not already have a version policy defined and, therefore, are not explicitly supported or restricted.</span></span>

<span data-ttu-id="7638d-106">También puede usar las directivas de versión de cliente para administrar las actualizaciones de cliente.</span><span class="sxs-lookup"><span data-stu-id="7638d-106">You can also use client version policies to manage client updates.</span></span> <span data-ttu-id="7638d-107">Al establecer una directiva de versión de cliente y usar las opciones **permitir y actualizar** , y **bloquear y actualizar**, los clientes recibirán software actualizado del servicio de actualización de Windows Server (si está usando este servicio) o de Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="7638d-107">When you set a client version policy and use the options **Allow and upgrade** and **Block and upgrade**, clients will receive updated software from the Windows Server Update Service (if you are using this service) or from Microsoft Update.</span></span>

<div>

## <a name="client-version-policy-settings"></a><span data-ttu-id="7638d-108">Configuración de la Directiva de versión del cliente</span><span class="sxs-lookup"><span data-stu-id="7638d-108">Client Version Policy Settings</span></span>

<span data-ttu-id="7638d-109">La Directiva de versión de cliente predeterminada requiere que todos los clientes ejecuten Lync.</span><span class="sxs-lookup"><span data-stu-id="7638d-109">The default client version policy requires that all clients run Lync.</span></span> <span data-ttu-id="7638d-110">Si los clientes de su entorno ejecutan versiones anteriores de Communicator, es posible que tenga que volver a configurar las reglas de versión de cliente para evitar que los clientes y dispositivos se bloqueen o actualicen de forma inesperada al conectarse a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7638d-110">If clients in your environment are running earlier versions of Communicator, you may need to reconfigure the Client Version rules to prevent clients and devices from being unexpectedly blocked or updated when connecting to Lync Server 2013.</span></span> <span data-ttu-id="7638d-111">Puede modificar la regla predeterminada o puede Agregar una regla en la lista de directivas de versión de cliente para invalidar la regla predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7638d-111">You can modify the default rule, or you can add a rule higher in the Client Version Policy list to override the default rule.</span></span> <span data-ttu-id="7638d-112">Además, a medida que se publican las actualizaciones acumulativas (CUs), debe configurar la Directiva de versión del cliente para que requiera las actualizaciones más recientes.</span><span class="sxs-lookup"><span data-stu-id="7638d-112">Additionally, as Cumulative Updates (CUs) are released, you should configure the Client Version Policy to require the latest updates.</span></span> <span data-ttu-id="7638d-113">Para obtener más información, vea [especificar las aplicaciones cliente que se pueden usar para iniciar sesión en Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="7638d-113">For details, see [Specifying the client applications that can be used to log on to Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md) in the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

