---
title: Personalizar la instalación de cliente de Windows en Skype para Business Server
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
description: 'Resumen: Información general de los métodos de instalación y las herramientas de Skype para la empresa.'
ms.openlocfilehash: e5d575e7a1efc54ade19d76575f3d5ec2937de62
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21009175"
---
# <a name="customize-windows-client-installation-in-skype-for-business-server"></a><span data-ttu-id="d2257-103">Personalizar la instalación de cliente de Windows en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="d2257-103">Customize Windows client installation in Skype for Business Server</span></span>
 
<span data-ttu-id="d2257-104">**Resumen:** Introducción a los métodos de instalación y las herramientas de Skype para la empresa.</span><span class="sxs-lookup"><span data-stu-id="d2257-104">**Summary:** Overview of installation methods and tools for Skype for Business.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d2257-105">Para obtener información de instalación acerca de Skype para la empresa que se incluye con Office 365, vea [implementar el Skype para cliente empresarial en Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span><span class="sxs-lookup"><span data-stu-id="d2257-105">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span> 
  
<span data-ttu-id="d2257-106">Los administradores de empresa pueden personalizar la instalación basada en Windows Installer (.msi) de las versiones de licencia por volumen de Skype para la empresa mediante el uso de los métodos descritos en esta sección.</span><span class="sxs-lookup"><span data-stu-id="d2257-106">Enterprise administrators can customize the Windows Installer-based (.msi) installation of volume licensed versions of Skype for Business by using the methods discussed in this section.</span></span> <span data-ttu-id="d2257-107">Debido a que no existe ninguna herramienta única proporciona todas las opciones de personalización, es probable que, debe usar una combinación de estos métodos en su Skype para la implementación de la empresa.</span><span class="sxs-lookup"><span data-stu-id="d2257-107">Because no single tool provides all customization options, you'll likely use a combination of these methods in your Skype for Business deployment.</span></span> <span data-ttu-id="d2257-108">Puede usar las herramientas que se describen en las secciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="d2257-108">You might use the tools described in the following sections:</span></span>
  
- <span data-ttu-id="d2257-109">[Use la herramienta de personalización de Office (OCT) en Skype para Business Server](use-the-office-customization-tool-oct.md) para personalizar las características y opciones de instalación de Skype para profesionales y otros programas de Office.</span><span class="sxs-lookup"><span data-stu-id="d2257-109">[Use the Office Customization Tool (OCT) in Skype for Business Server](use-the-office-customization-tool-oct.md) to customize setup options and features for Skype for Business and other Office programs.</span></span>
    
- <span data-ttu-id="d2257-110">[Usar Config.xml para realizar tareas de instalación en Skype para Business Server](use-config-xml-to-perform-installation-tasks.md) para especificar la ruta de acceso del punto de instalación de red y llevar a cabo una instalación silenciosa.</span><span class="sxs-lookup"><span data-stu-id="d2257-110">[Use Config.xml to perform installation tasks in Skype for Business Server](use-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>
    
- <span data-ttu-id="d2257-111">[Usar el programa de instalación de las opciones de línea de comandos en Skype para Business Server](use-setup-command-line-options.md) para especificar el archivo Config.xml para usar durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="d2257-111">[Use Setup command-line options in Skype for Business Server](use-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>
    
- <span data-ttu-id="d2257-112">[Configurar directivas de arranque cliente en Skype para Business Server](configure-client-bootstrapping-policies.md) mediante el complemento de MMC Editor de objetos de directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="d2257-112">[Configure client bootstrapping policies in Skype for Business Server](configure-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>
    
<span data-ttu-id="d2257-113">Probablemente habrá otras opciones que desee configurar como implementar el conjunto de productos de Office.</span><span class="sxs-lookup"><span data-stu-id="d2257-113">There will probably be other options you'll want to configure as you deploy the Office suite of products.</span></span> <span data-ttu-id="d2257-114">En los temas de esta sección proporcionar una descripción general de estas herramientas de personalización y se describen consideraciones específicas a Skype para la empresa.</span><span class="sxs-lookup"><span data-stu-id="d2257-114">The topics in this section give an overview of these customization tools and discuss considerations specific to Skype for Business.</span></span> <span data-ttu-id="d2257-115">También se incluyen vínculos a la ayuda detallada de Office sobre estas herramientas.</span><span class="sxs-lookup"><span data-stu-id="d2257-115">Included are links to detailed Office help for each tool.</span></span> 
  

