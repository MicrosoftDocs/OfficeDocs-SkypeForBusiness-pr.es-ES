---
title: Usar Config.xml para realizar tareas de instalación en Skype Empresarial Server 2015
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: 'Resumen: Cómo utilizar el archivo Config.xml para especificar las instrucciones de instalación adicionales.'
ms.openlocfilehash: f55683d672df890be8baf0ac7ca50b3170faf3d2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-server-2015"></a><span data-ttu-id="17e16-103">Usar Config.xml para realizar tareas de instalación en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="17e16-103">Use Config.xml to perform installation tasks in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="17e16-104">**Resumen:** cómo usar el archivo Config.xml para especificar instrucciones de instalación adicionales.</span><span class="sxs-lookup"><span data-stu-id="17e16-104">**Summary:** How to use the Config.xml file to specify additional installation instructions.</span></span>
  
<span data-ttu-id="17e16-p101">Aunque la Herramienta de personalización de Office (OCT) es la principal herramienta de instalación personalizada, los administradores pueden usar el archivo Config.xml para especificar instrucciones de instalación adicionales que no estén disponibles en la OCT. Las personalizaciones que se describen a continuación solo se pueden llevar a cabo mediante el archivo Config.xml:</span><span class="sxs-lookup"><span data-stu-id="17e16-p101">Although the Office Customization Tool (OCT) is the primary tool for customization installation, administrators can use the Config.xml file to specify additional installation instructions that are not available in the OCT. The following customizations can only be made by using the Config.xml file:</span></span>
  
- <span data-ttu-id="17e16-107">Especifique la ruta de acceso del punto de instalación de red.</span><span class="sxs-lookup"><span data-stu-id="17e16-107">Specify the path of the network installation point.</span></span>
    
- <span data-ttu-id="17e16-108">Seleccione los productos que desea instalar.</span><span class="sxs-lookup"><span data-stu-id="17e16-108">Select the products to install.</span></span>
    
- <span data-ttu-id="17e16-109">Configure el registro y la ubicación del archivo de personalización de la instalación y las actualizaciones de software.</span><span class="sxs-lookup"><span data-stu-id="17e16-109">Configure logging and the location of the Setup customization file and software updates.</span></span>
    
- <span data-ttu-id="17e16-110">Especifique las opciones de instalación como, por ejemplo, el nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="17e16-110">Specify installation options, such as user name.</span></span>
    
- <span data-ttu-id="17e16-111">Copie el origen de instalación local (LIS) en el equipo del usuario sin instalar Office.</span><span class="sxs-lookup"><span data-stu-id="17e16-111">Copy the local installation source (LIS) to the user's computer without installing Office.</span></span>
    
- <span data-ttu-id="17e16-112">Agregue o quite idiomas de la instalación.</span><span class="sxs-lookup"><span data-stu-id="17e16-112">Add or remove languages from the installation.</span></span>
    
<span data-ttu-id="17e16-113">Se recomienda que utilice el archivo Config.xml para configurar Skype para la instalación silenciosa del negocio.</span><span class="sxs-lookup"><span data-stu-id="17e16-113">We recommend that you use the Config.xml file to configure Skype for Business silent installation.</span></span> 
  
<span data-ttu-id="17e16-114">De forma predeterminada, el archivo Config.xml que se almacena en la carpeta del producto principal (por ejemplo, \ _producto_. WW) dirige el programa de instalación instale dicho producto.</span><span class="sxs-lookup"><span data-stu-id="17e16-114">By default, the Config.xml file that is stored in the core product folder (for example, \ _product_.WW) directs Setup to install that product.</span></span> <span data-ttu-id="17e16-115">Por ejemplo, el archivo Config.xml en la carpeta siguiente instala Skype para empresas:</span><span class="sxs-lookup"><span data-stu-id="17e16-115">For example, the Config.xml file in the following folder installs Skype for Business:</span></span>
  
- <span data-ttu-id="17e16-116">\\server\share\Skype15\Skype.WW \Config.xml</span><span class="sxs-lookup"><span data-stu-id="17e16-116">\\server\share\Skype15\Skype.WW \Config.xml</span></span>
    
