---
title: 'Lync Server 2013: preparación e instalación del analizador de procedimientos recomendados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing for and installing Best Practices Analyzer
ms:assetid: 550613dd-dc08-482e-9980-a3fe187cd162
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591347(v=OCS.15)
ms:contentKeyID: 48184149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59bcaca40414c9bd99e451846c0339d0af6e7bf3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183723"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-for-and-installing-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="0bfc7-102">Preparación e instalación del analizador de procedimientos recomendados en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0bfc7-102">Preparing for and installing Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0bfc7-103">_**Última modificación del tema:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="0bfc7-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="0bfc7-104">Para realizar las tareas que se describen en este tema debe haber iniciado sesión como miembro del grupo Administradores.</span><span class="sxs-lookup"><span data-stu-id="0bfc7-104">You must be logged on as a member of the Administrators group to perform the tasks that are described in this topic.</span></span>

<div>

## <a name="system-requirements-for-best-practices-analyzer-installation"></a><span data-ttu-id="0bfc7-105">Requisitos del sistema para la instalación del Analizador de procedimientos recomendados</span><span class="sxs-lookup"><span data-stu-id="0bfc7-105">System Requirements for Best Practices Analyzer Installation</span></span>

<span data-ttu-id="0bfc7-106">Para ejecutar Lync Server 2013, el analizador de procedimientos recomendados para examinar el entorno, el equipo debe ejecutar una edición de 64 bits de uno de los siguientes sistemas operativos:</span><span class="sxs-lookup"><span data-stu-id="0bfc7-106">To run Lync Server 2013, Best Practices Analyzer to scan your environment, the computer must be running a 64-bit edition of one of the following operating systems:</span></span>

  - <span data-ttu-id="0bfc7-107">Sistema operativo Windows Server 2008 R2 con Service Pack 1 (SP1) Standard</span><span class="sxs-lookup"><span data-stu-id="0bfc7-107">Windows Server 2008 R2 with Service Pack 1 (SP1) Standard operating system</span></span>

  - <span data-ttu-id="0bfc7-108">Sistema operativo Windows Server 2008 R2 con SP1 Enterprise</span><span class="sxs-lookup"><span data-stu-id="0bfc7-108">Windows Server 2008 R2 with SP1 Enterprise operating system</span></span>

  - <span data-ttu-id="0bfc7-109">Sistema operativo Windows Server 2008 R2 con SP1 Datacenter</span><span class="sxs-lookup"><span data-stu-id="0bfc7-109">Windows Server 2008 R2 with SP1 Datacenter operating system</span></span>

  - <span data-ttu-id="0bfc7-110">Sistema operativo Windows Server 2012 Datacenter</span><span class="sxs-lookup"><span data-stu-id="0bfc7-110">Windows Server 2012 Datacenter operating system</span></span>

  - <span data-ttu-id="0bfc7-111">Sistema operativo Windows Server 2012 Standard</span><span class="sxs-lookup"><span data-stu-id="0bfc7-111">Windows Server 2012 Standard operating system</span></span>

  - <span data-ttu-id="0bfc7-112">Sistema operativo Windows Server 2012 Enterprise</span><span class="sxs-lookup"><span data-stu-id="0bfc7-112">Windows Server 2012 Enterprise operating system</span></span>

  - <span data-ttu-id="0bfc7-113">Sistema operativo Windows Server 2012 R2 Datacenter</span><span class="sxs-lookup"><span data-stu-id="0bfc7-113">Windows Server 2012 R2 Datacenter operating system</span></span>

  - <span data-ttu-id="0bfc7-114">Sistema operativo Windows Server 2012 R2 Standard</span><span class="sxs-lookup"><span data-stu-id="0bfc7-114">Windows Server 2012 R2 Standard operating system</span></span>

  - <span data-ttu-id="0bfc7-115">Sistema operativo Windows Server 2012 R2 Enterprise</span><span class="sxs-lookup"><span data-stu-id="0bfc7-115">Windows Server 2012 R2 Enterprise operating system</span></span>

  - <span data-ttu-id="0bfc7-116">Sistema operativo Windows 8</span><span class="sxs-lookup"><span data-stu-id="0bfc7-116">Windows 8 operating system</span></span>

  - <span data-ttu-id="0bfc7-117">Sistema operativo Windows 7</span><span class="sxs-lookup"><span data-stu-id="0bfc7-117">Windows 7 operating system</span></span>

