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
description: 'Resumen: Aprenda a instalar las herramientas administrativas necesarias para una instalación de Skype empresarial Server. Descargue una prueba gratuita de Skype empresarial Server en el centro de evaluación de Microsoft en https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server:.'
ms.openlocfilehash: 3abf2eb35a4593f25db75e175f3cd30fdf49e21b
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41790178"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a><span data-ttu-id="3f82c-104">Instalar herramientas administrativas en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="3f82c-104">Install administrative tools in Skype for Business Server</span></span>
 
<span data-ttu-id="3f82c-105">**Resumen:** Obtenga información sobre cómo instalar las herramientas administrativas necesarias para una instalación de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="3f82c-105">**Summary:** Learn how to install the administrative tools required for an installation of Skype for Business Server.</span></span> <span data-ttu-id="3f82c-106">Descargue una prueba gratuita de Skype empresarial Server en el centro de evaluación de Microsoft en [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server):.</span><span class="sxs-lookup"><span data-stu-id="3f82c-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="3f82c-107">Las herramientas administrativas incluyen Topology Builder y el panel de control.</span><span class="sxs-lookup"><span data-stu-id="3f82c-107">The administrative tools include Topology Builder and the Control Panel.</span></span> <span data-ttu-id="3f82c-108">Las herramientas administrativas deben instalarse en al menos un servidor de la topología o una estación de trabajo de administración de 64 bits que ejecute una versión de Windows del sistema operativo compatible con Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="3f82c-108">The administrative tools must be installed on at least one server in the topology or a 64-bit management workstation running a Windows OS version that is supported for Skype for Business Server.</span></span> <span data-ttu-id="3f82c-109">Puede realizar los pasos 1 a 5 en cualquier orden.</span><span class="sxs-lookup"><span data-stu-id="3f82c-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="3f82c-110">Sin embargo, debe realizar los pasos 6, 7 y 8 en orden, y después de los pasos 1 a 5, según se indica en el diagrama.</span><span class="sxs-lookup"><span data-stu-id="3f82c-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="3f82c-111">Instalar las herramientas administrativas es el paso 3 de 8.</span><span class="sxs-lookup"><span data-stu-id="3f82c-111">Installing the administrative tools is step 3 of 8.</span></span>
  
