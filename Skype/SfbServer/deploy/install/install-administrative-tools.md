---
title: Instalar herramientas administrativas en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: 'Resumen: Obtenga información sobre cómo instalar las herramientas administrativas necesarias para una instalación de Skype empresarial Server. Descargue una versión de prueba gratuita de Skype empresarial Server del centro de evaluación de Microsoft https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serveren:.'
ms.openlocfilehash: 27cda52612eef1259017250ebcc4669e45165229
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018271"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a><span data-ttu-id="ae64c-104">Instalar herramientas administrativas en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="ae64c-104">Install administrative tools in Skype for Business Server</span></span>
 
<span data-ttu-id="ae64c-105">**Resumen:** Obtenga información sobre cómo instalar las herramientas administrativas necesarias para una instalación de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="ae64c-105">**Summary:** Learn how to install the administrative tools required for an installation of Skype for Business Server.</span></span> <span data-ttu-id="ae64c-106">Descargue una versión de prueba gratuita de Skype empresarial Server del centro de evaluación de Microsoft [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)en:.</span><span class="sxs-lookup"><span data-stu-id="ae64c-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="ae64c-107">Las herramientas administrativas incluyen el generador de topologías y el panel de control.</span><span class="sxs-lookup"><span data-stu-id="ae64c-107">The administrative tools include Topology Builder and the Control Panel.</span></span> <span data-ttu-id="ae64c-108">Las herramientas administrativas deben instalarse en al menos un servidor de la topología o una estación de trabajo de administración de 64 bits que ejecute una versión de sistema operativo de Windows compatible con Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="ae64c-108">The administrative tools must be installed on at least one server in the topology or a 64-bit management workstation running a Windows OS version that is supported for Skype for Business Server.</span></span> <span data-ttu-id="ae64c-109">Puede realizar los pasos del 1 al 5 en cualquier orden.</span><span class="sxs-lookup"><span data-stu-id="ae64c-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="ae64c-110">Sin embargo, debe realizar los pasos 6, 7 y 8 en orden, y después de los pasos del 1 al 5, tal y como se describe en el diagrama.</span><span class="sxs-lookup"><span data-stu-id="ae64c-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="ae64c-111">La instalación de las herramientas administrativas es el paso 3 de 8.</span><span class="sxs-lookup"><span data-stu-id="ae64c-111">Installing the administrative tools is step 3 of 8.</span></span>
  
