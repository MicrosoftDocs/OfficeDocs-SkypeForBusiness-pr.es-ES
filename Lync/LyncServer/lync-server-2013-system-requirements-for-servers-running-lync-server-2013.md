---
title: 'Lync Server 2013: requisitos del sistema para servidores que ejecutan Lync Server 2013'
description: 'Lync Server 2013: requisitos del sistema para servidores que ejecutan Lync Server 2013.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: System requirements for servers running Lync Server 2013
ms:assetid: 781d487d-5958-416a-becb-904d9af3cc0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398588(v=OCS.15)
ms:contentKeyID: 48184564
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b85940294e35a953d4ffb9c07bfdaba79141485
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562656"
---
# <a name="system-requirements-for-servers-running-lync-server-2013"></a><span data-ttu-id="98106-103">Requisitos del sistema para servidores que ejecutan Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98106-103">System requirements for servers running Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98106-104">_**Última modificación del tema:** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="98106-104">_**Topic Last Modified:** 2014-07-24_</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="98106-105">Para obtener más información sobre los requisitos de hardware, vea <A href="lync-server-2013-server-hardware-platforms.md">plataformas de hardware de servidor para Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="98106-105">For details about hardware requirements, see <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="98106-106">Los servidores Standard Edition y Enterprise Edition comparten los mismos requisitos de software.</span><span class="sxs-lookup"><span data-stu-id="98106-106">Standard Edition and Enterprise Edition servers share the same software requirements.</span></span>

<span data-ttu-id="98106-107">Los servidores que ejecutan Lync Server 2013, Enterprise Edition están pensados para grandes organizaciones como la implementación principal de la organización.</span><span class="sxs-lookup"><span data-stu-id="98106-107">Servers running Lync Server 2013, Enterprise Edition are intended for large organizations as the main organizational deployment.</span></span> <span data-ttu-id="98106-108">El servidor Enterprise Edition se ha diseñado para alcanzar una escala de, aproximadamente, 80.000 usuarios hospedados en cada grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="98106-108">Enterprise Edition server is designed to scale to approximately 80,000 homed users per pool.</span></span> <span data-ttu-id="98106-109">Los servidores que ejecutan Lync Server 2013, Standard Edition están pensados para organizaciones más pequeñas y ubicaciones remotas desde la implementación principal de la organización.</span><span class="sxs-lookup"><span data-stu-id="98106-109">Servers running Lync Server 2013, Standard Edition are intended for smaller organizations and remote locations from the main organization deployment.</span></span> <span data-ttu-id="98106-110">Un par de servidores Standard Edition puede admitir hasta 5.000 usuarios.</span><span class="sxs-lookup"><span data-stu-id="98106-110">One pair of Standard Edition servers can support up to 5,000 users..</span></span> <span data-ttu-id="98106-111">Para obtener más información sobre las diferencias entre los servidores Standard Edition y los servidores Enterprise Edition, consulte [información general sobre la implementación de Lync Server 2013](lync-server-2013-deployment-overview.md).</span><span class="sxs-lookup"><span data-stu-id="98106-111">For details on the differences between Standard Edition servers and Enterprise Edition servers, see [Deployment overview for Lync Server 2013](lync-server-2013-deployment-overview.md).</span></span>

<div>

## <a name="operating-system-installation"></a><span data-ttu-id="98106-112">Instalación del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="98106-112">Operating System Installation</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="98106-113">Lync Server 2013 solo está disponible en una edición de 64 bits, que requiere hardware de 64 bits y una edición de 64 bits del sistema operativo Windows Server.</span><span class="sxs-lookup"><span data-stu-id="98106-113">Lync Server 2013 is available only in a 64-bit edition, which requires 64-bit hardware and a 64-bit edition of the Windows Server operating system.</span></span> <span data-ttu-id="98106-114">Una edición de 32 bits de Lync Server 2013 no está disponible en esta versión.</span><span class="sxs-lookup"><span data-stu-id="98106-114">A 32-bit edition of Lync Server 2013 is not available with this release.</span></span>



</div>

