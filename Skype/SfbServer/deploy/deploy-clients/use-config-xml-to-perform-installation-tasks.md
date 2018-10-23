---
title: Usar Config.xml para realizar tareas de instalación en Skype para clientes empresariales
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: 'Resumen: cómo usar el archivo Config.xml para especificar instrucciones de instalación adicionales.'
ms.openlocfilehash: dfb6625146261b1bbf22e0f563717899c68beaae
ms.sourcegitcommit: d3c3467320a2928d3bad14a1a44a31ee5a9a988c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2018
ms.locfileid: "25699561"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a><span data-ttu-id="7362f-103">Usar Config.xml para realizar tareas de instalación en Skype para clientes empresariales</span><span class="sxs-lookup"><span data-stu-id="7362f-103">Use Config.xml to perform installation tasks in Skype for Business clients</span></span>

<span data-ttu-id="7362f-104">**Resumen:** cómo usar el archivo Config.xml para especificar instrucciones de instalación adicionales.</span><span class="sxs-lookup"><span data-stu-id="7362f-104">**Summary:** How to use the Config.xml file to specify additional installation instructions.</span></span>

<span data-ttu-id="7362f-p101">Aunque la Herramienta de personalización de Office (OCT) es la principal herramienta de instalación personalizada, los administradores pueden usar el archivo Config.xml para especificar instrucciones de instalación adicionales que no estén disponibles en la OCT. Las personalizaciones que se describen a continuación solo se pueden llevar a cabo mediante el archivo Config.xml:</span><span class="sxs-lookup"><span data-stu-id="7362f-p101">Although the Office Customization Tool (OCT) is the primary tool for customization installation, administrators can use the Config.xml file to specify additional installation instructions that are not available in the OCT. The following customizations can only be made by using the Config.xml file:</span></span>

- <span data-ttu-id="7362f-107">Especifique la ruta de acceso del punto de instalación de red.</span><span class="sxs-lookup"><span data-stu-id="7362f-107">Specify the path of the network installation point.</span></span>

- <span data-ttu-id="7362f-108">Seleccione los productos que desea instalar.</span><span class="sxs-lookup"><span data-stu-id="7362f-108">Select the products to install.</span></span>

- <span data-ttu-id="7362f-109">Configure el registro y la ubicación del archivo de personalización de la instalación y las actualizaciones de software.</span><span class="sxs-lookup"><span data-stu-id="7362f-109">Configure logging and the location of the Setup customization file and software updates.</span></span>

- <span data-ttu-id="7362f-110">Especifique las opciones de instalación como, por ejemplo, el nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="7362f-110">Specify installation options, such as user name.</span></span>

- <span data-ttu-id="7362f-111">Copie el origen de instalación local (LIS) en el equipo del usuario sin instalar Office.</span><span class="sxs-lookup"><span data-stu-id="7362f-111">Copy the local installation source (LIS) to the user's computer without installing Office.</span></span>

- <span data-ttu-id="7362f-112">Agregue o quite idiomas de la instalación.</span><span class="sxs-lookup"><span data-stu-id="7362f-112">Add or remove languages from the installation.</span></span>

<span data-ttu-id="7362f-113">Se recomienda que utilice el archivo Config.xml para configurar Skype para la instalación silenciosa de negocio.</span><span class="sxs-lookup"><span data-stu-id="7362f-113">We recommend that you use the Config.xml file to configure Skype for Business silent installation.</span></span> 

<span data-ttu-id="7362f-114">De forma predeterminada, el archivo Config.xml que se almacena en la carpeta de producto principal (por ejemplo, \ _producto_. WW) dirige el programa de instalación que instale ese producto.</span><span class="sxs-lookup"><span data-stu-id="7362f-114">By default, the Config.xml file that is stored in the core product folder (for example, \ _product_.WW) directs Setup to install that product.</span></span> <span data-ttu-id="7362f-115">Por ejemplo, el archivo Config.xml en la carpeta siguiente instala Skype para la empresa:</span><span class="sxs-lookup"><span data-stu-id="7362f-115">For example, the Config.xml file in the following folder installs Skype for Business:</span></span>

