---
title: Usar la herramienta de personalización de Office (OCT) en Skype empresarial Server
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
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: 'Resumen: Cómo usar la herramienta de personalización de Office con el cliente de Skype empresarial.'
ms.openlocfilehash: d5b9e5363f56842675831c4b3c0fe3582fb6d02a
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768453"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a><span data-ttu-id="6d21c-103">Usar la herramienta de personalización de Office (OCT) en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="6d21c-103">Use the Office Customization Tool (OCT) in Skype for Business Server</span></span>
 
<span data-ttu-id="6d21c-104">**Resumen:** Cómo usar la herramienta de personalización de Office con el cliente de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="6d21c-104">**Summary:** How to use the Office Customization Tool with the Skype for Business client.</span></span>
  
<span data-ttu-id="6d21c-105">La herramienta de personalización de Office (OCT) forma parte del programa de instalación y es la herramienta recomendada para muchas personalizaciones.</span><span class="sxs-lookup"><span data-stu-id="6d21c-105">The Office Customization Tool (OCT) is part of the Setup program and is the recommended tool for many customizations.</span></span> <span data-ttu-id="6d21c-106">Al usar la OCT, se personaliza Office y se guardan las personalizaciones en un archivo. MSP de personalización del programa de instalación.</span><span class="sxs-lookup"><span data-stu-id="6d21c-106">By using the OCT, you customize Office and save your customizations in a Setup customization .msp file.</span></span> <span data-ttu-id="6d21c-107">El archivo se coloca en la carpeta actualizaciones del punto de instalación de red.</span><span class="sxs-lookup"><span data-stu-id="6d21c-107">You place the file in the Updates folder on the network installation point.</span></span> <span data-ttu-id="6d21c-108">Al instalar Office, el programa de instalación busca un archivo de personalización de la configuración en la carpeta actualizaciones y aplica las personalizaciones.</span><span class="sxs-lookup"><span data-stu-id="6d21c-108">When you install Office, Setup looks for a Setup customization file in the Updates folder and applies the customizations.</span></span> <span data-ttu-id="6d21c-109">La carpeta actualizaciones solo se puede usar para implementar actualizaciones de software durante una instalación inicial de Office.</span><span class="sxs-lookup"><span data-stu-id="6d21c-109">The Updates folder can be used only to deploy software updates during an initial installation of Office.</span></span>
  
<span data-ttu-id="6d21c-110">La OCT es parte de la configuración y solo se usa para las versiones con licencia por volumen del producto.</span><span class="sxs-lookup"><span data-stu-id="6d21c-110">The OCT is part of setup and it is only used for volume licensed versions of the product.</span></span> <span data-ttu-id="6d21c-111">Para ejecutar la OCT, escriba `setup.exe /admin` en la línea de comandos de la raíz del punto de instalación de red que contiene los archivos de origen de Office.</span><span class="sxs-lookup"><span data-stu-id="6d21c-111">You run the OCT by typing  `setup.exe /admin` at the command line from the root of the network installation point that contains the Office source files.</span></span> <span data-ttu-id="6d21c-112">Por ejemplo, use lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6d21c-112">For example, use the following:</span></span>
  
 ```console
\\server\share\Office15\setup.exe /admin
```
  
<span data-ttu-id="6d21c-113">Los administradores usan la OCT para crear un archivo. MSP de personalización del programa de instalación y pueden personalizar las siguientes áreas:</span><span class="sxs-lookup"><span data-stu-id="6d21c-113">Administrators use the OCT to create a setup customization .msp file and can customize the following areas:</span></span>
  
- <span data-ttu-id="6d21c-114">**Configuración** Se usa para especificar la ubicación de instalación predeterminada en el cliente y el nombre de la organización predeterminada, otras fuentes de instalación en red, la clave de producto, el contrato de licencia para el usuario final, el nivel de presentación, las versiones anteriores de Office que se van a quitar;</span><span class="sxs-lookup"><span data-stu-id="6d21c-114">**Setup** Used to specify default installation location on the client and default organization name, additional network installation sources, product key, end-user license agreement, display level, earlier versions of Office to remove, custom programs to run during installation, security settings, and Setup properties.</span></span>
    
- <span data-ttu-id="6d21c-115">**Características** Se usa para configurar las opciones de usuario y personalizar la instalación de las características de Office.</span><span class="sxs-lookup"><span data-stu-id="6d21c-115">**Features** Used to configure user settings and to customize how Office features are installed.</span></span> <span data-ttu-id="6d21c-116">Los administradores pueden usar la OCT para especificar los valores iniciales predeterminados de la aplicación de Office para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="6d21c-116">Administrators can use the OCT to specify initial default values of Office application settings for users.</span></span> <span data-ttu-id="6d21c-117">Los usuarios pueden modificar la mayoría de las opciones después de la instalación.</span><span class="sxs-lookup"><span data-stu-id="6d21c-117">Users can modify most of the settings after the installation.</span></span>
    
- <span data-ttu-id="6d21c-118">**Contenido adicional** Se usa para agregar o quitar archivos, agregar o quitar entradas del registro y configurar accesos directos.</span><span class="sxs-lookup"><span data-stu-id="6d21c-118">**Additional content** Used to add or remove files, add or remove registry entries, and configure shortcuts.</span></span>
    
- <span data-ttu-id="6d21c-119">**Outlook** Se usa para personalizar el perfil predeterminado de Outlook de un usuario, especificar la configuración de Exchange, agregar cuentas, quitar cuentas y exportar configuraciones, y especificar grupos de envío y recepción.</span><span class="sxs-lookup"><span data-stu-id="6d21c-119">**Outlook** Used to customize a user's default Outlook profile, specify Exchange settings, add accounts, remove accounts and export settings, and specify Send\Receive groups.</span></span>
    
<span data-ttu-id="6d21c-120">Para obtener más información sobre la OCT, consulte [usar la Oct para personalizar Office 2013](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)).</span><span class="sxs-lookup"><span data-stu-id="6d21c-120">For information about the OCT, see [Use the OCT to customize Office 2013](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)).</span></span> <span data-ttu-id="6d21c-121">Tenga en cuenta que esta información también se aplica a versiones posteriores de Office.</span><span class="sxs-lookup"><span data-stu-id="6d21c-121">Note that this information also applies to later versions of Office.</span></span>
  

