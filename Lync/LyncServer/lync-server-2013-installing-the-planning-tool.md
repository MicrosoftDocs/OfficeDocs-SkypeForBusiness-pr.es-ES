---
title: 'Lync Server 2013: instalar la herramienta de planeación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Planning Tool
ms:assetid: ebdc9e26-4b22-4b02-85b9-7462bcfe7c93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615046(v=OCS.15)
ms:contentKeyID: 51541525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 792f72daac7eb1d7edb10087256bfda0912edfe9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006176"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-planning-tool-in-lync-server-2013"></a><span data-ttu-id="baf09-102">Instalar la herramienta de planeación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="baf09-102">Installing the Planning Tool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="baf09-103">_**Última modificación del tema:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="baf09-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="baf09-104">Antes de empezar a diseñar y planear la infraestructura de Lync Server 2013 mediante el uso de la herramienta de planeación de Microsoft Lync Server 2013, debe instalar primero la herramienta de planeación.</span><span class="sxs-lookup"><span data-stu-id="baf09-104">Before you begin designing and planning your Lync Server 2013 infrastructure by using the Microsoft Lync Server 2013, Planning Tool, you must first install the Planning Tool.</span></span> <span data-ttu-id="baf09-105">No es necesario implementar la herramienta de planeación en una estación de trabajo o servidor que forme parte del dominio o de la infraestructura donde tiene previsto instalar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="baf09-105">The Planning Tool does not need to be deployed to a workstation or server that is part of the domain or infrastructure where you plan to install Lync Server 2013.</span></span> <span data-ttu-id="baf09-106">El archivo Léame que acompaña a la herramienta de planeación detalla información importante sobre la instalación y el uso de la herramienta.</span><span class="sxs-lookup"><span data-stu-id="baf09-106">The Readme file that accompanies the Planning Tool details important information about installing and using the tool.</span></span> <span data-ttu-id="baf09-107">Alguna de la información del archivo Léame también aparece aquí por motivos de claridad.</span><span class="sxs-lookup"><span data-stu-id="baf09-107">Some of the information in the Readme file is duplicated here for clarity.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="baf09-108">La herramienta de Planeación requiere la instalación por parte de un usuario con permisos y derechos de administrador en el equipo en el que se va a instalar la herramienta.</span><span class="sxs-lookup"><span data-stu-id="baf09-108">The Planning Tool requires installation by a user with administrator rights and permissions on the computer on which the tool is to be installed.</span></span>



</div>

<span data-ttu-id="baf09-109">Los sistemas operativos compatibles para la instalación y el funcionamiento de la herramienta de planeación son:</span><span class="sxs-lookup"><span data-stu-id="baf09-109">The supported operating systems for installation and operation of the Planning Tool are:</span></span>

  - <span data-ttu-id="baf09-110">Windows 8</span><span class="sxs-lookup"><span data-stu-id="baf09-110">Windows 8</span></span>

  - <span data-ttu-id="baf09-111">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="baf09-111">Windows 8.1</span></span>

  - <span data-ttu-id="baf09-112">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="baf09-112">Windows Server 2012</span></span>

  - <span data-ttu-id="baf09-113">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="baf09-113">Windows Server 2012 R2</span></span>

  - <span data-ttu-id="baf09-114">Edición de 32 bits de Windows 7</span><span class="sxs-lookup"><span data-stu-id="baf09-114">Windows 7, 32-bit edition</span></span>

  - <span data-ttu-id="baf09-115">Edición de 64 bits de Windows 7 usando Windows en Win32 (WOW)</span><span class="sxs-lookup"><span data-stu-id="baf09-115">Windows 7, 64-bit edition using Windows on Win32 (WOW)</span></span>

  - <span data-ttu-id="baf09-116">Windows Server 2008 R2 usando WOW</span><span class="sxs-lookup"><span data-stu-id="baf09-116">Windows Server 2008 R2, using WOW</span></span>

<span data-ttu-id="baf09-117">Además, la herramienta de Planeación requiere Microsoft .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="baf09-117">Additionally, the Planning Tool requires Microsoft .NET Framework 4.5.</span></span>

<span data-ttu-id="baf09-118">Una vez cumplidos los requisitos de preinstalación, puede instalar la herramienta de planeación.</span><span class="sxs-lookup"><span data-stu-id="baf09-118">After the preinstallation requirements are met, you can then install the Planning Tool.</span></span>

<div>

