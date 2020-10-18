---
title: Administración de las opciones de configuración del servicio de registro centralizado
description: Administración de las opciones de configuración del servicio de registro centralizado.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing the Centralized Logging Service configuration settings
ms:assetid: f455c3aa-0061-413d-bdfb-a3e78f82723d
ms:mtpsurl: https://technet.microsoft.com/library/JJ721938(v=OCS.15)
ms:contentKeyID: 49733875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e25294e096b8368aa06a11e4ad851fe5d1a84c0f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572606"
---
# <a name="managing-the-centralized-logging-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="ae3f3-103">Administración de las opciones de configuración del servicio de registro centralizado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae3f3-103">Managing the Centralized Logging Service configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae3f3-104">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="ae3f3-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="ae3f3-105">El servicio de registro centralizado está controlado y configurado por la configuración y los parámetros que crea y usa el controlador del servicio de registro centralizado (CLSController) para enviar comandos al agente del servicio de registro centralizado (CLSAgent) del equipo individual.</span><span class="sxs-lookup"><span data-stu-id="ae3f3-105">The Centralized Logging Service is controlled and configured by settings and parameters that are created and used by the Centralized Logging Service Controller (CLSController) to send commands to the individual computer’s Centralized Logging Service Agent (CLSAgent).</span></span> <span data-ttu-id="ae3f3-106">El agente procesa los comandos que le envían y (en el caso del comando Start) usa la configuración de los escenarios, los proveedores, el tamaño del registro, la duración del seguimiento y los indicadores para comenzar a recopilar registros de seguimiento de acuerdo con la información de configuración facilitada.</span><span class="sxs-lookup"><span data-stu-id="ae3f3-106">The agent processes the commands that are sent to it and (in the case of a Start command) uses the configuration of the scenarios, providers, log size, trace duration, and flags to begin collecting trace logs according to the configuration information provided.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="ae3f3-107">No todos los cmdlets de Windows PowerShell que se muestran para el servicio de registro centralizado están pensados para su uso con implementaciones locales de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ae3f3-107">Not all Windows PowerShell cmdlets listed for the Centralized Logging Service are intended for use with Lync Server 2013 on-premises deployments.</span></span> <span data-ttu-id="ae3f3-108">Aunque puede parecer que funcionen, los siguientes cmdlets no están diseñados para funcionar con las implementaciones locales de Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="ae3f3-108">Although they may appear to work, the following cmdlets are not designed to function with Lync Server 2013 on-premises deployments:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="ae3f3-109"><STRONG>Cmdlets de CsClsRegion:</STRONG> <A href="https://technet.microsoft.com/library/JJ204879(v=OCS.15)">Get-CsClsRegion</A>, <A href="https://technet.microsoft.com/library/JJ204746(v=OCS.15)">Set-CsClsRegion</A>, <A href="https://technet.microsoft.com/library/JJ204658(v=OCS.15)">New-CsClsRegion</A> y <A href="https://technet.microsoft.com/library/JJ204971(v=OCS.15)">Remove-CsClsRegion</A>.</span><span class="sxs-lookup"><span data-stu-id="ae3f3-109"><STRONG>CsClsRegion cmdlets:</STRONG> <A href="https://technet.microsoft.com/library/JJ204879(v=OCS.15)">Get-CsClsRegion</A>, <A href="https://technet.microsoft.com/library/JJ204746(v=OCS.15)">Set-CsClsRegion</A>, <A href="https://technet.microsoft.com/library/JJ204658(v=OCS.15)">New-CsClsRegion</A>, and <A href="https://technet.microsoft.com/library/JJ204971(v=OCS.15)">Remove-CsClsRegion</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="ae3f3-110"><STRONG>Cmdlets de CsClsSearchTerm:</STRONG> <A href="https://technet.microsoft.com/library/JJ205061(v=OCS.15)">Get-CsClsSearchTerm</A> y <A href="https://technet.microsoft.com/library/JJ204911(v=OCS.15)">Set-CsClsSearchTerm</A>.</span><span class="sxs-lookup"><span data-stu-id="ae3f3-110"><STRONG>CsClsSearchTerm cmdlets:</STRONG> <A href="https://technet.microsoft.com/library/JJ205061(v=OCS.15)">Get-CsClsSearchTerm</A> and <A href="https://technet.microsoft.com/library/JJ204911(v=OCS.15)">Set-CsClsSearchTerm</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="ae3f3-111"><STRONG>Cmdlets de CsClsSecurityGroup:</STRONG> <A href="https://technet.microsoft.com/library/JJ205285(v=OCS.15)">Get-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/library/JJ204700(v=OCS.15)">Set-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/library/JJ205359(v=OCS.15)">New-CsClsSecurityGroup</A> y <A href="https://technet.microsoft.com/library/JJ204958(v=OCS.15)">Remove-CsClsSecurityGroup</A>.</span><span class="sxs-lookup"><span data-stu-id="ae3f3-111"><STRONG>CsClsSecurityGroup cmdlets:</STRONG> <A href="https://technet.microsoft.com/library/JJ205285(v=OCS.15)">Get-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/library/JJ204700(v=OCS.15)">Set-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/library/JJ205359(v=OCS.15)">New-CsClsSecurityGroup</A>, and <A href="https://technet.microsoft.com/library/JJ204958(v=OCS.15)">Remove-CsClsSecurityGroup</A>.</span></span></P></LI></UL><span data-ttu-id="ae3f3-112">La configuración definida en estos cmdlets no obstaculizará ni provocará ningún comportamiento adverso, pero está diseñado para usarse con Microsoft 365 y no proporcionará los resultados esperados en implementaciones locales.</span><span class="sxs-lookup"><span data-stu-id="ae3f3-112">The settings defined in these cmdlets will not hinder or cause any adverse behavior, but they are designed for use with Microsoft 365 and will not yield the expected results in on-premises deployments.</span></span> <span data-ttu-id="ae3f3-113">Lo cual no significa que estos cmdlets no sirvan para las implementaciones locales, sino que lo cierto es que tienen un uso más avanzado que no se aborda en esta documentación.</span><span class="sxs-lookup"><span data-stu-id="ae3f3-113">This is not to say that there is no use for these cmdlets in on-premises deployments, but their use is a more advanced topic that is not covered in this documentation.</span></span>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ae3f3-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ae3f3-114">In This Section</span></span>

