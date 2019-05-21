---
title: Personalizar la instalación del cliente de Windows en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
description: 'Resumen: información general sobre métodos de instalación y herramientas para Skype empresarial.'
ms.openlocfilehash: 40e5b9145f06038e76aee0b77b287e6dce9a8b3b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288581"
---
# <a name="customize-windows-client-installation-in-skype-for-business-server"></a><span data-ttu-id="848a4-103">Personalizar la instalación del cliente de Windows en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="848a4-103">Customize Windows client installation in Skype for Business Server</span></span>
 
<span data-ttu-id="848a4-104">**Resumen:** Información general sobre métodos de instalación y herramientas para Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="848a4-104">**Summary:** Overview of installation methods and tools for Skype for Business.</span></span>
  
> [!NOTE]
> <span data-ttu-id="848a4-105">Para obtener información sobre la instalación de Skype empresarial que se incluye con Office 365, consulte [implementar el cliente de Skype empresarial en office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span><span class="sxs-lookup"><span data-stu-id="848a4-105">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span> 
  
<span data-ttu-id="848a4-106">Los administradores de empresa pueden personalizar la instalación de Windows Installer (. msi) de las versiones con licencia por volumen de Skype empresarial mediante los métodos que se tratan en esta sección.</span><span class="sxs-lookup"><span data-stu-id="848a4-106">Enterprise administrators can customize the Windows Installer-based (.msi) installation of volume licensed versions of Skype for Business by using the methods discussed in this section.</span></span> <span data-ttu-id="848a4-107">Puesto que ninguna herramienta única ofrece todas las opciones de personalización, es probable que use una combinación de estos métodos en la implementación de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="848a4-107">Because no single tool provides all customization options, you'll likely use a combination of these methods in your Skype for Business deployment.</span></span> <span data-ttu-id="848a4-108">Puede usar las herramientas que se describen en las secciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="848a4-108">You might use the tools described in the following sections:</span></span>
  
- <span data-ttu-id="848a4-109">[Use la herramienta de personalización de Office (Oct) en Skype empresarial Server](use-the-office-customization-tool-oct.md) para personalizar las opciones de configuración y las características de Skype empresarial y de otros programas de Office.</span><span class="sxs-lookup"><span data-stu-id="848a4-109">[Use the Office Customization Tool (OCT) in Skype for Business Server](use-the-office-customization-tool-oct.md) to customize setup options and features for Skype for Business and other Office programs.</span></span>
    
- <span data-ttu-id="848a4-110">[Use config. XML para realizar tareas de instalación en Skype empresarial Server](use-config-xml-to-perform-installation-tasks.md) para especificar la ruta de acceso del punto de instalación de red y realizar una instalación silenciosa.</span><span class="sxs-lookup"><span data-stu-id="848a4-110">[Use Config.xml to perform installation tasks in Skype for Business Server](use-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>
    
- <span data-ttu-id="848a4-111">[Use las opciones de la línea de comandos de configuración de Skype empresarial Server](use-setup-command-line-options.md) para especificar el archivo config. XML para usar durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="848a4-111">[Use Setup command-line options in Skype for Business Server](use-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>
    
- <span data-ttu-id="848a4-112">[Configure las directivas de inicio del cliente en Skype empresarial Server](configure-client-bootstrapping-policies.md) con el complemento de MMC editor de objetos de directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="848a4-112">[Configure client bootstrapping policies in Skype for Business Server](configure-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>
    
<span data-ttu-id="848a4-113">Es probable que haya otras opciones que desee configurar al implementar el conjunto de productos de Office.</span><span class="sxs-lookup"><span data-stu-id="848a4-113">There will probably be other options you'll want to configure as you deploy the Office suite of products.</span></span> <span data-ttu-id="848a4-114">En los temas de esta sección se ofrece información general sobre estas herramientas de personalización y se describen algunas consideraciones específicas de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="848a4-114">The topics in this section give an overview of these customization tools and discuss considerations specific to Skype for Business.</span></span> <span data-ttu-id="848a4-115">También se incluyen vínculos a la ayuda detallada de Office sobre estas herramientas.</span><span class="sxs-lookup"><span data-stu-id="848a4-115">Included are links to detailed Office help for each tool.</span></span> 
  

