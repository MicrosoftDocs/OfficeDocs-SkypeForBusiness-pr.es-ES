---
title: Instalar herramientas administrativas en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: 'Resumen: Conozca cómo instalar las herramientas administrativas necesarias para una instalación de Skype para Business Server 2015. Descargue una prueba gratuita de Skype para Business Server 2015 desde el centro de Evaluation de Microsoft en: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: e54dfd4b29f3947b58517007949922a5c1230d51
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="install-administrative-tools-in-skype-for-business-server-2015"></a><span data-ttu-id="529e7-104">Instalar herramientas administrativas en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="529e7-104">Install administrative tools in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="529e7-105">**Resumen:** Obtenga información acerca de cómo instalar las herramientas administrativas necesarias para una instalación de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="529e7-105">**Summary:** Learn how to install the administrative tools required for an installation of Skype for Business Server 2015.</span></span> <span data-ttu-id="529e7-106">Descargue una prueba gratuita de Skype para Business Server 2015 desde el centro de Evaluation de Microsoft en: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="529e7-106">Download a free trial of Skype for Business Server 2015 from the Microsoft Evaluation center at: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="529e7-107">Las herramientas administrativas incluyen el generador de topología y el Panel de Control.</span><span class="sxs-lookup"><span data-stu-id="529e7-107">The administrative tools include Topology Builder and the Control Panel.</span></span> <span data-ttu-id="529e7-108">Las herramientas administrativas deben instalarse en al menos un servidor en la topología o en una estación de trabajo de administración de 64 bits que ejecuta una versión de sistema operativo de Windows que es compatible con Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="529e7-108">The administrative tools must be installed on at least one server in the topology or a 64-bit management workstation running a Windows OS version that is supported for Skype for Business Server.</span></span> <span data-ttu-id="529e7-109">Puede realizar los pasos 1 a 5 en cualquier orden.</span><span class="sxs-lookup"><span data-stu-id="529e7-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="529e7-110">Sin embargo, debe realizar los pasos 6, 7 y 8 en orden y después los pasos del 1 al 5, tal como se indica en el diagrama.</span><span class="sxs-lookup"><span data-stu-id="529e7-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="529e7-111">Instalar las herramientas administrativas es el paso 3 de 8.</span><span class="sxs-lookup"><span data-stu-id="529e7-111">Installing the administrative tools is step 3 of 8.</span></span>
  