<span data-ttu-id="ae3f3-115">En los temas de esta sección se definen las opciones de configuración, los parámetros y la configuración del servicio de registro centralizado.</span><span class="sxs-lookup"><span data-stu-id="ae3f3-115">The topics in this section define the configuration options, parameters, and settings for the Centralized Logging Service.</span></span> <span data-ttu-id="ae3f3-116">En los temas siguientes se incluye información sobre cómo configurar el servicio de registro centralizado, cómo recuperar las opciones de configuración, la creación de escenarios, la administración de grupos de seguridad para el servicio de registro centralizado, la búsqueda y más.</span><span class="sxs-lookup"><span data-stu-id="ae3f3-116">Information about how to configure the Centralized Logging Service, how to retrieve the configuration settings, creation of scenarios, management of security groups for Centralized Logging Service, searching, and more is contained in the following topics.</span></span>

  - [<span data-ttu-id="ae3f3-117">Administración de equipos, sitios y configuración del servicio de registro centralizado global en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae3f3-117">Managing computer, site and global Centralized Logging Service configuration in Lync Server 2013</span></span>](lync-server-2013-managing-computer-site-and-global-centralized-logging-service-configuration.md)

  - [<span data-ttu-id="ae3f3-118">Configuración de proveedores para el servicio de registro centralizado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae3f3-118">Configuring providers for Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-configuring-providers-for-centralized-logging-service.md)

  - [<span data-ttu-id="ae3f3-119">Configuración de escenarios para el servicio de registro centralizado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae3f3-119">Configuring scenarios for the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-configuring-scenarios-for-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ae3f3-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ae3f3-120">See Also</span></span>


[<span data-ttu-id="ae3f3-121">Información general sobre el servicio de registro centralizado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae3f3-121">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  
[<span data-ttu-id="ae3f3-122">Cmdlets de registro centralizado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae3f3-122">Centralized Logging cmdlets in Lync Server 2013</span></span>](lync-server-2013-centralized-logging-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

