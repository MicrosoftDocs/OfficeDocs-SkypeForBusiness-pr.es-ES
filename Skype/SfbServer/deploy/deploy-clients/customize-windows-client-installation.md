---
title: Personalizar la instalación de cliente de Windows en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
description: 'Resumen: información general sobre los métodos y herramientas de instalación de Skype Empresarial.'
ms.openlocfilehash: 001224369e46978e96ee063b31fcb546ef213a05
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805720"
---
# <a name="customize-windows-client-installation-in-skype-for-business-server"></a><span data-ttu-id="12e4d-103">Personalizar la instalación de cliente de Windows en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="12e4d-103">Customize Windows client installation in Skype for Business Server</span></span>
 
<span data-ttu-id="12e4d-104">**Resumen:** Información general sobre los métodos y herramientas de instalación para Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="12e4d-104">**Summary:** Overview of installation methods and tools for Skype for Business.</span></span>
  
> [!NOTE]
> <span data-ttu-id="12e4d-105">Para obtener información de instalación sobre Skype Empresarial que se incluye con Microsoft 365 y Office 365, vea Implementar el cliente de Skype Empresarial en [Microsoft 365 u Office 365.](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)</span><span class="sxs-lookup"><span data-stu-id="12e4d-105">For installation information about Skype for Business that comes with Microsoft 365 and Office 365, see [Deploy the Skype for Business client in Microsoft 365 or Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span> 
  
<span data-ttu-id="12e4d-106">Los administradores de empresa pueden personalizar la instalación basada en Windows Installer (.msi) de las versiones con licencia por volumen de Skype Empresarial mediante los métodos que se deban tratar en esta sección.</span><span class="sxs-lookup"><span data-stu-id="12e4d-106">Enterprise administrators can customize the Windows Installer-based (.msi) installation of volume licensed versions of Skype for Business by using the methods discussed in this section.</span></span> <span data-ttu-id="12e4d-107">Dado que ninguna herramienta única proporciona todas las opciones de personalización, es probable que use una combinación de estos métodos en su implementación de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="12e4d-107">Because no single tool provides all customization options, you'll likely use a combination of these methods in your Skype for Business deployment.</span></span> <span data-ttu-id="12e4d-108">Puede usar las herramientas que se describen en las secciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="12e4d-108">You might use the tools described in the following sections:</span></span>
  
- <span data-ttu-id="12e4d-109">[Use la Herramienta de personalización de Office (OCT)](use-the-office-customization-tool-oct.md) en Skype Empresarial Server para personalizar las opciones de configuración y las características de Skype Empresarial y otros programas de Office.</span><span class="sxs-lookup"><span data-stu-id="12e4d-109">[Use the Office Customization Tool (OCT) in Skype for Business Server](use-the-office-customization-tool-oct.md) to customize setup options and features for Skype for Business and other Office programs.</span></span>
    
- <span data-ttu-id="12e4d-110">[Use Config.xml para realizar tareas de](use-config-xml-to-perform-installation-tasks.md) instalación en Skype Empresarial Server para especificar la ruta de acceso del punto de instalación de red y realizar una instalación silenciosa.</span><span class="sxs-lookup"><span data-stu-id="12e4d-110">[Use Config.xml to perform installation tasks in Skype for Business Server](use-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>
    
- <span data-ttu-id="12e4d-111">[Use las opciones de la línea de](use-setup-command-line-options.md) comandos del programa de instalación en Skype Empresarial Server para especificar el Config.xml que se usará durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="12e4d-111">[Use Setup command-line options in Skype for Business Server](use-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>
    
- <span data-ttu-id="12e4d-112">[Configure las directivas de arranque de cliente en Skype Empresarial Server](configure-client-bootstrapping-policies.md) mediante el complemento MMC del Editor de objetos de directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="12e4d-112">[Configure client bootstrapping policies in Skype for Business Server](configure-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>
    
<span data-ttu-id="12e4d-113">Probablemente habrá otras opciones que querrá configurar al implementar el conjunto de productos de Office.</span><span class="sxs-lookup"><span data-stu-id="12e4d-113">There will probably be other options you'll want to configure as you deploy the Office suite of products.</span></span> <span data-ttu-id="12e4d-114">Los temas de esta sección proporcionan información general sobre estas herramientas de personalización y tratan consideraciones específicas de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="12e4d-114">The topics in this section give an overview of these customization tools and discuss considerations specific to Skype for Business.</span></span> <span data-ttu-id="12e4d-115">Se incluyen vínculos a la ayuda detallada de Office para cada herramienta.</span><span class="sxs-lookup"><span data-stu-id="12e4d-115">Included are links to detailed Office help for each tool.</span></span> 
  

