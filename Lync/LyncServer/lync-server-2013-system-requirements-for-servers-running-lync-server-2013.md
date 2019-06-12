---
title: 'Lync Server 2013: Requisitos del sistema para servidores que ejecuten Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: System requirements for servers running Lync Server 2013
ms:assetid: 781d487d-5958-416a-becb-904d9af3cc0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398588(v=OCS.15)
ms:contentKeyID: 48184564
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ad30b9687c9566adb7936612e71ae9f41e69095
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850514"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="system-requirements-for-servers-running-lync-server-2013"></a><span data-ttu-id="4ebe1-102">Requisitos del sistema para servidores que ejecuten Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4ebe1-102">System requirements for servers running Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ebe1-103">_**Última modificación del tema:** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="4ebe1-103">_**Topic Last Modified:** 2014-07-24_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4ebe1-104">Para obtener más información sobre los requisitos de hardware, vea <A href="lync-server-2013-server-hardware-platforms.md">plataformas de hardware de servidor para Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="4ebe1-104">For details about hardware requirements, see <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="4ebe1-105">Los servidores Standard Edition y Enterprise Edition comparten los mismos requisitos de software.</span><span class="sxs-lookup"><span data-stu-id="4ebe1-105">Standard Edition and Enterprise Edition servers share the same software requirements.</span></span>

