---
title: Usar las opciones de línea de comandos del programa de instalación con clientes de Skype Empresarial
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
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 'Resumen: obtenga información sobre cómo Setup.exe línea de comandos en el programa de instalación de Office.'
ms.openlocfilehash: 042ba2bdea6228f7c8a726c0bdb2ca5c3233d5f4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837210"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a><span data-ttu-id="2011d-103">Usar las opciones de línea de comandos del programa de instalación con clientes de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="2011d-103">Use Setup command-line options with Skype for Business clients</span></span>
 
<span data-ttu-id="2011d-104">**Resumen:** Obtenga información sobre Setup.exe de línea de comandos en el programa de instalación de Office.</span><span class="sxs-lookup"><span data-stu-id="2011d-104">**Summary:** Learn about Setup.exe command line operations in Office setup.</span></span>
  
<span data-ttu-id="2011d-105">La línea de comandos de Setup.exe se utiliza para muy pocas operaciones en la instalación de Office.</span><span class="sxs-lookup"><span data-stu-id="2011d-105">The Setup.exe command line is used for very few operations in Office setup.</span></span> <span data-ttu-id="2011d-106">En lugar de usar las opciones de la línea de comandos del programa de instalación, normalmente usará la Herramienta de personalización de Office y el archivo Config.xml para la configuración del producto y la personalización de características.</span><span class="sxs-lookup"><span data-stu-id="2011d-106">Instead of using the Setup command-line options, you'll typically use the Office Customization Tool and the Config.xml file for product setup and feature customization.</span></span>
  
<span data-ttu-id="2011d-107">La línea de comandos de Setup.exe de Office reconoce las opciones de línea de comandos que se detallan en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="2011d-107">The Office Setup.exe command line recognizes the command-line options described in the following table.</span></span>
  
<span data-ttu-id="2011d-108">**Opciones de línea de comandos del programa de instalación de Office**</span><span class="sxs-lookup"><span data-stu-id="2011d-108">**Office Setup Command-Line Options**</span></span>

|<span data-ttu-id="2011d-109">**Opción de línea de comandos del programa de instalación**</span><span class="sxs-lookup"><span data-stu-id="2011d-109">**Setup Command-Line Option**</span></span>|<span data-ttu-id="2011d-110">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="2011d-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2011d-111">/admin</span><span class="sxs-lookup"><span data-stu-id="2011d-111">/admin</span></span>  <br/> |<span data-ttu-id="2011d-112">Ejecuta la Herramienta de personalización del Office para crear un archivo de personalización del programa de instalación (archivo .msp).</span><span class="sxs-lookup"><span data-stu-id="2011d-112">Runs the Office Customization Tool to create a Setup customization file (.msp file).</span></span>  <br/> |
|<span data-ttu-id="2011d-113">/adminfile [path]</span><span class="sxs-lookup"><span data-stu-id="2011d-113">/adminfile [path]</span></span>  <br/> |<span data-ttu-id="2011d-p102">Aplica a la instalación el archivo de personalización del programa de instalación especificado. Puede especificar una ruta de acceso a un archivo de personalización (archivo .msp) específico o a la carpeta donde guarde los archivos de personalización.</span><span class="sxs-lookup"><span data-stu-id="2011d-p102">Applies the specified Setup customization file to the installation. You can specify a path of a specific customization file (.msp file) or to the folder where you store customization files.</span></span>  <br/> |
|<span data-ttu-id="2011d-116">/config [path]</span><span class="sxs-lookup"><span data-stu-id="2011d-116">/config [path]</span></span>  <br/> |<span data-ttu-id="2011d-117">Especifica el archivo Config.xml que usa el programa de instalación durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="2011d-117">Specifies the Config.xml file that Setup uses during the installation.</span></span> <span data-ttu-id="2011d-118">Use la opción /config para especificar el archivo Config.xml personalizado para las instalaciones de Skype Empresarial, por ejemplo:  `/config \\server\share\Skype15\Skype.WW\Config.xml`</span><span class="sxs-lookup"><span data-stu-id="2011d-118">Use the /config option to specify the Config.xml file you customized for Skype for Business installations, for example:  `/config \\server\share\Skype15\Skype.WW\Config.xml`</span></span> <br/> |
|<span data-ttu-id="2011d-119">/modify Skype</span><span class="sxs-lookup"><span data-stu-id="2011d-119">/modify Skype</span></span>  <br/> |<span data-ttu-id="2011d-120">Se utiliza con un archivo Config.xml modificado para ejecutar el programa de instalación en modo de mantenimiento y hacer cambios en una instalación de Office existente.</span><span class="sxs-lookup"><span data-stu-id="2011d-120">Used with a modified Config.xml file to run Setup in maintenance mode and make changes to an existing Office installation.</span></span> <span data-ttu-id="2011d-121">Por ejemplo, puede usar la opción /modify para agregar o quitar características de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="2011d-121">For example, you can use the /modify option to add or remove Skype for Business features.</span></span>  <br/> |
|<span data-ttu-id="2011d-122">/repair Skype</span><span class="sxs-lookup"><span data-stu-id="2011d-122">/repair Skype</span></span>  <br/> |<span data-ttu-id="2011d-123">Ejecuta el programa de instalación desde el equipo del usuario para reparar Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="2011d-123">Runs Setup from the user's computer to repair Skype for Business.</span></span>  <br/> |
|<span data-ttu-id="2011d-124">/uninstall Skype</span><span class="sxs-lookup"><span data-stu-id="2011d-124">/uninstall Skype</span></span>  <br/> |<span data-ttu-id="2011d-125">Ejecuta el programa de instalación para quitar Skype Empresarial del equipo del usuario.</span><span class="sxs-lookup"><span data-stu-id="2011d-125">Runs Setup to remove Skype for Business from the user's computer.</span></span>  <br/> |
   


