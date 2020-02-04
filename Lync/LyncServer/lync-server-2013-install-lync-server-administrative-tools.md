---
title: 'Lync Server 2013: Instalar las herramientas administrativas de Lync Server'
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
ms.openlocfilehash: 5ebdcf355618c4257ceaeced5f5e4032ede40cec
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763744"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-lync-server-2013-administrative-tools"></a><span data-ttu-id="e245d-102">Instalar las herramientas administrativas de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e245d-102">Install Lync Server 2013 administrative tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e245d-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="e245d-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="e245d-104">En este tema se describe cómo instalar las herramientas administrativas que necesita usar para implementar y administrar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e245d-104">This topic describes how to install the administrative tools you need to use to deploy and manage Lync Server 2013.</span></span> <span data-ttu-id="e245d-105">Las herramientas administrativas se instalan de forma predeterminada en todos los servidores que ejecutan Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e245d-105">The administrative tools are installed by default on each server running Lync Server 2013.</span></span> <span data-ttu-id="e245d-106">Además, puede instalar las herramientas administrativas en otros equipos, como consolas administrativas dedicadas.</span><span class="sxs-lookup"><span data-stu-id="e245d-106">Additionally, you can install the administrative tools on other computers, such as dedicated administrative consoles.</span></span> <span data-ttu-id="e245d-107">Le recomendamos encarecidamente que instale las herramientas administrativas en un equipo del mismo dominio o bosque que la implementación de Lync Server 2013 que está creando porque, de esta manera, tendrá que asegurarse de que los pasos de preparación de los servicios de dominio de Active Directory ya están completado, que le permite usar las herramientas administrativas en ese equipo más tarde para publicar su topología.</span><span class="sxs-lookup"><span data-stu-id="e245d-107">We strongly recommend that you install the administrative tools on a computer that is in the same domain or forest as the Lync Server 2013 deployment you are creating because by doing so you make sure that Active Directory Domain Services preparation steps are already complete, which enables you to use the administrative tools on that computer later to publish your topology.</span></span>