<span data-ttu-id="17e16-117">Los elementos de Config.xml usados más comúnmente para Skype para la instalación de negocios se enumeran en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="17e16-117">The Config.xml elements most commonly used for Skype for Business installation are listed in the following table.</span></span>
  
<span data-ttu-id="17e16-118">**Elementos de config.Xml**</span><span class="sxs-lookup"><span data-stu-id="17e16-118">**Config.xml elements**</span></span>

|<span data-ttu-id="17e16-119">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="17e16-119">**Element**</span></span>|<span data-ttu-id="17e16-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="17e16-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="17e16-121">Configuración</span><span class="sxs-lookup"><span data-stu-id="17e16-121">Configuration</span></span>  <br/> |<span data-ttu-id="17e16-p103">Elemento de nivel superior (obligatorio). Contiene el atributo del producto, como Product=Lync (esto funcionará con clientes de Skype Empresarial)</span><span class="sxs-lookup"><span data-stu-id="17e16-p103">Top-level element (required). Contains the Product attribute, for example: Product=Lync (This will work for Skype for Business clients)</span></span>  <br/> |
|<span data-ttu-id="17e16-124">OptionState</span><span class="sxs-lookup"><span data-stu-id="17e16-124">OptionState</span></span>  <br/> | <span data-ttu-id="17e16-125">Especifica cómo se controlan las características específicas del producto durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="17e16-125">Specifies how specific product features are handled during installation.</span></span> <span data-ttu-id="17e16-126">Utilice los siguientes atributos para impedir la instalación de Servicios de conectividad empresarial, que incluye los componentes compartidos que interfieren con 2016 de Outlook:</span><span class="sxs-lookup"><span data-stu-id="17e16-126">Use the following attributes to prevent installation of Business Connectivity Services, which includes shared components that interfere with Outlook 2016:</span></span> <br/>  <span data-ttu-id="17e16-127">ID = "LOBiMain"</span><span class="sxs-lookup"><span data-stu-id="17e16-127">Id="LOBiMain"</span></span> <br/>  <span data-ttu-id="17e16-128">State="Absent"</span><span class="sxs-lookup"><span data-stu-id="17e16-128">State="Absent"</span></span> <br/>  <span data-ttu-id="17e16-129">Children="Force"</span><span class="sxs-lookup"><span data-stu-id="17e16-129">Children="Force"</span></span> <br/> |
|<span data-ttu-id="17e16-130">Pantalla</span><span class="sxs-lookup"><span data-stu-id="17e16-130">Display</span></span>  <br/> | <span data-ttu-id="17e16-p105">El nivel de interfaz de usuario que el programa de instalación muestra al usuario. Los atributos típicos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="17e16-p105">The level of UI that Setup displays to the user. Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="17e16-133">CompletionNotice = "Yes"</span><span class="sxs-lookup"><span data-stu-id="17e16-133">CompletionNotice="Yes"</span></span> | <span data-ttu-id="17e16-134">"No"(default)</span><span class="sxs-lookup"><span data-stu-id="17e16-134">"No"(default)</span></span> <br/>  <span data-ttu-id="17e16-135">AcceptEula = "Yes"</span><span class="sxs-lookup"><span data-stu-id="17e16-135">AcceptEula="Yes"</span></span> | <span data-ttu-id="17e16-136">"No"(default)</span><span class="sxs-lookup"><span data-stu-id="17e16-136">"No"(default)</span></span> <br/> |
|<span data-ttu-id="17e16-137">Registro</span><span class="sxs-lookup"><span data-stu-id="17e16-137">Logging</span></span>  <br/> | <span data-ttu-id="17e16-p106">Opciones para el tipo de registro que realiza el programa de instalación. Los atributos típicos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="17e16-p106">Options for the kind of logging that Setup performs. Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="17e16-140">Tipo = "Off"</span><span class="sxs-lookup"><span data-stu-id="17e16-140">Type ="Off"</span></span> | <span data-ttu-id="17e16-141">"Standard"(default)</span><span class="sxs-lookup"><span data-stu-id="17e16-141">"Standard"(default)</span></span> | <span data-ttu-id="17e16-142">"Detallado"</span><span class="sxs-lookup"><span data-stu-id="17e16-142">"Verbose"</span></span> <br/>  <span data-ttu-id="17e16-143">Plantilla = " _nombre de archivo_.txt" (el nombre del archivo de registro)</span><span class="sxs-lookup"><span data-stu-id="17e16-143">Template=" _filename_.txt" (the name of the log file)</span></span>  <br/> |
|<span data-ttu-id="17e16-144">Configuración</span><span class="sxs-lookup"><span data-stu-id="17e16-144">Setting</span></span>  <br/> | <span data-ttu-id="17e16-p107">Especifica los valores de propiedades de Windows Installer. Los atributos típicos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="17e16-p107">Specifies values for Windows Installer properties. Typical attributes include the following: </span></span><br/>  <span data-ttu-id="17e16-147">Establecer Id = " _nombre_" (el nombre de la propiedad de Windows Installer)</span><span class="sxs-lookup"><span data-stu-id="17e16-147">Setting Id=" _name_" (the name of the Windows Installer property)</span></span>  <br/>  <span data-ttu-id="17e16-148">Valor = " _valor_" (el valor para asignar a la propiedad)</span><span class="sxs-lookup"><span data-stu-id="17e16-148">Value=" _value_" (the value to assign to the property)</span></span>  <br/> |
|<span data-ttu-id="17e16-149">DistributionPoint</span><span class="sxs-lookup"><span data-stu-id="17e16-149">DistributionPoint</span></span>  <br/> | <span data-ttu-id="17e16-p108">La ruta de acceso completa del punto de instalación de red desde la que se ejecuta la instalación. Incluye el atributo de ubicación:</span><span class="sxs-lookup"><span data-stu-id="17e16-p108">The fully qualified path of the network installation point from which the installation is to run. Includes the Location attribute: </span></span><br/>  <span data-ttu-id="17e16-152">Ubicación = " _ruta_"</span><span class="sxs-lookup"><span data-stu-id="17e16-152">Location=" _path_"</span></span>  <br/> |
   