![Diagrama de información general](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a><span data-ttu-id="3f82c-113">Instalar las herramientas administrativas de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="3f82c-113">Install Skype for Business Server administrative tools</span></span>

<span data-ttu-id="3f82c-114">Los medios de instalación de Skype empresarial Server proporcionan una experiencia flexible.</span><span class="sxs-lookup"><span data-stu-id="3f82c-114">The installation media for Skype for Business Server provides a flexible experience.</span></span> <span data-ttu-id="3f82c-115">La primera vez que ejecute setup. exe, las únicas herramientas instaladas serán el Asistente para la implementación de Skype empresarial Server y el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="3f82c-115">When you first run Setup.exe, the only tools installed are the Skype for Business Server Deployment Wizard and the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="3f82c-116">Al usar estas dos herramientas, conocidas como componentes básicos, puede continuar con el proceso de instalación, pero no proporcionan la funcionalidad principal para el entorno general de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="3f82c-116">By using these two tools, known as Core Components, you can continue with the installation process, but they do not provide primary functionality for the overall Skype for Business Server environment.</span></span> <span data-ttu-id="3f82c-117">El Asistente para la implementación se inicia automáticamente después de instalar los componentes principales.</span><span class="sxs-lookup"><span data-stu-id="3f82c-117">The Deployment Wizard launches automatically after you install the Core Components.</span></span> <span data-ttu-id="3f82c-118">La sección del asistente de implementación titulada **instalar herramientas administrativas** instala el generador de topologías de Skype empresarial Server y el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="3f82c-118">The section of the Deployment Wizard titled **Install Administrative Tools** installs Skype for Business Server Topology Builder and Skype for Business Server Control Panel.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3f82c-119">Cada entorno de Skype empresarial Server debe tener al menos un servidor con las herramientas administrativas instaladas.</span><span class="sxs-lookup"><span data-stu-id="3f82c-119">Every Skype for Business Server environment must have at least one server with the administrative tools installed.</span></span> 
  
<span data-ttu-id="3f82c-120">Vea los pasos del vídeo para **Instalar herramientas administrativas**:</span><span class="sxs-lookup"><span data-stu-id="3f82c-120">Watch the video steps for **Install administrative tools**:</span></span>
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a><span data-ttu-id="3f82c-121">Instalar las herramientas administrativas de Skype empresarial Server desde el Asistente para la implementación</span><span class="sxs-lookup"><span data-stu-id="3f82c-121">Install Skype for Business Server administrative tools from the Deployment Wizard</span></span>

1. <span data-ttu-id="3f82c-122">Inserte los medios de instalación de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="3f82c-122">Insert the Skype for Business Server installation media.</span></span> <span data-ttu-id="3f82c-123">Si la configuración no empieza automáticamente, haga doble clic en **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="3f82c-123">If the setup does not automatically begin, double-click **Setup**.</span></span>
    
2. <span data-ttu-id="3f82c-p106">La ejecución del disco de instalación necesita Microsoft Visual C++. Aparecerá un cuadro de diálogo preguntándole si quiere instalarlo. Haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="3f82c-p106">The installation media requires Microsoft Visual C++ to run. A dialog box will pop up asking if you want to install it. Click **Yes**.</span></span>
    
3. <span data-ttu-id="3f82c-127">Al usar la configuración inteligente, una nueva característica de Skype empresarial Server, puede conectarse a Internet para comprobar si hay actualizaciones durante el proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="3f82c-127">By using Smart Setup, a new feature in Skype for Business Server, you can connect to the Internet to check for updates during the installation process.</span></span> <span data-ttu-id="3f82c-128">Esto proporciona una mejor experiencia, ya que se asegura de que dispone de las actualizaciones más recientes del producto en el momento de la instalación.</span><span class="sxs-lookup"><span data-stu-id="3f82c-128">This provides a better experience by making sure you have the most recent updates to the product at installation.</span></span> <span data-ttu-id="3f82c-129">Haga clic en **Instalar** para empezar la instalación.</span><span class="sxs-lookup"><span data-stu-id="3f82c-129">Click **Install** to begin the installation.</span></span>
    
4. <span data-ttu-id="3f82c-130">Revise cuidadosamente el contrato de licencia y, si está de acuerdo, elija **Acepto los términos del Contrato de licencia** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3f82c-130">Carefully review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and click **OK**.</span></span>
    
5. <span data-ttu-id="3f82c-131">Los componentes principales de Skype empresarial Server se instalarán en el servidor.</span><span class="sxs-lookup"><span data-stu-id="3f82c-131">The Skype for Business Server Core Components will be installed on the server.</span></span> 
    
    <span data-ttu-id="3f82c-132">Estos componentes incluyen lo siguiente, como se muestra en la figura.</span><span class="sxs-lookup"><span data-stu-id="3f82c-132">The Core Components consist of the following, as shown in the figure.</span></span>
    
    ![Componentes principales de la pantalla Aplicaciones.](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - <span data-ttu-id="3f82c-134">**Asistente para la implementación de Skype empresarial Server** Un programa de implementación que proporciona un Launch Pad para instalar los distintos componentes de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="3f82c-134">**Skype for Business Server Deployment Wizard** A deployment program that provides a launch pad for installing the various components of Skype for Business Server.</span></span>
    
   - <span data-ttu-id="3f82c-135">**Shell de administración de Skype empresarial Server** Un programa de PowerShell preconfigurado que permite la administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="3f82c-135">**Skype for Business Server Management Shell** A preconfigured PowerShell program that allows for administration of Skype for Business Server.</span></span>
    
     <span data-ttu-id="3f82c-136">Una vez completada la instalación de los componentes principales, el Asistente para la implementación de Skype empresarial Server se iniciará automáticamente, tal como se muestra en la ilustración.</span><span class="sxs-lookup"><span data-stu-id="3f82c-136">Once the installation of the Core Components is complete, the Skype for Business Server Deployment Wizard will automatically launch, as shown in the figure.</span></span> 
    
     ![Asistente para la implementación de Skype Empresarial Server](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. <span data-ttu-id="3f82c-138">Además de los componentes principales, también tendrá que instalar el generador de topologías de Skype empresarial Server y el panel de control de Skype empresarial Server en al menos un servidor del entorno.</span><span class="sxs-lookup"><span data-stu-id="3f82c-138">In addition to the Core Components, you will also need to install Skype for Business Server Topology Builder and Skype for Business Server Control Panel on at least one server in the environment.</span></span> <span data-ttu-id="3f82c-139">Haga clic en **Instalar herramientas administrativas** en el Asistente para la implementación.</span><span class="sxs-lookup"><span data-stu-id="3f82c-139">Click **Install Administrative Tools** on the Deployment Wizard.</span></span>
    
7. <span data-ttu-id="3f82c-140">Haga clic en **Siguiente** para empezar la instalación.</span><span class="sxs-lookup"><span data-stu-id="3f82c-140">Click **Next** to begin the installation.</span></span>
    
8. <span data-ttu-id="3f82c-p109">Una vez que se completa la instalación, haga clic en **Finalizar**. Ahora, como se ve en la figura, se agregan las herramientas administrativas en el servidor.</span><span class="sxs-lookup"><span data-stu-id="3f82c-p109">Once the installation has completed, click **Finish**. The administrative tools are now added to the server, as shown in the figure.</span></span>
    
    ![Herramientas administrativas de Skype empresarial Server](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - <span data-ttu-id="3f82c-144">**Generador de topologías de Skype empresarial Server** Un programa que se usa para generar, implementar y administrar topologías.</span><span class="sxs-lookup"><span data-stu-id="3f82c-144">**Skype for Business Server Topology Builder** A program used to build, deploy, and manage topologies.</span></span>
    
   - <span data-ttu-id="3f82c-145">**Panel de control de Skype empresarial Server** Un programa que se usa para administrar la instalación.</span><span class="sxs-lookup"><span data-stu-id="3f82c-145">**Skype for Business Server Control Panel** A program used to administer the installation.</span></span>
    

