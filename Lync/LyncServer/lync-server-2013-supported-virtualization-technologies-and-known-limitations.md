---
title: 'Lync Server 2013: Tecnologías de virtualización admitidas y limitaciones comunes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported virtualization technologies and known limitations
ms:assetid: 6d3d749d-e840-4c05-afae-d6e69e7616aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204982(v=OCS.15)
ms:contentKeyID: 48184428
ms.date: 02/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b5c99151be45f70d1d95fa0a89835ebb6f7d352
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850533"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-virtualization-technologies-and-known-limitations-in-lync-server-2013"></a><span data-ttu-id="c716e-102">Tecnologías de virtualización admitidas y limitaciones comunes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c716e-102">Supported virtualization technologies and known limitations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c716e-103">_**Última modificación del tema:** 2017-02-06_</span><span class="sxs-lookup"><span data-stu-id="c716e-103">_**Topic Last Modified:** 2017-02-06_</span></span>

<span data-ttu-id="c716e-104">El complemento VDI para Lync permite llamadas de audio y vídeo para tecnologías de virtualización compatibles.</span><span class="sxs-lookup"><span data-stu-id="c716e-104">The Lync VDI plug-in allows audio and video calling for supported virtualization technologies.</span></span> <span data-ttu-id="c716e-105">Esto extiende la funcionalidad descrita para Microsoft Lync Server 2010 en las notas del producto [de virtualización de cliente en Microsoft lync 2010](https://go.microsoft.com/fwlink/?linkid=330447) .</span><span class="sxs-lookup"><span data-stu-id="c716e-105">This extends the functionality outlined for Microsoft Lync Server 2010 in the [Client Virtualization in Microsoft Lync 2010](https://go.microsoft.com/fwlink/?linkid=330447) white paper.</span></span> <span data-ttu-id="c716e-106">Conforme a las normativas estándar para teléfonos, también se incluye compatibilidad con E911.</span><span class="sxs-lookup"><span data-stu-id="c716e-106">In compliance with standard telephone regulations, support for E911 is also included.</span></span> <span data-ttu-id="c716e-107">En las siguientes secciones se describen las tecnologías de virtualización admitidas por el complemento VDI de Lync y las limitaciones de las características conocidas.</span><span class="sxs-lookup"><span data-stu-id="c716e-107">The following sections describe the virtualization technologies that are supported by the Lync VDI plug-in and the known feature limitations.</span></span>

<div>

## <a name="support-for-virtualization-technologies"></a><span data-ttu-id="c716e-108">Soporte de tecnologías de virtualización</span><span class="sxs-lookup"><span data-stu-id="c716e-108">Support for Virtualization Technologies</span></span>

<span data-ttu-id="c716e-109">El complemento de VDI para Lync es compatible con el entorno remoto de escritorio completo en el escenario de escritorio virtual personal, pero no en el escenario de sesión de escritorio remoto.</span><span class="sxs-lookup"><span data-stu-id="c716e-109">The Lync VDI plug-in supports full desktop remoting in the personal virtual desktop scenario, but not in the remote desktop session scenario.</span></span> <span data-ttu-id="c716e-110">Estos entornos pueden describirse así:</span><span class="sxs-lookup"><span data-stu-id="c716e-110">These scenarios can be described as follows:</span></span>

  - <span data-ttu-id="c716e-111">**Compatible: escritorios virtuales personalizados o infraestructura de escritorio virtual (VDI).**    En este escenario, cada usuario inicia sesión en un escritorio virtual personalizable y puede guardar archivos en el escritorio que permanecen entre sesiones.</span><span class="sxs-lookup"><span data-stu-id="c716e-111">**Supported: Personalized Virtual Desktops or Virtual Desktop Infrastructure (VDI).**   In this scenario, each user logs on to a customizable virtual desktop and is able to save files on the desktop that persist across sessions.</span></span> <span data-ttu-id="c716e-112">Los servicios de escritorio remoto de Microsoft, la vista de horizonte de VMware y Citrix XenDesktop son implementaciones probadas para su uso con Lync.</span><span class="sxs-lookup"><span data-stu-id="c716e-112">Microsoft Remote Desktop Services, VMware Horizon View, and Citrix XenDesktop are implementations that have been tested for use with Lync.</span></span> <span data-ttu-id="c716e-113">Para obtener información sobre los entornos de VDI específicos del proveedor y el hardware de cliente que Microsoft ha probado, consulte [infraestructura cualificada para Microsoft Lync](https://go.microsoft.com/fwlink/?linkid=313435).</span><span class="sxs-lookup"><span data-stu-id="c716e-113">For information about vendor-specific VDI environments and client hardware that have been tested by Microsoft, see [Infrastructure qualified for Microsoft Lync](https://go.microsoft.com/fwlink/?linkid=313435).</span></span>

  - <span data-ttu-id="c716e-114">**No admitido: sesiones de escritorio remoto.**    En este escenario, cada usuario inicia sesión en una sesión de escritorio virtual genérica que no se puede personalizar.</span><span class="sxs-lookup"><span data-stu-id="c716e-114">**Not supported: Remote Desktop Sessions.**   In this scenario, each user logs on to a generic virtual desktop session that cannot be customized.</span></span> <span data-ttu-id="c716e-115">Algunos ejemplos de implementaciones son las sesiones de escritorio remoto de Microsoft (RDSH) y Citrix XenApp combinadas con Citrix Receiver.</span><span class="sxs-lookup"><span data-stu-id="c716e-115">Example implementations include Microsoft Remote Desktop Sessions (RDSH) and Citrix XenApp combined with Citrix Receiver.</span></span>

<span data-ttu-id="c716e-116">El complemento de VDI para Lync no admite otras tecnologías de virtualización, como la virtualización de aplicaciones, que permite el uso de una aplicación sin requerir la instalación de la aplicación completa de forma local.</span><span class="sxs-lookup"><span data-stu-id="c716e-116">The Lync VDI plug-in does not support other virtualization technologies, such as application virtualization, which allows the use of an application without requiring installation of the full application locally.</span></span> <span data-ttu-id="c716e-117">Algunos ejemplos de implementaciones son Citrix XenApp y Microsoft Application Virtualization (App-V).</span><span class="sxs-lookup"><span data-stu-id="c716e-117">Example implementations include Citrix XenApp and Microsoft Application Virtualization (App-V).</span></span> <span data-ttu-id="c716e-118">El streaming de aplicaciones, la comunicación remota de aplicaciones y los modos mixtos de virtualización (por ejemplo, la comunicación remota de aplicaciones en la comunicación remota de escritorio completa) no se admiten.</span><span class="sxs-lookup"><span data-stu-id="c716e-118">Application streaming, application remoting, and mixed virtualization modes (for example, application remoting in full desktop remoting) are not supported.</span></span>

<span data-ttu-id="c716e-119">Para permitir la extensibilidad, el complemento de VDI para Lync se diseñó para usar las API independientes de la plataforma denominadas canales virtuales dinámicos (DVCs).</span><span class="sxs-lookup"><span data-stu-id="c716e-119">To allow extensibility, the Lync VDI plug-in was designed to use platform-independent APIs called Dynamic Virtual Channels (DVCs).</span></span> <span data-ttu-id="c716e-120">Para escenarios que no son explícitamente compatibles con Lync, consulte declaraciones de soporte técnico del proveedor de soluciones de VDI.</span><span class="sxs-lookup"><span data-stu-id="c716e-120">For scenarios that are not explicitly supported by Lync, refer to support statements from the VDI solution provider.</span></span>

</div>

<div>

## <a name="known-feature-limitations"></a><span data-ttu-id="c716e-121">Limitaciones comunes de la funciones</span><span class="sxs-lookup"><span data-stu-id="c716e-121">Known Feature Limitations</span></span>

<span data-ttu-id="c716e-122">A continuación se muestran algunas limitaciones conocidas al usar Lync 2013 en un entorno de VDI:</span><span class="sxs-lookup"><span data-stu-id="c716e-122">The following are known limitations when you use Lync 2013 in a VDI environment:</span></span>

  - <span data-ttu-id="c716e-123">La delegación de llamadas y las características de anonymization de grupo de respuesta son limitadas.</span><span class="sxs-lookup"><span data-stu-id="c716e-123">There is limited support for Call Delegation and Response Group Agent Anonymization features.</span></span>

  - <span data-ttu-id="c716e-124">No se admiten estas características:</span><span class="sxs-lookup"><span data-stu-id="c716e-124">There is no support for the following features:</span></span>
    
      - <span data-ttu-id="c716e-125">Las páginas de ajuste del dispositivo de audio y de vídeo integrados.</span><span class="sxs-lookup"><span data-stu-id="c716e-125">Integrated Audio Device and Video Device tuning pages.</span></span>
    
      - <span data-ttu-id="c716e-126">El vídeo de múltiples vistas.</span><span class="sxs-lookup"><span data-stu-id="c716e-126">Multiple-view video.</span></span>
    
      - <span data-ttu-id="c716e-127">La grabación de las conversaciones.</span><span class="sxs-lookup"><span data-stu-id="c716e-127">Recording of conversations.</span></span>
    
      - <span data-ttu-id="c716e-128">Servicios de escritorio remoto (RDS).</span><span class="sxs-lookup"><span data-stu-id="c716e-128">Remote Desktop Services (RDS).</span></span>
    
      - <span data-ttu-id="c716e-129">Unirse a reuniones de forma anónima (es decir, unirse a reuniones de Lync hospedadas por una organización que no se federan con su organización).</span><span class="sxs-lookup"><span data-stu-id="c716e-129">Joining meetings anonymously (that is, joining Lync meetings hosted by an organization that does not federate with your organization).</span></span>
    
      - <span data-ttu-id="c716e-130">Usar el complemento VDI de Lync junto con un dispositivo de Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="c716e-130">Using the Lync VDI plug-in along with a Lync Phone Edition device.</span></span>
    
      - <span data-ttu-id="c716e-131">La continuación de llamadas en caso de una interrupción de la red.</span><span class="sxs-lookup"><span data-stu-id="c716e-131">Call continuity in case of a network outage.</span></span>
    
      - <span data-ttu-id="c716e-132">Las características de tonos de llamada personalizados y de música en espera.</span><span class="sxs-lookup"><span data-stu-id="c716e-132">Customized ringtones and music-on-hold features.</span></span>

  - <span data-ttu-id="c716e-133">El complemento de VDI para Lync no es compatible en un entorno de Office 365.</span><span class="sxs-lookup"><span data-stu-id="c716e-133">The Lync VDI plug-in is not supported in an Office 365 environment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