![Diagrama de información general](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-2015-administrative-tools"></a><span data-ttu-id="529e7-113">Instalar Skype para herramientas administrativas Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="529e7-113">Install Skype for Business Server 2015 administrative tools</span></span>

<span data-ttu-id="529e7-114">Los medios de instalación de Skype para Business Server 2015 proporcionan una experiencia flexible.</span><span class="sxs-lookup"><span data-stu-id="529e7-114">The installation media for Skype for Business Server 2015 provides a flexible experience.</span></span> <span data-ttu-id="529e7-115">Cuando ejecuta Setup.exe por primera vez, las únicas herramientas instaladas son el Skype para el Asistente para implementación de Business Server y el Skype para el Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="529e7-115">When you first run Setup.exe, the only tools installed are the Skype for Business Server Deployment Wizard and the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="529e7-116">Mediante el uso de estas dos herramientas, conocidas como componentes principales, puede continuar con el proceso de instalación, pero no proporcionan la funcionalidad principal para el Skype para el entorno de servidor empresarial general.</span><span class="sxs-lookup"><span data-stu-id="529e7-116">By using these two tools, known as Core Components, you can continue with the installation process, but they do not provide primary functionality for the overall Skype for Business Server environment.</span></span> <span data-ttu-id="529e7-117">El Asistente para la implementación se inicia automáticamente después de instalar los componentes principales.</span><span class="sxs-lookup"><span data-stu-id="529e7-117">The Deployment Wizard launches automatically after you install the Core Components.</span></span> <span data-ttu-id="529e7-118">La sección del Asistente de implementación titulado **Instalar herramientas administrativas** instala Skype para el generador de topología de servidor empresarial y Skype para Business Server Control Panel.</span><span class="sxs-lookup"><span data-stu-id="529e7-118">The section of the Deployment Wizard titled **Install Administrative Tools** installs Skype for Business Server Topology Builder and Skype for Business Server Control Panel.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="529e7-119">Cada Skype para entorno Business Server debe tener al menos un servidor con las herramientas administrativas instaladas.</span><span class="sxs-lookup"><span data-stu-id="529e7-119">Every Skype for Business Server environment must have at least one server with the administrative tools installed.</span></span> 
  
<span data-ttu-id="529e7-120">Vea los pasos del vídeo para **Instalar herramientas administrativas**:</span><span class="sxs-lookup"><span data-stu-id="529e7-120">Watch the video steps for **Install administrative tools**:</span></span>
  
![Su explorador no admite vídeo. Instale Microsoft Silverlight, Adobe Flash Player o Internet Explorer 9.](../../media/MSN_Video_Widget.gif)
  
### <a name="install-skype-for-business-server-2015-administrative-tools-from-the-deployment-wizard"></a><span data-ttu-id="529e7-123">Instalar Skype para Business Server 2015 herramientas administrativas desde el Asistente para implementación</span><span class="sxs-lookup"><span data-stu-id="529e7-123">Install Skype for Business Server 2015 administrative tools from the Deployment Wizard</span></span>

1. <span data-ttu-id="529e7-124">Inserte el Skype para los medios de instalación de Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="529e7-124">Insert the Skype for Business Server 2015 installation media.</span></span> <span data-ttu-id="529e7-125">Si la configuración no empieza automáticamente, haga doble clic en **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="529e7-125">If the setup does not automatically begin, double-click **Setup**.</span></span>
    
2. <span data-ttu-id="529e7-p107">La ejecución del disco de instalación necesita Microsoft Visual C++. Aparecerá un cuadro de diálogo preguntándole si quiere instalarlo. Haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="529e7-p107">The installation media requires Microsoft Visual C++ to run. A dialog box will pop up asking if you want to install it. Click **Yes**.</span></span>
    
3. <span data-ttu-id="529e7-129">De forma inteligente, una nueva característica de Skype para Business Server 2015, puede conectarse a Internet para buscar actualizaciones durante el proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="529e7-129">By using Smart Setup, a new feature in Skype for Business Server 2015, you can connect to the Internet to check for updates during the installation process.</span></span> <span data-ttu-id="529e7-130">Esto proporciona una mejor experiencia, ya que se asegura de que dispone de las actualizaciones más recientes del producto en el momento de la instalación.</span><span class="sxs-lookup"><span data-stu-id="529e7-130">This provides a better experience by making sure you have the most recent updates to the product at installation.</span></span> <span data-ttu-id="529e7-131">Haga clic en **Instalar** para empezar la instalación.</span><span class="sxs-lookup"><span data-stu-id="529e7-131">Click **Install** to begin the installation.</span></span>
    
4. <span data-ttu-id="529e7-132">Revise cuidadosamente el contrato de licencia y, si está de acuerdo, elija **Acepto los términos del Contrato de licencia** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="529e7-132">Carefully review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and click **OK**.</span></span>
    
5. <span data-ttu-id="529e7-133">El Skype para componentes de núcleo de 2015 Business Server se instalará en el servidor.</span><span class="sxs-lookup"><span data-stu-id="529e7-133">The Skype for Business Server 2015 Core Components will be installed on the server.</span></span> 
    
    <span data-ttu-id="529e7-134">Estos componentes incluyen lo siguiente, como se muestra en la figura.</span><span class="sxs-lookup"><span data-stu-id="529e7-134">The Core Components consist of the following, as shown in the figure.</span></span>
    
    ![Componentes principales de la pantalla Aplicaciones.](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
  - <span data-ttu-id="529e7-136">**Skype para el Asistente de implementación de Business Server 2015** Programa de implementación que proporciona una plataforma de lanzamiento para instalar los diferentes componentes de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="529e7-136">**Skype for Business Server 2015 Deployment Wizard** A deployment program that provides a launch pad for installing the various components of Skype for Business Server 2015.</span></span>
    
  - <span data-ttu-id="529e7-137">**Skype para el Shell de administración de negocio servidor 2015** Un programa de PowerShell preconfigurado que permite administración de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="529e7-137">**Skype for Business Server 2015 Management Shell** A preconfigured PowerShell program that allows for administration of Skype for Business Server 2015.</span></span>
    
    <span data-ttu-id="529e7-138">Una vez finalizada la instalación de los componentes principales, se iniciará automáticamente el Skype para el Asistente para implementación de Business Server 2015, como se muestra en la figura.</span><span class="sxs-lookup"><span data-stu-id="529e7-138">Once the installation of the Core Components is complete, the Skype for Business Server 2015 Deployment Wizard will automatically launch, as shown in the figure.</span></span> 
    
    ![Asistente de implementación del servidor de Skype Empresarial 2015](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. <span data-ttu-id="529e7-140">Además de los componentes principales, también necesitará instalar Skype para el generador de topología de Business Server 2015 y Skype para Panel de Control de Business Server 2015 en al menos un servidor en el entorno.</span><span class="sxs-lookup"><span data-stu-id="529e7-140">In addition to the Core Components, you will also need to install Skype for Business Server 2015 Topology Builder and Skype for Business Server 2015 Control Panel on at least one server in the environment.</span></span> <span data-ttu-id="529e7-141">Haga clic en **Instalar herramientas administrativas** en el Asistente para la implementación.</span><span class="sxs-lookup"><span data-stu-id="529e7-141">Click **Install Administrative Tools** on the Deployment Wizard.</span></span>
    
7. <span data-ttu-id="529e7-142">Haga clic en **Siguiente** para empezar la instalación.</span><span class="sxs-lookup"><span data-stu-id="529e7-142">Click **Next** to begin the installation.</span></span>
    
8. <span data-ttu-id="529e7-p110">Una vez que se completa la instalación, haga clic en **Finalizar**. Ahora, como se ve en la figura, se agregan las herramientas administrativas en el servidor.</span><span class="sxs-lookup"><span data-stu-id="529e7-p110">Once the installation has completed, click **Finish**. The administrative tools are now added to the server, as shown in the figure.</span></span>
    
    ![Herramientas administrativas del servidor de Skype Empresarial 2015](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - <span data-ttu-id="529e7-146">**Skype para el generador de topología Business Server 2015** Un programa utilizado para generar, implementar y administrar topologías.</span><span class="sxs-lookup"><span data-stu-id="529e7-146">**Skype for Business Server 2015 Topology Builder** A program used to build, deploy, and manage topologies.</span></span>
    
   - <span data-ttu-id="529e7-147">**Skype para Panel de Control de Business Server 2015** Un programa que se utiliza para administrar la instalación.</span><span class="sxs-lookup"><span data-stu-id="529e7-147">**Skype for Business Server 2015 Control Panel** A program used to administer the installation.</span></span>
    