## <a name="to-install-the-planning-tool"></a><span data-ttu-id="baf09-119">Para instalar la Herramienta de planeación</span><span class="sxs-lookup"><span data-stu-id="baf09-119">To install the Planning Tool</span></span>

1.  <span data-ttu-id="baf09-120">Inicie sesión en el equipo local como miembro del grupo Administradores.</span><span class="sxs-lookup"><span data-stu-id="baf09-120">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="baf09-121">Mediante el explorador de Windows o una ventana de comandos, busque el directorio donde descargó los archivos de instalación de la herramienta de planeación.</span><span class="sxs-lookup"><span data-stu-id="baf09-121">Using Windows Explorer or a command window, locate the directory where you downloaded the Planning Tool installation files.</span></span>

3.  <span data-ttu-id="baf09-122">Busque el archivo LyncPlanningTool.msi.</span><span class="sxs-lookup"><span data-stu-id="baf09-122">Locate the LyncPlanningTool.msi.</span></span> <span data-ttu-id="baf09-123">En el Explorador de Windows, haga doble clic en el archivo.</span><span class="sxs-lookup"><span data-stu-id="baf09-123">In Windows Explorer, double-click the file.</span></span> <span data-ttu-id="baf09-124">En la ventana de comandos, escriba el nombre del archivo y, a continuación, presione **entrar** para ejecutar el archivo.</span><span class="sxs-lookup"><span data-stu-id="baf09-124">In the command window, type the name of the file, and then press **Enter** to run the file.</span></span>

4.  <span data-ttu-id="baf09-125">En la Página principal del **Asistente para la instalación de la herramienta de planeación de Microsoft Lync Server 2013**, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="baf09-125">On the Welcome page of the **Microsoft Lync Server 2013, Planning Tool Setup Wizard**, click **Next**.</span></span>

5.  <span data-ttu-id="baf09-126">Lea el **Contrato de licencia para el usuario final**, seleccione **Acepto los términos del contrato de licencia**, si quiere aceptar los términos de uso del contrato de licencia, y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="baf09-126">Review the **End-User License Agreement**, select **I accept the terms in the License Agreement** if you choose to accept the terms of use in the license agreement, and then click **Next**.</span></span>

6.  <span data-ttu-id="baf09-127">Elija donde quiere instalar los archivos de la Herramienta de planeación.</span><span class="sxs-lookup"><span data-stu-id="baf09-127">Choose where to install the Planning Tool files.</span></span> <span data-ttu-id="baf09-128">La ubicación predeterminada es C:\\archivos de programa (x86\\) Microsoft Lync Server\\2013 Planning Tool (en inglés).</span><span class="sxs-lookup"><span data-stu-id="baf09-128">The default location is C:\\Program Files (x86)\\Microsoft Lync Server 2013\\Planning Tool.</span></span> <span data-ttu-id="baf09-129">Si desea cambiar la ubicación de instalación, haga clic en **Cambiar**.</span><span class="sxs-lookup"><span data-stu-id="baf09-129">If you want to change the installation location, click **Change**.</span></span> <span data-ttu-id="baf09-130">En **Cambiar carpeta de destino**, busque o escriba la ubicación donde desea instalar los archivos; a continuación, haga clic en **Aceptar** y en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="baf09-130">On **Change destination folder**, browse or type the location to install the files, click **OK**, and then click **Next**.</span></span>

7.  <span data-ttu-id="baf09-131">El instalador ya está listo para instalar la herramienta de planeación.</span><span class="sxs-lookup"><span data-stu-id="baf09-131">The installer is now ready to install the Planning Tool.</span></span> <span data-ttu-id="baf09-132">Haga clic en **Instalar** para comenzar el proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="baf09-132">Click **Install** to begin the installation process.</span></span>

8.  <span data-ttu-id="baf09-133">La instalación se iniciará y se mostrará el progreso de la misma.</span><span class="sxs-lookup"><span data-stu-id="baf09-133">The installation will start, and the progress will be displayed.</span></span> <span data-ttu-id="baf09-134">Una vez completado el proceso de instalación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="baf09-134">After the installation is successfully completed, click **Finish**.</span></span>

9.  <span data-ttu-id="baf09-135">La herramienta de planeación está lista para usarse.</span><span class="sxs-lookup"><span data-stu-id="baf09-135">The Planning Tool is ready for use.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="baf09-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="baf09-136">See Also</span></span>


[<span data-ttu-id="baf09-137">Instalación de software opcional en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="baf09-137">Installing optional software in Lync Server 2013</span></span>](lync-server-2013-installing-optional-software.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