<span data-ttu-id="98106-115">El servidor Standard Edition y Enterprise Edition puede usar cualquiera de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="98106-115">Standard Edition and Enterprise Edition server can use any of the following:</span></span>

  - <span data-ttu-id="98106-116">Windows Server 2008 R2 SP1 o el último Service Pack</span><span class="sxs-lookup"><span data-stu-id="98106-116">Windows Server 2008 R2 SP1 or latest service pack</span></span>

  - <span data-ttu-id="98106-117">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="98106-117">Windows Server 2012</span></span>

  - <span data-ttu-id="98106-118">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="98106-118">Windows Server 2012 R2</span></span>

<span data-ttu-id="98106-119">Instale el software del sistema operativo en el servidor Standard Edition o el servidor front-end Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="98106-119">Install the operating system software on the Standard Edition Server or Enterprise Edition Front End Server.</span></span> <span data-ttu-id="98106-120">Aplique todas las actualizaciones para dotar al sistema operativo de la versión más reciente y del nivel de actualización necesario que sea coherente con los estándares de su organización.</span><span class="sxs-lookup"><span data-stu-id="98106-120">Apply all updates in order to bring the operating system up to the latest update and required update level consistent with your organization’s standards.</span></span> <span data-ttu-id="98106-121">Para obtener más información sobre los requisitos operativos, consulte [compatibilidad con sistemas operativos de servidor y herramientas en Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) en la documentación sobre compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="98106-121">For more details about the operating requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

> [!NOTE] 
> <span data-ttu-id="98106-122">La actualización local del sistema operativo no es compatible con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="98106-122">In-place upgrade of the operating system is not supported with Lync Server 2013.</span></span>  <span data-ttu-id="98106-123">Debe implementar un grupo independiente y migrar los usuarios al nuevo grupo con un sistema operativo diferente.</span><span class="sxs-lookup"><span data-stu-id="98106-123">You must deploy a separate pool and migrate users to the new pool with a different operating system.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="98106-124">Para que Lync Server 2013 funcione en Windows Server 2012 R2, es posible que deba cambiar el valor de una clave del registro en Windows Server.</span><span class="sxs-lookup"><span data-stu-id="98106-124">For Lync Server 2013 to work on Windows Server 2012 R2, you may need to change the value of a registry key in Windows Server.</span></span> <span data-ttu-id="98106-125">Este cambio puede ser necesario para que los certificados funcionen correctamente y para que los clientes se registren con aplicaciones de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="98106-125">This change may be necessary for certificates to work correctly, and for clients to register with Survivable Branch Appliances.</span></span> <span data-ttu-id="98106-126">Para obtener más información, consulte <A class=uri href="https://support.microsoft.com/kb/2901554">https://support.microsoft.com/kb/2901554</A> .</span><span class="sxs-lookup"><span data-stu-id="98106-126">For more information, see <A class=uri href="https://support.microsoft.com/kb/2901554">https://support.microsoft.com/kb/2901554</A>.</span></span>



</div>

<div>

## <a name="additional-software-for-lync-server-2013"></a><span data-ttu-id="98106-127">Software adicional para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98106-127">Additional Software for Lync Server 2013</span></span>

