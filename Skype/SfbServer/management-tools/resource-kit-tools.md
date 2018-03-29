---
title: Documentación de las herramientas del kit de recursos de Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/20/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
description: En este tema se describe las herramientas en el Skype for Business Server 2015 Resource Kit, incluida la finalidad de cada herramienta y ejemplos de su uso. El Skype para el Kit de recursos de 2015 Business Server ayuda a facilitar las tareas rutinarias para los administradores de TI que implementan y administran Skype para Business Server 2015. Por ejemplo, la herramienta Web Conf datos puede utilizarse para controlar fácilmente los datos que están cargados por los usuarios durante una reunión en línea. La herramienta SEFAUtil puede utilizarse para configurar la llamada al delegado reenviar y responder a los usuarios. Recomendamos a los administradores de TI a utilizar estas herramientas para administrar con más eficacia Skype para Business Server 2015.
ms.openlocfilehash: 8367400ea7730eabbd2686c3bb2b7c16cdf9a1f2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="skype-for-business-server-2015-resource-kit-tools-documentation"></a><span data-ttu-id="3cbaa-107">Documentación de las herramientas del kit de recursos de Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="3cbaa-107">Skype for Business Server 2015 Resource Kit Tools Documentation</span></span>
 
<span data-ttu-id="3cbaa-108">En este tema se describe las herramientas en el Skype for Business Server 2015 Resource Kit, incluida la finalidad de cada herramienta y ejemplos de su uso.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-108">This topic describes the tools in the Skype for Business Server 2015 Resource Kit, including the purpose of each tool, and examples of its use.</span></span> <span data-ttu-id="3cbaa-109">El Skype para el Kit de recursos de 2015 Business Server ayuda a facilitar las tareas rutinarias para los administradores de TI que implementan y administran Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-109">The Skype for Business Server 2015 Resource Kit helps to make routine tasks easier for IT administrators who deploy and manage Skype for Business Server 2015.</span></span> <span data-ttu-id="3cbaa-110">Por ejemplo, la herramienta **Web Conf Data** se puede usar para controlar fácilmente los datos que suben los usuarios durante una reunión de Internet.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-110">For example, the **Web Conf Data** tool can be used to easily control data that is uploaded by users during an online meeting.</span></span> <span data-ttu-id="3cbaa-111">La herramienta **SEFAUtil** se puede usar para delegar el desvío de llamadas y respuesta para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-111">The **SEFAUtil** tool can be used to set up delegate call forwarding and answering for users.</span></span> <span data-ttu-id="3cbaa-112">Recomendamos a los administradores de TI a utilizar estas herramientas para administrar con más eficacia Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-112">We encourage IT administrators to use these tools to more effectively manage Skype for Business Server 2015.</span></span>
  
## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="3cbaa-113">Instalación de las herramientas del kit de recursos</span><span class="sxs-lookup"><span data-stu-id="3cbaa-113">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="3cbaa-114">Para instalar el Skype para el Kit de recursos de Business Server 2015, descargue [OCSReskit.msi](https://www.microsoft.com/en-us/download/details.aspx?id=52631) del centro de descarga.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-114">To install the Skype for Business Server 2015 Resource Kit, download [OCSReskit.msi](https://www.microsoft.com/en-us/download/details.aspx?id=52631) from the Download Center.</span></span>
  
<span data-ttu-id="3cbaa-p103">Ejecute **OCSResKit.msi** para hacer una instalación sencilla. El archivo .msi instala todas las herramientas en la ruta de acceso siguiente: **%Archivos de programa%\Skype Empresarial Server 2015\ResKit**. Las herramientas que son ejecutables independientes se encuentran en esta carpeta. Las herramientas que tienen archivos auxiliares están en sus propias subcarpetas.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-p103">Run **OCSResKit.msi** to do a simple installation. The .msi installs all the tools in the following path: **%Program Files%\Skype for Business Server 2015\ResKit**. Tools that are self-contained executables are in this folder. Tools that also have supporting files are in their own subfolders.</span></span>
  
## <a name="supported-environments"></a><span data-ttu-id="3cbaa-119">Entornos compatibles</span><span class="sxs-lookup"><span data-stu-id="3cbaa-119">Supported Environments</span></span>

<span data-ttu-id="3cbaa-120">El Skype para el Kit de recursos de 2015 Business Server debe instalarse en un servidor que cumpla los requisitos exigidos para Skype para Business Server 2015, generalmente uno que se utiliza para ejecutar Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-120">The Skype for Business Server 2015 Resource Kit should be installed on a server that meets the specifications required for Skype for Business Server 2015, usually one being used to run Skype for Business Server 2015.</span></span>
  
## <a name="resource-kit-tools-overview"></a><span data-ttu-id="3cbaa-121">Información general sobre las herramientas del kit de recursos</span><span class="sxs-lookup"><span data-stu-id="3cbaa-121">Resource Kit Tools Overview</span></span>

<span data-ttu-id="3cbaa-122">La siguiente es una lista de las herramientas que se proporcionan en el Skype para el Kit de recursos de Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-122">The following is a list of the tools that are provided in the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="3cbaa-123">En las siguientes secciones se incluye una descripción de cada herramienta, además de los requisitos y ejemplos de uso.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-123">A description of each tool, including the requirements and example usage is covered in the following sections.</span></span>
  
