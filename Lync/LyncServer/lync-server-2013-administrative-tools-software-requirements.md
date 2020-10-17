---
title: 'Lync Server 2013: requisitos de software para herramientas administrativas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administrative tools software requirements
ms:assetid: 2fb172c3-7b84-4e49-981c-2a17e7a00a29
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195653(v=OCS.15)
ms:contentKeyID: 48183740
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7c7b08d22933947c2f8079a2713fd134feb4629
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509047"
---
# <a name="administrative-tools-software-requirements-in-lync-server-2013"></a><span data-ttu-id="64756-102">Requisitos de software de herramientas administrativas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64756-102">Administrative tools software requirements in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64756-103">_**Última modificación del tema:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="64756-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="64756-104">En este tema se describe el software necesario para instalar y usar las herramientas administrativas 2013 de Lync Server, además de los requisitos del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="64756-104">This topic describes the software required to install and use Lync Server 2013 administrative tools in addition to the operating system requirements.</span></span>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="64756-105">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="64756-105">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="64756-106">La edición de 64 bits de Microsoft .NET Framework 4,5 es necesaria para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="64756-106">The 64-bit edition of Microsoft .NET Framework 4.5 is required for Lync Server 2013.</span></span>

</div>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="64756-107">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="64756-107">Windows PowerShell 3.0</span></span>

<span data-ttu-id="64756-108">Windows PowerShell 3,0 es necesario para ejecutar cualquier componente de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="64756-108">Windows PowerShell 3.0 is required for running any component of Microsoft Lync Server 2013.</span></span> <span data-ttu-id="64756-109">Para obtener más información, consulte [Installing Windows PowerShell 3,0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span><span class="sxs-lookup"><span data-stu-id="64756-109">For more information, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

</div>

<div>

## <a name="windows-installer-version-45"></a><span data-ttu-id="64756-110">Windows Installer versión 4.5</span><span class="sxs-lookup"><span data-stu-id="64756-110">Windows Installer Version 4.5</span></span>

<span data-ttu-id="64756-111">Lync Server 2013 usa la tecnología de Windows Installer para instalar, desinstalar y mantener varios roles de servidor.</span><span class="sxs-lookup"><span data-stu-id="64756-111">Lync Server 2013 uses Windows Installer technology to install, uninstall, and maintain various server roles.</span></span> <span data-ttu-id="64756-112">Windows Installer versión 4.5 está disponible como un componente redistribuible para el sistema operativo Windows Server.</span><span class="sxs-lookup"><span data-stu-id="64756-112">Windows Installer version 4.5 is available as a redistributable component for the Windows Server operating system.</span></span> <span data-ttu-id="64756-113">Windows Installer 4,5 se incluye con Windows Server 2012 R2, Windows Server 2012 y Windows Server 2008 R2, lo que significa que no es necesario descargar la utilidad para todos los equipos que ejecuten Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="64756-113">Windows Installer 4.5 ships with Windows Server 2012 R2, Windows Server 2012, and Windows Server 2008 R2 meaning that you do not need to download the utility for any computer that is running Lync Server 2013.</span></span> <span data-ttu-id="64756-114">(Lync Server 2013 solo se puede instalar en equipos que ejecuten Windows Server 2012 R2, Windows Server 2012 o Windows Server 2008 R2).</span><span class="sxs-lookup"><span data-stu-id="64756-114">(Lync Server 2013 can only be installed on computers running Windows Server 2012 R2, Windows Server 2012 or Windows Server 2008 R2.)</span></span>

<span data-ttu-id="64756-115">Sin embargo, si desea instalar el shell de administración de Lync Server o el generador de topologías de Lync Server en una estación de trabajo de administrador, es posible que deba descargar Windows Installer 4,5.</span><span class="sxs-lookup"><span data-stu-id="64756-115">However, if you want to install Lync Server Management Shell or Lync Server Topology Builder on an administrator workstation you might need to download Windows Installer 4.5.</span></span> <span data-ttu-id="64756-116">Esta utilidad se suministra con Windows 7 y Windows 2008 R2, pero no con las versiones anteriores del sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="64756-116">That utility ships with Windows 7 and Windows 2008 R2 but not with any previous versions of the Windows operating system.</span></span> <span data-ttu-id="64756-117">Puede descargar Windows Installer 4,5 desde el centro de descarga de Microsoft en <https://go.microsoft.com/fwlink/p/?linkid=197395> .</span><span class="sxs-lookup"><span data-stu-id="64756-117">You can download Windows Installer 4.5 from the Microsoft Download Center at <https://go.microsoft.com/fwlink/p/?linkid=197395>.</span></span>

</div>

<div>

## <a name="microsoft-silverlight-5-browser-plug-in"></a><span data-ttu-id="64756-118">Complemento de explorador Microsoft Silverlight 5</span><span class="sxs-lookup"><span data-stu-id="64756-118">Microsoft Silverlight 5 browser plug-in</span></span>

<span data-ttu-id="64756-119">El panel de control de Lync Server 2013 es una herramienta basada en Web y requiere que instale la versión más reciente del complemento del explorador Microsoft Silverlight 5.</span><span class="sxs-lookup"><span data-stu-id="64756-119">Lync Server 2013 Control Panel is a web-based tool and requires that you install the latest version of Microsoft Silverlight 5 browser plug-in.</span></span> <span data-ttu-id="64756-120">Cuando inicie el panel de control de Lync Server 2013, si este software no está instalado o si hay instalada una versión anterior, el panel de control de Lync Server 2013 le pedirá que instale la versión requerida.</span><span class="sxs-lookup"><span data-stu-id="64756-120">When you start Lync Server 2013 Control Panel, if this software is not installed or if an earlier version is installed, Lync Server 2013 Control Panel prompts you to install the required version.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="64756-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="64756-121">See Also</span></span>


[<span data-ttu-id="64756-122">Compatibilidad del sistema operativo con el servidor y las herramientas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64756-122">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)  


[<span data-ttu-id="64756-123">Requisitos de infraestructura de herramientas administrativas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64756-123">Administrative tools infrastructure requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-infrastructure-requirements.md)  
[<span data-ttu-id="64756-124">Permisos y derechos de administrador necesarios para la instalación y administración de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64756-124">Administrator rights and permissions required for setup and administration of Lync Server 2013</span></span>](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

