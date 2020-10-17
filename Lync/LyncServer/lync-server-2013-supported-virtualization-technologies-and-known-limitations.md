---
title: 'Lync Server 2013: tecnologías de virtualización admitidas y limitaciones conocidas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported virtualization technologies and known limitations
ms:assetid: 6d3d749d-e840-4c05-afae-d6e69e7616aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204982(v=OCS.15)
ms:contentKeyID: 48184428
ms.date: 02/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61d2d884566c21933e00dd3897f5fe394b4a2624
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523937"
---
# <a name="supported-virtualization-technologies-and-known-limitations-in-lync-server-2013"></a><span data-ttu-id="7ac07-102">Tecnologías de virtualización admitidas y limitaciones conocidas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ac07-102">Supported virtualization technologies and known limitations in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ac07-103">_**Última modificación del tema:** 2017-02-06_</span><span class="sxs-lookup"><span data-stu-id="7ac07-103">_**Topic Last Modified:** 2017-02-06_</span></span>

<span data-ttu-id="7ac07-104">El complemento de VDI de Lync permite llamadas de audio y vídeo para tecnologías de virtualización compatibles.</span><span class="sxs-lookup"><span data-stu-id="7ac07-104">The Lync VDI plug-in allows audio and video calling for supported virtualization technologies.</span></span> <span data-ttu-id="7ac07-105">Esto amplía la funcionalidad que se describe en Microsoft Lync Server 2010 en las notas del producto [de virtualización de clientes en Microsoft lync 2010](https://go.microsoft.com/fwlink/?linkid=330447) .</span><span class="sxs-lookup"><span data-stu-id="7ac07-105">This extends the functionality outlined for Microsoft Lync Server 2010 in the [Client Virtualization in Microsoft Lync 2010](https://go.microsoft.com/fwlink/?linkid=330447) white paper.</span></span> <span data-ttu-id="7ac07-106">De acuerdo con las regulaciones telefónicas estándar, también se incluye compatibilidad con E911.</span><span class="sxs-lookup"><span data-stu-id="7ac07-106">In compliance with standard telephone regulations, support for E911 is also included.</span></span> <span data-ttu-id="7ac07-107">En las siguientes secciones se describen las tecnologías de virtualización que son compatibles con el complemento VDI de Lync y las limitaciones de características conocidas.</span><span class="sxs-lookup"><span data-stu-id="7ac07-107">The following sections describe the virtualization technologies that are supported by the Lync VDI plug-in and the known feature limitations.</span></span>

<div>

## <a name="support-for-virtualization-technologies"></a><span data-ttu-id="7ac07-108">Compatibilidad con tecnologías de virtualización</span><span class="sxs-lookup"><span data-stu-id="7ac07-108">Support for Virtualization Technologies</span></span>

<span data-ttu-id="7ac07-109">El complemento de VDI de Lync admite la comunicación remota de escritorio completa en el escenario de escritorio virtual personal, pero no en el escenario de sesión de escritorio remoto.</span><span class="sxs-lookup"><span data-stu-id="7ac07-109">The Lync VDI plug-in supports full desktop remoting in the personal virtual desktop scenario, but not in the remote desktop session scenario.</span></span> <span data-ttu-id="7ac07-110">Estos escenarios se pueden describir de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="7ac07-110">These scenarios can be described as follows:</span></span>

  - <span data-ttu-id="7ac07-111">Se **admite: escritorios virtuales personalizados o infraestructura de escritorio virtual (VDI).**     En este escenario, cada usuario inicia sesión en un escritorio virtual personalizable y puede guardar archivos en el escritorio que se conservan entre sesiones.</span><span class="sxs-lookup"><span data-stu-id="7ac07-111">**Supported: Personalized Virtual Desktops or Virtual Desktop Infrastructure (VDI).**   In this scenario, each user logs on to a customizable virtual desktop and is able to save files on the desktop that persist across sessions.</span></span> <span data-ttu-id="7ac07-112">Los servicios de escritorio remoto de Microsoft, la vista del horizonte de VMware y Citrix XenDesktop son implementaciones que se han probado para su uso con Lync.</span><span class="sxs-lookup"><span data-stu-id="7ac07-112">Microsoft Remote Desktop Services, VMware Horizon View, and Citrix XenDesktop are implementations that have been tested for use with Lync.</span></span> <span data-ttu-id="7ac07-113">Para obtener información sobre entornos VDI específicos del proveedor y hardware de cliente que han sido probados por Microsoft, consulte [infraestructura apta para Microsoft Lync](https://go.microsoft.com/fwlink/?linkid=313435).</span><span class="sxs-lookup"><span data-stu-id="7ac07-113">For information about vendor-specific VDI environments and client hardware that have been tested by Microsoft, see [Infrastructure qualified for Microsoft Lync](https://go.microsoft.com/fwlink/?linkid=313435).</span></span>

  - <span data-ttu-id="7ac07-114">**No admitido: sesiones de escritorio remoto.**     En este escenario, cada usuario inicia sesión en una sesión de escritorio virtual genérica que no se puede personalizar.</span><span class="sxs-lookup"><span data-stu-id="7ac07-114">**Not supported: Remote Desktop Sessions.**   In this scenario, each user logs on to a generic virtual desktop session that cannot be customized.</span></span> <span data-ttu-id="7ac07-115">Las implementaciones de ejemplo incluyen sesiones de escritorio remoto de Microsoft (RDSH) y Citrix XenApp junto con el receptor Citrix.</span><span class="sxs-lookup"><span data-stu-id="7ac07-115">Example implementations include Microsoft Remote Desktop Sessions (RDSH) and Citrix XenApp combined with Citrix Receiver.</span></span>

<span data-ttu-id="7ac07-116">El complemento de VDI de Lync no admite otras tecnologías de virtualización, como la virtualización de aplicaciones, que permite el uso de una aplicación sin necesidad de instalar la aplicación completa de forma local.</span><span class="sxs-lookup"><span data-stu-id="7ac07-116">The Lync VDI plug-in does not support other virtualization technologies, such as application virtualization, which allows the use of an application without requiring installation of the full application locally.</span></span> <span data-ttu-id="7ac07-117">Las implementaciones de ejemplo incluyen Citrix XenApp y Microsoft Application Virtualization (App-V).</span><span class="sxs-lookup"><span data-stu-id="7ac07-117">Example implementations include Citrix XenApp and Microsoft Application Virtualization (App-V).</span></span> <span data-ttu-id="7ac07-118">No se admiten la transmisión por secuencias de aplicaciones, la comunicación remota de aplicaciones y los modos mixtos de virtualización (por ejemplo, el acceso remoto de aplicaciones en el entorno remoto de escritorio completo).</span><span class="sxs-lookup"><span data-stu-id="7ac07-118">Application streaming, application remoting, and mixed virtualization modes (for example, application remoting in full desktop remoting) are not supported.</span></span>

<span data-ttu-id="7ac07-119">Para permitir la extensibilidad, el complemento de VDI de Lync se diseñó para usar API independientes de la plataforma denominadas canales virtuales dinámicos (DVC).</span><span class="sxs-lookup"><span data-stu-id="7ac07-119">To allow extensibility, the Lync VDI plug-in was designed to use platform-independent APIs called Dynamic Virtual Channels (DVCs).</span></span> <span data-ttu-id="7ac07-120">Para escenarios que no son compatibles de forma explícita con Lync, consulte las instrucciones de compatibilidad del proveedor de la solución de VDI.</span><span class="sxs-lookup"><span data-stu-id="7ac07-120">For scenarios that are not explicitly supported by Lync, refer to support statements from the VDI solution provider.</span></span>

</div>

<div>

## <a name="known-feature-limitations"></a><span data-ttu-id="7ac07-121">Limitaciones de las características conocidas</span><span class="sxs-lookup"><span data-stu-id="7ac07-121">Known Feature Limitations</span></span>

<span data-ttu-id="7ac07-122">A continuación se indican las limitaciones conocidas al usar Lync 2013 en un entorno de VDI:</span><span class="sxs-lookup"><span data-stu-id="7ac07-122">The following are known limitations when you use Lync 2013 in a VDI environment:</span></span>

  - <span data-ttu-id="7ac07-123">La delegación de llamadas y las características de anonymization del agente de grupo de respuesta tienen compatibilidad limitada.</span><span class="sxs-lookup"><span data-stu-id="7ac07-123">There is limited support for Call Delegation and Response Group Agent Anonymization features.</span></span>

  - <span data-ttu-id="7ac07-124">No se admiten estas características:</span><span class="sxs-lookup"><span data-stu-id="7ac07-124">There is no support for the following features:</span></span>
    
      - <span data-ttu-id="7ac07-125">Las páginas de ajuste del dispositivo de audio y de vídeo integrados.</span><span class="sxs-lookup"><span data-stu-id="7ac07-125">Integrated Audio Device and Video Device tuning pages.</span></span>
    
      - <span data-ttu-id="7ac07-126">Vídeo de varias vistas.</span><span class="sxs-lookup"><span data-stu-id="7ac07-126">Multiple-view video.</span></span>
    
      - <span data-ttu-id="7ac07-127">La grabación de las conversaciones.</span><span class="sxs-lookup"><span data-stu-id="7ac07-127">Recording of conversations.</span></span>
    
      - <span data-ttu-id="7ac07-128">Servicios de escritorio remoto (RDS).</span><span class="sxs-lookup"><span data-stu-id="7ac07-128">Remote Desktop Services (RDS).</span></span>
    
      - <span data-ttu-id="7ac07-129">Unirse a reuniones de forma anónima (es decir, unirse a reuniones de Lync hospedadas por una organización que no se federa con la organización).</span><span class="sxs-lookup"><span data-stu-id="7ac07-129">Joining meetings anonymously (that is, joining Lync meetings hosted by an organization that does not federate with your organization).</span></span>
    
      - <span data-ttu-id="7ac07-130">Usar el complemento de VDI de Lync junto con un dispositivo de Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="7ac07-130">Using the Lync VDI plug-in along with a Lync Phone Edition device.</span></span>
    
      - <span data-ttu-id="7ac07-131">La continuación de llamadas en caso de una interrupción de la red.</span><span class="sxs-lookup"><span data-stu-id="7ac07-131">Call continuity in case of a network outage.</span></span>
    
      - <span data-ttu-id="7ac07-132">Tonos personalizados y características de música en espera.</span><span class="sxs-lookup"><span data-stu-id="7ac07-132">Customized ringtones and music-on-hold features.</span></span>

  - <span data-ttu-id="7ac07-133">El complemento de VDI para Lync no es compatible con un entorno de Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="7ac07-133">The Lync VDI plug-in is not supported in a Microsoft 365 or Office 365 environment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