![Diagrama de información general](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a><span data-ttu-id="ae64c-113">Instalar las herramientas administrativas de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="ae64c-113">Install Skype for Business Server administrative tools</span></span>

<span data-ttu-id="ae64c-114">Los medios de instalación de Skype empresarial Server proporcionan una experiencia flexible.</span><span class="sxs-lookup"><span data-stu-id="ae64c-114">The installation media for Skype for Business Server provides a flexible experience.</span></span> <span data-ttu-id="ae64c-115">La primera vez que se ejecuta Setup. exe, las únicas herramientas instaladas son el Asistente para la implementación de Skype empresarial Server y el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="ae64c-115">When you first run Setup.exe, the only tools installed are the Skype for Business Server Deployment Wizard and the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="ae64c-116">Mediante el uso de estas dos herramientas, conocidas como componentes principales, puede continuar con el proceso de instalación, pero no proporcionan funciones principales para el entorno general de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="ae64c-116">By using these two tools, known as Core Components, you can continue with the installation process, but they do not provide primary functionality for the overall Skype for Business Server environment.</span></span> <span data-ttu-id="ae64c-117">El Asistente para la implementación se inicia automáticamente después de instalar los componentes principales.</span><span class="sxs-lookup"><span data-stu-id="ae64c-117">The Deployment Wizard launches automatically after you install the Core Components.</span></span> <span data-ttu-id="ae64c-118">La sección del Asistente para la implementación titulada **instalar herramientas administrativas** instala el generador de topologías de Skype empresarial Server y el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="ae64c-118">The section of the Deployment Wizard titled **Install Administrative Tools** installs Skype for Business Server Topology Builder and Skype for Business Server Control Panel.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ae64c-119">Todos los entornos de Skype empresarial Server deben tener al menos un servidor con las herramientas administrativas instaladas.</span><span class="sxs-lookup"><span data-stu-id="ae64c-119">Every Skype for Business Server environment must have at least one server with the administrative tools installed.</span></span> 
  
<span data-ttu-id="ae64c-120">Vea los pasos del vídeo para **instalar herramientas administrativas**:</span><span class="sxs-lookup"><span data-stu-id="ae64c-120">Watch the video steps for **Install administrative tools**:</span></span>
  
> [!video https://www.microsoft.com/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a><span data-ttu-id="ae64c-121">Instalar las herramientas administrativas de Skype empresarial Server desde el Asistente para la implementación</span><span class="sxs-lookup"><span data-stu-id="ae64c-121">Install Skype for Business Server administrative tools from the Deployment Wizard</span></span>

1. <span data-ttu-id="ae64c-122">Inserte los medios de instalación de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="ae64c-122">Insert the Skype for Business Server installation media.</span></span> <span data-ttu-id="ae64c-123">Si el programa de instalación no se inicia automáticamente, haga doble clic en **setup**.</span><span class="sxs-lookup"><span data-stu-id="ae64c-123">If the setup does not automatically begin, double-click **Setup**.</span></span>
    
2. <span data-ttu-id="ae64c-124">El medio de instalación requiere que se ejecute Microsoft Visual C++.</span><span class="sxs-lookup"><span data-stu-id="ae64c-124">The installation media requires Microsoft Visual C++ to run.</span></span> <span data-ttu-id="ae64c-125">Aparecerá un cuadro de diálogo preguntándole si quiere instalarlo.</span><span class="sxs-lookup"><span data-stu-id="ae64c-125">A dialog box will pop up asking if you want to install it.</span></span> <span data-ttu-id="ae64c-126">Haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="ae64c-126">Click **Yes**.</span></span>
    
3. <span data-ttu-id="ae64c-127">Mediante el uso de la configuración inteligente, una nueva característica de Skype empresarial Server, puede conectarse a Internet para comprobar si hay actualizaciones durante el proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="ae64c-127">By using Smart Setup, a new feature in Skype for Business Server, you can connect to the Internet to check for updates during the installation process.</span></span> <span data-ttu-id="ae64c-128">Esto proporciona una mejor experiencia asegurándose de que tiene las actualizaciones más recientes del producto durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="ae64c-128">This provides a better experience by making sure you have the most recent updates to the product at installation.</span></span> <span data-ttu-id="ae64c-129">Haga clic en **Instalar** para comenzar el proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="ae64c-129">Click **Install** to begin the installation.</span></span>
    
4. <span data-ttu-id="ae64c-130">Revise atentamente el contrato de licencia y, si está de acuerdo, seleccione Acepto **los términos del contrato de licencia**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ae64c-130">Carefully review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and click **OK**.</span></span>
    
5. <span data-ttu-id="ae64c-131">Los componentes principales de Skype empresarial Server se instalarán en el servidor.</span><span class="sxs-lookup"><span data-stu-id="ae64c-131">The Skype for Business Server Core Components will be installed on the server.</span></span> 
    
    <span data-ttu-id="ae64c-132">Los componentes principales constan de lo siguiente, tal como se muestra en la figura.</span><span class="sxs-lookup"><span data-stu-id="ae64c-132">The Core Components consist of the following, as shown in the figure.</span></span>
    
    ![Componentes principales de la pantalla de aplicaciones.](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - <span data-ttu-id="ae64c-134">**Asistente para la implementación de Skype empresarial Server** Un programa de implementación que proporciona un panel de inicio para la instalación de los diversos componentes de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="ae64c-134">**Skype for Business Server Deployment Wizard** A deployment program that provides a launch pad for installing the various components of Skype for Business Server.</span></span>
    
   - <span data-ttu-id="ae64c-135">**Shell de administración de Skype empresarial Server** Un programa de PowerShell preconfigurado que permite la administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="ae64c-135">**Skype for Business Server Management Shell** A preconfigured PowerShell program that allows for administration of Skype for Business Server.</span></span>
    
     <span data-ttu-id="ae64c-136">Una vez completada la instalación de los componentes principales, se iniciará automáticamente el Asistente para la implementación de Skype empresarial Server, como se muestra en la figura.</span><span class="sxs-lookup"><span data-stu-id="ae64c-136">Once the installation of the Core Components is complete, the Skype for Business Server Deployment Wizard will automatically launch, as shown in the figure.</span></span> 
    
     ![Asistente para la implementación de Skype empresarial Server](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. <span data-ttu-id="ae64c-138">Además de los componentes principales, también tendrá que instalar el generador de topologías de Skype empresarial Server y el panel de control de Skype empresarial Server en al menos un servidor del entorno.</span><span class="sxs-lookup"><span data-stu-id="ae64c-138">In addition to the Core Components, you will also need to install Skype for Business Server Topology Builder and Skype for Business Server Control Panel on at least one server in the environment.</span></span> <span data-ttu-id="ae64c-139">Haga clic en **instalar herramientas administrativas** en el Asistente para la implementación.</span><span class="sxs-lookup"><span data-stu-id="ae64c-139">Click **Install Administrative Tools** on the Deployment Wizard.</span></span>
    
7. <span data-ttu-id="ae64c-140">Haga clic en **Siguiente** para comenzar la instalación.</span><span class="sxs-lookup"><span data-stu-id="ae64c-140">Click **Next** to begin the installation.</span></span>
    
8. <span data-ttu-id="ae64c-141">Una vez finalizada la instalación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="ae64c-141">Once the installation has completed, click **Finish**.</span></span> <span data-ttu-id="ae64c-142">Las herramientas administrativas se agregan ahora al servidor, como se muestra en la figura.</span><span class="sxs-lookup"><span data-stu-id="ae64c-142">The administrative tools are now added to the server, as shown in the figure.</span></span>
    
    ![Herramientas administrativas de Skype empresarial Server](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - <span data-ttu-id="ae64c-144">**Generador de topologías de Skype empresarial Server** Un programa que se usa para crear, implementar y administrar topologías.</span><span class="sxs-lookup"><span data-stu-id="ae64c-144">**Skype for Business Server Topology Builder** A program used to build, deploy, and manage topologies.</span></span>
    
   - <span data-ttu-id="ae64c-145">**Panel de control de Skype empresarial Server** Un programa usado para administrar la instalación.</span><span class="sxs-lookup"><span data-stu-id="ae64c-145">**Skype for Business Server Control Panel** A program used to administer the installation.</span></span>
    

