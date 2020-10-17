---
title: 'Lync Server 2013: instalar las herramientas administrativas de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Lync Server administrative tools
ms:assetid: 842b85e4-2eeb-464f-b1c1-ceb8cc04f8d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398665(v=OCS.15)
ms:contentKeyID: 48184695
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ded1dbdcd81c846db9f23574fa0b39efa0c33dc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498727"
---
# <a name="install-lync-server-2013-administrative-tools"></a><span data-ttu-id="c69ed-102">Instalación de las herramientas administrativas de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c69ed-102">Install Lync Server 2013 administrative tools</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c69ed-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="c69ed-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="c69ed-104">En este tema se describe cómo instalar las herramientas administrativas que necesita usar para implementar y administrar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c69ed-104">This topic describes how to install the administrative tools you need to use to deploy and manage Lync Server 2013.</span></span> <span data-ttu-id="c69ed-105">Las herramientas administrativas se instalan de forma predeterminada en todos los servidores que ejecutan Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c69ed-105">The administrative tools are installed by default on each server running Lync Server 2013.</span></span> <span data-ttu-id="c69ed-106">Además, puede instalar las herramientas administrativas en otros equipos, como consolas administrativas dedicadas.</span><span class="sxs-lookup"><span data-stu-id="c69ed-106">Additionally, you can install the administrative tools on other computers, such as dedicated administrative consoles.</span></span> <span data-ttu-id="c69ed-107">Se recomienda instalar las herramientas administrativas en un equipo que se encuentre en el mismo dominio o bosque que la implementación de Lync Server 2013 que está creando porque, al hacerlo, se asegura de que ya se hayan completado los pasos de preparación de los servicios de dominio de Active Directory, lo que le permite usar las herramientas administrativas en ese equipo más adelante para publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="c69ed-107">We strongly recommend that you install the administrative tools on a computer that is in the same domain or forest as the Lync Server 2013 deployment you are creating because by doing so you make sure that Active Directory Domain Services preparation steps are already complete, which enables you to use the administrative tools on that computer later to publish your topology.</span></span>

