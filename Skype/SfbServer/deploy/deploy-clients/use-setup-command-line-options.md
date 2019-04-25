---
title: Utilice las opciones de línea de comandos del programa de instalación con Skype para clientes empresariales
ms.reviewer: ''
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 'Resumen: Obtenga información sobre las operaciones de la línea de comandos de Setup.exe en el programa de instalación de Office.'
ms.openlocfilehash: d3bf2b4d867fbbb43c346f2b9572de329ec66bdc
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214880"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a><span data-ttu-id="240a8-103">Utilice las opciones de línea de comandos del programa de instalación con Skype para clientes empresariales</span><span class="sxs-lookup"><span data-stu-id="240a8-103">Use Setup command-line options with Skype for Business clients</span></span>
 
<span data-ttu-id="240a8-104">**Resumen:** Obtenga información acerca de las operaciones de la línea de comandos de Setup.exe en el programa de instalación de Office.</span><span class="sxs-lookup"><span data-stu-id="240a8-104">**Summary:** Learn about Setup.exe command line operations in Office setup.</span></span>
  
<span data-ttu-id="240a8-105">La línea de comandos de Setup.exe se utiliza para muy pocas operaciones en la instalación de Office.</span><span class="sxs-lookup"><span data-stu-id="240a8-105">The Setup.exe command line is used for very few operations in Office setup.</span></span> <span data-ttu-id="240a8-106">En lugar de usar las opciones de línea de comandos del programa de instalación, por lo general, debe usar la herramienta de personalización de Office y el archivo Config.xml para la personalización del programa de instalación y la característica de producto.</span><span class="sxs-lookup"><span data-stu-id="240a8-106">Instead of using the Setup command-line options, you'll typically use the Office Customization Tool and the Config.xml file for product setup and feature customization.</span></span>
  
<span data-ttu-id="240a8-107">La línea de comandos de Setup.exe de Office reconoce las opciones de línea de comandos que se detallan en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="240a8-107">The Office Setup.exe command line recognizes the command-line options described in the following table.</span></span>
  
<span data-ttu-id="240a8-108">**Opciones de línea de comandos del programa de instalación de Office**</span><span class="sxs-lookup"><span data-stu-id="240a8-108">**Office Setup Command-Line Options**</span></span>

|<span data-ttu-id="240a8-109">**Opción de línea de comandos del programa de instalación**</span><span class="sxs-lookup"><span data-stu-id="240a8-109">**Setup Command-Line Option**</span></span>|<span data-ttu-id="240a8-110">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="240a8-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="240a8-111">/admin</span><span class="sxs-lookup"><span data-stu-id="240a8-111">/admin</span></span>  <br/> |<span data-ttu-id="240a8-112">Ejecuta la Herramienta de personalización del Office para crear un archivo de personalización del programa de instalación (archivo .msp).</span><span class="sxs-lookup"><span data-stu-id="240a8-112">Runs the Office Customization Tool to create a Setup customization file (.msp file).</span></span>  <br/> |
|<span data-ttu-id="240a8-113">/adminfile [path]</span><span class="sxs-lookup"><span data-stu-id="240a8-113">/adminfile [path]</span></span>  <br/> |<span data-ttu-id="240a8-p102">Aplica a la instalación el archivo de personalización del programa de instalación especificado. Puede especificar una ruta de acceso a un archivo de personalización (archivo .msp) específico o a la carpeta donde guarde los archivos de personalización.</span><span class="sxs-lookup"><span data-stu-id="240a8-p102">Applies the specified Setup customization file to the installation. You can specify a path of a specific customization file (.msp file) or to the folder where you store customization files.</span></span>  <br/> |
|<span data-ttu-id="240a8-116">/config [path]</span><span class="sxs-lookup"><span data-stu-id="240a8-116">/config [path]</span></span>  <br/> |<span data-ttu-id="240a8-117">Especifica el archivo Config.xml que el programa de instalación usará durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="240a8-117">Specifies the Config.xml file that Setup uses during the installation.</span></span> <span data-ttu-id="240a8-118">Use la opción /config para especificar el archivo Config.xml que personalizó para Skype para las instalaciones de negocio, por ejemplo:`/config \\server\share\Skype15\Skype.WW\Config.xml`</span><span class="sxs-lookup"><span data-stu-id="240a8-118">Use the /config option to specify the Config.xml file you customized for Skype for Business installations, for example:  `/config \\server\share\Skype15\Skype.WW\Config.xml`</span></span> <br/> |
|<span data-ttu-id="240a8-119">/modify Skype</span><span class="sxs-lookup"><span data-stu-id="240a8-119">/modify Skype</span></span>  <br/> |<span data-ttu-id="240a8-120">Se usa con un archivo Config.xml modificado para ejecutar el programa de instalación en modo de mantenimiento y realizar cambios en una instalación de Office existente.</span><span class="sxs-lookup"><span data-stu-id="240a8-120">Used with a modified Config.xml file to run Setup in maintenance mode and make changes to an existing Office installation.</span></span> <span data-ttu-id="240a8-121">Por ejemplo, puede usar el / modificar opción para agregar o quitar Skype para las características de negocio.</span><span class="sxs-lookup"><span data-stu-id="240a8-121">For example, you can use the /modify option to add or remove Skype for Business features.</span></span>  <br/> |
|<span data-ttu-id="240a8-122">/repair Skype</span><span class="sxs-lookup"><span data-stu-id="240a8-122">/repair Skype</span></span>  <br/> |<span data-ttu-id="240a8-123">Ejecuta el programa de instalación desde el equipo del usuario para reparar Skype para la empresa.</span><span class="sxs-lookup"><span data-stu-id="240a8-123">Runs Setup from the user's computer to repair Skype for Business.</span></span>  <br/> |
|<span data-ttu-id="240a8-124">/uninstall Skype</span><span class="sxs-lookup"><span data-stu-id="240a8-124">/uninstall Skype</span></span>  <br/> |<span data-ttu-id="240a8-125">Se ejecuta el programa de instalación para quitar Skype para la empresa desde el equipo del usuario.</span><span class="sxs-lookup"><span data-stu-id="240a8-125">Runs Setup to remove Skype for Business from the user's computer.</span></span>  <br/> |
   