- <span data-ttu-id="7362f-116">\\server\share\Skype15\Skype.WW \Config.xml</span><span class="sxs-lookup"><span data-stu-id="7362f-116">\\server\share\Skype15\Skype.WW \Config.xml</span></span>

<span data-ttu-id="7362f-117">Los elementos de Config.xml usados con más frecuencia para Skype para la instalación de negocio se enumeran en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="7362f-117">The Config.xml elements most commonly used for Skype for Business installation are listed in the following table.</span></span>

<span data-ttu-id="7362f-118">**Elementos de Config.xml**</span><span class="sxs-lookup"><span data-stu-id="7362f-118">**Config.xml elements**</span></span>


| <span data-ttu-id="7362f-119">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="7362f-119">**Element**</span></span>              | <span data-ttu-id="7362f-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="7362f-120">**Description**</span></span>                                                                                                                                                                                                                                                                                         |
|:-------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="7362f-121">Configuración</span><span class="sxs-lookup"><span data-stu-id="7362f-121">Configuration</span></span>  <br/>     | <span data-ttu-id="7362f-p103">Elemento de nivel superior (obligatorio). Contiene el atributo del producto, como Product=Lync (esto funcionará con clientes de Skype Empresarial)</span><span class="sxs-lookup"><span data-stu-id="7362f-p103">Top-level element (required). Contains the Product attribute, for example: Product=Lync (This will work for Skype for Business clients)</span></span>  <br/>                                                                                                                                                          |
| <span data-ttu-id="7362f-124">OptionState</span><span class="sxs-lookup"><span data-stu-id="7362f-124">OptionState</span></span>  <br/>       | <span data-ttu-id="7362f-125">Especifica cómo se controlan las características específicas del producto durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="7362f-125">Specifies how specific product features are handled during installation.</span></span> <span data-ttu-id="7362f-126">Use los siguientes atributos para impedir la instalación de servicios de conectividad empresarial, que incluye los componentes compartidos que interferirán con Outlook:</span><span class="sxs-lookup"><span data-stu-id="7362f-126">Use the following attributes to prevent installation of Business Connectivity Services, which includes shared components that interfere with Outlook:</span></span> <br/>  <span data-ttu-id="7362f-127">Id="LOBiMain"</span><span class="sxs-lookup"><span data-stu-id="7362f-127">Id="LOBiMain"</span></span> <br/>  <span data-ttu-id="7362f-128">State="Absent"</span><span class="sxs-lookup"><span data-stu-id="7362f-128">State="Absent"</span></span> <br/>  <span data-ttu-id="7362f-129">Children="Force"</span><span class="sxs-lookup"><span data-stu-id="7362f-129">Children="Force"</span></span> <br/> |
| <span data-ttu-id="7362f-130">Pantalla</span><span class="sxs-lookup"><span data-stu-id="7362f-130">Display</span></span>  <br/>           | <span data-ttu-id="7362f-p105">El nivel de interfaz de usuario que el programa de instalación muestra al usuario. Los atributos típicos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="7362f-p105">The level of UI that Setup displays to the user. Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="7362f-133">CompletionNotice = "Yes"</span><span class="sxs-lookup"><span data-stu-id="7362f-133">CompletionNotice="Yes"</span></span>                                                                                                                                                                                |
| <span data-ttu-id="7362f-134">Registro</span><span class="sxs-lookup"><span data-stu-id="7362f-134">Logging</span></span>  <br/>           | <span data-ttu-id="7362f-p106">Opciones para el tipo de registro que realiza el programa de instalación. Los atributos típicos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="7362f-p106">Options for the kind of logging that Setup performs. Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="7362f-137">Tipo = "Off"</span><span class="sxs-lookup"><span data-stu-id="7362f-137">Type ="Off"</span></span>                                                                                                                                                                                       |
| <span data-ttu-id="7362f-138">Configuración</span><span class="sxs-lookup"><span data-stu-id="7362f-138">Setting</span></span>  <br/>           | <span data-ttu-id="7362f-p107">Especifica los valores de propiedades de Windows Installer. Los atributos típicos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="7362f-p107">Specifies values for Windows Installer properties. Typical attributes include the following: </span></span><br/>  <span data-ttu-id="7362f-141">Setting Id = " *nombre*" (el nombre de la propiedad de Windows Installer)</span><span class="sxs-lookup"><span data-stu-id="7362f-141">Setting Id=" *name*" (the name of the Windows Installer property)</span></span>  <br/>  <span data-ttu-id="7362f-142">Valor = " *valor*" (el valor para asignar a la propiedad)</span><span class="sxs-lookup"><span data-stu-id="7362f-142">Value=" *value*" (the value to assign to the property)</span></span>  <br/>                                                             |
| <span data-ttu-id="7362f-143">DistributionPoint</span><span class="sxs-lookup"><span data-stu-id="7362f-143">DistributionPoint</span></span>  <br/> | <span data-ttu-id="7362f-p108">La ruta de acceso completa del punto de instalación de red desde la que se ejecuta la instalación. Incluye el atributo de ubicación:</span><span class="sxs-lookup"><span data-stu-id="7362f-p108">The fully qualified path of the network installation point from which the installation is to run. Includes the Location attribute: </span></span><br/>  <span data-ttu-id="7362f-146">Ubicación = " *ruta de acceso*"</span><span class="sxs-lookup"><span data-stu-id="7362f-146">Location=" *path*"</span></span>  <br/>                                                                                                                                     |

