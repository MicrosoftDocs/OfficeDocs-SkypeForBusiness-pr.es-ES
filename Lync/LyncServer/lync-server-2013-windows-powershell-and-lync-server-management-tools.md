---
title: 'Lync Server 2013: herramientas de administración de Windows PowerShell y Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell and Lync Server 2013 management tools
ms:assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481130(v=OCS.15)
ms:contentKeyID: 59893869
ms.date: 07/20/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c24a94bf74b2ecf911179d64691e95153acceeeb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210214"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="windows-powershell-and-lync-server-2013-management-tools"></a><span data-ttu-id="758a7-102">Herramientas de administración de Windows PowerShell y Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="758a7-102">Windows PowerShell and Lync Server 2013 management tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="758a7-103">_**Última modificación del tema:** 2016-07-20_</span><span class="sxs-lookup"><span data-stu-id="758a7-103">_**Topic Last Modified:** 2016-07-20_</span></span>

<span data-ttu-id="758a7-104">En Microsoft Lync Server 2013, las herramientas de administración se implementan con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="758a7-104">In Microsoft Lync Server 2013, management tools are implemented using Windows PowerShell.</span></span> <span data-ttu-id="758a7-105">Windows PowerShell incluye un entorno de línea de comandos, comandos específicos del producto y un lenguaje de scripting completo.</span><span class="sxs-lookup"><span data-stu-id="758a7-105">Windows PowerShell includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="758a7-106">Entre las herramientas de Lync Server 2013 que se implementan con Windows PowerShell se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="758a7-106">Lync Server 2013 tools that are implemented using Windows PowerShell include the following:</span></span>

  - <span data-ttu-id="758a7-107">**Generador de topologías**.</span><span class="sxs-lookup"><span data-stu-id="758a7-107">**Topology Builder**.</span></span> <span data-ttu-id="758a7-108">Puede usar el generador de topologías para crear, ajustar y publicar la topología planeada, así como validar la topología antes de comenzar con las instalaciones del servidor.</span><span class="sxs-lookup"><span data-stu-id="758a7-108">You use Topology Builder to create, adjust, and publish your planned topology, and it validates your topology before you begin server installations.</span></span> <span data-ttu-id="758a7-109">Al instalar Lync Server 2013 en servidores individuales, los servidores leen la topología publicada como parte del proceso de instalación y el programa de instalación implementa el servidor tal como se indicó en la topología.</span><span class="sxs-lookup"><span data-stu-id="758a7-109">When you install Lync Server 2013 on individual servers, the servers read the published topology as part of the installation process, and the installation program deploys the server as directed in the topology.</span></span> <span data-ttu-id="758a7-110">Después de la instalación, la información de configuración se replica automáticamente en todos los servidores.</span><span class="sxs-lookup"><span data-stu-id="758a7-110">After setup, configuration information is automatically replicated to all servers.</span></span> <span data-ttu-id="758a7-111">Los componentes se pueden agregar a la implementación solo mediante el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="758a7-111">Components can be added to your deployment only by using Topology Builder.</span></span>

  - <span data-ttu-id="758a7-112">**Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="758a7-112">**Lync Server Management Shell**.</span></span> <span data-ttu-id="758a7-113">Puede usar el shell de administración de Lync Server para la administración de la línea de comandos completa de la implementación.</span><span class="sxs-lookup"><span data-stu-id="758a7-113">You can use Lync Server Management Shell for full command-line management of your deployment.</span></span>

  - <span data-ttu-id="758a7-114">**Panel de control de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="758a7-114">**Lync Server Control Panel**.</span></span> <span data-ttu-id="758a7-115">Puede usar la interfaz de usuario del panel de control de Microsoft Lync Server 2013 para administrar las tareas más comunes en su implementación.</span><span class="sxs-lookup"><span data-stu-id="758a7-115">You can use the Microsoft Lync Server 2013 Control Panel user interface to manage the most common tasks in your deployment.</span></span>

