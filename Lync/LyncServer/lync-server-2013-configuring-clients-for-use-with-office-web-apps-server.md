---
title: 'Lync Server 2013: configuración de clientes para su uso con Office Web Apps Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring clients for use with Office Web Apps Server
ms:assetid: e5eaead7-0b32-42fb-97eb-ca203af59a9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205339(v=OCS.15)
ms:contentKeyID: 48185668
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 263f53b61aa609c4385af2a9646bf84da2dea3cd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842273"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-clients-of-lync-server-2013-for-use-with-office-web-apps-server"></a><span data-ttu-id="8ac33-102">Configuración de clientes de Lync Server 2013 para su uso con Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="8ac33-102">Configuring clients of Lync Server 2013 for use with Office Web Apps Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ac33-103">_**Última modificación del tema:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="8ac33-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="8ac33-104">Si quiere que los usuarios experimenten todas las capacidades de Office Web App Server, debe actualizar esos usuarios a Microsoft Lync 2013. solo los usuarios de Lync 2013 podrán realizar tareas como desplazarse por las diapositivas de PowerPoint independientemente de la presentación real de PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="8ac33-104">If you want users to experience the full capabilities of Office Web App Server then you should upgrade those users to Microsoft Lync 2013; only users of Lync 2013 will be able to do such things as scroll through PowerPoint slides independent of the actual PowerPoint presentation.</span></span> <span data-ttu-id="8ac33-105">(Es decir, estos usuarios pueden ver cualquier diapositiva de la presentación en cualquier momento, sin interferir de ninguna manera con la presentación real). Los usuarios que no utilicen Lync 2013 seguirán pudiendo unirse a conferencias en línea y ver la presentación de PowerPoint. sin embargo, no podrán desplazarse independientemente por las diapositivas, ni podrán ver las transiciones de diapositivas ni ver los vídeos incrustados.</span><span class="sxs-lookup"><span data-stu-id="8ac33-105">(That is, these users can look at any slide in the presentation at any time, without interfering in any way with the actual presentation.) Users who are not using Lync 2013 will still be able to join online conferences and view the PowerPoint presentation; however, they will not be able to independently scroll through the slides, nor will they be able to see slide transitions or view embedded videos.</span></span>

<span data-ttu-id="8ac33-106">Tenga en cuenta que estas capacidades siempre estarán disponibles para los usuarios de Lync 2013. Esto es cierto incluso si el moderador de PowerPoint ejecuta Microsoft Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="8ac33-106">Note that these capabilities will always be available to users of Lync 2013; this is true even if the PowerPoint presenter is running Microsoft Lync 2010.</span></span> <span data-ttu-id="8ac33-107">Si un usuario que ejecuta Lync 2010 está hospedando una presentación de PowerPoint, Lync Server 2013 se coordinará con Office Web Apps Server para asegurarse de que los usuarios de Lync 2013 verán la versión de Office Web Apps Server de la presentación.</span><span class="sxs-lookup"><span data-stu-id="8ac33-107">If a PowerPoint presentation is being hosted by a user running Lync 2010, Lync Server 2013 will coordinate with Office Web Apps Server to make sure that Lync 2013 users will view the Office Web Apps Server version of that presentation.</span></span> <span data-ttu-id="8ac33-108">Office Web Apps Server no proporciona servicios de PowerPoint para los usuarios que ejecutan clientes distintos de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="8ac33-108">Office Web Apps Server does not provide PowerPoint services for users running clients other than Lync 2013.</span></span> <span data-ttu-id="8ac33-109">En su lugar, estos usuarios se conectan al servicio del servidor de conferencia y ven las presentaciones de PowerPoint de la misma manera que lo hacían en Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ac33-109">Instead, those users connect to the Conferencing server service and view PowerPoint presentations the same way they did in Microsoft Lync Server 2010.</span></span> <span data-ttu-id="8ac33-110">Esto también significa que estos usuarios solo tendrán acceso a las funciones más limitadas que ofrece Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ac33-110">This also means that these users will only have access to the more-limited capabilities offered by Lync Server 2010.</span></span>

<span data-ttu-id="8ac33-111">Aunque no se necesita ninguna configuración de cliente para Office Web Apps Server (aparte de la actualización de usuarios a Lync 2013), se recomienda que los asistentes a la Conferencia se actualicen a Internet Explorer 9.</span><span class="sxs-lookup"><span data-stu-id="8ac33-111">Although no client configuration is required for Office Web Apps Server (other than upgrading users to Lync 2013), it is recommended that conference attendees be upgrade to Internet Explorer 9.</span></span> <span data-ttu-id="8ac33-112">A pesar de que se puede acceder a las conferencias con Internet Explorer 8, hay algunas limitaciones en el uso de ese explorador Web.</span><span class="sxs-lookup"><span data-stu-id="8ac33-112">Although conferences can be accessed using Internet Explorer 8, there are some limitations to using that Web browser.</span></span> <span data-ttu-id="8ac33-113">Por ejemplo, los usuarios de Internet Explorer 8 no podrán cambiar el tamaño de la fase de PowerPoint a un tamaño personalizado; en su lugar, se limitarán a usar uno de los tres tamaños de escenario predefinidos.</span><span class="sxs-lookup"><span data-stu-id="8ac33-113">For example, users of Internet Explorer 8 will not be able to resize the PowerPoint stage to a custom size; instead, they will be limited to using one of three predefined stage sizes.</span></span> <span data-ttu-id="8ac33-114">Del mismo modo, los usuarios de Internet Explorer 8 no podrán reproducir archivos multimedia.</span><span class="sxs-lookup"><span data-stu-id="8ac33-114">Likewise, Internet Explorer 8 users will not be able to play media files.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

