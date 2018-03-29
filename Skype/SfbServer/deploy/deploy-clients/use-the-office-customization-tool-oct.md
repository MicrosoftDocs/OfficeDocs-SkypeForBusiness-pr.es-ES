---
title: Usar la Herramienta de personalización de Office (OCT) en Skype Empresarial Server 2015
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 10/20/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: 'Resumen: Cómo utilizar la herramienta de personalización de Office con el Skype para cliente de empresa.'
ms.openlocfilehash: b0e8dd399af7a75a6f575d554cbe6c25c4e8ffd3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server-2015"></a><span data-ttu-id="c207a-103">Usar la Herramienta de personalización de Office (OCT) en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="c207a-103">Use the Office Customization Tool (OCT) in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c207a-104">**Resumen:** Cómo utilizar la herramienta de personalización de Office con el Skype para cliente de empresa.</span><span class="sxs-lookup"><span data-stu-id="c207a-104">**Summary:** How to use the Office Customization Tool with the Skype for Business client.</span></span>
  
<span data-ttu-id="c207a-105">La herramienta de personalización de Office (OCT) forma parte del programa de instalación y es la herramienta recomendada para muchas personalizaciones.</span><span class="sxs-lookup"><span data-stu-id="c207a-105">The Office Customization Tool (OCT) is part of the Setup program and is the recommended tool for many customizations.</span></span> <span data-ttu-id="c207a-106">Mediante el uso de la herramienta OCT, personalizar Office y guardar las personalizaciones en un archivo .msp de personalización de instalación.</span><span class="sxs-lookup"><span data-stu-id="c207a-106">By using the OCT, you customize Office and save your customizations in a Setup customization .msp file.</span></span> <span data-ttu-id="c207a-107">Coloque el archivo en la carpeta actualizaciones del punto de instalación de red.</span><span class="sxs-lookup"><span data-stu-id="c207a-107">You place the file in the Updates folder on the network installation point.</span></span> <span data-ttu-id="c207a-108">Al instalar Office, el programa de instalación busca un archivo de personalización del programa de instalación en la carpeta actualizaciones y aplica las personalizaciones.</span><span class="sxs-lookup"><span data-stu-id="c207a-108">When you install Office, Setup looks for a Setup customization file in the Updates folder and applies the customizations.</span></span> <span data-ttu-id="c207a-109">La carpeta de actualizaciones puede utilizarse sólo para implementar actualizaciones de software durante una instalación inicial de Office.</span><span class="sxs-lookup"><span data-stu-id="c207a-109">The Updates folder can be used only to deploy software updates during an initial installation of Office.</span></span>
  
<span data-ttu-id="c207a-110">Los PTU es parte de la instalación y se utiliza únicamente para las versiones de licencia por volumen del producto.</span><span class="sxs-lookup"><span data-stu-id="c207a-110">The OCT is part of setup and it is only used for volume licensed versions of the product.</span></span> <span data-ttu-id="c207a-111">Para ejecutar OCT escribiendo `setup.exe /admin` en la línea de comandos desde la raíz del punto de instalación de red que contiene la oficina de los archivos de origen.</span><span class="sxs-lookup"><span data-stu-id="c207a-111">You run the OCT by typing  `setup.exe /admin` at the command line from the root of the network installation point that contains the Office source files.</span></span> <span data-ttu-id="c207a-112">Por ejemplo, use lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c207a-112">For example, use the following:</span></span>
  
 `\\server\share\Office15\setup.exe /admin`
  
<span data-ttu-id="c207a-113">Los administradores utilizan la herramienta OCT para crear un archivo .msp de personalización de instalación y puede personalizar las siguientes áreas:</span><span class="sxs-lookup"><span data-stu-id="c207a-113">Administrators use the OCT to create a setup customization .msp file and can customize the following areas:</span></span>
  
- <span data-ttu-id="c207a-114">**Programa de instalación** Se utiliza para especificar la ubicación de instalación predeterminada en el cliente y organización el nombre predeterminado, los orígenes de instalación de red adicional, clave de producto, contrato de licencia de usuario final, Mostrar nivel de versiones anteriores de Office para quitar los programas personalizados que se ejecutarán durante instalación, configuración de seguridad y las propiedades de instalación.</span><span class="sxs-lookup"><span data-stu-id="c207a-114">**Setup** Used to specify default installation location on the client and default organization name, additional network installation sources, product key, end-user license agreement, display level, earlier versions of Office to remove, custom programs to run during installation, security settings, and Setup properties.</span></span>
    
- <span data-ttu-id="c207a-115">**Características** Se utiliza para configurar opciones de usuario y personalizar cómo se instalan las características de Office.</span><span class="sxs-lookup"><span data-stu-id="c207a-115">**Features** Used to configure user settings and to customize how Office features are installed.</span></span> <span data-ttu-id="c207a-116">Los administradores pueden usar la OCT para especificar los valores iniciales predeterminados de la aplicación de Office para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="c207a-116">Administrators can use the OCT to specify initial default values of Office application settings for users.</span></span> <span data-ttu-id="c207a-117">Los usuarios pueden modificar la mayoría de las opciones después de la instalación.</span><span class="sxs-lookup"><span data-stu-id="c207a-117">Users can modify most of the settings after the installation.</span></span>
    
- <span data-ttu-id="c207a-118">**Contenido adicional** Se utiliza para agregar o quitar archivos, agregar o quitar entradas del registro y configurar accesos directos.</span><span class="sxs-lookup"><span data-stu-id="c207a-118">**Additional content** Used to add or remove files, add or remove registry entries, and configure shortcuts.</span></span>
    
- <span data-ttu-id="c207a-119">**Outlook** Se utiliza para personalizar el perfil predeterminado de Outlook de un usuario, especificar la configuración de Exchange, agregar cuentas, quitar cuentas y exportar la configuración y especificar grupos de envío y recepción.</span><span class="sxs-lookup"><span data-stu-id="c207a-119">**Outlook** Used to customize a user's default Outlook profile, specify Exchange settings, add accounts, remove accounts and export settings, and specify Send\Receive groups.</span></span>
    
<span data-ttu-id="c207a-120">Para obtener información acerca de los PTU, consulte [utilizar la herramienta OCT para personalizar Office 2013](https://technet.microsoft.com/library/cc179132.aspx).</span><span class="sxs-lookup"><span data-stu-id="c207a-120">For information about the OCT, see [Use the OCT to customize Office 2013](https://technet.microsoft.com/library/cc179132.aspx).</span></span> <span data-ttu-id="c207a-121">Tenga en cuenta que esta información también se aplica a Office 2016.</span><span class="sxs-lookup"><span data-stu-id="c207a-121">Note that this information also applies to Office 2016.</span></span>
  

