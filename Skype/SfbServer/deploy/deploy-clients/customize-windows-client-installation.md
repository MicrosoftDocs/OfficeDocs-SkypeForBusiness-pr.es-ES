---
title: Personalizar la instalación de cliente de Windows en Skype para Business Server 2015
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 10/20/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
description: 'Resumen: Visión general de los métodos de instalación y las herramientas de Skype para empresas.'
ms.openlocfilehash: 8f74f3930e296d8f49eca4bf2a097c88883d7981
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="customize-windows-client-installation-in-skype-for-business-server-2015"></a><span data-ttu-id="1c301-103">Personalizar la instalación de cliente de Windows en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="1c301-103">Customize Windows client installation in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="1c301-104">**Resumen:** Visión general de los métodos de instalación y las herramientas de Skype para empresas.</span><span class="sxs-lookup"><span data-stu-id="1c301-104">**Summary:** Overview of installation methods and tools for Skype for Business.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1c301-105">Para obtener información de instalación acerca de Skype para el negocio que viene con Office 365, vea [implementar el Skype para cliente de negocio de Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span><span class="sxs-lookup"><span data-stu-id="1c301-105">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span> 
  
<span data-ttu-id="1c301-106">Los administradores de empresa pueden personalizar la instalación basada en Windows Installer (.msi) de las versiones de licencia por volumen de Skype para el negocio mediante el uso de los métodos descritos en esta sección.</span><span class="sxs-lookup"><span data-stu-id="1c301-106">Enterprise administrators can customize the Windows Installer-based (.msi) installation of volume licensed versions of Skype for Business by using the methods discussed in this section.</span></span> <span data-ttu-id="1c301-107">Debido a que ninguna herramienta única proporciona todas las opciones de personalización, probablemente utilizará una combinación de estos métodos en su Skype para implementación en la empresa.</span><span class="sxs-lookup"><span data-stu-id="1c301-107">Because no single tool provides all customization options, you'll likely use a combination of these methods in your Skype for Business deployment.</span></span> <span data-ttu-id="1c301-108">Puede usar las herramientas que se describen en las secciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="1c301-108">You might use the tools described in the following sections:</span></span>
  
- <span data-ttu-id="1c301-109">[Utilice la herramienta de personalización de Office (OCT) en Skype para Business Server 2015](use-the-office-customization-tool-oct.md) para personalizar opciones de configuración y características de Skype para empresas y otros programas de Office.</span><span class="sxs-lookup"><span data-stu-id="1c301-109">[Use the Office Customization Tool (OCT) in Skype for Business Server 2015](use-the-office-customization-tool-oct.md) to customize setup options and features for Skype for Business and other Office programs.</span></span>
    
- <span data-ttu-id="1c301-110">[Uso de Config.xml para realizar tareas de instalación de Skype para Business Server 2015](use-config-xml-to-perform-installation-tasks.md) para especificar la ruta de acceso del punto de instalación de red y realizar una instalación silenciosa.</span><span class="sxs-lookup"><span data-stu-id="1c301-110">[Use Config.xml to perform installation tasks in Skype for Business Server 2015](use-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>
    
- <span data-ttu-id="1c301-111">[Opciones de línea de comandos de configuración de utilizar en Skype para Business Server 2015](use-setup-command-line-options.md) para especificar el archivo Config.xml para usar durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="1c301-111">[Use Setup command-line options in Skype for Business Server 2015](use-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>
    
- <span data-ttu-id="1c301-112">[Configurar directivas de inicio de cliente de Skype para Business Server 2015](configure-client-bootstrapping-policies.md) utilizando el complemento de MMC Editor de objetos de directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="1c301-112">[Configure client bootstrapping policies in Skype for Business Server 2015](configure-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>
    
<span data-ttu-id="1c301-113">Probablemente habrá otras opciones que desee configurar como implementar el conjunto de productos de Office.</span><span class="sxs-lookup"><span data-stu-id="1c301-113">There will probably be other options you'll want to configure as you deploy the Office suite of products.</span></span> <span data-ttu-id="1c301-114">En los temas de esta sección proporcionan una visión general de estas herramientas de personalización y discutir las consideraciones específicas de Skype para el negocio.</span><span class="sxs-lookup"><span data-stu-id="1c301-114">The topics in this section give an overview of these customization tools and discuss considerations specific to Skype for Business.</span></span> <span data-ttu-id="1c301-115">También se incluyen vínculos a la ayuda detallada de Office sobre estas herramientas.</span><span class="sxs-lookup"><span data-stu-id="1c301-115">Included are links to detailed Office help for each tool.</span></span> 
  

