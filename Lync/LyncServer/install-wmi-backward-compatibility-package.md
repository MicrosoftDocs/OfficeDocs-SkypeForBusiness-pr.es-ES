---
title: Instalar el paquete de compatibilidad con versiones anteriores de WMI
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Install WMI Backward Compatibility package
ms:assetid: 38797fbd-06a0-4008-b099-158e7b5d7703
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204816(v=OCS.15)
ms:contentKeyID: 48183893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c59e3ea03b3b6f4085f8acf461b1da3f32e21fa9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199403"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-wmi-backward-compatibility-package"></a><span data-ttu-id="3b875-102">Instalar el paquete de compatibilidad con versiones anteriores de WMI</span><span class="sxs-lookup"><span data-stu-id="3b875-102">Install WMI Backward Compatibility package</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b875-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="3b875-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="3b875-104">Si intenta ejecutar el asistente de combinación del asistente para combinaciones del Generador de topologías sin instalar el paquete de compatibilidad con versiones anteriores de WMI, verá el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="3b875-104">If you attempt to run the Topology Builder Merge wizard without installing the WMI Backward Compatibility package, you will see the following error:</span></span>

<span data-ttu-id="3b875-105">![Mensaje de error de WMI](images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "Mensaje de error de WMI")</span><span class="sxs-lookup"><span data-stu-id="3b875-105">![WMI error message](images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "WMI error message")</span></span>

<span data-ttu-id="3b875-106">Si intenta ejecutar el cmdlet **Merge-CsLegacytopology** sin instalar el paquete de compatibilidad con versiones anteriores de WMI, verá el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="3b875-106">If you attempt to run the **Merge-CsLegacytopology** cmdlet without installing the WMI Backward Compatibility package, you will see the following error:</span></span>

<span data-ttu-id="3b875-107">![Error del proveedor WMI de Windows PowerShell](images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Error del proveedor WMI de Windows PowerShell")</span><span class="sxs-lookup"><span data-stu-id="3b875-107">![Windows PowerShell WMI Provider Error](images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Windows PowerShell WMI Provider Error")</span></span>

<span data-ttu-id="3b875-108">Para instalar el paquete de compatibilidad con versiones anteriores de WMI</span><span class="sxs-lookup"><span data-stu-id="3b875-108">To install the WMI Backward Compatibility Package</span></span>

1.  <span data-ttu-id="3b875-109">Desde los medios de instalación, vaya \\a\\Setup\\AMD64\\Setup OCSWMIBC. MS.</span><span class="sxs-lookup"><span data-stu-id="3b875-109">From your installation media, navigate to \\SETUP\\AMD64\\SETUP\\OCSWMIBC.MSI.</span></span>

2.  <span data-ttu-id="3b875-110">Instale OCSWMIBC.MSI.</span><span class="sxs-lookup"><span data-stu-id="3b875-110">Install OCSWMIBC.MSI.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3b875-p101">OCSWMIBC.msi debe instalarse en el equipo donde se ejecute el asistente de combinación del generador de topologías. Sin embargo, se recomienda instalar OCSWMIBC.msi en todos los servidores front-end de la topología.</span><span class="sxs-lookup"><span data-stu-id="3b875-p101">OCSWMIBC.msi must be installed on the computer where the Topology Builder Merge wizard is run. However, we recommend installing OCSWMIBC.msi on all Front End servers in your topology.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3b875-113">OCSWMIBC. msi puede instalarse en cualquier equipo del dominio que tenga instalados los componentes principales de Lync Server 2013 y el shell de administración de Lync Server 2013, y que tenga acceso a la topología de Office Communications Server 2007 R2 (proveedor de WMI al dominio de Active Directory). Servicios (AD DS) y SQL Server).</span><span class="sxs-lookup"><span data-stu-id="3b875-113">OCSWMIBC.msi can be installed on any computer in the domain that has the Lync Server 2013 Core Components and the Lync Server 2013 Management Shell installed, and has access to the Office Communications Server 2007 R2 topology (WMI provider to Active Directory Domain Services (AD DS) and SQL Server).</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