<span data-ttu-id="e245d-108">Asegúrese de revisar los requisitos de los derechos de infraestructura, sistema operativo, software y administrador antes de instalar o usar las herramientas administrativas de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e245d-108">Make sure that you review infrastructure, operating system, software, and administrator rights requirements before you install or use the Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="e245d-109">Para obtener más información sobre los requisitos de infraestructura, consulte [requisitos de infraestructura de herramientas administrativas en Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e245d-109">For details about infrastructure requirements, see [Administrative tools infrastructure requirements in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md).</span></span> <span data-ttu-id="e245d-110">Para obtener más información sobre los requisitos del sistema operativo y del software para instalar las herramientas administrativas de Lync Server 2013, consulte [compatibilidad del sistema operativo de servidor y herramientas en Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [requisitos de software adicionales para Lync Server 2013](lync-server-2013-additional-software-requirements.md), así como [requisitos y compatibilidad de servidor adicionales en Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e245d-110">For details about operating system and software requirements to install the Lync Server 2013 administrative tools, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md), and [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span></span> <span data-ttu-id="e245d-111">Para obtener más información sobre los derechos de usuario y los permisos necesarios para instalar y usar las herramientas, consulte [derechos y permisos de administrador necesarios para la configuración y administración de Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).</span><span class="sxs-lookup"><span data-stu-id="e245d-111">For details about the user rights and permissions required to install and use the tools, see [Administrator rights and permissions required for setup and administration of Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e245d-112">Si su organización requiere que encuentre Internet Information Services (IIS) y todos los servicios web en una unidad distinta de la del sistema, puede cambiar la ruta de acceso de la ubicación de instalación para los archivos de Lync Server en el cuadro de diálogo Configuración.</span><span class="sxs-lookup"><span data-stu-id="e245d-112">If your organization requires that you locate Internet Information Services (IIS) and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server files in the Setup dialog box.</span></span> <span data-ttu-id="e245d-113">Si instala los archivos de instalación en esta ruta de acceso, incluido OCSCore. msi, el resto de los archivos de Lync Server 2013 se implementarán también en esta unidad.</span><span class="sxs-lookup"><span data-stu-id="e245d-113">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive as well.</span></span>



</div>

<div>

## <a name="to-install-the-lync-server-2013-administrative-tools"></a><span data-ttu-id="e245d-114">Para instalar las herramientas administrativas 2013 de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e245d-114">To install the Lync Server 2013 administrative tools</span></span>

1.  <span data-ttu-id="e245d-115">Inicie sesión como administrador local (requisito mínimo) en el equipo en el que desea instalar las herramientas administrativas.</span><span class="sxs-lookup"><span data-stu-id="e245d-115">Log on as a local administrator (minimum requirement) to the computer where you want to install the administrative tools.</span></span> <span data-ttu-id="e245d-116">Si ha iniciado sesión como un usuario estándar en los sistemas operativos Windows Vista o Windows 7, y el control de cuentas de usuario (UAC) está habilitado, se le solicitará el administrador local o un nombre de usuario y una contraseña de dominio equivalente.</span><span class="sxs-lookup"><span data-stu-id="e245d-116">If you are logged on as an a standard user on the Windows Vista or Windows 7 operating systems, and User Account Control (UAC) is enabled, you will be prompted for the local administrator or a domain equivalent user name and password.</span></span>

2.  <span data-ttu-id="e245d-117">Busque los medios de instalación en el equipo y, a continuación, \\haga\\doble\\clic en Setup AMD64 Setup. exe.</span><span class="sxs-lookup"><span data-stu-id="e245d-117">Locate the installation media on your computer, and then double-click \\Setup\\amd64\\Setup.exe.</span></span>

3.  <span data-ttu-id="e245d-118">Si se le pide que instale el paquete distribuible de Microsoft Visual C++ 2008, haga clic en **sí**.</span><span class="sxs-lookup"><span data-stu-id="e245d-118">If you are prompted to install the Microsoft Visual C++ 2008 distributable, click **Yes**.</span></span>

4.  <span data-ttu-id="e245d-119">En la página **Ubicación de instalación de Microsoft Lync Server 2013** , haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e245d-119">On the **Microsoft Lync Server 2013 Installation Location** page, click **OK**.</span></span> <span data-ttu-id="e245d-120">Cambie esta ruta de acceso a otra ubicación o unidad si necesita tener los archivos instalados en otra ubicación.</span><span class="sxs-lookup"><span data-stu-id="e245d-120">Change this path to another location or drive if you need to have the files installed to another location.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e245d-121">Si su organización requiere que encuentre Internet Information Services (IIS) y todos los servicios web en una unidad distinta de la del sistema, puede cambiar la ruta de acceso de la ubicación de instalación para los archivos de Lync Server 2013 en el cuadro de diálogo de configuración.</span><span class="sxs-lookup"><span data-stu-id="e245d-121">If your organization requires that you locate Internet Information Services (IIS) and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server 2013 files in the Setup dialog box.</span></span> <span data-ttu-id="e245d-122">Si instala los archivos de instalación en esta ruta de acceso, incluido OCSCore. msi, el resto de los archivos de Lync Server 2013 se implementarán también en esta unidad.</span><span class="sxs-lookup"><span data-stu-id="e245d-122">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive too.</span></span>

    
    </div>

5.  <span data-ttu-id="e245d-123">En la página contrato de licencia para el **usuario final** , revise los términos de licencia **, haga clic en Acepto y**, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e245d-123">On the **End User License Agreement** page, review the license terms, click **I accept**, and then click **OK**.</span></span> <span data-ttu-id="e245d-124">Este paso es necesario para poder continuar.</span><span class="sxs-lookup"><span data-stu-id="e245d-124">This step is required before you can continue.</span></span>

6.  <span data-ttu-id="e245d-125">En la página **Microsoft Lync Server 2013: Asistente para la implementación** , haga clic en **instalar herramientas del administrador**.</span><span class="sxs-lookup"><span data-stu-id="e245d-125">On the **Microsoft Lync Server 2013 – Deployment Wizard** page, click **Install Administrator Tools**.</span></span>

7.  <span data-ttu-id="e245d-126">Cuando la instalación finalice correctamente, haga clic en **salir**.</span><span class="sxs-lookup"><span data-stu-id="e245d-126">When the installation successfully completes, click **Exit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e245d-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="e245d-127">See Also</span></span>


[<span data-ttu-id="e245d-128">Abrir las herramientas administrativas de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e245d-128">Open Lync Server 2013 administrative tools</span></span>](lync-server-2013-open-lync-server-administrative-tools.md)  


[<span data-ttu-id="e245d-129">Herramientas administrativas de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e245d-129">Lync Server 2013 administrative tools</span></span>](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