<span data-ttu-id="0bfc7-118">El equipo también debe ejecutar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0bfc7-118">The computer must also be running the following:</span></span>

  - <span data-ttu-id="0bfc7-119">Microsoft .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="0bfc7-119">Microsoft .NET Framework 4.5.</span></span> <span data-ttu-id="0bfc7-120">Para Lync Server 2013, debe instalar manualmente la edición de 64 bits de Microsoft .NET Framework 4,5 en el servidor antes de instalar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0bfc7-120">For Lync Server 2013, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span>

  - <span data-ttu-id="0bfc7-121">Lync Server 2013, componentes principales.</span><span class="sxs-lookup"><span data-stu-id="0bfc7-121">Lync Server 2013, Core Components.</span></span>

  - <span data-ttu-id="0bfc7-122">Paquete de compatibilidad con versiones anteriores de WMI.</span><span class="sxs-lookup"><span data-stu-id="0bfc7-122">WMI Backward Compatibility Package.</span></span> <span data-ttu-id="0bfc7-123">Para obtener más información, consulte [instalar paquete de compatibilidad con versiones anteriores de WMI](install-wmi-backward-compatibility-package.md) en la documentación de migración.</span><span class="sxs-lookup"><span data-stu-id="0bfc7-123">For details, see [Install WMI Backward Compatibility package](install-wmi-backward-compatibility-package.md) in the Migration documentation.</span></span>

  - <span data-ttu-id="0bfc7-124">Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0bfc7-124">Windows PowerShell 3.0.</span></span> <span data-ttu-id="0bfc7-125">Para obtener más información, consulte [Installing Windows PowerShell 3,0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="0bfc7-125">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md) in the Deployment documentation.</span></span>

<span data-ttu-id="0bfc7-126">Puede instalar el analizador de procedimientos recomendados en equipos con un sistema operativo compatible que no ejecute Lync Server 2013, los componentes principales o el paquete de compatibilidad con versiones anteriores de WMI, pero puede usar el analizador de procedimientos recomendados en esos equipos solo para ver los informes, no para ejecutar los análisis.</span><span class="sxs-lookup"><span data-stu-id="0bfc7-126">You can install Best Practices Analyzer on computers with a supported operating system that are not running Lync Server 2013, Core Components or WMI Backward Compatibility Package, but you can use Best Practices Analyzer on those computers only to view reports, not to run scans.</span></span>

</div>

<div>

## <a name="choosing-a-computer-for-installation"></a><span data-ttu-id="0bfc7-127">Selección de un equipo para la instalación</span><span class="sxs-lookup"><span data-stu-id="0bfc7-127">Choosing a Computer for Installation</span></span>

<span data-ttu-id="0bfc7-128">Se recomienda instalar Lync Server 2013, Best Practices Analyzer en un equipo dedicado a la administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0bfc7-128">We recommend that you install Lync Server 2013, Best Practices Analyzer on a computer that is dedicated to Lync Server 2013 management.</span></span> <span data-ttu-id="0bfc7-129">Puede instalar la herramienta en un servidor que ejecute Lync Server 2013 o en un equipo administrativo en el que se ejecuten las herramientas administrativas de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0bfc7-129">You can install the tool on a server running Lync Server 2013 or an administrative computer running Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="0bfc7-130">Si instala la herramienta en un servidor que ejecuta Lync Server, le recomendamos que use la herramienta para analizar solo ese servidor.</span><span class="sxs-lookup"><span data-stu-id="0bfc7-130">If you install the tool on a server that is running Lync Server, we recommend that you use the tool to scan only that server.</span></span>

</div>

<div>

## <a name="installing-best-practices-analyzer"></a><span data-ttu-id="0bfc7-131">Instalación del Analizador de procedimientos recomendados</span><span class="sxs-lookup"><span data-stu-id="0bfc7-131">Installing Best Practices Analyzer</span></span>

<span data-ttu-id="0bfc7-132">Puede descargar el analizador de procedimientos recomendados para Lync Server 2013 en [https://go.microsoft.com/fwlink/p/?linkId=266539](https://go.microsoft.com/fwlink/p/?linkid=266539).</span><span class="sxs-lookup"><span data-stu-id="0bfc7-132">You can download the Best Practices Analyzer for Lync Server 2013 at [https://go.microsoft.com/fwlink/p/?linkId=266539](https://go.microsoft.com/fwlink/p/?linkid=266539).</span></span>

<span data-ttu-id="0bfc7-133">Para instalar el Analizador de procedimientos recomendados, inicie el archivo RtcBPA.msi de Microsoft Installer en el equipo donde desea instalar la herramienta y luego siga las instrucciones que aparecen en pantalla.</span><span class="sxs-lookup"><span data-stu-id="0bfc7-133">To install Best Practices Analyzer, start the Microsoft Installer file RtcBPA.msi on the computer where you want to install the tool, and then follow the instructions on the screen.</span></span> <span data-ttu-id="0bfc7-134">La ubicación predeterminada para instalar los archivos de programa \<es archivos\>\\\\de programa de unidad de\\sistema Lync Server 2013 BPA.</span><span class="sxs-lookup"><span data-stu-id="0bfc7-134">The default location for installing the program files is \<system drive\>\\Program Files\\Lync Server 2013\\BPA.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

