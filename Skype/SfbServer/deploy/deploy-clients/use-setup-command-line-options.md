---
title: Usar las opciones de la línea de comandos de configuración con clientes de Skype empresarial
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
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 'Resumen: Obtenga información sobre las operaciones de la línea de comandos de Setup. exe en el programa de instalación de Office.'
ms.openlocfilehash: 68add6e2744e9648db49508519c14e64b4e6aeef
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768633"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a><span data-ttu-id="d6451-103">Usar las opciones de la línea de comandos de configuración con clientes de Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="d6451-103">Use Setup command-line options with Skype for Business clients</span></span>
 
<span data-ttu-id="d6451-104">**Resumen:** Obtenga información sobre las operaciones de la línea de comandos de Setup. exe en el programa de instalación de Office.</span><span class="sxs-lookup"><span data-stu-id="d6451-104">**Summary:** Learn about Setup.exe command line operations in Office setup.</span></span>
  
<span data-ttu-id="d6451-105">La línea de comandos de Setup.exe se utiliza para muy pocas operaciones en la instalación de Office.</span><span class="sxs-lookup"><span data-stu-id="d6451-105">The Setup.exe command line is used for very few operations in Office setup.</span></span> <span data-ttu-id="d6451-106">En lugar de usar las opciones de la línea de comandos de configuración, normalmente usará la herramienta de personalización de Office y el archivo config. XML para la configuración del producto y la personalización de las características.</span><span class="sxs-lookup"><span data-stu-id="d6451-106">Instead of using the Setup command-line options, you'll typically use the Office Customization Tool and the Config.xml file for product setup and feature customization.</span></span>
  
<span data-ttu-id="d6451-107">La línea de comandos de Setup.exe de Office reconoce las opciones de línea de comandos que se detallan en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="d6451-107">The Office Setup.exe command line recognizes the command-line options described in the following table.</span></span>
  
<span data-ttu-id="d6451-108">**Opciones de línea de comandos del programa de instalación de Office**</span><span class="sxs-lookup"><span data-stu-id="d6451-108">**Office Setup Command-Line Options**</span></span>

|<span data-ttu-id="d6451-109">**Opción de línea de comandos del programa de instalación**</span><span class="sxs-lookup"><span data-stu-id="d6451-109">**Setup Command-Line Option**</span></span>|<span data-ttu-id="d6451-110">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d6451-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d6451-111">/admin</span><span class="sxs-lookup"><span data-stu-id="d6451-111">/admin</span></span>  <br/> |<span data-ttu-id="d6451-112">Ejecuta la Herramienta de personalización del Office para crear un archivo de personalización del programa de instalación (archivo .msp).</span><span class="sxs-lookup"><span data-stu-id="d6451-112">Runs the Office Customization Tool to create a Setup customization file (.msp file).</span></span>  <br/> |
|<span data-ttu-id="d6451-113">/adminfile [path]</span><span class="sxs-lookup"><span data-stu-id="d6451-113">/adminfile [path]</span></span>  <br/> |<span data-ttu-id="d6451-p102">Aplica a la instalación el archivo de personalización del programa de instalación especificado. Puede especificar una ruta de acceso a un archivo de personalización (archivo .msp) específico o a la carpeta donde guarde los archivos de personalización.</span><span class="sxs-lookup"><span data-stu-id="d6451-p102">Applies the specified Setup customization file to the installation. You can specify a path of a specific customization file (.msp file) or to the folder where you store customization files.</span></span>  <br/> |
|<span data-ttu-id="d6451-116">/config [path]</span><span class="sxs-lookup"><span data-stu-id="d6451-116">/config [path]</span></span>  <br/> |<span data-ttu-id="d6451-117">Especifica el archivo Config.xml que el programa de instalación usará durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="d6451-117">Specifies the Config.xml file that Setup uses during the installation.</span></span> <span data-ttu-id="d6451-118">Use la opción/config para especificar el archivo config. XML que ha personalizado para las instalaciones de Skype empresarial, por ejemplo:`/config \\server\share\Skype15\Skype.WW\Config.xml`</span><span class="sxs-lookup"><span data-stu-id="d6451-118">Use the /config option to specify the Config.xml file you customized for Skype for Business installations, for example:  `/config \\server\share\Skype15\Skype.WW\Config.xml`</span></span> <br/> |
|<span data-ttu-id="d6451-119">/modify Skype</span><span class="sxs-lookup"><span data-stu-id="d6451-119">/modify Skype</span></span>  <br/> |<span data-ttu-id="d6451-120">Se usa con un archivo Config.xml modificado para ejecutar el programa de instalación en modo de mantenimiento y realizar cambios en una instalación de Office existente.</span><span class="sxs-lookup"><span data-stu-id="d6451-120">Used with a modified Config.xml file to run Setup in maintenance mode and make changes to an existing Office installation.</span></span> <span data-ttu-id="d6451-121">Por ejemplo, puede usar la opción/Modify para agregar o quitar características de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="d6451-121">For example, you can use the /modify option to add or remove Skype for Business features.</span></span>  <br/> |
|<span data-ttu-id="d6451-122">/repair Skype</span><span class="sxs-lookup"><span data-stu-id="d6451-122">/repair Skype</span></span>  <br/> |<span data-ttu-id="d6451-123">Ejecuta el programa de instalación desde el equipo del usuario para reparar Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="d6451-123">Runs Setup from the user's computer to repair Skype for Business.</span></span>  <br/> |
|<span data-ttu-id="d6451-124">/uninstall Skype</span><span class="sxs-lookup"><span data-stu-id="d6451-124">/uninstall Skype</span></span>  <br/> |<span data-ttu-id="d6451-125">Ejecuta el programa de instalación para quitar Skype empresarial del equipo del usuario.</span><span class="sxs-lookup"><span data-stu-id="d6451-125">Runs Setup to remove Skype for Business from the user's computer.</span></span>  <br/> |
   