<span data-ttu-id="7362f-147">En el ejemplo siguiente se muestra un archivo Config.xml para una instalación silenciosa típica de la Skype para clientes empresariales.</span><span class="sxs-lookup"><span data-stu-id="7362f-147">The following example shows a Config.xml file for a typical silent installation of the Skype for Business client.</span></span> 

```
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

<span data-ttu-id="7362f-148">Obtener información detallada acerca de cómo utilizar el archivo Config.xml para realizar tareas de instalación y mantenimiento de Office está disponible en [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514).</span><span class="sxs-lookup"><span data-stu-id="7362f-148">Detailed information about using the Config.xml file to perform Office installation and maintenance tasks is available at [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514).</span></span>

## <a name="to-customize-the-configxml-file"></a><span data-ttu-id="7362f-149">Para personalizar el archivo Config.xml</span><span class="sxs-lookup"><span data-stu-id="7362f-149">To customize the Config.xml file</span></span>

1. <span data-ttu-id="7362f-150">Abra el archivo Config.xml usando una herramienta de edición de texto como el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="7362f-150">Open the Config.xml file by using a text editor tool, such as Notepad.</span></span>

2. <span data-ttu-id="7362f-151">Localice las líneas que contienen los elementos que desee cambiar.</span><span class="sxs-lookup"><span data-stu-id="7362f-151">Locate the lines that contain the elements you want to change.</span></span>

3. <span data-ttu-id="7362f-152">Modifique la entrada de elemento con las opciones silenciosas que desea usar.</span><span class="sxs-lookup"><span data-stu-id="7362f-152">Modify the element entry with the silent options that you want to use.</span></span> <span data-ttu-id="7362f-153">Asegúrese de que quita los delimitadores de comentarios, "\<!--" y "--\>".</span><span class="sxs-lookup"><span data-stu-id="7362f-153">Make sure that you remove the comment delimiters, "\<!--" and "--\>".</span></span> <span data-ttu-id="7362f-154">Por ejemplo, utilice la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="7362f-154">For example, use the following syntax:</span></span>

   <pre>
   < DistributionPoint Location="\\server\share\Skype15" />
   </pre>

4. <span data-ttu-id="7362f-155">Guarde el archivo Config.xml.</span><span class="sxs-lookup"><span data-stu-id="7362f-155">Save the Config.xml file.</span></span>


