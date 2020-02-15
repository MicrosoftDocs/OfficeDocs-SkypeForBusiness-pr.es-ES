---
title: Documentación de las herramientas del kit de recursos de Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/20/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
description: En este tema se describen las herramientas del kit de recursos de Skype empresarial Server 2015, incluido el propósito de cada herramienta y ejemplos de uso. El kit de recursos de Skype empresarial Server 2015 ayuda a simplificar las tareas rutinarias para los administradores de ti que implementan y administran Skype empresarial Server 2015. Por ejemplo, la herramienta de datos Web conf puede usarse para controlar fácilmente los datos cargados por los usuarios durante una reunión en línea. La herramienta SEFAUtil se puede usar para configurar el desvío de llamadas de delegado y responder para los usuarios. Recomendamos a los administradores de ti que usen estas herramientas para administrar de forma más eficaz Skype empresarial Server 2015.
ms.openlocfilehash: ab43d8e951308fab5a4aefc25d9dad2804ea5d0e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42005995"
---
# <a name="skype-for-business-server-2015-resource-kit-tools-documentation"></a><span data-ttu-id="434e6-107">Documentación de las herramientas del kit de recursos de Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="434e6-107">Skype for Business Server 2015 Resource Kit Tools Documentation</span></span>

<span data-ttu-id="434e6-108">En este tema se describen las herramientas del kit de recursos de Skype empresarial Server 2015, incluido el propósito de cada herramienta y ejemplos de uso.</span><span class="sxs-lookup"><span data-stu-id="434e6-108">This topic describes the tools in the Skype for Business Server 2015 Resource Kit, including the purpose of each tool, and examples of its use.</span></span> <span data-ttu-id="434e6-109">El kit de recursos de Skype empresarial Server 2015 ayuda a simplificar las tareas rutinarias para los administradores de ti que implementan y administran Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="434e6-109">The Skype for Business Server 2015 Resource Kit helps to make routine tasks easier for IT administrators who deploy and manage Skype for Business Server 2015.</span></span> <span data-ttu-id="434e6-110">Por ejemplo, la herramienta de **datos Web conf** puede usarse para controlar fácilmente los datos cargados por los usuarios durante una reunión en línea.</span><span class="sxs-lookup"><span data-stu-id="434e6-110">For example, the **Web Conf Data** tool can be used to easily control data that is uploaded by users during an online meeting.</span></span> <span data-ttu-id="434e6-111">La herramienta **SEFAUtil** se puede usar para configurar el desvío de llamadas de delegado y responder para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="434e6-111">The **SEFAUtil** tool can be used to set up delegate call forwarding and answering for users.</span></span> <span data-ttu-id="434e6-112">Recomendamos a los administradores de ti que usen estas herramientas para administrar de forma más eficaz Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="434e6-112">We encourage IT administrators to use these tools to more effectively manage Skype for Business Server 2015.</span></span>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="434e6-113">Instalación de las herramientas del kit de recursos</span><span class="sxs-lookup"><span data-stu-id="434e6-113">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="434e6-114">Para instalar el kit de recursos de Skype empresarial Server 2015, descargue [OCSReskit. msi](https://www.microsoft.com/download/details.aspx?id=52631) desde el centro de descarga.</span><span class="sxs-lookup"><span data-stu-id="434e6-114">To install the Skype for Business Server 2015 Resource Kit, download [OCSReskit.msi](https://www.microsoft.com/download/details.aspx?id=52631) from the Download Center.</span></span>

<span data-ttu-id="434e6-115">Ejecute **OCSResKit. msi** para realizar una instalación sencilla.</span><span class="sxs-lookup"><span data-stu-id="434e6-115">Run **OCSResKit.msi** to do a simple installation.</span></span> <span data-ttu-id="434e6-116">El. msi instala todas las herramientas en la siguiente ruta de acceso: **% Program Programa%\skype for Business Server 2015 \ reskit**.</span><span class="sxs-lookup"><span data-stu-id="434e6-116">The .msi installs all the tools in the following path: **%Program Files%\Skype for Business Server 2015\ResKit**.</span></span> <span data-ttu-id="434e6-117">Las herramientas que son ejecutables independientes se encuentran en esta carpeta.</span><span class="sxs-lookup"><span data-stu-id="434e6-117">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="434e6-118">Las herramientas que también tienen archivos auxiliares están en sus propias subcarpetas.</span><span class="sxs-lookup"><span data-stu-id="434e6-118">Tools that also have supporting files are in their own subfolders.</span></span>

## <a name="supported-environments"></a><span data-ttu-id="434e6-119">Entornos compatibles</span><span class="sxs-lookup"><span data-stu-id="434e6-119">Supported Environments</span></span>

<span data-ttu-id="434e6-120">El kit de recursos de Skype empresarial Server 2015 debe instalarse en un servidor que cumpla las especificaciones requeridas para Skype empresarial Server 2015, normalmente uno que se usa para ejecutar Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="434e6-120">The Skype for Business Server 2015 Resource Kit should be installed on a server that meets the specifications required for Skype for Business Server 2015, usually one being used to run Skype for Business Server 2015.</span></span>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="434e6-121">Introducción a las herramientas del kit de recursos</span><span class="sxs-lookup"><span data-stu-id="434e6-121">Resource Kit Tools Overview</span></span>

<span data-ttu-id="434e6-122">A continuación se muestra una lista de las herramientas que se proporcionan en el kit de recursos de Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="434e6-122">The following is a list of the tools that are provided in the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="434e6-123">En las siguientes secciones se describe una descripción de cada herramienta, incluidos los requisitos y el uso de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="434e6-123">A description of each tool, including the requirements and example usage is covered in the following sections.</span></span>

- [<span data-ttu-id="434e6-124">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="434e6-124">ABSConfig</span></span>](resource-kit-tools.md#ABSConfig)

- [<span data-ttu-id="434e6-125">Monitor del servicio de directiva de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="434e6-125">Bandwidth Policy Service Monitor</span></span>](resource-kit-tools.md#bpsm)

- [<span data-ttu-id="434e6-126">Analizador de uso de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="434e6-126">Bandwidth Utilization Analyzer</span></span>](resource-kit-tools.md#bua)

- [<span data-ttu-id="434e6-127">Llamar a Parkometer</span><span class="sxs-lookup"><span data-stu-id="434e6-127">Call Parkometer</span></span>](resource-kit-tools.md#callpark)

- [<span data-ttu-id="434e6-128">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="434e6-128">DBAnalyze</span></span>](resource-kit-tools.md#dba)

- [<span data-ttu-id="434e6-129">Importar datos del servicio de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="434e6-129">Import Storage Service Data</span></span>](resource-kit-tools.md#Issd)

- [<span data-ttu-id="434e6-130">LCSSync</span><span class="sxs-lookup"><span data-stu-id="434e6-130">LCSSync</span></span>](resource-kit-tools.md#LCSSync)

- [<span data-ttu-id="434e6-131">Consola del usuario de búsqueda</span><span class="sxs-lookup"><span data-stu-id="434e6-131">Lookup User Console</span></span>](resource-kit-tools.md#LUC)

- [<span data-ttu-id="434e6-132">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="434e6-132">MsTurnPing</span></span>](resource-kit-tools.md#MsTurnPing)

- [<span data-ttu-id="434e6-133">Visor de configuración de red</span><span class="sxs-lookup"><span data-stu-id="434e6-133">Network Configuration Viewer</span></span>](resource-kit-tools.md#NCV)

- [<span data-ttu-id="434e6-134">Response Group Agent Live</span><span class="sxs-lookup"><span data-stu-id="434e6-134">Response Group Agent Live</span></span>](resource-kit-tools.md#RGAL)

- [<span data-ttu-id="434e6-135">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="434e6-135">SEFAUtil</span></span>](resource-kit-tools.md#SEFAUtil)

- [<span data-ttu-id="434e6-136">SYSPrep. ps1</span><span class="sxs-lookup"><span data-stu-id="434e6-136">SYSPrep.ps1</span></span>](resource-kit-tools.md#SYSPrep)

- [<span data-ttu-id="434e6-137">Número de anuncios no asignados a la migración</span><span class="sxs-lookup"><span data-stu-id="434e6-137">Unassigned Number Announcements Migration</span></span>](resource-kit-tools.md#UNAM)

- [<span data-ttu-id="434e6-138">Datos de conf de Web</span><span class="sxs-lookup"><span data-stu-id="434e6-138">Web Conf Data</span></span>](resource-kit-tools.md#WebConfData)

## <a name="absconfig"></a><span data-ttu-id="434e6-139">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="434e6-139">ABSConfig</span></span>
<span data-ttu-id="434e6-140"><a name="ABSConfig"> </a></span><span class="sxs-lookup"><span data-stu-id="434e6-140"><a name="ABSConfig"> </a></span></span>

<span data-ttu-id="434e6-141">La herramienta de configuración del servicio de libreta de direcciones (ABSConfig) es una herramienta administrativa que ayuda a los administradores a personalizar la configuración del servicio de libreta de direcciones en Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="434e6-141">The Address Book Service Configuration tool (ABSConfig) is an administrative tool that helps administrators customize Address Book Service configuration in Skype for Business Server 2015.</span></span> <span data-ttu-id="434e6-142">Esta herramienta también permite a los administradores de Skype empresarial Server 2015 restaurar la configuración predeterminada del servicio de libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="434e6-142">This tool also enables Skype for Business Server 2015 administrators to restore the default Address Book Service settings.</span></span>

### <a name="description"></a><span data-ttu-id="434e6-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="434e6-143">Description</span></span>

<span data-ttu-id="434e6-144">ABSConfig es una aplicación de interfaz de usuario gráfica que permite a los administradores configurar los atributos de servicios de dominio de Active Directory relacionados con el servicio de libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="434e6-144">ABSConfig is a graphical user interface application that enables administrators to configure Active Directory Domain Services attributes that are related to Address Book Service.</span></span>

<span data-ttu-id="434e6-145">Los escenarios principales de la herramienta son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="434e6-145">The primary scenarios for the tool are the following:</span></span>

- <span data-ttu-id="434e6-146">Permitir a los administradores asignar atributos en los servicios de dominio de Active Directory a los atributos de Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="434e6-146">To enable administrators to map attributes in Active Directory Domain Services to the attributes for Skype for Business Server 2015.</span></span>

- <span data-ttu-id="434e6-147">Permitir a los administradores especificar el atributo de servicios de dominio de Active Directory que se va a incluir o excluir en los archivos del servicio de libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="434e6-147">To enable administrators to specify the Active Directory Domain Services attribute to be included or excluded in the Address Book Service files.</span></span>

- <span data-ttu-id="434e6-148">Para permitir a los administradores restaurar la configuración predeterminada del servicio de libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="434e6-148">To enable administrators to restore default Address Book Service settings.</span></span>

<span data-ttu-id="434e6-149">La herramienta ABSConfig se puede iniciar mediante el archivo ABSConfig. exe.</span><span class="sxs-lookup"><span data-stu-id="434e6-149">The ABSConfig tool can be started by using the ABSConfig.exe file.</span></span> <span data-ttu-id="434e6-150">La herramienta se abre en la ficha **configurar atributos** . Esta tabla tiene opciones para asignar atributos de servicios de dominio de Active Directory a los campos de atributo de Skype empresarial Server 2015 y para especificar qué usuarios se deben incluir o excluir en los archivos del servicio de libreta de direcciones basándose en filtros de atributo específicos.</span><span class="sxs-lookup"><span data-stu-id="434e6-150">The tool opens to the **Configure Attributes** tab. This table has options to map Active Directory Domain Services attributes to the attribute fields for Skype for Business Server 2015 and to specify which users to include or exclude in Address Book Service files based on specific attribute filters.</span></span> <span data-ttu-id="434e6-151">También tiene opciones para personalizar el valor del número de teléfono que se incluirá en el archivo de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="434e6-151">It also has options to customize which value of the phone number to be included in the Address Book file.</span></span> <span data-ttu-id="434e6-152">La opción **Restaurar valores predeterminados** permite a los administradores restaurar la configuración del servicio de libreta de direcciones en los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="434e6-152">The **Restore Defaults** option enables administrators to restore Address Book Service settings to default values.</span></span>

> [!NOTE]
> <span data-ttu-id="434e6-153">La reasignación de atributos de AD a distintos nombres de campo OC solo funciona con la descarga del archivo de la libreta de direcciones y no es compatible con la consulta Web de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="434e6-153">Re-mapping of AD attributes to different OC Field Names will only work for Address Book File Download, and is not supported by Address Book Web Query.</span></span>

### <a name="output"></a><span data-ttu-id="434e6-154">Output</span><span class="sxs-lookup"><span data-stu-id="434e6-154">Output</span></span>

<span data-ttu-id="434e6-155">ABSConfig almacena la configuración del servicio de libreta de direcciones en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="434e6-155">ABSConfig stores the Address Book Service configuration in the database.</span></span>

```console
Path: %ProgramFiles%\Skype for Business Server 2015\Reskit
```

### <a name="purpose"></a><span data-ttu-id="434e6-156">Finalidad</span><span class="sxs-lookup"><span data-stu-id="434e6-156">Purpose</span></span>

<span data-ttu-id="434e6-157">ABSConfig proporciona una forma rápida y sencilla de personalizar el servicio de libreta de direcciones de Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="434e6-157">ABSConfig provides a quick and easy way to customize Skype for Business Server 2015 Address Book Service.</span></span>

### <a name="requirements"></a><span data-ttu-id="434e6-158">Requisitos</span><span class="sxs-lookup"><span data-stu-id="434e6-158">Requirements</span></span>

#### <a name="computer"></a><span data-ttu-id="434e6-159">Equipo</span><span class="sxs-lookup"><span data-stu-id="434e6-159">Computer</span></span>

<span data-ttu-id="434e6-160">ABSConfig solo puede ejecutarse desde un equipo unido a un dominio que tenga instalado Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="434e6-160">ABSConfig can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span> <span data-ttu-id="434e6-161">En el caso de Skype empresarial Server 2015, Enterprise Edition, esta herramienta se puede ejecutar en cualquier servidor front-end que tenga habilitado el servicio de libreta de direcciones durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="434e6-161">In the case of Skype for Business Server 2015, Enterprise Edition, this tool can be run on any Front End servers that have the Address Book Service enabled during setup.</span></span>

#### <a name="network"></a><span data-ttu-id="434e6-162">Red</span><span class="sxs-lookup"><span data-stu-id="434e6-162">Network</span></span>

<span data-ttu-id="434e6-163">El equipo debe ser capaz de conectarse al grupo de servidores front-end y a la base de datos back-end.</span><span class="sxs-lookup"><span data-stu-id="434e6-163">The computer should be able to connect to the Front End pool and back-end database.</span></span>

#### <a name="software"></a><span data-ttu-id="434e6-164">Software</span><span class="sxs-lookup"><span data-stu-id="434e6-164">Software</span></span>

<span data-ttu-id="434e6-165">Los siguientes componentes de software deben instalarse antes de ejecutar la herramienta ABSConfig:</span><span class="sxs-lookup"><span data-stu-id="434e6-165">The following software components must be installed before running the ABSConfig tool:</span></span>

- <span data-ttu-id="434e6-166">Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="434e6-166">Skype for Business Server 2015</span></span>

#### <a name="users"></a><span data-ttu-id="434e6-167">Usuarios</span><span class="sxs-lookup"><span data-stu-id="434e6-167">Users</span></span>

<span data-ttu-id="434e6-168">Administradores que tienen los permisos necesarios para actualizar la implementación de Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="434e6-168">Administrators who have the permissions required to update the Skype for Business Server 2015 deployment.</span></span>

### <a name="examples"></a><span data-ttu-id="434e6-169">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="434e6-169">Examples</span></span>

<span data-ttu-id="434e6-170">Para iniciar ABSConfig, escriba **ABSConfig. exe** en un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="434e6-170">ABSConfig can be started by typing **ABSConfig.exe** at a command prompt.</span></span> <span data-ttu-id="434e6-171">A continuación se muestra la interfaz de usuario de la herramienta ABSConfig.</span><span class="sxs-lookup"><span data-stu-id="434e6-171">Shown below is the ABSConfig tool user interface.</span></span>

![La herramienta ABSConfig. exe.](../media/Reskit_2012_Tools_Documentation_ABSConfig.JPG)

### <a name="summary"></a><span data-ttu-id="434e6-173">Resumen</span><span class="sxs-lookup"><span data-stu-id="434e6-173">Summary</span></span>

<span data-ttu-id="434e6-174">La herramienta ABSConfig proporciona a los administradores una herramienta rápida y fácil de usar para personalizar el servicio de libreta de direcciones de Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="434e6-174">The ABSConfig tool provides administrators a quick and easy to use tool to customize Skype for Business Server 2015 Address Book Service.</span></span>

## <a name="bandwidth-policy-service-monitor"></a><span data-ttu-id="434e6-175">Monitor del servicio de directiva de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="434e6-175">Bandwidth Policy Service Monitor</span></span>
<span data-ttu-id="434e6-176"><a name="bpsm"> </a></span><span class="sxs-lookup"><span data-stu-id="434e6-176"><a name="bpsm"> </a></span></span>

<span data-ttu-id="434e6-177">La herramienta de supervisión del servicio de directiva de ancho de banda está diseñada para permitir a los administradores ver una lista de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="434e6-177">The Bandwidth Policy Service Monitor tool is intended to allow administrators to view a list of the following:</span></span>

1. <span data-ttu-id="434e6-178">Todos los servicios de directiva de ancho de banda de Skype empresarial Server 2015 (autenticación y núcleo) configurados en la topología</span><span class="sxs-lookup"><span data-stu-id="434e6-178">All the configured Skype for Business Server 2015 Bandwidth Policy services (Authentication and Core) in the topology</span></span>

2. <span data-ttu-id="434e6-179">Las conexiones que realiza cada servicio a otros servicios de directiva de ancho de banda y a los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="434e6-179">The connections that each service makes to other Bandwidth Policy services and to the Edge servers</span></span>

3. <span data-ttu-id="434e6-180">Todos los vínculos configurados en el documento de configuración de red y el uso de ancho de banda en tiempo real tal y como lo indica cada uno de los servicios de directiva de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="434e6-180">All the links that are configured in the Network configuration document and real-time bandwidth usage as reported by each of the Bandwidth Policy services</span></span>

### <a name="description"></a><span data-ttu-id="434e6-181">Descripción</span><span class="sxs-lookup"><span data-stu-id="434e6-181">Description</span></span>

<span data-ttu-id="434e6-182">La herramienta de supervisión del servicio de directiva de ancho de banda se implementa como una aplicación basada en GUI.</span><span class="sxs-lookup"><span data-stu-id="434e6-182">The Bandwidth Policy Service Monitor tool is implemented as a GUI-based application.</span></span> <span data-ttu-id="434e6-183">Los administradores inician la herramienta ejecutando PDPMonUI. exe.</span><span class="sxs-lookup"><span data-stu-id="434e6-183">Administrators start the tool by running PDPMonUI.exe.</span></span>

<span data-ttu-id="434e6-184">Cuando se inicia la herramienta, intenta descubrir la lista de servicios de directivas de ancho de banda en la topología.</span><span class="sxs-lookup"><span data-stu-id="434e6-184">When the tool starts, it attempts to discover the list of Bandwidth Policy services in the topology.</span></span> <span data-ttu-id="434e6-185">Una vez realizada la actualización inicial, el panel de la izquierda de la ventana se rellena con una lista de servicios agrupados por los clústeres a los que pertenecen.</span><span class="sxs-lookup"><span data-stu-id="434e6-185">After the initial update is done, the pane to the left of the window is populated with a list of services that are grouped by the clusters that they belong to.</span></span>

<span data-ttu-id="434e6-186">Cuando los administradores seleccionan un servicio de directiva de ancho de banda en particular, el panel de la derecha muestra la información sobre ese servicio en particular.</span><span class="sxs-lookup"><span data-stu-id="434e6-186">When administrators select a particular Bandwidth Policy Service, the pane on the right displays the information about that particular service.</span></span> <span data-ttu-id="434e6-187">Ese panel también tiene dos pestañas principales que muestran información.</span><span class="sxs-lookup"><span data-stu-id="434e6-187">That pane also has two main tabs that display information.</span></span>

#### <a name="machine-info-tab"></a><span data-ttu-id="434e6-188">Ficha información del equipo</span><span class="sxs-lookup"><span data-stu-id="434e6-188">Machine Info Tab</span></span>

<span data-ttu-id="434e6-189">La ficha **información del equipo** muestra los detalles del servicio de directiva de ancho de banda seleccionado y la lista y el estado de todas las conexiones realizadas por el servicio de directiva de ancho de banda seleccionado a otros servicios.</span><span class="sxs-lookup"><span data-stu-id="434e6-189">The **Machine Info** tab shows the details of the Bandwidth Policy Service that is selected and the list and state of all the connections that are made by the selected Bandwidth Policy Service to other services.</span></span>

#### <a name="topology-info-tab"></a><span data-ttu-id="434e6-190">Pestaña información de topología</span><span class="sxs-lookup"><span data-stu-id="434e6-190">Topology Info Tab</span></span>

<span data-ttu-id="434e6-191">La ficha **información de topología** muestra una lista de todos los vínculos que se configuran en las opciones de configuración de red.</span><span class="sxs-lookup"><span data-stu-id="434e6-191">The **Topology Info** tab shows a list of all the links that are configured in the Network configuration settings.</span></span> <span data-ttu-id="434e6-192">Para cada vínculo, se muestra la capacidad de ancho de banda de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="434e6-192">For each link, the audio and video bandwidth capacity is displayed.</span></span> <span data-ttu-id="434e6-193">Además, se muestra el ancho de banda utilizado actualmente, tanto en Kbps como en un porcentaje de la capacidad.</span><span class="sxs-lookup"><span data-stu-id="434e6-193">Additionally, the currently utilized bandwidth is displayed, both in Kbps and as a percentage of the capacity.</span></span> <span data-ttu-id="434e6-194">La herramienta usa código de colores para resaltar los vínculos que tienen un uso similar al de la capacidad, lo que permite a los administradores aislar rápidamente estos vínculos.</span><span class="sxs-lookup"><span data-stu-id="434e6-194">The tool uses color-coding to highlight links that have utilization that is close to the capacity—this allows administrators to quickly isolate such links.</span></span>

> [!NOTE]
>  <span data-ttu-id="434e6-195">Si la herramienta de supervisión del servicio de directiva de ancho de banda experimenta errores cuando se conecta a cualquiera de los servicios de directiva de ancho de banda configurados, la información de las fichas información del **equipo** y información de la **topología** no se rellenará.</span><span class="sxs-lookup"><span data-stu-id="434e6-195">If the Bandwidth Policy Service Monitor tool experiences failure when it connects to any of the configured Bandwidth Policy services, the information in the **Machine Info** and the **Topology Info** tabs won't be populated.</span></span> <span data-ttu-id="434e6-196">Sin embargo, es posible que la herramienta se conecte inicialmente pero que pierda su conexión al servicio.</span><span class="sxs-lookup"><span data-stu-id="434e6-196">However, it is possible that the tool might connect initially but subsequently lose its connection to the service.</span></span> <span data-ttu-id="434e6-197">En estos casos, los administradores pueden ver información obsoleta.</span><span class="sxs-lookup"><span data-stu-id="434e6-197">In such cases, administrators might see outdated information.</span></span> <span data-ttu-id="434e6-198">Hay una marca de hora de **última actualización** en cada una de las pestañas que permite a los administradores ver cuándo se actualizó por última vez los datos de un servicio de directivas de ancho de banda determinado.</span><span class="sxs-lookup"><span data-stu-id="434e6-198">There is a **Last Updated** time stamp on each of the tabs that can allow administrators to see when the data was last updated for a particular Bandwidth Policy Service.</span></span>

### <a name="output"></a><span data-ttu-id="434e6-199">Output</span><span class="sxs-lookup"><span data-stu-id="434e6-199">Output</span></span>

<span data-ttu-id="434e6-200">No hay resultados en la línea de comandos; la salida del programa está contenida en la interfaz gráfica de usuario (GUI) principal.</span><span class="sxs-lookup"><span data-stu-id="434e6-200">There is no command-line output; the program output is contained within the main graphical user interface (GUI).</span></span>

### <a name="purpose"></a><span data-ttu-id="434e6-201">Finalidad</span><span class="sxs-lookup"><span data-stu-id="434e6-201">Purpose</span></span>

<span data-ttu-id="434e6-202">La finalidad de la herramienta de supervisión del servicio de directiva de ancho de banda es permitir a los administradores ver el estado de cada uno de los servicios de directivas de ancho de banda que se definen en la topología.</span><span class="sxs-lookup"><span data-stu-id="434e6-202">The purpose of the Bandwidth Policy Service Monitor tool is to allow administrators visibility into the state of each of the Bandwidth Policy services that are defined in the topology.</span></span> <span data-ttu-id="434e6-203">Además, los administradores pueden ver el uso de ancho de banda en tiempo real para todos los vínculos definidos en el documento de configuración de red.</span><span class="sxs-lookup"><span data-stu-id="434e6-203">In addition, administrators can see real-time bandwidth usage for all the links that are defined in the Network configuration document.</span></span>

### <a name="requirements"></a><span data-ttu-id="434e6-204">Requisitos</span><span class="sxs-lookup"><span data-stu-id="434e6-204">Requirements</span></span>

<span data-ttu-id="434e6-205">La herramienta de supervisión del servicio de directiva de ancho de banda debe ejecutarse en un equipo que forme parte de la topología de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="434e6-205">The Bandwidth Policy Service Monitor tool needs to be run on a computer that is part of the Skype for Business Server topology.</span></span>

### <a name="summary"></a><span data-ttu-id="434e6-206">Resumen</span><span class="sxs-lookup"><span data-stu-id="434e6-206">Summary</span></span>

<span data-ttu-id="434e6-207">La herramienta de supervisión del servicio de directiva de ancho de banda puede ser un recurso valioso para los administradores, de modo que puedan inspeccionar el estado de todos los servicios de directivas de ancho de banda de la topología y, lo que sea más importante, puedan obtener un uso de ancho de banda en tiempo real para los vínculos que se se define en las opciones de configuración de red.</span><span class="sxs-lookup"><span data-stu-id="434e6-207">The Bandwidth Policy Service Monitor tool can be a valuable resource to administrators so they can inspect the state of all the Bandwidth Policy services in the topology—and more importantly—they can obtain real-time bandwidth utilization for the links that are defined in the Network configuration settings.</span></span>

## <a name="bandwidth-utilization-analyzer"></a><span data-ttu-id="434e6-208">Analizador de uso de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="434e6-208">Bandwidth Utilization Analyzer</span></span>
<span data-ttu-id="434e6-209"><a name="bua"> </a></span><span class="sxs-lookup"><span data-stu-id="434e6-209"><a name="bua"> </a></span></span>

<span data-ttu-id="434e6-210">El analizador de uso de ancho de banda es una herramienta que crea informes sobre diversas vistas de consumo de ancho de banda por los puntos de conexión de UC a través de vínculos WAN en la red empresarial.</span><span class="sxs-lookup"><span data-stu-id="434e6-210">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network.</span></span> <span data-ttu-id="434e6-211">Estos informes se pueden usar para comprender el patrón de consumo de ancho de banda actual y para ayudar a planear la capacidad de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="434e6-211">These reports can be used to understand the current bandwidth consumption pattern and to aid in bandwidth capacity planning.</span></span>

### <a name="description"></a><span data-ttu-id="434e6-212">Descripción</span><span class="sxs-lookup"><span data-stu-id="434e6-212">Description</span></span>

<span data-ttu-id="434e6-213">El analizador de uso de ancho de banda se implementa como una aplicación basada en la interfaz gráfica de usuario.</span><span class="sxs-lookup"><span data-stu-id="434e6-213">Bandwidth Utilization Analyzer is implemented as a GUI-based application.</span></span> <span data-ttu-id="434e6-214">Esta herramienta genera informes específicos para el uso de audio en la red y ayuda a planear la capacidad.</span><span class="sxs-lookup"><span data-stu-id="434e6-214">This tool generates reports specifically for audio utilization across the network and helps with capacity planning.</span></span> <span data-ttu-id="434e6-215">También recorre en iteración la capacidad de ancho de banda asignada a varios vínculos.</span><span class="sxs-lookup"><span data-stu-id="434e6-215">It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

### <a name="output"></a><span data-ttu-id="434e6-216">Output</span><span class="sxs-lookup"><span data-stu-id="434e6-216">Output</span></span>

<span data-ttu-id="434e6-217">El analizador de uso de ancho de banda proporciona gráficos al al de la capacidad de ancho de banda y utilización de audio para todos los vínculos WAN configurados en el sistema.</span><span class="sxs-lookup"><span data-stu-id="434e6-217">Bandwidth Utilization Analyzer provides graphic al plots of bandwidth capacity and utilization for audio for all the WAN links that are configured in the system.</span></span>

### <a name="purpose"></a><span data-ttu-id="434e6-218">Finalidad</span><span class="sxs-lookup"><span data-stu-id="434e6-218">Purpose</span></span>

<span data-ttu-id="434e6-219">En cualquier implementación de voz y vídeo, es fundamental supervisar y comprender la tendencia del uso de ancho de banda del tráfico multimedia en toda la red de la empresa.</span><span class="sxs-lookup"><span data-stu-id="434e6-219">In any voice and video deployment, it's critical to monitor and understand the trend of bandwidth utilization of media traffic across the enterprise network.</span></span> <span data-ttu-id="434e6-220">La herramienta analizador de uso de ancho de banda permite que un administrador logre exactamente eso.</span><span class="sxs-lookup"><span data-stu-id="434e6-220">The Bandwidth Utilization Analyzer tool allows an administrator to achieve just that.</span></span> <span data-ttu-id="434e6-221">Esta herramienta hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="434e6-221">This tool does the following:</span></span>

- <span data-ttu-id="434e6-222">Genera informes específicos para el uso de audio en la red</span><span class="sxs-lookup"><span data-stu-id="434e6-222">Generates specific reports for audio utilization across the network</span></span>

- <span data-ttu-id="434e6-223">Ayuda a planear y iterar la capacidad con mayor eficacia en la capacidad de ancho de banda asignada a varios vínculos</span><span class="sxs-lookup"><span data-stu-id="434e6-223">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="434e6-224">El analizador de uso de ancho de banda puede generar trazados gráficos de la capacidad de ancho de banda e informes de utilización; son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="434e6-224">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and utilization reports; they are as follows:</span></span>

- <span data-ttu-id="434e6-225">Todos los vínculos WAN en la red empresarial</span><span class="sxs-lookup"><span data-stu-id="434e6-225">All the WAN links in the enterprise network</span></span>

- <span data-ttu-id="434e6-226">Filtrados por los vínculos WAN seleccionados que se han elegido</span><span class="sxs-lookup"><span data-stu-id="434e6-226">Filtered by selected WAN links that have been chosen</span></span>

- <span data-ttu-id="434e6-227">Filtrados por los vínculos WAN que han superado la capacidad de vínculo</span><span class="sxs-lookup"><span data-stu-id="434e6-227">Filtered by WAN links that have exceeded link capacity</span></span>

- <span data-ttu-id="434e6-228">Filtrados por los vínculos WAN que han estado bajo el uso del ancho de banda aprovisionado</span><span class="sxs-lookup"><span data-stu-id="434e6-228">Filtered by WAN links that have been under-utilizing the provisioned bandwidth</span></span>

- <span data-ttu-id="434e6-229">Filtra por vínculos WAN que han alcanzado niveles críticos (un uso de ancho de banda superior al 90% de la capacidad de ancho de banda del vínculo WAN)</span><span class="sxs-lookup"><span data-stu-id="434e6-229">Filter by WAN links that have been reaching critical levels (a bandwidth utilization that is greater than 90% of bandwidth capacity of the WAN link)</span></span>

- <span data-ttu-id="434e6-230">Filtrados por tipo de vínculo WAN: vínculos de sitios de red, vínculos interregionales y vínculos dentro de un sitio</span><span class="sxs-lookup"><span data-stu-id="434e6-230">Filtered by WAN link type—network-site links, interregional links, and links within a site</span></span>

- <span data-ttu-id="434e6-231">Filtrados por región de red</span><span class="sxs-lookup"><span data-stu-id="434e6-231">Filtered by network region</span></span>

#### <a name="applications"></a><span data-ttu-id="434e6-232">Aplicaciones</span><span class="sxs-lookup"><span data-stu-id="434e6-232">Applications</span></span>

<span data-ttu-id="434e6-233">El analizador de uso de ancho de banda tiene las dos aplicaciones siguientes (herramientas):</span><span class="sxs-lookup"><span data-stu-id="434e6-233">Bandwidth Utilization Analyzer has the following two applications (tools):</span></span>

- <span data-ttu-id="434e6-234">**WanLinkLogCollector. exe** esta herramienta permite al usuario especificar la información necesaria.</span><span class="sxs-lookup"><span data-stu-id="434e6-234">**WanLinkLogCollector.exe** This tool enables its user to input the required information.</span></span>

- <span data-ttu-id="434e6-235">**BandwidthUtilizationAnalyzer. xlsm** se inicia automáticamente un informe de software de hoja de cálculo de Microsoft Excel mediante WanLinkLogCollector. exe.</span><span class="sxs-lookup"><span data-stu-id="434e6-235">**BandwidthUtilizationAnalyzer.xlsm** A Microsoft Excel spreadsheet software report is automatically launched by WanLinkLogCollector.exe.</span></span> <span data-ttu-id="434e6-236">Esta aplicación permite al usuario aplicar filtros al informe, tal como se muestra más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="434e6-236">This application allows the user to apply filters to the report as shown later in this article.</span></span>

#### <a name="phases-of-using-bandwidth-utilization-analyzer"></a><span data-ttu-id="434e6-237">Fases del uso del analizador de uso de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="434e6-237">Phases of Using Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="434e6-238">Hay dos fases al usar el analizador de uso de ancho de banda:</span><span class="sxs-lookup"><span data-stu-id="434e6-238">There are two phases when using Bandwidth Utilization Analyzer:</span></span>

- <span data-ttu-id="434e6-239">Recopilar registros, que se realiza mediante WanLinkLogCollector. exe</span><span class="sxs-lookup"><span data-stu-id="434e6-239">Collect logs, which is performed by using WanLinkLogCollector.exe</span></span>

- <span data-ttu-id="434e6-240">Personalización de informes, que se realiza mediante BandwidthUtilizationAnalyzer. xlsm</span><span class="sxs-lookup"><span data-stu-id="434e6-240">Customize reports, which is performed by using BandwidthUtilizationAnalyzer.xlsm</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="434e6-241">Se recomienda encarecidamente que los usuarios finales no inicien manualmente BandwidthUtilizationAnalyzer. xlsm.</span><span class="sxs-lookup"><span data-stu-id="434e6-241">We strongly recommend that BandwidthUtilizationAnalyzer.xlsm not be manually launched by end users.</span></span>

#### <a name="starting-bandwidth-utilization-analyzer"></a><span data-ttu-id="434e6-242">Inicio del analizador de uso de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="434e6-242">Starting Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="434e6-243">Inicie WanLinkLogCollector. exe en el símbolo del sistema o mediante el explorador de Windows.</span><span class="sxs-lookup"><span data-stu-id="434e6-243">Start WanLinkLogCollector.exe at the command prompt or by using Windows Explorer.</span></span>

 <span data-ttu-id="434e6-244">**Uso de WanLinkLogCollector. exe**</span><span class="sxs-lookup"><span data-stu-id="434e6-244">**Using WanLinkLogCollector.exe**</span></span>

<span data-ttu-id="434e6-245">Hay tres pasos para usar WanLinkLogCollector. exe:</span><span class="sxs-lookup"><span data-stu-id="434e6-245">There are three steps to using WanLinkLogCollector.exe:</span></span>

1. <span data-ttu-id="434e6-246">**Registrar la escala de tiempo** Proporcionar la escala de tiempo que debe generarse el informe para</span><span class="sxs-lookup"><span data-stu-id="434e6-246">**Log the timeline** Provide the timeline that the report needs to be generated for</span></span>

2. <span data-ttu-id="434e6-247">**Especificar los directorios de archivos** Proporcionar información de ubicación de archivos</span><span class="sxs-lookup"><span data-stu-id="434e6-247">**Specify the file directories** Provide file location information</span></span>

3. <span data-ttu-id="434e6-248">**Recopilar los registros e iniciar el visor de informes** Ejecutar el comando para generar el informe</span><span class="sxs-lookup"><span data-stu-id="434e6-248">**Collect the logs and launch the report viewer** Execute the command to generate the report</span></span>

#### <a name="step-1---log-the-timeline"></a><span data-ttu-id="434e6-249">Paso 1: registrar la escala de tiempo</span><span class="sxs-lookup"><span data-stu-id="434e6-249">Step 1 - Log the timeline</span></span>

<span data-ttu-id="434e6-250">El registro de la escala de tiempo permite que el usuario de la herramienta especifique lo siguiente, tal como se muestra en la figura siguiente.</span><span class="sxs-lookup"><span data-stu-id="434e6-250">Logging the timeline allows the tool user to specify the following as shown in the figure below.</span></span>

1. <span data-ttu-id="434e6-251">**Fecha de inicio** Esta es la fecha de inicio de la escala de tiempo para la que se generará el informe; por ejemplo, 1 de agosto de 2010.</span><span class="sxs-lookup"><span data-stu-id="434e6-251">**Start date** This is the start date of the timeline that the report is to be generated for; for example, August 1, 2010.</span></span>

2. <span data-ttu-id="434e6-252">**Fecha de finalización** Esta es la fecha de finalización de la escala de tiempo para la que se generará el informe; por ejemplo, 30 de septiembre de 2010.</span><span class="sxs-lookup"><span data-stu-id="434e6-252">**End date** This is the end date of the timeline that the report is to be generated for; for example, September 30, 2010.</span></span>

     ![Fechas de inicio y finalización en el uso del ancho de banda](../media/Reskit_2012_Tools_Documentation_Image4.jpg)

#### <a name="step-2---specify-the-file-directories"></a><span data-ttu-id="434e6-254">Paso 2: especificar los directorios de archivos</span><span class="sxs-lookup"><span data-stu-id="434e6-254">Step 2 - Specify the file directories</span></span>

<span data-ttu-id="434e6-255">El usuario puede especificar los siguientes directorios de archivos, tal y como se muestra.</span><span class="sxs-lookup"><span data-stu-id="434e6-255">The following file directories can be specified by the user as shown.</span></span>

- <span data-ttu-id="434e6-256">**Ubicación de los archivos de registro del servidor** La ubicación de la carpeta donde se almacenan los registros del servidor de directivas de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="434e6-256">**Server log files location** The folder location where Bandwidth policy server logs are stored.</span></span> <span data-ttu-id="434e6-257">Esto se suele en \<fileserver\> \\<opción de\>fe \AppServerFiles\PDP.</span><span class="sxs-lookup"><span data-stu-id="434e6-257">This is typically in \<fileserver\>\\<choice of FE\>\AppServerFiles\PDP.</span></span>

- <span data-ttu-id="434e6-258">**Ubicación de almacenamiento de archivos temporales** Ubicación del archivo temporal donde se almacenan los archivos intermedios mientras se genera el informe.</span><span class="sxs-lookup"><span data-stu-id="434e6-258">**Temporary file storage location** The temporary file location where intermediate files are stored while the report is being generated.</span></span>

    ![Directorios de archivos en el banda de uso de ancho de banda](../media/Reskit_2012_Tools_Documentation_Image5.jpg)

    > [!NOTE]
    > <span data-ttu-id="434e6-260">Asegúrese de que el acceso a los registros del servidor y la carpeta de almacén de archivos temporales sea suficiente para el usuario de la herramienta.</span><span class="sxs-lookup"><span data-stu-id="434e6-260">Ensure that sufficient file access to the server logs and the temporary file store folder is provided to the tool user.</span></span>

#### <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a><span data-ttu-id="434e6-261">Paso 3: recopilar los registros e iniciar el visor de informes</span><span class="sxs-lookup"><span data-stu-id="434e6-261">Step 3 - Collect the logs and start the report viewer</span></span>

<span data-ttu-id="434e6-262">Para recopilar los registros e iniciar el visor de informes, haga clic en **Ejecutar** como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="434e6-262">To collect the logs and start the report viewer, click **Execute** as shown below.</span></span> <span data-ttu-id="434e6-263">Este paso recopila los datos necesarios.</span><span class="sxs-lookup"><span data-stu-id="434e6-263">This step collects the required data.</span></span>

![Recopilar datos en el banda de uso de ancho de banda](../media/Reskit_2012_Tools_Documentation_Image6.jpg)

<span data-ttu-id="434e6-265">Cuando la validación de entrada es correcta, se muestra el mensaje que se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="434e6-265">When the input validation is successful, the message shown below is displayed.</span></span>

![Registros recopilados de la notificación en el uso de ancho de banda](../media/Reskit_2012_Tools_Documentation_Image7.jpg)

<span data-ttu-id="434e6-267">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="434e6-267">Click **OK**.</span></span> <span data-ttu-id="434e6-268">BandwidthUtilizationAnalyzer. xlsm se inicia automáticamente.</span><span class="sxs-lookup"><span data-stu-id="434e6-268">BandwidthUtilizationAnalyzer.xlsm is automatically started.</span></span> <span data-ttu-id="434e6-269">Siga las instrucciones del cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="434e6-269">Follow the instructions in the message box.</span></span> <span data-ttu-id="434e6-270">Para obtener más información, consulte **uso de BandwidthUtilizationAnalyzer. xlsm** en la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="434e6-270">For details, see **Using BandwidthUtilizationAnalyzer.xlsm** in the next section.</span></span>


### <a name="using-bandwidthutilizationanalyzerxlsm"></a><span data-ttu-id="434e6-271">Uso de BandwidthUtilizationAnalyzer. xlsm</span><span class="sxs-lookup"><span data-stu-id="434e6-271">Using BandwidthUtilizationAnalyzer.xlsm</span></span>

1. <span data-ttu-id="434e6-272">Cuando BandwidthUtilizationAnalyzer. xlsm se inicie automáticamente, haga clic en **Actualizar** como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="434e6-272">When BandwidthUtilizationAnalyzer.xlsm is automatically started, click **Refresh** as shown below.</span></span>

     ![BandwidthUtilizationAnalyzer. xlsm](../media/Reskit_2012_Tools_Documentation_Image8.jpg)

2. <span data-ttu-id="434e6-274">Cuando se abre una carpeta de archivos, seleccione Consolidated. csv en la ubicación que se especifica en el cuadro de mensaje, como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="434e6-274">When a file folder is opened, select consolidated.csv from the location that is specified in the message box as shown below.</span></span> <span data-ttu-id="434e6-275">También muestra la ubicación como **C:\temp**.</span><span class="sxs-lookup"><span data-stu-id="434e6-275">It also shows the location as **C:\Temp**.</span></span>

     ![Abrir una carpeta en BandwidthUtilizationAnalyzer.](../media/Reskit_2012_Tools_Documentation_Image9.jpg)

3. <span data-ttu-id="434e6-277">Haga clic en **Importar**.</span><span class="sxs-lookup"><span data-stu-id="434e6-277">Click **Import**.</span></span>

4. <span data-ttu-id="434e6-278">El trazado gráfico se genera automáticamente.</span><span class="sxs-lookup"><span data-stu-id="434e6-278">The graphical plot is automatically generated.</span></span> <span data-ttu-id="434e6-279">Está disponible cuando desaparece el puntero de trabajo en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="434e6-279">It is available when the working-in-the-background pointer disappears.</span></span>

     ![Aplicar filtros en la vista informe.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

#### <a name="applying-filters-to-the-report-view"></a><span data-ttu-id="434e6-281">Aplicación de filtros a la vista de informe</span><span class="sxs-lookup"><span data-stu-id="434e6-281">Applying Filters to the Report View</span></span>

<span data-ttu-id="434e6-282">Los filtros que se pueden aplicar a la vista informes, tal como se muestra a continuación, se describen a continuación:</span><span class="sxs-lookup"><span data-stu-id="434e6-282">The filters that can be applied to the report view as shown below are described as follows:</span></span>

![Aplicar filtros en la vista informe.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

1. <span data-ttu-id="434e6-284">**Nombre** de Filtrar por vínculos WAN (el filtro está en el lado derecho del gráfico). El prefijo denota los siguientes tipos de vínculos; Vea el cuadro vertical (azul):</span><span class="sxs-lookup"><span data-stu-id="434e6-284">**Name** Filter by WAN links (the filter is on the right side of the graph).The prefix denotes the following link types; see the vertical (blue) box:</span></span>

   - <span data-ttu-id="434e6-285">**Sitio S** Vínculo WAN de un sitio de red a una región de red</span><span class="sxs-lookup"><span data-stu-id="434e6-285">**S Site** The WAN link from a network site to a network region</span></span>

   - <span data-ttu-id="434e6-286">**Es entre sitios** El vínculo WAN entre dos sitios de red</span><span class="sxs-lookup"><span data-stu-id="434e6-286">**IS Inter-Site** The WAN link between two network sites</span></span>

   - <span data-ttu-id="434e6-287">**R inter-region** El vínculo WAN entre dos regiones de red</span><span class="sxs-lookup"><span data-stu-id="434e6-287">**R Inter-Region** The WAN link between two network region</span></span>

2. <span data-ttu-id="434e6-288">**Límite superado** Filtra por vínculos WAN cuyo uso de ancho de banda es mayor que la capacidad de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="434e6-288">**Exceeded limit** Filter by WAN links whose bandwidth utilization is more than the bandwidth capacity</span></span>

3. <span data-ttu-id="434e6-289">**Niveles críticos** Filtra por vínculos WAN cuyo uso de ancho de banda ha alcanzado el 90% o más de la capacidad de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="434e6-289">**Critical levels** Filter by WAN links whose bandwidth utilization has reached 90% or more than the bandwidth capacity</span></span>

4. <span data-ttu-id="434e6-290">**Subutilizado** Filtra por vínculos WAN cuyo uso de ancho de banda ha sido inferior al 25% de la capacidad de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="434e6-290">**Under-utilized** Filter by WAN links whose bandwidth utilization has been less than 25% of the bandwidth capacity</span></span>

5. <span data-ttu-id="434e6-291">**Tipo de vínculo** Filtrar por los siguientes tipos de vínculos WAN:</span><span class="sxs-lookup"><span data-stu-id="434e6-291">**Link type** Filter by the following WAN links types:</span></span>

   - <span data-ttu-id="434e6-292">Tipo de **sitio de red**</span><span class="sxs-lookup"><span data-stu-id="434e6-292">**Network site** type</span></span>

   - <span data-ttu-id="434e6-293">Tipo **entre sitios**</span><span class="sxs-lookup"><span data-stu-id="434e6-293">**Inter-site** type</span></span>

   - <span data-ttu-id="434e6-294">Tipo **de vínculo entre regiones**</span><span class="sxs-lookup"><span data-stu-id="434e6-294">**Inter-Region link** type</span></span>

6. <span data-ttu-id="434e6-295">**Región** Filtrar por región de red</span><span class="sxs-lookup"><span data-stu-id="434e6-295">**Region** Filter by network region</span></span>

<span data-ttu-id="434e6-296">Las figuras siguientes muestran los filtros descritos anteriormente.</span><span class="sxs-lookup"><span data-stu-id="434e6-296">The following figures show the previously described filters.</span></span>

<span data-ttu-id="434e6-297">Filtrar por **nombre**.</span><span class="sxs-lookup"><span data-stu-id="434e6-297">Filter by **Name**.</span></span> <span data-ttu-id="434e6-298">Seleccione la lista de vínculos que deben mostrarse en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="434e6-298">Select the list of links that need to be displayed in the graph.</span></span>

![Filtrado por nombre en BandwidthUtilizationAnalyzer.](../media/Reskit_2012_Tools_Documentation_Image12.jpg)

<span data-ttu-id="434e6-300">Filtrar por **límite superado**.</span><span class="sxs-lookup"><span data-stu-id="434e6-300">Filter by **Exceeded limit**.</span></span> <span data-ttu-id="434e6-301">Seleccione **true** para aplicar el filtro.</span><span class="sxs-lookup"><span data-stu-id="434e6-301">Select **True** to enforce the filter.</span></span>

![Filtrado por límite superado.](../media/Reskit_2012_Tools_Documentation_Image13.jpg)

<span data-ttu-id="434e6-303">Filtrar por **niveles críticos**.</span><span class="sxs-lookup"><span data-stu-id="434e6-303">Filter by **Critical levels**.</span></span> <span data-ttu-id="434e6-304">Seleccione **true** para aplicar el filtro.</span><span class="sxs-lookup"><span data-stu-id="434e6-304">Select **True** to enforce the filter.</span></span>

![Filtrado por niveles críticos.](../media/Reskit_2012_Tools_Documentation_Image14.jpg)

<span data-ttu-id="434e6-306">Filtrar por **en uso**.</span><span class="sxs-lookup"><span data-stu-id="434e6-306">Filter by **Under utilized**.</span></span> <span data-ttu-id="434e6-307">Seleccione **true** para aplicar el filtro.</span><span class="sxs-lookup"><span data-stu-id="434e6-307">Select **True** to enforce the filter.</span></span>

![Filtrado por en uso.](../media/Reskit_2012_Tools_Documentation_Image15.jpg)

<span data-ttu-id="434e6-309">Filtra por **tipo de vínculo**.</span><span class="sxs-lookup"><span data-stu-id="434e6-309">Filter by **Link Type**.</span></span> <span data-ttu-id="434e6-310">Seleccione el tipo o tipos que deben mostrarse.</span><span class="sxs-lookup"><span data-stu-id="434e6-310">Select the type or types that need to be displayed.</span></span>

![Filtrado por tipo de vínculo.](../media/Reskit_2012_Tools_Documentation_Image16.jpg)

<span data-ttu-id="434e6-312">Filtrar por **región**.</span><span class="sxs-lookup"><span data-stu-id="434e6-312">Filter by **Region**.</span></span> <span data-ttu-id="434e6-313">Seleccione una lista de regiones cuyos vínculos se deben mostrar.</span><span class="sxs-lookup"><span data-stu-id="434e6-313">Select a list of regions whose links need to be displayed.</span></span>

![Filtrado por región.](../media/Reskit_2012_Tools_Documentation_Image17.jpg)

### <a name="requirements"></a><span data-ttu-id="434e6-315">Requisitos</span><span class="sxs-lookup"><span data-stu-id="434e6-315">Requirements</span></span>

- <span data-ttu-id="434e6-316">.NET Framework 3,5</span><span class="sxs-lookup"><span data-stu-id="434e6-316">The .NET Framework 3.5</span></span>

- <span data-ttu-id="434e6-317">Microsoft Excel 2010 o Excel 2007</span><span class="sxs-lookup"><span data-stu-id="434e6-317">Microsoft Excel 2010 or Excel 2007</span></span>

### <a name="summary"></a><span data-ttu-id="434e6-318">Resumen</span><span class="sxs-lookup"><span data-stu-id="434e6-318">Summary</span></span>

<span data-ttu-id="434e6-319">El analizador de uso de ancho de banda se usa para trazar el uso del ancho de banda de audio para tráfico de comunicaciones unificadas en la red.</span><span class="sxs-lookup"><span data-stu-id="434e6-319">Bandwidth Utilization Analyzer is used to plot the audio bandwidth utilization for UC traffic across the network.</span></span> <span data-ttu-id="434e6-320">Esta herramienta se puede usar también para informar del uso de ancho de banda de vídeo en la red.</span><span class="sxs-lookup"><span data-stu-id="434e6-320">This tool can be used to report the utilization of video bandwidth on the network as well.</span></span>

## <a name="call-parkometer"></a><span data-ttu-id="434e6-321">Llamar a Parkometer</span><span class="sxs-lookup"><span data-stu-id="434e6-321">Call Parkometer</span></span>
<span data-ttu-id="434e6-322"><a name="callpark"> </a></span><span class="sxs-lookup"><span data-stu-id="434e6-322"><a name="callpark"> </a></span></span>

<span data-ttu-id="434e6-323">Call Parkometer es una aplicación de línea de comandos que proporciona acceso sencillo a la base de datos de órbitas de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="434e6-323">Call Parkometer is a command-line application that provides easy access to the Call Park orbit database.</span></span>

### <a name="description"></a><span data-ttu-id="434e6-324">Descripción</span><span class="sxs-lookup"><span data-stu-id="434e6-324">Description</span></span>

<span data-ttu-id="434e6-325">Call Parkometer es una herramienta para realizar un seguimiento de las llamadas estacionadas actualmente.</span><span class="sxs-lookup"><span data-stu-id="434e6-325">Call Parkometer is a tool to track currently parked calls.</span></span> <span data-ttu-id="434e6-326">También recopila estadísticas sobre las órbitas y el uso del servidor de estacionamiento de llamadas (CPS).</span><span class="sxs-lookup"><span data-stu-id="434e6-326">It also collects statistics about orbits and Call Park Server (CPS) usage.</span></span> <span data-ttu-id="434e6-327">Esta herramienta de línea de comandos proporciona acceso de lectura y escritura a la base de datos de SQL Server de CPS de la órbita desde un equipo conectado local o remoto.</span><span class="sxs-lookup"><span data-stu-id="434e6-327">This command-line tool provides both read and write-access to the CPS orbit SQL Server database from a local or remotely connected computer.</span></span>

<span data-ttu-id="434e6-328">Todas las opciones se excluyen mutuamente.</span><span class="sxs-lookup"><span data-stu-id="434e6-328">All options are mutually exclusive.</span></span> <span data-ttu-id="434e6-329">La sintaxis de la línea de comandos es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="434e6-329">Command-line syntax is as follows:</span></span>

- <span data-ttu-id="434e6-330">parámetro **-o** : enumera todos los intervalos de órbita configurados para este grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="434e6-330">**-o** parameter—lists all orbit ranges configured for this pool.</span></span>

- <span data-ttu-id="434e6-331">parámetro **-n** : enumera todas las órbitas usadas actualmente en este grupo.</span><span class="sxs-lookup"><span data-stu-id="434e6-331">**-n** parameter—lists all currently used orbits in this pool.</span></span> <span data-ttu-id="434e6-332">La información mostrada es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="434e6-332">The information displayed is as follows:</span></span>

  - <span data-ttu-id="434e6-333">Identificador uniforme de recursos (URI) de SIP del parque y Estacionador.</span><span class="sxs-lookup"><span data-stu-id="434e6-333">SIP Uniform Resource Identifier (URI) of the parkee and parker.</span></span>

  - <span data-ttu-id="434e6-334">Nombre de host de la CPS donde se estaciona la llamada.</span><span class="sxs-lookup"><span data-stu-id="434e6-334">Host name of the CPS where the call is parked.</span></span>

  - <span data-ttu-id="434e6-335">Marca de tiempo del momento en el que se estaciona la llamada.</span><span class="sxs-lookup"><span data-stu-id="434e6-335">Time stamp of when the call was parked.</span></span>

- <span data-ttu-id="434e6-336">parámetro **-f** : enumera el número de órbitas libres actualmente en el grupo.</span><span class="sxs-lookup"><span data-stu-id="434e6-336">**-f** parameter—lists the number of currently free orbits in the pool.</span></span>

- <span data-ttu-id="434e6-337">**-r \<el\> parámetro-n** : \<enumera\> las n últimas llamadas estacionadas.</span><span class="sxs-lookup"><span data-stu-id="434e6-337">**-r \<n\>** parameter—lists the \<n\> last parked calls.</span></span> <span data-ttu-id="434e6-338">La información mostrada es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="434e6-338">The information displayed is as follows:</span></span>

  - <span data-ttu-id="434e6-339">URI del SIP estacionado.</span><span class="sxs-lookup"><span data-stu-id="434e6-339">Parkee SIP URI.</span></span>

  - <span data-ttu-id="434e6-340">URI del SIP Estacionador.</span><span class="sxs-lookup"><span data-stu-id="434e6-340">Parker SIP URI.</span></span>

  - <span data-ttu-id="434e6-341">Nombre de host de la CPS en la que se estaciona la llamada.</span><span class="sxs-lookup"><span data-stu-id="434e6-341">Host name of the CPS where the call was parked.</span></span>

  - <span data-ttu-id="434e6-342">Marca de tiempo de Cuándo se recuperó o se quitó la llamada.</span><span class="sxs-lookup"><span data-stu-id="434e6-342">Time stamp of when the call was retrieved or dropped.</span></span>

- <span data-ttu-id="434e6-343">\*\*-t\<n\> \*\* parámetro-pruebas que reservan una órbita en la base de datos para mostrar la aleatoriedad de los números de órbitas asignados.</span><span class="sxs-lookup"><span data-stu-id="434e6-343">**-t\<n\>** parameter - tests reserving an orbit in the database to show the randomness of the assigned orbit numbers.</span></span>

### <a name="output"></a><span data-ttu-id="434e6-344">Output</span><span class="sxs-lookup"><span data-stu-id="434e6-344">Output</span></span>

<span data-ttu-id="434e6-345">En función de los parámetros de entrada que se especifiquen en un símbolo del sistema, Call Parkometer muestra el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="434e6-345">Depending on the input parameters that are specified at a command prompt, Call Parkometer displays the following output:</span></span>

- <span data-ttu-id="434e6-346">Todos los intervalos de órbitas que están configurados para este grupo</span><span class="sxs-lookup"><span data-stu-id="434e6-346">All orbit ranges that are configured for this pool</span></span>

- <span data-ttu-id="434e6-347">Llamadas estacionadas actualmente</span><span class="sxs-lookup"><span data-stu-id="434e6-347">Currently parked calls</span></span>

- <span data-ttu-id="434e6-348">Número de órbitas libres (disponibles)</span><span class="sxs-lookup"><span data-stu-id="434e6-348">Number of free (available) orbits</span></span>

- <span data-ttu-id="434e6-349">Llamadas estacionadas recientemente</span><span class="sxs-lookup"><span data-stu-id="434e6-349">Recently parked calls</span></span>

- <span data-ttu-id="434e6-350">Órbitas reservadas para probar valores de órbitas uniformes y aleatorios</span><span class="sxs-lookup"><span data-stu-id="434e6-350">Reserved orbits for testing uniform and random orbit values</span></span>

### <a name="purpose"></a><span data-ttu-id="434e6-351">Finalidad</span><span class="sxs-lookup"><span data-stu-id="434e6-351">Purpose</span></span>

<span data-ttu-id="434e6-352">La finalidad de la herramienta CPS es proporcionar acceso desde la línea de comandos a la base de datos de CPS.</span><span class="sxs-lookup"><span data-stu-id="434e6-352">The purpose of the CPS tool is to provide command-line access to the CPS database.</span></span> <span data-ttu-id="434e6-353">El administrador puede ver el uso de CPS y determinar el número de órbitas asignadas a un grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="434e6-353">The administrator can view the CPS usage and determine the number of orbits assigned to a pool.</span></span>

### <a name="requirements"></a><span data-ttu-id="434e6-354">Requisitos</span><span class="sxs-lookup"><span data-stu-id="434e6-354">Requirements</span></span>

<span data-ttu-id="434e6-355">No hay requisitos si esta herramienta se ejecuta en el mismo equipo que ejecuta CPS.</span><span class="sxs-lookup"><span data-stu-id="434e6-355">There are no requirements if this tool is run on the same computer that is running CPS.</span></span> <span data-ttu-id="434e6-356">Si esta herramienta se ejecuta en un equipo remoto, la base de datos de SQL Server usada por Skype empresarial Server 2015 debe estar configurada para permitir el acceso remoto.</span><span class="sxs-lookup"><span data-stu-id="434e6-356">If this tool is run on a remote computer, the SQL Server database used by Skype for Business Server 2015 must be configured to allow remote access.</span></span> <span data-ttu-id="434e6-357">Llamar a Parkometer debe configurarse con una cadena de conexión de base de datos de SQL Server para conectarse al servidor SQL Server del grupo.</span><span class="sxs-lookup"><span data-stu-id="434e6-357">Call Parkometer must be configured with a SQL Server database connection string to connect to the pool's SQL Server.</span></span> <span data-ttu-id="434e6-358">Esta cadena de conexión de base de datos de SQL Server se define en el archivo de configuración, **parkometer. exe. config**. Debe colocarse en el mismo directorio donde se encuentra parkometer. exe.</span><span class="sxs-lookup"><span data-stu-id="434e6-358">This SQL Server database connection string is defined in the configuration file, **parkometer.exe.config**. It must be placed in the same directory where parkometer.exe is located.</span></span> <span data-ttu-id="434e6-359">El siguiente archivo XML es un ejemplo de parkometer. exe. config. Los parámetros que deben configurarse son el nombre de usuario (por ejemplo, mydomain\Administrator), la contraseña (por ejemplo, contraseña) y el nombre de host (por ejemplo, mi servidor).</span><span class="sxs-lookup"><span data-stu-id="434e6-359">The following XML file is an example of a parkometer.exe.config. The parameters that must be configured are user name (for example, mydomain\Administrator), password (for example, mypassword), and host name (for example, myserver).</span></span>

```xml
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

### <a name="examples"></a><span data-ttu-id="434e6-360">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="434e6-360">Examples</span></span>

<span data-ttu-id="434e6-361">Intervalos de órbitas implementados: el parámetro-o muestra todos los intervalos de órbitas que están configurados para este grupo de servidores, tal y como se muestra</span><span class="sxs-lookup"><span data-stu-id="434e6-361">Deployed orbit ranges: the -o parameter lists all orbit ranges that are configured for this pool as shown</span></span>

![Intervalos de órbita en llamada Parkometer.](../media/Reskit_2012_Tools_Documentation_Image18.jpg)

<span data-ttu-id="434e6-363">Llamadas estacionadas actualmente: el parámetro-n enumera todas las órbitas usadas actualmente en este grupo de servidores, tal como se muestra</span><span class="sxs-lookup"><span data-stu-id="434e6-363">Currently parked calls: the -n parameter lists all currently used orbits on this pool as shown</span></span>

![Llamadas estacionadas actualmente en Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image19.jpg)

<span data-ttu-id="434e6-365">Número de órbitas libres: el parámetro-f enumera el número de órbitas libres actualmente en el grupo, tal como se muestra</span><span class="sxs-lookup"><span data-stu-id="434e6-365">Number of free orbits: the -f parameter lists the number of currently free orbits in the pool as shown</span></span>

![Órbitas libres en llamadas Parkometer.](../media/Reskit_2012_Tools_Documentation_Image20.jpg)

<span data-ttu-id="434e6-367">Llamadas estacionadas recientemente: el parámetro- \<r\> n enumera las \<llamadas\> de las que se han estacionado las n últimas, como se muestra</span><span class="sxs-lookup"><span data-stu-id="434e6-367">Recently parked calls: the -r \<n\> parameter lists the \<n\> last parked calls as shown</span></span>

![Llamadas estacionadas recientemente en Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image21.jpg)

<span data-ttu-id="434e6-369">Prueba de reserva orbital: el parámetro \<-\> t n comprueba la reserva de una órbita en la base de datos tal como se muestra</span><span class="sxs-lookup"><span data-stu-id="434e6-369">Test orbit reservation: the -t \<n\> parameter tests reserving an orbit in the database as shown</span></span>

![Pruebe las reservas de órbitas en Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image22.jpg)

### <a name="summary"></a><span data-ttu-id="434e6-371">Resumen</span><span class="sxs-lookup"><span data-stu-id="434e6-371">Summary</span></span>

<span data-ttu-id="434e6-372">Call Parkometer es una herramienta de línea de comandos que proporciona información detallada sobre el servidor de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="434e6-372">Call Parkometer is a command-line tool that provides detailed information about the Call Park Server.</span></span>

## <a name="dbanalyze"></a><span data-ttu-id="434e6-373">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="434e6-373">DBAnalyze</span></span>
<span data-ttu-id="434e6-374"><a name="dba"> </a></span><span class="sxs-lookup"><span data-stu-id="434e6-374"><a name="dba"> </a></span></span>

### <a name="description"></a><span data-ttu-id="434e6-375">Descripción</span><span class="sxs-lookup"><span data-stu-id="434e6-375">Description</span></span>

<span data-ttu-id="434e6-376">DBAnalyze es una herramienta de línea de comandos que ayuda a los administradores a recopilar informes de análisis sobre las bases de datos de Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="434e6-376">DBAnalyze is a command-line tool that helps administrators to gather analysis reports about the Skype for Business Server 2015 databases.</span></span> <span data-ttu-id="434e6-377">DBAnalyze tiene los siguientes modos: diagnóstico, datos de usuario, Conferencia, MCU y fragmentación de disco:</span><span class="sxs-lookup"><span data-stu-id="434e6-377">DBAnalyze has the following modes: diagnostic, user data, conference, MCUs, and disk fragmentation:</span></span>

- <span data-ttu-id="434e6-378">**Modo de diagnóstico** Crea un informe que incluye información sobre tablas (el número de registros, la fragmentación, el tamaño de los datos y el tamaño del índice), tamaño de los archivos de registro y de datos, el último tiempo de copia de seguridad, la distribución entre los servidores que ejecutan Microsoft Office Communications Server, el número promedio de permisos, contactos, contenedores, suscripciones, publicaciones, extremos por usuario, los usuarios alojados incorrectamente, los usuarios que no se pueden enrutar, el número medio de conferencias organizadas por usuario, conferencias programa y la versión de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="434e6-378">**Diagnostic mode** Creates a report that includes information about tables (number of records, fragmentation, data size, and index size), data and log file sizes, the last back-up time, contact distribution among servers that are running Microsoft Office Communications Server, the average number of permissions, contacts, containers, subscriptions, publications, endpoints per user, any improperly homed users, users that can't be routed, the average number of conferences organized per user, scheduled conferences, active conferences, and the database version.</span></span>

    > [!NOTE]
    > <span data-ttu-id="434e6-379">El modo de diagnóstico en ejecución puede afectar al rendimiento del servidor.</span><span class="sxs-lookup"><span data-stu-id="434e6-379">Running diagnostic mode can affect server performance.</span></span>

- <span data-ttu-id="434e6-380">**Modo de datos de usuario** Informa sobre los datos del contacto, el contenedor, la suscripción, la publicación, el permiso y el grupo de contactos para un usuario específico o para los usuarios que tienen ese usuario en sus listas de contactos y permisos.</span><span class="sxs-lookup"><span data-stu-id="434e6-380">**User data mode** Reports contact, container, subscription, publication, permission, and contact-group data for a specified user or for users who have that user in their contact and permission lists.</span></span> <span data-ttu-id="434e6-381">Este modo también informa de los datos de Resumen de las conferencias a las que un usuario organiza o al que está invitado.</span><span class="sxs-lookup"><span data-stu-id="434e6-381">This mode also reports summary data for conferences that a user organizes or is invited to.</span></span>

- <span data-ttu-id="434e6-382">**Modo de conferencia** Informa de datos detallados para una conferencia específica, incluidos todos los detalles de tiempo de programación de la Conferencia, la lista de invitados, la lista de tipos de medios permitidos para la Conferencia, las MCU activas (unidades de control multipunto), la lista de participantes activos y el estado de señalización de cada participante.</span><span class="sxs-lookup"><span data-stu-id="434e6-382">**Conference mode** Reports detailed data for a specific conference, including all schedule-time details for the conference, the invitee list, the list of media types allowed for the conference, active MCUs (multipoint control units), the active participant list, and each participant's signaling state.</span></span>

- <span data-ttu-id="434e6-383">**Identificador de reunión de descodificación** Descodifica un identificador de reunión de la red telefónica conmutada (RTC) que especifica el conmutador **/pstnid** pero no se conecta al back-end para obtener información detallada.</span><span class="sxs-lookup"><span data-stu-id="434e6-383">**Decode Meeting ID** Decodes a public switched telephone network (PSTN) meeting ID that is specified by the **/pstnid** switch but does not connect to the back end for detailed information.</span></span>

- <span data-ttu-id="434e6-384">**Resolver Conferencia** Descodifica un identificador de reunión RTC especificado por el modificador **/pstnid** y muestra información sobre la Conferencia indicada por el identificador.</span><span class="sxs-lookup"><span data-stu-id="434e6-384">**Resolve conference** Decodes a PSTN meeting ID that is specified by the **/pstnid** switch and displays information about the conference indicated by the ID.</span></span>

- <span data-ttu-id="434e6-385">**Modo MCU** Informa del identificador, el tipo de medio, la dirección URL, el estado de latido, la carga de conferencia y la carga de participantes de cada MCU del grupo.</span><span class="sxs-lookup"><span data-stu-id="434e6-385">**MCUs mode** Reports the ID, media type, URL, heartbeat status, conference load, and participant load for each MCU in the pool.</span></span>

- <span data-ttu-id="434e6-386">**Modo de fragmentación de disco** Muestra el estado de fragmentación de todos los discos.</span><span class="sxs-lookup"><span data-stu-id="434e6-386">**Disk fragmentation mode** Displays the fragmentation status of all disks.</span></span>

<span data-ttu-id="434e6-387">Esta herramienta se puede usar para diagnosticar varios problemas o ayudar a los administradores con la planeación de la capacidad.</span><span class="sxs-lookup"><span data-stu-id="434e6-387">This tool can be used to diagnose various problems or to assist administrators with capacity planning.</span></span> <span data-ttu-id="434e6-388">Por ejemplo, si la mayoría de los usuarios hospedados en el servidor A eligen a los usuarios hospedados en el servidor B como sus contactos, el administrador puede mover a los usuarios del servidor a al servidor B para reducir el tráfico entre servidores.</span><span class="sxs-lookup"><span data-stu-id="434e6-388">For example, if most of the users homed on server A choose users homed on server B as their contacts, the administrator can move the users on server A to server B to reduce cross-server traffic.</span></span>

### <a name="output"></a><span data-ttu-id="434e6-389">Output</span><span class="sxs-lookup"><span data-stu-id="434e6-389">Output</span></span>

<span data-ttu-id="434e6-390">Esta herramienta genera informes predefinidos sobre la base de datos de Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="434e6-390">This tool outputs predefined reports about the Skype for Business Server 2015 database.</span></span> <span data-ttu-id="434e6-391">**Ruta de acceso**:%programfiles%\Skype para Business Server 2015 \ reskit</span><span class="sxs-lookup"><span data-stu-id="434e6-391">**Path**: %ProgramFiles%\Skype for Business Server 2015\Reskit</span></span>

### <a name="purpose"></a><span data-ttu-id="434e6-392">Finalidad</span><span class="sxs-lookup"><span data-stu-id="434e6-392">Purpose</span></span>

<span data-ttu-id="434e6-393">Para instalar Dbanalyze. exe, cópielo en una carpeta local y, a continuación, ejecute la herramienta.</span><span class="sxs-lookup"><span data-stu-id="434e6-393">To install Dbanalyze.exe, copy it to a local folder and then run the tool.</span></span> <span data-ttu-id="434e6-394">Para usar la herramienta, ejecute el siguiente comando desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="434e6-394">To use the tool, run the following command from the command line.</span></span> <span data-ttu-id="434e6-395">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`A continuación se muestran las descripciones de las opciones de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="434e6-395">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` The descriptions for the command-line options are shown below.</span></span>

![Opciones de la línea de comandos para Dbanalyze. exe.](../media/Reskit_2012_Tools_Documentation_Image35.JPG)

### <a name="requirements"></a><span data-ttu-id="434e6-397">Requisitos</span><span class="sxs-lookup"><span data-stu-id="434e6-397">Requirements</span></span>

 <span data-ttu-id="434e6-398">**Equipo** DBAnalyze solo puede ejecutarse desde un equipo unido a un dominio que tenga instalado Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="434e6-398">**Computer** DBAnalyze can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span>

 <span data-ttu-id="434e6-399">**Red** El equipo debe ser capaz de conectarse a la base de datos back-end.</span><span class="sxs-lookup"><span data-stu-id="434e6-399">**Network** The computer should be able to connect to the back-end database.</span></span>

 <span data-ttu-id="434e6-400">**Software** de Los componentes de software de Skype empresarial Server 2015 deben estar instalados antes de ejecutar DBAnalyze.</span><span class="sxs-lookup"><span data-stu-id="434e6-400">**Software** Skype for Business Server 2015 software components must be installed before running DBAnalyze.</span></span>

 <span data-ttu-id="434e6-401">**Usuarios** de En la tabla siguiente se muestran los administradores que tienen los permisos necesarios para acceder a las bases de datos de Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="434e6-401">**Users**The table below shows the administrators who have the necessary permissions to access Skype for Business Server 2015 databases.</span></span>

![Tabla de permisos para Dbanalyze. exe.](../media/Reskit_2012_Tools_Documentation_Image36.JPG)

> [!NOTE]
> <span data-ttu-id="434e6-403">Se requiere una cuenta de administrador local para **/Report:** modo de disco.</span><span class="sxs-lookup"><span data-stu-id="434e6-403">A local administrator account is required for **/report:disk** mode.</span></span>

### <a name="examples"></a><span data-ttu-id="434e6-404">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="434e6-404">Examples</span></span>

<span data-ttu-id="434e6-405">Los siguientes son ejemplos de comandos Dbanalyze. exe válidos:</span><span class="sxs-lookup"><span data-stu-id="434e6-405">The following are examples of valid Dbanalyze.exe commands:</span></span>

```console
dbanalyze.exe /report:diag
dbanalyze.exe /report:user /user:usera@domainb.com
dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
dbanalyze.exe /report:resolve /pstnid:12345
dbanalyze.exe /report:mcus
dbanalyze.exe /report:disk
```

### <a name="summary"></a><span data-ttu-id="434e6-406">Resumen</span><span class="sxs-lookup"><span data-stu-id="434e6-406">Summary</span></span>

<span data-ttu-id="434e6-407">DBAnalyzer proporciona a los administradores un análisis rápido y sencillo de las bases de datos de Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="434e6-407">DBAnalyzer provides administrators a quick and easy to analyze Skype for Business Server 2015 databases.</span></span>

## <a name="import-storage-service-data"></a><span data-ttu-id="434e6-408">Importar datos del servicio de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="434e6-408">Import Storage Service Data</span></span>
<span data-ttu-id="434e6-409"><a name="Issd"> </a></span><span class="sxs-lookup"><span data-stu-id="434e6-409"><a name="Issd"> </a></span></span>

<span data-ttu-id="434e6-410">La herramienta del kit de recursos de ImportStorageServiceData permite volver a importar datos de cola y de extremo que se han vaciado del servicio de almacenamiento (LYSS) de nuevo en el servicio de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="434e6-410">The ImportStorageServiceData resource kit tool allows for re-importing Queue and Endpoint data that was flushed out of the Storage Service (LYSS) back into the Storage Service.</span></span>

### <a name="description"></a><span data-ttu-id="434e6-411">Descripción</span><span class="sxs-lookup"><span data-stu-id="434e6-411">Description</span></span>

<span data-ttu-id="434e6-412">Los datos vaciados del servicio de almacenamiento podrían haber sido automáticos (periódicos) según el estado de los elementos de la cola o la base de datos.</span><span class="sxs-lookup"><span data-stu-id="434e6-412">The data flushed out of the Storage Service could have been automatic (periodic) based on Queue Item status or database size.</span></span> <span data-ttu-id="434e6-413">Podría haber sucedido debido a la invocación manual del cmdlet de conmutación por error del grupo o al cmdlet StorageServiceFullFlush (que invoca el cmdlet de conmutación por error del grupo de servidores).</span><span class="sxs-lookup"><span data-stu-id="434e6-413">It could have happened due to the manual invocation of the pool failover cmdlet, or the StorageServiceFullFlush cmdlet (which the pool failover cmdlet invokes).</span></span> <span data-ttu-id="434e6-414">Tenga en cuenta que los datos no deberían volver a importarse si el tamaño de la base de datos del servicio de almacenamiento (LYSS) de los servidores front-end es superior al nivel normal, ya que, por lo tanto, es probable que solo se exporten más datos hacia atrás. Además, los problemas que podrían haber contribuido a errores que provocaron el crecimiento de la cola del servicio de almacenamiento deberían resolverse en primer lugar (por ejemplo, errores de punto de conexión de Exchange, problemas de red u otros problemas).</span><span class="sxs-lookup"><span data-stu-id="434e6-414">Note that data should ideally not be re-imported if any of the Storage Service (LYSS ) database size on the front ends is above the normal level, because doing so will likely just cause more data to be exported back out. Furthermore, any problems which could have contributed to errors that caused the Storage Service Queue to grow should first be resolved (for example Exchange endpoint errors, network issues, or other problems).</span></span>

 <span data-ttu-id="434e6-415">**Escenario 1:** durante la conmutación por error del grupo, es posible que los archivos se vacíen del servicio de almacenamiento para cada front-end.</span><span class="sxs-lookup"><span data-stu-id="434e6-415">**Scenario 1:** during pool failover, files may be flushed out from storage service for each front end.</span></span> <span data-ttu-id="434e6-416">Una vez completada la conmutación por error, debe ejecutarse la herramienta para volver a importar los datos.</span><span class="sxs-lookup"><span data-stu-id="434e6-416">After failover is completed, the tool should be run to re-import the data.</span></span>

 <span data-ttu-id="434e6-417">**Escenario 2:** los datos se vacían automáticamente cada día o en respuesta a la base de datos del servicio de almacenamiento que supera determinados umbrales de tamaño (por ejemplo, 60%, 80%, 90% completo).</span><span class="sxs-lookup"><span data-stu-id="434e6-417">**Scenario 2:** data is being flushed automatically each day or in response to Storage Service database exceeding certain size thresholds ( for example 60%, 80%, 90% full ).</span></span> <span data-ttu-id="434e6-418">El administrador debe volver a importar periódicamente los datos vaciados de forma automática.</span><span class="sxs-lookup"><span data-stu-id="434e6-418">This automatically flushed data should be re-imported routinely by the administrator.</span></span> <span data-ttu-id="434e6-419">En la situación anterior, si no se implementa el paquete SCOM de supervisión, hay eventos para el servicio de almacenamiento de Skype empresarial Server relacionados con los datos que se vacían del servicio de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="434e6-419">In the above situation, if the monitoring SCOM pack is not deployed, there are events for Skype for Business Server Storage Service relating to data being flushed from the Storage Service.</span></span> <span data-ttu-id="434e6-420">Se han iniciado los identificadores de evento de 32075 (operación de vaciado completa), 32076 (vaciado completo), 32082 (se inició el vaciado de nivel de mantenimiento), 32083 (vaciado de nivel de mantenimiento completo), 32089 (vaciado debido a rellenar la base de datos).</span><span class="sxs-lookup"><span data-stu-id="434e6-420">Event IDs of 32075 (full flush operation is started), 32076 (full flush has completed), 32082 (maintenance level flush started), 32083 (maintenance level flush complete), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="434e6-421">Nota estos identificadores de evento corresponden a la versión RTM.</span><span class="sxs-lookup"><span data-stu-id="434e6-421">Note these event Ids correspond to the RTM release.</span></span> <span data-ttu-id="434e6-422">Cuando un administrador ve estos eventos, significa que hay archivos que se han vaciado. Estos datos deben volver a importarse rutinariamente con esta herramienta, por ejemplo, una vez por semana.</span><span class="sxs-lookup"><span data-stu-id="434e6-422">When an administrator sees these events, it means that there are files that have been flushed out. This data should routinely be imported back using this tool, for example once per week.</span></span>

<span data-ttu-id="434e6-423">Para la versión de servicio en línea, si se ha implementado el paquete SCOM de supervisión de mantenimiento de Skype empresarial Server, hay nuevas alertas que se pueden plantear que piden al administrador que vuelva a importar los datos vaciados en el servicio de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="434e6-423">For the Online Service release, if health monitoring SCOM pack for Skype for Business Server is deployed, there are new alerts which may be raised which ask the administrator to re-import the flushed data back into Storage Service.</span></span> <span data-ttu-id="434e6-424">Habrá un evento correspondiente en el registro de eventos del servidor front-end que activó la alerta.</span><span class="sxs-lookup"><span data-stu-id="434e6-424">There will be a corresponding event in the event log on the Front End server which triggered the alert.</span></span> <span data-ttu-id="434e6-425">El evento proporcionará una descripción de la ruta de acceso principal en la que se ubican los archivos de datos vaciados, así como el número de archivos que cumplen los criterios de alerta.</span><span class="sxs-lookup"><span data-stu-id="434e6-425">The event will give a description of the Parent path under which the flushed data files are located, as well as how many files there are which meet the alert criteria.</span></span> <span data-ttu-id="434e6-426">Los criterios de alerta son que hay X o más archivos en la ruta de acceso del elemento primario concreta que tienen al menos días Y de antigüedad (donde X e Y están preestablecidos en el StorageService, pero se pueden invalidar cambiando el archivo APPCONFIG). A continuación, se muestran dos ejemplos de eventos que pueden desencadenar la alerta de mantenimiento, con la diferencia de que la ruta de acceso principal.</span><span class="sxs-lookup"><span data-stu-id="434e6-426">The alert criteria is that there are X or more files under the particular parent path which are at least Y days old ( where X and Y are preset within the StorageService but can be overridden by changing the APPCONFIG file.)Two examples of events which can trigger the health alert are shown below, with the difference being their parent path.</span></span> <span data-ttu-id="434e6-427">Una posibilidad está en el uso compartido de archivos del servicio Web, mientras que la otra posibilidad es el directorio de datos de la aplicación local de cada front-end.</span><span class="sxs-lookup"><span data-stu-id="434e6-427">One possibility is under Web service file share, while the other possibility is the local Application Data directory of each front end.</span></span> <span data-ttu-id="434e6-428">(por ejemplo c:\ProgramData\Microsoft\Skype para Business Server 2015 \ StorageService).</span><span class="sxs-lookup"><span data-stu-id="434e6-428">( for example c:\ProgramData\Microsoft\Skype for Business Server 2015\StorageService ).</span></span> <span data-ttu-id="434e6-429">A continuación, el administrador ejecutará esta herramienta de reskit.</span><span class="sxs-lookup"><span data-stu-id="434e6-429">The administrator will then run this reskit tool.</span></span>

<span data-ttu-id="434e6-430">Esta herramienta aumentará la carga de la CPU y de e/s en el front-end en el que se ejecuta, así como otros front-end, en la situación en que los datos no son propiedad del servidor front-end en el que se ejecuta la herramienta.</span><span class="sxs-lookup"><span data-stu-id="434e6-430">This tool will increase CPU and IO load on the front end it is running on, as well as other front ends, in the situation that the data is not owned by the front end that the tool is executed on.</span></span> <span data-ttu-id="434e6-431">Se recomienda ejecutar esta herramienta cuando los servidores front-end no tienen una carga de CPU y de e/s intensa, por ejemplo, fuera de las horas pico.</span><span class="sxs-lookup"><span data-stu-id="434e6-431">We recommend runng this tool when front ends are not under heavy CPU and IO load, for example outside of peak hours.</span></span> <span data-ttu-id="434e6-432">En segundo lugar, esta herramienta puede tener entre 2 y 3 minutos para importar un archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="434e6-432">Secondly, this tool can 2 to 3 minutes to import one data file.</span></span> <span data-ttu-id="434e6-433">Tenga esto en cuenta al estimar cuánto tiempo se ejecutará la herramienta.</span><span class="sxs-lookup"><span data-stu-id="434e6-433">Keep this in mind when estimating how long tool will be running.</span></span> <span data-ttu-id="434e6-434">El archivo de registro detallado generado por la herramienta aparecerá de forma predeterminada en el almacén de archivos.</span><span class="sxs-lookup"><span data-stu-id="434e6-434">The verbose log file generated by the tool will by default appear on the File Store.</span></span> <span data-ttu-id="434e6-435">Elimínelo si no se han notificado errores, ya que el archivo de registro puede tener decenas de MB o más.</span><span class="sxs-lookup"><span data-stu-id="434e6-435">Delete it if there are no errors reported, because the log file can be tens of MB or more.</span></span>

![Ejemplo de eventos del registro de eventos del servidor de almacenamiento.](../media/Reskit_2012_Tools_Documentation_Image1.jpg)

### <a name="requirements"></a><span data-ttu-id="434e6-437">Requisitos</span><span class="sxs-lookup"><span data-stu-id="434e6-437">Requirements</span></span>

<span data-ttu-id="434e6-438">Instale las herramientas del kit de recursos de Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="434e6-438">Install the Skype for Business Server 2015 Resource Kit tools.</span></span> <span data-ttu-id="434e6-439">La herramienta se ejecuta en equipos Unidos a un dominio donde están instalados Skype empresarial Server y Skype empresarial Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="434e6-439">The tool runs on domain-joined machines where Skype for Business Server and Skype for Business Server Management Shell are installed.</span></span> <span data-ttu-id="434e6-440">La herramienta usa un cmdlet desde el shell de administración para identificar todos los servidores front-end del grupo.</span><span class="sxs-lookup"><span data-stu-id="434e6-440">The tool uses a cmdlet from the management shell to identify all the Front End servers in the pool.</span></span> <span data-ttu-id="434e6-441">En segundo lugar, la herramienta debe ejecutarse desde un equipo en el grupo de servidores que tenga instalada la base de datos **RtcLocal** .</span><span class="sxs-lookup"><span data-stu-id="434e6-441">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="434e6-442">Esta base de datos la usa la herramienta para recuperar la ubicación del recurso compartido de archivos WebService para el grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="434e6-442">This database is used by the tool to retrieve the location of the WEBSERVICE file share for the pool.</span></span> <span data-ttu-id="434e6-443">Además, antes de usar la herramienta, cada servidor front-end debe habilitar la comunicación remota de Windows PowerShell con **enable-PSRemoting** en cada servidor front-end, así como el equipo desde el que se ejecuta la herramienta.</span><span class="sxs-lookup"><span data-stu-id="434e6-443">Additionally, before using the tool, each Front End server must first enable Windows PowerShell Remoting using **Enable-PSRemoting** on each Front End server, as well as the machine that the tool is executed from.</span></span> <span data-ttu-id="434e6-444">De lo contrario, se producirá un error en los comandos remotos de Windows PowerShell de esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="434e6-444">Otherwise, remote Windows PowerShell commands from this tool will fail.</span></span> <span data-ttu-id="434e6-445">La comunicación remota de Windows PowerShell puede desactivarse en todos los servidores front-end del grupo una vez finalizado.</span><span class="sxs-lookup"><span data-stu-id="434e6-445">Windows PowerShell Remoting can be turned off on all Front End servers in the pool after it is finished.</span></span> <span data-ttu-id="434e6-446">Por último, la cuenta o credencial que invoca la herramienta debe tener permiso de lectura y escritura en el recurso compartido de archivos WebService para el grupo en el que está ejecutando esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="434e6-446">Finally, the account or credential invoking the tool must have read/write permission to the webservice file share for the pool they are executing this tool on.</span></span> <span data-ttu-id="434e6-447">De lo contrario, la herramienta producirá errores de permiso de e/s.</span><span class="sxs-lookup"><span data-stu-id="434e6-447">Otherwise the tool will fail with IO Permission errors.</span></span>

> [!NOTE]
> <span data-ttu-id="434e6-448">En Windows Server 2012, la comunicación remota de Windows PowerShell está habilitada de forma predeterminada, pero no en el sistema operativo Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="434e6-448">On Windows Server 2012, Windows PowerShell Remoting is enabled by default, but not on the Windows Server 2008 operating system.</span></span>

### <a name="examples"></a><span data-ttu-id="434e6-449">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="434e6-449">Examples</span></span>

```console
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

## <a name="lcssync"></a><span data-ttu-id="434e6-450">LCSSync</span><span class="sxs-lookup"><span data-stu-id="434e6-450">LCSSync</span></span>
<span data-ttu-id="434e6-451"><a name="LCSSync"> </a></span><span class="sxs-lookup"><span data-stu-id="434e6-451"><a name="LCSSync"> </a></span></span>

<span data-ttu-id="434e6-452">La herramienta LCSSync ayuda a implementar el software de comunicaciones de Skype empresarial Server 2015 en un entorno de varios bosques.</span><span class="sxs-lookup"><span data-stu-id="434e6-452">The LCSSync tool helps to deploy Skype for Business Server 2015 communications software in a multi-forest environment.</span></span> <span data-ttu-id="434e6-453">Esta herramienta se usa para sincronizar usuarios y grupos de bosques de usuarios diferentes como un objeto de contacto de servicios de dominio de Active Directory para un bosque central en el que se ha instalado Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="434e6-453">This tool is used to synchronize users and groups from different user forests as an Active Directory Domain Services contact object to a central forest where Skype for Business Server 2015 is installed.</span></span>

### <a name="description"></a><span data-ttu-id="434e6-454">Descripción</span><span class="sxs-lookup"><span data-stu-id="434e6-454">Description</span></span>

 <span data-ttu-id="434e6-455">LCSSync usa los objetos de contacto de los servicios de dominio de Active Directory sincronizados en el bosque central para habilitar a los usuarios en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="434e6-455">LCSSync uses the synchronized Active Directory Domain Services contact objects in the central forest to enable users for Skype for Business Server.</span></span> <span data-ttu-id="434e6-456">Para proporcionar un inicio de sesión único, la cuenta de usuario principal debe estar asignada al objeto de contacto de servicios de dominio de Active Directory en el bosque central de Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="434e6-456">To provide single sign-in, the primary user account must be mapped to the Active Directory Domain Services contact object in the central forest for Skype for Business Server 2015.</span></span> <span data-ttu-id="434e6-457">Esta herramienta ayuda a realizar esa asignación.</span><span class="sxs-lookup"><span data-stu-id="434e6-457">This tool helps perform that mapping.</span></span> <span data-ttu-id="434e6-458">Esta herramienta proporciona plantillas para crear agentes de administración en Microsoft Identity Integration Server.</span><span class="sxs-lookup"><span data-stu-id="434e6-458">This tool provides templates for creating Management Agents in the Microsoft Identity Integration Server.</span></span>

### <a name="summary"></a><span data-ttu-id="434e6-459">Resumen</span><span class="sxs-lookup"><span data-stu-id="434e6-459">Summary</span></span>

<span data-ttu-id="434e6-460">La herramienta LCSSync ayuda a implementar Skype empresarial Server 2015 en un entorno de varios bosques.</span><span class="sxs-lookup"><span data-stu-id="434e6-460">The LCSSync tool helps to deploy Skype for Business Server 2015 in a multi-forest environment.</span></span>

## <a name="lookup-user-console"></a><span data-ttu-id="434e6-461">Consola del usuario de búsqueda</span><span class="sxs-lookup"><span data-stu-id="434e6-461">Lookup User Console</span></span>
<span data-ttu-id="434e6-462"><a name="LUC"> </a></span><span class="sxs-lookup"><span data-stu-id="434e6-462"><a name="LUC"> </a></span></span>

<span data-ttu-id="434e6-463">La herramienta LookupUserConsole muestra información de enrutamiento del servidor de Skype empresarial interno sobre usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="434e6-463">The LookupUserConsole tool displays internal Skype for Business Server routing information about specific users.</span></span> <span data-ttu-id="434e6-464">Esta información puede ser útil para que Microsoft admita personal en el diagnóstico de problemas de implementación y enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="434e6-464">This information may be useful to Microsoft support personal in diagnosing deployment and routing problems.</span></span>

### <a name="description"></a><span data-ttu-id="434e6-465">Descripción</span><span class="sxs-lookup"><span data-stu-id="434e6-465">Description</span></span>

 <span data-ttu-id="434e6-466">Al ejecutar LookupUserConsole. exe se abrirá un símbolo del sistema que acepta direcciones SIP e intenta mostrar la información de enrutamiento de Skype empresarial Server interna relacionada.</span><span class="sxs-lookup"><span data-stu-id="434e6-466">Executing LookupUserConsole.exe will open a command prompt that accepts SIP addresses and attempts to display internal Skype for Business Server routing information relating them.</span></span> <span data-ttu-id="434e6-467">Escriba **Exit** para salir de la herramienta LookupUserConsole.</span><span class="sxs-lookup"><span data-stu-id="434e6-467">Type **exit** to quit the LookupUserConsole tool.</span></span>

### <a name="requirements"></a><span data-ttu-id="434e6-468">Requisitos</span><span class="sxs-lookup"><span data-stu-id="434e6-468">Requirements</span></span>

<span data-ttu-id="434e6-469">Instale el kit de recursos de Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="434e6-469">Install the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="434e6-470">La herramienta se ejecuta en equipos Unidos a un dominio donde está instalado Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="434e6-470">The tool runs on domain-joined machines where Skype for Business Server is installed.</span></span>

### <a name="examples"></a><span data-ttu-id="434e6-471">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="434e6-471">Examples</span></span>

<span data-ttu-id="434e6-472">C:\Archivos de Files\Skype para Business Server 2015 \ reskit\>LookupUserConsole. exe</span><span class="sxs-lookup"><span data-stu-id="434e6-472">C:\Program Files\Skype for Business Server 2015\ResKit\>LookupUserConsole.exe</span></span>

```console
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

## <a name="msturnping"></a><span data-ttu-id="434e6-473">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="434e6-473">MsTurnPing</span></span>
<span data-ttu-id="434e6-474"><a name="MsTurnPing"> </a></span><span class="sxs-lookup"><span data-stu-id="434e6-474"><a name="MsTurnPing"> </a></span></span>

<span data-ttu-id="434e6-475">La herramienta MSTurnPing permite a un administrador del software de comunicaciones de Skype empresarial Server 2015 comprobar el estado de los servidores que ejecutan el servidor perimetral de audio y vídeo y los servicios de autenticación de audio y vídeo, así como los servidores que ejecutan los servicios de directivas de ancho de banda en la topología.</span><span class="sxs-lookup"><span data-stu-id="434e6-475">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

### <a name="description"></a><span data-ttu-id="434e6-476">Descripción</span><span class="sxs-lookup"><span data-stu-id="434e6-476">Description</span></span>

<span data-ttu-id="434e6-477">La herramienta MSTurnPing permite a un administrador del software de comunicaciones de Skype empresarial Server 2015 comprobar el estado de los servidores que ejecutan el servidor perimetral de audio y vídeo y los servicios de autenticación de audio y vídeo, así como los servidores que ejecutan los servicios de directivas de ancho de banda en la topología.</span><span class="sxs-lookup"><span data-stu-id="434e6-477">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

<span data-ttu-id="434e6-478">La herramienta permite al administrador realizar las siguientes pruebas:</span><span class="sxs-lookup"><span data-stu-id="434e6-478">The tool allows the administrator to perform the following tests:</span></span>

1. <span data-ttu-id="434e6-479">Prueba del servidor perimetral a/V: la herramienta realiza pruebas en todos los servidores perimetrales A/V de la topología mediante el siguiente procedimiento:</span><span class="sxs-lookup"><span data-stu-id="434e6-479">A/V Edge Server test: The tool performs tests against all A/V Edge Servers in the topology by doing the following:</span></span>

   - <span data-ttu-id="434e6-480">Comprobar que el servicio de autenticación de audio y vídeo de Skype empresarial Server se ha iniciado y que puede emitir las credenciales correctas.</span><span class="sxs-lookup"><span data-stu-id="434e6-480">Verifying that the Skype for Business Server Audio/Video Authentication service is started and can issue proper credentials.</span></span>

   - <span data-ttu-id="434e6-481">Comprobando que el servicio perimetral de audio y vídeo de Skype empresarial Server se ha iniciado y que puede asignar correctamente los recursos en el servidor perimetral externo.</span><span class="sxs-lookup"><span data-stu-id="434e6-481">Verifying that the Skype for Business Server Audio/Video Edge service is started and can allocate the resources on the external edge successfully.</span></span>

2. <span data-ttu-id="434e6-482">Prueba del servicio de directiva de ancho de banda: la herramienta realiza pruebas en todos los servidores que ejecutan los servicios de directiva de ancho de banda de la topología haciendo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="434e6-482">Bandwidth Policy Service test: The tool performs tests against all the servers that are running the Bandwidth Policy Services in the topology by doing the following:</span></span>

   - <span data-ttu-id="434e6-483">Comprobar que el servicio de directiva de ancho de banda (autenticación) de Skype empresarial Server se ha iniciado y puede emitir las credenciales correctas.</span><span class="sxs-lookup"><span data-stu-id="434e6-483">Verifying that the Skype for Business Server Bandwidth Policy Service (Authentication) is started and can issue proper credentials.</span></span>

   - <span data-ttu-id="434e6-484">Comprobar que el servicio de directiva de ancho de banda (principal) de Skype empresarial Server se ha iniciado y puede realizar correctamente la comprobación del ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="434e6-484">Verifying that the Skype for Business Server Bandwidth Policy Service (Core) is started and can perform the bandwidth check successfully.</span></span>

<span data-ttu-id="434e6-485">Esta herramienta debe ejecutarse desde un equipo que forme parte de la topología y tenga instalado el almacén local.</span><span class="sxs-lookup"><span data-stu-id="434e6-485">This tool must be run from a computer that is part of the topology and has the local store installed.</span></span>

### <a name="output"></a><span data-ttu-id="434e6-486">Output</span><span class="sxs-lookup"><span data-stu-id="434e6-486">Output</span></span>

<span data-ttu-id="434e6-487">La herramienta genera los resultados de cada una de las operaciones.</span><span class="sxs-lookup"><span data-stu-id="434e6-487">The tool outputs the results of each of the operations.</span></span>

- <span data-ttu-id="434e6-488">Si se realiza la prueba **AudioVideoEdgeServer** , los resultados de la herramienta son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="434e6-488">If the **AudioVideoEdgeServer** test is performed, the tool outputs are the following:</span></span>

  - <span data-ttu-id="434e6-489">Los resultados de la prueba de los equipos que proporcionan el servicio de autenticación de audio y vídeo de Skype empresarial Server 2015 en la topología</span><span class="sxs-lookup"><span data-stu-id="434e6-489">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Authentication service in the topology</span></span>

  - <span data-ttu-id="434e6-490">Los resultados de la prueba de los equipos que proporcionan el servicio perimetral de audio y vídeo de Skype empresarial Server 2015 en la topología</span><span class="sxs-lookup"><span data-stu-id="434e6-490">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Edge service in the topology</span></span>

- <span data-ttu-id="434e6-491">Si se realiza la prueba **BandwidthPolicyServer** , los resultados de la herramienta son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="434e6-491">If the **BandwidthPolicyServer** test is performed, the tool outputs are the following:</span></span>

  - <span data-ttu-id="434e6-492">Los resultados de la prueba de los equipos que proporcionan el servicio de directiva de ancho de banda (autenticación) de Skype empresarial Server 2015 en la topología</span><span class="sxs-lookup"><span data-stu-id="434e6-492">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Authentication) in the topology</span></span>

  - <span data-ttu-id="434e6-493">Los resultados de la prueba de los equipos que proporcionan el servicio de directiva de ancho de banda (principal) de Skype empresarial Server 2015 en la topología</span><span class="sxs-lookup"><span data-stu-id="434e6-493">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Core) in the topology</span></span>

### <a name="requirements"></a><span data-ttu-id="434e6-494">Requisitos</span><span class="sxs-lookup"><span data-stu-id="434e6-494">Requirements</span></span>

- <span data-ttu-id="434e6-495">Esta herramienta debe ejecutarse desde un equipo que esté en la topología y que tenga el almacén local.</span><span class="sxs-lookup"><span data-stu-id="434e6-495">This tool must be run from a computer that is in the topology and that has the local store.</span></span>

- <span data-ttu-id="434e6-496">La herramienta debe ejecutarse como un administrador que tenga acceso al almacén local.</span><span class="sxs-lookup"><span data-stu-id="434e6-496">The tool must be run as an administrator who has access to the local store.</span></span>

### <a name="examples"></a><span data-ttu-id="434e6-497">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="434e6-497">Examples</span></span>

<span data-ttu-id="434e6-498">El siguiente es un ejemplo de la entrada de la herramienta.</span><span class="sxs-lookup"><span data-stu-id="434e6-498">The following is an example of the tool input.</span></span>

```console
MsTurnPing -ServerRole AudioVideoEdgeServer

MsTurnPing -ServerRole BandwidthPolicyServer
```

### <a name="summary"></a><span data-ttu-id="434e6-499">Resumen</span><span class="sxs-lookup"><span data-stu-id="434e6-499">Summary</span></span>

<span data-ttu-id="434e6-500">Esta herramienta puede ser un recurso valioso para los administradores de Skype empresarial Server 2015 que quieran comprobar el estado de los servidores que ejecutan los servicios de directivas de audio y vídeo y de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="434e6-500">This tool can be a valuable resource to Skype for Business Server 2015 administrators who want to check the status of the servers that are running audio/video and bandwidth policy services.</span></span>

## <a name="network-configuration-viewer"></a><span data-ttu-id="434e6-501">Visor de configuración de red</span><span class="sxs-lookup"><span data-stu-id="434e6-501">Network Configuration Viewer</span></span>
<span data-ttu-id="434e6-502"><a name="NCV"> </a></span><span class="sxs-lookup"><span data-stu-id="434e6-502"><a name="NCV"> </a></span></span>

<span data-ttu-id="434e6-503">Los administradores de software de comunicaciones de Skype empresarial Server 2015 pueden usar el visor de configuración de red para ver la topología de red de control de admisión de llamadas (CAC) para una empresa que se aprovisiona para permitir sesiones de comunicación en tiempo real, como llamadas de voz o vídeo basadas en la capacidad de ancho de banda especificada.</span><span class="sxs-lookup"><span data-stu-id="434e6-503">Network Configuration Viewer can be used by Skype for Business Server 2015 communications software administrators to view call admission control (CAC) network topology for an enterprise that is provisioned to allow real-time communication sessions, such as voice or video calls based on specified bandwidth capacity.</span></span> <span data-ttu-id="434e6-504">Los administradores de Skype empresarial Server 2015 definen directivas de CAC, que aplican los servicios de directivas de ancho de banda que se instalan con Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="434e6-504">Skype for Business Server 2015 administrators define CAC policies, which are enforced by the Bandwidth Policy services that are installed with Skype for Business Server 2015.</span></span>

### <a name="description"></a><span data-ttu-id="434e6-505">Descripción</span><span class="sxs-lookup"><span data-stu-id="434e6-505">Description</span></span>

<span data-ttu-id="434e6-506">El visor de configuración de red (NetworkConfigurationViewer. exe) permite a los administradores realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="434e6-506">Network Configuration Viewer (NetworkConfigurationViewer.exe) allows administrators to perform the following tasks:</span></span>

- <span data-ttu-id="434e6-507">Cargar y ver la topología de red de CAC de una implementación de Skype empresarial Server 2015 en formato gráfico.</span><span class="sxs-lookup"><span data-stu-id="434e6-507">Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format.</span></span>

- <span data-ttu-id="434e6-508">Cargar y ver la topología de red de CAC de un archivo de registro de servidor de directivas de ancho de banda en un formato gráfico.</span><span class="sxs-lookup"><span data-stu-id="434e6-508">Load and view CAC network topology from a Bandwidth Policy Server log file in a graphical format.</span></span>

- <span data-ttu-id="434e6-509">Guarde y almacene la topología de red de CAC en formato XML en el disco.</span><span class="sxs-lookup"><span data-stu-id="434e6-509">Save and store CAC network topology in an XML format on the disk.</span></span>

- <span data-ttu-id="434e6-510">Guarde y almacene el diagrama de topología de red de CAC en formato JPG o BMP.</span><span class="sxs-lookup"><span data-stu-id="434e6-510">Save and store CAC network topology diagram in JPG or BMP format.</span></span>

- <span data-ttu-id="434e6-511">Ver los datos de configuración de la topología de red de CAC.</span><span class="sxs-lookup"><span data-stu-id="434e6-511">View CAC network topology configuration data.</span></span>

- <span data-ttu-id="434e6-512">Ver la topología de red de CAC en un estilo de vista de árbol.</span><span class="sxs-lookup"><span data-stu-id="434e6-512">View CAC network topology in a tree-view style.</span></span>

- <span data-ttu-id="434e6-513">Defina los conectores personalizados para los vínculos de topología de red de CAC (por ejemplo, vínculos de sitio a región, de región a región y de sitio a sitio).</span><span class="sxs-lookup"><span data-stu-id="434e6-513">Define custom connectors for CAC network topology links (for example, site-to-region, region-to-region, and site-to-site links).</span></span>

- <span data-ttu-id="434e6-514">Ver información del sitio de la topología de red de CAC, información de región y directivas de ancho de banda aprovisionadas y vínculos de red.</span><span class="sxs-lookup"><span data-stu-id="434e6-514">View CAC network topology site information, region Information, and provisioned bandwidth policies and network links.</span></span>

### <a name="purpose"></a><span data-ttu-id="434e6-515">Finalidad</span><span class="sxs-lookup"><span data-stu-id="434e6-515">Purpose</span></span>

<span data-ttu-id="434e6-516">Ver los vínculos de topología de red CAC empresarial en una interfaz gráfica.</span><span class="sxs-lookup"><span data-stu-id="434e6-516">View enterprise CAC network topology links in a graphical interface.</span></span>

### <a name="examples"></a><span data-ttu-id="434e6-517">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="434e6-517">Examples</span></span>

 <span data-ttu-id="434e6-518">**Cargar y ver la topología de red de CAC de una implementación de Skype empresarial server 2015 en formato gráfico**: los administradores de Skype empresarial Server 2015 pueden cargar y ver la configuración de la topología de red de CAC en cualquier equipo de Skype empresarial Server 2015 mediante la opción de **descarga de configuración de red** , tal como se muestra en la figura siguiente.</span><span class="sxs-lookup"><span data-stu-id="434e6-518">**Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format**: Skype for Business Server 2015 administrators can load and view CAC network topology configuration on any Skype for Business Server 2015 computer by using the **Download Network Configuration** option as shown in the figure below.</span></span> <span data-ttu-id="434e6-519">La herramienta no podrá descargar ni ver dicha configuración cuando se implemente en un equipo que no tiene conectividad con el almacén de configuración de Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="434e6-519">The tool will fail to download or view such a configuration when deployed on a computer that does not have connectivity to the Skype for Business Server 2015 configuration store.</span></span>

![Descargar la configuración de red.](../media/Reskit_2012_Tools_Documentation_Image23.jpg)

 <span data-ttu-id="434e6-521">**Cargar y ver la topología de red de CAC de un archivo de registro de servidor de directivas de ancho de banda en formato gráfico:** Los servidores de directivas de ancho de banda de Skype empresarial Server 2015 guardan la topología de red de CAC como parte del mecanismo de registro en la ubicación del recurso compartido de archivos de Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="434e6-521">**Load and View CAC network topology from a Bandwidth Policy server log file in a graphical format:** Skype for Business Server 2015 Bandwidth Policy servers save the CAC network topology as a part of the logging mechanism under the Skype for Business Server 2015 file share location.</span></span> <span data-ttu-id="434e6-522">Los administradores de Skype empresarial Server 2015 pueden ver este archivo en formato gráfico con la opción **abrir configuración de red** , tal como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="434e6-522">Skype for Business Server 2015 administrators can view such a file in a graphical format by using the **Open Network Configuration** option as shown below.</span></span>

![Abrir un archivo de registro de servidor de directivas de ancho de banda.](../media/Reskit_2012_Tools_Documentation_Image24.jpg)

<span data-ttu-id="434e6-524">Guarde y almacene la topología de red de CAC en formato XML en el disco: Skype empresarial Server 2015 los administradores pueden guardar el archivo de configuración de la topología de red de CAC en formato XML con la opción **guardar una copia de la configuración de red** , tal como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="434e6-524">Save and store CAC network topology in an XML format on the disk: Skype for Business Server 2015 administrators can save the CAC network topology configuration file in an XML format by using the **Save a copy of Network Configuration** option as shown below.</span></span> <span data-ttu-id="434e6-525">El archivo de configuración guardado puede usarse sin conexión para fines de visualización gráfica.</span><span class="sxs-lookup"><span data-stu-id="434e6-525">The saved configuration file can then be used offline for graphical viewing purposes.</span></span>

![Guardar la configuración de red como un archivo XML.](../media/Reskit_2012_Tools_Documentation_Image25.jpg)

<span data-ttu-id="434e6-527">Guarde y almacene el diagrama de topología de red de CAC en formato JPG o BMP: Skype empresarial Server 2015 los administradores pueden guardar la configuración de la topología de red de CAC en formato gráfico (formatos de archivo JPG y BMP) mediante la opción **Guardar diagrama de configuración de red como imagen** , como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="434e6-527">Save and Store CAC network topology diagram in JPG or BMP format: Skype for Business Server 2015 administrators can save the CAC network topology configuration in a graphical format (JPG and BMP file formats) by using the **Save Network Configuration diagram as picture** option as shown below.</span></span>

![Guardar la configuración de red como una imagen.](../media/Reskit_2012_Tools_Documentation_Image26.jpg)

 <span data-ttu-id="434e6-529"><strong>Ver los datos de configuración de la topología de red de CAC:</strong> Los administradores de Skype empresarial Server 2015 pueden ver los datos de configuración de red relacionados, como las regiones de red, los sitios de red, los perfiles de ancho de banda y las direcciones IP de subred de sitio en formato de texto mediante la opción ver datos de configuración de red, tal como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="434e6-529"><strong>View CAC network topology configuration data:</strong>Skype for Business Server 2015 administrators can view related network configuration data such as network regions, network sites, bandwidth profiles, and site subnet IP addresses in a textual format by using the View Network Configuration data option as shown below.</span></span>

![Ver los datos de configuración de la red.](../media/Reskit_2012_Tools_Documentation_Image27.jpg)

 <span data-ttu-id="434e6-531">**Ver la topología de red de CAC en un estilo de vista de árbol:** Los administradores de Skype empresarial Server 2015 pueden ver los datos de configuración de red relacionados en un estilo de vista de árbol gráfico mediante el panel de control, en el lado izquierdo de la ventana de herramientas, tal como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="434e6-531">**View CAC network topology in a tree-view style:** Skype for Business Server 2015 administrators can view related network configuration data in a graphical tree view style by using the control panel on the left side of the tool window as shown below.</span></span>

![Ver los datos de configuración de red en una vista de árbol.](../media/Reskit_2012_Tools_Documentation_Image28.jpg)

 <span data-ttu-id="434e6-533">**Definir conectores personalizados para los vínculos de topología de red de CAC (como vínculos de sitio a región, de región a región y de sitio a sitio):** Los administradores de Skype empresarial Server 2015 pueden definir conectores gráficos personalizados para los vínculos WAN de configuración de red de CAC mediante la opción configuración, tal como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="434e6-533">**Define custom connectors for CAC network topology links (such as site-to-region, region-to-region, and site-to-site links):** Skype for Business Server 2015 administrators can define custom graphical connectors for CAC network configuration WAN links by using the Settings option as shown below.</span></span> <span data-ttu-id="434e6-534">Esto ayuda a diferenciar entre varios tipos de vínculos de red que se aprovisionan en la configuración de red.</span><span class="sxs-lookup"><span data-stu-id="434e6-534">This helps differentiate between various types of network links that are provisioned in the network configuration.</span></span>

![Herramientas](../media/Reskit_2012_Tools_Documentation_Image29.jpg)

 <span data-ttu-id="434e6-536">**Ver la información del sitio de la topología de red de CAC, información de región y directivas de ancho de banda aprovisionadas:** Los administradores de Skype empresarial Server 2015 pueden ver la información de la región de red CAC, la información del sitio y la información de aprovisionamiento de ancho de banda de CAC con las opciones que se muestran a continuación.</span><span class="sxs-lookup"><span data-stu-id="434e6-536">**View CAC network topology site information, region information, and provisioned bandwidth policies:** Skype for Business Server 2015 administrators can view related CAC network region information, site information, and CAC bandwidth provisioning information by using options shown below.</span></span> <span data-ttu-id="434e6-537">(Por ejemplo, haga clic en **información** en una región de red o un objeto de sitio de red).</span><span class="sxs-lookup"><span data-stu-id="434e6-537">(For example, click **Info** in a network region or network site object.)</span></span>

![Definir conectores personalizados para la red.](../media/Reskit_2012_Tools_Documentation_Image30.jpg)

### <a name="summary"></a><span data-ttu-id="434e6-539">Resumen</span><span class="sxs-lookup"><span data-stu-id="434e6-539">Summary</span></span>

<span data-ttu-id="434e6-540">Esta herramienta puede ser un recurso valioso para los administradores de Skype empresarial Server 2015 que quieran ver la topología de red de CAC para su implementación en un formato gráfico.</span><span class="sxs-lookup"><span data-stu-id="434e6-540">This tool can be a valuable resource to Skype for Business Server 2015 administrators who would like to view CAC network topology for their deployment in a graphical format.</span></span>

## <a name="response-group-agent-live"></a><span data-ttu-id="434e6-541">Response Group Agent Live</span><span class="sxs-lookup"><span data-stu-id="434e6-541">Response Group Agent Live</span></span>
<span data-ttu-id="434e6-542"><a name="RGAL"> </a></span><span class="sxs-lookup"><span data-stu-id="434e6-542"><a name="RGAL"> </a></span></span>

<span data-ttu-id="434e6-543">La aplicación de grupo de respuesta ofrece a los agentes la capacidad de tener acceso a información útil en tiempo real mediante su servicio Web integrado.</span><span class="sxs-lookup"><span data-stu-id="434e6-543">The Response Group application gives agents the ability to access useful real-time information using its built-in Web service.</span></span> <span data-ttu-id="434e6-544">Desafortunadamente, no hay ninguna vista gráfica de estos datos disponibles fuera de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="434e6-544">Unfortunately, no graphical view of this data is available outside the application.</span></span> <span data-ttu-id="434e6-545">La herramienta de kit de recursos Live Response Agent Live Report resuelve este problema proporcionando una forma sencilla y gráfica para obtener acceso a esta información, mejorada con información de software de comunicaciones de Skype empresarial en tiempo real, como la presencia de otros agentes.</span><span class="sxs-lookup"><span data-stu-id="434e6-545">The Response Group Agent Live Resource Kit tool solves this issue by providing a simple and graphical way to access this information, enhanced with real-time Skype for Business communications software information such as the presence of other agents.</span></span>

### <a name="description"></a><span data-ttu-id="434e6-546">Descripción</span><span class="sxs-lookup"><span data-stu-id="434e6-546">Description</span></span>

<span data-ttu-id="434e6-547">Response Group Agent Live es una aplicación de Windows que proporciona la funcionalidad de inicio y cierre de sesión, así como información en tiempo real (como la pertenencia a grupos y el número actual de llamadas) a los agentes del grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="434e6-547">Response Group Agent Live is a Windows application that provides sign-in and sign-out functionality and some real-time information (such as group membership and current number of calls) to Response Group agents.</span></span> <span data-ttu-id="434e6-548">Está diseñada para ser una versión mejorada de la página grupos de agentes (accesible desde Skype empresarial).</span><span class="sxs-lookup"><span data-stu-id="434e6-548">It is meant to be an enhanced version of the Agent Groups page (accessible from Skype for Business.</span></span>

### <a name="purpose"></a><span data-ttu-id="434e6-549">Finalidad</span><span class="sxs-lookup"><span data-stu-id="434e6-549">Purpose</span></span>

<span data-ttu-id="434e6-550">La aplicación de grupo de respuesta pone en cola las llamadas entrantes y, a continuación, las enruta a los grupos de agentes.</span><span class="sxs-lookup"><span data-stu-id="434e6-550">The Response Group application queues incoming calls, and then routes them to agent groups.</span></span> <span data-ttu-id="434e6-551">Para tomar decisiones informadas sobre las llamadas al servicio, los agentes pueden obtener acceso a información en tiempo real sobre sus grupos de agentes, como qué otros agentes están disponibles y cuántas llamadas están esperando en cada cola.</span><span class="sxs-lookup"><span data-stu-id="434e6-551">To make informed decisions about which calls to service, agents can access real-time information about their agent groups, such as what other agents are available and how many calls are waiting in each queue.</span></span> <span data-ttu-id="434e6-552">Esta información, inicialmente accesible solo a través del servicio de grupo de respuesta, está disponible de forma intuitiva mediante Response Group Agent Live.</span><span class="sxs-lookup"><span data-stu-id="434e6-552">This information, initially accessible only through the Response Group service, is made available in an intuitive way by Response Group Agent Live.</span></span>

#### <a name="features"></a><span data-ttu-id="434e6-553">Características</span><span class="sxs-lookup"><span data-stu-id="434e6-553">Features</span></span>

<span data-ttu-id="434e6-554">La herramienta Response Group Agent Live se basa en el servicio de grupo de respuesta y el SDK de Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="434e6-554">The Response Group Agent Live tool is built on the Response Group service and the Skype for Business Server 2015 SDK.</span></span> <span data-ttu-id="434e6-555">Proporciona agentes de grupo de respuesta información y capacidades que están disponibles en el servicio de grupo de respuesta (como la pertenencia a grupos, la presencia de otros agentes y el número de llamadas en espera).</span><span class="sxs-lookup"><span data-stu-id="434e6-555">It provides Response Group agents the information and capabilities that are available from the Response Group service (such as group membership, presence of other agents, and number of waiting calls).</span></span>

<span data-ttu-id="434e6-556">La ilustración siguiente muestra la interfaz principal de Response Group Agent Live.</span><span class="sxs-lookup"><span data-stu-id="434e6-556">The figure below illustrates the main interface of Response Group Agent Live.</span></span>

![La herramienta Response Group Agent Live.](../media/Reskit_2012_Tools_Documentation_Image37.JPG)

<span data-ttu-id="434e6-558">Las siguientes tres características principales están disponibles para los agentes en Response Group Agent Live:</span><span class="sxs-lookup"><span data-stu-id="434e6-558">The following three main features are available for agents in Response Group Agent Live:</span></span>

- <span data-ttu-id="434e6-559">**Iniciar/cerrar sesión:** Al contrario que la página grupos de agentes (accesible desde Skype empresarial Server 2015), el agente de grupo de respuesta Live permite que solo los agentes inicien o salgan de todos los grupos de agentes a la vez.</span><span class="sxs-lookup"><span data-stu-id="434e6-559">**Sign-in/out:** Contrary to the Agent Groups page (accessible from Skype for Business Server 2015), Response Group Agent Live allows only agents to sign-in or out of all agent groups at once.</span></span> <span data-ttu-id="434e6-560">Esta aplicación proporciona tres métodos rápidos para que los agentes inicien o cierren sesión:</span><span class="sxs-lookup"><span data-stu-id="434e6-560">This application provides three quick ways for agents to sign in or out:</span></span>

  - <span data-ttu-id="434e6-561">Haga clic en los botones de inicio y cierre de sesión (verde y rojo) dentro de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="434e6-561">Click the Sign-in/out (green and red) buttons within the application.</span></span>

  - <span data-ttu-id="434e6-562">Haga clic con el botón derecho en el icono de la bandeja del sistema y seleccione iniciar sesión o cerrar sesión.</span><span class="sxs-lookup"><span data-stu-id="434e6-562">Right-click the system tray icon, and select sign in or sign out.</span></span>

  - <span data-ttu-id="434e6-563">Usar métodos abreviados de teclado configurables.</span><span class="sxs-lookup"><span data-stu-id="434e6-563">Using configurable keyboard shortcuts.</span></span>

- <span data-ttu-id="434e6-564">**Pertenencia a grupos:** Cuando se selecciona un grupo de agentes, Response Group Agent Live muestra la lista de agentes de este grupo en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="434e6-564">**Group membership:** When an agent group is selected, Response Group Agent Live displays the list of agents in this group in the right pane.</span></span> <span data-ttu-id="434e6-565">Si Skype empresarial Server 2015 se está ejecutando en el mismo equipo que esta aplicación, la información de presencia y la tarjeta de contacto se muestran en el Group Response Agent Live.</span><span class="sxs-lookup"><span data-stu-id="434e6-565">If Skype for Business Server 2015 is running on the same computer as this application, presence information and the contact card are displayed in the Response Group Agent Live.</span></span> <span data-ttu-id="434e6-566">Los agentes pueden enviar un mensaje instantáneo o llamar a otros agentes directamente desde allí.</span><span class="sxs-lookup"><span data-stu-id="434e6-566">Agents can send an IM or call other agents directly from there.</span></span>

- <span data-ttu-id="434e6-567">**Estadísticas en tiempo real:** Response Group Agent Live proporciona estadísticas en tiempo real para todos los grupos de agentes.</span><span class="sxs-lookup"><span data-stu-id="434e6-567">**Real-time statistics:** Response Group Agent Live provides real-time statistics for all agent groups.</span></span> <span data-ttu-id="434e6-568">La frecuencia de actualización es un minuto.</span><span class="sxs-lookup"><span data-stu-id="434e6-568">The update frequency is one minute.</span></span> <span data-ttu-id="434e6-569">Cuando un grupo de respuesta responde a una llamada, se agrega un indicador visual junto al nombre del grupo con el número actual de llamadas en cola.</span><span class="sxs-lookup"><span data-stu-id="434e6-569">When a call is answered by a Response Group, a visual indicator is added next to the group name with the current number of queued calls.</span></span> <span data-ttu-id="434e6-570">Al pausar el puntero sobre un grupo, también se muestra el tiempo de espera más largo.</span><span class="sxs-lookup"><span data-stu-id="434e6-570">Pausing the pointer over a group also displays the longest waiting time.</span></span>

### <a name="requirements"></a><span data-ttu-id="434e6-571">Requisitos</span><span class="sxs-lookup"><span data-stu-id="434e6-571">Requirements</span></span>

<span data-ttu-id="434e6-572">Response Group Agent Live requiere .NET Framework 4,0.</span><span class="sxs-lookup"><span data-stu-id="434e6-572">Response Group Agent Live requires the .NET Framework 4.0.</span></span> <span data-ttu-id="434e6-573">Además, para aprovechar las características de presencia y tarjeta de contacto, Skype empresarial debe instalarse de forma local (y estar en ejecución).</span><span class="sxs-lookup"><span data-stu-id="434e6-573">In addition, to take advantage of the presence and contact card features, Skype for Business must be installed locally (and be running).</span></span>

#### <a name="configuration"></a><span data-ttu-id="434e6-574">Configuración</span><span class="sxs-lookup"><span data-stu-id="434e6-574">Configuration</span></span>

<span data-ttu-id="434e6-575">Response Group Agent Live puede personalizarse según las preferencias individuales mediante el cuadro de diálogo Opciones de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="434e6-575">Response Group Agent Live can be customized to individual preferences by using the Options dialog box in the application.</span></span> <span data-ttu-id="434e6-576">Además, el administrador puede definir la dirección de host predeterminada editando directamente la propiedad defaultHostAddress del archivo RGAgentLive. exe. config.</span><span class="sxs-lookup"><span data-stu-id="434e6-576">In addition, the administrator can define the default host address by editing directly the defaultHostAddress property of the RGAgentLive.exe.config file.</span></span>

<span data-ttu-id="434e6-577">La ilustración siguiente muestra el cuadro de diálogo Opciones que los agentes pueden usar para configurar las teclas de acceso directo y dirección de host.</span><span class="sxs-lookup"><span data-stu-id="434e6-577">The figure below illustrates the Options dialog box that agents can use to configure the host address and shortcut keys.</span></span> <span data-ttu-id="434e6-578">Para obtener acceso a este cuadro de diálogo, haga clic en el botón Opciones de la parte superior derecha de la interfaz principal.</span><span class="sxs-lookup"><span data-stu-id="434e6-578">This dialog is accessed by clicking the Options button on the top right of the main interface.</span></span>

![El cuadro de diálogo Opciones del agente de respuesta dinámica del grupo de respuesta.](../media/Reskit_2012_Tools_Documentation_Image38.JPG)

<span data-ttu-id="434e6-580">Las siguientes tres opciones de configuración distintas se pueden personalizar en la configuración de agente de grupo de respuesta:</span><span class="sxs-lookup"><span data-stu-id="434e6-580">The following three different settings can be customized in the Response Group Agent Live configuration:</span></span>

- <span data-ttu-id="434e6-581">Dirección de host: suele ser el FQDN del grupo de servidores web que pertenece al grupo principal del agente.</span><span class="sxs-lookup"><span data-stu-id="434e6-581">Host address: This is typically the web pool FQDN belonging to the agent's home pool.</span></span> <span data-ttu-id="434e6-582">La dirección exacta del servicio del grupo de respuesta se deriva automáticamente en segundo plano a partir de esta información (anexando la ruta de acceso correcta después del host).</span><span class="sxs-lookup"><span data-stu-id="434e6-582">The exact Response Group service address is automatically derived in the background from this information (by appending the right path after the host).</span></span>

- <span data-ttu-id="434e6-583">Accesos directos: los métodos abreviados exactos para iniciar y cerrar sesión pueden personalizarse.</span><span class="sxs-lookup"><span data-stu-id="434e6-583">Shortcuts: The exact shortcuts to sign-in/out can be customized.</span></span> <span data-ttu-id="434e6-584">La única limitación es que ambos métodos abreviados deben contener la tecla del logotipo de Windows (además de, al menos, otra tecla).</span><span class="sxs-lookup"><span data-stu-id="434e6-584">The only limitation is that both shortcuts must contain the "Windows Logo" key (in addition to at least another key).</span></span>

- <span data-ttu-id="434e6-585">Iniciar con Windows: la aplicación se puede configurar para iniciarse automáticamente con Windows.</span><span class="sxs-lookup"><span data-stu-id="434e6-585">Start with Windows: The application can be configured to start automatically with Windows.</span></span>

### <a name="examples"></a><span data-ttu-id="434e6-586">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="434e6-586">Examples</span></span>

<span data-ttu-id="434e6-587">En la siguiente figura se muestra cómo llamar o enviar un mensaje instantáneo a otro agente haciendo clic con el botón secundario en el contacto en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="434e6-587">The figure below illustrates how to call or send an IM to another agent by right-clicking the contact in the right pane.</span></span>

![Hacer una llamada o enviar un mensaje instantáneo.](../media/Reskit_2012_Tools_Documentation_Image39.JPG)

<span data-ttu-id="434e6-589">La ilustración siguiente muestra cómo Response Group Agent Live muestra el número actual de llamadas en la cola y el tiempo de espera más largo entre todas estas llamadas entrantes.</span><span class="sxs-lookup"><span data-stu-id="434e6-589">The figure below illustrates how Response Group Agent Live displays the current number of calls in the queue and the longest waiting time among all these incoming calls.</span></span>

![Ver información de cola.](../media/Reskit_2012_Tools_Documentation_Image40.JPG)

### <a name="summary"></a><span data-ttu-id="434e6-591">Resumen</span><span class="sxs-lookup"><span data-stu-id="434e6-591">Summary</span></span>

<span data-ttu-id="434e6-592">La rapidez en el inicio y el cierre de sesión, la pertenencia a grupos y las estadísticas básicas en tiempo real son características interesantes del agente de grupo de respuesta que solo están disponibles fuera de la aplicación desde el servicio de grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="434e6-592">Fast sign-in and sign-out, group membership, and basic real-time statistics are interesting Response Group agent features that are only available outside the application from the Response Group service.</span></span> <span data-ttu-id="434e6-593">Con la herramienta del kit de recursos del agente de grupo de respuesta Live, los administradores de Skype empresarial Server 2015 pueden proporcionar a sus agentes una aplicación de Windows que les permita realizar tareas de una manera gráfica y rápida.</span><span class="sxs-lookup"><span data-stu-id="434e6-593">With the Response Group Agent Live Resource Kit tool, Skype for Business Server 2015 administrators can provide their agents with a Windows application that allows them to perform tasks in a faster and graphical way.</span></span>

## <a name="sefautil"></a><span data-ttu-id="434e6-594">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="434e6-594">SEFAUtil</span></span>
<span data-ttu-id="434e6-595"><a name="SEFAUtil"> </a></span><span class="sxs-lookup"><span data-stu-id="434e6-595"><a name="SEFAUtil"> </a></span></span>

<span data-ttu-id="434e6-596">SEFAUtil (la activación de características de extensión secundaria) es una herramienta de línea de comandos que permite a los administradores de software de comunicaciones de Skype empresarial Server 2015 y a los agentes de asistencia técnica configurar la llamada delegada, el desvío de llamadas, las llamadas simultáneas configuración de llamada de equipo y recogida de llamadas de grupo en nombre de un usuario de Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="434e6-596">SEFAUtil (secondary extension feature activation) is a command-line tool that enables Skype for Business Server 2015 communications software administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="434e6-597">La herramienta también permite a los administradores consultar la configuración de enrutamiento de llamadas publicada para un usuario en particular. La herramienta SEFAUtil permite al administrador habilitar/deshabilitar/modificar el desvío de llamadas o las llamadas simultáneas en nombre del usuario.</span><span class="sxs-lookup"><span data-stu-id="434e6-597">The tool also allows administrators to query the call-routing settings that are published for a particular user.The SEFAUtil tool allows the administrator to enable/disable/modify call forwarding or simultaneously ringing on behalf of the user.</span></span> <span data-ttu-id="434e6-598">El administrador puede especificar el destino (en forma de URI de SIP) o usar un destino ya publicado por el usuario.</span><span class="sxs-lookup"><span data-stu-id="434e6-598">The administrator can specify the target (in the form of a SIP URI) or use a target that has already been published by the user.</span></span> <span data-ttu-id="434e6-599">Esta herramienta también permite a los administradores agregar o quitar delegados o miembros del grupo de llamada de equipo en nombre del usuario. Esta herramienta se basa en la API administrada de comunicaciones unificadas de Microsoft (UCMA) 3,0 y requiere que los administradores creen una aplicación de confianza en el almacén de administración central para SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="434e6-599">This tool also allows administrators to add or remove delegates or team-call group members on behalf of the user.This tool is built on Microsoft Unified Communications Managed API (UCMA) 3.0 and requires that administrators create a trusted application in the Central Management store for SEFAUtil.</span></span>

<span data-ttu-id="434e6-600">SEFAUtil (activación de características de extensión secundaria) permite a los administradores y los agentes del Departamento de soporte técnico de Skype empresarial Server 2015 configurar las llamadas delegadas, el desvío de llamadas, las llamadas simultáneas, la configuración de llamada de equipo y la atención de llamadas grupales en nombre de un cliente de Skype para el usuario de Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="434e6-600">SEFAUtil (secondary extension feature activation) enables Skype for Business Server 2015 administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="434e6-601">Esta herramienta también permite a los administradores consultar la configuración de enrutamiento de llamadas publicada para un usuario en particular.</span><span class="sxs-lookup"><span data-stu-id="434e6-601">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span>

### <a name="description"></a><span data-ttu-id="434e6-602">Descripción</span><span class="sxs-lookup"><span data-stu-id="434e6-602">Description</span></span>

<span data-ttu-id="434e6-603">La versión actual de SEFAUtil es solo una herramienta de línea de comandos; no hay ninguna interfaz gráfica de usuario compatible.</span><span class="sxs-lookup"><span data-stu-id="434e6-603">The current version of SEFAUtil is only a command-line tool; there is no supporting graphical user interface.</span></span> <span data-ttu-id="434e6-604">Esta herramienta se basa en la API administrada de comunicaciones unificadas de Microsoft (UCMA) 3,0.</span><span class="sxs-lookup"><span data-stu-id="434e6-604">This tool is based on Microsoft Unified Communications Managed API (UCMA) 3.0.</span></span> <span data-ttu-id="434e6-605">Las características de esta herramienta permiten que los administradores y los agentes del Departamento de soporte técnico hagan lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="434e6-605">The features in this tool allow administrators and helpdesk agents to do the following:</span></span>

- <span data-ttu-id="434e6-606">Ver toda la configuración de enrutamiento de llamadas de un usuario (incluye el desvío de llamadas, la delegación, las llamadas simultáneas, la llamada de equipo y la atención de llamadas de grupo)</span><span class="sxs-lookup"><span data-stu-id="434e6-606">View all call routing settings for a user (includes call-forwarding, delegation, simultaneous ringing, team-call and group call pickup)</span></span>

- <span data-ttu-id="434e6-607">Habilitar/deshabilitar/modificar la configuración de desvío de llamadas (incluye el destino y el temporizador sin respuesta)</span><span class="sxs-lookup"><span data-stu-id="434e6-607">Enable/disable/modify call-forwarding setting (includes destination and no-answer timer)</span></span>

- <span data-ttu-id="434e6-608">Habilitar/deshabilitar/modificar las configuraciones inmediatas de reenvío de llamadas</span><span class="sxs-lookup"><span data-stu-id="434e6-608">Enable/disable/modify call-forwarding immediate configurations</span></span>

- <span data-ttu-id="434e6-609">Habilitar/deshabilitar/modificar la configuración de la delegación</span><span class="sxs-lookup"><span data-stu-id="434e6-609">Enable/disable/modify delegation settings</span></span>

- <span data-ttu-id="434e6-610">Habilitar/deshabilitar/modificar la configuración de grupo de llamada de equipo</span><span class="sxs-lookup"><span data-stu-id="434e6-610">Enable/disable/modify team-call group settings</span></span>

    > [!NOTE]
    > <span data-ttu-id="434e6-611">New in Skype for Business Server 2015 SEFAUtil Tool</span><span class="sxs-lookup"><span data-stu-id="434e6-611">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

- <span data-ttu-id="434e6-612">Habilitar/deshabilitar/modificar la configuración de llamadas simultáneas (incluye el destino)</span><span class="sxs-lookup"><span data-stu-id="434e6-612">Enable/disable/modify simultaneous ringing settings (includes destination)</span></span>

    > [!NOTE]
    > <span data-ttu-id="434e6-613">New in Skype for Business Server 2015 SEFAUtil Tool</span><span class="sxs-lookup"><span data-stu-id="434e6-613">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

- <span data-ttu-id="434e6-614">Habilitar/deshabilitar/modificar la configuración de RECALL de llamadas de grupo</span><span class="sxs-lookup"><span data-stu-id="434e6-614">Enable/disable/modify group call pickup settings</span></span>

    > [!CAUTION]
    > <span data-ttu-id="434e6-615">New in Skype for Business Server 2015 SEFAUtil Tool</span><span class="sxs-lookup"><span data-stu-id="434e6-615">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

<span data-ttu-id="434e6-616">Esta herramienta tiene las siguientes limitaciones:</span><span class="sxs-lookup"><span data-stu-id="434e6-616">This tool has the following limitations:</span></span>

- <span data-ttu-id="434e6-617">Compatible solo para usuarios hospedados en un grupo de servidores de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="434e6-617">Supported only for users homed in a Skype for Business Server pool</span></span>

- <span data-ttu-id="434e6-618">No se admite la edición en masa de la configuración de enrutamiento de llamadas para varios usuarios</span><span class="sxs-lookup"><span data-stu-id="434e6-618">Bulk-edit of call routing settings for several users is not supported</span></span>

### <a name="output"></a><span data-ttu-id="434e6-619">Output</span><span class="sxs-lookup"><span data-stu-id="434e6-619">Output</span></span>

<span data-ttu-id="434e6-620">La versión actual de esta herramienta proporciona resultados sólo en la ventana del símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="434e6-620">The current version of this tool provides output only in the Command Prompt window.</span></span> <span data-ttu-id="434e6-621">Para obtener más información, vea la sección ejemplos más adelante en este documento.</span><span class="sxs-lookup"><span data-stu-id="434e6-621">For details, see the Examples section later in this document.</span></span>

### <a name="purpose"></a><span data-ttu-id="434e6-622">Finalidad</span><span class="sxs-lookup"><span data-stu-id="434e6-622">Purpose</span></span>

<span data-ttu-id="434e6-623">A continuación se muestran algunos de los escenarios clave en los que se puede usar esta herramienta:</span><span class="sxs-lookup"><span data-stu-id="434e6-623">Following are some of the key scenarios where this tool may be used:</span></span>

- <span data-ttu-id="434e6-624">Bob es un ejecutivo y se ha trasladado a la telefonía de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="434e6-624">Bob is an executive and has been moved to Skype for Business Server telephony.</span></span> <span data-ttu-id="434e6-625">Ha delegado en su sistema PBX existente.</span><span class="sxs-lookup"><span data-stu-id="434e6-625">He has delegation on his existing PBX system.</span></span> <span data-ttu-id="434e6-626">Como parte de la migración a Skype empresarial Server 2015, el administrador puede configurar el enrutamiento de Bob para reflejar su configuración de delegación preexistente.</span><span class="sxs-lookup"><span data-stu-id="434e6-626">As part of the move to Skype for Business Server 2015, the administrator is able to configure Bob's routing to reflect his pre-existing delegation configuration.</span></span>

- <span data-ttu-id="434e6-627">Alicia está viajando y se da cuenta de que espera una llamada importante de uno de sus clientes.</span><span class="sxs-lookup"><span data-stu-id="434e6-627">Alice is travelling and realizes that she is expecting an important call from one of her customers.</span></span> <span data-ttu-id="434e6-628">Sin embargo, se encuentra en un hotel y no tiene acceso a un equipo.</span><span class="sxs-lookup"><span data-stu-id="434e6-628">However, she is in a hotel and has no access to a computer.</span></span> <span data-ttu-id="434e6-629">Llama al Departamento de soporte técnico y solicita que se reenvíen a su número de teléfono móvil todas las llamadas realizadas a su número de trabajo.</span><span class="sxs-lookup"><span data-stu-id="434e6-629">She calls the helpdesk and requests that they forward to her mobile number all the calls made to her work number.</span></span> <span data-ttu-id="434e6-630">El personal del Departamento de soporte técnico puede realizar la configuración en su nombre.</span><span class="sxs-lookup"><span data-stu-id="434e6-630">The helpdesk personnel are able to do the configuration on her behalf.</span></span>

- <span data-ttu-id="434e6-631">Las llamadas de Joe a su número de trabajo van a su correo de voz móvil siempre que esté en el trabajo; sin embargo, las cosas parecen funcionar correctamente en la mayoría de las demás ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="434e6-631">Joe's calls to his work number are going to his mobile voicemail whenever he is at work; however, things appear to be working correctly in most other locations.</span></span> <span data-ttu-id="434e6-632">El técnico del Departamento de soporte técnico puede ver la configuración de enrutamiento de Joe y detecta que José ha configurado las llamadas simultáneas a su teléfono móvil.</span><span class="sxs-lookup"><span data-stu-id="434e6-632">The helpdesk technician is able to view Joe's routing configuration and discovers that Joe has simultaneous ringing configured to his mobile phone.</span></span> <span data-ttu-id="434e6-633">El técnico pregunta a Joe sobre la cobertura móvil en su oficina y puede determinar que la regla de timbre simultáneo es lo que está causando que las llamadas se desplazan al correo de voz móvil de Joe cuando su cobertura de red es deficiente.</span><span class="sxs-lookup"><span data-stu-id="434e6-633">The technician asks Joe about the mobile coverage at his office and is able to determine that the simultaneous ringing rule is what is causing the calls to go to Joe's mobile voicemail when his network coverage is poor.</span></span>

- <span data-ttu-id="434e6-634">Mike es un nuevo empleado de Contoso y se une a un nuevo equipo en el que todos los miembros están configurados para la llamada de equipo, cuando se habilitan para Skype empresarial Server 2015, el administrador puede establecer la configuración del grupo de llamada de equipo para incluir a todos los nuevos miembros del equipo. Además, el administrador agrega Mike como miembro del grupo de llamada de equipo para cada uno de los miembros de su equipo.</span><span class="sxs-lookup"><span data-stu-id="434e6-634">Mike is a new employee at Contoso and he's joining a new team on which all members are configured for team-call, when being enabled for Skype for Business Server 2015, the administrator is able to set his team-call group settings to include all his new team members, additionally, the administrator adds Mike as a team-call group member for each of the members in his team.</span></span>

- <span data-ttu-id="434e6-635">Una práctica de servicio al cliente en el Departamento de recursos humanos de Contoso es proporcionar servicio personal para todos los autores de llamadas desde la primera llamada.</span><span class="sxs-lookup"><span data-stu-id="434e6-635">A customer service practice in the human resources department at Contoso is to provide personal service for all callers since the first call.</span></span> <span data-ttu-id="434e6-636">Dado que todos los miembros del Departamento se encuentran muy cercanos entre sí, tener todos los teléfonos que suenen al mismo tiempo con la llamada de equipo es muy disruptiva para el equipo.</span><span class="sxs-lookup"><span data-stu-id="434e6-636">Given that all members of the department sit very close to each other, having all phones ringing at the same time with team-call is very disruptive for the team.</span></span> <span data-ttu-id="434e6-637">Para proporcionar el mejor servicio sin interrumpir a los miembros del equipo, el administrador de Skype empresarial Server 2015 aprovecha la capacidad de llamada de grupo.</span><span class="sxs-lookup"><span data-stu-id="434e6-637">To provide the best service without disrupting the team members, the Skype for Business Server 2015 administrator takes advantage of the Group Call Pickup capability.</span></span> <span data-ttu-id="434e6-638">El administrador agrega todos los miembros del Departamento a un grupo de recogida y se comunica con el número de grupo de recogida del Departamento.</span><span class="sxs-lookup"><span data-stu-id="434e6-638">The administrator adds all department members to a pickup group and communicates to the department the pickup group number.</span></span> <span data-ttu-id="434e6-639">Cuando Samantha no está en su escritorio, Joe detecta su timbre telefónico y continúa respondiendo a la llamada desde su escritorio.</span><span class="sxs-lookup"><span data-stu-id="434e6-639">When Samantha is absent from her desk, Joe notices her phone ringing and he proceeds to answer the call from his desk.</span></span>

### <a name="requirements"></a><span data-ttu-id="434e6-640">Requisitos</span><span class="sxs-lookup"><span data-stu-id="434e6-640">Requirements</span></span>

<span data-ttu-id="434e6-641">La herramienta SEFAUtil solo puede ejecutarse en un equipo que forme parte de un grupo de aplicaciones de confianza.</span><span class="sxs-lookup"><span data-stu-id="434e6-641">The SEFAUtil tool can be run only on a computer that is a part of a Trusted Application Pool.</span></span> <span data-ttu-id="434e6-642">UCMA 3,0 debe estar instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="434e6-642">UCMA 3.0 must be installed on that computer.</span></span> <span data-ttu-id="434e6-643">Para ejecutar la herramienta, se debe crear una nueva aplicación de confianza con el identificador de la aplicación SEFAUtil en ese grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="434e6-643">To run the tool, a new Trusted Application with the SEFAUtil application ID must be created on that pool.</span></span>

### <a name="creating-a-new-trusted-application-for-the-sefautil-tool"></a><span data-ttu-id="434e6-644">Creación de una nueva aplicación de confianza para la herramienta SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="434e6-644">Creating a new Trusted Application for the SEFAUtil tool</span></span>

1. <span data-ttu-id="434e6-645">La herramienta SEFAUTil solo puede ejecutarse en un equipo que forme parte de un grupo de aplicaciones de confianza.</span><span class="sxs-lookup"><span data-stu-id="434e6-645">The SEFAUTil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="434e6-646">Si es necesario, puede Agregar un grupo de servidores como un nuevo grupo de aplicaciones de confianza mediante el shell de administración de Skype empresarial Server con el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="434e6-646">If needed, adding a pool as a new trusted application pool can be done via the Skype for Business Server Management Shell with the following cmdlet:</span></span>

   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

    > [!NOTE]
    > <span data-ttu-id="434e6-647">UCMA 3,0 debe instalarse en cualquier equipo que se use para ejecutar la herramienta SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="434e6-647">UCMA 3.0 must be installed on any computer that will be used to run the SEFAUtil tool.</span></span>

2. <span data-ttu-id="434e6-648">Una aplicación de confianza debe definirse en la topología de la herramienta SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="434e6-648">A trusted application needs to be defined in the topology for the SEFAUtil tool.</span></span> <span data-ttu-id="434e6-649">Para definir SEFAUtil como una nueva aplicación de confianza, use el shell de administración de Skype empresarial Server y ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="434e6-649">To define SEFAUtil as a new trusted application, use the Skype for Business Server Management Shell and execute the following cmdlet:</span></span>

   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN> -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="434e6-650">Si es necesario, se puede usar un puerto diferente.</span><span class="sxs-lookup"><span data-stu-id="434e6-650">A different port can be used if needed.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="434e6-651">FQDN del grupo de servidores: el FQDN del servidor o grupo de servidores que va a hospedar la aplicación de SEFAUtil (normalmente un servidor front-end de Skype empresarial > o grupo de servidores).</span><span class="sxs-lookup"><span data-stu-id="434e6-651">Pool FQDN: The FQDN of the server or pool that will host the SEFAUtil application (usually a Skype for Business Front End server     > or pool).</span></span>
    > <span data-ttu-id="434e6-652">FQDN del registrador de grupo de servidores: el FQDN del servidor front-end o grupo de servidores front-end de Skype empresarial asociado con este grupo de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="434e6-652">Pool Registrar FQDN: The FQDN of the Skype for Business Front End server or pool associated with this application pool.</span></span>
    > <span data-ttu-id="434e6-653">Sitio de Grupo: el identificador de sitio del sitio en el que se hospeda este grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="434e6-653">Pool Site: The Site ID of the site on which this pool is homed.</span></span>

3. <span data-ttu-id="434e6-654">Los cambios en la topología deben estar habilitados.</span><span class="sxs-lookup"><span data-stu-id="434e6-654">The topology changes need to be enabled.</span></span> <span data-ttu-id="434e6-655">La habilitación de los cambios en la topología se puede realizar mediante el shell de administración de Skype empresarial Server ejecutando el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="434e6-655">Enabling the topology changes can be done via the Skype for Business Server Management Shell by executing the following cmdlet:</span></span>

   ```powershell
   Enable-CsToplogy
   ```

4. <span data-ttu-id="434e6-656">Si es necesario, instale las herramientas del kit de recursos de Skype empresarial Server 2015 en el servidor que se usará para ejecutar la herramienta SEFAUtil (el servidor debe formar parte de un grupo de aplicaciones de confianza).</span><span class="sxs-lookup"><span data-stu-id="434e6-656">If needed, install the Skype for Business Server 2015 Resource Kit Tools in the server that will be used to run the SEFAUtil tool (the server must be part of a trusted application pool).</span></span>

5. <span data-ttu-id="434e6-657">Compruebe que la SEFAUtil se está ejecutando correctamente.</span><span class="sxs-lookup"><span data-stu-id="434e6-657">Verify the SEFAUtil is running correctly.</span></span> <span data-ttu-id="434e6-658">Para ello, ejecute la herramienta desde un símbolo del sistema de Windows con privilegios de administrador para mostrar la configuración de desvío de llamadas de un usuario en la implementación.</span><span class="sxs-lookup"><span data-stu-id="434e6-658">To do this, run the tool from a windows command prompt with administrator privileges to display the call forwarding settings of a user in the deployment.</span></span> <span data-ttu-id="434e6-659">De forma predeterminada, la herramienta se encontrará en: ". ..\Archivos de Files\Skype para empresas Server 2015 \ reskit".</span><span class="sxs-lookup"><span data-stu-id="434e6-659">By default the tool will be located in: "…\Program Files\Skype for Business Server 2015\Reskit".</span></span> <span data-ttu-id="434e6-660">Para mostrar la configuración de desvío de llamadas de un usuario, use el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="434e6-660">To display the call forwarding settings of a user, use the following command:</span></span>

   ```console
   SEFAUtil.exe <user SIP address> /server:<Skype for Business Server/Pool FQDN>
   ```

    <span data-ttu-id="434e6-661">Se debe mostrar la configuración de desvío de llamadas del usuario.</span><span class="sxs-lookup"><span data-stu-id="434e6-661">The call forwarding settings of the user should be displayed.</span></span>

#### <a name="group-call-pickup"></a><span data-ttu-id="434e6-662">Recogida de llamadas grupales</span><span class="sxs-lookup"><span data-stu-id="434e6-662">Group Call Pickup</span></span>

<span data-ttu-id="434e6-663">La recogida de llamadas de grupo requiere una configuración adicional en Skype empresarial Server 2015 para que la capacidad esté completamente habilitada.</span><span class="sxs-lookup"><span data-stu-id="434e6-663">Group Call Pickup requires additional configuration in Skype for Business Server 2015 for the capability to be fully enabled.</span></span> <span data-ttu-id="434e6-664">Antes de asignar grupos de recogida a los usuarios, consulte la documentación del producto de recogida de llamadas de grupo para conocer los pasos de planeación e implementación de esta función.</span><span class="sxs-lookup"><span data-stu-id="434e6-664">Before assigning pickup groups to users, refer to the Group Call Pickup product documentation for the planning and deployment steps of this capability.</span></span>

### <a name="examples"></a><span data-ttu-id="434e6-665">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="434e6-665">Examples</span></span>

#### <a name="display-current-call-handling-settings"></a><span data-ttu-id="434e6-666">Mostrar la configuración de control de llamadas actual</span><span class="sxs-lookup"><span data-stu-id="434e6-666">Display Current Call Handling Settings</span></span>

<span data-ttu-id="434e6-667">El siguiente comando muestra el control de llamadas del usuario.</span><span class="sxs-lookup"><span data-stu-id="434e6-667">The following command displays the call handling for the user.</span></span>  `SEFAUtil.exe /server:SfBS2015server.contoso.com katarina@contoso.com`

> [!NOTE]
> <span data-ttu-id="434e6-668">En este ejemplo, se usa el modificador **/Server** para especificar el servidor de Skype empresarial al que se va a conectar.</span><span class="sxs-lookup"><span data-stu-id="434e6-668">This example uses the **/server** switch to specify the Skype for Business Server to connect to.</span></span>

 <span data-ttu-id="434e6-669">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="434e6-669">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:20
Call Forward No Answer to: voicemail
```

#### <a name="set-the-call-forwardno-answer-destination"></a><span data-ttu-id="434e6-670">Establecer el destino de desvío de llamadas/sin respuesta</span><span class="sxs-lookup"><span data-stu-id="434e6-670">Set the Call Forward/No Answer Destination</span></span>

<span data-ttu-id="434e6-671">En este ejemplo se establece el destino de desvío de llamadas y de no respuesta y el retraso del timbre.</span><span class="sxs-lookup"><span data-stu-id="434e6-671">This example sets the call forward/no answer destination and the ring delay.</span></span> <span data-ttu-id="434e6-672">Aquí no se proporciona el modificador/Server; SEFAUtil intenta detectar automáticamente Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="434e6-672">Here, the /server switch is not provided; SEFAUtil attempts to autodiscover the Skype for Business Server 2015.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone
```

 <span data-ttu-id="434e6-673">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="434e6-673">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="enable-call-forwarding-immediately"></a><span data-ttu-id="434e6-674">Habilitar el desvío de llamadas inmediatamente</span><span class="sxs-lookup"><span data-stu-id="434e6-674">Enable Call Forwarding Immediately</span></span>

<span data-ttu-id="434e6-675">En este ejemplo se habilita inmediatamente el desvío de llamadas a otro usuario.</span><span class="sxs-lookup"><span data-stu-id="434e6-675">This example immediately enables call-forwarding to another user.</span></span>

```console
SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com
```

 <span data-ttu-id="434e6-676">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="434e6-676">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Forward immediate to: sip:anders@contoso.com
```

#### <a name="disable-call-forwarding-immediately"></a><span data-ttu-id="434e6-677">Deshabilitar el desvío de llamadas inmediatamente</span><span class="sxs-lookup"><span data-stu-id="434e6-677">Disable Call Forwarding Immediately</span></span>

<span data-ttu-id="434e6-678">En este ejemplo se deshabilita inmediatamente el desvío de llamadas.</span><span class="sxs-lookup"><span data-stu-id="434e6-678">This example immediately disables call forwarding.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com katarina@contoso.com  /disablefwdimmediate
```

 <span data-ttu-id="434e6-679">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="434e6-679">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a><span data-ttu-id="434e6-680">Adición de un usuario como delegado y configuración de llamadas simultáneas de delegados</span><span class="sxs-lookup"><span data-stu-id="434e6-680">Add a User as a Delegate and Set Up Simultaneous Ringing of Delegates</span></span>

<span data-ttu-id="434e6-681">En este ejemplo se agrega un usuario como delegado y se configura la llamada simultánea de los delegados.</span><span class="sxs-lookup"><span data-stu-id="434e6-681">This example adds a user as a delegate and sets up simultaneous ringing of delegates.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates
```

 <span data-ttu-id="434e6-682">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="434e6-682">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simultaneously Ringing Delegates: sip:joe@contoso.com
```

#### <a name="change-simultaneous-ringing-rule-of-delegates"></a><span data-ttu-id="434e6-683">Cambiar la regla de llamadas simultáneas de delegados</span><span class="sxs-lookup"><span data-stu-id="434e6-683">Change Simultaneous Ringing Rule of Delegates</span></span>

<span data-ttu-id="434e6-684">En este ejemplo se cambia la regla de llamadas simultáneas que se estableció en el ejemplo anterior por la regla de timbre aplazado.</span><span class="sxs-lookup"><span data-stu-id="434e6-684">This example changes the simultaneous ringing rule that was set in the previous example to the delayed ringing rule.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10
```

 <span data-ttu-id="434e6-685">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="434e6-685">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com
```

#### <a name="remove-the-delegate"></a><span data-ttu-id="434e6-686">Quitar el delegado</span><span class="sxs-lookup"><span data-stu-id="434e6-686">Remove the Delegate</span></span>

<span data-ttu-id="434e6-687">En este ejemplo se quita el delegado.</span><span class="sxs-lookup"><span data-stu-id="434e6-687">This example removes the delegate.</span></span>

> [!NOTE]
> <span data-ttu-id="434e6-688">Cuando se quita el último delegado, se deshabilita automáticamente el timbre de delegación.</span><span class="sxs-lookup"><span data-stu-id="434e6-688">When the last delegate is removed, delegate ringing is automatically disabled.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com
```

 <span data-ttu-id="434e6-689">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="434e6-689">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a><span data-ttu-id="434e6-690">Adición de un delegado y configuración de la regla de desvío de llamadas a delegados</span><span class="sxs-lookup"><span data-stu-id="434e6-690">Add a Delegate and Set Up the Call-Forward to Delegates Rule</span></span>

<span data-ttu-id="434e6-691">En este ejemplo se agrega un delegado y se configura la regla de desvío de llamadas a delegados.</span><span class="sxs-lookup"><span data-stu-id="434e6-691">This example adds a delegate and sets up the call-forward to delegates rule.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates
```

 <span data-ttu-id="434e6-692">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="434e6-692">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Forwarding calls to Delegates: sip:anders@contoso.com
```

#### <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a><span data-ttu-id="434e6-693">Habilitar llamadas simultáneas y establecer un número de destino</span><span class="sxs-lookup"><span data-stu-id="434e6-693">Enable Simultaneous Ringing and Set a Destination Number</span></span>

<span data-ttu-id="434e6-694">En este ejemplo se habilitan las llamadas simultáneas y se establece un número de destino de llamadas simultáneas.</span><span class="sxs-lookup"><span data-stu-id="434e6-694">This example enables simultaneous ringing and sets a simultaneous ringing destination number.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring
```

> [!NOTE]
> <span data-ttu-id="434e6-695">Para cambiar el número de destino de llamadas simultáneas de un usuario que ya tiene habilitada la llamada simultánea, mantenga el comando con el modificador/enablesimulring; de lo contrario, no se cambiará el número de destino.</span><span class="sxs-lookup"><span data-stu-id="434e6-695">To change the simultaneous ringing destination number of a user that has already simultaneous ringing enabled, keep the command with the /enablesimulring switch, otherwise the destination number will not be changed.</span></span>

 <span data-ttu-id="434e6-696">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="434e6-696">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: True
Simul_Ringing to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="disable-simultaneous-ringing"></a><span data-ttu-id="434e6-697">Deshabilitar las llamadas simultáneas</span><span class="sxs-lookup"><span data-stu-id="434e6-697">Disable Simultaneous Ringing</span></span>

<span data-ttu-id="434e6-698">En este ejemplo se deshabilita la característica de llamadas simultáneas.</span><span class="sxs-lookup"><span data-stu-id="434e6-698">This example disables simultaneous ringing.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablesimulring
```

 <span data-ttu-id="434e6-699">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="434e6-699">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a><span data-ttu-id="434e6-700">Agregar un integrante del grupo para la llamada de equipo y configurar las llamadas simultáneas al grupo de miembros de llamada de equipo</span><span class="sxs-lookup"><span data-stu-id="434e6-700">Add a Team Member for Team-Call and Set up Simultaneous Ringing to the Team-Call Members Group</span></span>

<span data-ttu-id="434e6-701">En este ejemplo se agrega un integrante del grupo al grupo de llamada de equipo de un usuario y se habilita la característica de llamadas simultáneas al grupo de llamada de equipo.</span><span class="sxs-lookup"><span data-stu-id="434e6-701">This example adds a team member to the team-call group of a user and enables simultaneous ringing to the team-call group.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="434e6-702">Al agregar un miembro al grupo de llamada de equipo de un usuario, se cambiará automáticamente el configuración de llamadas simultáneas de los usuarios para situaciones su grupo de llamada de equipo.</span><span class="sxs-lookup"><span data-stu-id="434e6-702">Adding a member to the team-call group of a user will automatically switch the simultaneous ringing settigs of the users to simulring his team-call group.</span></span>

 <span data-ttu-id="434e6-703">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="434e6-703">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Team ringing enabled. Team: sip:anders@contoso.com
```

#### <a name="remove-a-member-from-the-team-call-group"></a><span data-ttu-id="434e6-704">Quitar un miembro del grupo de llamada de equipo</span><span class="sxs-lookup"><span data-stu-id="434e6-704">Remove a Member from the Team-Call Group</span></span>

<span data-ttu-id="434e6-705">En este ejemplo se quita un miembro del equipo del grupo de llamada de equipo de un usuario.</span><span class="sxs-lookup"><span data-stu-id="434e6-705">This example removes a team member of the team-call group of a user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com
```

> [!NOTE]
> <span data-ttu-id="434e6-706">Si el miembro que se va a quitar es el único miembro del grupo de llamada de equipo, las llamadas simultáneas al grupo de llamada de equipo se deshabilitarán de forma automática.</span><span class="sxs-lookup"><span data-stu-id="434e6-706">If the member being removed is the only member of the team-call group, simultaneously ringing to the team-call group will be automatically disabled.</span></span>

 <span data-ttu-id="434e6-707">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="434e6-707">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="set-the-delayed-ring-to-the-team-call-group"></a><span data-ttu-id="434e6-708">Establecer el anillo retrasado en el grupo de llamada de equipo</span><span class="sxs-lookup"><span data-stu-id="434e6-708">Set the Delayed Ring to the Team-Call Group</span></span>

<span data-ttu-id="434e6-709">En este ejemplo se cambia el timbre retrasado a la configuración de hora de grupo de llamada de equipo.</span><span class="sxs-lookup"><span data-stu-id="434e6-709">This example changes the delayed ring to the team-call group time setting.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringteam:5
```

 <span data-ttu-id="434e6-710">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="434e6-710">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com
```

#### <a name="enable-team-call"></a><span data-ttu-id="434e6-711">Habilitar llamada de equipo</span><span class="sxs-lookup"><span data-stu-id="434e6-711">Enable Team-Call</span></span>

<span data-ttu-id="434e6-712">En este ejemplo se habilita la llamada de equipo para un usuario determinado.</span><span class="sxs-lookup"><span data-stu-id="434e6-712">This example enables team-call for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="434e6-713">Si el grupo de llamada de equipo del usuario no tiene miembros, la llamada de equipo no se habilitará.</span><span class="sxs-lookup"><span data-stu-id="434e6-713">If the team-call group of the user has no members, team-call won't be enabled.</span></span>

 <span data-ttu-id="434e6-714">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="434e6-714">**Output**</span></span>

#### <a name="disable-team-call"></a><span data-ttu-id="434e6-715">Deshabilitar llamada de equipo</span><span class="sxs-lookup"><span data-stu-id="434e6-715">Disable Team-Call</span></span>

<span data-ttu-id="434e6-716">En este ejemplo se deshabilita la llamada de equipo para un usuario determinado.</span><span class="sxs-lookup"><span data-stu-id="434e6-716">This example disables team-call for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disableteamcall
```

 <span data-ttu-id="434e6-717">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="434e6-717">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a><span data-ttu-id="434e6-718">Habilitar la atención de llamadas grupales y asignar un grupo de recogida a un usuario</span><span class="sxs-lookup"><span data-stu-id="434e6-718">Enable Group Call Pickup and Assign a Pickup Group to a User</span></span>

<span data-ttu-id="434e6-719">En este ejemplo se asigna un grupo de recogida a un usuario y se habilita la recogida de llamadas grupales.</span><span class="sxs-lookup"><span data-stu-id="434e6-719">This example assigns a pickup group to a user and enables Group Call Pickup.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199
```

 <span data-ttu-id="434e6-720">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="434e6-720">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone
```

#### <a name="disable-group-call-pickup"></a><span data-ttu-id="434e6-721">Deshabilitar la recogida de llamadas de grupo</span><span class="sxs-lookup"><span data-stu-id="434e6-721">Disable Group Call Pickup</span></span>

<span data-ttu-id="434e6-722">En este ejemplo se deshabilita la llamada de llamadas grupales para un usuario determinado.</span><span class="sxs-lookup"><span data-stu-id="434e6-722">This example disables Group Call Pickup for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablegrouppickup
```

> [!NOTE]
> <span data-ttu-id="434e6-723">Cuando se deshabilita la recepción de llamadas de grupo para un usuario, no se conserva el número de grupo que se asignó al usuario.</span><span class="sxs-lookup"><span data-stu-id="434e6-723">When you disable Group Call Pickup for a user, the group number that was assigned to the user is not retained.</span></span> <span data-ttu-id="434e6-724">Si, posteriormente, desea volver a habilitar la atención de llamadas grupales para ese usuario, debe volver a asignar el número de grupo con el modificador/enablegrouppickup.</span><span class="sxs-lookup"><span data-stu-id="434e6-724">If you subsequently want to re-enable Group Call Pickup for that user, you must assign the group number again with the /enablegrouppickup switch.</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
```

## <a name="sysprepps1"></a><span data-ttu-id="434e6-725">SYSPrep. ps1</span><span class="sxs-lookup"><span data-stu-id="434e6-725">SYSPrep.ps1</span></span>
<span data-ttu-id="434e6-726"><a name="SYSPrep"> </a></span><span class="sxs-lookup"><span data-stu-id="434e6-726"><a name="SYSPrep"> </a></span></span>

### <a name="description"></a><span data-ttu-id="434e6-727">Descripción</span><span class="sxs-lookup"><span data-stu-id="434e6-727">Description</span></span>

<span data-ttu-id="434e6-728">SYSPrep. PS1 es un script de Windows PowerShell que instalará los siguientes requisitos previos de Skype empresarial Server 2015 en el equipo del sistema operativo Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="434e6-728">SYSPrep.ps1 is a Windows PowerShell script that will install the following Skype for Business Server 2015 prerequisites on your Windows Server 2008 operating system machine.</span></span>

- <span data-ttu-id="434e6-729">Microsoft .NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="434e6-729">Microsoft .Net Framework 4.5</span></span>

- <span data-ttu-id="434e6-730">Microsoft SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="434e6-730">Microsoft SQL Server Express</span></span>

- <span data-ttu-id="434e6-731">Windows PowerShell versión 3,0</span><span class="sxs-lookup"><span data-stu-id="434e6-731">Windows Powershell version 3.0</span></span>

- <span data-ttu-id="434e6-732">Paquete redistribuible de Visual C++ 2010</span><span class="sxs-lookup"><span data-stu-id="434e6-732">Visual C++ 2010 Redistributable</span></span>

- <span data-ttu-id="434e6-733">Actualizaciones de Internet Information Server</span><span class="sxs-lookup"><span data-stu-id="434e6-733">Internet Information Server Updates</span></span>

- <span data-ttu-id="434e6-734">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="434e6-734">Windows Identity Foundation</span></span>

- <span data-ttu-id="434e6-735">Archivos principales de Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="434e6-735">Skype for Business Server 2015 Core files</span></span>

  <span data-ttu-id="434e6-736">Aunque el nombre del script es similar a la herramienta de preparación del sistema para los sistemas operativos de Microsoft Windows, son diferentes.</span><span class="sxs-lookup"><span data-stu-id="434e6-736">While the script name is similar to the System Preparation Tool for the Microsoft Windows operating systems, they are different.</span></span> <span data-ttu-id="434e6-737">Este script solo instalará los requisitos previos necesarios para Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="434e6-737">This script will only install the required prerequisites for Skype for Business Server 2015.</span></span> <span data-ttu-id="434e6-738">Una vez instalados estos requisitos previos, puede usar la herramienta SYSPrep de Windows para crear una imagen del servidor.</span><span class="sxs-lookup"><span data-stu-id="434e6-738">Once those prerequisites are installed, the Windows SYSPrep tool can then be used to create an image of the server.</span></span>

### <a name="requirements"></a><span data-ttu-id="434e6-739">Requisitos</span><span class="sxs-lookup"><span data-stu-id="434e6-739">Requirements</span></span>

<span data-ttu-id="434e6-740">Antes de ejecutar el script SYSPrep. ps1, debe copiar los archivos de requisitos previos en una carpeta local del equipo del sistema operativo Windows Server 2008 (por ejemplo **, D:\setup)**.</span><span class="sxs-lookup"><span data-stu-id="434e6-740">Prior to running the SYSPrep.ps1 script, you must copy the prerequisite files to a local folder on the Windows Server 2008 operating system machine (for example **D:\Setup)**.</span></span> <span data-ttu-id="434e6-741">Esta carpeta también debe incluir una copia de los archivos de Skype empresarial Server 2015, concretamente **setup. exe.**</span><span class="sxs-lookup"><span data-stu-id="434e6-741">This folder must also include a copy of the Skype for Business Server 2015 files, specifically **Setup.exe.**</span></span> <span data-ttu-id="434e6-742">Los archivos de requisitos previos se pueden descargar desde las siguientes ubicaciones:</span><span class="sxs-lookup"><span data-stu-id="434e6-742">The prerequisite files can be downloaded from the following locations:</span></span>


| <span data-ttu-id="434e6-743">**Requisitos previos**</span><span class="sxs-lookup"><span data-stu-id="434e6-743">**Prerequisite**</span></span>                                | <span data-ttu-id="434e6-744">**Ubicación**</span><span class="sxs-lookup"><span data-stu-id="434e6-744">**Location**</span></span>                                                            |
|:------------------------------------------------|:------------------------------------------------------------------------|
| <span data-ttu-id="434e6-745">Microsoft .NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="434e6-745">Microsoft .Net Framework 4.5</span></span>  <br/>             | <https://go.microsoft.com/?linkid=9816306>  <br/>                       |
| <span data-ttu-id="434e6-746">Microsoft SQL Server Express 2008 R2</span><span class="sxs-lookup"><span data-stu-id="434e6-746">Microsoft SQL Server Express 2008 R2</span></span>  <br/>     | <https://www.microsoft.com/download/details.aspx?id=23650>  <br/> |
| <span data-ttu-id="434e6-747">Windows PowerShell versión 3,0</span><span class="sxs-lookup"><span data-stu-id="434e6-747">Windows Powershell version 3.0</span></span>  <br/>           | <https://www.microsoft.com/download/details.aspx?id=34595>  <br/> |
| <span data-ttu-id="434e6-748">Paquete redistribuible de Visual C++ 2010</span><span class="sxs-lookup"><span data-stu-id="434e6-748">Visual C++ 2010 Redistributable</span></span>  <br/>          | <https://www.microsoft.com/download/details.aspx?id=5555>  <br/>  |
| <span data-ttu-id="434e6-749">Actualizaciones de Internet Information Server</span><span class="sxs-lookup"><span data-stu-id="434e6-749">Internet Information Server Updates</span></span>  <br/>      | <https://www.microsoft.com/download/details.aspx?id=34869>  <br/> |
| <span data-ttu-id="434e6-750">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="434e6-750">Windows Identity Foundation</span></span>  <br/>              | <https://www.microsoft.com/download/details.aspx?id=17331>  <br/> |
| <span data-ttu-id="434e6-751">Setup. exe de Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="434e6-751">Skype for Business Server 2015 Setup.exe</span></span>  <br/> | <span data-ttu-id="434e6-752">Copiar desde los medios de Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="434e6-752">Copy from Skype for Business Server 2015 media</span></span>  <br/>                   |

### <a name="parameter"></a><span data-ttu-id="434e6-753">Parámetro</span><span class="sxs-lookup"><span data-stu-id="434e6-753">Parameter</span></span>

<span data-ttu-id="434e6-754">El parámetro **-SetupFolder** toma como argumento la ubicación del directorio de los archivos de requisitos previos</span><span class="sxs-lookup"><span data-stu-id="434e6-754">The **-SetupFolder** parameter takes as an argument the directory location of the prerequisite files</span></span>

### <a name="examples"></a><span data-ttu-id="434e6-755">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="434e6-755">Examples</span></span>

<span data-ttu-id="434e6-756">Para ejecutar el script SYSPrep. PS1 e instalar los requisitos previos de Skype empresarial Server 2015, ejecute el siguiente comando desde un símbolo del sistema con privilegios elevados:</span><span class="sxs-lookup"><span data-stu-id="434e6-756">To run the SYSPrep.ps1 script and install the Skype for Business Server 2015 prerequisites, run the following command from an elevated command prompt:</span></span>

```console
./SysPrep.PS1 -SetupFolder D:\Setup
```

## <a name="unassigned-number-announcements-migration"></a><span data-ttu-id="434e6-757">Número de anuncios no asignados a la migración</span><span class="sxs-lookup"><span data-stu-id="434e6-757">Unassigned Number Announcements Migration</span></span>
<span data-ttu-id="434e6-758"><a name="UNAM"> </a></span><span class="sxs-lookup"><span data-stu-id="434e6-758"><a name="UNAM"> </a></span></span>

<span data-ttu-id="434e6-759">La herramienta de migración de anuncios de números sin asignar permite que un administrador de Skype empresarial Server 2015 mueva la configuración de números sin asignar que recibe el servicio de la aplicación de anuncio de un servidor o grupo de Skype empresarial de origen a un destino de Skype empresarial Server o grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="434e6-759">The Unassigned Number Announcements Migration tool enables a Skype for Business Server 2015 administrator to move the unassigned numbers configuration that is serviced by the announcement application from a source Skype for Business Server or Pool to a destination Skype for Business Server or Pool.</span></span>

### <a name="description"></a><span data-ttu-id="434e6-760">Descripción</span><span class="sxs-lookup"><span data-stu-id="434e6-760">Description</span></span>

<span data-ttu-id="434e6-761">La herramienta de migración de anuncios de números sin asignar es un script de Windows PowerShell que mueve la configuración de números sin asignar que recibe el servicio de la aplicación de anuncio de un servidor o grupo de origen a otro servidor o grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="434e6-761">The Unassigned Number Announcements Migration tool is a Windows PowerShell script that moves the unassigned numbers configuration serviced by the announcement application of a source server or pool to a different server or pool.</span></span>

<span data-ttu-id="434e6-762">Cuando se ejecuta, el script de migración de números sin asignar de anuncios realizará las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="434e6-762">When executed, the Unassigned Number Announcements Migration script will perform the following operations:</span></span>

1. <span data-ttu-id="434e6-763">Mueva todos los archivos de audio usados por los anuncios de números sin asignar de la aplicación de anuncio hospedada en el servidor o grupo de origen al almacén de archivos del servidor o grupo de destino.</span><span class="sxs-lookup"><span data-stu-id="434e6-763">Move all the audio files used by the unassigned number announcements of the announcement application hosted in the source server or pool to the file store of the destination server or pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="434e6-764">Los archivos de audio se quitan del grupo de origen una vez que se copian en el grupo de servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="434e6-764">The audio files are removed from the source pool once they're copied to the destination pool.</span></span>

2. <span data-ttu-id="434e6-765">Se mueven todos los anuncios de números sin asignar configurados para la aplicación de anuncio hospedada en el servidor o grupo de origen al servidor o grupo de destino.</span><span class="sxs-lookup"><span data-stu-id="434e6-765">Move all unassigned number announcements configured for the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

3. <span data-ttu-id="434e6-766">Reasignar todos los intervalos de números no asignados que reciben servicio de la aplicación de anuncio hospedada en el servidor o grupo de origen al servidor o grupo de destino.</span><span class="sxs-lookup"><span data-stu-id="434e6-766">Reassign all the unassigned number ranges that are serviced by the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

<span data-ttu-id="434e6-767">Después de ejecutar correctamente el script, todos los intervalos de números sin asignar que provienen de la aplicación de anuncio hospedada en el servidor o grupo de servidores de origen se proporcionarán con la misma configuración que el servidor o el grupo de destino.</span><span class="sxs-lookup"><span data-stu-id="434e6-767">After successfully running the script, all the unassigned number ranges that were serviced by the announcement application hosted in the source server or pool will now be serviced with the same configuration by the destination server or pool.</span></span>

### <a name="output"></a><span data-ttu-id="434e6-768">Output</span><span class="sxs-lookup"><span data-stu-id="434e6-768">Output</span></span>

<span data-ttu-id="434e6-769">El script **Move-CsAnnouncementConfiguration** indica en la ventana del shell de administración de Skype empresarial Server desde donde se ejecuta el éxito o el fracaso de la operación de migración.</span><span class="sxs-lookup"><span data-stu-id="434e6-769">The **Move-CsAnnouncementConfiguration** script indicates in the Skype for Business Server Management Shell window from where it's executed the success or failure of the migration operation.</span></span>

<span data-ttu-id="434e6-770">Si cualquier error interrumpe la ejecución de la operación, los intervalos de números sin asignar que se movieron correctamente al destino permanecerán en el destino en un formulario operativo y el resto de los intervalos de números sin asignar que se van a migrar permanecerán en el origen también en un formulario operativo.</span><span class="sxs-lookup"><span data-stu-id="434e6-770">If the execution of the operation is interrupted by any error, the unassigned number ranges that were successfully moved to the destination will remain in the destination in an operational form and the rest of the unassigned number ranges to be migrated will remain in the source as well in an operational form.</span></span> <span data-ttu-id="434e6-771">Para migrar por completo el resto de la configuración, vuelva a ejecutar el script después de solucionar el error.</span><span class="sxs-lookup"><span data-stu-id="434e6-771">To fully migrate the rest of the configuration, rerun the script after addressing the error.</span></span>

### <a name="purpose"></a><span data-ttu-id="434e6-772">Finalidad</span><span class="sxs-lookup"><span data-stu-id="434e6-772">Purpose</span></span>

<span data-ttu-id="434e6-773">Se puede usar el script de migración de anuncios de números sin asignar en los tres escenarios siguientes:</span><span class="sxs-lookup"><span data-stu-id="434e6-773">The Unassigned Number Announcements Migration script can be used in the following three scenarios:</span></span>

- <span data-ttu-id="434e6-774">**Migrar las opciones de configuración a una nueva versión de Skype empresarial Server:** Contoso está en proceso de migrar a Skype empresarial Server 2015 y, como parte del proceso de migración, el administrador de Skype empresarial Server desea mover la configuración de números no asignados a la que el anuncio ha dado servicio desde la implementación de Lync Server 2013 a la nueva implementación de Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="434e6-774">**Migrating configuration settings to a new version of Skype for Business Server:** Contoso is in the process of migrating to Skype for Business Server 2015 and as part of the migration process the Skype for Business Server administrator would like to move the unassigned numbers configuration serviced by the announcement application from the Lync Server 2013 deployment to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="434e6-775">Para mover las opciones de configuración, el administrador de Skype empresarial Server usa la herramienta de migración de anuncios de números sin asignar.</span><span class="sxs-lookup"><span data-stu-id="434e6-775">To move the configuration settings, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool.</span></span>

- <span data-ttu-id="434e6-776">**Revertir una implementación de Skype empresarial Server 2015 a Lync Server 2013:** Debido a los factores inesperados, Contoso tiene que revertir la migración a la nueva implementación de Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="434e6-776">**Rolling back a deployment from Skype for Business Server 2015 to Lync Server 2013:** Due unexpected factors, Contoso has to roll back the migration to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="434e6-777">Para minimizar las interrupciones en el servicio, el administrador de Skype empresarial Server usa la herramienta de migración de anuncios de números sin asignar para revertir la configuración de la implementación de Skype empresarial Server 2015 a la implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="434e6-777">To minimize disruptions to the service, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool to roll back the configuration from the Skype for Business Server 2015 deployment to the Lync Server 2013 deployment.</span></span>

- <span data-ttu-id="434e6-778">**Movimiento de datos entre implementaciones:** Contoso está en proceso de reemplazar todos los servidores de un grupo por los nuevos servidores.</span><span class="sxs-lookup"><span data-stu-id="434e6-778">**Moving data between deployments:** Contoso is in the process of replacing all the servers of one pool with newer servers.</span></span> <span data-ttu-id="434e6-779">Su estrategia es implementar un nuevo grupo de servidores de Skype empresarial Server 2015, mover todos los datos del antiguo al nuevo y, a continuación, dejar de utilizar el grupo anterior.</span><span class="sxs-lookup"><span data-stu-id="434e6-779">Their strategy is to deploy a new Skype for Business Server 2015 pool, move all the data from the old to the new pool, and then deprecate the old pool.</span></span> <span data-ttu-id="434e6-780">Una vez que se haya implementado el nuevo grupo de servidores, se usará la herramienta de migración de anuncios de números sin asignar para mover la configuración del grupo anterior al nuevo.</span><span class="sxs-lookup"><span data-stu-id="434e6-780">Once the new pool is deployed, the Unassigned Number Announcements Migration tool is used to move the configuration from the old pool to the new one.</span></span>

#### <a name="requirements"></a><span data-ttu-id="434e6-781">Requisitos</span><span class="sxs-lookup"><span data-stu-id="434e6-781">Requirements</span></span>

<span data-ttu-id="434e6-782">Los siguientes son los requisitos principales necesarios para ejecutar correctamente la herramienta:</span><span class="sxs-lookup"><span data-stu-id="434e6-782">The following are the main requirements needed to successfully run the tool:</span></span>

1. <span data-ttu-id="434e6-783">El script debe ejecutarse desde un equipo que tenga instalado el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="434e6-783">The script must be run from a computer that has Skype for Business Server Management Shell installed.</span></span>

2. <span data-ttu-id="434e6-784">La aplicación de anuncio tiene que implementarse correctamente en los servidores o grupos de servidores de Skype empresarial de origen y de destino.</span><span class="sxs-lookup"><span data-stu-id="434e6-784">The announcement application has to be successfully deployed in the source and destination Skype for Business Servers or Pools.</span></span>

#### <a name="move-csannouncementconfiguration-script"></a><span data-ttu-id="434e6-785">Secuencia de comandos Move-CsAnnouncementConfiguration</span><span class="sxs-lookup"><span data-stu-id="434e6-785">Move-CsAnnouncementConfiguration script</span></span>

<span data-ttu-id="434e6-786">El script Move-CsAnnouncementConfiguration requiere los dos parámetros que se describen en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="434e6-786">The Move-CsAnnouncementConfiguration script requires the two parameters that are described in the table below.</span></span>

![Parámetros Move-CsAnnouncementConfiguration.](../media/Reskit_2012_Tools_Documentation_Image41.JPG)

### <a name="examples"></a><span data-ttu-id="434e6-788">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="434e6-788">Examples</span></span>

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-skype-for-business-server-2015-pool"></a><span data-ttu-id="434e6-789">Mover la configuración de anuncios de números sin asignar de un grupo de servidores de Lync Server 2013 a un grupo de servidores de Skype empresarial 2015</span><span class="sxs-lookup"><span data-stu-id="434e6-789">Moving the Unassigned Number Announcements Configuration from a Lync Server 2013 Pool to a Skype for Business Server 2015 Pool</span></span>

<span data-ttu-id="434e6-790">En este ejemplo se mueven los anuncios de números sin asignar del grupo de origen (Lync Server 2013) al grupo de destino (Skype empresarial Server 2015).</span><span class="sxs-lookup"><span data-stu-id="434e6-790">This example moves the unassigned number announcements from the source pool (Lync Server 2013) to the destination pool (Skype for Business Server 2015).</span></span>

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination SfBS2015Pool.contoso.com
```

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-skype-for-business-server-2015-pool-to-a-lync-server-2013-pool"></a><span data-ttu-id="434e6-791">Mover la configuración de anuncios de números sin asignar de un grupo de servidores de Skype empresarial Server 2015 a un grupo de servidores de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="434e6-791">Moving the Unassigned Number Announcements Configuration from a Skype for Business Server 2015 Pool to a Lync Server 2013 Pool</span></span>

<span data-ttu-id="434e6-792">En este ejemplo se mueven los anuncios de números sin asignar del grupo de origen (Skype empresarial Server 2015) al grupo de servidores de destino (Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="434e6-792">This example moves the unassigned number announcements from the source pool (Skype for Business Server 2015) to the destination pool (Lync Server 2013).</span></span>

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source SfBS2015Pool.contoso.com -Destination LS2013Pool.contoso.com
```

## <a name="web-conf-data"></a><span data-ttu-id="434e6-793">Datos de conf de Web</span><span class="sxs-lookup"><span data-stu-id="434e6-793">Web Conf Data</span></span>
<span data-ttu-id="434e6-794"><a name="WebConfData"> </a></span><span class="sxs-lookup"><span data-stu-id="434e6-794"><a name="WebConfData"> </a></span></span>

<span data-ttu-id="434e6-795">La herramienta de datos Web conf permite que un administrador del software de comunicaciones de Skype empresarial Server 2015 tenga más control sobre los datos asociados con las conferencias web del organizador.</span><span class="sxs-lookup"><span data-stu-id="434e6-795">The Web Conf Data Tool allows an administrator of Skype for Business Server 2015 communications software to have more control over the data associated with an organizer's Web conferences.</span></span> <span data-ttu-id="434e6-796">Los escenarios incluyen la capacidad de eliminar los datos específicos de una reunión de un usuario en función de los criterios de marca de tiempo.</span><span class="sxs-lookup"><span data-stu-id="434e6-796">Scenarios include the ability to delete a specific user's meeting data based on a time stamp criteria.</span></span>

### <a name="description"></a><span data-ttu-id="434e6-797">Descripción</span><span class="sxs-lookup"><span data-stu-id="434e6-797">Description</span></span>

<span data-ttu-id="434e6-798">Esta herramienta permite al administrador realizar las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="434e6-798">This tool allows the administrator to perform the following operations:</span></span>

1. <span data-ttu-id="434e6-799">Buscar todos los datos de conferencias web asociados con un único usuario.</span><span class="sxs-lookup"><span data-stu-id="434e6-799">Find all Web conferencing data associated with a single user.</span></span>

2. <span data-ttu-id="434e6-800">Eliminar todos los datos de conferencias web asociados con un único usuario.</span><span class="sxs-lookup"><span data-stu-id="434e6-800">Delete all Web conferencing data associated with a single user.</span></span>

3. <span data-ttu-id="434e6-801">Elimine todos los datos de conferencias web asociados con un único usuario que sea anterior a una fecha concreta.</span><span class="sxs-lookup"><span data-stu-id="434e6-801">Delete all Web conferencing data associated with a single user that is older than a certain date.</span></span>

4. <span data-ttu-id="434e6-802">Se mueven todos los datos de conferencias web asociados con un usuario único cuando este usuario se mueve de un grupo de servidores a otro.</span><span class="sxs-lookup"><span data-stu-id="434e6-802">Move all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span>

    > [!NOTE]
    > <span data-ttu-id="434e6-803">Las herramientas del kit de recursos para Lync Server 2010 admiten el traslado de todos los datos de conferencias web asociados con un usuario único cuando se mueve a ese usuario de un grupo de servidores a otro.</span><span class="sxs-lookup"><span data-stu-id="434e6-803">The Resource Kit Tools for Lync Server 2010 supported moving all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span> <span data-ttu-id="434e6-804">Esa funcionalidad ahora está en desuso de esta herramienta en favor del parámetro **MoveConferenceData** .</span><span class="sxs-lookup"><span data-stu-id="434e6-804">That functionality is now deprecated from this tool in favor of the **MoveConferenceData** parameter.</span></span> <span data-ttu-id="434e6-805">Para obtener más información sobre este parámetro, consulte el cmdlet [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="434e6-805">For details about this parameter, see the [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps) cmdlet.</span></span>

<span data-ttu-id="434e6-806">La herramienta elimina los datos de la reunión solo para las reuniones inactivas.</span><span class="sxs-lookup"><span data-stu-id="434e6-806">The tool deletes meeting data only for meetings that are inactive.</span></span> <span data-ttu-id="434e6-807">Las reuniones activas (o reuniones en sesiones) no se pueden eliminar.</span><span class="sxs-lookup"><span data-stu-id="434e6-807">Active meetings (or meetings in sessions) cannot be deleted.</span></span>

<span data-ttu-id="434e6-808">Esta herramienta debe ejecutarse desde un equipo que esté en el mismo grupo de servidores que el usuario de destino.</span><span class="sxs-lookup"><span data-stu-id="434e6-808">This tool must be run from a computer that is in the same pool as the target user.</span></span> <span data-ttu-id="434e6-809">El usuario cuyos datos de contenido de reunión se administran mediante esta herramienta debe estar hospedado en el mismo grupo de usuarios.</span><span class="sxs-lookup"><span data-stu-id="434e6-809">The user whose meeting content data is being managed by this tool must be homed in the same user pool.</span></span>

### <a name="output"></a><span data-ttu-id="434e6-810">Output</span><span class="sxs-lookup"><span data-stu-id="434e6-810">Output</span></span>

<span data-ttu-id="434e6-811">Esta herramienta genera los resultados de cada una de las operaciones:</span><span class="sxs-lookup"><span data-stu-id="434e6-811">This tool outputs the results of each of the operations:</span></span>

- <span data-ttu-id="434e6-812">Si se realiza una consulta, la herramienta genera la lista de todas las carpetas de datos de reuniones inactivas que el usuario tiene como organizador.</span><span class="sxs-lookup"><span data-stu-id="434e6-812">If a query is performed, the tool outputs the list of all inactive meeting data folders that have that user as an organizer.</span></span>

- <span data-ttu-id="434e6-813">Si se realiza una eliminación, la herramienta genera la lista de todas las carpetas de datos de la reunión cuyos datos se eliminarán.</span><span class="sxs-lookup"><span data-stu-id="434e6-813">If a delete is performed, the tool outputs the list of all meeting data folders whose data will be deleted.</span></span>

### <a name="requirements"></a><span data-ttu-id="434e6-814">Requisitos</span><span class="sxs-lookup"><span data-stu-id="434e6-814">Requirements</span></span>

<span data-ttu-id="434e6-815">La herramienta debe ejecutarse en el mismo grupo de servidores donde está hospedada actualmente el organizador.</span><span class="sxs-lookup"><span data-stu-id="434e6-815">The tool needs to be run in the same pool where the organizer is currently homed.</span></span>

<span data-ttu-id="434e6-816">La herramienta debe ejecutarse con privilegios de administrador con acceso al almacén de archivos de contenido.</span><span class="sxs-lookup"><span data-stu-id="434e6-816">The tool must be run using administrator privileges with access to the Content File Store.</span></span>

### <a name="examples"></a><span data-ttu-id="434e6-817">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="434e6-817">Examples</span></span>

<span data-ttu-id="434e6-818">En la tabla siguiente se describen los parámetros, algunos de los cuales se usan en los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="434e6-818">The following table describes the parameters, some of which are used in the examples.</span></span>

![Parámetros de la herramienta de datos Web conf.](../media/Reskit_2012_Tools_Documentation_Image51.JPG)

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""
```

<span data-ttu-id="434e6-820">En el ejemplo anterior se muestra el funcionamiento de un comando de consulta.</span><span class="sxs-lookup"><span data-stu-id="434e6-820">The preceding example shows how a query command would work.</span></span> <span data-ttu-id="434e6-821">El resultado de un comando de este tipo sería una lista de todas las carpetas de contenido de reuniones que se verían afectadas por esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="434e6-821">The output of such a command would be a list of all meeting content folders that would be affected by this tool.</span></span>

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:delete
```

<span data-ttu-id="434e6-822">El ejemplo anterior es un ejemplo de un comando DELETE.</span><span class="sxs-lookup"><span data-stu-id="434e6-822">The preceding is an example of a delete command.</span></span> <span data-ttu-id="434e6-823">El comando eliminar quitará todas las carpetas de reuniones inactivas de este usuario.</span><span class="sxs-lookup"><span data-stu-id="434e6-823">The delete command will remove all inactive meeting folders from this user.</span></span>

### <a name="summary"></a><span data-ttu-id="434e6-824">Resumen</span><span class="sxs-lookup"><span data-stu-id="434e6-824">Summary</span></span>

<span data-ttu-id="434e6-825">Esta herramienta puede ser un recurso útil para los administradores que necesitan un control más preciso sobre los datos de las reuniones de conferencia.</span><span class="sxs-lookup"><span data-stu-id="434e6-825">This tool can be a valuable resource to administrators who need more precise control over conference meeting data.</span></span>


