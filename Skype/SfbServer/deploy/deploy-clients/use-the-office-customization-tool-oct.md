---
title: Use la herramienta de personalización de Office (OCT) en Skype para Business Server
ms.reviewer: ''
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: 'Resumen: Cómo usar la herramienta de personalización de Office con el Skype para clientes empresariales.'
ms.openlocfilehash: 6530199ce86914feae6b44ae8b73137263fcd6a2
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32207905"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a><span data-ttu-id="d4ac8-103">Use la herramienta de personalización de Office (OCT) en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="d4ac8-103">Use the Office Customization Tool (OCT) in Skype for Business Server</span></span>
 
<span data-ttu-id="d4ac8-104">**Resumen:** Cómo usar la herramienta de personalización de Office con el Skype para clientes empresariales.</span><span class="sxs-lookup"><span data-stu-id="d4ac8-104">**Summary:** How to use the Office Customization Tool with the Skype for Business client.</span></span>
  
<span data-ttu-id="d4ac8-105">La herramienta de personalización de Office (OCT) es parte del programa de instalación y es la herramienta recomendada para muchas personalizaciones.</span><span class="sxs-lookup"><span data-stu-id="d4ac8-105">The Office Customization Tool (OCT) is part of the Setup program and is the recommended tool for many customizations.</span></span> <span data-ttu-id="d4ac8-106">Mediante el uso de la herramienta OCT, personalización de Office y guardar las personalizaciones en un archivo .msp de personalización.</span><span class="sxs-lookup"><span data-stu-id="d4ac8-106">By using the OCT, you customize Office and save your customizations in a Setup customization .msp file.</span></span> <span data-ttu-id="d4ac8-107">Coloque el archivo en la carpeta actualizaciones del punto de instalación de red.</span><span class="sxs-lookup"><span data-stu-id="d4ac8-107">You place the file in the Updates folder on the network installation point.</span></span> <span data-ttu-id="d4ac8-108">Al instalar Office, el programa de instalación busca un archivo de personalización del programa de instalación en la carpeta actualizaciones y aplica las personalizaciones.</span><span class="sxs-lookup"><span data-stu-id="d4ac8-108">When you install Office, Setup looks for a Setup customization file in the Updates folder and applies the customizations.</span></span> <span data-ttu-id="d4ac8-109">La carpeta de actualizaciones se puede usar solo para implementar actualizaciones de software durante la instalación inicial de Office.</span><span class="sxs-lookup"><span data-stu-id="d4ac8-109">The Updates folder can be used only to deploy software updates during an initial installation of Office.</span></span>
  
<span data-ttu-id="d4ac8-110">La herramienta OCT forma parte del programa de instalación y sólo se utiliza para las versiones de licencia por volumen del producto.</span><span class="sxs-lookup"><span data-stu-id="d4ac8-110">The OCT is part of setup and it is only used for volume licensed versions of the product.</span></span> <span data-ttu-id="d4ac8-111">Ejecute la herramienta OCT escribiendo `setup.exe /admin` en la línea de comandos desde la raíz del punto de instalación de red que contiene la oficina de los archivos de origen.</span><span class="sxs-lookup"><span data-stu-id="d4ac8-111">You run the OCT by typing  `setup.exe /admin` at the command line from the root of the network installation point that contains the Office source files.</span></span> <span data-ttu-id="d4ac8-112">Por ejemplo, use lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d4ac8-112">For example, use the following:</span></span>
  
 ```
\\server\share\Office15\setup.exe /admin
```
  
<span data-ttu-id="d4ac8-113">Los administradores usan la herramienta OCT para crear un archivo .msp de personalización y puede personalizar las siguientes áreas:</span><span class="sxs-lookup"><span data-stu-id="d4ac8-113">Administrators use the OCT to create a setup customization .msp file and can customize the following areas:</span></span>
  
- <span data-ttu-id="d4ac8-114">**Programa de instalación** Se utiliza para especificar la ubicación de instalación predeterminada en el nombre de la organización de cliente y de forma predeterminada, los orígenes de instalación de red adicionales, clave de producto, contrato de licencia para el usuario final, mostrar el nivel de versiones anteriores de Office para quitar programas personalizados que se ejecutan durante instalación, configuración de seguridad y las propiedades del programa de instalación.</span><span class="sxs-lookup"><span data-stu-id="d4ac8-114">**Setup** Used to specify default installation location on the client and default organization name, additional network installation sources, product key, end-user license agreement, display level, earlier versions of Office to remove, custom programs to run during installation, security settings, and Setup properties.</span></span>
    
- <span data-ttu-id="d4ac8-115">**Características** Se usa para establecer la configuración de usuario y para personalizar el modo en que se instalan las características de Office.</span><span class="sxs-lookup"><span data-stu-id="d4ac8-115">**Features** Used to configure user settings and to customize how Office features are installed.</span></span> <span data-ttu-id="d4ac8-116">Los administradores pueden usar la OCT para especificar los valores iniciales predeterminados de la aplicación de Office para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="d4ac8-116">Administrators can use the OCT to specify initial default values of Office application settings for users.</span></span> <span data-ttu-id="d4ac8-117">Los usuarios pueden modificar la mayoría de las opciones después de la instalación.</span><span class="sxs-lookup"><span data-stu-id="d4ac8-117">Users can modify most of the settings after the installation.</span></span>
    
- <span data-ttu-id="d4ac8-118">**Contenido adicional** Se usa para agregar o quitar archivos, agregar o quitar entradas del registro y configurar accesos directos.</span><span class="sxs-lookup"><span data-stu-id="d4ac8-118">**Additional content** Used to add or remove files, add or remove registry entries, and configure shortcuts.</span></span>
    
- <span data-ttu-id="d4ac8-119">**Outlook** Usar para personalizar el perfil predeterminado de Outlook de un usuario, especificar la configuración de Exchange, agregar cuentas, quitar cuentas y exportar la configuración de y especificar grupos de envío o recepción.</span><span class="sxs-lookup"><span data-stu-id="d4ac8-119">**Outlook** Used to customize a user's default Outlook profile, specify Exchange settings, add accounts, remove accounts and export settings, and specify Send\Receive groups.</span></span>
    
<span data-ttu-id="d4ac8-120">Para obtener información acerca de la herramienta OCT, vea [utilizar la herramienta OCT para personalizar Office 2013](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)).</span><span class="sxs-lookup"><span data-stu-id="d4ac8-120">For information about the OCT, see [Use the OCT to customize Office 2013](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)).</span></span> <span data-ttu-id="d4ac8-121">Tenga en cuenta que esta información también se aplica a las versiones posteriores de Office.</span><span class="sxs-lookup"><span data-stu-id="d4ac8-121">Note that this information also applies to later versions of Office.</span></span>
  

