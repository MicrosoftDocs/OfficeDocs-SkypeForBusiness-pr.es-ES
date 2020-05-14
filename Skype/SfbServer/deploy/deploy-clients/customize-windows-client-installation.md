---
title: Personalización de la instalación del cliente de Windows en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
description: 'Resumen: información general sobre los métodos y las herramientas de instalación de Skype empresarial.'
ms.openlocfilehash: ea8a07bf6a6e00eee93f2a0a8b3ffc756b239ce9
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220840"
---
# <a name="customize-windows-client-installation-in-skype-for-business-server"></a><span data-ttu-id="bed48-103">Personalización de la instalación del cliente de Windows en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="bed48-103">Customize Windows client installation in Skype for Business Server</span></span>
 
<span data-ttu-id="bed48-104">**Resumen:** Información general sobre los métodos y las herramientas de instalación de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="bed48-104">**Summary:** Overview of installation methods and tools for Skype for Business.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bed48-105">Para obtener información sobre la instalación de Skype empresarial incluida con Microsoft 365 y Office 365, consulte [implementar el cliente de Skype empresarial en microsoft 365 u office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span><span class="sxs-lookup"><span data-stu-id="bed48-105">For installation information about Skype for Business that comes with Microsoft 365 and Office 365, see [Deploy the Skype for Business client in Microsoft 365 or Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span> 
  
<span data-ttu-id="bed48-106">Los administradores de la empresa pueden personalizar la instalación basada en Windows Installer (. msi) de las versiones de licencia por volumen de Skype empresarial mediante los métodos descritos en esta sección.</span><span class="sxs-lookup"><span data-stu-id="bed48-106">Enterprise administrators can customize the Windows Installer-based (.msi) installation of volume licensed versions of Skype for Business by using the methods discussed in this section.</span></span> <span data-ttu-id="bed48-107">Debido a que ninguna herramienta única proporciona todas las opciones de personalización, es probable que use una combinación de estos métodos en su implementación de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="bed48-107">Because no single tool provides all customization options, you'll likely use a combination of these methods in your Skype for Business deployment.</span></span> <span data-ttu-id="bed48-108">Puede usar las herramientas que se describen en las siguientes secciones:</span><span class="sxs-lookup"><span data-stu-id="bed48-108">You might use the tools described in the following sections:</span></span>
  
- <span data-ttu-id="bed48-109">[Use la herramienta de personalización de Office (Oct) en Skype empresarial Server](use-the-office-customization-tool-oct.md) para personalizar las opciones de instalación y las características de Skype empresarial y otros programas de Office.</span><span class="sxs-lookup"><span data-stu-id="bed48-109">[Use the Office Customization Tool (OCT) in Skype for Business Server](use-the-office-customization-tool-oct.md) to customize setup options and features for Skype for Business and other Office programs.</span></span>
    
- <span data-ttu-id="bed48-110">[Use config. XML para realizar tareas de instalación en Skype empresarial Server](use-config-xml-to-perform-installation-tasks.md) para especificar la ruta de acceso del punto de instalación de red y realizar una instalación silenciosa.</span><span class="sxs-lookup"><span data-stu-id="bed48-110">[Use Config.xml to perform installation tasks in Skype for Business Server](use-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>
    
- <span data-ttu-id="bed48-111">[Use las opciones de la línea de comandos del programa de instalación en Skype empresarial Server](use-setup-command-line-options.md) para especificar el archivo config. XML que se usará durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="bed48-111">[Use Setup command-line options in Skype for Business Server](use-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>
    
- <span data-ttu-id="bed48-112">[Configure las directivas de arranque de cliente en Skype empresarial Server](configure-client-bootstrapping-policies.md) mediante el complemento MMC del editor de objetos de directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="bed48-112">[Configure client bootstrapping policies in Skype for Business Server](configure-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>
    
<span data-ttu-id="bed48-113">Probablemente habrá otras opciones que querrá configurar al implementar el conjunto de productos de Office.</span><span class="sxs-lookup"><span data-stu-id="bed48-113">There will probably be other options you'll want to configure as you deploy the Office suite of products.</span></span> <span data-ttu-id="bed48-114">En los temas de esta sección se ofrece información general sobre estas herramientas de personalización y se explican consideraciones específicas de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="bed48-114">The topics in this section give an overview of these customization tools and discuss considerations specific to Skype for Business.</span></span> <span data-ttu-id="bed48-115">Se incluyen vínculos a la ayuda detallada de Office para cada herramienta.</span><span class="sxs-lookup"><span data-stu-id="bed48-115">Included are links to detailed Office help for each tool.</span></span> 
  