<span data-ttu-id="758a7-116">Estas herramientas usan los cmdlets de Windows PowerShell para la administración de la implementación, incluidos los cmdlets cercanos a 550 específicos del producto.</span><span class="sxs-lookup"><span data-stu-id="758a7-116">These tools use Windows PowerShell cmdlets for management of your deployment, including close to 550 product-specific cmdlets.</span></span> <span data-ttu-id="758a7-117">Los cmdlets de seguridad incluidos en Lync Server 2013 se usan principalmente para administrar la autenticación y los permisos y derechos de usuario.</span><span class="sxs-lookup"><span data-stu-id="758a7-117">The security cmdlets included in Lync Server 2013 are primarily used to manage authentication, and user rights and permissions.</span></span> <span data-ttu-id="758a7-118">Hay una gran variedad de cmdlets para administrar la autenticación, por ejemplo cmdlets para certificado y autenticación del PIN.</span><span class="sxs-lookup"><span data-stu-id="758a7-118">A wide variety of cmdlets are available for managing authentication, including cmdlets for certificate and personal identification number (PIN) authentication.</span></span> <span data-ttu-id="758a7-119">Además, una serie de cmdlets le permiten usar la nueva característica de control de acceso basado en roles (RBAC) para delegar el control administrativo de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="758a7-119">In addition, a number of cmdlets enable you to use the new Role-Based Access Control (RBAC) feature to delegate administrative control of Lync Server 2013.</span></span> <span data-ttu-id="758a7-120">Para obtener más información sobre los cmdlets de Lync Server, consulte [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="758a7-120">For details about the Lync Server cmdlets, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span></span>

<span data-ttu-id="758a7-121">Las características de seguridad de scripts de Windows PowerShell están diseñadas específicamente para ayudar a evitar algunos de los problemas de seguridad relacionados con las secuencias de comandos de tecnologías anteriores, como Microsoft Visual Basic Scripting Edition (VBScript).</span><span class="sxs-lookup"><span data-stu-id="758a7-121">The script security features for Windows PowerShell are specifically designed to help prevent some of the scripting-related security problems of older technologies, including Microsoft Visual Basic Scripting Edition (VBScript).</span></span> <span data-ttu-id="758a7-122">Las características de seguridad de Windows PowerShell están pensadas para crear un entorno en el que los usuarios no puedan ejecutar scripts fácilmente o sin saberlo.</span><span class="sxs-lookup"><span data-stu-id="758a7-122">The Windows PowerShell security features are intended to create an environment in which users cannot easily or unknowingly run scripts.</span></span> <span data-ttu-id="758a7-123">De forma predeterminada, las características de seguridad de Windows PowerShell están habilitadas.</span><span class="sxs-lookup"><span data-stu-id="758a7-123">By default, Windows PowerShell security features are enabled.</span></span> <span data-ttu-id="758a7-124">Puede modificar el estado de esas características para adaptarlo a sus necesidades de scripting y a una variedad de objetivos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="758a7-124">You can modify the state of those features to accommodate your scripting needs and a variety of security goals.</span></span> <span data-ttu-id="758a7-125">Esto no quiere decir que el shell impida a los usuarios ejecutar scripts.</span><span class="sxs-lookup"><span data-stu-id="758a7-125">This is not to say that the shell makes it impossible for users to run scripts.</span></span> <span data-ttu-id="758a7-126">En su lugar, el shell dificulta (de forma predeterminada) que los usuarios ejecuten scripts sin darse cuenta de que lo hacen.</span><span class="sxs-lookup"><span data-stu-id="758a7-126">Rather, the shell makes it difficult—by default—for users to run scripts without realizing they are doing so.</span></span> <span data-ttu-id="758a7-127">Para obtener más información, consulte Seguridad de scripts de Windows PowerShell en [https://go.microsoft.com/fwlink/p/?LinkId=213145](https://go.microsoft.com/fwlink/p/?linkid=213145).</span><span class="sxs-lookup"><span data-stu-id="758a7-127">For details, see Windows PowerShell Script Security at [https://go.microsoft.com/fwlink/p/?LinkId=213145](https://go.microsoft.com/fwlink/p/?linkid=213145).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