<span data-ttu-id="17e16-153">En el ejemplo siguiente se muestra un archivo Config.xml para una instalación silenciosa típica de Skype para el negocio.</span><span class="sxs-lookup"><span data-stu-id="17e16-153">The following example shows a Config.xml file for a typical silent installation of Skype for Business.</span></span> 
  
```
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

<span data-ttu-id="17e16-154">Información detallada acerca de cómo utilizar el archivo Config.xml para realizar tareas de mantenimiento e instalación de Office está disponible en [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514).</span><span class="sxs-lookup"><span data-stu-id="17e16-154">Detailed information about using the Config.xml file to perform Office installation and maintenance tasks is available at [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514).</span></span>
  
## <a name="to-customize-the-configxml-file"></a><span data-ttu-id="17e16-155">Para personalizar el archivo Config.xml</span><span class="sxs-lookup"><span data-stu-id="17e16-155">To customize the Config.xml file</span></span>

1. <span data-ttu-id="17e16-156">Abra el archivo Config.xml usando una herramienta de edición de texto como el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="17e16-156">Open the Config.xml file by using a text editor tool, such as Notepad.</span></span>
    
2. <span data-ttu-id="17e16-157">Localice las líneas que contienen los elementos que desee cambiar.</span><span class="sxs-lookup"><span data-stu-id="17e16-157">Locate the lines that contain the elements you want to change.</span></span>
    
3. <span data-ttu-id="17e16-158">Modifique la entrada de elemento con las opciones silenciosas que desea usar.</span><span class="sxs-lookup"><span data-stu-id="17e16-158">Modify the element entry with the silent options that you want to use.</span></span> <span data-ttu-id="17e16-159">Asegúrese de que quita los delimitadores de comentario "\<!--" y "--\>".</span><span class="sxs-lookup"><span data-stu-id="17e16-159">Make sure that you remove the comment delimiters, "\<!--" and "--\>".</span></span> <span data-ttu-id="17e16-160">Por ejemplo, utilice la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="17e16-160">For example, use the following syntax:</span></span>
    
  ```
  < DistributionPoint Location="\\server\share\Skype15" />
  ```

4. <span data-ttu-id="17e16-161">Guarde el archivo Config.xml.</span><span class="sxs-lookup"><span data-stu-id="17e16-161">Save the Config.xml file.</span></span>
    