<span data-ttu-id="4ebe1-106">Los servidores que ejecutan Lync Server 2013, Enterprise Edition están pensados para organizaciones grandes como la implementación de la organización principal.</span><span class="sxs-lookup"><span data-stu-id="4ebe1-106">Servers running Lync Server 2013, Enterprise Edition are intended for large organizations as the main organizational deployment.</span></span> <span data-ttu-id="4ebe1-107">El servidor Enterprise Edition está diseñado para escalar a unos 80.000 usuarios alojados por cada grupo.</span><span class="sxs-lookup"><span data-stu-id="4ebe1-107">Enterprise Edition server is designed to scale to approximately 80,000 homed users per pool.</span></span> <span data-ttu-id="4ebe1-108">Los servidores que ejecutan Lync Server 2013, Standard Edition están pensados para organizaciones más pequeñas y ubicaciones remotas de la implementación de la organización principal.</span><span class="sxs-lookup"><span data-stu-id="4ebe1-108">Servers running Lync Server 2013, Standard Edition are intended for smaller organizations and remote locations from the main organization deployment.</span></span> <span data-ttu-id="4ebe1-109">Un par de servidores Standard Edition puede admitir hasta 5.000 usuarios..</span><span class="sxs-lookup"><span data-stu-id="4ebe1-109">One pair of Standard Edition servers can support up to 5,000 users..</span></span> <span data-ttu-id="4ebe1-110">Para obtener más información sobre las diferencias entre los servidores Standard Edition y los servidores Enterprise Edition, consulte [información general sobre la implementación de Lync Server 2013](lync-server-2013-deployment-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4ebe1-110">For details on the differences between Standard Edition servers and Enterprise Edition servers, see [Deployment overview for Lync Server 2013](lync-server-2013-deployment-overview.md).</span></span>

<div>

## <a name="operating-system-installation"></a><span data-ttu-id="4ebe1-111">Instalación del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="4ebe1-111">Operating System Installation</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4ebe1-112">Lync Server 2013 solo está disponible en una edición de 64 bits, que requiere hardware de 64 bits y una edición de 64 bits del sistema operativo Windows Server.</span><span class="sxs-lookup"><span data-stu-id="4ebe1-112">Lync Server 2013 is available only in a 64-bit edition, which requires 64-bit hardware and a 64-bit edition of the Windows Server operating system.</span></span> <span data-ttu-id="4ebe1-113">Una edición de 32 bits de Lync Server 2013 no está disponible en esta versión.</span><span class="sxs-lookup"><span data-stu-id="4ebe1-113">A 32-bit edition of Lync Server 2013 is not available with this release.</span></span>



</div>

<span data-ttu-id="4ebe1-114">El servidor Standard Edition y Enterprise Edition puede usar cualquiera de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="4ebe1-114">Standard Edition and Enterprise Edition server can use any of the following:</span></span>

  - <span data-ttu-id="4ebe1-115">Windows Server 2008 R2 SP1 o el Service Pack más reciente</span><span class="sxs-lookup"><span data-stu-id="4ebe1-115">Windows Server 2008 R2 SP1 or latest service pack</span></span>

  - <span data-ttu-id="4ebe1-116">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="4ebe1-116">Windows Server 2012</span></span>

  - <span data-ttu-id="4ebe1-117">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="4ebe1-117">Windows Server 2012 R2</span></span>

<span data-ttu-id="4ebe1-118">Instale el software del sistema operativo en el servidor Standard Edition o el servidor front-end Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="4ebe1-118">Install the operating system software on the Standard Edition Server or Enterprise Edition Front End Server.</span></span> <span data-ttu-id="4ebe1-119">Aplique todas las actualizaciones para llevar el sistema operativo al nivel de actualización más reciente y requisitos conforme a los estándares de la organización.</span><span class="sxs-lookup"><span data-stu-id="4ebe1-119">Apply all updates in order to bring the operating system up to the latest update and required update level consistent with your organization’s standards.</span></span> <span data-ttu-id="4ebe1-120">Para obtener más información sobre los requisitos operativos, vea [compatibilidad del sistema operativo servidor y herramientas en Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) en la documentación de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="4ebe1-120">For more details about the operating requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4ebe1-121">Para que Lync Server 2013 funcione en Windows Server 2012 R2, es posible que tenga que cambiar el valor de una clave del registro en Windows Server.</span><span class="sxs-lookup"><span data-stu-id="4ebe1-121">For Lync Server 2013 to work on Windows Server 2012 R2, you may need to change the value of a registry key in Windows Server.</span></span> <span data-ttu-id="4ebe1-122">Es posible que este cambio sea necesario para que los certificados funcionen correctamente y para que los clientes se registren con las aplicaciones de sucursales reactivas.</span><span class="sxs-lookup"><span data-stu-id="4ebe1-122">This change may be necessary for certificates to work correctly, and for clients to register with Survivable Branch Appliances.</span></span> <span data-ttu-id="4ebe1-123">Para obtener más información, <A class=uri href="http://support.microsoft.com/kb/2901554">http://support.microsoft.com/kb/2901554</A>consulte.</span><span class="sxs-lookup"><span data-stu-id="4ebe1-123">For more information, see <A class=uri href="http://support.microsoft.com/kb/2901554">http://support.microsoft.com/kb/2901554</A>.</span></span>



</div>

<div>

## <a name="additional-software-for-lync-server-2013"></a><span data-ttu-id="4ebe1-124">Software adicional para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4ebe1-124">Additional Software for Lync Server 2013</span></span>

<span data-ttu-id="4ebe1-125">Además de las actualizaciones necesarias para el sistema operativo, Lync Server 2013 requiere que los roles del sistema operativo, las características y el software funcionen.</span><span class="sxs-lookup"><span data-stu-id="4ebe1-125">In addition to the updates required for the operating system, Lync Server 2013 requires operating system roles, features, and software to operate.</span></span> <span data-ttu-id="4ebe1-126">Para obtener detalles sobre el software adicional que debe instalarse antes de publicar su Topología e instalar Lync Server 2013, consulte [requisitos de software adicionales para Lync Server 2013](lync-server-2013-additional-software-requirements.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="4ebe1-126">For details about the additional software that must be installed prior to publishing your topology and installing Lync Server 2013, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

</div>

</div>

<div>

## <a name="additional-software-necessary-for-all-server-roles"></a><span data-ttu-id="4ebe1-127">Software adicional necesario para todos los roles de servidor</span><span class="sxs-lookup"><span data-stu-id="4ebe1-127">Additional Software Necessary for All Server Roles</span></span>

<span data-ttu-id="4ebe1-128">En todos los roles de servidor, también debe asegurarse de que la interfaz de línea de comandos de Windows PowerShell 3,0 y Microsoft .NET Framework 4,5 estén instaladas.</span><span class="sxs-lookup"><span data-stu-id="4ebe1-128">On all server roles, you must also make sure that Windows PowerShell command-line interface 3.0 and Microsoft .NET Framework 4.5 are installed.</span></span>

<span data-ttu-id="4ebe1-129">Además, se necesita la interfaz de línea de comandos de Windows PowerShell 3,0 y Microsoft .NET Framework 4,5 en cualquier equipo donde se ejecuten las herramientas administrativas de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4ebe1-129">Additionally, Windows PowerShell command-line interface 3.0 and Microsoft .NET Framework 4.5 are required on any computer where you will run the Lync Server administrative tools.</span></span>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="4ebe1-130">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="4ebe1-130">Windows PowerShell 3.0</span></span>

<span data-ttu-id="4ebe1-131">Lync Server 2013 requiere instalar Windows PowerShell 3,0 en cada equipo que vaya a formar parte de la topología de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4ebe1-131">Lync Server 2013 requires you to install Windows PowerShell 3.0 on each computer that will take part in your Lync Server topology.</span></span> <span data-ttu-id="4ebe1-132">Para obtener más información sobre cómo instalar Windows PowerShell 3,0, consulte [instalar Windows powershell 3,0 para Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span><span class="sxs-lookup"><span data-stu-id="4ebe1-132">For details about installing Windows PowerShell 3.0, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4ebe1-133">En Windows Server&nbsp;2008&nbsp;R2 con SP1, no se puede instalar la interfaz de línea de comandos de Windows PowerShell 3,0 antes de instalar Microsoft .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="4ebe1-133">On Windows Server&nbsp;2008&nbsp;R2 with SP1, Windows PowerShell command-line interface 3.0 cannot be installed before installing Microsoft .NET Framework 4.5.</span></span>



</div>

</div>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="4ebe1-134">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="4ebe1-134">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="4ebe1-135">Al instalar Microsoft .NET Framework 4,5 en servidores que ejecutarán Lync Server 2013 en Windows Server 2012 o Windows Server 2012 R2, debe realizar un paso adicional.</span><span class="sxs-lookup"><span data-stu-id="4ebe1-135">When you install Microsoft .NET Framework 4.5 on servers that will run Lync Server 2013 on Windows Server 2012 or Windows Server 2012 R2, you must perform one additional step.</span></span> <span data-ttu-id="4ebe1-136">Después de instalar .NET Framework 4,5, use el administrador del servidor para instalar la activación de HTTP.</span><span class="sxs-lookup"><span data-stu-id="4ebe1-136">After .NET Framework 4.5 is installed, use Server Manager to install HTTP Activation.</span></span>

<span data-ttu-id="4ebe1-137">**Para instalar la activación HTTP de .NET 4,5 en Windows Server 2012 o Windows Server 2012 R2**</span><span class="sxs-lookup"><span data-stu-id="4ebe1-137">**To Install .NET 4.5 HTTP Activation on Windows Server 2012 or Windows Server 2012 R2**</span></span>

1.  <span data-ttu-id="4ebe1-138">En el menú **Inicio** , haga clic en **programas**y, a continuación, en **herramientas administrativas**y en **Administrador del servidor**.</span><span class="sxs-lookup"><span data-stu-id="4ebe1-138">From the **Start** menu, click **Programs**, then click **Administrative Tools**, then click **Server Manager**.</span></span>

2.  <span data-ttu-id="4ebe1-139">En Administrador del servidor, en **Resumen de características**, elija **Agregar características**.</span><span class="sxs-lookup"><span data-stu-id="4ebe1-139">In Server Manager, under **Features Summary**, choose **Add Features**.</span></span>

3.  <span data-ttu-id="4ebe1-140">Expanda **.NET Framework 4,5**.</span><span class="sxs-lookup"><span data-stu-id="4ebe1-140">Expand **.NET Framework 4.5**.</span></span>

4.  <span data-ttu-id="4ebe1-141">Seleccione **activación de WCF** si aún no está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="4ebe1-141">Select **WCF Activation** if it isn’t already selected.</span></span> <span data-ttu-id="4ebe1-142">Después, seleccione **activación http**.</span><span class="sxs-lookup"><span data-stu-id="4ebe1-142">Then select **HTTP Activation**.</span></span>

5.  <span data-ttu-id="4ebe1-143">Haga clic en **siguiente** y siga las indicaciones para finalizar la instalación.</span><span class="sxs-lookup"><span data-stu-id="4ebe1-143">Click **Next** and follow the prompts to finish the installation.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

