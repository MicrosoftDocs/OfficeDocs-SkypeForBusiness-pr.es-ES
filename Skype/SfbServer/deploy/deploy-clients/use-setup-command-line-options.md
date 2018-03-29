---
title: Usar las opciones de la línea de comandos en Skype Empresarial Server 2015
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 10/20/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 'Resumen: Conozca las operaciones de línea de comandos de Setup.exe en la instalación de Office.'
ms.openlocfilehash: 0fa4f31750697f0bd0dbe87bbde025cbc7f530bd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="use-setup-command-line-options-in-skype-for-business-server-2015"></a><span data-ttu-id="03746-103">Usar las opciones de la línea de comandos en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="03746-103">Use Setup command-line options in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="03746-104">**Resumen:** Obtenga información sobre las operaciones de línea de comandos de Setup.exe en la instalación de Office.</span><span class="sxs-lookup"><span data-stu-id="03746-104">**Summary:** Learn about Setup.exe command line operations in Office setup.</span></span>
  
<span data-ttu-id="03746-105">La línea de comandos de Setup.exe se utiliza para muy pocas operaciones en la instalación de Office.</span><span class="sxs-lookup"><span data-stu-id="03746-105">The Setup.exe command line is used for very few operations in Office setup.</span></span> <span data-ttu-id="03746-106">En lugar de utilizar las opciones de línea de comandos de instalación, normalmente utilizará la herramienta de personalización de Office y el archivo Config.xml para productos de setup y la característica de personalización.</span><span class="sxs-lookup"><span data-stu-id="03746-106">Instead of using the Setup command-line options, you'll typically use the Office Customization Tool and the Config.xml file for product setup and feature customization.</span></span>
  
<span data-ttu-id="03746-107">La línea de comandos de Setup.exe de Office reconoce las opciones de línea de comandos que se detallan en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="03746-107">The Office Setup.exe command line recognizes the command-line options described in the following table.</span></span>
  
<span data-ttu-id="03746-108">**Opciones de línea de comandos de instalación de Office**</span><span class="sxs-lookup"><span data-stu-id="03746-108">**Office Setup Command-Line Options**</span></span>

|<span data-ttu-id="03746-109">**Opción de línea de comandos de instalación**</span><span class="sxs-lookup"><span data-stu-id="03746-109">**Setup Command-Line Option**</span></span>|<span data-ttu-id="03746-110">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="03746-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="03746-111">/admin</span><span class="sxs-lookup"><span data-stu-id="03746-111">/admin</span></span>  <br/> |<span data-ttu-id="03746-112">Ejecuta la Herramienta de personalización del Office para crear un archivo de personalización del programa de instalación (archivo .msp).</span><span class="sxs-lookup"><span data-stu-id="03746-112">Runs the Office Customization Tool to create a Setup customization file (.msp file).</span></span>  <br/> |
|<span data-ttu-id="03746-113">/adminfile [path]</span><span class="sxs-lookup"><span data-stu-id="03746-113">/adminfile [path]</span></span>  <br/> |<span data-ttu-id="03746-p102">Aplica a la instalación el archivo de personalización del programa de instalación especificado. Puede especificar una ruta de acceso a un archivo de personalización (archivo .msp) específico o a la carpeta donde guarde los archivos de personalización.</span><span class="sxs-lookup"><span data-stu-id="03746-p102">Applies the specified Setup customization file to the installation. You can specify a path of a specific customization file (.msp file) or to the folder where you store customization files.</span></span>  <br/> |
|<span data-ttu-id="03746-116">/config [path]</span><span class="sxs-lookup"><span data-stu-id="03746-116">/config [path]</span></span>  <br/> |<span data-ttu-id="03746-117">Especifica el archivo Config.xml que el programa de instalación usará durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="03746-117">Specifies the Config.xml file that Setup uses during the installation.</span></span> <span data-ttu-id="03746-118">Utilice la opción /config para especificar el archivo Config.xml que personalizó de Skype para las instalaciones de la empresa, por ejemplo:`/config \\server\share\Skype15\Skype.WW\Config.xml`</span><span class="sxs-lookup"><span data-stu-id="03746-118">Use the /config option to specify the Config.xml file you customized for Skype for Business installations, for example:  `/config \\server\share\Skype15\Skype.WW\Config.xml`</span></span> <br/> |
|<span data-ttu-id="03746-119">/modify Skype</span><span class="sxs-lookup"><span data-stu-id="03746-119">/modify Skype</span></span>  <br/> |<span data-ttu-id="03746-120">Se usa con un archivo Config.xml modificado para ejecutar el programa de instalación en modo de mantenimiento y realizar cambios en una instalación de Office existente.</span><span class="sxs-lookup"><span data-stu-id="03746-120">Used with a modified Config.xml file to run Setup in maintenance mode and make changes to an existing Office installation.</span></span> <span data-ttu-id="03746-121">Por ejemplo, puede utilizar el / modificar la opción de agregar o quitar Skype para funciones de negocio.</span><span class="sxs-lookup"><span data-stu-id="03746-121">For example, you can use the /modify option to add or remove Skype for Business features.</span></span>  <br/> |
|<span data-ttu-id="03746-122">/repair Skype</span><span class="sxs-lookup"><span data-stu-id="03746-122">/repair Skype</span></span>  <br/> |<span data-ttu-id="03746-123">Ejecuta la instalación desde el equipo del usuario para reparar Skype para el negocio.</span><span class="sxs-lookup"><span data-stu-id="03746-123">Runs Setup from the user's computer to repair Skype for Business.</span></span>  <br/> |
|<span data-ttu-id="03746-124">/uninstall Skype</span><span class="sxs-lookup"><span data-stu-id="03746-124">/uninstall Skype</span></span>  <br/> |<span data-ttu-id="03746-125">Ejecuta la instalación para quitar Skype para el negocio desde el equipo del usuario.</span><span class="sxs-lookup"><span data-stu-id="03746-125">Runs Setup to remove Skype for Business from the user's computer.</span></span>  <br/> |
   
<span data-ttu-id="03746-126">Para obtener más información acerca de cómo utilizar las opciones de línea de comandos de instalación, consulte [https://go.microsoft.com/fwlink/p/?linkid=267515](https://go.microsoft.com/fwlink/p/?linkid=267515).</span><span class="sxs-lookup"><span data-stu-id="03746-126">For details about using the setup command-line options, see [https://go.microsoft.com/fwlink/p/?linkid=267515](https://go.microsoft.com/fwlink/p/?linkid=267515).</span></span> 
  