- [<span data-ttu-id="3cbaa-124">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="3cbaa-124">ABSConfig</span></span>](resource-kit-tools.md#ABSConfig)
    
- [<span data-ttu-id="3cbaa-125">Bandwidth Policy Service Monitor (Monitor del servicio de directiva de ancho de banda)</span><span class="sxs-lookup"><span data-stu-id="3cbaa-125">Bandwidth Policy Service Monitor</span></span>](resource-kit-tools.md#bpsm)
    
- [<span data-ttu-id="3cbaa-126">Bandwidth Utilization Analyzer (Analizador de uso de ancho de banda)</span><span class="sxs-lookup"><span data-stu-id="3cbaa-126">Bandwidth Utilization Analyzer</span></span>](resource-kit-tools.md#bua)
    
- [<span data-ttu-id="3cbaa-127">Call Parkometer (Estacionamiento de llamadas)</span><span class="sxs-lookup"><span data-stu-id="3cbaa-127">Call Parkometer</span></span>](resource-kit-tools.md#callpark)
    
- [<span data-ttu-id="3cbaa-128">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="3cbaa-128">DBAnalyze</span></span>](resource-kit-tools.md#dba)
    
- [<span data-ttu-id="3cbaa-129">Import Storage Service Data (Importación de datos del servicio de almacenamiento)</span><span class="sxs-lookup"><span data-stu-id="3cbaa-129">Import Storage Service Data</span></span>](resource-kit-tools.md#Issd)
    
- [<span data-ttu-id="3cbaa-130">LCSSync</span><span class="sxs-lookup"><span data-stu-id="3cbaa-130">LCSSync</span></span>](resource-kit-tools.md#LCSSync)
    
- [<span data-ttu-id="3cbaa-131">Lookup User Console (Consola de búsqueda de usuario)</span><span class="sxs-lookup"><span data-stu-id="3cbaa-131">Lookup User Console</span></span>](resource-kit-tools.md#LUC)
    
- [<span data-ttu-id="3cbaa-132">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="3cbaa-132">MsTurnPing</span></span>](resource-kit-tools.md#MsTurnPing)
    
- [<span data-ttu-id="3cbaa-133">Network Configuration Viewer (Visor de configuración de red)</span><span class="sxs-lookup"><span data-stu-id="3cbaa-133">Network Configuration Viewer</span></span>](resource-kit-tools.md#NCV)
    
- [<span data-ttu-id="3cbaa-134">Response Group Agent Live (Información en vivo del agente del grupo de respuesta)</span><span class="sxs-lookup"><span data-stu-id="3cbaa-134">Response Group Agent Live</span></span>](resource-kit-tools.md#RGAL)
    
- [<span data-ttu-id="3cbaa-135">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="3cbaa-135">SEFAUtil</span></span>](resource-kit-tools.md#SEFAUtil)
    
- [<span data-ttu-id="3cbaa-136">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="3cbaa-136">SYSPrep.ps1</span></span>](resource-kit-tools.md#SYSPrep)
    
- [<span data-ttu-id="3cbaa-137">Unassigned Number Announcements Migration (Migración de anuncios de números sin asignar)</span><span class="sxs-lookup"><span data-stu-id="3cbaa-137">Unassigned Number Announcements Migration</span></span>](resource-kit-tools.md#UNAM)
    
- [<span data-ttu-id="3cbaa-138">Web Conf Data</span><span class="sxs-lookup"><span data-stu-id="3cbaa-138">Web Conf Data</span></span>](resource-kit-tools.md#WebConfData)
    
## <a name="absconfig"></a><span data-ttu-id="3cbaa-139">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="3cbaa-139">ABSConfig</span></span>
<span data-ttu-id="3cbaa-140"><a name="ABSConfig"> </a></span><span class="sxs-lookup"><span data-stu-id="3cbaa-140"></span></span>

<span data-ttu-id="3cbaa-141">La herramienta de configuración del servicio de libreta de direcciones (ABSConfig) es una herramienta administrativa que permite a los administradores personalizar la configuración del servicio de libreta de direcciones en Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-141">The Address Book Service Configuration tool (ABSConfig) is an administrative tool that helps administrators customize Address Book Service configuration in Skype for Business Server 2015.</span></span> <span data-ttu-id="3cbaa-142">Esta herramienta también permite Skype para los administradores de servidor de negocios 2015 restaurar la configuración del servicio de libreta de direcciones predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-142">This tool also enables Skype for Business Server 2015 administrators to restore the default Address Book Service settings.</span></span>
  
### <a name="description"></a><span data-ttu-id="3cbaa-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="3cbaa-143">Description</span></span>

<span data-ttu-id="3cbaa-144">ABSConfig es una aplicación de interfaz gráfica de usuario que permite a los administradores configurar atributos de servicios de dominio de Active Directory que están relacionados con el servicio de libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-144">ABSConfig is a graphical user interface application that enables administrators to configure Active Directory Domain Services attributes that are related to Address Book Service.</span></span>
  
<span data-ttu-id="3cbaa-145">Los escenarios principales para la herramienta son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="3cbaa-145">The primary scenarios for the tool are the following:</span></span>
  
- <span data-ttu-id="3cbaa-146">Para permitir a los administradores asignar atributos en servicios de dominio de Active Directory a los atributos de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-146">To enable administrators to map attributes in Active Directory Domain Services to the attributes for Skype for Business Server 2015.</span></span>
    
- <span data-ttu-id="3cbaa-147">Permitir a los administradores especificar el atributo de Active Directory Domain Services que se incluirá o excluirá en los archivos del Servicio de libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-147">To enable administrators to specify the Active Directory Domain Services attribute to be included or excluded in the Address Book Service files.</span></span>
    
- <span data-ttu-id="3cbaa-148">Permitir a los administradores restaurar la configuración predeterminada del Servicio de libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-148">To enable administrators to restore default Address Book Service settings.</span></span>
    
<span data-ttu-id="3cbaa-149">La herramienta ABSConfig puede iniciarse mediante el archivo ABSConfig.exe.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-149">The ABSConfig tool can be started by using the ABSConfig.exe file.</span></span> <span data-ttu-id="3cbaa-150">La herramienta se abre en la ficha **Configurar atributos** . Esta tabla tiene opciones para asignar atributos de servicios de dominio de Active Directory a los campos de atributo de Skype para Business Server 2015 y especificar los usuarios que desea incluir o excluir en archivos del servicio de libreta de direcciones basados en filtros de atributo específico.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-150">The tool opens to the **Configure Attributes** tab. This table has options to map Active Directory Domain Services attributes to the attribute fields for Skype for Business Server 2015 and to specify which users to include or exclude in Address Book Service files based on specific attribute filters.</span></span> <span data-ttu-id="3cbaa-151">También tiene opciones para personalizar el valor del número de teléfono que se incluirá en el archivo de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-151">It also has options to customize which value of the phone number to be included in the Address Book file.</span></span> <span data-ttu-id="3cbaa-152">La opción **Restaurar valores predeterminados** permite a los administradores restaurar la configuración del Servicio de libreta de direcciones a los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-152">The **Restore Defaults** option enables administrators to restore Address Book Service settings to default values.</span></span>
  
### <a name="output"></a><span data-ttu-id="3cbaa-153">Salida</span><span class="sxs-lookup"><span data-stu-id="3cbaa-153">Output</span></span>

<span data-ttu-id="3cbaa-154">ABSConfig guarda la configuración del Servicio de libreta de direcciones en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-154">ABSConfig stores the Address Book Service configuration in the database.</span></span>
  
```
Path: %ProgramFiles%\Skype for Business Server 2015\Reskit
```

### <a name="purpose"></a><span data-ttu-id="3cbaa-155">Finalidad</span><span class="sxs-lookup"><span data-stu-id="3cbaa-155">Purpose</span></span>

<span data-ttu-id="3cbaa-156">ABSConfig proporciona una forma rápida y fácil para personalizar Skype para el servicio de libreta de direcciones de negocio servidor 2015.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-156">ABSConfig provides a quick and easy way to customize Skype for Business Server 2015 Address Book Service.</span></span>
  
### <a name="requirements"></a><span data-ttu-id="3cbaa-157">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3cbaa-157">Requirements</span></span>

#### <a name="computer"></a><span data-ttu-id="3cbaa-158">Equipo</span><span class="sxs-lookup"><span data-stu-id="3cbaa-158">Computer</span></span>

<span data-ttu-id="3cbaa-159">ABSConfig puede ejecutarse únicamente desde un equipo unido al dominio que tenga Skype para Business Server 2015 instalado.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-159">ABSConfig can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span> <span data-ttu-id="3cbaa-160">En el caso de Skype para Business Server 2015, Enterprise Edition, esta herramienta se puede ejecutar en cualquier servidor de Front-End que tenga habilitado durante la instalación del servicio de libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-160">In the case of Skype for Business Server 2015, Enterprise Edition, this tool can be run on any Front End servers that have the Address Book Service enabled during setup.</span></span>
  
#### <a name="network"></a><span data-ttu-id="3cbaa-161">Red</span><span class="sxs-lookup"><span data-stu-id="3cbaa-161">Network</span></span>

<span data-ttu-id="3cbaa-162">El equipo debe ser capaz de conectarse al grupo de servidores front-end y a la base de datos back-end.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-162">The computer should be able to connect to the Front End pool and back-end database.</span></span>
  
#### <a name="software"></a><span data-ttu-id="3cbaa-163">Software</span><span class="sxs-lookup"><span data-stu-id="3cbaa-163">Software</span></span>

<span data-ttu-id="3cbaa-164">Antes de ejecutar la herramienta ABSConfig es necesario instalar los siguientes componentes de software:</span><span class="sxs-lookup"><span data-stu-id="3cbaa-164">The following software components must be installed before running the ABSConfig tool:</span></span>
  
- <span data-ttu-id="3cbaa-165">Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="3cbaa-165">Skype for Business Server 2015</span></span>
    
#### <a name="users"></a><span data-ttu-id="3cbaa-166">Usuarios</span><span class="sxs-lookup"><span data-stu-id="3cbaa-166">Users</span></span>

<span data-ttu-id="3cbaa-167">Administradores que tengan los permisos necesarios para actualizar el Skype para la implementación de Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-167">Administrators who have the permissions required to update the Skype for Business Server 2015 deployment.</span></span>
  
### <a name="examples"></a><span data-ttu-id="3cbaa-168">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="3cbaa-168">Examples</span></span>

<span data-ttu-id="3cbaa-p108">Para iniciar ABSConfig, escriba **ABSConfig.exe** en un símbolo del sistema. A continuación se muestra la interfaz de usuario de la herramienta ABSConfig.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-p108">ABSConfig can be started by typing **ABSConfig.exe** at a command prompt. Shown below is the ABSConfig tool user interface.</span></span>
  
![La herramienta ABSConfig.exe.](../media/Reskit_2012_Tools_Documentation_ABSConfig.JPG)
  
### <a name="summary"></a><span data-ttu-id="3cbaa-172">Resumen</span><span class="sxs-lookup"><span data-stu-id="3cbaa-172">Summary</span></span>

<span data-ttu-id="3cbaa-173">La herramienta ABSConfig proporciona a los administradores una herramienta rápida y fácil de usar para personalizar Skype para el servicio de libreta de direcciones de negocio servidor 2015.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-173">The ABSConfig tool provides administrators a quick and easy to use tool to customize Skype for Business Server 2015 Address Book Service.</span></span>
  
## <a name="bandwidth-policy-service-monitor"></a><span data-ttu-id="3cbaa-174">Bandwidth Policy Service Monitor (Monitor del servicio de directiva de ancho de banda)</span><span class="sxs-lookup"><span data-stu-id="3cbaa-174">Bandwidth Policy Service Monitor</span></span>
<span data-ttu-id="3cbaa-175"><a name="bpsm"> </a></span><span class="sxs-lookup"><span data-stu-id="3cbaa-175"></span></span>

<span data-ttu-id="3cbaa-176">La herramienta Bandwidth Policy Service Monitor permite a los administradores ver una lista de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3cbaa-176">The Bandwidth Policy Service Monitor tool is intended to allow administrators to view a list of the following:</span></span>
  
1. <span data-ttu-id="3cbaa-177">Todos lo Skype configurado para servicios de directiva de ancho de banda de 2015 Business Server (autenticación y Core) de la topología</span><span class="sxs-lookup"><span data-stu-id="3cbaa-177">All the configured Skype for Business Server 2015 Bandwidth Policy services (Authentication and Core) in the topology</span></span>
    
2. <span data-ttu-id="3cbaa-178">Las conexiones que realiza cada servicio con otros servicios de directivas de ancho de banda y a los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-178">The connections that each service makes to other Bandwidth Policy services and to the Edge servers</span></span>
    
3. <span data-ttu-id="3cbaa-179">Todos los vínculos configurados en el documento de configuración de red y el uso de ancho de banda en tiempo real informado por los servicios de directiva de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-179">All the links that are configured in the Network configuration document and real-time bandwidth usage as reported by each of the Bandwidth Policy services</span></span>
    
### <a name="description"></a><span data-ttu-id="3cbaa-180">Descripción</span><span class="sxs-lookup"><span data-stu-id="3cbaa-180">Description</span></span>

<span data-ttu-id="3cbaa-p109">La herramienta Bandwidth Policy Service Monitor se implementa como una aplicación basada en GUI. Los administradores pueden ejecutar la herramienta mediante PDPMonUI.exe.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-p109">The Bandwidth Policy Service Monitor tool is implemented as a GUI-based application. Administrators start the tool by running PDPMonUI.exe.</span></span>
  
<span data-ttu-id="3cbaa-p110">Al iniciar la aplicación, esta intenta detectar la lista de servicios de directiva de ancho de banda en la topología. Después de completar la actualización inicial, en el panel de la izquierda de la ventana se muestra una lista de servicios agrupados por los clústeres a los que pertenecen.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-p110">When the tool starts, it attempts to discover the list of Bandwidth Policy services in the topology. After the initial update is done, the pane to the left of the window is populated with a list of services that are grouped by the clusters that they belong to.</span></span>
  
<span data-ttu-id="3cbaa-p111">Cuando los administradores seleccionan un servicio de directiva de ancho de banda concreto, en el panel de la derecha se muestra información sobre dicho servicio. Además, el panel también contiene dos pestañas principales con información.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-p111">When administrators select a particular Bandwidth Policy Service, the pane on the right displays the information about that particular service. That pane also has two main tabs that display information.</span></span>
  
#### <a name="machine-info-tab"></a><span data-ttu-id="3cbaa-187">Pestaña Información de equipo</span><span class="sxs-lookup"><span data-stu-id="3cbaa-187">Machine Info Tab</span></span>

<span data-ttu-id="3cbaa-188">La pestaña **Información de equipo** contiene información detallada sobre el servicio de directiva de ancho de banda seleccionado, además de la lista y el estado de todas las conexiones realizadas por dicho servicio de directiva de ancho de banda seleccionado con otros servicios.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-188">The **Machine Info** tab shows the details of the Bandwidth Policy Service that is selected and the list and state of all the connections that are made by the selected Bandwidth Policy Service to other services.</span></span>
  
#### <a name="topology-info-tab"></a><span data-ttu-id="3cbaa-189">Pestaña Información de topología</span><span class="sxs-lookup"><span data-stu-id="3cbaa-189">Topology Info Tab</span></span>

<span data-ttu-id="3cbaa-p112">En la pestaña **Información de topología** se muestra una lista de todos los vínculos configurados en las opciones de red. Para cada vínculo se muestra la capacidad de ancho de banda de audio y de vídeo. Además, también se muestra el ancho de banda utilizado actualmente, tanto en kbps como en porcentaje de capacidad. La herramienta utiliza códigos de color para resaltar vínculos cuyo uso está próximo al límite de capacidad, lo que permite a los administradores aislarlos rápidamente.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-p112">The **Topology Info** tab shows a list of all the links that are configured in the Network configuration settings. For each link, the audio and video bandwidth capacity is displayed. Additionally, the currently utilized bandwidth is displayed, both in Kbps and as a percentage of the capacity. The tool uses color-coding to highlight links that have utilization that is close to the capacity—this allows administrators to quickly isolate such links.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="3cbaa-194">Si la herramienta Monitor de servicios de la política de ancho de banda experimenta errores cuando se conecta a cualquiera de los servicios configurados de la política de ancho de banda, no se rellena la información en la **Información del equipo** y las fichas de **Información de topología** .</span><span class="sxs-lookup"><span data-stu-id="3cbaa-194">If the Bandwidth Policy Service Monitor tool experiences failure when it connects to any of the configured Bandwidth Policy services, the information in the **Machine Info** and the **Topology Info** tabs won't be populated.</span></span> <span data-ttu-id="3cbaa-195">Sin embargo, es posible que la herramienta pueda conectarse de forma inicial, pero que posteriormente pierda la conexión al servicio.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-195">However, it is possible that the tool might connect initially but subsequently lose its connection to the service.</span></span> <span data-ttu-id="3cbaa-196">En estos casos, los administradores podrían ver información desactualizada.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-196">In such cases, administrators might see outdated information.</span></span> <span data-ttu-id="3cbaa-197">En las pestañas hay una marca de tiempo **Última actualización** que permite a los administradores ver cuándo se actualizó por última vez un servicio de directiva de ancho de banda concreto.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-197">There is a **Last Updated** time stamp on each of the tabs that can allow administrators to see when the data was last updated for a particular Bandwidth Policy Service.</span></span>
  
### <a name="output"></a><span data-ttu-id="3cbaa-198">Salida</span><span class="sxs-lookup"><span data-stu-id="3cbaa-198">Output</span></span>

<span data-ttu-id="3cbaa-199">No hay salida de línea de comandos; la salida del programa está contenida en la interfaz gráfica de usuario (GUI) principal.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-199">There is no command-line output; the program output is contained within the main graphical user interface (GUI).</span></span>
  
### <a name="purpose"></a><span data-ttu-id="3cbaa-200">Finalidad</span><span class="sxs-lookup"><span data-stu-id="3cbaa-200">Purpose</span></span>

<span data-ttu-id="3cbaa-p114">El objetivo de la herramienta Bandwidth Policy Service Monitor es permitir a los administradores ver el estado de los servicios de directiva de ancho de banda definidos en la topología. Además, los administradores pueden ver el uso de ancho de banda en tiempo real de todos los vínculos definidos en el documento de configuración de red.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-p114">The purpose of the Bandwidth Policy Service Monitor tool is to allow administrators visibility into the state of each of the Bandwidth Policy services that are defined in the topology. In addition, administrators can see real-time bandwidth usage for all the links that are defined in the Network configuration document.</span></span>
  
### <a name="requirements"></a><span data-ttu-id="3cbaa-203">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3cbaa-203">Requirements</span></span>

<span data-ttu-id="3cbaa-204">La herramienta Monitor de ancho de banda Directiva servicio debe ejecutarse en un equipo que forma parte de la Skype para la topología de servidores de empresa.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-204">The Bandwidth Policy Service Monitor tool needs to be run on a computer that is part of the Skype for Business Server topology.</span></span>
  
### <a name="summary"></a><span data-ttu-id="3cbaa-205">Resumen</span><span class="sxs-lookup"><span data-stu-id="3cbaa-205">Summary</span></span>

<span data-ttu-id="3cbaa-206">La herramienta Bandwidth Policy Service Monitor puede ser un recurso útil para los administradores, ya que permite inspeccionar el estado de todos los servicios de directiva de ancho de banda en la topología y, lo que es aún más importante, les permite conocer el uso de ancho de banda en tiempo real de los vínculos definidos en las opciones de configuración de red.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-206">The Bandwidth Policy Service Monitor tool can be a valuable resource to administrators so they can inspect the state of all the Bandwidth Policy services in the topology—and more importantly—they can obtain real-time bandwidth utilization for the links that are defined in the Network configuration settings.</span></span>
  
## <a name="bandwidth-utilization-analyzer"></a><span data-ttu-id="3cbaa-207">Bandwidth Utilization Analyzer (Analizador de uso de ancho de banda)</span><span class="sxs-lookup"><span data-stu-id="3cbaa-207">Bandwidth Utilization Analyzer</span></span>
<span data-ttu-id="3cbaa-208"><a name="bua"> </a></span><span class="sxs-lookup"><span data-stu-id="3cbaa-208"></span></span>

<span data-ttu-id="3cbaa-p115">Bandwidth Utilization Analyzer es una herramienta que genera informes sobre diferentes vistas de consumo de ancho de banda por los puntos de conexión de comunicaciones unificadas en vínculos WAN de la red empresarial. Estos informes pueden utilizarse para conocer el patrón de consumo de ancho de banda y ayudar a planificar la capacidad de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-p115">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network. These reports can be used to understand the current bandwidth consumption pattern and to aid in bandwidth capacity planning.</span></span>
  
### <a name="description"></a><span data-ttu-id="3cbaa-211">Descripción</span><span class="sxs-lookup"><span data-stu-id="3cbaa-211">Description</span></span>

<span data-ttu-id="3cbaa-p116">El analizador de uso de ancho de banda se implementa como una aplicación basada en GUI. Esta herramienta genera informes específicos para el uso de audio en la red y ayuda a planificar la capacidad. Además, también itera en la capacidad de ancho de banda asignada a diferentes vínculos.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-p116">Bandwidth Utilization Analyzer is implemented as a GUI-based application. This tool generates reports specifically for audio utilization across the network and helps with capacity planning. It also iterates on the bandwidth capacity that is assigned to various links.</span></span>
  
### <a name="output"></a><span data-ttu-id="3cbaa-215">Salida</span><span class="sxs-lookup"><span data-stu-id="3cbaa-215">Output</span></span>

<span data-ttu-id="3cbaa-216">El analizador de uso de ancho de banda proporciona representaciones gráficas de la capacidad de ancho de banda y el consumo de audio para todos los vínculos WAN configurados en el sistema.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-216">Bandwidth Utilization Analyzer provides graphic al plots of bandwidth capacity and utilization for audio for all the WAN links that are configured in the system.</span></span>
  
### <a name="purpose"></a><span data-ttu-id="3cbaa-217">Finalidad</span><span class="sxs-lookup"><span data-stu-id="3cbaa-217">Purpose</span></span>

<span data-ttu-id="3cbaa-218">En cualquier voz y vídeo implementación, resulta fundamental supervisar y comprender la tendencia de uso de ancho de banda del tráfico de multimedia a través de la red empresarial.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-218">In any voice and video deployment, it's critical to monitor and understand the trend of bandwidth utilization of media traffic across the enterprise network.</span></span> <span data-ttu-id="3cbaa-219">La herramienta Bandwidth Utilization Analyzer permite a los administradores conseguir justo eso.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-219">The Bandwidth Utilization Analyzer tool allows an administrator to achieve just that.</span></span> <span data-ttu-id="3cbaa-220">Esta herramienta hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3cbaa-220">This tool does the following:</span></span>
  
- <span data-ttu-id="3cbaa-221">Genera informes específicos para el uso de audio en la red</span><span class="sxs-lookup"><span data-stu-id="3cbaa-221">Generates specific reports for audio utilization across the network</span></span>
    
- <span data-ttu-id="3cbaa-222">Mejora la eficacia de planificación de capacidad y la iteración en la capacidad de ancho de banda asignada a diferentes vínculos</span><span class="sxs-lookup"><span data-stu-id="3cbaa-222">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>
    
<span data-ttu-id="3cbaa-223">El analizador de uso de ancho de banda puede generar las siguientes representaciones gráficas de capacidad de ancho de banda e informes de uso:</span><span class="sxs-lookup"><span data-stu-id="3cbaa-223">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and utilization reports; they are as follows:</span></span>
  
- <span data-ttu-id="3cbaa-224">Todos los vínculos WAN en la red empresarial</span><span class="sxs-lookup"><span data-stu-id="3cbaa-224">All the WAN links in the enterprise network</span></span>
    
- <span data-ttu-id="3cbaa-225">Filtrados por los vínculos WAN seleccionados</span><span class="sxs-lookup"><span data-stu-id="3cbaa-225">Filtered by selected WAN links that have been chosen</span></span>
    
- <span data-ttu-id="3cbaa-226">Filtrados por los vínculos WAN que han superado la capacidad de vínculos</span><span class="sxs-lookup"><span data-stu-id="3cbaa-226">Filtered by WAN links that have exceeded link capacity</span></span>
    
- <span data-ttu-id="3cbaa-227">Filtrados por los vínculos WAN que no han utilizado toda la capacidad de ancho de banda proporcionada</span><span class="sxs-lookup"><span data-stu-id="3cbaa-227">Filtered by WAN links that have been under-utilizing the provisioned bandwidth</span></span>
    
- <span data-ttu-id="3cbaa-228">Filtrados por los vínculos WAN que han alcanzado niveles críticos (un uso de ancho de banda superior al 90 % de capacidad de ancho de banda del vínculo WAN)</span><span class="sxs-lookup"><span data-stu-id="3cbaa-228">Filter by WAN links that have been reaching critical levels (a bandwidth utilization that is greater than 90% of bandwidth capacity of the WAN link)</span></span>
    
- <span data-ttu-id="3cbaa-229">Filtrados por tipo de vínculo WAN: vínculos de sitios de red, vínculos interregionales y vínculos dentro de un sitio</span><span class="sxs-lookup"><span data-stu-id="3cbaa-229">Filtered by WAN link type—network-site links, interregional links, and links within a site</span></span>
    
- <span data-ttu-id="3cbaa-230">Filtrados por región de red</span><span class="sxs-lookup"><span data-stu-id="3cbaa-230">Filtered by network region</span></span>
    
#### <a name="applications"></a><span data-ttu-id="3cbaa-231">Aplicaciones</span><span class="sxs-lookup"><span data-stu-id="3cbaa-231">Applications</span></span>

<span data-ttu-id="3cbaa-232">El analizador de uso de ancho de banda incluye las siguientes dos aplicaciones (herramientas):</span><span class="sxs-lookup"><span data-stu-id="3cbaa-232">Bandwidth Utilization Analyzer has the following two applications (tools):</span></span>
  
- <span data-ttu-id="3cbaa-233">**WanLinkLogCollector.exe** esta herramienta permite su usuario introduzca la información necesaria.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-233">**WanLinkLogCollector.exe** This tool enables its user to input the required information.</span></span>
    
- <span data-ttu-id="3cbaa-234">**BandwidthUtilizationAnalyzer.xlsm** informe de software de hoja de cálculo A Microsoft Excel se inicia automáticamente por WanLinkLogCollector.exe.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-234">**BandwidthUtilizationAnalyzer.xlsm** A Microsoft Excel spreadsheet software report is automatically launched by WanLinkLogCollector.exe.</span></span> <span data-ttu-id="3cbaa-235">Esta aplicación permite al usuario aplicar filtros al informe, como se muestra posteriormente en este artículo.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-235">This application allows the user to apply filters to the report as shown later in this article.</span></span>
    
#### <a name="phases-of-using-bandwidth-utilization-analyzer"></a><span data-ttu-id="3cbaa-236">Fases de uso de Bandwidth Utilization Analyzer</span><span class="sxs-lookup"><span data-stu-id="3cbaa-236">Phases of Using Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="3cbaa-237">Existen dos fases al usar el analizador de uso de ancho de banda:</span><span class="sxs-lookup"><span data-stu-id="3cbaa-237">There are two phases when using Bandwidth Utilization Analyzer:</span></span>
  
- <span data-ttu-id="3cbaa-238">Recopilar registros, que se realiza automáticamente mediante WanLinkLogCollector.exe</span><span class="sxs-lookup"><span data-stu-id="3cbaa-238">Collect logs, which is performed by using WanLinkLogCollector.exe</span></span>
    
- <span data-ttu-id="3cbaa-239">Personalizar informes, que se realiza mediante BandwidthUtilizationAnalyzer.xlsm</span><span class="sxs-lookup"><span data-stu-id="3cbaa-239">Customize reports, which is performed by using BandwidthUtilizationAnalyzer.xlsm</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="3cbaa-240">No se recomienda que los usuarios finales inicien BandwidthUtilizationAnalyzer.xlsm de forma manual.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-240">We strongly recommend that BandwidthUtilizationAnalyzer.xlsm not be manually launched by end users.</span></span> 
  
#### <a name="starting-bandwidth-utilization-analyzer"></a><span data-ttu-id="3cbaa-241">Inicio del analizador de uso de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="3cbaa-241">Starting Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="3cbaa-242">Inicie WanLinkLogCollector.exe en el símbolo del sistema o mediante el Explorador de Windows.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-242">Start WanLinkLogCollector.exe at the command prompt or by using Windows Explorer.</span></span>
  
 <span data-ttu-id="3cbaa-243">**Uso de WanLinkLogCollector.exe**</span><span class="sxs-lookup"><span data-stu-id="3cbaa-243">**Using WanLinkLogCollector.exe**</span></span>
  
<span data-ttu-id="3cbaa-244">Hay tres pasos para usar WanLinkLogCollector.exe:</span><span class="sxs-lookup"><span data-stu-id="3cbaa-244">There are three steps to using WanLinkLogCollector.exe:</span></span>
  
1. <span data-ttu-id="3cbaa-245">**Registro de la línea de tiempo** Proporcionar la escala de tiempo que debe generarse para el informe</span><span class="sxs-lookup"><span data-stu-id="3cbaa-245">**Log the timeline** Provide the timeline that the report needs to be generated for</span></span>
    
2. <span data-ttu-id="3cbaa-246">**Especificar los directorios de archivos** Proporcionar información de ubicación de archivo</span><span class="sxs-lookup"><span data-stu-id="3cbaa-246">**Specify the file directories** Provide file location information</span></span>
    
3. <span data-ttu-id="3cbaa-247">**Recopilar los registros e iniciar el Visor de informes** Ejecute el comando para generar el informe</span><span class="sxs-lookup"><span data-stu-id="3cbaa-247">**Collect the logs and launch the report viewer** Execute the command to generate the report</span></span>
    
#### <a name="step-1---log-the-timeline"></a><span data-ttu-id="3cbaa-248">Paso 1: registrar la escala de tiempo</span><span class="sxs-lookup"><span data-stu-id="3cbaa-248">Step 1 - Log the timeline</span></span>

<span data-ttu-id="3cbaa-249">Al registrar la escala de tiempo, el usuario de la herramienta puede especificar lo siguiente como se muestra en la ilustración siguiente. </span><span class="sxs-lookup"><span data-stu-id="3cbaa-249">Logging the timeline allows the tool user to specify the following as shown in the figure below.</span></span> 
  
1. <span data-ttu-id="3cbaa-250">**Fecha de inicio** Se trata de la fecha de comienzo de la línea de tiempo que el informe que se generará para; Por ejemplo, el 1 de agosto de 2010.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-250">**Start date** This is the start date of the timeline that the report is to be generated for; for example, August 1, 2010.</span></span>
    
2. <span data-ttu-id="3cbaa-251">**Fecha de finalización** Ésta es la fecha final de la línea de tiempo que el informe que se generará para; Por ejemplo, el 30 de septiembre de 2010.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-251">**End date** This is the end date of the timeline that the report is to be generated for; for example, September 30, 2010.</span></span>
    
     ![Fecha de inicio y fin en el análisis de utilización de ancho de banda](../media/Reskit_2012_Tools_Documentation_Image4.jpg)
  
#### <a name="step-2---specify-the-file-directories"></a><span data-ttu-id="3cbaa-253">Paso 2: especificar los directorios de archivos</span><span class="sxs-lookup"><span data-stu-id="3cbaa-253">Step 2 - Specify the file directories</span></span>

<span data-ttu-id="3cbaa-254">El usuario puede especificar los directorios de archivos siguientes, como se muestra.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-254">The following file directories can be specified by the user as shown.</span></span>
  
- <span data-ttu-id="3cbaa-255">**Ubicación de los archivos de registro de servidor** La ubicación de la carpeta donde se almacenan los registros del servidor de directivas de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-255">**Server log files location** The folder location where Bandwidth policy server logs are stored.</span></span> <span data-ttu-id="3cbaa-256">Esto es por lo general en \<fileserve\>\\< choice de FE\>\AppServerFiles\PDP.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-256">This is typically in \<fileserver\>\\<choice of FE\>\AppServerFiles\PDP.</span></span>
    
- <span data-ttu-id="3cbaa-257">**Ubicación de almacenamiento temporal de archivos** La ubicación del archivo temporal donde se almacenan los archivos intermedios mientras se genera el informe.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-257">**Temporary file storage location** The temporary file location where intermediate files are stored while the report is being generated.</span></span>
    
![Directorios de archivos en análisis de utilización de ancho de banda](../media/Reskit_2012_Tools_Documentation_Image5.jpg)
  
> [!NOTE]
> <span data-ttu-id="3cbaa-259">Compruebe que el usuario de la herramienta posee acceso a los archivos de los registros del servidor y a la carpeta donde se almacenan los archivos temporales.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-259">Ensure that sufficient file access to the server logs and the temporary file store folder is provided to the tool user.</span></span> 
  
#### <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a><span data-ttu-id="3cbaa-260">Paso 3: recopilar los registros e iniciar el visor de informes</span><span class="sxs-lookup"><span data-stu-id="3cbaa-260">Step 3 - Collect the logs and start the report viewer</span></span>

<span data-ttu-id="3cbaa-p120">Para recopilar los registros e iniciar el visor de informes, haga clic en **Ejecutar** como se indica a continuación. Este paso recopila todos los datos necesarios.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-p120">To collect the logs and start the report viewer, click **Execute** as shown below. This step collects the required data.</span></span>
  
![Recopilación de datos en el análisis de utilización de ancho de banda](../media/Reskit_2012_Tools_Documentation_Image6.jpg)
  
<span data-ttu-id="3cbaa-264">Cuando la validación de entrada es correcta, se muestra el mensaje que aparece a continuación.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-264">When the input validation is successful, the message shown below is displayed.</span></span>
  
![Notificación de registros recopilados en la utilidad de ancho de banda](../media/Reskit_2012_Tools_Documentation_Image7.jpg)
  
<span data-ttu-id="3cbaa-p121">Haga clic en **Aceptar**. BandwidthUtilizationAnalyzer.xlsm se iniciará automáticamente. Siga las instrucciones del cuadro de mensaje. Para obtener más información, consulte **Uso de BandwidthUtilizationAnalyzer.xlsm** en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-p121">Click **OK**. BandwidthUtilizationAnalyzer.xlsm is automatically started. Follow the instructions in the message box. For details, see **Using BandwidthUtilizationAnalyzer.xlsm** in the next section.</span></span>
  
#### 

### <a name="using-bandwidthutilizationanalyzerxlsm"></a><span data-ttu-id="3cbaa-270">Uso de BandwidthUtilizationAnalyzer.xlsm</span><span class="sxs-lookup"><span data-stu-id="3cbaa-270">Using BandwidthUtilizationAnalyzer.xlsm</span></span>

1. <span data-ttu-id="3cbaa-271">Cuando BandwidthUtilizationAnalyzer.xlsm se inicie automáticamente, haga clic en **Actualizar** como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-271">When BandwidthUtilizationAnalyzer.xlsm is automatically started, click **Refresh** as shown below.</span></span>
    
     ![BandwidthUtilizationAnalyzer.xlsm](../media/Reskit_2012_Tools_Documentation_Image8.jpg)
  
2. <span data-ttu-id="3cbaa-p122">Al abrir una carpeta de archivos, seleccione consolidated.csv de la ubicación especificada en el cuadro de mensaje, como se muestra a continuación. También se muestra la ubicación como **C:\Temp**.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-p122">When a file folder is opened, select consolidated.csv from the location that is specified in the message box as shown below. It also shows the location as **C:\Temp**.</span></span>
    
     ![Abrir una carpeta en BandwidthUtilizationAnalyzer.](../media/Reskit_2012_Tools_Documentation_Image9.jpg)
  
3. <span data-ttu-id="3cbaa-276">Haga clic en **Importar**.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-276">Click **Import**.</span></span>
    
4. <span data-ttu-id="3cbaa-p123">Se generará automáticamente la representación gráfica. Está disponible cuando desaparece el puntero que indica un proceso en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-p123">The graphical plot is automatically generated. It is available when the working-in-the-background pointer disappears.</span></span>
    
     ![Aplicación de filtros en la vista de informes.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)
  
#### <a name="applying-filters-to-the-report-view"></a><span data-ttu-id="3cbaa-280">Aplicar filtros a la vista de informes</span><span class="sxs-lookup"><span data-stu-id="3cbaa-280">Applying Filters to the Report View</span></span>

<span data-ttu-id="3cbaa-281">Los filtros que se pueden aplicar a la vista de informes son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="3cbaa-281">The filters that can be applied to the report view as shown below are described as follows:</span></span>
  
![Aplicación de filtros en la vista de informes.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)
  
1. <span data-ttu-id="3cbaa-283">**Nombre** Filtra por vínculos WAN (el filtro se encuentra en la parte derecha del gráfico). El prefijo indica los siguientes tipos de vínculos; consulte el cuadro vertical (azul):</span><span class="sxs-lookup"><span data-stu-id="3cbaa-283">**Name** Filter by WAN links (the filter is on the right side of the graph).The prefix denotes the following link types; see the vertical (blue) box:</span></span>
    
  - <span data-ttu-id="3cbaa-284">**Sitio S** El vínculo WAN de un sitio de red con una región de red</span><span class="sxs-lookup"><span data-stu-id="3cbaa-284">**S Site** The WAN link from a network site to a network region</span></span>
    
  - <span data-ttu-id="3cbaa-285">**ES entre sitios** El vínculo WAN entre dos sitios de red</span><span class="sxs-lookup"><span data-stu-id="3cbaa-285">**IS Inter-Site** The WAN link between two network sites</span></span>
    
  - <span data-ttu-id="3cbaa-286">**Interregional R** El vínculo WAN entre dos regiones de red</span><span class="sxs-lookup"><span data-stu-id="3cbaa-286">**R Inter-Region** The WAN link between two network region</span></span>
    
2. <span data-ttu-id="3cbaa-287">**Límite superado** Filtra por vínculos WAN cuyo uso de ancho de banda supera la capacidad de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="3cbaa-287">**Exceeded limit** Filter by WAN links whose bandwidth utilization is more than the bandwidth capacity</span></span>
    
3. <span data-ttu-id="3cbaa-288">**Niveles críticos** Filtra por vínculos WAN cuyo uso de ancho de banda ha alcanzado el 90 % o más de la capacidad de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="3cbaa-288">**Critical levels** Filter by WAN links whose bandwidth utilization has reached 90% or more than the bandwidth capacity</span></span>
    
4. <span data-ttu-id="3cbaa-289">**Infrautilizados** Filtra por vínculos WAN cuyo uso de ancho de banda ha sido inferior al 25 % de la capacidad de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="3cbaa-289">**Under-utilized** Filter by WAN links whose bandwidth utilization has been less than 25% of the bandwidth capacity</span></span>
    
5. <span data-ttu-id="3cbaa-290">**Tipo de vínculo** Filtra por los siguientes tipos de vínculos WAN:</span><span class="sxs-lookup"><span data-stu-id="3cbaa-290">**Link type** Filter by the following WAN links types:</span></span>
    
  - <span data-ttu-id="3cbaa-291">
            Tipo **sitio de red**</span><span class="sxs-lookup"><span data-stu-id="3cbaa-291">**Network site** type</span></span>
    
  - <span data-ttu-id="3cbaa-292">
            Tipo **entre sitios**</span><span class="sxs-lookup"><span data-stu-id="3cbaa-292">**Inter-site** type</span></span>
    
  - <span data-ttu-id="3cbaa-293">
            Tipo **vínculo entre regiones**</span><span class="sxs-lookup"><span data-stu-id="3cbaa-293">**Inter-Region link** type</span></span>
    
6. <span data-ttu-id="3cbaa-294">**Región** Filtra por región de red</span><span class="sxs-lookup"><span data-stu-id="3cbaa-294">**Region** Filter by network region</span></span>
    
<span data-ttu-id="3cbaa-295">En las ilustraciones siguientes se muestran los filtros descritos anteriormente.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-295">The following figures show the previously described filters.</span></span>
  
<span data-ttu-id="3cbaa-p124">Filtrar por **Nombre**. Seleccione la lista de vínculos que han de mostrarse en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-p124">Filter by **Name**. Select the list of links that need to be displayed in the graph.</span></span>
  
![Filtrado por Nombre en BandwidthUtilizationAnalyzer.](../media/Reskit_2012_Tools_Documentation_Image12.jpg)
  
<span data-ttu-id="3cbaa-p125">Filtrar por **Límite superado**. Seleccione **True** para aplicar el filtro.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-p125">Filter by **Exceeded limit**. Select **True** to enforce the filter.</span></span>
  
![Filtrado por Límite superado.](../media/Reskit_2012_Tools_Documentation_Image13.jpg)
  
<span data-ttu-id="3cbaa-p126">Filtrar por **Niveles críticos**. Seleccione **True** para aplicar el filtro.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-p126">Filter by **Critical levels**. Select **True** to enforce the filter.</span></span>
  
![Filtrado por Niveles críticos.](../media/Reskit_2012_Tools_Documentation_Image14.jpg)
  
<span data-ttu-id="3cbaa-p127">Filtrar por **Infrautilizado**. Seleccione **True** para aplicar el filtro.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-p127">Filter by **Under utilized**. Select **True** to enforce the filter.</span></span>
  
![Filtrado por Sin aprovechar.](../media/Reskit_2012_Tools_Documentation_Image15.jpg)
  
<span data-ttu-id="3cbaa-p128">Filtrar por **Tipo de vínculo**. Seleccione el tipo o tipos que desee mostrar.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-p128">Filter by **Link Type**. Select the type or types that need to be displayed.</span></span>
  
![Filtrado por Tipo de vínculo.](../media/Reskit_2012_Tools_Documentation_Image16.jpg)
  
<span data-ttu-id="3cbaa-p129">Filtrar por **Región**. Seleccione una lista de regiones cuyos vínculos desee mostrar.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-p129">Filter by **Region**. Select a list of regions whose links need to be displayed.</span></span>
  
![Filtrado por Región.](../media/Reskit_2012_Tools_Documentation_Image17.jpg)
  
### <a name="requirements"></a><span data-ttu-id="3cbaa-314">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3cbaa-314">Requirements</span></span>

- <span data-ttu-id="3cbaa-315">.NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="3cbaa-315">The .NET Framework 3.5</span></span>
    
- <span data-ttu-id="3cbaa-316">Microsoft Excel 2010 o Excel 2007</span><span class="sxs-lookup"><span data-stu-id="3cbaa-316">Microsoft Excel 2010 or Excel 2007</span></span>
    
### <a name="summary"></a><span data-ttu-id="3cbaa-317">Resumen</span><span class="sxs-lookup"><span data-stu-id="3cbaa-317">Summary</span></span>

<span data-ttu-id="3cbaa-p130">El analizador de uso de ancho de banda se utiliza para representar el uso de ancho de banda de audio para el tráfico de comunicaciones unificadas en la red. Esta herramienta también se puede utilizar para informar sobre el uso de ancho de banda de vídeo en la red.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-p130">Bandwidth Utilization Analyzer is used to plot the audio bandwidth utilization for UC traffic across the network. This tool can be used to report the utilization of video bandwidth on the network as well.</span></span>
  
## <a name="call-parkometer"></a><span data-ttu-id="3cbaa-320">Call Parkometer (Estacionamiento de llamadas)</span><span class="sxs-lookup"><span data-stu-id="3cbaa-320">Call Parkometer</span></span>
<span data-ttu-id="3cbaa-321"><a name="callpark"> </a></span><span class="sxs-lookup"><span data-stu-id="3cbaa-321"></span></span>

<span data-ttu-id="3cbaa-322">Call Parkometer es una aplicación de línea de comandos que proporciona acceso rápido a la base de datos de órbitas de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-322">Call Parkometer is a command-line application that provides easy access to the Call Park orbit database.</span></span>
  
### <a name="description"></a><span data-ttu-id="3cbaa-323">Descripción</span><span class="sxs-lookup"><span data-stu-id="3cbaa-323">Description</span></span>

<span data-ttu-id="3cbaa-324">Call Parkometer es una herramienta que se utiliza para realizar un seguimiento de las llamadas estacionadas actualmente.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-324">Call Parkometer is a tool to track currently parked calls.</span></span> <span data-ttu-id="3cbaa-325">También recopila estadísticas sobre el uso de órbitas y el servidor de estacionamiento de llamadas (CPS).</span><span class="sxs-lookup"><span data-stu-id="3cbaa-325">It also collects statistics about orbits and Call Park Server (CPS) usage.</span></span> <span data-ttu-id="3cbaa-326">Esta herramienta de línea de comandos proporciona acceso de lectura y escritura la órbita de CPS base de datos de SQL Server desde un equipo local o conectado de forma remota.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-326">This command-line tool provides both read and write-access to the CPS orbit SQL Server database from a local or remotely connected computer.</span></span>
  
<span data-ttu-id="3cbaa-p132">Todas las opciones se excluyen mutuamente. La sintaxis de línea de comandos es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="3cbaa-p132">All options are mutually exclusive. Command-line syntax is as follows:</span></span>
  
- <span data-ttu-id="3cbaa-329">parámetro **-o** , todos órbita rangos configurados para este grupo de listas.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-329">**-o** parameter—lists all orbit ranges configured for this pool.</span></span>
    
- <span data-ttu-id="3cbaa-330">parámetro **-n** : listas utilizadas actualmente todas las órbitas de este grupo.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-330">**-n** parameter—lists all currently used orbits in this pool.</span></span> <span data-ttu-id="3cbaa-331">La información que se muestra es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="3cbaa-331">The information displayed is as follows:</span></span>
    
  - <span data-ttu-id="3cbaa-332">Identificador uniforme de recursos (URI) de SIP del estacionado y el estacionador.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-332">SIP Uniform Resource Identifier (URI) of the parkee and parker.</span></span>
    
  - <span data-ttu-id="3cbaa-333">Nombre de host del CPS donde se ha estacionado la llamada.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-333">Host name of the CPS where the call is parked.</span></span>
    
  - <span data-ttu-id="3cbaa-334">Marca de tiempo correspondiente al momento en que se estacionó la llamada.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-334">Time stamp of when the call was parked.</span></span>
    
- <span data-ttu-id="3cbaa-335">parámetro **-f** : muestra el número de Órbitas libres en la agrupación.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-335">**-f** parameter—lists the number of currently free orbits in the pool.</span></span>
    
- <span data-ttu-id="3cbaa-336">**-r \<n\> ** parámetro — muestra el \<n\> última estacionado llamadas.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-336">**-r \<n\>** parameter—lists the \<n\> last parked calls.</span></span> <span data-ttu-id="3cbaa-337">La información mostrada es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="3cbaa-337">The information displayed is as follows:</span></span>
    
  - <span data-ttu-id="3cbaa-338">URI de SIP del estacionado.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-338">Parkee SIP URI.</span></span>
    
  - <span data-ttu-id="3cbaa-339">URI de SIP del estacionador.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-339">Parker SIP URI.</span></span>
    
  - <span data-ttu-id="3cbaa-340">Nombre de host del CPS donde se estacionó la llamada.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-340">Host name of the CPS where the call was parked.</span></span>
    
  - <span data-ttu-id="3cbaa-341">Marca de tiempo correspondiente al momento en que se recuperó o finalizó la llamada.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-341">Time stamp of when the call was retrieved or dropped.</span></span>
    
- <span data-ttu-id="3cbaa-342">**-t\<n\> ** parámetro - prueba reservando una órbita en la base de datos para mostrar la aleatoriedad de los números asignados orbital.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-342">**-t\<n\>** parameter - tests reserving an orbit in the database to show the randomness of the assigned orbit numbers.</span></span>
    
### <a name="output"></a><span data-ttu-id="3cbaa-343">Salida</span><span class="sxs-lookup"><span data-stu-id="3cbaa-343">Output</span></span>

<span data-ttu-id="3cbaa-344">Según los parámetros de entrada especificados en el símbolo del sistema, Call Parkometer muestra la salida siguiente:</span><span class="sxs-lookup"><span data-stu-id="3cbaa-344">Depending on the input parameters that are specified at a command prompt, Call Parkometer displays the following output:</span></span>
  
- <span data-ttu-id="3cbaa-345">Todos los intervalos de órbitas configurados para este grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="3cbaa-345">All orbit ranges that are configured for this pool</span></span>
    
- <span data-ttu-id="3cbaa-346">Llamadas estacionadas actualmente</span><span class="sxs-lookup"><span data-stu-id="3cbaa-346">Currently parked calls</span></span>
    
- <span data-ttu-id="3cbaa-347">Número de órbitas libres (disponibles)</span><span class="sxs-lookup"><span data-stu-id="3cbaa-347">Number of free (available) orbits</span></span>
    
- <span data-ttu-id="3cbaa-348">Llamadas estacionadas recientemente</span><span class="sxs-lookup"><span data-stu-id="3cbaa-348">Recently parked calls</span></span>
    
- <span data-ttu-id="3cbaa-349">Órbitas reservadas para comprobar valores de órbitas uniformes y aleatorias</span><span class="sxs-lookup"><span data-stu-id="3cbaa-349">Reserved orbits for testing uniform and random orbit values</span></span>
    
### <a name="purpose"></a><span data-ttu-id="3cbaa-350">Finalidad</span><span class="sxs-lookup"><span data-stu-id="3cbaa-350">Purpose</span></span>

<span data-ttu-id="3cbaa-p135">El objetivo de la herramienta CPS es proporcionar acceso mediante línea de comandos a la base de datos de CPS. El administrador puede ver el uso de CPS y determinar el número de órbitas asignadas a un grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-p135">The purpose of the CPS tool is to provide command-line access to the CPS database. The administrator can view the CPS usage and determine the number of orbits assigned to a pool.</span></span>
  
### <a name="requirements"></a><span data-ttu-id="3cbaa-353">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3cbaa-353">Requirements</span></span>

<span data-ttu-id="3cbaa-354">No existen requisitos si esta herramienta se ejecuta en el mismo equipo que ejecuta CPS.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-354">There are no requirements if this tool is run on the same computer that is running CPS.</span></span> <span data-ttu-id="3cbaa-355">Si esta herramienta se ejecuta en un equipo remoto, la base de datos de SQL Server que utiliza Skype para Business Server 2015 debe configurarse para permitir el acceso remoto.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-355">If this tool is run on a remote computer, the SQL Server database used by Skype for Business Server 2015 must be configured to allow remote access.</span></span> <span data-ttu-id="3cbaa-356">Parkometer de llamada debe configurarse con una cadena de conexión de base de datos de SQL Server para conectarse a la SQL Server del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-356">Call Parkometer must be configured with a SQL Server database connection string to connect to the pool's SQL Server.</span></span> <span data-ttu-id="3cbaa-357">Esta cadena de conexión de base de datos de SQL Server se define en el archivo de configuración **parkometer.exe.config**. Se debe colocar en el mismo directorio donde se encuentra parkometer.exe.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-357">This SQL Server database connection string is defined in the configuration file, **parkometer.exe.config**. It must be placed in the same directory where parkometer.exe is located.</span></span> <span data-ttu-id="3cbaa-358">El siguiente archivo XML es un ejemplo de un parkometer.exe.config. Los parámetros que deben configurarse son nombre de usuario (por ejemplo, mydomain\Administrator), (por ejemplo, micontraseña) de contraseña y nombre de host (por ejemplo, miservidor).</span><span class="sxs-lookup"><span data-stu-id="3cbaa-358">The following XML file is an example of a parkometer.exe.config. The parameters that must be configured are user name (for example, mydomain\Administrator), password (for example, mypassword), and host name (for example, myserver).</span></span>
  
```
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <appSettings>
   <add key="SQL" value="server=myserver\RTC;
database=cpsdyn;
User Id=mydomain\Administrator;
Password=mypassword.;
Integrated Security=false;"/>
  </appSettings>
</configuration>
```

### <a name="examples"></a><span data-ttu-id="3cbaa-359">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="3cbaa-359">Examples</span></span>

<span data-ttu-id="3cbaa-360">Implementar intervalos de órbita: el parámetro -o enumera todos los intervalos de órbita que están configurados para este grupo tal como se muestra</span><span class="sxs-lookup"><span data-stu-id="3cbaa-360">Deployed orbit ranges: the -o parameter lists all orbit ranges that are configured for this pool as shown</span></span>
  
![Órbita de estacionamiento en Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image18.jpg)
  
<span data-ttu-id="3cbaa-362">Actualmente estacionado llamadas: el parámetro - n muestra todas las órbitas utilizadas actualmente en este grupo, como se muestra</span><span class="sxs-lookup"><span data-stu-id="3cbaa-362">Currently parked calls: the -n parameter lists all currently used orbits on this pool as shown</span></span>
  
![Llamadas actualmente estacionadas en Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image19.jpg)
  
<span data-ttu-id="3cbaa-364">Número de Órbitas libres: el parámetro -f indica el número de Órbitas actualmente disponible en el grupo tal como se muestra</span><span class="sxs-lookup"><span data-stu-id="3cbaa-364">Number of free orbits: the -f parameter lists the number of currently free orbits in the pool as shown</span></span>
  
![Órbitas libres en Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image20.jpg)
  
<span data-ttu-id="3cbaa-366">Recientemente estacionado llamadas: - r \<n\> listas de parámetros de la \<n\> última estacionado llamadas como se muestra</span><span class="sxs-lookup"><span data-stu-id="3cbaa-366">Recently parked calls: the -r \<n\> parameter lists the \<n\> last parked calls as shown</span></span>
  
![Llamadas recién estacionadas en Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image21.jpg)
  
<span data-ttu-id="3cbaa-368">Reserva de la órbita de prueba: -t \<n\> parámetro comprueba reservar una órbita en la base de datos, como se muestra</span><span class="sxs-lookup"><span data-stu-id="3cbaa-368">Test orbit reservation: the -t \<n\> parameter tests reserving an orbit in the database as shown</span></span>
  
![Reservas de órbitas de prueba en Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image22.jpg)
  
### <a name="summary"></a><span data-ttu-id="3cbaa-370">Resumen</span><span class="sxs-lookup"><span data-stu-id="3cbaa-370">Summary</span></span>

<span data-ttu-id="3cbaa-371">Call Parkometer es una herramienta de línea de comandos que proporciona información detallada sobre el servidor de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-371">Call Parkometer is a command-line tool that provides detailed information about the Call Park Server.</span></span>
  
## <a name="dbanalyze"></a><span data-ttu-id="3cbaa-372">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="3cbaa-372">DBAnalyze</span></span>
<span data-ttu-id="3cbaa-373"><a name="dba"> </a></span><span class="sxs-lookup"><span data-stu-id="3cbaa-373"></span></span>

### <a name="description"></a><span data-ttu-id="3cbaa-374">Descripción</span><span class="sxs-lookup"><span data-stu-id="3cbaa-374">Description</span></span>

<span data-ttu-id="3cbaa-375">DBAnalyze es una herramienta de línea de comandos que permite a los administradores para recopilar informes de análisis sobre el Skype para bases de datos de Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-375">DBAnalyze is a command-line tool that helps administrators to gather analysis reports about the Skype for Business Server 2015 databases.</span></span> <span data-ttu-id="3cbaa-376">DBAnalyze tiene los modos siguientes: diagnóstico, datos de usuario, conferencia, MCU y fragmentación de disco:</span><span class="sxs-lookup"><span data-stu-id="3cbaa-376">DBAnalyze has the following modes: diagnostic, user data, conference, MCUs, and disk fragmentation:</span></span>
  
- <span data-ttu-id="3cbaa-377">**Modo de diagnóstico** Crea un informe que incluya información sobre tablas (número de tamaño del índice, fragmentación, tamaño de los datos y registros), tamaño de los archivos de datos y de registro, la última vez que copia de seguridad, distribución de contactos entre servidores que ejecutan Microsoft Office Communications Server, el número medio de permisos, contactos, contenedores, suscripciones, publicaciones, extremos por usuario, todos los usuarios asignados correctamente, los usuarios que no se pueden enrutar, el promedio de conferencias organizados por usuario, las conferencias programadas, conferencias activas, y la versión de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-377">**Diagnostic mode** Creates a report that includes information about tables (number of records, fragmentation, data size, and index size), data and log file sizes, the last back-up time, contact distribution among servers that are running Microsoft Office Communications Server, the average number of permissions, contacts, containers, subscriptions, publications, endpoints per user, any improperly homed users, users that can't be routed, the average number of conferences organized per user, scheduled conferences, active conferences, and the database version.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3cbaa-378">La ejecución en modo de diagnóstico puede afectar al rendimiento del servidor.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-378">Running diagnostic mode can affect server performance.</span></span> 
  
- <span data-ttu-id="3cbaa-379">**Modo de datos de usuario** Contacto de informes, contenedor, suscripción, publicación, permisos y datos del grupo de contacto para un usuario específico o para usuarios que tienen ese usuario en sus listas de contactos y permisos.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-379">**User data mode** Reports contact, container, subscription, publication, permission, and contact-group data for a specified user or for users who have that user in their contact and permission lists.</span></span> <span data-ttu-id="3cbaa-380">Este modo también proporciona datos de resumen para conferencias que un usuario organice o a las que esté invitado.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-380">This mode also reports summary data for conferences that a user organizes or is invited to.</span></span>
    
- <span data-ttu-id="3cbaa-381">**Modo conferencia** Informes de datos detallados para una conferencia específica, incluya todos los detalles de la programación de tiempo para la conferencia, la lista de invitados, la lista de tipos de medio permiten para la conferencia, active MCU (unidades de control multipunto), la lista de participantes activa y cada uno estado de señalización del participante.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-381">**Conference mode** Reports detailed data for a specific conference, including all schedule-time details for the conference, the invitee list, the list of media types allowed for the conference, active MCUs (multipoint control units), the active participant list, and each participant's signaling state.</span></span>
    
- <span data-ttu-id="3cbaa-382">**Descodificar el ID de la reunión** Descodifica una red telefónica pública conmutada (PSTN) ID que es especificado por el modificador **/pstnid** pero no se conecta al servidor para obtener información detallada de la reunión.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-382">**Decode Meeting ID** Decodes a public switched telephone network (PSTN) meeting ID that is specified by the **/pstnid** switch but does not connect to the back end for detailed information.</span></span>
    
- <span data-ttu-id="3cbaa-383">**Resolver la conferencia** Descodifica un identificador de reunión PSTN que es especificado por el modificador **/pstnid** y muestra información sobre la conferencia indicada por el Id.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-383">**Resolve conference** Decodes a PSTN meeting ID that is specified by the **/pstnid** switch and displays information about the conference indicated by the ID.</span></span>
    
- <span data-ttu-id="3cbaa-384">**Modo de MCU** Informes de ID, tipo de medios, dirección URL, estado del latido, carga de conferencia y carga participante para cada MCU en el grupo.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-384">**MCUs mode** Reports the ID, media type, URL, heartbeat status, conference load, and participant load for each MCU in the pool.</span></span>
    
- <span data-ttu-id="3cbaa-385">**Modo de fragmentación de disco** Muestra el estado de fragmentación de todos los discos.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-385">**Disk fragmentation mode** Displays the fragmentation status of all disks.</span></span>
    
<span data-ttu-id="3cbaa-p139">Esta herramienta puede utilizarse para diagnosticar diferentes problemas o para ayudar a los administradores con la planificación de capacidad. Por ejemplo, si la mayoría de los usuarios alojados en el servidor A eligen a usuarios alojados en el servidor B como sus contactos, el administrador puede mover los usuarios del servidor A al servidor B para reducir el tráfico entre servidores.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-p139">This tool can be used to diagnose various problems or to assist administrators with capacity planning. For example, if most of the users homed on server A choose users homed on server B as their contacts, the administrator can move the users on server A to server B to reduce cross-server traffic.</span></span>
  
### <a name="output"></a><span data-ttu-id="3cbaa-388">Salida</span><span class="sxs-lookup"><span data-stu-id="3cbaa-388">Output</span></span>

<span data-ttu-id="3cbaa-389">Esta herramienta genera informes predefinidos sobre el Skype para base de datos de Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-389">This tool outputs predefined reports about the Skype for Business Server 2015 database.</span></span> <span data-ttu-id="3cbaa-390">**Ruta de acceso**: %Archivos de programa%\Skype Empresarial Server 2015\Reskit</span><span class="sxs-lookup"><span data-stu-id="3cbaa-390">**Path**: %ProgramFiles%\Skype for Business Server 2015\Reskit</span></span>
  
### <a name="purpose"></a><span data-ttu-id="3cbaa-391">Finalidad</span><span class="sxs-lookup"><span data-stu-id="3cbaa-391">Purpose</span></span>

<span data-ttu-id="3cbaa-392">Para instalar Dbanalyze.exe, copie el archivo en una carpeta local y, a continuación, ejecute la herramienta.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-392">To install Dbanalyze.exe, copy it to a local folder and then run the tool.</span></span> <span data-ttu-id="3cbaa-393">Para usar la herramienta, ejecute el comando siguiente desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-393">To use the tool, run the following command from the command line.</span></span> <span data-ttu-id="3cbaa-394">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`A continuación se muestran las descripciones de las opciones de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-394">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` The descriptions for the command-line options are shown below.</span></span>
  
![Opciones de la línea de comandos para Dbanalyze.exe.](../media/Reskit_2012_Tools_Documentation_Image35.JPG)
  
### <a name="requirements"></a><span data-ttu-id="3cbaa-396">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3cbaa-396">Requirements</span></span>

 <span data-ttu-id="3cbaa-397">**Equipo** DBAnalyze puede ejecutarse únicamente desde un equipo unido al dominio que tenga Skype para Business Server 2015 instalado.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-397">**Computer** DBAnalyze can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span>
  
 <span data-ttu-id="3cbaa-398">**Red** El equipo debe ser capaz de conectarse a la base de datos back-end.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-398">**Network** The computer should be able to connect to the back-end database.</span></span>
  
 <span data-ttu-id="3cbaa-399">**Software** Skype Business Server 2015 componentes de software debe estar instalado antes de ejecutar DBAnalyze.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-399">**Software** Skype for Business Server 2015 software components must be installed before running DBAnalyze.</span></span>
  
 <span data-ttu-id="3cbaa-400">**Usuarios** La tabla siguiente muestra a los administradores que tienen los permisos necesarios para tener acceso a Skype para bases de datos de Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-400">**Users**The table below shows the administrators who have the necessary permissions to access Skype for Business Server 2015 databases.</span></span>
  
![Tabla de permisos para Dbanalyze.exe.](../media/Reskit_2012_Tools_Documentation_Image36.JPG)
  
> [!NOTE]
> <span data-ttu-id="3cbaa-402">Para el modo **/report:disk** se necesita una cuenta de administrador local.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-402">A local administrator account is required for **/report:disk** mode.</span></span>
  
### <a name="examples"></a><span data-ttu-id="3cbaa-403">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="3cbaa-403">Examples</span></span>

<span data-ttu-id="3cbaa-404">A continuación se muestran varios ejemplos de comandos de Dbanalyze.exe válidos:</span><span class="sxs-lookup"><span data-stu-id="3cbaa-404">The following are examples of valid Dbanalyze.exe commands:</span></span>
  
```
dbanalyze.exe /report:diag
dbanalyze.exe /report:user /user:usera@domainb.com
dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
dbanalyze.exe /report:resolve /pstnid:12345
dbanalyze.exe /report:mcus
dbanalyze.exe /report:disk
```

### <a name="summary"></a><span data-ttu-id="3cbaa-405">Resumen</span><span class="sxs-lookup"><span data-stu-id="3cbaa-405">Summary</span></span>

<span data-ttu-id="3cbaa-406">DBAnalyzer proporciona a los administradores un rápido y fácil de analizar Skype para bases de datos de Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-406">DBAnalyzer provides administrators a quick and easy to analyze Skype for Business Server 2015 databases.</span></span>
  
## <a name="import-storage-service-data"></a><span data-ttu-id="3cbaa-407">Import Storage Service Data (Importación de datos del servicio de almacenamiento)</span><span class="sxs-lookup"><span data-stu-id="3cbaa-407">Import Storage Service Data</span></span>
<span data-ttu-id="3cbaa-408"><a name="Issd"> </a></span><span class="sxs-lookup"><span data-stu-id="3cbaa-408"></span></span>

<span data-ttu-id="3cbaa-409">La herramienta de kit de recursos ImportStorageServiceData permite reimportar datos de colas y puntos de conexión que hayan sido vaciados del servicio de almacenamiento (LYSS) de nuevo en el servicio de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-409">The ImportStorageServiceData resource kit tool allows for re-importing Queue and Endpoint data that was flushed out of the Storage Service (LYSS) back into the Storage Service.</span></span>
  
### <a name="description"></a><span data-ttu-id="3cbaa-410">Descripción</span><span class="sxs-lookup"><span data-stu-id="3cbaa-410">Description</span></span>

<span data-ttu-id="3cbaa-411">Los datos del servicio de almacenamiento pueden haber sido vaciados de forma automática (periódica) según el estado del elemento de cola o el tamaño de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-411">The data flushed out of the Storage Service could have been automatic (periodic) based on Queue Item status or database size.</span></span> <span data-ttu-id="3cbaa-412">Puede haber ocurrido debido a la invocación manual del cmdlet de la conmutación por error del grupo de servidores o por el cmdlet StorageServiceFullFlush (invocado por el cmdlet de conmutación por error del grupo de servidores).</span><span class="sxs-lookup"><span data-stu-id="3cbaa-412">It could have happened due to the manual invocation of the pool failover cmdlet, or the StorageServiceFullFlush cmdlet (which the pool failover cmdlet invokes).</span></span> <span data-ttu-id="3cbaa-413">Tenga en cuenta que datos idealmente no deben volver a importarse si cualquiera del tamaño de la base de datos de servicio de almacenamiento de información (LYSS) en la parte delantera está por encima del nivel normal, porque al hacerlo sólo provocará más datos a ser exportados hacia. Además, los problemas que podrían haber contribuido a errores que provocaron que la cola de servicio de almacenamiento de información crecer en primer lugar se deben resolver (para ejemplos de errores de Exchange extremo, problemas de red u otros problemas).</span><span class="sxs-lookup"><span data-stu-id="3cbaa-413">Note that data should ideally not be re-imported if any of the Storage Service (LYSS ) database size on the front ends is above the normal level, because doing so will likely just cause more data to be exported back out. Furthermore, any problems which could have contributed to errors that caused the Storage Service Queue to grow should first be resolved (for example Exchange endpoint errors, network issues, or other problems).</span></span>
  
 <span data-ttu-id="3cbaa-414">**Escenario 1:** durante la conmutación por error del grupo de servidores, los archivos pueden vaciarse del servicio de almacenamiento para cada front-end.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-414">**Scenario 1:** during pool failover, files may be flushed out from storage service for each front end.</span></span> <span data-ttu-id="3cbaa-415">Después de completar la conmutación por error, debe ejecutarse la herramienta para volver a importar los datos.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-415">After failover is completed, the tool should be run to re-import the data.</span></span>
  
 <span data-ttu-id="3cbaa-416">**Escenario 2:** los datos se vacían automáticamente todos los días o cuando el tamaño de la base de datos del servicio de almacenamiento supera determinados umbrales (por ejemplo, 60 %, 80 %, 90 %).</span><span class="sxs-lookup"><span data-stu-id="3cbaa-416">**Scenario 2:** data is being flushed automatically each day or in response to Storage Service database exceeding certain size thresholds ( for example 60%, 80%, 90% full ).</span></span> <span data-ttu-id="3cbaa-417">El administrador debe volver a importar de forma periódica los datos que hayan sido vaciados de forma automática.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-417">This automatically flushed data should be re-imported routinely by the administrator.</span></span> <span data-ttu-id="3cbaa-418">En la situación anterior, si no se implementa el módulo de supervisión SCOM, hay eventos de Skype para el servicio de almacenamiento de servidor empresariales relacionadas con los datos que se vuelcan desde el servicio de almacenamiento de información.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-418">In the above situation, if the monitoring SCOM pack is not deployed, there are events for Skype for Business Server Storage Service relating to data being flushed from the Storage Service.</span></span> <span data-ttu-id="3cbaa-419">Los id. de evento son 32075 (se ha iniciado una operación de vaciado completo), 32076 (se ha completado el vaciado completo), 32082 (se ha iniciado el vaciado de nivel de mantenimiento), 32083 (se ha completado el vaciado de nivel de mantenimiento) y 32089 (se ha producido un vaciado porque se ha llenado la base de datos).</span><span class="sxs-lookup"><span data-stu-id="3cbaa-419">Event IDs of 32075 (full flush operation is started), 32076 (full flush has completed), 32082 (maintenance level flush started), 32083 (maintenance level flush complete), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="3cbaa-420">Estos identificadores de evento se corresponden con la versión RTM.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-420">Note these event Ids correspond to the RTM release.</span></span> <span data-ttu-id="3cbaa-421">Cuando un administrador ve estos eventos, significa que hay archivos que se han volcado hacia fuera. Estos datos deben importarse rutinariamente mediante esta herramienta, por ejemplo una vez por semana.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-421">When an administrator sees these events, it means that there are files that have been flushed out. This data should routinely be imported back using this tool, for example once per week.</span></span>
  
<span data-ttu-id="3cbaa-422">Para la versión de servicio en línea, si se implementa el paquete SCOM para Skype para Business Server de supervisión de estado, hay nuevas alertas podrán alegar que pida al administrador que volver a importar esos datos en el servicio de almacenamiento de información.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-422">For the Online Service release, if health monitoring SCOM pack for Skype for Business Server is deployed, there are new alerts which may be raised which ask the administrator to re-import the flushed data back into Storage Service.</span></span> <span data-ttu-id="3cbaa-423">Existirá un evento correspondiente en el registro de eventos del servidor front-end que haya activado la alerta.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-423">There will be a corresponding event in the event log on the Front End server which triggered the alert.</span></span> <span data-ttu-id="3cbaa-424">El evento ofrecerá una descripción de la ruta de acceso principal donde se encuentran los archivos de los datos vaciados, así como el número de archivos que cumplen con los criterios de alerta.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-424">The event will give a description of the Parent path under which the flushed data files are located, as well as how many files there are which meet the alert criteria.</span></span> <span data-ttu-id="3cbaa-425">Los criterios de alerta es que haya X o más archivos en la ruta de acceso primaria con un mínimo de Y días (donde X e Y están predefinidos en el servicio de almacenamiento, pero pueden reemplazarse si se cambia el archivo APPCONFIG).</span><span class="sxs-lookup"><span data-stu-id="3cbaa-425">The alert criteria is that there are X or more files under the particular parent path which are at least Y days old ( where X and Y are preset within the StorageService but can be overridden by changing the APPCONFIG file.)Two examples of events which can trigger the health alert are shown below, with the difference being their parent path.</span></span> <span data-ttu-id="3cbaa-426">A continuación se muestran dos ejemplos de eventos que pueden activar la alerta de estado, cuya diferencia es la ruta de acceso primaria.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-426">One possibility is under Web service file share, while the other possibility is the local Application Data directory of each front end.</span></span> <span data-ttu-id="3cbaa-427">Una posibilidad se encuentra en el recurso compartido de archivos del servicio web, mientras que la otra es el directorio de datos de aplicación local de cada front-end (por ejemplo, c:\ProgramData\Microsoft\Skype Empresarial Server 2015\StorageService ).</span><span class="sxs-lookup"><span data-stu-id="3cbaa-427">( for example c:\ProgramData\Microsoft\Skype for Business Server 2015\StorageService ).</span></span> <span data-ttu-id="3cbaa-428">A continuación, el administrador ejecutará esta herramienta de kit de recursos.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-428">The administrator will then run this reskit tool.</span></span>
  
<span data-ttu-id="3cbaa-429">Esta herramienta aumentará la carga de CPU y de E/S en el front-end donde se ejecute, así como en otros front-end, si los datos no son propiedad del front-end donde se ejecuta la herramienta.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-429">This tool will increase CPU and IO load on the front end it is running on, as well as other front ends, in the situation that the data is not owned by the front end that the tool is executed on.</span></span> <span data-ttu-id="3cbaa-430">Se recomienda ejecutar esta herramienta cuando los front-end no estén sometidos a cargas elevadas de CPU y de E/S (por ejemplo, en horas de poca actividad).</span><span class="sxs-lookup"><span data-stu-id="3cbaa-430">We recommend runng this tool when front ends are not under heavy CPU and IO load, for example outside of peak hours.</span></span> <span data-ttu-id="3cbaa-431">En segundo lugar, esta herramienta puede tardar entre 2 y 3 minutos para importar un archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-431">Secondly, this tool can 2 to 3 minutes to import one data file.</span></span> <span data-ttu-id="3cbaa-432">Esto debe tenerse en cuenta al calcular el tiempo de ejecución de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-432">Keep this in mind when estimating how long tool will be running.</span></span> <span data-ttu-id="3cbaa-433">El archivo de registro detallado generado por la herramienta aparecerá de forma predeterminada en el almacén de archivos.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-433">The verbose log file generated by the tool will by default appear on the File Store.</span></span> <span data-ttu-id="3cbaa-434">Elimínelo si no se detectan errores, ya que el tamaño del archivo de registro puede ser de varias decenas de MB o más.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-434">Delete it if there are no errors reported, because the log file can be tens of MB or more.</span></span>
  
![Eventos de ejemplo del registro de eventos del servidor de almacenamiento.](../media/Reskit_2012_Tools_Documentation_Image1.jpg)
  
### <a name="requirements"></a><span data-ttu-id="3cbaa-436">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3cbaa-436">Requirements</span></span>

<span data-ttu-id="3cbaa-437">Instale el Skype para las herramientas del Kit de recursos de Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-437">Install the Skype for Business Server 2015 Resource Kit tools.</span></span> <span data-ttu-id="3cbaa-438">La herramienta se ejecuta en equipos unidos a un dominio donde se instalan Skype para Business Server y Skype para el Shell de administración de servidor de empresa.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-438">The tool runs on domain-joined machines where Skype for Business Server and Skype for Business Server Management Shell are installed.</span></span> <span data-ttu-id="3cbaa-439">La herramienta utiliza un cmdlet del shell de administración para identificar todos los servidores Front-End de la piscina.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-439">The tool uses a cmdlet from the management shell to identify all the Front End servers in the pool.</span></span> <span data-ttu-id="3cbaa-440">En segundo lugar, la herramienta debe ejecutarse desde un equipo en el grupo que tiene instalada la base de datos de **RtcLocal** .</span><span class="sxs-lookup"><span data-stu-id="3cbaa-440">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="3cbaa-441">Esta base de datos se utiliza la herramienta para recuperar la ubicación del recurso compartido de archivos de servicio Web para el grupo.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-441">This database is used by the tool to retrieve the location of the WEBSERVICE file share for the pool.</span></span> <span data-ttu-id="3cbaa-442">Además, antes de utilizar la herramienta, cada servidor Front-End debe habilitar Windows PowerShell Remoting utilizando **Enable-PSRemoting** en cada servidor Front-End, así como el equipo en el que se ejecutó la herramienta.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-442">Additionally, before using the tool, each Front End server must first enable Windows PowerShell Remoting using **Enable-PSRemoting** on each Front End server, as well as the machine that the tool is executed from.</span></span> <span data-ttu-id="3cbaa-443">De lo contrario, se producirá un error de comandos remotos de Windows PowerShell de esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-443">Otherwise, remote Windows PowerShell commands from this tool will fail.</span></span> <span data-ttu-id="3cbaa-444">Windows PowerShell Remoting puede desactivarse en todos los servidores Front-End del grupo después de que finalice.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-444">Windows PowerShell Remoting can be turned off on all Front End servers in the pool after it is finished.</span></span> <span data-ttu-id="3cbaa-445">Por último, la cuenta o credencial invocar la herramienta debe tener permiso de lectura y escritura al recurso compartido de archivo webservice para el grupo que se ejecutan en esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-445">Finally, the account or credential invoking the tool must have read/write permission to the webservice file share for the pool they are executing this tool on.</span></span> <span data-ttu-id="3cbaa-446">De lo contrario se producirá un error de la herramienta con errores de permiso de E/S.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-446">Otherwise the tool will fail with IO Permission errors.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3cbaa-447">En Windows Server 2012, Windows PowerShell Remoting está habilitado de forma predeterminada, pero no en el sistema operativo Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-447">On Windows Server 2012, Windows PowerShell Remoting is enabled by default, but not on the Windows Server 2008 operating system.</span></span> 
  
### <a name="examples"></a><span data-ttu-id="3cbaa-448">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="3cbaa-448">Examples</span></span>

```
>  C:\StorageService>ImportStorageServiceData.exe
Description:
This tool will re-import Storage Service (LYSS) flushed queue data back in.  For a pool: you are required to run this tool on a machine inside the pool which has the Lync Server Management Shell installed.  Additionally, all front end machines need to have Windows Powershell Remoting enabled before executing this tool by executing Enable-PSRemoting.  Also, please ensure that all Storage Service instance DB Size are at the 'Normal' level (verify this by viewing Eventlog events). Otherwise re-importing may cause data to be flushed out again if any Storage Service instance DB size level goes above 'Normal'.
Usage: Default behavior is to Import data from web service file share as well as any files on all Front End machines in pool.
Additional Options:
-Verbose                    : Turn verbose output on.

-StorageServiceHostName     : Host Name of Storage Service WCF endpoint.  ( Default=localhost netnamedpipe binding. )
                                    
-FileSharePath              : Import only all data from just under the UNC path specified.

ActivityID: cc3b62ff-bb66-4e61-a6e2-96cb3626315c. <-- Use this to correlate with StorageService trace logs if troubleshooting.
Type Server name (TCP binding) or press <enter> for localhost (NamePipe binding):
Using NetNamedPipeBinding...
OnTopologyChanged Event received
Web Service File Share: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService

Front Ends:
server.vdomain.com
server2.vdomain.com
server1.vdomain.com
server3.vdomain.com
Looking under directory: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService for exported data.
# Files found: 8
Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml
Items deserialized: 20

All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml

All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml: succeeded: 20, failed: 0

Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml
Items deserialized: 20

[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server1.vdomain.com, queueItems=20

All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml

All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml: succeeded: 20, failed: 0

Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d3832e4__0.xml

Items deserialized: 20
[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server1.vdomain.com, queueItems=20

All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d
3832e4__0.xml

All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c
86684d3832e4__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d3832e4__0.xml: succeeded: 20, failed: 0

Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42287dd6__0.xml

Items deserialized: 20

[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server2.vdom
ain.com, queueItems=20

All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42
287dd6__0.xml

All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER2.vdomain.com\69844a271e6c5633a1f2
b46a42287dd6__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42287dd6__0.xml: succeeded: 20, failed: 0

Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER3.vdomain.com\3313935458e35b9b9759e08a15d251e6__0.xml

Items deserialized: 20

[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
ain.com, queueItems=1

All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\3313935458e35b9b9759e08a15
d251e6__0.xml

All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\3313935458e35b9b9759
e08a15d251e6__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER3.vdomain.com\3313935458e35b9b9759e08a15d251e6__0.xml: succeeded: 20, failed: 0

Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER3.vdomain.com\4501e04eae4856059346949ff817c220__0.xml
Items deserialized: 20
[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
ain.com, queueItems=1
All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\4501e04eae4856059346949ff8
17c220__0.xml
All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\4501e04eae4856059346
949ff817c220__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER3.vdomain.com\4501e04eae4856059346949ff817c220__0.xml: succeeded: 20, failed: 0
Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER3.vdomain.com\5ad77443ad955a22a876749be66d5317__0.xml

Items deserialized: 20
[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
ain.com, queueItems=20
All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\5ad77443ad955a22a876749be6
6d5317__0.xml
All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\5ad77443ad955a22a876
749be66d5317__0.xml
Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER3.vdomain.com\5ad77443ad955a22a876749be66d5317__0.xml: succeeded: 20, failed: 0
Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER3.vdomain.com\a11e27ae439a582288d4657eda86b565__0.xml
Items deserialized: 20
[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
ain.com, queueItems=20
All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\a11e27ae439a582288d4657eda
86b565__0.xml
All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\a11e27ae439a582288d4
657eda86b565__0.xml
Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER3.vdomain.com\a11e27ae439a582288d4657eda86b565__0.xml: succeeded: 20, failed: 0
All files have been imported into Storage Service for path: \\dc.vdomain.com\OcsFileStore\co1-WebSer
vices-1\StorageService
Importing files for: server.vdomain.com
No files founds.
Importing files for: server2.vdomain.com
No files founds.
Importing files for: server1.vdomain.com
No files founds.
Importing files for: server3.vdomain.com
No files founds.
Writing log: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\ImportStorageServiceData
Log20120910_1609SS
Tool has finished execution.
>  C:\StorageService>
```

## <a name="lcssync"></a><span data-ttu-id="3cbaa-449">LCSSync</span><span class="sxs-lookup"><span data-stu-id="3cbaa-449">LCSSync</span></span>
<span data-ttu-id="3cbaa-450"><a name="LCSSync"> </a></span><span class="sxs-lookup"><span data-stu-id="3cbaa-450"></span></span>

<span data-ttu-id="3cbaa-451">La herramienta LCSSync ayuda a implementar Skype para Business Server 2015 software de comunicaciones en un entorno de varios bosque.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-451">The LCSSync tool helps to deploy Skype for Business Server 2015 communications software in a multi-forest environment.</span></span> <span data-ttu-id="3cbaa-452">Esta herramienta se utiliza para sincronizar los usuarios y grupos de bosques de otro usuario como un servicios de dominio de Active Directory, póngase en contacto con el objeto a un bosque central donde está instalado Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-452">This tool is used to synchronize users and groups from different user forests as an Active Directory Domain Services contact object to a central forest where Skype for Business Server 2015 is installed.</span></span>
  
### <a name="description"></a><span data-ttu-id="3cbaa-453">Descripción</span><span class="sxs-lookup"><span data-stu-id="3cbaa-453">Description</span></span>

 <span data-ttu-id="3cbaa-454">LCSSync utiliza los servicios de dominio de Active Directory sincronizado póngase en contacto con objetos en el bosque central para habilitar a usuarios de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-454">LCSSync uses the synchronized Active Directory Domain Services contact objects in the central forest to enable users for Skype for Business Server.</span></span> <span data-ttu-id="3cbaa-455">Para proporcionar en Inicio de sesión único, la cuenta de usuario principal debe asignar al objeto de contacto de los servicios de dominio de Active Directory en el bosque central de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-455">To provide single sign-in, the primary user account must be mapped to the Active Directory Domain Services contact object in the central forest for Skype for Business Server 2015.</span></span> <span data-ttu-id="3cbaa-456">Esta herramienta ayuda a realizar dicha asignación.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-456">This tool helps perform that mapping.</span></span> <span data-ttu-id="3cbaa-457">Esta herramienta proporciona plantillas para crear agentes de administración en Microsoft Identity Integration Server.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-457">This tool provides templates for creating Management Agents in the Microsoft Identity Integration Server.</span></span>
  
### <a name="summary"></a><span data-ttu-id="3cbaa-458">Resumen</span><span class="sxs-lookup"><span data-stu-id="3cbaa-458">Summary</span></span>

<span data-ttu-id="3cbaa-459">La herramienta LCSSync ayuda a implementar Skype para el año 2015 de servidor empresarial en un entorno de varios bosque.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-459">The LCSSync tool helps to deploy Skype for Business Server 2015 in a multi-forest environment.</span></span>
  
## <a name="lookup-user-console"></a><span data-ttu-id="3cbaa-460">Lookup User Console (Consola de búsqueda de usuario)</span><span class="sxs-lookup"><span data-stu-id="3cbaa-460">Lookup User Console</span></span>
<span data-ttu-id="3cbaa-461"><a name="LUC"> </a></span><span class="sxs-lookup"><span data-stu-id="3cbaa-461"></span></span>

<span data-ttu-id="3cbaa-462">La herramienta LookupUserConsole muestra interno Skype Business Server información de enrutamiento acerca de determinados usuarios.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-462">The LookupUserConsole tool displays internal Skype for Business Server routing information about specific users.</span></span> <span data-ttu-id="3cbaa-463">Esta información puede ser útil para que el personal de soporte de Microsoft pueda diagnosticar problemas de implementación y enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-463">This information may be useful to Microsoft support personal in diagnosing deployment and routing problems.</span></span>
  
### <a name="description"></a><span data-ttu-id="3cbaa-464">Descripción</span><span class="sxs-lookup"><span data-stu-id="3cbaa-464">Description</span></span>

 <span data-ttu-id="3cbaa-465">Ejecutar LookupUserConsole.exe, se abrirá un símbolo que acepta direcciones SIP e intenta mostrar Skype interno Business Server información de enrutamiento sobre ellos.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-465">Executing LookupUserConsole.exe will open a command prompt that accepts SIP addresses and attempts to display internal Skype for Business Server routing information relating them.</span></span> <span data-ttu-id="3cbaa-466">Escriba **exit** para salir de la herramienta LookupUserConsole.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-466">Type **exit** to quit the LookupUserConsole tool.</span></span>
  
### <a name="requirements"></a><span data-ttu-id="3cbaa-467">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3cbaa-467">Requirements</span></span>

<span data-ttu-id="3cbaa-468">Instale el Skype para el Kit de recursos de Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-468">Install the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="3cbaa-469">La herramienta se ejecuta en equipos unidos a un dominio donde está instalado Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-469">The tool runs on domain-joined machines where Skype for Business Server is installed.</span></span>
  
### <a name="examples"></a><span data-ttu-id="3cbaa-470">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="3cbaa-470">Examples</span></span>

<span data-ttu-id="3cbaa-471">C:\Program Files\Skype for Business Server 2015\ResKit\>LookupUserConsole.exe</span><span class="sxs-lookup"><span data-stu-id="3cbaa-471">C:\Program Files\Skype for Business Server 2015\ResKit\>LookupUserConsole.exe</span></span>
  
```
> sip:john.doe@vdomain.com

  Execution time (ms):                            171.094
  Exeuction result:                               Success
  SIP URI:                                        sip:john.doe@vdomain.com
  User info:
    SID:                                          S-1-5-21-2831376166-29632525...    Display name:                                     John Doe
    Grouping ID:                                  00000000-0000-0000-0000-...
    Line URI:                                     <null>
    Policy assignment:                            TenantId={00000000--0000-000....
    SIP enabled:                                  True
    UC enabled:                                   False
    Tenant ID:                                    00000000-0000-0000-0000-...  Cluster info:
    Active cluster:                               pool0.vdomain.com
    Backup registrar cluster:                     <null>
    Deployment location:                          <null>
    Home Front-End FQDN:                          SERVER.vdomain.com
    Primary Registrar cluster:                    pool0.vdomain.com
    Remote Director external SIP FQDN:            <null>
    Remote Director internal SIP FQDN:            <null>
    Remote Director Web FQDN:                     <null>
    Routing group ID:                             4501e04e-ae48-5605-9346...
    Service tag ID:                               1266953005
    User Front-End resolved:                      True
    User in local forest:                         True
    User in remote forest:                        False
    User in split domain:                         False
    User-Services cluster:                        pool0.vdomain.com

> sip:nouser@vdomain.com

  Execution time (ms):                            948.7574
  Exeuction result:                               UserDoesNotExist

> exit
```

## <a name="msturnping"></a><span data-ttu-id="3cbaa-472">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="3cbaa-472">MsTurnPing</span></span>
<span data-ttu-id="3cbaa-473"><a name="MsTurnPing"> </a></span><span class="sxs-lookup"><span data-stu-id="3cbaa-473"></span></span>

<span data-ttu-id="3cbaa-474">La herramienta MSTurnPing permite a un administrador de Skype para el software de comunicaciones de Business Server 2015 para comprobar el estado de los servidores que ejecutan los servicios de autenticación de Audio y vídeo y borde de Audio y vídeo, así como los servidores que ejecutan la política de ancho de banda Servicios en la topología.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-474">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>
  
### <a name="description"></a><span data-ttu-id="3cbaa-475">Descripción</span><span class="sxs-lookup"><span data-stu-id="3cbaa-475">Description</span></span>

<span data-ttu-id="3cbaa-476">La herramienta MSTurnPing permite a un administrador de Skype para el software de comunicaciones de Business Server 2015 para comprobar el estado de los servidores que ejecutan los servicios de autenticación de Audio y vídeo y borde de Audio y vídeo, así como los servidores que ejecutan la política de ancho de banda Servicios en la topología.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-476">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>
  
<span data-ttu-id="3cbaa-477">La herramienta permite a los administradores realizar las pruebas siguientes:</span><span class="sxs-lookup"><span data-stu-id="3cbaa-477">The tool allows the administrator to perform the following tests:</span></span>
  
1. <span data-ttu-id="3cbaa-478">Prueba de servidor perimetral de A/V: la herramienta realiza las siguientes pruebas contra todos los servidores perimetrales de A/V en la topología:</span><span class="sxs-lookup"><span data-stu-id="3cbaa-478">A/V Edge Server test: The tool performs tests against all A/V Edge Servers in the topology by doing the following:</span></span>
    
  - <span data-ttu-id="3cbaa-479">Comprobar que el Skype para el servicio de autenticación de Audio y vídeo de Business Server está iniciado y puede emitir las credenciales adecuadas.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-479">Verifying that the Skype for Business Server Audio/Video Authentication service is started and can issue proper credentials.</span></span>
    
  - <span data-ttu-id="3cbaa-480">Comprobar que el Skype para el servicio perimetral de Audio/vídeo Business Server está iniciado y puede asignar los recursos en el contorno externo correctamente.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-480">Verifying that the Skype for Business Server Audio/Video Edge service is started and can allocate the resources on the external edge successfully.</span></span>
    
2. <span data-ttu-id="3cbaa-481">Prueba del servicio de directiva de ancho de banda: la herramienta realiza las pruebas siguientes contra todos los servidores que ejecutan los servicios de directiva de ancho de banda en la topología:</span><span class="sxs-lookup"><span data-stu-id="3cbaa-481">Bandwidth Policy Service test: The tool performs tests against all the servers that are running the Bandwidth Policy Services in the topology by doing the following:</span></span>
    
  - <span data-ttu-id="3cbaa-482">Comprobar que el Skype para el servicio de directivas de ancho de banda Business Server (autenticación) se inicia y puede emitir las credenciales adecuadas.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-482">Verifying that the Skype for Business Server Bandwidth Policy Service (Authentication) is started and can issue proper credentials.</span></span>
    
  - <span data-ttu-id="3cbaa-483">Comprobar que el Skype para servicio de directivas de ancho de banda Business Server (núcleo) está iniciado y puede realizar correctamente la comprobación de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-483">Verifying that the Skype for Business Server Bandwidth Policy Service (Core) is started and can perform the bandwidth check successfully.</span></span>
    
<span data-ttu-id="3cbaa-484">Esta herramienta debe ejecutarse en un equipo que forme parte de la topología y que tenga instalado el almacén local. </span><span class="sxs-lookup"><span data-stu-id="3cbaa-484">This tool must be run from a computer that is part of the topology and has the local store installed.</span></span> 
  
### <a name="output"></a><span data-ttu-id="3cbaa-485">Salida</span><span class="sxs-lookup"><span data-stu-id="3cbaa-485">Output</span></span>

<span data-ttu-id="3cbaa-486">La herramienta genera los resultados de todas las operaciones.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-486">The tool outputs the results of each of the operations.</span></span>
  
- <span data-ttu-id="3cbaa-487">Si se ejecuta la prueba **AudioVideoEdgeServer**, los resultados de la herramienta son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="3cbaa-487">If the **AudioVideoEdgeServer** test is performed, the tool outputs are the following:</span></span>
    
  - <span data-ttu-id="3cbaa-488">Los resultados de las pruebas de los equipos que proporcionan el Skype para el servicio de autenticación de servidor 2015 Audio y vídeo de negocio en la topología</span><span class="sxs-lookup"><span data-stu-id="3cbaa-488">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Authentication service in the topology</span></span>
    
  - <span data-ttu-id="3cbaa-489">Los resultados de las pruebas de los equipos que proporcionan el Skype para servicio Business Server 2015 audiovisual borde en la topología</span><span class="sxs-lookup"><span data-stu-id="3cbaa-489">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Edge service in the topology</span></span>
    
- <span data-ttu-id="3cbaa-490">Si se ejecuta la prueba **BandwidthPolicyServer**, los resultados de la herramienta son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="3cbaa-490">If the **BandwidthPolicyServer** test is performed, the tool outputs are the following:</span></span>
    
  - <span data-ttu-id="3cbaa-491">Los resultados de las pruebas de los equipos que proporcionan el Skype para Business Server 2015 banda Directiva servicio (autenticación) en la topología</span><span class="sxs-lookup"><span data-stu-id="3cbaa-491">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Authentication) in the topology</span></span>
    
  - <span data-ttu-id="3cbaa-492">Los resultados de las pruebas de los equipos que proporcionan el Skype para Business Server 2015 ancho de banda Directiva servicio (núcleo) de la topología</span><span class="sxs-lookup"><span data-stu-id="3cbaa-492">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Core) in the topology</span></span>
    
### <a name="requirements"></a><span data-ttu-id="3cbaa-493">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3cbaa-493">Requirements</span></span>

- <span data-ttu-id="3cbaa-494">Esta herramienta debe ejecutarse en un equipo que se encuentre en la topología y que tenga el almacén local.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-494">This tool must be run from a computer that is in the topology and that has the local store.</span></span>
    
- <span data-ttu-id="3cbaa-495">La herramienta debe ejecutarse como un administrador con acceso al almacén local.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-495">The tool must be run as an administrator who has access to the local store.</span></span>
    
### <a name="examples"></a><span data-ttu-id="3cbaa-496">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="3cbaa-496">Examples</span></span>

<span data-ttu-id="3cbaa-497">A continuación se muestra un ejemplo de la entrada de la herramienta.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-497">The following is an example of the tool input.</span></span>
  
```
MsTurnPing -ServerRole AudioVideoEdgeServer

MsTurnPing -ServerRole BandwidthPolicyServer
```

### <a name="summary"></a><span data-ttu-id="3cbaa-498">Resumen</span><span class="sxs-lookup"><span data-stu-id="3cbaa-498">Summary</span></span>

<span data-ttu-id="3cbaa-499">Esta herramienta puede ser un recurso valioso para los administradores de Business Server 2015 que deseen comprobar el estado de los servidores que ejecutan audio y vídeo y los servicios de políticas de ancho de banda de Skype.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-499">This tool can be a valuable resource to Skype for Business Server 2015 administrators who want to check the status of the servers that are running audio/video and bandwidth policy services.</span></span>
  
## <a name="network-configuration-viewer"></a><span data-ttu-id="3cbaa-500">Network Configuration Viewer (Visor de configuración de red</span><span class="sxs-lookup"><span data-stu-id="3cbaa-500">Network Configuration Viewer</span></span>
<span data-ttu-id="3cbaa-501"><a name="NCV"> </a></span><span class="sxs-lookup"><span data-stu-id="3cbaa-501"></span></span>

<span data-ttu-id="3cbaa-502">Visor de configuración de red puede utilizarse por Skype para administradores de software de comunicaciones de Business Server 2015 para ver la topología de red de control (CAC) de admisión de llamada para una empresa que está configurada para permitir sesiones de comunicación en tiempo real, como voz o llamadas de vídeo basadas en la capacidad de ancho de banda especificado.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-502">Network Configuration Viewer can be used by Skype for Business Server 2015 communications software administrators to view call admission control (CAC) network topology for an enterprise that is provisioned to allow real-time communication sessions, such as voice or video calls based on specified bandwidth capacity.</span></span> <span data-ttu-id="3cbaa-503">Skype para Business Server 2015 administradores definir directivas CAC, que se aplican por los servicios de políticas de ancho de banda que se instalan con Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-503">Skype for Business Server 2015 administrators define CAC policies, which are enforced by the Bandwidth Policy services that are installed with Skype for Business Server 2015.</span></span>
  
### <a name="description"></a><span data-ttu-id="3cbaa-504">Descripción</span><span class="sxs-lookup"><span data-stu-id="3cbaa-504">Description</span></span>

<span data-ttu-id="3cbaa-505">El visor de configuración de red (NetworkConfigurationViewer.exe) permite a los administradores realizar las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="3cbaa-505">Network Configuration Viewer (NetworkConfigurationViewer.exe) allows administrators to perform the following tasks:</span></span>
  
- <span data-ttu-id="3cbaa-506">Cargar y ver la topología de la red desde un Skype para la implementación de Business Server 2015 CAC en un formato gráfico.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-506">Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format.</span></span>
    
- <span data-ttu-id="3cbaa-507">Cargar y ver la topología de red de CAC de un archivo de registro de servidor de directiva de ancho de banda en un formato gráfico.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-507">Load and view CAC network topology from a Bandwidth Policy Server log file in a graphical format.</span></span>
    
- <span data-ttu-id="3cbaa-508">Guardar y almacenar la topología de red de CAC en formato XML en el disco.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-508">Save and store CAC network topology in an XML format on the disk.</span></span>
    
- <span data-ttu-id="3cbaa-509">Guardar y almacenar el diagrama de topología de red de CAC en formato JP o BMP.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-509">Save and store CAC network topology diagram in JPG or BMP format.</span></span>
    
- <span data-ttu-id="3cbaa-510">Ver los datos de configuración de la topología de red de CAC.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-510">View CAC network topology configuration data.</span></span>
    
- <span data-ttu-id="3cbaa-511">Ver la topología de red de CAC en estilo de vista de árbol.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-511">View CAC network topology in a tree-view style.</span></span>
    
- <span data-ttu-id="3cbaa-512">Definir conectores personalizados para vínculos de topología de red de CAC (por ejemplo, vínculos de sitio a región, de región a región y de sitio a sitio).</span><span class="sxs-lookup"><span data-stu-id="3cbaa-512">Define custom connectors for CAC network topology links (for example, site-to-region, region-to-region, and site-to-site links).</span></span>
    
- <span data-ttu-id="3cbaa-513">Ver información de sitio de topología de red de CAC, información de región y directivas de ancho de banda y vínculos de red proporcionados.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-513">View CAC network topology site information, region Information, and provisioned bandwidth policies and network links.</span></span>
    
### <a name="purpose"></a><span data-ttu-id="3cbaa-514">Finalidad</span><span class="sxs-lookup"><span data-stu-id="3cbaa-514">Purpose</span></span>

<span data-ttu-id="3cbaa-515">Ver vínculos de topología de red de CAC de empresa en una interfaz gráfica.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-515">View enterprise CAC network topology links in a graphical interface.</span></span>
  
### <a name="examples"></a><span data-ttu-id="3cbaa-516">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="3cbaa-516">Examples</span></span>

 <span data-ttu-id="3cbaa-517">**Carga y vista de topología de red CAC desde un Skype para la implementación de Business Server 2015 en un formato gráfico**: puede cargar y ver la configuración de topología de red CAC en cualquier Skype para equipo Business Server 2015 por Skype para los administradores de servidor de negocios 2015 con la opción de **Configuración de descarga de red** como se muestra en la figura siguiente.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-517">**Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format**: Skype for Business Server 2015 administrators can load and view CAC network topology configuration on any Skype for Business Server 2015 computer by using the **Download Network Configuration** option as shown in the figure below.</span></span> <span data-ttu-id="3cbaa-518">La herramienta no podrá descargar o ver la configuración cuando se implementa en un equipo que no tiene conectividad con el Skype para el almacén de configuración de servidor de negocios 2015.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-518">The tool will fail to download or view such a configuration when deployed on a computer that does not have connectivity to the Skype for Business Server 2015 configuration store.</span></span>
  
![Descargar la configuración de red.](../media/Reskit_2012_Tools_Documentation_Image23.jpg)
  
 <span data-ttu-id="3cbaa-520">**Topología de red de carga y CAC vista desde un archivo de registro del servidor de directivas de ancho de banda en un formato gráfico:** Skype para servidores de directivas de ancho de banda de Business Server 2015 guardar la topología de red CAC como parte del mecanismo de registro bajo el Skype Business Server 2015 ubicación de recurso compartido de archivo.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-520">**Load and View CAC network topology from a Bandwidth Policy server log file in a graphical format:** Skype for Business Server 2015 Bandwidth Policy servers save the CAC network topology as a part of the logging mechanism under the Skype for Business Server 2015 file share location.</span></span> <span data-ttu-id="3cbaa-521">Skype para los administradores de servidor de negocios 2015 puede ver ese archivo en un formato gráfico mediante la opción de **Configuración de red abierta** , como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-521">Skype for Business Server 2015 administrators can view such a file in a graphical format by using the **Open Network Configuration** option as shown below.</span></span>
  
![Abrir un archivo de registro de servidor de directiva de ancho de banda.](../media/Reskit_2012_Tools_Documentation_Image24.jpg)
  
<span data-ttu-id="3cbaa-523">Guarda y almacena la topología de la red CAC en formato XML en el disco: Skype para los administradores de servidor de negocios 2015 puede guardar el archivo de configuración de topología de red CAC en formato XML mediante la opción de **Guardar una copia de la configuración de red** , como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-523">Save and store CAC network topology in an XML format on the disk: Skype for Business Server 2015 administrators can save the CAC network topology configuration file in an XML format by using the **Save a copy of Network Configuration** option as shown below.</span></span> <span data-ttu-id="3cbaa-524">El archivo de configuración guardado puede utilizarse para ver una representación gráfica en un entorno sin conexión.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-524">The saved configuration file can then be used offline for graphical viewing purposes.</span></span>
  
![Guardar la configuración de red como archivo XML.](../media/Reskit_2012_Tools_Documentation_Image25.jpg)
  
<span data-ttu-id="3cbaa-526">Guardar y diagrama de topología de red de almacén CAC en formato JPG o BMP: Skype para los administradores de servidor de negocios 2015 puede guardar la configuración de topología de red CAC en un formato gráfico (formatos JPG y BMP) mediante el diagrama de **Guardar la configuración de red como imagen** opción como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-526">Save and Store CAC network topology diagram in JPG or BMP format: Skype for Business Server 2015 administrators can save the CAC network topology configuration in a graphical format (JPG and BMP file formats) by using the **Save Network Configuration diagram as picture** option as shown below.</span></span>
  
![Guardar la configuración de red como imagen.](../media/Reskit_2012_Tools_Documentation_Image26.jpg)
  
 <span data-ttu-id="3cbaa-528">**Datos de configuración de topología de red de vista CAC:** Skype para los administradores de servidor de negocios 2015 puede ver los datos de configuración de red relacionado como regiones de red, sitios de red, perfiles de ancho de banda y direcciones IP de subred sitio en formato de texto utilizando la opción de datos de configuración de red de vista tal como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-528">**View CAC network topology configuration data:**Skype for Business Server 2015 administrators can view related network configuration data such as network regions, network sites, bandwidth profiles, and site subnet IP addresses in a textual format by using the View Network Configuration data option as shown below.</span></span> 
  
![Ver los datos de configuración de red.](../media/Reskit_2012_Tools_Documentation_Image27.jpg)
  
 <span data-ttu-id="3cbaa-530">**Topología de red de vista CAC en un estilo de vista de árbol:** Skype para los administradores de servidor de negocios 2015 puede ver los datos de configuración de red relacionado en un estilo de vista de árbol gráfico mediante el panel de control en el lado izquierdo de la ventana de la herramienta como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-530">**View CAC network topology in a tree-view style:** Skype for Business Server 2015 administrators can view related network configuration data in a graphical tree view style by using the control panel on the left side of the tool window as shown below.</span></span>
  
![Ver los datos de configuración de red en vista de árbol.](../media/Reskit_2012_Tools_Documentation_Image28.jpg)
  
 <span data-ttu-id="3cbaa-532">**Vínculos de topología (por ejemplo, vínculos de sitio a sitio, región a otra y región del sitio) de red definir conectores personalizados para CAC:** Skype para los administradores de servidor de negocios 2015 puede definir conectores gráficos personalizada para los vínculos WAN de configuración de red CAC mediante la opción de configuración como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-532">**Define custom connectors for CAC network topology links (such as site-to-region, region-to-region, and site-to-site links):** Skype for Business Server 2015 administrators can define custom graphical connectors for CAC network configuration WAN links by using the Settings option as shown below.</span></span> <span data-ttu-id="3cbaa-533">Esto ayuda a diferenciar entre diferentes tipos de vínculos de red proporcionados en la configuración de red.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-533">This helps differentiate between various types of network links that are provisioned in the network configuration.</span></span>
  
![Herramientas](../media/Reskit_2012_Tools_Documentation_Image29.jpg)
  
 <span data-ttu-id="3cbaa-535">**Información de sitio de topología de red de vista CAC, información región y políticas de provisioning de ancho de banda:** Skype para los administradores de servidor de negocios 2015 puede ver información relacionada de área de red CAC, información del sitio y ancho de banda CAC provisioning información mediante las opciones que se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-535">**View CAC network topology site information, region information, and provisioned bandwidth policies:** Skype for Business Server 2015 administrators can view related CAC network region information, site information, and CAC bandwidth provisioning information by using options shown below.</span></span> <span data-ttu-id="3cbaa-536">(Por ejemplo, haga clic en **información** en un objeto de sitio de red o región de la red.)</span><span class="sxs-lookup"><span data-stu-id="3cbaa-536">(For example, click **Info** in a network region or network site object.)</span></span>
  
![Definir los conectores personalizados para su red.](../media/Reskit_2012_Tools_Documentation_Image30.jpg)
  
### <a name="summary"></a><span data-ttu-id="3cbaa-538">Resumen</span><span class="sxs-lookup"><span data-stu-id="3cbaa-538">Summary</span></span>

<span data-ttu-id="3cbaa-539">Esta herramienta puede ser un valioso recurso para Skype para los administradores de servidor de negocios 2015 que les gustaría ver la topología de la red CAC para su implementación en un formato gráfico.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-539">This tool can be a valuable resource to Skype for Business Server 2015 administrators who would like to view CAC network topology for their deployment in a graphical format.</span></span>
  
## <a name="response-group-agent-live"></a><span data-ttu-id="3cbaa-540">Response Group Agent Live (Información en vivo del agente del grupo de respuesta)</span><span class="sxs-lookup"><span data-stu-id="3cbaa-540">Response Group Agent Live</span></span>
<span data-ttu-id="3cbaa-541"><a name="RGAL"> </a></span><span class="sxs-lookup"><span data-stu-id="3cbaa-541"></span></span>

<span data-ttu-id="3cbaa-542">La aplicación de grupo de respuesta permite a los agentes acceder en tiempo real a información útil mediante el servicio web integrado.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-542">The Response Group application gives agents the ability to access useful real-time information using its built-in Web service.</span></span> <span data-ttu-id="3cbaa-543">Desafortunadamente, no hay disponible una vista gráfica de estos datos fuera de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-543">Unfortunately, no graphical view of this data is available outside the application.</span></span> <span data-ttu-id="3cbaa-544">La herramienta del Kit de recursos Live de respuesta grupo agente resuelve este problema al proporcionar una forma sencilla y gráfica para obtener acceso a esta información, mejorada con Skype en tiempo real para Business communications software obtener información como la presencia de otros agentes.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-544">The Response Group Agent Live Resource Kit tool solves this issue by providing a simple and graphical way to access this information, enhanced with real-time Skype for Business communications software information such as the presence of other agents.</span></span>
  
### <a name="description"></a><span data-ttu-id="3cbaa-545">Descripción</span><span class="sxs-lookup"><span data-stu-id="3cbaa-545">Description</span></span>

<span data-ttu-id="3cbaa-546">Response Group Agent Live es una aplicación para Windows que proporciona funciones de inicio y cierre de sesión, así como determinada información en tiempo real (como pertenencia a grupo y número actual de llamadas) a los agentes del grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-546">Response Group Agent Live is a Windows application that provides sign-in and sign-out functionality and some real-time information (such as group membership and current number of calls) to Response Group agents.</span></span> <span data-ttu-id="3cbaa-547">Está diseñada para ser una versión mejorada de la página de grupos de agentes (accesible desde Skype para el negocio.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-547">It is meant to be an enhanced version of the Agent Groups page (accessible from Skype for Business.</span></span>
  
### <a name="purpose"></a><span data-ttu-id="3cbaa-548">Finalidad</span><span class="sxs-lookup"><span data-stu-id="3cbaa-548">Purpose</span></span>

<span data-ttu-id="3cbaa-p161">La aplicación de grupo de respuesta envía las llamadas entrantes a una cola y, a continuación, las redirige a grupos de agentes. Para poder tomar decisiones fundamentadas sobre las llamadas que deben atenderse, los agentes pueden acceder a información en tiempo real sobre sus grupos de agentes, como los agentes disponibles y el número de llamadas que espera en cada cola. Esta información, inicialmente accesible solo mediante el servicio de grupo de respuesta, es facilitada de forma intuitiva por la herramienta Response Group Agent Live.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-p161">The Response Group application queues incoming calls, and then routes them to agent groups. To make informed decisions about which calls to service, agents can access real-time information about their agent groups, such as what other agents are available and how many calls are waiting in each queue. This information, initially accessible only through the Response Group service, is made available in an intuitive way by Response Group Agent Live.</span></span>
  
#### <a name="features"></a><span data-ttu-id="3cbaa-552">Características</span><span class="sxs-lookup"><span data-stu-id="3cbaa-552">Features</span></span>

<span data-ttu-id="3cbaa-553">La herramienta Agente de grupo de respuesta Live se basa en el servicio de grupo de respuesta y el Skype para Business Server SDK de 2015.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-553">The Response Group Agent Live tool is built on the Response Group service and the Skype for Business Server 2015 SDK.</span></span> <span data-ttu-id="3cbaa-554">Proporciona a los agentes de grupo de respuesta la información y las funciones disponibles del servicio de grupo de respuesta (como pertenencia a grupo, presencia de otros agentes y número de llamadas en espera).</span><span class="sxs-lookup"><span data-stu-id="3cbaa-554">It provides Response Group agents the information and capabilities that are available from the Response Group service (such as group membership, presence of other agents, and number of waiting calls).</span></span>
  
<span data-ttu-id="3cbaa-555">En la ilustración siguiente se muestra la interfaz principal de la herramienta Response Group Agent Live.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-555">The figure below illustrates the main interface of Response Group Agent Live.</span></span>
  
![La herramienta Response Group Agent Live.](../media/Reskit_2012_Tools_Documentation_Image37.JPG)
  
<span data-ttu-id="3cbaa-557">Las tres características principales que aparecen a continuación están disponibles para los agentes en Response Group Agent Live:</span><span class="sxs-lookup"><span data-stu-id="3cbaa-557">The following three main features are available for agents in Response Group Agent Live:</span></span>
  
- <span data-ttu-id="3cbaa-558">**Sign-in/out:** Contrariamente a la página de grupos de agentes (accesible desde Skype para Business Server 2015), respuesta grupo agente Live permite agentes exclusivos para iniciar sesión en o fuera del agente de todos los grupos a la vez.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-558">**Sign-in/out:** Contrary to the Agent Groups page (accessible from Skype for Business Server 2015), Response Group Agent Live allows only agents to sign-in or out of all agent groups at once.</span></span> <span data-ttu-id="3cbaa-559">Esta aplicación ofrece tres maneras rápidas de agentes firmar o alejar:</span><span class="sxs-lookup"><span data-stu-id="3cbaa-559">This application provides three quick ways for agents to sign in or out:</span></span>
    
  - <span data-ttu-id="3cbaa-560">Hacer clic en los botones de inicio y cierre de sesión (verde y rojo) en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-560">Click the Sign-in/out (green and red) buttons within the application.</span></span>
    
  - <span data-ttu-id="3cbaa-561">Hacer clic en el icono de la bandeja del sistema y seleccionar iniciar sesión o cerrar sesión.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-561">Right-click the system tray icon, and select sign in or sign out.</span></span>
    
  - <span data-ttu-id="3cbaa-562">Usar los métodos abreviados de teclado configurables.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-562">Using configurable keyboard shortcuts.</span></span>
    
- <span data-ttu-id="3cbaa-563">**Pertenencia al grupo:** Cuando se selecciona un grupo de agentes, agente de grupo de respuesta Live muestra la lista de agentes de este grupo en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-563">**Group membership:** When an agent group is selected, Response Group Agent Live displays the list of agents in this group in the right pane.</span></span> <span data-ttu-id="3cbaa-564">Si Skype para Business Server 2015 se ejecuta en el mismo equipo que esta aplicación, información de presencia y la tarjeta de contacto se muestran en el agente de respuesta grupo Live.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-564">If Skype for Business Server 2015 is running on the same computer as this application, presence information and the contact card are displayed in the Response Group Agent Live.</span></span> <span data-ttu-id="3cbaa-565">Agentes pueden enviar un mensaje instantáneo o llamar a otros agentes directamente desde allí.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-565">Agents can send an IM or call other agents directly from there.</span></span>
    
- <span data-ttu-id="3cbaa-p165">**Estadísticas en tiempo real:** Response Group Agent Live proporciona estadísticas en tiempo real para todos los grupos de agentes. La frecuencia de actualización es de un minuto. Cuando un grupo de respuesta responde a una llamada, se añade un indicador visual junto al nombre del grupo con el número actual de llamadas en cola. Al detener el puntero sobre un grupo, también se muestra el tiempo de espera más largo.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-p165">**Real-time statistics:** Response Group Agent Live provides real-time statistics for all agent groups. The update frequency is one minute. When a call is answered by a Response Group, a visual indicator is added next to the group name with the current number of queued calls. Pausing the pointer over a group also displays the longest waiting time.</span></span>
    
### <a name="requirements"></a><span data-ttu-id="3cbaa-570">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3cbaa-570">Requirements</span></span>

<span data-ttu-id="3cbaa-571">Response Group Agent Live requiere .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-571">Response Group Agent Live requires the .NET Framework 4.0.</span></span> <span data-ttu-id="3cbaa-572">Además, para aprovechar las funciones de presencia y contacto, Skype para el negocio debe estar instalado localmente (y ejecutar).</span><span class="sxs-lookup"><span data-stu-id="3cbaa-572">In addition, to take advantage of the presence and contact card features, Skype for Business must be installed locally (and be running).</span></span>
  
#### <a name="configuration"></a><span data-ttu-id="3cbaa-573">Configuración</span><span class="sxs-lookup"><span data-stu-id="3cbaa-573">Configuration</span></span>

<span data-ttu-id="3cbaa-p167">Response Group Agent Live puede personalizarse según preferencias individuales mediante el cuadro de diálogo de opciones de la aplicación. Además, el administrador puede definir la dirección de host predeterminada al editar directamente la propiedad defaultHostAddress del archivo RGAgentLive.exe.config.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-p167">Response Group Agent Live can be customized to individual preferences by using the Options dialog box in the application. In addition, the administrator can define the default host address by editing directly the defaultHostAddress property of the RGAgentLive.exe.config file.</span></span>
  
<span data-ttu-id="3cbaa-p168">En la ilustración siguiente se muestra el cuadro de diálogo de opciones que los agentes pueden usar para configurar la dirección de host y las teclas de método abreviado. Para acceder a este cuadro de diálogo, haga clic en el botón Opciones de la parte superior derecha de la interfaz principal.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-p168">The figure below illustrates the Options dialog box that agents can use to configure the host address and shortcut keys. This dialog is accessed by clicking the Options button on the top right of the main interface.</span></span>
  
![El cuadro de diálogo de las opciones de Response Group Agent Live.](../media/Reskit_2012_Tools_Documentation_Image38.JPG)
  
<span data-ttu-id="3cbaa-579">Las tres opciones siguientes pueden personalizarse en la configuración de Response Group Agent Live:</span><span class="sxs-lookup"><span data-stu-id="3cbaa-579">The following three different settings can be customized in the Response Group Agent Live configuration:</span></span>
  
- <span data-ttu-id="3cbaa-580">Dirección de host: suele ser el web pool FQDN que pertenecen al grupo doméstico del agente.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-580">Host address: This is typically the web pool FQDN belonging to the agent's home pool.</span></span> <span data-ttu-id="3cbaa-581">La dirección exacta del servicio de grupo de respuesta se obtiene automáticamente en segundo plano a partir de esta información (al añadir la ruta de acceso correcta después del host).</span><span class="sxs-lookup"><span data-stu-id="3cbaa-581">The exact Response Group service address is automatically derived in the background from this information (by appending the right path after the host).</span></span>
    
- <span data-ttu-id="3cbaa-582">Métodos abreviados de teclado: los métodos abreviados de teclado exactos para iniciar/cerrar sesión se pueden personalizar.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-582">Shortcuts: The exact shortcuts to sign-in/out can be customized.</span></span> <span data-ttu-id="3cbaa-583">La única limitación es que ambos métodos abreviados deben contener la clave "Windows Logo" (además de al menos otra tecla).</span><span class="sxs-lookup"><span data-stu-id="3cbaa-583">The only limitation is that both shortcuts must contain the "Windows Logo" key (in addition to at least another key).</span></span>
    
- <span data-ttu-id="3cbaa-584">Iniciar con Windows: la aplicación puede configurarse para iniciarse automáticamente con Windows.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-584">Start with Windows: The application can be configured to start automatically with Windows.</span></span>
    
### <a name="examples"></a><span data-ttu-id="3cbaa-585">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="3cbaa-585">Examples</span></span>

<span data-ttu-id="3cbaa-586">En la ilustración siguiente se muestra cómo llamar o enviar un mensaje instantáneo a otro agente; para ello es necesario hacer clic con el botón derecho en el contacto del panel derecho.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-586">The figure below illustrates how to call or send an IM to another agent by right-clicking the contact in the right pane.</span></span>
  
![Hacer una llamada o enviar un mensaje instantáneo.](../media/Reskit_2012_Tools_Documentation_Image39.JPG)
  
<span data-ttu-id="3cbaa-588">En la ilustración siguiente aparece cómo Response Group Agent Live muestra el número de llamadas en la cola y el tiempo de espera más largo de todas las llamadas entrantes.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-588">The figure below illustrates how Response Group Agent Live displays the current number of calls in the queue and the longest waiting time among all these incoming calls.</span></span>
  
![Ver información de cola.](../media/Reskit_2012_Tools_Documentation_Image40.JPG)
  
### <a name="summary"></a><span data-ttu-id="3cbaa-590">Resumen</span><span class="sxs-lookup"><span data-stu-id="3cbaa-590">Summary</span></span>

<span data-ttu-id="3cbaa-591">Inicio y cierre de sesión rápidos, pertenencia a grupos y estadísticas básicas en tiempo real son algunas de las características interesantes del agente del grupo de respuesta que solo están disponibles fuera de la aplicación del servicio de grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-591">Fast sign-in and sign-out, group membership, and basic real-time statistics are interesting Response Group agent features that are only available outside the application from the Response Group service.</span></span> <span data-ttu-id="3cbaa-592">Con la herramienta del Kit de recursos Live de respuesta grupo agente, Skype para los administradores de servidor de negocios 2015 puede proporcionar a sus agentes con una aplicación de Windows que les permita realizar tareas de manera más rápida y gráfica.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-592">With the Response Group Agent Live Resource Kit tool, Skype for Business Server 2015 administrators can provide their agents with a Windows application that allows them to perform tasks in a faster and graphical way.</span></span>
  
## <a name="sefautil"></a><span data-ttu-id="3cbaa-593">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="3cbaa-593">SEFAUtil</span></span>
<span data-ttu-id="3cbaa-594"><a name="SEFAUtil"> </a></span><span class="sxs-lookup"><span data-stu-id="3cbaa-594"></span></span>

<span data-ttu-id="3cbaa-595">SEFAUtil (activación de la característica de extensión secundaria) es una herramienta de línea de comandos que permite Skype para administradores de software de comunicaciones de Business Server 2015 y agentes de asistencia técnica para configurar timbre timbre delegado, reenvío de llamadas, simultáneo, configuración de llamada de equipo y grupo de atención de llamadas en nombre de un Skype para usuario Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-595">SEFAUtil (secondary extension feature activation) is a command-line tool that enables Skype for Business Server 2015 communications software administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="3cbaa-596">La herramienta también permite a los administradores consultar la configuración de enrutamiento de llamadas que se publica para un usuario determinado. La herramienta SEFAUtil permite al administrador habilitar o deshabilitar o modificar llamada de reenvío o timbre simultáneamente en nombre del usuario.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-596">The tool also allows administrators to query the call-routing settings that are published for a particular user.The SEFAUtil tool allows the administrator to enable/disable/modify call forwarding or simultaneously ringing on behalf of the user.</span></span> <span data-ttu-id="3cbaa-597">El administrador puede especificar el destino (en forma de un URI de SIP) o utilizar un destino que ya ha sido publicado por el usuario.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-597">The administrator can specify the target (in the form of a SIP URI) or use a target that has already been published by the user.</span></span> <span data-ttu-id="3cbaa-598">Esta herramienta permite a los administradores agregar o quitar a delegados o miembros del grupo de llamada de equipo en nombre del usuario. Esta herramienta se basa en la API de administrados para comunicaciones de unificado de Microsoft (UCMA) 3.0 y requiere que los administradores creen una aplicación de confianza en el almacén de Administración Central para SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-598">This tool also allows administrators to add or remove delegates or team-call group members on behalf of the user.This tool is built on Microsoft Unified Communications Managed API (UCMA) 3.0 and requires that administrators create a trusted application in the Central Management store for SEFAUtil.</span></span>
  
<span data-ttu-id="3cbaa-599">SEFAUtil (activación de la característica de extensión secundaria) permite Skype para los administradores de Business Server 2015 y agentes de asistencia técnica configurar timbre timbre delegado, reenvío de llamadas, simultáneas, llamada de equipo Configuración y grupo llamada recogida en nombre de un Skype para usuario Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-599">SEFAUtil (secondary extension feature activation) enables Skype for Business Server 2015 administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="3cbaa-600">Esta herramienta también permite a los administradores consultar la configuración de enrutamiento de llamadas que se haya publicado para un usuario concreto.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-600">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span>
  
### <a name="description"></a><span data-ttu-id="3cbaa-601">Descripción</span><span class="sxs-lookup"><span data-stu-id="3cbaa-601">Description</span></span>

<span data-ttu-id="3cbaa-602">La versión actual de SEFAUtil es tan solo una herramienta de línea de comandos; no dispone de una interfaz gráfica de usuario.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-602">The current version of SEFAUtil is only a command-line tool; there is no supporting graphical user interface.</span></span> <span data-ttu-id="3cbaa-603">Esta herramienta se basa en la API de administrados para comunicaciones de unificado de Microsoft (UCMA) 3.0.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-603">This tool is based on Microsoft Unified Communications Managed API (UCMA) 3.0.</span></span> <span data-ttu-id="3cbaa-604">Las características de esta herramienta permiten a los administradores y agentes del departamento de soporte técnico realizar las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="3cbaa-604">The features in this tool allow administrators and helpdesk agents to do the following:</span></span>
  
- <span data-ttu-id="3cbaa-605">Ver todas las opciones de configuración de enrutamiento de llamadas para un usuario (incluidos el desvío de llamadas, la delegación, llamadas simultáneas, llamadas de equipo y respuestas de llamada de grupo)</span><span class="sxs-lookup"><span data-stu-id="3cbaa-605">View all call routing settings for a user (includes call-forwarding, delegation, simultaneous ringing, team-call and group call pickup)</span></span>
    
- <span data-ttu-id="3cbaa-606">Habilitar/deshabilitar/modificar la configuración del desvío de llamadas (incluidos el destino y el temporizador de llamadas sin respuesta)</span><span class="sxs-lookup"><span data-stu-id="3cbaa-606">Enable/disable/modify call-forwarding setting (includes destination and no-answer timer)</span></span>
    
- <span data-ttu-id="3cbaa-607">Habilitar/deshabilitar/modificar las configuraciones inmediatas de desvío de llamadas</span><span class="sxs-lookup"><span data-stu-id="3cbaa-607">Enable/disable/modify call-forwarding immediate configurations</span></span>
    
- <span data-ttu-id="3cbaa-608">Habilitar/deshabilitar/modificar la configuración de delegación</span><span class="sxs-lookup"><span data-stu-id="3cbaa-608">Enable/disable/modify delegation settings</span></span>
    
- <span data-ttu-id="3cbaa-609">Habilitar/deshabilitar/modificar la configuración de grupo de llamada de equipo</span><span class="sxs-lookup"><span data-stu-id="3cbaa-609">Enable/disable/modify team-call group settings</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3cbaa-610">Nuevo en Skype para la herramienta Business Server 2015 SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="3cbaa-610">New in Skype for Business Server 2015 SEFAUtil tool</span></span> 
  
- <span data-ttu-id="3cbaa-611">Habilitar/deshabilitar/modificar la configuración de llamadas simultáneas (incluido el destino)</span><span class="sxs-lookup"><span data-stu-id="3cbaa-611">Enable/disable/modify simultaneous ringing settings (includes destination)</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3cbaa-612">Nuevo en Skype para la herramienta Business Server 2015 SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="3cbaa-612">New in Skype for Business Server 2015 SEFAUtil tool</span></span> 
  
- <span data-ttu-id="3cbaa-613">Habilitar/deshabilitar/modificar la configuración de respuesta a llamada grupal</span><span class="sxs-lookup"><span data-stu-id="3cbaa-613">Enable/disable/modify group call pickup settings</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="3cbaa-614">Nuevo en Skype para la herramienta Business Server 2015 SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="3cbaa-614">New in Skype for Business Server 2015 SEFAUtil tool</span></span> 
  
<span data-ttu-id="3cbaa-615">Esta herramienta tiene las limitaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="3cbaa-615">This tool has the following limitations:</span></span>
  
- <span data-ttu-id="3cbaa-616">Admite sólo para usuarios alojados en un Skype para el grupo de servidores empresariales</span><span class="sxs-lookup"><span data-stu-id="3cbaa-616">Supported only for users homed in a Skype for Business Server pool</span></span>
    
- <span data-ttu-id="3cbaa-617">No admite la edición en masa de las opciones de configuración de enrutamiento de llamadas para varios usuarios</span><span class="sxs-lookup"><span data-stu-id="3cbaa-617">Bulk-edit of call routing settings for several users is not supported</span></span>
    
### <a name="output"></a><span data-ttu-id="3cbaa-618">Salida</span><span class="sxs-lookup"><span data-stu-id="3cbaa-618">Output</span></span>

<span data-ttu-id="3cbaa-p175">La versión actual de esta herramienta solo ofrece resultados en la ventana del símbolo del sistema. Para obtener más información, consulte la sección Ejemplos más adelante en este documento.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-p175">The current version of this tool provides output only in the Command Prompt window. For details, see the Examples section later in this document.</span></span>
  
### <a name="purpose"></a><span data-ttu-id="3cbaa-621">Finalidad</span><span class="sxs-lookup"><span data-stu-id="3cbaa-621">Purpose</span></span>

<span data-ttu-id="3cbaa-622">A continuación se describen algunos de los escenarios donde puede utilizarse esta herramienta:</span><span class="sxs-lookup"><span data-stu-id="3cbaa-622">Following are some of the key scenarios where this tool may be used:</span></span>
  
- <span data-ttu-id="3cbaa-623">Bob es un ejecutivo y se ha movido a Skype para telefonía Business Server.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-623">Bob is an executive and has been moved to Skype for Business Server telephony.</span></span> <span data-ttu-id="3cbaa-624">Ha configurado la delegación en su sistema PBX existente.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-624">He has delegation on his existing PBX system.</span></span> <span data-ttu-id="3cbaa-625">Como parte del cambio a Skype para Business Server 2015, el administrador es capaz de configurar el enrutamiento de Bob para reflejar su configuración preexistente de delegación.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-625">As part of the move to Skype for Business Server 2015, the administrator is able to configure Bob's routing to reflect his pre-existing delegation configuration.</span></span>
    
- <span data-ttu-id="3cbaa-p177">Alicia está de viaje y se da cuenta de que está esperando una llamada importante de uno de sus clientes. Sin embargo, está en un hotel y no tiene acceso a un PC. Entonces, llama al departamento de soporte técnico y solicita que se desvíen a su número de teléfono móvil todas las llamadas realizadas a su número de trabajo. El personal de soporte técnico puede realizar la configuración en su nombre.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-p177">Alice is travelling and realizes that she is expecting an important call from one of her customers. However, she is in a hotel and has no access to a computer. She calls the helpdesk and requests that they forward to her mobile number all the calls made to her work number. The helpdesk personnel are able to do the configuration on her behalf.</span></span>
    
- <span data-ttu-id="3cbaa-630">Las llamadas a su número de trabajo de Juan va a su correo de voz móvil siempre que él está en el trabajo; Sin embargo, las cosas parecen funcionar correctamente en la mayoría de las otra ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-630">Joe's calls to his work number are going to his mobile voicemail whenever he is at work; however, things appear to be working correctly in most other locations.</span></span> <span data-ttu-id="3cbaa-631">El técnico de asistencia puede ver la configuración de enrutamiento de Joe y descubre que Juan tiene llamadas simultáneas configurado a su teléfono móvil.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-631">The helpdesk technician is able to view Joe's routing configuration and discovers that Joe has simultaneous ringing configured to his mobile phone.</span></span> <span data-ttu-id="3cbaa-632">El técnico pide a Joe sobre la cobertura móvil en su oficina y es capaz de determinar que la regla llamada simultánea es la causa de las llamadas ir al correo de voz de Joe móvil cuando su cobertura de la red es deficiente.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-632">The technician asks Joe about the mobile coverage at his office and is able to determine that the simultaneous ringing rule is what is causing the calls to go to Joe's mobile voicemail when his network coverage is poor.</span></span>
    
- <span data-ttu-id="3cbaa-633">Mike es un nuevo empleado de Contoso y él une un nuevo equipo en el que todos los miembros están configurados para la llamada de equipo, cuando se habilita por Skype para Business Server 2015, el administrador puede establecer su llamada de equipo Configuración de grupo para incluir todos los nuevos miembros de su equipo , además, el administrador agrega Mike como un miembro del grupo de llamada de equipo para cada uno de los miembros de su equipo.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-633">Mike is a new employee at Contoso and he's joining a new team on which all members are configured for team-call, when being enabled for Skype for Business Server 2015, the administrator is able to set his team-call group settings to include all his new team members, additionally, the administrator adds Mike as a team-call group member for each of the members in his team.</span></span>
    
- <span data-ttu-id="3cbaa-634">Uno de los procedimientos de atención al cliente en el departamento de recursos humanos de Contoso es proporcionar personal de servicio para todos los autores de llamadas desde la primera llamada.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-634">A customer service practice in the human resources department at Contoso is to provide personal service for all callers since the first call.</span></span> <span data-ttu-id="3cbaa-635">Debido a que todos los miembros del departamento se sientan muy cerca unos de otros, tener todos los teléfonos sonando de forma simultánea con llamadas de equipo es muy molesto para el equipo.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-635">Given that all members of the department sit very close to each other, having all phones ringing at the same time with team-call is very disruptive for the team.</span></span> <span data-ttu-id="3cbaa-636">Para proporcionar el mejor servicio sin interrumpir a los miembros del equipo, el Skype para el Administrador de servidor de negocios 2015 aprovecha la capacidad de recogida de llamar al grupo.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-636">To provide the best service without disrupting the team members, the Skype for Business Server 2015 administrator takes advantage of the Group Call Pickup capability.</span></span> <span data-ttu-id="3cbaa-637">El administrador agrega a todos los miembros del departamento al número de respuesta.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-637">The administrator adds all department members to a pickup group and communicates to the department the pickup group number.</span></span> <span data-ttu-id="3cbaa-638">Cuando Sandra no está en su escritorio, Jorge se da cuenta de que suena el teléfono de Sandra y responde a la llamada desde su escritorio.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-638">When Samantha is absent from her desk, Joe notices her phone ringing and he proceeds to answer the call from his desk.</span></span>
    
### <a name="requirements"></a><span data-ttu-id="3cbaa-639">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3cbaa-639">Requirements</span></span>

<span data-ttu-id="3cbaa-p180">La herramienta SEFAUtil solo puede ejecutarse desde un equipo que forme parte de un grupo de aplicaciones de confianza. UCMA 3.0 debe instalarse en dicho equipo. Para ejecutar la herramienta es necesario crear un id. de aplicación de SEFAUtil en el grupo.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-p180">The SEFAUtil tool can be run only on a computer that is a part of a Trusted Application Pool. UCMA 3.0 must be installed on that computer. To run the tool, a new Trusted Application with the SEFAUtil application ID must be created on that pool.</span></span>
  
### <a name="creating-a-new-trusted-application-for-the-sefautil-tool"></a><span data-ttu-id="3cbaa-643">Crear una nueva aplicación de confianza para la herramienta SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="3cbaa-643">Creating a new Trusted Application for the SEFAUtil tool</span></span>

1. <span data-ttu-id="3cbaa-644">La herramienta SEFAUTil solo puede ejecutarse en un equipo que pertenezca a un grupo de aplicaciones de confianza.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-644">The SEFAUTil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="3cbaa-645">Si es necesario, agregar un grupo como un nuevo grupo de aplicaciones de confianza puede realizarse a través del Skype para el Shell de administración de servidor de negocios con el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3cbaa-645">If needed, adding a pool as a new trusted application pool can be done via the Skype for Business Server Management Shell with the following cmdlet:</span></span>
    
  ```
  New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
  ```

    > [!NOTE]
    > <span data-ttu-id="3cbaa-646">UCMA 3.0 debe estar instalado en todos los equipos que se utilicen para ejecutar la herramienta SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-646">UCMA 3.0 must be installed on any computer that will be used to run the SEFAUtil tool.</span></span> 
  
2. <span data-ttu-id="3cbaa-647">Es necesario definir una aplicación de confianza en la topología para la herramienta SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-647">A trusted application needs to be defined in the topology for the SEFAUtil tool.</span></span> <span data-ttu-id="3cbaa-648">Para definir SEFAUtil como una nueva aplicación de confianza, utilice el Skype para negocios de Shell de administración de servidor y ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3cbaa-648">To define SEFAUtil as a new trusted application, use the Skype for Business Server Management Shell and execute the following cmdlet:</span></span> 
    
  ```
  New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
  ```

    > [!NOTE]
    > <span data-ttu-id="3cbaa-649">Si fuera necesario, puede utilizarse un puerto distinto.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-649">A different port can be used if needed.</span></span> 
  
3. <span data-ttu-id="3cbaa-650">Es necesario habilitar los cambios de topología.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-650">The topology changes need to be enabled.</span></span> <span data-ttu-id="3cbaa-651">Habilitar los cambios de topología puede realizarse mediante el Skype para el Shell de administración de servidor empresarial ejecutando el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3cbaa-651">Enabling the topology changes can be done via the Skype for Business Server Management Shell by executing the following cmdlet:</span></span> 
    
  ```
  Enable-CsToplogy
  ```

4. <span data-ttu-id="3cbaa-652">Si es necesario, instale el Skype para Business Server 2015 Resource Kit Tools en el servidor que se utilizará para ejecutar la herramienta SEFAUtil (el servidor debe ser parte de un grupo de aplicaciones de confianza).</span><span class="sxs-lookup"><span data-stu-id="3cbaa-652">If needed, install the Skype for Business Server 2015 Resource Kit Tools in the server that will be used to run the SEFAUtil tool (the server must be part of a trusted application pool).</span></span>
    
5. <span data-ttu-id="3cbaa-653">Compruebe si SEFAUtil se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-653">Verify the SEFAUtil is running correctly.</span></span> <span data-ttu-id="3cbaa-654">Para ello, ejecute la herramienta desde un símbolo del sistema de Windows con privilegios de administrador para mostrar la configuración de desvío de llamadas de un usuario en la implementación.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-654">To do this, run the tool from a windows command prompt with administrator privileges to display the call forwarding settings of a user in the deployment.</span></span> <span data-ttu-id="3cbaa-655">De forma predeterminada, la herramienta se ubicará en: "...\Program Files\Skype de 2015\Reskit Business Server".</span><span class="sxs-lookup"><span data-stu-id="3cbaa-655">By default the tool will be located in: "…\Program Files\Skype for Business Server 2015\Reskit".</span></span> <span data-ttu-id="3cbaa-656">Para mostrar la configuración de desvío de llamadas de un usuario, utilice el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="3cbaa-656">To display the call forwarding settings of a user, use the following command:</span></span> 
    
  ```
  SEFAUtil.exe <user SIP address> /server:<Skype for Business Server/Pool FQDN>
  ```

    <span data-ttu-id="3cbaa-657">Se mostrará la configuración de desvío de llamadas del usuario.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-657">The call forwarding settings of the user should be displayed.</span></span>
    
#### <a name="group-call-pickup"></a><span data-ttu-id="3cbaa-658">Respuesta de llamadas grupales</span><span class="sxs-lookup"><span data-stu-id="3cbaa-658">Group Call Pickup</span></span>

<span data-ttu-id="3cbaa-659">Recogida de grupo llamar requiere una configuración adicional en Skype para Business Server 2015 para la capacidad de ser totalmente habilitada.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-659">Group Call Pickup requires additional configuration in Skype for Business Server 2015 for the capability to be fully enabled.</span></span> <span data-ttu-id="3cbaa-660">Antes de asignar grupos de respuesta a los usuarios, consulte los pasos de planificación e implementación de esta función en la documentación del producto de respuesta de llamadas grupales.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-660">Before assigning pickup groups to users, refer to the Group Call Pickup product documentation for the planning and deployment steps of this capability.</span></span>
  
### <a name="examples"></a><span data-ttu-id="3cbaa-661">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="3cbaa-661">Examples</span></span>

#### <a name="display-current-call-handling-settings"></a><span data-ttu-id="3cbaa-662">Mostrar la configuración administración de llamadas actual</span><span class="sxs-lookup"><span data-stu-id="3cbaa-662">Display Current Call Handling Settings</span></span>

<span data-ttu-id="3cbaa-663">El comando siguiente muestra la administración de llamadas para el usuario.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-663">The following command displays the call handling for the user.</span></span>  `SEFAUtil.exe /server:SfBS2015server.contoso.com katarina@contoso.com`
  
> [!NOTE]
> <span data-ttu-id="3cbaa-664">En este ejemplo se utiliza el modificador **/server** para especificar el Skype para Business Server para conectarse a.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-664">This example uses the **/server** switch to specify the Skype for Business Server to connect to.</span></span>
  
 <span data-ttu-id="3cbaa-665">**Salida**</span><span class="sxs-lookup"><span data-stu-id="3cbaa-665">**Output**</span></span>
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:20
Call Forward No Answer to: voicemail
```

#### <a name="set-the-call-forwardno-answer-destination"></a><span data-ttu-id="3cbaa-666">Establecer el desvío de llamadas/destino sin respuesta</span><span class="sxs-lookup"><span data-stu-id="3cbaa-666">Set the Call Forward/No Answer Destination</span></span>

<span data-ttu-id="3cbaa-667">En este ejemplo se establece el desvío de llamadas/destino sin respuesta y la demora de timbre.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-667">This example sets the call forward/no answer destination and the ring delay.</span></span> <span data-ttu-id="3cbaa-668">En este caso, no se proporciona el modificador /server; SEFAUtil intenta autodiscover el Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-668">Here, the /server switch is not provided; SEFAUtil attempts to autodiscover the Skype for Business Server 2015.</span></span>
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone
```

 <span data-ttu-id="3cbaa-669">**Salida**</span><span class="sxs-lookup"><span data-stu-id="3cbaa-669">**Output**</span></span>
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="enable-call-forwarding-immediately"></a><span data-ttu-id="3cbaa-670">Habilitar desvío de llamadas inmediatamente</span><span class="sxs-lookup"><span data-stu-id="3cbaa-670">Enable Call Forwarding Immediately</span></span>

<span data-ttu-id="3cbaa-671">En este ejemplo se habilita el desvío de llamadas inmediatamente a otro usuario.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-671">This example immediately enables call-forwarding to another user.</span></span>
  
```
SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com
```

 <span data-ttu-id="3cbaa-672">**Salida**</span><span class="sxs-lookup"><span data-stu-id="3cbaa-672">**Output**</span></span>
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Forward immediate to: sip:anders@contoso.com
```

#### <a name="disable-call-forwarding-immediately"></a><span data-ttu-id="3cbaa-673">Deshabilitar desvío de llamadas inmediatamente</span><span class="sxs-lookup"><span data-stu-id="3cbaa-673">Disable Call Forwarding Immediately</span></span>

<span data-ttu-id="3cbaa-674">En este ejemplo se deshabilita automáticamente el desvío de llamadas.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-674">This example immediately disables call forwarding.</span></span>
  
```
SEFAUtil.exe /server:SfBserver.contoso.com katarina@contoso.com  /disablefwdimmediate
```

 <span data-ttu-id="3cbaa-675">**Salida**</span><span class="sxs-lookup"><span data-stu-id="3cbaa-675">**Output**</span></span>
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a><span data-ttu-id="3cbaa-676">Agregar un usuario como delegado y configurar las llamadas simultáneas de delegados</span><span class="sxs-lookup"><span data-stu-id="3cbaa-676">Add a User as a Delegate and Set Up Simultaneous Ringing of Delegates</span></span>

<span data-ttu-id="3cbaa-677">En este ejemplo se agrega un usuario como delegado y se configuran las llamadas simultáneas de delegados.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-677">This example adds a user as a delegate and sets up simultaneous ringing of delegates.</span></span>
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates
```

 <span data-ttu-id="3cbaa-678">**Salida**</span><span class="sxs-lookup"><span data-stu-id="3cbaa-678">**Output**</span></span>
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simultaneously Ringing Delegates: sip:joe@contoso.com
```

#### <a name="change-simultaneous-ringing-rule-of-delegates"></a><span data-ttu-id="3cbaa-679">Cambiar la regla de llamadas simultáneas de delegados</span><span class="sxs-lookup"><span data-stu-id="3cbaa-679">Change Simultaneous Ringing Rule of Delegates</span></span>

<span data-ttu-id="3cbaa-680">En este ejemplo se cambia la regla de llamadas simultáneas configurada en el ejemplo anterior a la regla de demora de timbre.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-680">This example changes the simultaneous ringing rule that was set in the previous example to the delayed ringing rule.</span></span>
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10
```

 <span data-ttu-id="3cbaa-681">**Salida**</span><span class="sxs-lookup"><span data-stu-id="3cbaa-681">**Output**</span></span>
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com
```

#### <a name="remove-the-delegate"></a><span data-ttu-id="3cbaa-682">Quitar al delegado</span><span class="sxs-lookup"><span data-stu-id="3cbaa-682">Remove the Delegate</span></span>

<span data-ttu-id="3cbaa-683">En este ejemplo se quita el delegado.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-683">This example removes the delegate.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3cbaa-684">Al quitar el último delegado, se deshabilita automáticamente la llamada a delegados.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-684">When the last delegate is removed, delegate ringing is automatically disabled.</span></span> 
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com
```

 <span data-ttu-id="3cbaa-685">**Salida**</span><span class="sxs-lookup"><span data-stu-id="3cbaa-685">**Output**</span></span>
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a><span data-ttu-id="3cbaa-686">Agregar un delegado y configurar la regla de desvío de llamadas a delegados</span><span class="sxs-lookup"><span data-stu-id="3cbaa-686">Add a Delegate and Set Up the Call-Forward to Delegates Rule</span></span>

<span data-ttu-id="3cbaa-687">En este ejemplo se agrega un delegado y se configura la regla de desvío de llamadas a delegados.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-687">This example adds a delegate and sets up the call-forward to delegates rule.</span></span>
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates
```

 <span data-ttu-id="3cbaa-688">**Salida**</span><span class="sxs-lookup"><span data-stu-id="3cbaa-688">**Output**</span></span>
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Forwarding calls to Delegates: sip:anders@contoso.com
```

#### <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a><span data-ttu-id="3cbaa-689">Habilitar las llamadas simultáneas y establecer un número de destino</span><span class="sxs-lookup"><span data-stu-id="3cbaa-689">Enable Simultaneous Ringing and Set a Destination Number</span></span>

<span data-ttu-id="3cbaa-690">En este ejemplo se habilitan las llamadas simultáneas y se establece un número de destino de llamadas simultáneas.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-690">This example enables simultaneous ringing and sets a simultaneous ringing destination number.</span></span>
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring
```

> [!NOTE]
> <span data-ttu-id="3cbaa-691">Para cambiar el número de destino de las llamadas simultáneas de un usuario que ya tenga habilitadas las llamadas simultáneas, mantenga el comando con el modificador /enablesimulring, ya que en caso contrario no se cambiaría el número de destino.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-691">To change the simultaneous ringing destination number of a user that has already simultaneous ringing enabled, keep the command with the /enablesimulring switch, otherwise the destination number will not be changed.</span></span> 
  
 <span data-ttu-id="3cbaa-692">**Salida**</span><span class="sxs-lookup"><span data-stu-id="3cbaa-692">**Output**</span></span>
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: True
Simul_Ringing to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="disable-simultaneous-ringing"></a><span data-ttu-id="3cbaa-693">Deshabilitar llamadas simultáneas</span><span class="sxs-lookup"><span data-stu-id="3cbaa-693">Disable Simultaneous Ringing</span></span>

<span data-ttu-id="3cbaa-694">En este ejemplo se deshabilitan las llamadas simultáneas.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-694">This example disables simultaneous ringing.</span></span>
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablesimulring
```

 <span data-ttu-id="3cbaa-695">**Salida**</span><span class="sxs-lookup"><span data-stu-id="3cbaa-695">**Output**</span></span>
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a><span data-ttu-id="3cbaa-696">Agregar un miembro para llamada de equipo y configurar las llamadas simultáneas en el grupo de miembros de llamada de equipo</span><span class="sxs-lookup"><span data-stu-id="3cbaa-696">Add a Team Member for Team-Call and Set up Simultaneous Ringing to the Team-Call Members Group</span></span>

<span data-ttu-id="3cbaa-697">En este ejemplo se agrega un miembro de equipo al grupo de llamada de equipo de un usuario y se habilitan las llamadas simultáneas al grupo de llamada de equipo.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-697">This example adds a team member to the team-call group of a user and enables simultaneous ringing to the team-call group.</span></span>
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="3cbaa-698">Al agregar a un miembro a un grupo de llamada de equipo de un usuario se cambiará automáticamente a la configuración de llamadas simultáneas de los usuarios para llamar simultáneamente a su grupo de llamada de equipo.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-698">Adding a member to the team-call group of a user will automatically switch the simultaneous ringing settigs of the users to simulring his team-call group.</span></span> 
  
 <span data-ttu-id="3cbaa-699">**Salida**</span><span class="sxs-lookup"><span data-stu-id="3cbaa-699">**Output**</span></span>
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Team ringing enabled. Team: sip:anders@contoso.com
```

#### <a name="remove-a-member-from-the-team-call-group"></a><span data-ttu-id="3cbaa-700">Quitar a un miembro del grupo de llamada de equipo</span><span class="sxs-lookup"><span data-stu-id="3cbaa-700">Remove a Member from the Team-Call Group</span></span>

<span data-ttu-id="3cbaa-701">En este ejemplo se quita a un miembro del equipo del grupo de llamada de equipo de un usuario.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-701">This example removes a team member of the team-call group of a user.</span></span>
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com
```

> [!NOTE]
> <span data-ttu-id="3cbaa-702">Si el miembro que va a quitarse es el único miembro del grupo de llamada de equipo, se deshabilitarán automáticamente las llamadas simultáneas al grupo de llamada de equipo.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-702">If the member being removed is the only member of the team-call group, simultaneously ringing to the team-call group will be automatically disabled.</span></span> 
  
 <span data-ttu-id="3cbaa-703">**Salida**</span><span class="sxs-lookup"><span data-stu-id="3cbaa-703">**Output**</span></span>
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="set-the-delayed-ring-to-the-team-call-group"></a><span data-ttu-id="3cbaa-704">Establecer la demora de timbre al grupo de llamada de equipo</span><span class="sxs-lookup"><span data-stu-id="3cbaa-704">Set the Delayed Ring to the Team-Call Group</span></span>

<span data-ttu-id="3cbaa-705">En este ejemplo se cambia la configuración de hora de demora de timbre al grupo de llamada de equipo.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-705">This example changes the delayed ring to the team-call group time setting.</span></span>
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringteam:5
```

 <span data-ttu-id="3cbaa-706">**Salida**</span><span class="sxs-lookup"><span data-stu-id="3cbaa-706">**Output**</span></span>
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com
```

#### <a name="enable-team-call"></a><span data-ttu-id="3cbaa-707">Habilitar llamada de equipo</span><span class="sxs-lookup"><span data-stu-id="3cbaa-707">Enable Team-Call</span></span>

<span data-ttu-id="3cbaa-708">En este ejemplo se habilita la llamada de equipo para un usuario concreto.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-708">This example enables team-call for a given user.</span></span>
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="3cbaa-709">Si el grupo de llamada de equipo del usuario no tiene miembros, llamada de equipo no estará activado.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-709">If the team-call group of the user has no members, team-call won't be enabled.</span></span> 
  
 <span data-ttu-id="3cbaa-710">**Salida**</span><span class="sxs-lookup"><span data-stu-id="3cbaa-710">**Output**</span></span>
  
#### <a name="disable-team-call"></a><span data-ttu-id="3cbaa-711">Deshabilitar la llamada de equipo</span><span class="sxs-lookup"><span data-stu-id="3cbaa-711">Disable Team-Call</span></span>

<span data-ttu-id="3cbaa-712">En este ejemplo se deshabilita la llamada de equipo para un usuario concreto.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-712">This example disables team-call for a given user.</span></span>
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disableteamcall
```

 <span data-ttu-id="3cbaa-713">**Salida**</span><span class="sxs-lookup"><span data-stu-id="3cbaa-713">**Output**</span></span>
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a><span data-ttu-id="3cbaa-714">Habilitar la respuesta de llamadas grupales y asignar un grupo de respuesta a un usuario</span><span class="sxs-lookup"><span data-stu-id="3cbaa-714">Enable Group Call Pickup and Assign a Pickup Group to a User</span></span>

<span data-ttu-id="3cbaa-715">En este ejemplo se asigna un grupo de respuesta a un usuario y se habilita la respuesta de llamadas grupales.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-715">This example assigns a pickup group to a user and enables Group Call Pickup.</span></span>
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199
```

 <span data-ttu-id="3cbaa-716">**Salida**</span><span class="sxs-lookup"><span data-stu-id="3cbaa-716">**Output**</span></span>
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone
```

#### <a name="disable-group-call-pickup"></a><span data-ttu-id="3cbaa-717">Deshabilitar la respuesta de llamadas grupales</span><span class="sxs-lookup"><span data-stu-id="3cbaa-717">Disable Group Call Pickup</span></span>

<span data-ttu-id="3cbaa-718">En este ejemplo se deshabilita la respuesta de llamadas grupales para un usuario concreto.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-718">This example disables Group Call Pickup for a given user.</span></span>
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablegrouppickup
```

> [!NOTE]
> <span data-ttu-id="3cbaa-p187">Cuando se deshabilita la respuesta de llamadas grupales para un usuario, no se conserva el número de grupo que se asignó al usuario. Si posteriormente quiere volver a habilitar la respuesta de llamadas grupales para ese usuario, deberá volver a asignar el número de grupo con el modificador /enablegrouppickup.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-p187">When you disable Group Call Pickup for a user, the group number that was assigned to the user is not retained. If you subsequently want to re-enable Group Call Pickup for that user, you must assign the group number again with the /enablegrouppickup switch.</span></span> 
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
```

## <a name="sysprepps1"></a><span data-ttu-id="3cbaa-721">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="3cbaa-721">SYSPrep.ps1</span></span>
<span data-ttu-id="3cbaa-722"><a name="SYSPrep"> </a></span><span class="sxs-lookup"><span data-stu-id="3cbaa-722"></span></span>

### <a name="description"></a><span data-ttu-id="3cbaa-723">Descripción</span><span class="sxs-lookup"><span data-stu-id="3cbaa-723">Description</span></span>

<span data-ttu-id="3cbaa-724">SYSPrep.ps1 es una secuencia de comandos de Windows PowerShell que instalará la siguiente Skype Business Server 2015 los requisitos previos en el equipo del sistema operativo Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-724">SYSPrep.ps1 is a Windows PowerShell script that will install the following Skype for Business Server 2015 prerequisites on your Windows Server 2008 operating system machine.</span></span>
  
- <span data-ttu-id="3cbaa-725">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="3cbaa-725">Microsoft .Net Framework 4.5</span></span>
    
- <span data-ttu-id="3cbaa-726">Microsoft SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="3cbaa-726">Microsoft SQL Server Express</span></span>
    
- <span data-ttu-id="3cbaa-727">Windows Powershell versión 3.0</span><span class="sxs-lookup"><span data-stu-id="3cbaa-727">Windows Powershell version 3.0</span></span>
    
- <span data-ttu-id="3cbaa-728">Paquete redistribuible de Visual C++ 2010</span><span class="sxs-lookup"><span data-stu-id="3cbaa-728">Visual C++ 2010 Redistributable</span></span>
    
- <span data-ttu-id="3cbaa-729">Actualizaciones de Internet Information Server</span><span class="sxs-lookup"><span data-stu-id="3cbaa-729">Internet Information Server Updates</span></span>
    
- <span data-ttu-id="3cbaa-730">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="3cbaa-730">Windows Identity Foundation</span></span>
    
- <span data-ttu-id="3cbaa-731">Skype para archivos de Business Server Core de 2015</span><span class="sxs-lookup"><span data-stu-id="3cbaa-731">Skype for Business Server 2015 Core files</span></span>
    
 <span data-ttu-id="3cbaa-732">Aunque el nombre del script es parecido a la herramienta de preparación del sistema de los sistemas operativos Microsoft Windows, en realidad son distintos.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-732">While the script name is similar to the System Preparation Tool for the Microsoft Windows operating systems, they are different.</span></span> <span data-ttu-id="3cbaa-733">Esta secuencia de comandos sólo instalará los prerrequisitos necesarios para Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-733">This script will only install the required prerequisites for Skype for Business Server 2015.</span></span> <span data-ttu-id="3cbaa-734">Después de instalar estos requisitos previos, puede utilizarse la herramienta SYSPrep de Windows para crear una imagen del servidor.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-734">Once those prerequisites are installed, the Windows SYSPrep tool can then be used to create an image of the server.</span></span>
  
### <a name="requirements"></a><span data-ttu-id="3cbaa-735">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3cbaa-735">Requirements</span></span>

<span data-ttu-id="3cbaa-736">Antes de ejecutar la secuencia de comandos de SYSPrep.ps1, debe copiar los archivos necesarios en una carpeta local en el equipo del sistema operativo Windows Server 2008 (por ejemplo **D:\Setup)**.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-736">Prior to running the SYSPrep.ps1 script, you must copy the prerequisite files to a local folder on the Windows Server 2008 operating system machine (for example **D:\Setup)**.</span></span> <span data-ttu-id="3cbaa-737">Esta carpeta también debe incluir una copia de la Skype para archivos de Business Server 2015, específicamente **Setup.exe.**</span><span class="sxs-lookup"><span data-stu-id="3cbaa-737">This folder must also include a copy of the Skype for Business Server 2015 files, specifically **Setup.exe.**</span></span> <span data-ttu-id="3cbaa-738">Los archivos de requisitos previos pueden descargarse desde las ubicaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="3cbaa-738">The prerequisite files can be downloaded from the following locations:</span></span>
  
|<span data-ttu-id="3cbaa-739">**Requisito previo**</span><span class="sxs-lookup"><span data-stu-id="3cbaa-739">**Prerequisite**</span></span>|<span data-ttu-id="3cbaa-740">**Ubicación**</span><span class="sxs-lookup"><span data-stu-id="3cbaa-740">**Location**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3cbaa-741">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="3cbaa-741">Microsoft .Net Framework 4.5</span></span>  <br/> |http://go.microsoft.com/?linkid=9816306  <br/> |
|<span data-ttu-id="3cbaa-742">Microsoft SQL Server Express 2008 R2</span><span class="sxs-lookup"><span data-stu-id="3cbaa-742">Microsoft SQL Server Express 2008 R2</span></span>  <br/> |http://www.microsoft.com/en-us/download/details.aspx?id=23650  <br/> |
|<span data-ttu-id="3cbaa-743">Windows Powershell versión 3.0</span><span class="sxs-lookup"><span data-stu-id="3cbaa-743">Windows Powershell version 3.0</span></span>  <br/> |http://www.microsoft.com/en-us/download/details.aspx?id=34595  <br/> |
|<span data-ttu-id="3cbaa-744">Paquete redistribuible de Visual C++ 2010</span><span class="sxs-lookup"><span data-stu-id="3cbaa-744">Visual C++ 2010 Redistributable</span></span>  <br/> |http://www.microsoft.com/en-us/download/details.aspx?id=5555  <br/> |
|<span data-ttu-id="3cbaa-745">Actualizaciones de Internet Information Server</span><span class="sxs-lookup"><span data-stu-id="3cbaa-745">Internet Information Server Updates</span></span>  <br/> |http://www.microsoft.com/en-us/download/details.aspx?id=34869  <br/> |
|<span data-ttu-id="3cbaa-746">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="3cbaa-746">Windows Identity Foundation</span></span>  <br/> |http://www.microsoft.com/en-us/download/details.aspx?id=17331  <br/> |
|<span data-ttu-id="3cbaa-747">Skype para Business Server 2015 Setup.exe</span><span class="sxs-lookup"><span data-stu-id="3cbaa-747">Skype for Business Server 2015 Setup.exe</span></span>  <br/> |<span data-ttu-id="3cbaa-748">Copie de Skype de media Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="3cbaa-748">Copy from Skype for Business Server 2015 media</span></span>  <br/> |
   
### <a name="parameter"></a><span data-ttu-id="3cbaa-749">Parámetro</span><span class="sxs-lookup"><span data-stu-id="3cbaa-749">Parameter</span></span>

<span data-ttu-id="3cbaa-750">El parámetro **- SetupFolder** toma como argumento la ubicación del directorio de los archivos de requisitos previos</span><span class="sxs-lookup"><span data-stu-id="3cbaa-750">The **-SetupFolder** parameter takes as an argument the directory location of the prerequisite files</span></span>
  
### <a name="examples"></a><span data-ttu-id="3cbaa-751">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="3cbaa-751">Examples</span></span>

<span data-ttu-id="3cbaa-752">Para ejecutar la secuencia de comandos de SYSPrep.ps1 e instalar el Skype para los requisitos previos de Business Server 2015, ejecute el comando siguiente desde un símbolo del sistema con privilegios elevados:</span><span class="sxs-lookup"><span data-stu-id="3cbaa-752">To run the SYSPrep.ps1 script and install the Skype for Business Server 2015 prerequisites, run the following command from an elevated command prompt:</span></span>
  
```
./SysPrep.PS1 -SetupFolder D:\Setup
```

## <a name="unassigned-number-announcements-migration"></a><span data-ttu-id="3cbaa-753">Unassigned Number Announcements Migration (Migración de anuncios de números sin asignar)</span><span class="sxs-lookup"><span data-stu-id="3cbaa-753">Unassigned Number Announcements Migration</span></span>
<span data-ttu-id="3cbaa-754"><a name="UNAM"> </a></span><span class="sxs-lookup"><span data-stu-id="3cbaa-754"></span></span>

<span data-ttu-id="3cbaa-755">La herramienta de migración de anuncios sin asignar de número permite un Skype para el Administrador de servidor de negocios 2015 mover la configuración de los números no asignados que atiende la solicitud de anuncio desde un origen de Skype de negocio o grupo de servidores a un destino Skype de negocio o grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-755">The Unassigned Number Announcements Migration tool enables a Skype for Business Server 2015 administrator to move the unassigned numbers configuration that is serviced by the announcement application from a source Skype for Business Server or Pool to a destination Skype for Business Server or Pool.</span></span>
  
### <a name="description"></a><span data-ttu-id="3cbaa-756">Descripción</span><span class="sxs-lookup"><span data-stu-id="3cbaa-756">Description</span></span>

<span data-ttu-id="3cbaa-757">La herramienta Unassigned Number Announcements Migration es un script de Windows PowerShell script que mueve la configuración de los números sin asignar de la aplicación del anuncio desde un servidor o grupo de origen a un servidor o grupo distinto.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-757">The Unassigned Number Announcements Migration tool is a Windows PowerShell script that moves the unassigned numbers configuration serviced by the announcement application of a source server or pool to a different server or pool.</span></span>
  
<span data-ttu-id="3cbaa-758">Al ejecutar el script Unassigned Number Announcements Migration realizará las operaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="3cbaa-758">When executed, the Unassigned Number Announcements Migration script will perform the following operations:</span></span>
  
1. <span data-ttu-id="3cbaa-759">Mueve todos los archivos de audio utilizados en los anuncios de números sin asignar de la aplicación del anuncio hospedada en el servidor o grupo de origen al almacén de archivos del servidor o grupo de destino.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-759">Move all the audio files used by the unassigned number announcements of the announcement application hosted in the source server or pool to the file store of the destination server or pool.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3cbaa-760">Se quitan los archivos de audio desde el grupo de origen una vez que se copiarán al grupo de destino.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-760">The audio files are removed from the source pool once they're copied to the destination pool.</span></span> 
  
2. <span data-ttu-id="3cbaa-761">Mueve todos los anuncios de números sin asignar configurados para la aplicación del anuncio hospedada en el servidor o grupo de origen al servidor o grupo de destino.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-761">Move all unassigned number announcements configured for the announcement application hosted in the source server or pool to the destination server or pool.</span></span>
    
3. <span data-ttu-id="3cbaa-762">Reasigna todos los intervalos de números sin asignar de la aplicación del anuncio hospedada en el servidor o grupo de origen al servidor o grupo de destino.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-762">Reassign all the unassigned number ranges that are serviced by the announcement application hosted in the source server or pool to the destination server or pool.</span></span>
    
<span data-ttu-id="3cbaa-763">Después de ejecutar correctamente el script, todos los intervalos de números sin asignar de la aplicación del anuncio hospedada en el servidor o grupo de origen serán atendidos por la misma configuración por el destino o grupo de destino.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-763">After successfully running the script, all the unassigned number ranges that were serviced by the announcement application hosted in the source server or pool will now be serviced with the same configuration by the destination server or pool.</span></span>
  
### <a name="output"></a><span data-ttu-id="3cbaa-764">Salida</span><span class="sxs-lookup"><span data-stu-id="3cbaa-764">Output</span></span>

<span data-ttu-id="3cbaa-765">Indica la secuencia de comandos de **CsAnnouncementConfiguration de mover** en el Skype para la ventana de Shell de administración de servidor de negocio desde donde se ejecuta el éxito o el fracaso de la operación de migración.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-765">The **Move-CsAnnouncementConfiguration** script indicates in the Skype for Business Server Management Shell window from where it's executed the success or failure of the migration operation.</span></span>
  
<span data-ttu-id="3cbaa-p190">Si la ejecución de la operación es interrumpida por algún error, los intervalos de números sin asignar que se hayan movido correctamente al destino permanecerán en este de forma operativa, mientras que el resto de intervalos de números sin asignar que aún no hayan sido migrados permanecerán en el origen también de forma operativa. Para completar la migración del resto de la configuración, vuelva a ejecutar el script después de corregir el error.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-p190">If the execution of the operation is interrupted by any error, the unassigned number ranges that were successfully moved to the destination will remain in the destination in an operational form and the rest of the unassigned number ranges to be migrated will remain in the source as well in an operational form. To fully migrate the rest of the configuration, rerun the script after addressing the error.</span></span>
  
### <a name="purpose"></a><span data-ttu-id="3cbaa-768">Finalidad</span><span class="sxs-lookup"><span data-stu-id="3cbaa-768">Purpose</span></span>

<span data-ttu-id="3cbaa-769">El script Unassigned Number Announcements Migration puede utilizarse en los tres casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="3cbaa-769">The Unassigned Number Announcements Migration script can be used in the following three scenarios:</span></span>
  
- <span data-ttu-id="3cbaa-770">**Opciones de configuración de migración a una nueva versión de Skype para Business Server:** Contoso está migrando a Skype para Business Server 2015 y como parte del proceso de migración del Skype para Business Server administrador desea mover la configuración de los números no asignados atendida por la aplicación de anuncio desde el Lync Implementación de servidor de 2013 en el nuevo Skype para la implementación de Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-770">**Migrating configuration settings to a new version of Skype for Business Server:** Contoso is in the process of migrating to Skype for Business Server 2015 and as part of the migration process the Skype for Business Server administrator would like to move the unassigned numbers configuration serviced by the announcement application from the Lync Server 2013 deployment to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="3cbaa-771">Para mover los valores de configuración, el Skype para Administrador Business Server utiliza la herramienta de migración de anuncios número sin asignar.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-771">To move the configuration settings, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool.</span></span>
    
- <span data-ttu-id="3cbaa-772">**Deshacer una implementación de Skype para Business Server 2015 a Lync Server 2013:** Debido a factores inesperados, Contoso debe revertir la migración a la nueva Skype para la implementación de Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-772">**Rolling back a deployment from Skype for Business Server 2015 to Lync Server 2013:** Due unexpected factors, Contoso has to roll back the migration to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="3cbaa-773">Para minimizar las interrupciones en el servicio, el Skype para el administrador del servidor de empresa utiliza la herramienta de migración de anuncios número sin asignar para revertir la configuración de la Skype para la implementación de Business Server 2015 para la implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-773">To minimize disruptions to the service, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool to roll back the configuration from the Skype for Business Server 2015 deployment to the Lync Server 2013 deployment.</span></span>
    
- <span data-ttu-id="3cbaa-774">**El movimiento de datos entre las distintas implementaciones:** Contoso está en proceso de reemplazo de todos los servidores de un grupo con los servidores más recientes.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-774">**Moving data between deployments:** Contoso is in the process of replacing all the servers of one pool with newer servers.</span></span> <span data-ttu-id="3cbaa-775">Su estrategia consiste en implementar un nuevo Skype para el grupo de Business Server 2015, mover todos los datos del antiguo al nuevo grupo y, a continuación, descartar el antiguo grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-775">Their strategy is to deploy a new Skype for Business Server 2015 pool, move all the data from the old to the new pool, and then deprecate the old pool.</span></span> <span data-ttu-id="3cbaa-776">Después de implementar el nuevo grupo de servidores, la herramienta Unassigned Number Announcements Migration se utiliza para mover la configuración del grupo anterior al nuevo.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-776">Once the new pool is deployed, the Unassigned Number Announcements Migration tool is used to move the configuration from the old pool to the new one.</span></span>
    
#### <a name="requirements"></a><span data-ttu-id="3cbaa-777">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3cbaa-777">Requirements</span></span>

<span data-ttu-id="3cbaa-778">Estos son los requisitos principales para ejecutar correctamente la herramienta:</span><span class="sxs-lookup"><span data-stu-id="3cbaa-778">The following are the main requirements needed to successfully run the tool:</span></span>
  
1. <span data-ttu-id="3cbaa-779">La secuencia de comandos se debe ejecutar desde un equipo que tenga Skype para el Shell de administración de Business Server instalado.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-779">The script must be run from a computer that has Skype for Business Server Management Shell installed.</span></span>
    
2. <span data-ttu-id="3cbaa-780">La aplicación de anuncio debe implementarse con éxito en el origen y el destino Skype de negocio o grupos de servidores.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-780">The announcement application has to be successfully deployed in the source and destination Skype for Business Servers or Pools.</span></span>
    
#### <a name="move-csannouncementconfiguration-script"></a><span data-ttu-id="3cbaa-781">Script Move-CsAnnouncementConfiguration</span><span class="sxs-lookup"><span data-stu-id="3cbaa-781">Move-CsAnnouncementConfiguration script</span></span>

<span data-ttu-id="3cbaa-782">El script Move-CsAnnouncementConfiguration requiere los dos parámetros descritos en la tabla siguiente. </span><span class="sxs-lookup"><span data-stu-id="3cbaa-782">The Move-CsAnnouncementConfiguration script requires the two parameters that are described in the table below.</span></span> 
  
![Parámetros Move-CsAnnouncementConfiguration.](../media/Reskit_2012_Tools_Documentation_Image41.JPG)
  
### <a name="examples"></a><span data-ttu-id="3cbaa-784">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="3cbaa-784">Examples</span></span>

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-skype-for-business-server-2015-pool"></a><span data-ttu-id="3cbaa-785">Mover la configuración de anuncios sin asignar número de un grupo de Lync Server 2013 a un Skype para Business Server 2015 Pool</span><span class="sxs-lookup"><span data-stu-id="3cbaa-785">Moving the Unassigned Number Announcements Configuration from a Lync Server 2013 Pool to a Skype for Business Server 2015 Pool</span></span>

<span data-ttu-id="3cbaa-786">Este ejemplo mueve los anuncios número sin asignar desde el grupo de origen (Lync Server 2013) al grupo de destino (Skype para Business Server 2015).</span><span class="sxs-lookup"><span data-stu-id="3cbaa-786">This example moves the unassigned number announcements from the source pool (Lync Server 2013) to the destination pool (Skype for Business Server 2015).</span></span>
  
```
Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination SfBS2015Pool.contoso.com

```

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-skype-for-business-server-2015-pool-to-a-lync-server-2013-pool"></a><span data-ttu-id="3cbaa-787">Mover la configuración de anuncios sin asignar número de un Skype para Business Server 2015 grupo a un grupo de 2013 de Lync Server</span><span class="sxs-lookup"><span data-stu-id="3cbaa-787">Moving the Unassigned Number Announcements Configuration from a Skype for Business Server 2015 Pool to a Lync Server 2013 Pool</span></span>

<span data-ttu-id="3cbaa-788">Este ejemplo mueve los anuncios número sin asignar desde el grupo de origen (Skype para Business Server 2015) al grupo de destino (Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="3cbaa-788">This example moves the unassigned number announcements from the source pool (Skype for Business Server 2015) to the destination pool (Lync Server 2013).</span></span>
  
```
Move-CsAnnouncementConfiguration.ps1 -Source SfBS2015Pool.contoso.com -Destination LS2013Pool.contoso.com
```

## <a name="web-conf-data"></a><span data-ttu-id="3cbaa-789">Web Conf Data</span><span class="sxs-lookup"><span data-stu-id="3cbaa-789">Web Conf Data</span></span>
<span data-ttu-id="3cbaa-790"><a name="WebConfData"> </a></span><span class="sxs-lookup"><span data-stu-id="3cbaa-790"></span></span>

<span data-ttu-id="3cbaa-791">La herramienta de datos Conf Web permite a un administrador de Skype para el software de comunicaciones de Business Server 2015 para tener más control sobre los datos asociados a las conferencias Web del organizador.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-791">The Web Conf Data Tool allows an administrator of Skype for Business Server 2015 communications software to have more control over the data associated with an organizer's Web conferences.</span></span> <span data-ttu-id="3cbaa-792">Escenarios incluyen la capacidad para eliminar datos de un usuario específico de la reunión basados en un criterio de sello de tiempo.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-792">Scenarios include the ability to delete a specific user's meeting data based on a time stamp criteria.</span></span>
  
### <a name="description"></a><span data-ttu-id="3cbaa-793">Descripción</span><span class="sxs-lookup"><span data-stu-id="3cbaa-793">Description</span></span>

<span data-ttu-id="3cbaa-794">Esta herramienta permite al administrador realizar las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="3cbaa-794">This tool allows the administrator to perform the following operations:</span></span>
  
1. <span data-ttu-id="3cbaa-795">Buscar todos los datos de conferencias web asociados con un usuario concreto.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-795">Find all Web conferencing data associated with a single user.</span></span>
    
2. <span data-ttu-id="3cbaa-796">Eliminar todos los datos de conferencias web asociados con un usuario concreto.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-796">Delete all Web conferencing data associated with a single user.</span></span>
    
3. <span data-ttu-id="3cbaa-797">Eliminar todos los datos de conferencias web asociados con un usuario concreto anteriores a una fecha concreta</span><span class="sxs-lookup"><span data-stu-id="3cbaa-797">Delete all Web conferencing data associated with a single user that is older than a certain date.</span></span>
    
4. <span data-ttu-id="3cbaa-798">Mover todos los datos de conferencias web asociados con un usuario concreto al mover a dicho usuario desde un grupo a otro.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-798">Move all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span>
    
> [!NOTE]
> <span data-ttu-id="3cbaa-799">Las herramientas del Kit de recursos de Lync Server 2010 admite mover todos los datos de la conferencia Web asociados a un único usuario al que el usuario se mueve de un grupo a otro.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-799">The Resource Kit Tools for Lync Server 2010 supported moving all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span> <span data-ttu-id="3cbaa-800">Dicha funcionalidad ya no se utiliza en favor del parámetro **MoveConferenceData**.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-800">That functionality is now deprecated from this tool in favor of the **MoveConferenceData** parameter.</span></span> <span data-ttu-id="3cbaa-801">Para obtener más información sobre este parámetro, vea el cmdlet [Move-Csusuario](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="3cbaa-801">For details about this parameter, see the [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps) cmdlet.</span></span>
  
<span data-ttu-id="3cbaa-p196">Esta herramienta elimina únicamente los datos de las reuniones inactivas. Las reuniones activas (o reuniones en sesiones) no se pueden eliminar.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-p196">The tool deletes meeting data only for meetings that are inactive. Active meetings (or meetings in sessions) cannot be deleted.</span></span>
  
<span data-ttu-id="3cbaa-p197">Esta herramienta debe ejecutarse desde un equipo que se encuentre en el mismo grupo que el usuario de destino. El usuario cuyos datos de contenidos de reuniones vayan a ser administrados por esta herramienta ha de ser hospedado en el mismo grupo de usuarios.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-p197">This tool must be run from a computer that is in the same pool as the target user. The user whose meeting content data is being managed by this tool must be homed in the same user pool.</span></span>
  
### <a name="output"></a><span data-ttu-id="3cbaa-806">Salida</span><span class="sxs-lookup"><span data-stu-id="3cbaa-806">Output</span></span>

<span data-ttu-id="3cbaa-807">Esta herramienta informa de los resultados de todas las operaciones:</span><span class="sxs-lookup"><span data-stu-id="3cbaa-807">This tool outputs the results of each of the operations:</span></span>
  
- <span data-ttu-id="3cbaa-808">Si se realiza una consulta, la herramienta genera una lista de todas las carpetas de datos de reuniones inactivas que tengan al usuario como organizador.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-808">If a query is performed, the tool outputs the list of all inactive meeting data folders that have that user as an organizer.</span></span>
    
- <span data-ttu-id="3cbaa-809">Si se eliminan datos, la herramienta genera una lista de todas las carpetas de datos de reuniones cuyos datos se eliminarán.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-809">If a delete is performed, the tool outputs the list of all meeting data folders whose data will be deleted.</span></span>
    
### <a name="requirements"></a><span data-ttu-id="3cbaa-810">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3cbaa-810">Requirements</span></span>

<span data-ttu-id="3cbaa-811">La herramienta ha de ejecutarse en el mismo grupo donde esté hospedado actualmente el organizador.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-811">The tool needs to be run in the same pool where the organizer is currently homed.</span></span>
  
<span data-ttu-id="3cbaa-812">La herramienta debe ejecutarse con privilegios de administrador con acceso al almacén de archivos de contenido.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-812">The tool must be run using administrator privileges with access to the Content File Store.</span></span>
  
### <a name="examples"></a><span data-ttu-id="3cbaa-813">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="3cbaa-813">Examples</span></span>

<span data-ttu-id="3cbaa-814">En la tabla siguiente se describen los parámetros, algunos de los cuales se han utilizado en los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-814">The following table describes the parameters, some of which are used in the examples.</span></span>
  
![Parámetros de herramientas de datos de configuración web.](../media/Reskit_2012_Tools_Documentation_Image51.JPG)
  
```
WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""
```

<span data-ttu-id="3cbaa-p198">En el ejemplo anterior se mostraba el funcionamiento de un comando de consulta. La salida de dicho comando sería una lista de todas las carpetas de contenido de reuniones que serían afectadas por esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-p198">The preceding example shows how a query command would work. The output of such a command would be a list of all meeting content folders that would be affected by this tool.</span></span>
  
```
WebConfDataTool.exe /User:user0@contoso.com /Action:delete
```

<span data-ttu-id="3cbaa-p199">En el ejemplo anterior se muestra el comando delete. Este comando elimina todas las carpetas de reuniones inactivas de este usuario.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-p199">The preceding is an example of a delete command. The delete command will remove all inactive meeting folders from this user.</span></span>
  
### <a name="summary"></a><span data-ttu-id="3cbaa-820">Resumen</span><span class="sxs-lookup"><span data-stu-id="3cbaa-820">Summary</span></span>

<span data-ttu-id="3cbaa-821">Esta herramienta puede ser un recurso útil para administradores que necesiten un control más preciso en los datos de reuniones de conferencias.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-821">This tool can be a valuable resource to administrators who need more precise control over conference meeting data.</span></span>
  