<span data-ttu-id="c69ed-108">Asegúrese de revisar los requisitos de la infraestructura, el sistema operativo, el software y los derechos de administrador antes de instalar o usar las herramientas administrativas de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c69ed-108">Make sure that you review infrastructure, operating system, software, and administrator rights requirements before you install or use the Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="c69ed-109">Para obtener más información acerca de los requisitos de infraestructura, consulte [Administrative Tools Infrastructure requirements in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c69ed-109">For details about infrastructure requirements, see [Administrative tools infrastructure requirements in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md).</span></span> <span data-ttu-id="c69ed-110">Para obtener más información sobre los requisitos del sistema operativo y del software para instalar las herramientas administrativas de Lync Server 2013, consulte [compatibilidad con sistemas operativos de servidor y herramientas en Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [requisitos de software adicionales para Lync Server 2013](lync-server-2013-additional-software-requirements.md)y [compatibilidad con servidores y requisitos adicionales en Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c69ed-110">For details about operating system and software requirements to install the Lync Server 2013 administrative tools, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md), and [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span></span> <span data-ttu-id="c69ed-111">Para obtener más información sobre los derechos de usuario y los permisos necesarios para instalar y usar las herramientas, consulte [derechos de administrador y permisos necesarios para la instalación y administración de Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).</span><span class="sxs-lookup"><span data-stu-id="c69ed-111">For details about the user rights and permissions required to install and use the tools, see [Administrator rights and permissions required for setup and administration of Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c69ed-112">Si su organización necesita que ubique Internet Information Services (IIS) y todos los servicios web en una unidad que no sea la unidad del sistema, debe cambiar la ruta de acceso a la ubicación de instalación de los archivos de Lync Server en el cuadro de diálogo de instalación.</span><span class="sxs-lookup"><span data-stu-id="c69ed-112">If your organization requires that you locate Internet Information Services (IIS) and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server files in the Setup dialog box.</span></span> <span data-ttu-id="c69ed-113">Si instala los archivos de instalación en esta ruta de acceso, incluido OCSCore.msi, también se implementará el resto de los archivos de Lync Server 2013 en esta unidad.</span><span class="sxs-lookup"><span data-stu-id="c69ed-113">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive as well.</span></span>



</div>

<div>

## <a name="to-install-the-lync-server-2013-administrative-tools"></a><span data-ttu-id="c69ed-114">Para instalar las herramientas administrativas de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c69ed-114">To install the Lync Server 2013 administrative tools</span></span>

1.  <span data-ttu-id="c69ed-p104">Inicie sesión como administrador local (requisito mínimo) en el equipo donde desee instalar las herramientas administrativas. Si ha iniciado la sesión como usuario estándar en los sistemas operativos Windows Vista o Windows 7 y está habilitado el control de cuenta de usuarios (UAC), se le pedirá que indique el administrador local o un nombre de usuario equivalente del dominio y una contraseña.</span><span class="sxs-lookup"><span data-stu-id="c69ed-p104">Log on as a local administrator (minimum requirement) to the computer where you want to install the administrative tools. If you are logged on as an a standard user on the Windows Vista or Windows 7 operating systems, and User Account Control (UAC) is enabled, you will be prompted for the local administrator or a domain equivalent user name and password.</span></span>

2.  <span data-ttu-id="c69ed-117">Busque los medios de instalación en el equipo y, a continuación, haga doble clic en \\ configuración \\ AMD64 \\Setup.exe.</span><span class="sxs-lookup"><span data-stu-id="c69ed-117">Locate the installation media on your computer, and then double-click \\Setup\\amd64\\Setup.exe.</span></span>

3.  <span data-ttu-id="c69ed-118">Si se le pide que instale Microsoft Visual C++ 2008 distribuible, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="c69ed-118">If you are prompted to install the Microsoft Visual C++ 2008 distributable, click **Yes**.</span></span>

4.  <span data-ttu-id="c69ed-119">En la página **Ubicación de instalación de Microsoft Lync Server 2013** , haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c69ed-119">On the **Microsoft Lync Server 2013 Installation Location** page, click **OK**.</span></span> <span data-ttu-id="c69ed-120">Cambie esta ruta de acceso a otra ubicación o unidad si necesita que los archivos se instalen en una ubicación diferente.</span><span class="sxs-lookup"><span data-stu-id="c69ed-120">Change this path to another location or drive if you need to have the files installed to another location.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c69ed-121">Si su organización requiere Internet Information Services (IIS) y todos los servicios web en una unidad distinta de la unidad del sistema, puede cambiar la ruta de acceso de la ubicación de instalación para los archivos de Lync Server 2013 en el cuadro de diálogo de configuración.</span><span class="sxs-lookup"><span data-stu-id="c69ed-121">If your organization requires that you locate Internet Information Services (IIS) and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server 2013 files in the Setup dialog box.</span></span> <span data-ttu-id="c69ed-122">Si instala los archivos de instalación en esta ruta de acceso, incluido OCSCore.msi, el resto de los archivos de Lync Server 2013 se implementarán también en esta unidad.</span><span class="sxs-lookup"><span data-stu-id="c69ed-122">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive too.</span></span>

    
    </div>

5.  <span data-ttu-id="c69ed-p107">En la página **Contrato de licencia para el usuario final**, revise los términos de la licencia, haga clic en **Acepto** y, a continuación, haga clic en **Aceptar**. Este paso es necesario para poder continuar</span><span class="sxs-lookup"><span data-stu-id="c69ed-p107">On the **End User License Agreement** page, review the license terms, click **I accept**, and then click **OK**. This step is required before you can continue.</span></span>

6.  <span data-ttu-id="c69ed-125">En la página **Microsoft Lync Server 2013 – Asistente para la implementación** , haga clic en **instalar herramientas del administrador**.</span><span class="sxs-lookup"><span data-stu-id="c69ed-125">On the **Microsoft Lync Server 2013 – Deployment Wizard** page, click **Install Administrator Tools**.</span></span>

7.  <span data-ttu-id="c69ed-126">Cuando finalice la instalación correctamente, haga clic en **Salir**.</span><span class="sxs-lookup"><span data-stu-id="c69ed-126">When the installation successfully completes, click **Exit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c69ed-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c69ed-127">See Also</span></span>


[<span data-ttu-id="c69ed-128">Abrir las herramientas administrativas de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c69ed-128">Open Lync Server 2013 administrative tools</span></span>](lync-server-2013-open-lync-server-administrative-tools.md)  


[<span data-ttu-id="c69ed-129">Herramientas administrativas de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c69ed-129">Lync Server 2013 administrative tools</span></span>](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