<span data-ttu-id="98106-128">Además de las actualizaciones necesarias para el sistema operativo, Lync Server 2013 requiere funciones del sistema operativo, características y software para funcionar.</span><span class="sxs-lookup"><span data-stu-id="98106-128">In addition to the updates required for the operating system, Lync Server 2013 requires operating system roles, features, and software to operate.</span></span> <span data-ttu-id="98106-129">Para obtener información detallada sobre el software adicional que debe instalarse antes de publicar la topología e instalar Lync Server 2013, consulte [Additional software Requirements for Lync server 2013](lync-server-2013-additional-software-requirements.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="98106-129">For details about the additional software that must be installed prior to publishing your topology and installing Lync Server 2013, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

</div>

</div>

<div>

## <a name="additional-software-necessary-for-all-server-roles"></a><span data-ttu-id="98106-130">Software adicional necesario para todos los roles de servidor</span><span class="sxs-lookup"><span data-stu-id="98106-130">Additional Software Necessary for All Server Roles</span></span>

<span data-ttu-id="98106-131">En todos los roles de servidor, también debe asegurarse de que la interfaz de línea de comandos de Windows PowerShell 3,0 y Microsoft .NET Framework 4,5 estén instalados.</span><span class="sxs-lookup"><span data-stu-id="98106-131">On all server roles, you must also make sure that Windows PowerShell command-line interface 3.0 and Microsoft .NET Framework 4.5 are installed.</span></span>

<span data-ttu-id="98106-132">Además, se requiere la interfaz de línea de comandos 3,0 de Windows PowerShell y Microsoft .NET Framework 4,5 en cualquier equipo en el que vaya a ejecutar las herramientas administrativas de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="98106-132">Additionally, Windows PowerShell command-line interface 3.0 and Microsoft .NET Framework 4.5 are required on any computer where you will run the Lync Server administrative tools.</span></span>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="98106-133">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="98106-133">Windows PowerShell 3.0</span></span>

<span data-ttu-id="98106-134">Lync Server 2013 requiere la instalación de Windows PowerShell 3,0 en cada equipo que vaya a formar parte de la topología de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="98106-134">Lync Server 2013 requires you to install Windows PowerShell 3.0 on each computer that will take part in your Lync Server topology.</span></span> <span data-ttu-id="98106-135">Para más detalles sobre la instalación de Windows PowerShell 3,0, vea [Installing Windows powershell 3,0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span><span class="sxs-lookup"><span data-stu-id="98106-135">For details about installing Windows PowerShell 3.0, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="98106-136">En Windows Server &nbsp; 2008 &nbsp; R2 con SP1, la interfaz de línea de comandos de windows PowerShell 3,0 no se puede instalar antes de instalar Microsoft .net Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="98106-136">On Windows Server&nbsp;2008&nbsp;R2 with SP1, Windows PowerShell command-line interface 3.0 cannot be installed before installing Microsoft .NET Framework 4.5.</span></span>



</div>

</div>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="98106-137">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="98106-137">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="98106-138">Al instalar Microsoft .NET Framework 4,5 en servidores que ejecutarán Lync Server 2013 en Windows Server 2012 o Windows Server 2012 R2, debe realizar un paso adicional.</span><span class="sxs-lookup"><span data-stu-id="98106-138">When you install Microsoft .NET Framework 4.5 on servers that will run Lync Server 2013 on Windows Server 2012 or Windows Server 2012 R2, you must perform one additional step.</span></span> <span data-ttu-id="98106-139">Una vez instalado .NET Framework 4,5, use el administrador del servidor para instalar la activación HTTP.</span><span class="sxs-lookup"><span data-stu-id="98106-139">After .NET Framework 4.5 is installed, use Server Manager to install HTTP Activation.</span></span>

<span data-ttu-id="98106-140">**Para instalar la activación HTTP de .NET 4,5 en Windows Server 2012 o Windows Server 2012 R2**</span><span class="sxs-lookup"><span data-stu-id="98106-140">**To Install .NET 4.5 HTTP Activation on Windows Server 2012 or Windows Server 2012 R2**</span></span>

1.  <span data-ttu-id="98106-141">En el menú **Inicio** , haga clic en **programas**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Administrador de servidores**.</span><span class="sxs-lookup"><span data-stu-id="98106-141">From the **Start** menu, click **Programs**, then click **Administrative Tools**, then click **Server Manager**.</span></span>

2.  <span data-ttu-id="98106-142">En Administrador del servidor, en **Resumen de características**, elija **Agregar características**.</span><span class="sxs-lookup"><span data-stu-id="98106-142">In Server Manager, under **Features Summary**, choose **Add Features**.</span></span>

3.  <span data-ttu-id="98106-143">Expanda **.NET Framework 4,5**.</span><span class="sxs-lookup"><span data-stu-id="98106-143">Expand **.NET Framework 4.5**.</span></span>

4.  <span data-ttu-id="98106-144">Seleccione **activación de WCF** si aún no está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="98106-144">Select **WCF Activation** if it isn’t already selected.</span></span> <span data-ttu-id="98106-145">A continuación, seleccione **activación http**.</span><span class="sxs-lookup"><span data-stu-id="98106-145">Then select **HTTP Activation**.</span></span>

5.  <span data-ttu-id="98106-146">Haga clic en **siguiente** y siga las instrucciones para finalizar la instalación.</span><span class="sxs-lookup"><span data-stu-id="98106-146">Click **Next** and follow the prompts to finish the installation.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

