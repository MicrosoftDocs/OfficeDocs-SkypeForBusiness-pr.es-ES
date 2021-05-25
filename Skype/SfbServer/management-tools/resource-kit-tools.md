---
title: Skype Empresarial Server de herramientas del kit de recursos de 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/20/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
description: En este artículo se describen las herramientas del kit de recursos Skype Empresarial Server 2015, incluido el propósito de cada herramienta, y ejemplos de su uso. El Skype Empresarial Server de recursos de 2015 ayuda a facilitar las tareas rutinarias a los administradores de TI que implementan y administran Skype Empresarial Server 2015. Por ejemplo, la herramienta de datos de Web Conf se puede usar para controlar fácilmente los datos que cargan los usuarios durante una reunión en línea. La herramienta SEFAUtil se puede usar para configurar el reenvío delegado de llamadas y el contestado para los usuarios. Animamos a los administradores de TI a que usen estas herramientas para administrar de forma Skype Empresarial Server 2015.
ms.openlocfilehash: 6c68a94d331f2ad5f9ffaa169228aa9d64e41293
ms.sourcegitcommit: 330e60ff3549cd5cff5b52ad95dc4259e4e8de13
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2021
ms.locfileid: "52629049"
---
# <a name="skype-for-business-server-2015-resource-kit-tools-documentation"></a><span data-ttu-id="90398-107">Skype Empresarial Server de herramientas del kit de recursos de 2015</span><span class="sxs-lookup"><span data-stu-id="90398-107">Skype for Business Server 2015 Resource Kit Tools Documentation</span></span>

<span data-ttu-id="90398-108">En este artículo se describen las herramientas del kit de recursos Skype Empresarial Server 2015, incluido el propósito de cada herramienta, y ejemplos de su uso.</span><span class="sxs-lookup"><span data-stu-id="90398-108">This article describes the tools in the Skype for Business Server 2015 Resource Kit, including the purpose of each tool, and examples of its use.</span></span> <span data-ttu-id="90398-109">El Skype Empresarial Server de recursos de 2015 ayuda a facilitar las tareas rutinarias a los administradores de TI que implementan y administran Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="90398-109">The Skype for Business Server 2015 Resource Kit helps to make routine tasks easier for IT administrators who deploy and manage Skype for Business Server 2015.</span></span> <span data-ttu-id="90398-110">Por ejemplo, la herramienta de datos **de Web Conf** se puede usar para controlar fácilmente los datos que cargan los usuarios durante una reunión en línea.</span><span class="sxs-lookup"><span data-stu-id="90398-110">For example, the **Web Conf Data** tool can be used to easily control data that is uploaded by users during an online meeting.</span></span> <span data-ttu-id="90398-111">La **herramienta SEFAUtil** se puede usar para configurar el reenvío delegado de llamadas y el contestado para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="90398-111">The **SEFAUtil** tool can be used to set up delegate call forwarding and answering for users.</span></span> <span data-ttu-id="90398-112">Animamos a los administradores de TI a que usen estas herramientas para administrar de forma Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="90398-112">We encourage IT administrators to use these tools to more effectively manage Skype for Business Server 2015.</span></span>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="90398-113">Instalación de las herramientas del kit de recursos</span><span class="sxs-lookup"><span data-stu-id="90398-113">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="90398-114">Para instalar el kit Skype Empresarial Server recursos de 2015, descargueOCSReskit.msi[desde](https://www.microsoft.com/download/details.aspx?id=52631) el Centro de descarga.</span><span class="sxs-lookup"><span data-stu-id="90398-114">To install the Skype for Business Server 2015 Resource Kit, download [OCSReskit.msi](https://www.microsoft.com/download/details.aspx?id=52631) from the Download Center.</span></span>

<span data-ttu-id="90398-115">Ejecute **OCSResKit.msi** para realizar una instalación sencilla.</span><span class="sxs-lookup"><span data-stu-id="90398-115">Run **OCSResKit.msi** to do a simple installation.</span></span> <span data-ttu-id="90398-116">El .msi instala todas las herramientas en la siguiente ruta de acceso: **%Program Files%\Skype Empresarial Server 2015\ResKit**.</span><span class="sxs-lookup"><span data-stu-id="90398-116">The .msi installs all the tools in the following path: **%Program Files%\Skype for Business Server 2015\ResKit**.</span></span> <span data-ttu-id="90398-117">Las herramientas que son ejecutables independientes se encuentran en esta carpeta.</span><span class="sxs-lookup"><span data-stu-id="90398-117">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="90398-118">Las herramientas que también tienen archivos compatibles están en sus propias subcarpetas.</span><span class="sxs-lookup"><span data-stu-id="90398-118">Tools that also have supporting files are in their own subfolders.</span></span>

## <a name="supported-environments"></a><span data-ttu-id="90398-119">Entornos compatibles</span><span class="sxs-lookup"><span data-stu-id="90398-119">Supported Environments</span></span>

<span data-ttu-id="90398-120">El kit de recursos Skype Empresarial Server 2015 debe instalarse en un servidor que cumpla las especificaciones necesarias para Skype Empresarial Server 2015, normalmente uno que se usa para ejecutar Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="90398-120">The Skype for Business Server 2015 Resource Kit should be installed on a server that meets the specifications required for Skype for Business Server 2015, usually one being used to run Skype for Business Server 2015.</span></span>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="90398-121">Introducción a herramientas del kit de recursos</span><span class="sxs-lookup"><span data-stu-id="90398-121">Resource Kit Tools Overview</span></span>

<span data-ttu-id="90398-122">A continuación se muestra una lista de las herramientas que se proporcionan en el kit de recursos de Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="90398-122">The following is a list of the tools that are provided in the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="90398-123">En las secciones siguientes se incluye una descripción de cada herramienta, incluidos los requisitos y el uso de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="90398-123">A description of each tool, including the requirements and example usage is covered in the following sections.</span></span>

- [<span data-ttu-id="90398-124">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="90398-124">ABSConfig</span></span>](resource-kit-tools.md#ABSConfig)

- [<span data-ttu-id="90398-125">Monitor de servicio de directivas de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="90398-125">Bandwidth Policy Service Monitor</span></span>](resource-kit-tools.md#bpsm)

- [<span data-ttu-id="90398-126">Analizador de uso de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="90398-126">Bandwidth Utilization Analyzer</span></span>](resource-kit-tools.md#bua)

- [<span data-ttu-id="90398-127">Parkometer de llamadas</span><span class="sxs-lookup"><span data-stu-id="90398-127">Call Parkometer</span></span>](resource-kit-tools.md#callpark)

- [<span data-ttu-id="90398-128">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="90398-128">DBAnalyze</span></span>](resource-kit-tools.md#dba)

- [<span data-ttu-id="90398-129">Importar Storage de servicio</span><span class="sxs-lookup"><span data-stu-id="90398-129">Import Storage Service Data</span></span>](resource-kit-tools.md#Issd)

- [<span data-ttu-id="90398-130">LCSSync</span><span class="sxs-lookup"><span data-stu-id="90398-130">LCSSync</span></span>](resource-kit-tools.md#LCSSync)

- [<span data-ttu-id="90398-131">Consola de usuario de búsqueda</span><span class="sxs-lookup"><span data-stu-id="90398-131">Lookup User Console</span></span>](resource-kit-tools.md#LUC)

- [<span data-ttu-id="90398-132">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="90398-132">MsTurnPing</span></span>](resource-kit-tools.md#MsTurnPing)

- [<span data-ttu-id="90398-133">Visor de configuración de red</span><span class="sxs-lookup"><span data-stu-id="90398-133">Network Configuration Viewer</span></span>](resource-kit-tools.md#NCV)

- [<span data-ttu-id="90398-134">Agente de grupo de respuesta en directo</span><span class="sxs-lookup"><span data-stu-id="90398-134">Response Group Agent Live</span></span>](resource-kit-tools.md#RGAL)

- [<span data-ttu-id="90398-135">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="90398-135">SEFAUtil</span></span>](resource-kit-tools.md#SEFAUtil)

- [<span data-ttu-id="90398-136">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="90398-136">SYSPrep.ps1</span></span>](resource-kit-tools.md#SYSPrep)

- [<span data-ttu-id="90398-137">Migración de anuncios de números sin asign</span><span class="sxs-lookup"><span data-stu-id="90398-137">Unassigned Number Announcements Migration</span></span>](resource-kit-tools.md#UNAM)

- [<span data-ttu-id="90398-138">Datos de Web Conf</span><span class="sxs-lookup"><span data-stu-id="90398-138">Web Conf Data</span></span>](resource-kit-tools.md#WebConfData)

## <a name="absconfig"></a><span data-ttu-id="90398-139">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="90398-139">ABSConfig</span></span>
<span data-ttu-id="90398-140"><a name="ABSConfig"> </a></span><span class="sxs-lookup"><span data-stu-id="90398-140"><a name="ABSConfig"> </a></span></span>

<span data-ttu-id="90398-141">La herramienta de configuración del servicio de libreta de direcciones (ABSConfig) es una herramienta administrativa que ayuda a los administradores a personalizar la configuración del servicio de libreta de direcciones en Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="90398-141">The Address Book Service Configuration tool (ABSConfig) is an administrative tool that helps administrators customize Address Book Service configuration in Skype for Business Server 2015.</span></span> <span data-ttu-id="90398-142">Esta herramienta también permite a Skype Empresarial Server administradores de 2015 restaurar la configuración predeterminada del servicio de libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="90398-142">This tool also enables Skype for Business Server 2015 administrators to restore the default Address Book Service settings.</span></span>

### <a name="description"></a><span data-ttu-id="90398-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="90398-143">Description</span></span>

<span data-ttu-id="90398-144">ABSConfig es una aplicación gráfica de interfaz de usuario que permite a los administradores configurar atributos de servicios de dominio de Active Directory relacionados con el servicio de libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="90398-144">ABSConfig is a graphical user interface application that enables administrators to configure Active Directory Domain Services attributes that are related to Address Book Service.</span></span>

<span data-ttu-id="90398-145">Los escenarios principales de la herramienta son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="90398-145">The primary scenarios for the tool are the following:</span></span>

- <span data-ttu-id="90398-146">Para permitir que los administradores asignen atributos de Servicios de dominio de Active Directory a los atributos de Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="90398-146">To enable administrators to map attributes in Active Directory Domain Services to the attributes for Skype for Business Server 2015.</span></span>

- <span data-ttu-id="90398-147">Para permitir que los administradores especifiquen el atributo Servicios de dominio de Active Directory que se incluirá o excluirá en los archivos del servicio de libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="90398-147">To enable administrators to specify the Active Directory Domain Services attribute to be included or excluded in the Address Book Service files.</span></span>

- <span data-ttu-id="90398-148">Para permitir a los administradores restaurar, configuración predeterminada del servicio de libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="90398-148">To enable administrators to restore,  default Address Book Service settings.</span></span>

<span data-ttu-id="90398-149">La herramienta ABSConfig se puede iniciar mediante el ABSConfig.exe archivo.</span><span class="sxs-lookup"><span data-stu-id="90398-149">The ABSConfig tool can be started by using the ABSConfig.exe file.</span></span> <span data-ttu-id="90398-150">La herramienta se abre en la **pestaña Configurar atributos.** Esta tabla tiene opciones para asignar atributos de Servicios de dominio de Active Directory a los campos de atributo de Skype Empresarial Server 2015 y especificar qué usuarios deben incluir o excluir en los archivos de servicio de libreta de direcciones en función de filtros de atributos específicos.</span><span class="sxs-lookup"><span data-stu-id="90398-150">The tool opens to the **Configure Attributes** tab. This table has options to map Active Directory Domain Services attributes to the attribute fields for Skype for Business Server 2015 and to specify which users to include or exclude in Address Book Service files based on specific attribute filters.</span></span> <span data-ttu-id="90398-151">También tiene opciones para personalizar el valor del número de teléfono que se incluirá en el archivo de libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="90398-151">It also has options to customize which value of the phone number to be included in the Address Book file.</span></span> <span data-ttu-id="90398-152">La **opción Restaurar valores predeterminados** permite a los administradores restaurar la configuración del servicio de libreta de direcciones a los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="90398-152">The **Restore Defaults** option enables administrators to restore Address Book Service settings to default values.</span></span>

> [!NOTE]
> <span data-ttu-id="90398-153">La nueva asignación de atributos de AD a diferentes nombres de campo OC solo funcionará para la descarga de archivos de libreta de direcciones y no es compatible con la consulta web de libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="90398-153">Re-mapping of AD attributes to different OC Field Names will only work for Address Book File Download, and is not supported by Address Book Web Query.</span></span>

### <a name="output"></a><span data-ttu-id="90398-154">Salida</span><span class="sxs-lookup"><span data-stu-id="90398-154">Output</span></span>

<span data-ttu-id="90398-155">ABSConfig almacena la configuración del servicio de libreta de direcciones en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="90398-155">ABSConfig stores the Address Book Service configuration in the database.</span></span>

```console
Path: %ProgramFiles%\Skype for Business Server 2015\Reskit
```

### <a name="purpose"></a><span data-ttu-id="90398-156">Objetivo</span><span class="sxs-lookup"><span data-stu-id="90398-156">Purpose</span></span>

<span data-ttu-id="90398-157">ABSConfig proporciona una forma rápida y fácil de personalizar Skype Empresarial Server de libreta de direcciones de 2015.</span><span class="sxs-lookup"><span data-stu-id="90398-157">ABSConfig provides a quick and easy way to customize Skype for Business Server 2015 Address Book Service.</span></span>

### <a name="requirements"></a><span data-ttu-id="90398-158">Requirements</span><span class="sxs-lookup"><span data-stu-id="90398-158">Requirements</span></span>

#### <a name="computer"></a><span data-ttu-id="90398-159">Equipo</span><span class="sxs-lookup"><span data-stu-id="90398-159">Computer</span></span>

<span data-ttu-id="90398-160">ABSConfig solo se puede ejecutar desde un equipo unido a un dominio que Skype Empresarial Server 2015 instalado.</span><span class="sxs-lookup"><span data-stu-id="90398-160">ABSConfig can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span> <span data-ttu-id="90398-161">En el caso de Skype Empresarial Server 2015, Enterprise Edition, esta herramienta se puede ejecutar en cualquier servidor Front-End que tenga habilitado el servicio de libreta de direcciones durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="90398-161">In the case of Skype for Business Server 2015, Enterprise Edition, this tool can be run on any Front-End servers that have the Address Book Service enabled during setup.</span></span>

#### <a name="network"></a><span data-ttu-id="90398-162">Red</span><span class="sxs-lookup"><span data-stu-id="90398-162">Network</span></span>

<span data-ttu-id="90398-163">El equipo debe poder conectarse a la base Front-End grupo de servidores y la base de datos back-end.</span><span class="sxs-lookup"><span data-stu-id="90398-163">The computer should be able to connect to the Front-End pool and back-end database.</span></span>

#### <a name="software"></a><span data-ttu-id="90398-164">Software</span><span class="sxs-lookup"><span data-stu-id="90398-164">Software</span></span>

<span data-ttu-id="90398-165">Los siguientes componentes de software deben instalarse antes de ejecutar la herramienta ABSConfig:</span><span class="sxs-lookup"><span data-stu-id="90398-165">The following software components must be installed before running the ABSConfig tool:</span></span>

- <span data-ttu-id="90398-166">Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="90398-166">Skype for Business Server 2015</span></span>

#### <a name="users"></a><span data-ttu-id="90398-167">Usuarios</span><span class="sxs-lookup"><span data-stu-id="90398-167">Users</span></span>

<span data-ttu-id="90398-168">Administradores que tienen los permisos necesarios para actualizar la implementación Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="90398-168">Administrators who have the permissions required to update the Skype for Business Server 2015 deployment.</span></span>

### <a name="examples"></a><span data-ttu-id="90398-169">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="90398-169">Examples</span></span>

<span data-ttu-id="90398-170">ABSConfig se puede iniciar escribiendo **ABSConfig.exe** en un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="90398-170">ABSConfig can be started by typing **ABSConfig.exe** at a command prompt.</span></span> <span data-ttu-id="90398-171">A continuación se muestra la interfaz de usuario de la herramienta ABSConfig.</span><span class="sxs-lookup"><span data-stu-id="90398-171">Shown below is the ABSConfig tool user interface.</span></span>

![La ABSConfig.exe de datos.](../media/Reskit_2012_Tools_Documentation_ABSConfig.JPG)

### <a name="summary"></a><span data-ttu-id="90398-173">Resumen</span><span class="sxs-lookup"><span data-stu-id="90398-173">Summary</span></span>

<span data-ttu-id="90398-174">La herramienta ABSConfig proporciona a los administradores una herramienta rápida y fácil de usar para personalizar Skype Empresarial Server de libreta de direcciones de 2015.</span><span class="sxs-lookup"><span data-stu-id="90398-174">The ABSConfig tool provides administrators a quick and easy to use tool to customize Skype for Business Server 2015 Address Book Service.</span></span>

## <a name="bandwidth-policy-service-monitor"></a><span data-ttu-id="90398-175">Monitor de servicio de directivas de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="90398-175">Bandwidth Policy Service Monitor</span></span>
<span data-ttu-id="90398-176"><a name="bpsm"> </a></span><span class="sxs-lookup"><span data-stu-id="90398-176"><a name="bpsm"> </a></span></span>

<span data-ttu-id="90398-177">La herramienta Monitor de servicio de directivas de ancho de banda está diseñada para permitir a los administradores ver una lista de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="90398-177">The Bandwidth Policy Service Monitor tool is intended to allow administrators to view a list of the following:</span></span>

1. <span data-ttu-id="90398-178">Todos los servicios de Skype Empresarial Server de directiva de ancho de banda de 2015 configurados (autenticación y núcleo) en la topología</span><span class="sxs-lookup"><span data-stu-id="90398-178">All the configured Skype for Business Server 2015 Bandwidth Policy services (Authentication and Core) in the topology</span></span>

2. <span data-ttu-id="90398-179">Las conexiones que cada servicio realiza a otros servicios de directiva de ancho de banda y a los servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="90398-179">The connections that each service makes to other Bandwidth Policy services and to the Edge servers</span></span>

3. <span data-ttu-id="90398-180">Todos los vínculos configurados en el documento de configuración de red y el uso de ancho de banda en tiempo real según lo notificado por cada uno de los servicios de directiva de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="90398-180">All the links that are configured in the Network configuration document and real-time bandwidth usage as reported by each of the Bandwidth Policy services</span></span>

### <a name="description"></a><span data-ttu-id="90398-181">Descripción</span><span class="sxs-lookup"><span data-stu-id="90398-181">Description</span></span>

<span data-ttu-id="90398-182">La herramienta Monitor de servicio de directivas de ancho de banda se implementa como una aplicación basada en GUI.</span><span class="sxs-lookup"><span data-stu-id="90398-182">The Bandwidth Policy Service Monitor tool is implemented as a GUI-based application.</span></span> <span data-ttu-id="90398-183">Los administradores inician la herramienta ejecutando PDPMonUI.exe.</span><span class="sxs-lookup"><span data-stu-id="90398-183">Administrators start the tool by running PDPMonUI.exe.</span></span>

<span data-ttu-id="90398-184">Cuando se inicia la herramienta, intenta descubrir la lista de servicios de directiva de ancho de banda en la topología.</span><span class="sxs-lookup"><span data-stu-id="90398-184">When the tool starts, it attempts to discover the list of Bandwidth Policy services in the topology.</span></span> <span data-ttu-id="90398-185">Una vez realizada la actualización inicial, el panel situado a la izquierda de la ventana se rellena con una lista de servicios agrupados por los clústeres a los que pertenecen.</span><span class="sxs-lookup"><span data-stu-id="90398-185">After the initial update is done, the pane to the left of the window is populated with a list of services that are grouped by the clusters that they belong to.</span></span>

<span data-ttu-id="90398-186">Cuando los administradores seleccionan un servicio de directiva de ancho de banda determinado, el panel de la derecha muestra la información sobre ese servicio en particular.</span><span class="sxs-lookup"><span data-stu-id="90398-186">When administrators select a particular Bandwidth Policy Service, the pane on the right displays the information about that particular service.</span></span> <span data-ttu-id="90398-187">Ese panel también tiene dos pestañas principales que muestran información.</span><span class="sxs-lookup"><span data-stu-id="90398-187">That pane also has two main tabs that display information.</span></span>

#### <a name="machine-info-tab"></a><span data-ttu-id="90398-188">Pestaña Información de la máquina</span><span class="sxs-lookup"><span data-stu-id="90398-188">Machine Info Tab</span></span>

<span data-ttu-id="90398-189">La **pestaña Información del** equipo muestra los detalles del servicio de directiva de ancho de banda seleccionado y la lista y el estado de todas las conexiones que realiza el servicio de directivas de ancho de banda seleccionado a otros servicios.</span><span class="sxs-lookup"><span data-stu-id="90398-189">The **Machine Info** tab shows the details of the Bandwidth Policy Service that is selected and the list and state of all the connections that are made by the selected Bandwidth Policy Service to other services.</span></span>

#### <a name="topology-info-tab"></a><span data-ttu-id="90398-190">Pestaña Información de topología</span><span class="sxs-lookup"><span data-stu-id="90398-190">Topology Info Tab</span></span>

<span data-ttu-id="90398-191">La **pestaña Información de** topología muestra una lista de todos los vínculos configurados en las opciones de configuración de red.</span><span class="sxs-lookup"><span data-stu-id="90398-191">The **Topology Info** tab shows a list of all the links that are configured in the Network configuration settings.</span></span> <span data-ttu-id="90398-192">Para cada vínculo, se muestra la capacidad de ancho de banda de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="90398-192">For each link, the audio and video bandwidth capacity is displayed.</span></span> <span data-ttu-id="90398-193">Además, se muestra el ancho de banda utilizado actualmente, tanto en Kbps como como un porcentaje de la capacidad.</span><span class="sxs-lookup"><span data-stu-id="90398-193">Additionally, the currently utilized bandwidth is displayed, both in Kbps and as a percentage of the capacity.</span></span> <span data-ttu-id="90398-194">La herramienta usa la codificación de colores para resaltar vínculos que tienen un uso cercano a la capacidad, lo que permite a los administradores aislar rápidamente dichos vínculos.</span><span class="sxs-lookup"><span data-stu-id="90398-194">The tool uses color-coding to highlight links that have utilization that is close to the capacity—this allows administrators to quickly isolate such links.</span></span>

> [!NOTE]
>  <span data-ttu-id="90398-195">Si la herramienta Detección de servicio de directivas de ancho de banda experimenta  un error  al conectarse a cualquiera de los servicios de directiva de ancho de banda configurados, no se rellenará la información de las pestañas Información del equipo y Información de topología.</span><span class="sxs-lookup"><span data-stu-id="90398-195">If the Bandwidth Policy Service Monitor tool experiences failure when it connects to any of the configured Bandwidth Policy services, the information in the **Machine Info** and the **Topology Info** tabs won't be populated.</span></span> <span data-ttu-id="90398-196">Sin embargo, es posible que la herramienta se conecte inicialmente pero, posteriormente, pierda su conexión con el servicio.</span><span class="sxs-lookup"><span data-stu-id="90398-196">However, it is possible that the tool might connect initially but subsequently lose its connection to the service.</span></span> <span data-ttu-id="90398-197">En estos casos, es posible que los administradores vean información obsoleta.</span><span class="sxs-lookup"><span data-stu-id="90398-197">In such cases, administrators might see outdated information.</span></span> <span data-ttu-id="90398-198">Hay una marca de tiempo **Last Updated** en cada una de las pestañas que puede permitir a los administradores ver cuándo se actualizaron por última vez los datos para un servicio de directivas de ancho de banda determinado.</span><span class="sxs-lookup"><span data-stu-id="90398-198">There is a **Last Updated** time stamp on each of the tabs that can allow administrators to see when the data was last updated for a particular Bandwidth Policy Service.</span></span>

### <a name="output"></a><span data-ttu-id="90398-199">Salida</span><span class="sxs-lookup"><span data-stu-id="90398-199">Output</span></span>

<span data-ttu-id="90398-200">No hay salida de línea de comandos; el resultado del programa se encuentra dentro de la interfaz gráfica de usuario (GUI) principal.</span><span class="sxs-lookup"><span data-stu-id="90398-200">There is no command-line output; the program output is contained within the main graphical user interface (GUI).</span></span>

### <a name="purpose"></a><span data-ttu-id="90398-201">Objetivo</span><span class="sxs-lookup"><span data-stu-id="90398-201">Purpose</span></span>

<span data-ttu-id="90398-202">El propósito de la herramienta Detección de servicios de directivas de ancho de banda es permitir a los administradores visibilidad del estado de cada uno de los servicios de directiva de ancho de banda definidos en la topología.</span><span class="sxs-lookup"><span data-stu-id="90398-202">The purpose of the Bandwidth Policy Service Monitor tool is to allow administrators visibility into the state of each of the Bandwidth Policy services that are defined in the topology.</span></span> <span data-ttu-id="90398-203">Además, los administradores pueden ver el uso de ancho de banda en tiempo real para todos los vínculos definidos en el documento de configuración de red.</span><span class="sxs-lookup"><span data-stu-id="90398-203">In addition, administrators can see real-time bandwidth usage for all the links that are defined in the Network configuration document.</span></span>

### <a name="requirements"></a><span data-ttu-id="90398-204">Requirements</span><span class="sxs-lookup"><span data-stu-id="90398-204">Requirements</span></span>

<span data-ttu-id="90398-205">La herramienta de supervisión del servicio de directivas de ancho de banda debe ejecutarse en un equipo que forma parte de la topología Skype Empresarial Server directiva.</span><span class="sxs-lookup"><span data-stu-id="90398-205">The Bandwidth Policy Service Monitor tool needs to be run on a computer that is part of the Skype for Business Server topology.</span></span>

### <a name="summary"></a><span data-ttu-id="90398-206">Resumen</span><span class="sxs-lookup"><span data-stu-id="90398-206">Summary</span></span>

<span data-ttu-id="90398-207">La herramienta Bandwidth Policy Service Monitor puede ser un recurso valioso para los administradores para que puedan inspeccionar el estado de todos los servicios de directiva de ancho de banda de la topología y, lo que es más importante, pueden obtener el uso del ancho de banda en tiempo real para los vínculos definidos en las opciones de configuración de red.</span><span class="sxs-lookup"><span data-stu-id="90398-207">The Bandwidth Policy Service Monitor tool can be a valuable resource to administrators so they can inspect the state of all the Bandwidth Policy services in the topology—and more importantly—they can obtain real-time bandwidth utilization for the links that are defined in the Network configuration settings.</span></span>

## <a name="bandwidth-utilization-analyzer"></a><span data-ttu-id="90398-208">Analizador de uso de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="90398-208">Bandwidth Utilization Analyzer</span></span>
<span data-ttu-id="90398-209"><a name="bua"> </a></span><span class="sxs-lookup"><span data-stu-id="90398-209"><a name="bua"> </a></span></span>

<span data-ttu-id="90398-210">El Analizador de uso de ancho de banda es una herramienta que crea informes sobre varias vistas del consumo de ancho de banda por parte de los puntos de conexión uc en los vínculos WAN de la red empresarial.</span><span class="sxs-lookup"><span data-stu-id="90398-210">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network.</span></span> <span data-ttu-id="90398-211">Estos informes se pueden usar para comprender el patrón de consumo de ancho de banda actual y para ayudar en la planeación de la capacidad de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="90398-211">These reports can be used to understand the current bandwidth consumption pattern and to aid in bandwidth capacity planning.</span></span>

### <a name="description"></a><span data-ttu-id="90398-212">Descripción</span><span class="sxs-lookup"><span data-stu-id="90398-212">Description</span></span>

<span data-ttu-id="90398-213">El Analizador de uso de ancho de banda se implementa como una aplicación basada en GUI.</span><span class="sxs-lookup"><span data-stu-id="90398-213">Bandwidth Utilization Analyzer is implemented as a GUI-based application.</span></span> <span data-ttu-id="90398-214">Esta herramienta genera informes específicamente para el uso de audio en toda la red y ayuda con la planeación de capacidad.</span><span class="sxs-lookup"><span data-stu-id="90398-214">This tool generates reports specifically for audio utilization across the network and helps with capacity planning.</span></span> <span data-ttu-id="90398-215">También itera en la capacidad de ancho de banda que se asigna a varios vínculos.</span><span class="sxs-lookup"><span data-stu-id="90398-215">It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

### <a name="output"></a><span data-ttu-id="90398-216">Salida</span><span class="sxs-lookup"><span data-stu-id="90398-216">Output</span></span>

<span data-ttu-id="90398-217">El Analizador de uso de ancho de banda proporciona gráficas gráficas de capacidad de ancho de banda y uso de audio para todos los vínculos WAN configurados en el sistema.</span><span class="sxs-lookup"><span data-stu-id="90398-217">Bandwidth Utilization Analyzer provides graphical plots of bandwidth capacity and utilization for audio for all the WAN links that are configured in the system.</span></span>

### <a name="purpose"></a><span data-ttu-id="90398-218">Objetivo</span><span class="sxs-lookup"><span data-stu-id="90398-218">Purpose</span></span>

<span data-ttu-id="90398-219">En cualquier implementación de voz y vídeo, es fundamental supervisar y comprender la tendencia del uso del ancho de banda del tráfico multimedia en toda la red empresarial.</span><span class="sxs-lookup"><span data-stu-id="90398-219">In any voice and video deployment, it's critical to monitor and understand the trend of bandwidth utilization of media traffic across the enterprise network.</span></span> <span data-ttu-id="90398-220">La herramienta Analizador de uso de ancho de banda permite que un administrador logre eso.</span><span class="sxs-lookup"><span data-stu-id="90398-220">The Bandwidth Utilization Analyzer tool allows an administrator to achieve just that.</span></span> <span data-ttu-id="90398-221">Esta herramienta hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="90398-221">This tool does the following:</span></span>

- <span data-ttu-id="90398-222">Genera informes específicos para el uso de audio en toda la red</span><span class="sxs-lookup"><span data-stu-id="90398-222">Generates specific reports for audio utilization across the network</span></span>

- <span data-ttu-id="90398-223">Ayuda con una planeación e iteración de capacidad más eficaces en la capacidad de ancho de banda que se asigna a varios vínculos</span><span class="sxs-lookup"><span data-stu-id="90398-223">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="90398-224">El Analizador de uso de ancho de banda puede generar trazados gráficos de informes de uso y capacidad de ancho de banda; son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="90398-224">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and utilization reports; they are as follows:</span></span>

- <span data-ttu-id="90398-225">Todos los vínculos WAN de la red empresarial</span><span class="sxs-lookup"><span data-stu-id="90398-225">All the WAN links in the enterprise network</span></span>

- <span data-ttu-id="90398-226">Filtrado por vínculos WAN seleccionados que se han elegido</span><span class="sxs-lookup"><span data-stu-id="90398-226">Filtered by selected WAN links that have been chosen</span></span>

- <span data-ttu-id="90398-227">Filtrado por vínculos WAN que han excedido la capacidad de vínculos</span><span class="sxs-lookup"><span data-stu-id="90398-227">Filtered by WAN links that have exceeded link capacity</span></span>

- <span data-ttu-id="90398-228">Filtrado por vínculos WAN que han usado poco el ancho de banda aprovisionado</span><span class="sxs-lookup"><span data-stu-id="90398-228">Filtered by WAN links that have been under-utilizing the provisioned bandwidth</span></span>

- <span data-ttu-id="90398-229">Filtrar por vínculos WAN que han llegado a niveles críticos (un uso de ancho de banda superior al 90 % de la capacidad de ancho de banda del vínculo WAN)</span><span class="sxs-lookup"><span data-stu-id="90398-229">Filter by WAN links that have been reaching critical levels (a bandwidth utilization that is greater than 90% of bandwidth capacity of the WAN link)</span></span>

- <span data-ttu-id="90398-230">Filtrado por tipo de vínculo WAN: vínculos de sitio de red, vínculos interregionales y vínculos dentro de un sitio</span><span class="sxs-lookup"><span data-stu-id="90398-230">Filtered by WAN link type—network-site links, interregional links, and links within a site</span></span>

- <span data-ttu-id="90398-231">Filtrado por región de red</span><span class="sxs-lookup"><span data-stu-id="90398-231">Filtered by network region</span></span>

#### <a name="applications"></a><span data-ttu-id="90398-232">Aplicaciones</span><span class="sxs-lookup"><span data-stu-id="90398-232">Applications</span></span>

<span data-ttu-id="90398-233">El Analizador de uso de ancho de banda tiene las siguientes dos aplicaciones (herramientas):</span><span class="sxs-lookup"><span data-stu-id="90398-233">Bandwidth Utilization Analyzer has the following two applications (tools):</span></span>

- <span data-ttu-id="90398-234">**WanLinkLogCollector.exe** Esta herramienta permite al usuario introducir la información necesaria.</span><span class="sxs-lookup"><span data-stu-id="90398-234">**WanLinkLogCollector.exe** This tool enables its user to input the required information.</span></span>

- <span data-ttu-id="90398-235">**BandwidthUtilizationAnalyzer.xlsm** Un Microsoft Excel de software de hoja de cálculo se inicia automáticamente mediante WanLinkLogCollector.exe.</span><span class="sxs-lookup"><span data-stu-id="90398-235">**BandwidthUtilizationAnalyzer.xlsm** A Microsoft Excel spreadsheet software report is automatically launched by WanLinkLogCollector.exe.</span></span> <span data-ttu-id="90398-236">Esta aplicación permite al usuario aplicar filtros al informe, como se muestra más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="90398-236">This application allows the user to apply filters to the report as shown later in this article.</span></span>

#### <a name="phases-of-using-bandwidth-utilization-analyzer"></a><span data-ttu-id="90398-237">Fases de uso del analizador de uso de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="90398-237">Phases of Using Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="90398-238">Hay dos fases al usar el Analizador de uso de ancho de banda:</span><span class="sxs-lookup"><span data-stu-id="90398-238">There are two phases when using Bandwidth Utilization Analyzer:</span></span>

- <span data-ttu-id="90398-239">Recopilar registros, que se realizan mediante WanLinkLogCollector.exe</span><span class="sxs-lookup"><span data-stu-id="90398-239">Collect logs, which are performed by using WanLinkLogCollector.exe</span></span>

- <span data-ttu-id="90398-240">Personalizar informes, que se realizan mediante BandwidthUtilizationAnalyzer.xlsm</span><span class="sxs-lookup"><span data-stu-id="90398-240">Customize reports, which are performed by using BandwidthUtilizationAnalyzer.xlsm</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="90398-241">Se recomienda encarecidamente que BandwidthUtilizationAnalyzer.xlsm no se inicia manualmente por parte de los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="90398-241">We strongly recommend that BandwidthUtilizationAnalyzer.xlsm not be manually launched by end users.</span></span>

#### <a name="starting-bandwidth-utilization-analyzer"></a><span data-ttu-id="90398-242">Iniciar analizador de uso de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="90398-242">Starting Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="90398-243">Inicie WanLinkLogCollector.exe en el símbolo del sistema o mediante Windows Explorer.</span><span class="sxs-lookup"><span data-stu-id="90398-243">Start WanLinkLogCollector.exe at the command prompt or by using Windows Explorer.</span></span>

 <span data-ttu-id="90398-244">**Uso de WanLinkLogCollector.exe**</span><span class="sxs-lookup"><span data-stu-id="90398-244">**Using WanLinkLogCollector.exe**</span></span>

<span data-ttu-id="90398-245">Hay tres pasos para usar WanLinkLogCollector.exe:</span><span class="sxs-lookup"><span data-stu-id="90398-245">There are three steps to using WanLinkLogCollector.exe:</span></span>

1. <span data-ttu-id="90398-246">**Registrar la escala de tiempo** Proporcionar la escala de tiempo para la que debe generarse el informe</span><span class="sxs-lookup"><span data-stu-id="90398-246">**Log the timeline** Provide the timeline that the report needs to be generated for</span></span>

2. <span data-ttu-id="90398-247">**Especificar los directorios de archivos** Proporcionar información de ubicación de archivos</span><span class="sxs-lookup"><span data-stu-id="90398-247">**Specify the file directories** Provide file location information</span></span>

3. <span data-ttu-id="90398-248">**Recopilar los registros e iniciar el visor de informes** Ejecutar el comando para generar el informe</span><span class="sxs-lookup"><span data-stu-id="90398-248">**Collect the logs and launch the report viewer** Execute the command to generate the report</span></span>

#### <a name="step-1---log-the-timeline"></a><span data-ttu-id="90398-249">Paso 1: registrar la escala de tiempo</span><span class="sxs-lookup"><span data-stu-id="90398-249">Step 1 - Log the timeline</span></span>

<span data-ttu-id="90398-250">El registro de la escala de tiempo permite al usuario de la herramienta especificar lo siguiente como se muestra en la figura siguiente.</span><span class="sxs-lookup"><span data-stu-id="90398-250">Logging the timeline allows the tool user to specify the following as shown in the figure below.</span></span>

1. <span data-ttu-id="90398-251">**Fecha de inicio** Esta es la fecha de inicio de la escala de tiempo para la que se va a generar el informe; por ejemplo, el 1 de agosto de 2010.</span><span class="sxs-lookup"><span data-stu-id="90398-251">**Start date** This is the start date of the timeline that the report is to be generated for; for example, August 1, 2010.</span></span>

2. <span data-ttu-id="90398-252">**Fecha de finalización** Esta es la fecha de finalización de la escala de tiempo para la que se va a generar el informe; por ejemplo, 30 de septiembre de 2010.</span><span class="sxs-lookup"><span data-stu-id="90398-252">**End date** This is the end date of the timeline that the report is to be generated for; for example, September 30, 2010.</span></span>

     ![Fechas de inicio y finalización en el uso de ancho de banda A](../media/Reskit_2012_Tools_Documentation_Image4.jpg)

#### <a name="step-2---specify-the-file-directories"></a><span data-ttu-id="90398-254">Paso 2: especificar los directorios de archivos</span><span class="sxs-lookup"><span data-stu-id="90398-254">Step 2 - Specify the file directories</span></span>

<span data-ttu-id="90398-255">El usuario puede especificar los siguientes directorios de archivos como se muestra.</span><span class="sxs-lookup"><span data-stu-id="90398-255">The following file directories can be specified by the user as shown.</span></span>

- <span data-ttu-id="90398-256">**Ubicación de los archivos de registro del servidor** Ubicación de carpeta donde se almacenan los registros del servidor de directivas de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="90398-256">**Server log files location** The folder location where Bandwidth policy server logs are stored.</span></span> <span data-ttu-id="90398-257">Esto suele estar en \<fileserver\> \\<de FE \> \AppServerFiles\PDP.</span><span class="sxs-lookup"><span data-stu-id="90398-257">This is typically in \<fileserver\>\\<choice of FE\>\AppServerFiles\PDP.</span></span>

- <span data-ttu-id="90398-258">**Ubicación de almacenamiento temporal de archivos** Ubicación de archivo temporal donde se almacenan los archivos intermedios mientras se genera el informe.</span><span class="sxs-lookup"><span data-stu-id="90398-258">**Temporary file storage location** The temporary file location where intermediate files are stored while the report is being generated.</span></span>

    ![Directorios de archivos en el anal de uso de ancho de banda](../media/Reskit_2012_Tools_Documentation_Image5.jpg)

    > [!NOTE]
    > <span data-ttu-id="90398-260">Asegúrese de que se proporciona suficiente acceso a los registros del servidor y a la carpeta de almacén de archivos temporales al usuario de la herramienta.</span><span class="sxs-lookup"><span data-stu-id="90398-260">Ensure that sufficient file access to the server logs and the temporary file store folder is provided to the tool user.</span></span>

#### <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a><span data-ttu-id="90398-261">Paso 3: recopilar los registros e iniciar el visor de informes</span><span class="sxs-lookup"><span data-stu-id="90398-261">Step 3 - Collect the logs and start the report viewer</span></span>

<span data-ttu-id="90398-262">Para recopilar los registros e iniciar el visor de informes, haga clic **en Ejecutar** como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="90398-262">To collect the logs and start the report viewer, click **Execute** as shown below.</span></span> <span data-ttu-id="90398-263">En este paso se recopilan los datos necesarios.</span><span class="sxs-lookup"><span data-stu-id="90398-263">This step collects the required data.</span></span>

![Recopilación de datos en el análisis de uso de ancho de banda](../media/Reskit_2012_Tools_Documentation_Image6.jpg)

<span data-ttu-id="90398-265">Cuando la validación de entrada se realiza correctamente, se muestra el mensaje que se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="90398-265">When the input validation is successful, the message shown below is displayed.</span></span>

![Registra la notificación recopilada en el Utili de ancho de banda](../media/Reskit_2012_Tools_Documentation_Image7.jpg)

<span data-ttu-id="90398-267">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="90398-267">Click **OK**.</span></span> <span data-ttu-id="90398-268">BandwidthUtilizationAnalyzer.xlsm se inicia automáticamente.</span><span class="sxs-lookup"><span data-stu-id="90398-268">BandwidthUtilizationAnalyzer.xlsm is automatically started.</span></span> <span data-ttu-id="90398-269">Siga las instrucciones del cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="90398-269">Follow the instructions in the message box.</span></span> <span data-ttu-id="90398-270">Para obtener más información, **consulte Using BandwidthUtilizationAnalyzer.xlsm** en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="90398-270">For details, see **Using BandwidthUtilizationAnalyzer.xlsm** in the next section.</span></span>


### <a name="using-bandwidthutilizationanalyzerxlsm"></a><span data-ttu-id="90398-271">Uso BandwidthUtilizationAnalyzer.xlsm</span><span class="sxs-lookup"><span data-stu-id="90398-271">Using BandwidthUtilizationAnalyzer.xlsm</span></span>

1. <span data-ttu-id="90398-272">Cuando BandwidthUtilizationAnalyzer.xlsm se inicie automáticamente, haga clic **en Actualizar** como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="90398-272">When BandwidthUtilizationAnalyzer.xlsm is automatically started, click **Refresh** as shown below.</span></span>

     ![BandwidthUtilizationAnalyzer.xlsm](../media/Reskit_2012_Tools_Documentation_Image8.jpg)

2. <span data-ttu-id="90398-274">Cuando se abra una carpeta de archivos, seleccione consolidated.csv de la ubicación especificada en el cuadro de mensaje como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="90398-274">When a file folder is opened, select consolidated.csv from the location that is specified in the message box as shown below.</span></span> <span data-ttu-id="90398-275">También muestra la ubicación como **C:\Temp**.</span><span class="sxs-lookup"><span data-stu-id="90398-275">It also shows the location as **C:\Temp**.</span></span>

     ![Abrir una carpeta en BandwidthUtilizationAnalyzer.](../media/Reskit_2012_Tools_Documentation_Image9.jpg)

3. <span data-ttu-id="90398-277">Haga clic en **Importar**.</span><span class="sxs-lookup"><span data-stu-id="90398-277">Click **Import**.</span></span>

4. <span data-ttu-id="90398-278">El trazado gráfico se genera automáticamente.</span><span class="sxs-lookup"><span data-stu-id="90398-278">The graphical plot is automatically generated.</span></span> <span data-ttu-id="90398-279">Está disponible cuando desaparece el puntero de trabajo en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="90398-279">It is available when the working-in-the-background pointer disappears.</span></span>

     ![Aplicación de filtros en la vista Informe.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

#### <a name="applying-filters-to-the-report-view"></a><span data-ttu-id="90398-281">Aplicación de filtros a la vista informe</span><span class="sxs-lookup"><span data-stu-id="90398-281">Applying Filters to the Report View</span></span>

<span data-ttu-id="90398-282">Los filtros que se pueden aplicar a la vista de informe como se muestra a continuación se describen de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="90398-282">The filters that can be applied to the report view as shown below are described as follows:</span></span>

![Aplicación de filtros en la vista Informe.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

1. <span data-ttu-id="90398-284">**Nombre** Filtrar por vínculos WAN (el filtro está en el lado derecho del gráfico).</span><span class="sxs-lookup"><span data-stu-id="90398-284">**Name** Filter by WAN links (the filter is on the right side of the graph).</span></span> <span data-ttu-id="90398-285">El prefijo indica los siguientes tipos de vínculos; vea el cuadro vertical (azul):</span><span class="sxs-lookup"><span data-stu-id="90398-285">The prefix denotes the following link types; see the vertical (blue) box:</span></span>

   - <span data-ttu-id="90398-286">**Sitio S** Vínculo WAN de un sitio de red a una región de red</span><span class="sxs-lookup"><span data-stu-id="90398-286">**S Site** The WAN link from a network site to a network region</span></span>

   - <span data-ttu-id="90398-287">**IS Entre sitios** Vínculo WAN entre dos sitios de red</span><span class="sxs-lookup"><span data-stu-id="90398-287">**IS Inter-Site** The WAN link between two network sites</span></span>

   - <span data-ttu-id="90398-288">**R Entre regiones** El vínculo WAN entre dos regiones de red</span><span class="sxs-lookup"><span data-stu-id="90398-288">**R Inter-Region** The WAN link between two network region</span></span>

2. <span data-ttu-id="90398-289">**Límite excedido** Filtrar por vínculos WAN cuyo uso de ancho de banda es mayor que la capacidad de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="90398-289">**Exceeded limit** Filter by WAN links whose bandwidth utilization is more than the bandwidth capacity</span></span>

3. <span data-ttu-id="90398-290">**Niveles críticos** Filtrar por vínculos WAN cuyo uso de ancho de banda ha alcanzado el 90 % o más de la capacidad de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="90398-290">**Critical levels** Filter by WAN links whose bandwidth utilization has reached 90% or more than the bandwidth capacity</span></span>

4. <span data-ttu-id="90398-291">**Infrautilizó** Filtrar por vínculos WAN cuyo uso de ancho de banda ha sido inferior al 25 % de la capacidad de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="90398-291">**Under-utilized** Filter by WAN links whose bandwidth utilization has been less than 25% of the bandwidth capacity</span></span>

5. <span data-ttu-id="90398-292">**Tipo de vínculo** Filtrar por los siguientes tipos de vínculos WAN:</span><span class="sxs-lookup"><span data-stu-id="90398-292">**Link type** Filter by the following WAN links types:</span></span>

   - <span data-ttu-id="90398-293">**Tipo de sitio de** red</span><span class="sxs-lookup"><span data-stu-id="90398-293">**Network site** type</span></span>

   - <span data-ttu-id="90398-294">**Tipo entre sitios**</span><span class="sxs-lookup"><span data-stu-id="90398-294">**Inter-site** type</span></span>

   - <span data-ttu-id="90398-295">**Tipo de vínculo entre regiones**</span><span class="sxs-lookup"><span data-stu-id="90398-295">**Inter-Region link** type</span></span>

6. <span data-ttu-id="90398-296">**Región** Filtrar por región de red</span><span class="sxs-lookup"><span data-stu-id="90398-296">**Region** Filter by network region</span></span>

<span data-ttu-id="90398-297">Las siguientes cifras muestran los filtros descritos anteriormente.</span><span class="sxs-lookup"><span data-stu-id="90398-297">The following figures show the previously described filters.</span></span>

<span data-ttu-id="90398-298">Filtrar por **nombre**.</span><span class="sxs-lookup"><span data-stu-id="90398-298">Filter by **Name**.</span></span> <span data-ttu-id="90398-299">Seleccione la lista de vínculos que deben mostrarse en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="90398-299">Select the list of links that need to be displayed in the graph.</span></span>

![Filtrado por nombre en BandwidthUtilizationAnalyzer.](../media/Reskit_2012_Tools_Documentation_Image12.jpg)

<span data-ttu-id="90398-301">Filtrar por **límite excedido**.</span><span class="sxs-lookup"><span data-stu-id="90398-301">Filter by **Exceeded limit**.</span></span> <span data-ttu-id="90398-302">Seleccione **True** para aplicar el filtro.</span><span class="sxs-lookup"><span data-stu-id="90398-302">Select **True** to enforce the filter.</span></span>

![Filtrado por límite excedido.](../media/Reskit_2012_Tools_Documentation_Image13.jpg)

<span data-ttu-id="90398-304">Filtrar por **niveles críticos**.</span><span class="sxs-lookup"><span data-stu-id="90398-304">Filter by **Critical levels**.</span></span> <span data-ttu-id="90398-305">Seleccione **True** para aplicar el filtro.</span><span class="sxs-lookup"><span data-stu-id="90398-305">Select **True** to enforce the filter.</span></span>

![Filtrado por niveles críticos.](../media/Reskit_2012_Tools_Documentation_Image14.jpg)

<span data-ttu-id="90398-307">Filter by **Under used**.</span><span class="sxs-lookup"><span data-stu-id="90398-307">Filter by **Under utilized**.</span></span> <span data-ttu-id="90398-308">Seleccione **True** para aplicar el filtro.</span><span class="sxs-lookup"><span data-stu-id="90398-308">Select **True** to enforce the filter.</span></span>

![Filtrado por UnderUtilizó.](../media/Reskit_2012_Tools_Documentation_Image15.jpg)

<span data-ttu-id="90398-310">Filtrar por **tipo de vínculo**.</span><span class="sxs-lookup"><span data-stu-id="90398-310">Filter by **Link Type**.</span></span> <span data-ttu-id="90398-311">Seleccione el tipo o los tipos que deben mostrarse.</span><span class="sxs-lookup"><span data-stu-id="90398-311">Select the type or types that need to be displayed.</span></span>

![Filtrado por tipo de vínculo.](../media/Reskit_2012_Tools_Documentation_Image16.jpg)

<span data-ttu-id="90398-313">Filtrar por **región**.</span><span class="sxs-lookup"><span data-stu-id="90398-313">Filter by **Region**.</span></span> <span data-ttu-id="90398-314">Seleccione una lista de regiones cuyos vínculos deben mostrarse.</span><span class="sxs-lookup"><span data-stu-id="90398-314">Select a list of regions whose links need to be displayed.</span></span>

![Filtrado por región.](../media/Reskit_2012_Tools_Documentation_Image17.jpg)

### <a name="requirements"></a><span data-ttu-id="90398-316">Requirements</span><span class="sxs-lookup"><span data-stu-id="90398-316">Requirements</span></span>

- <span data-ttu-id="90398-317">El .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="90398-317">The .NET Framework 3.5</span></span>

- <span data-ttu-id="90398-318">Microsoft Excel 2010 o Excel 2007</span><span class="sxs-lookup"><span data-stu-id="90398-318">Microsoft Excel 2010 or Excel 2007</span></span>

### <a name="summary"></a><span data-ttu-id="90398-319">Resumen</span><span class="sxs-lookup"><span data-stu-id="90398-319">Summary</span></span>

<span data-ttu-id="90398-320">El Analizador de uso de ancho de banda se usa para trazar el uso del ancho de banda de audio para el tráfico UC en toda la red.</span><span class="sxs-lookup"><span data-stu-id="90398-320">Bandwidth Utilization Analyzer is used to plot the audio bandwidth utilization for UC traffic across the network.</span></span> <span data-ttu-id="90398-321">Esta herramienta también se puede usar para informar del uso del ancho de banda de vídeo en la red.</span><span class="sxs-lookup"><span data-stu-id="90398-321">This tool can be used to report the utilization of video bandwidth on the network as well.</span></span>

## <a name="call-parkometer"></a><span data-ttu-id="90398-322">Parkometer de llamadas</span><span class="sxs-lookup"><span data-stu-id="90398-322">Call Parkometer</span></span>
<span data-ttu-id="90398-323"><a name="callpark"> </a></span><span class="sxs-lookup"><span data-stu-id="90398-323"><a name="callpark"> </a></span></span>

<span data-ttu-id="90398-324">Call Parkometer es una aplicación de línea de comandos que proporciona un fácil acceso a la base de datos de órbitas de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="90398-324">Call Parkometer is a command-line application that provides easy access to the Call Park orbit database.</span></span>

### <a name="description"></a><span data-ttu-id="90398-325">Descripción</span><span class="sxs-lookup"><span data-stu-id="90398-325">Description</span></span>

<span data-ttu-id="90398-326">El Parkometer de llamadas es una herramienta para realizar un seguimiento de las llamadas estacionadas actualmente.</span><span class="sxs-lookup"><span data-stu-id="90398-326">Call Parkometer is a tool to track currently parked calls.</span></span> <span data-ttu-id="90398-327">También recopila estadísticas sobre órbitas y uso del servidor de estacionamiento de llamadas (CPS).</span><span class="sxs-lookup"><span data-stu-id="90398-327">It also collects statistics about orbits and Call Park Server (CPS) usage.</span></span> <span data-ttu-id="90398-328">Esta herramienta de línea de comandos proporciona acceso de lectura y escritura a la órbita cps SQL Server base de datos desde un equipo local o conectado remotamente.</span><span class="sxs-lookup"><span data-stu-id="90398-328">This command-line tool provides both read and write-access to the CPS orbit SQL Server database from a local or remotely connected computer.</span></span>

<span data-ttu-id="90398-329">Todas las opciones son mutuamente excluyentes.</span><span class="sxs-lookup"><span data-stu-id="90398-329">All options are mutually exclusive.</span></span> <span data-ttu-id="90398-330">La sintaxis de línea de comandos es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="90398-330">Command-line syntax is as follows:</span></span>

- <span data-ttu-id="90398-331">**Parámetro -o:** enumera todos los intervalos de órbitas configurados para este grupo.</span><span class="sxs-lookup"><span data-stu-id="90398-331">**-o** parameter—lists all orbit ranges configured for this pool.</span></span>

- <span data-ttu-id="90398-332">**Parámetro -n:** enumera todas las órbitas usadas actualmente en este grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="90398-332">**-n** parameter—lists all currently used orbits in this pool.</span></span> <span data-ttu-id="90398-333">La información mostrada es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="90398-333">The information displayed is as follows:</span></span>

  - <span data-ttu-id="90398-334">Identificador uniforme de recursos SIP (URI) del estacionamiento y el estacionamiento.</span><span class="sxs-lookup"><span data-stu-id="90398-334">SIP Uniform Resource Identifier (URI) of the parkee and parker.</span></span>

  - <span data-ttu-id="90398-335">Nombre de host del CPS donde está estacionada la llamada.</span><span class="sxs-lookup"><span data-stu-id="90398-335">Host name of the CPS where the call is parked.</span></span>

  - <span data-ttu-id="90398-336">Marca de hora del momento en que se estacionó la llamada.</span><span class="sxs-lookup"><span data-stu-id="90398-336">Time stamp of when the call was parked.</span></span>

- <span data-ttu-id="90398-337">**Parámetro -f:** enumera el número de órbitas libres actualmente en el grupo.</span><span class="sxs-lookup"><span data-stu-id="90398-337">**-f** parameter—lists the number of currently free orbits in the pool.</span></span>

- <span data-ttu-id="90398-338">**-r \<n\>** parameter: enumera las \<n\> últimas llamadas estacionadas.</span><span class="sxs-lookup"><span data-stu-id="90398-338">**-r \<n\>** parameter—lists the \<n\> last parked calls.</span></span> <span data-ttu-id="90398-339">La información mostrada es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="90398-339">The information displayed is as follows:</span></span>

  - <span data-ttu-id="90398-340">URI de SIP parkee.</span><span class="sxs-lookup"><span data-stu-id="90398-340">Parkee SIP URI.</span></span>

  - <span data-ttu-id="90398-341">URI de SIP de Parker.</span><span class="sxs-lookup"><span data-stu-id="90398-341">Parker SIP URI.</span></span>

  - <span data-ttu-id="90398-342">Nombre de host del CPS donde se estacionó la llamada.</span><span class="sxs-lookup"><span data-stu-id="90398-342">Host name of the CPS where the call was parked.</span></span>

  - <span data-ttu-id="90398-343">Marca de hora de cuándo se recuperó o se soltó la llamada.</span><span class="sxs-lookup"><span data-stu-id="90398-343">Time stamp of when the call was retrieved or dropped.</span></span>

- <span data-ttu-id="90398-344">**-t \<n\>** parámetro: prueba la reserva de una órbita en la base de datos para mostrar la aleatoriedad de los números de órbita asignados.</span><span class="sxs-lookup"><span data-stu-id="90398-344">**-t\<n\>** parameter - tests reserving an orbit in the database to show the randomness of the assigned orbit numbers.</span></span>

### <a name="output"></a><span data-ttu-id="90398-345">Salida</span><span class="sxs-lookup"><span data-stu-id="90398-345">Output</span></span>

<span data-ttu-id="90398-346">Según los parámetros de entrada especificados en un símbolo del sistema, El parkómetro de llamadas muestra la salida siguiente:</span><span class="sxs-lookup"><span data-stu-id="90398-346">Depending on the input parameters that are specified at a command prompt, Call Parkometer displays the following output:</span></span>

- <span data-ttu-id="90398-347">Todos los intervalos de órbitas configurados para este grupo</span><span class="sxs-lookup"><span data-stu-id="90398-347">All orbit ranges that are configured for this pool</span></span>

- <span data-ttu-id="90398-348">Llamadas estacionadas actualmente</span><span class="sxs-lookup"><span data-stu-id="90398-348">Currently parked calls</span></span>

- <span data-ttu-id="90398-349">Número de órbitas libres (disponibles)</span><span class="sxs-lookup"><span data-stu-id="90398-349">Number of free (available) orbits</span></span>

- <span data-ttu-id="90398-350">Llamadas estacionadas recientemente</span><span class="sxs-lookup"><span data-stu-id="90398-350">Recently parked calls</span></span>

- <span data-ttu-id="90398-351">Órbitas reservadas para probar valores de órbita uniformes y aleatorios</span><span class="sxs-lookup"><span data-stu-id="90398-351">Reserved orbits for testing uniform and random orbit values</span></span>

### <a name="purpose"></a><span data-ttu-id="90398-352">Objetivo</span><span class="sxs-lookup"><span data-stu-id="90398-352">Purpose</span></span>

<span data-ttu-id="90398-353">El propósito de la herramienta CPS es proporcionar acceso a la línea de comandos a la base de datos cps.</span><span class="sxs-lookup"><span data-stu-id="90398-353">The purpose of the CPS tool is to provide command-line access to the CPS database.</span></span> <span data-ttu-id="90398-354">El administrador puede ver el uso de CPS y determinar el número de órbitas asignadas a un grupo.</span><span class="sxs-lookup"><span data-stu-id="90398-354">The administrator can view the CPS usage and determine the number of orbits assigned to a pool.</span></span>

### <a name="requirements"></a><span data-ttu-id="90398-355">Requirements</span><span class="sxs-lookup"><span data-stu-id="90398-355">Requirements</span></span>

<span data-ttu-id="90398-356">No hay requisitos si esta herramienta se ejecuta en el mismo equipo que ejecuta CPS.</span><span class="sxs-lookup"><span data-stu-id="90398-356">There are no requirements if this tool is run on the same computer that is running CPS.</span></span> <span data-ttu-id="90398-357">Si esta herramienta se ejecuta en un equipo remoto, la base de datos SQL Server que usa Skype Empresarial Server 2015 debe configurarse para permitir el acceso remoto.</span><span class="sxs-lookup"><span data-stu-id="90398-357">If this tool is run on a remote computer, the SQL Server database used by Skype for Business Server 2015 must be configured to allow remote access.</span></span> <span data-ttu-id="90398-358">El Parkometer de llamadas debe configurarse con una SQL Server de conexión de base de datos para conectarse a la red del grupo SQL Server.</span><span class="sxs-lookup"><span data-stu-id="90398-358">Call Parkometer must be configured with a SQL Server database connection string to connect to the pool's SQL Server.</span></span> <span data-ttu-id="90398-359">Esta SQL Server de conexión de base de datos se define en el archivo de **configuración,parkometer.exe.config**. Debe colocarse en el mismo directorio donde parkometer.exe se encuentra.</span><span class="sxs-lookup"><span data-stu-id="90398-359">This SQL Server database connection string is defined in the configuration file, **parkometer.exe.config**. It must be placed in the same directory where parkometer.exe is located.</span></span> <span data-ttu-id="90398-360">El siguiente archivo XML es un ejemplo de una parkometer.exe.config. Los parámetros que deben configurarse son nombre de usuario (por ejemplo, mydomain\Administrator), contraseña (por ejemplo, mypassword) y nombre de host (por ejemplo, myserver).</span><span class="sxs-lookup"><span data-stu-id="90398-360">The following XML file is an example of a parkometer.exe.config. The parameters that must be configured are user name (for example, mydomain\Administrator), password (for example, mypassword), and host name (for example, myserver).</span></span>

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

### <a name="examples"></a><span data-ttu-id="90398-361">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="90398-361">Examples</span></span>

<span data-ttu-id="90398-362">Intervalos de órbita implementados: el parámetro -o enumera todos los intervalos de órbitas que están configurados para este grupo, como se muestra</span><span class="sxs-lookup"><span data-stu-id="90398-362">Deployed orbit ranges: the -o parameter lists all orbit ranges that are configured for this pool as shown</span></span>

![Rangos de órbitas en el Parkometer de llamadas.](../media/Reskit_2012_Tools_Documentation_Image18.jpg)

<span data-ttu-id="90398-364">Llamadas estacionadas actualmente: el parámetro -n enumera todas las órbitas usadas actualmente en este grupo como se muestra</span><span class="sxs-lookup"><span data-stu-id="90398-364">Currently parked calls: the -n parameter lists all currently used orbits on this pool as shown</span></span>

![Llamadas actualmente estacionadas en el Parkometer de llamadas.](../media/Reskit_2012_Tools_Documentation_Image19.jpg)

<span data-ttu-id="90398-366">Número de órbitas libres: el parámetro -f enumera el número de órbitas libres actualmente en el grupo como se muestra</span><span class="sxs-lookup"><span data-stu-id="90398-366">Number of free orbits: the -f parameter lists the number of currently free orbits in the pool as shown</span></span>

![Órbitas libres en el Parkometer de llamadas.](../media/Reskit_2012_Tools_Documentation_Image20.jpg)

<span data-ttu-id="90398-368">Llamadas estacionadas recientemente: el parámetro -r \<n\> enumera las \<n\> últimas llamadas estacionadas como se muestra</span><span class="sxs-lookup"><span data-stu-id="90398-368">Recently parked calls: the -r \<n\> parameter lists the \<n\> last parked calls as shown</span></span>

![Llamadas estacionadas recientemente en el Parkometer de llamadas.](../media/Reskit_2012_Tools_Documentation_Image21.jpg)

<span data-ttu-id="90398-370">Reserva de órbita de prueba: las pruebas de parámetro -t \<n\> que reservan una órbita en la base de datos como se muestra</span><span class="sxs-lookup"><span data-stu-id="90398-370">Test orbit reservation: the -t \<n\> parameter tests reserving an orbit in the database as shown</span></span>

![Probar reservas de órbitas en el Parkometer de llamadas.](../media/Reskit_2012_Tools_Documentation_Image22.jpg)

### <a name="summary"></a><span data-ttu-id="90398-372">Resumen</span><span class="sxs-lookup"><span data-stu-id="90398-372">Summary</span></span>

<span data-ttu-id="90398-373">Call Parkometer es una herramienta de línea de comandos que proporciona información detallada sobre el servidor de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="90398-373">Call Parkometer is a command-line tool that provides detailed information about the Call Park Server.</span></span>

## <a name="dbanalyze"></a><span data-ttu-id="90398-374">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="90398-374">DBAnalyze</span></span>
<span data-ttu-id="90398-375"><a name="dba"> </a></span><span class="sxs-lookup"><span data-stu-id="90398-375"><a name="dba"> </a></span></span>

### <a name="description"></a><span data-ttu-id="90398-376">Descripción</span><span class="sxs-lookup"><span data-stu-id="90398-376">Description</span></span>

<span data-ttu-id="90398-377">DBAnalyze es una herramienta de línea de comandos que ayuda a los administradores a recopilar informes de análisis sobre las bases de datos Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="90398-377">DBAnalyze is a command-line tool that helps administrators to gather analysis reports about the Skype for Business Server 2015 databases.</span></span> <span data-ttu-id="90398-378">DBAnalyze tiene los siguientes modos: diagnóstico, datos de usuario, conferencia, MCO y fragmentación de disco:</span><span class="sxs-lookup"><span data-stu-id="90398-378">DBAnalyze has the following modes: diagnostic, user data, conference, MCUs, and disk fragmentation:</span></span>

- <span data-ttu-id="90398-379">**Modo de diagnóstico** Crea un informe que incluye información sobre tablas (número de registros, fragmentación, tamaño de datos y tamaño de índice), tamaños de archivos de datos y registros, el último tiempo de copia de seguridad, la distribución de contactos entre servidores que ejecutan Microsoft Office Communications Server, el promedio de permisos, contactos, contenedores, suscripciones, publicaciones, puntos de conexión por usuario, usuarios que no se pueden enrutar de forma incorrecta, el número promedio de conferencias organizadas por usuario, conferencias programadas, conferencias activas y la versión de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="90398-379">**Diagnostic mode** Creates a report that includes information about tables (number of records, fragmentation, data size, and index size), data and log file sizes, the last back-up time, contact distribution among servers that are running Microsoft Office Communications Server, the average number of permissions, contacts, containers, subscriptions, publications, endpoints per user, any improperly homed users, users that can't be routed, the average number of conferences organized per user, scheduled conferences, active conferences, and the database version.</span></span>

    > [!NOTE]
    > <span data-ttu-id="90398-380">Ejecutar el modo de diagnóstico puede afectar al rendimiento del servidor.</span><span class="sxs-lookup"><span data-stu-id="90398-380">Running diagnostic mode can affect server performance.</span></span>

- <span data-ttu-id="90398-381">**Modo de datos de usuario** Informa de datos de contacto, contenedor, suscripción, publicación, permisos y grupos de contactos para un usuario especificado o para los usuarios que tienen ese usuario en sus listas de contactos y permisos.</span><span class="sxs-lookup"><span data-stu-id="90398-381">**User data mode** Reports contact, container, subscription, publication, permission, and contact-group data for a specified user or for users who have that user in their contact and permission lists.</span></span> <span data-ttu-id="90398-382">Este modo también informa de los datos de resumen de las conferencias a las que un usuario organiza o a la que se invita.</span><span class="sxs-lookup"><span data-stu-id="90398-382">This mode also reports summary data for conferences that a user organizes or is invited to.</span></span>

- <span data-ttu-id="90398-383">**Modo de conferencia** Informa de los datos detallados de una conferencia específica, incluidos todos los detalles de horario de programación de la conferencia, la lista de invitados, la lista de tipos de medios permitidos para la conferencia, las MCU activas (unidades de control multipunto), la lista de participantes activos y el estado de señalización de cada participante.</span><span class="sxs-lookup"><span data-stu-id="90398-383">**Conference mode** Reports detailed data for a specific conference, including all schedule-time details for the conference, the invitee list, the list of media types allowed for the conference, active MCUs (multipoint control units), the active participant list, and each participant's signaling state.</span></span>

- <span data-ttu-id="90398-384">**Descodificar id. de reunión** Descodifica un identificador de reunión de red telefónica conmutada (RTC) especificado por el modificador **/pstnid,** pero que no se conecta al back-end para obtener información detallada.</span><span class="sxs-lookup"><span data-stu-id="90398-384">**Decode Meeting ID** Decodes a public switched telephone network (PSTN) meeting ID that is specified by the **/pstnid** switch but does not connect to the back end for detailed information.</span></span>

- <span data-ttu-id="90398-385">**Resolver conferencia** Descodifica un identificador de reunión RTC especificado por el modificador **/pstnid** y muestra información sobre la conferencia indicada por el identificador.</span><span class="sxs-lookup"><span data-stu-id="90398-385">**Resolve conference** Decodes a PSTN meeting ID that is specified by the **/pstnid** switch and displays information about the conference indicated by the ID.</span></span>

- <span data-ttu-id="90398-386">**Modo M.M.** Notifica el identificador, el tipo de medio, la dirección URL, el estado del latido, la carga de conferencia y la carga de participantes para cada MCU del grupo.</span><span class="sxs-lookup"><span data-stu-id="90398-386">**MCUs mode** Reports the ID, media type, URL, heartbeat status, conference load, and participant load for each MCU in the pool.</span></span>

- <span data-ttu-id="90398-387">**Modo de fragmentación de disco** Muestra el estado de fragmentación de todos los discos.</span><span class="sxs-lookup"><span data-stu-id="90398-387">**Disk fragmentation mode** Displays the fragmentation status of all disks.</span></span>

<span data-ttu-id="90398-388">Esta herramienta se puede usar para diagnosticar diversos problemas o para ayudar a los administradores con la planeación de capacidad.</span><span class="sxs-lookup"><span data-stu-id="90398-388">This tool can be used to diagnose various problems or to assist administrators with capacity planning.</span></span> <span data-ttu-id="90398-389">Por ejemplo, si la mayoría de los usuarios que se hospedaron en el servidor A eligen usuarios que se hospedaron en el servidor B como sus contactos, el administrador puede mover los usuarios del servidor A al servidor B para reducir el tráfico entre servidores.</span><span class="sxs-lookup"><span data-stu-id="90398-389">For example, if most of the users homed on server A choose users homed on server B as their contacts, the administrator can move the users on server A to server B to reduce cross-server traffic.</span></span>

### <a name="output"></a><span data-ttu-id="90398-390">Salida</span><span class="sxs-lookup"><span data-stu-id="90398-390">Output</span></span>

<span data-ttu-id="90398-391">Esta herramienta genera informes predefinidos sobre la Skype Empresarial Server base de datos de 2015.</span><span class="sxs-lookup"><span data-stu-id="90398-391">This tool outputs predefined reports about the Skype for Business Server 2015 database.</span></span> <span data-ttu-id="90398-392">**Ruta** de acceso: %ProgramFiles%\Skype Empresarial Server 2015\Reskit</span><span class="sxs-lookup"><span data-stu-id="90398-392">**Path**: %ProgramFiles%\Skype for Business Server 2015\Reskit</span></span>

### <a name="purpose"></a><span data-ttu-id="90398-393">Objetivo</span><span class="sxs-lookup"><span data-stu-id="90398-393">Purpose</span></span>

<span data-ttu-id="90398-394">Para instalar Dbanalyze.exe, cópielo en una carpeta local y, a continuación, ejecute la herramienta.</span><span class="sxs-lookup"><span data-stu-id="90398-394">To install Dbanalyze.exe, copy it to a local folder and then run the tool.</span></span> <span data-ttu-id="90398-395">Para usar la herramienta, ejecute el siguiente comando desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="90398-395">To use the tool, run the following command from the command line.</span></span> <span data-ttu-id="90398-396">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` A continuación se muestran las descripciones de las opciones de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="90398-396">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` The descriptions for the command-line options are shown below.</span></span>

![Opciones de línea de comandos para Dbanalyze.exe.](../media/Reskit_2012_Tools_Documentation_Image35.JPG)

### <a name="requirements"></a><span data-ttu-id="90398-398">Requirements</span><span class="sxs-lookup"><span data-stu-id="90398-398">Requirements</span></span>

 <span data-ttu-id="90398-399">**Equipo** DBAnalyze solo se puede ejecutar desde un equipo unido a un dominio que Skype Empresarial Server 2015 instalado.</span><span class="sxs-lookup"><span data-stu-id="90398-399">**Computer** DBAnalyze can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span>

 <span data-ttu-id="90398-400">**Red** El equipo debe poder conectarse a la base de datos back-end.</span><span class="sxs-lookup"><span data-stu-id="90398-400">**Network** The computer should be able to connect to the back-end database.</span></span>

 <span data-ttu-id="90398-401">**Los** Skype Empresarial Server software de 2015 deben instalarse antes de ejecutar DBAnalyze.</span><span class="sxs-lookup"><span data-stu-id="90398-401">**Software** Skype for Business Server 2015 software components must be installed before running DBAnalyze.</span></span>

 <span data-ttu-id="90398-402">**Usuarios** En la tabla siguiente se muestran los administradores que tienen los permisos necesarios para acceder a Skype Empresarial Server bases de datos de 2015.</span><span class="sxs-lookup"><span data-stu-id="90398-402">**Users** The table below shows the administrators who have the necessary permissions to access Skype for Business Server 2015 databases.</span></span>

![Tabla de permisos para Dbanalyze.exe.](../media/Reskit_2012_Tools_Documentation_Image36.JPG)

> [!NOTE]
> <span data-ttu-id="90398-404">Se requiere una cuenta de administrador local para **el modo /report:disk.**</span><span class="sxs-lookup"><span data-stu-id="90398-404">A local administrator account is required for **/report:disk** mode.</span></span>

### <a name="examples"></a><span data-ttu-id="90398-405">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="90398-405">Examples</span></span>

<span data-ttu-id="90398-406">A continuación se muestran ejemplos de comandos Dbanalyze.exe válidos:</span><span class="sxs-lookup"><span data-stu-id="90398-406">The following are examples of valid Dbanalyze.exe commands:</span></span>

```console
dbanalyze.exe /report:diag
dbanalyze.exe /report:user /user:usera@domainb.com
dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
dbanalyze.exe /report:resolve /pstnid:12345
dbanalyze.exe /report:mcus
dbanalyze.exe /report:disk
```

### <a name="summary"></a><span data-ttu-id="90398-407">Resumen</span><span class="sxs-lookup"><span data-stu-id="90398-407">Summary</span></span>

<span data-ttu-id="90398-408">DBAnalyzer proporciona a los administradores un análisis rápido y fácil de Skype Empresarial Server bases de datos de 2015.</span><span class="sxs-lookup"><span data-stu-id="90398-408">DBAnalyzer provides administrators a quick and easy to analyze Skype for Business Server 2015 databases.</span></span>

## <a name="import-storage-service-data"></a><span data-ttu-id="90398-409">Importar Storage de servicio</span><span class="sxs-lookup"><span data-stu-id="90398-409">Import Storage Service Data</span></span>
<span data-ttu-id="90398-410"><a name="Issd"> </a></span><span class="sxs-lookup"><span data-stu-id="90398-410"><a name="Issd"> </a></span></span>

<span data-ttu-id="90398-411">La herramienta del kit de recursos ImportStorageServiceData permite volver a importar los datos de cola y punto de conexión que se vaciaron del servicio de Storage (LYSS) de nuevo en el servicio de Storage.</span><span class="sxs-lookup"><span data-stu-id="90398-411">The ImportStorageServiceData resource kit tool allows for reimporting Queue and Endpoint data that was flushed out of the Storage Service (LYSS) back into the Storage Service.</span></span>

### <a name="description"></a><span data-ttu-id="90398-412">Descripción</span><span class="sxs-lookup"><span data-stu-id="90398-412">Description</span></span>

<span data-ttu-id="90398-413">Los datos vaciados del servicio Storage podrían haber sido automáticos (periódicos) según el estado del elemento de cola o el tamaño de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="90398-413">The data flushed out of the Storage Service could have been automatic (periodic) based on Queue Item status or database size.</span></span> <span data-ttu-id="90398-414">Podría haber ocurrido debido a la invocación manual del cmdlet de conmutación por error del grupo de servidores o al cmdlet StorageServiceFullFlush (que invoca el cmdlet de conmutación por error del grupo).</span><span class="sxs-lookup"><span data-stu-id="90398-414">It could have happened due to the manual invocation of the pool failover cmdlet, or the StorageServiceFullFlush cmdlet (which the pool failover cmdlet invokes).</span></span> <span data-ttu-id="90398-415">Tenga en cuenta que lo ideal es que los datos no se vuelvan a importar si alguno de los tamaños de base de datos del servicio de Storage (LYSS) en los front-ends está por encima del nivel normal, ya que es probable que esto solo haga que se exporten más datos. Además, los problemas que podrían haber contribuido a errores que provocaron el crecimiento de la cola de servicios de Storage primero deben resolverse (por ejemplo, Exchange errores de extremo, problemas de red u otros problemas).</span><span class="sxs-lookup"><span data-stu-id="90398-415">Note that data should ideally not be reimported if any of the Storage Service (LYSS ) database sizes on the front ends is above the normal level, because doing so will likely just cause more data to be exported back out. Furthermore, any problems that could have contributed to errors that caused the Storage Service Queue to grow should first be resolved (for example Exchange endpoint errors, network issues, or other problems).</span></span>

 <span data-ttu-id="90398-416">**Escenario 1: durante la** conmutación por error del grupo, los archivos pueden vaciarse del servicio de almacenamiento para cada front-end.</span><span class="sxs-lookup"><span data-stu-id="90398-416">**Scenario 1:** during pool failover, files may be flushed out from storage service for each front end.</span></span> <span data-ttu-id="90398-417">Una vez completada la conmutación por error, se debe ejecutar la herramienta para volver a importar los datos.</span><span class="sxs-lookup"><span data-stu-id="90398-417">After failover is completed, the tool should be run to reimport the data.</span></span>

 <span data-ttu-id="90398-418">**Escenario 2:** los datos se vacían automáticamente cada día o en respuesta Storage a una base de datos de servicio que supera determinados umbrales de tamaño (por ejemplo, 60%, 80%, 90 % de lleno).</span><span class="sxs-lookup"><span data-stu-id="90398-418">**Scenario 2:** data is being flushed automatically each day or in response to Storage Service database exceeding certain size thresholds (for example 60%, 80%, 90% full).</span></span> <span data-ttu-id="90398-419">El administrador debe volver a importar de forma rutinaria estos datos vaciados automáticamente.</span><span class="sxs-lookup"><span data-stu-id="90398-419">This automatically flushed data should be reimported routinely by the administrator.</span></span> <span data-ttu-id="90398-420">En la situación anterior, si no se implementa el paquete SCOM de supervisión, hay eventos para el servicio de Skype Empresarial Server Storage relacionado con los datos que se van a vaciar del servicio de Storage.</span><span class="sxs-lookup"><span data-stu-id="90398-420">In the above situation, if the monitoring SCOM pack is not deployed, there are events for Skype for Business Server Storage Service relating to data being flushed from the Storage Service.</span></span> <span data-ttu-id="90398-421">Los IDs de eventos de 32075 (se inicia la operación de vaciado completo), 32076 (se ha completado el vaciado completo), 32082 (vaciado de nivel de mantenimiento iniciado), 32083 (vaciado de nivel de mantenimiento completo), 32089 (vaciado debido al llenado de la base de datos).</span><span class="sxs-lookup"><span data-stu-id="90398-421">Event IDs of 32075 (full flush operation is started), 32076 (full flush has completed), 32082 (maintenance level flush started), 32083 (maintenance level flush complete), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="90398-422">Tenga en cuenta que estos identificadores de evento corresponden a la versión rtm.</span><span class="sxs-lookup"><span data-stu-id="90398-422">Note these event Ids correspond to the RTM release.</span></span> <span data-ttu-id="90398-423">Cuando un administrador ve estos eventos, significa que hay archivos que se han vaciado. Estos datos deben importarse de forma rutinaria con esta herramienta, por ejemplo, una vez a la semana.</span><span class="sxs-lookup"><span data-stu-id="90398-423">When an administrator sees these events, it means that there are files that have been flushed out. This data should routinely be imported back using this tool, for example once per week.</span></span>

<span data-ttu-id="90398-424">Para la versión del servicio en línea, si se implementa el paquete SCOM de supervisión de estado para Skype Empresarial Server, se pueden generar nuevas alertas que piden al administrador que vuelva a importar los datos vaciados en el servicio Storage.</span><span class="sxs-lookup"><span data-stu-id="90398-424">For the Online Service release, if health monitoring SCOM pack for Skype for Business Server is deployed, there are new alerts that may be raised which ask the administrator to reimport the flushed data back into Storage Service.</span></span> <span data-ttu-id="90398-425">Habrá un evento correspondiente en el registro de eventos en el servidor Front-End que desencadenó la alerta.</span><span class="sxs-lookup"><span data-stu-id="90398-425">There will be a corresponding event in the event log on the Front-End server that triggered the alert.</span></span> <span data-ttu-id="90398-426">El evento dará una descripción de la ruta de acceso principal en la que se encuentran los archivos de datos vaciados y cuántos archivos hay que cumplen los criterios de alerta.</span><span class="sxs-lookup"><span data-stu-id="90398-426">The event will give a description of the Parent path under which the flushed data files are located, and how many files there are which meet the alert criteria.</span></span> <span data-ttu-id="90398-427">El criterio de alerta es que hay X o más archivos bajo la ruta de acceso principal en particular que tienen al menos Y días de antigüedad (donde X e Y están preestablecidos dentro del StorageService, pero se pueden invalidar cambiando el archivo APPCONFIG). A continuación se muestran dos ejemplos de eventos que pueden desencadenar la alerta de estado, con la diferencia de que su ruta principal.</span><span class="sxs-lookup"><span data-stu-id="90398-427">The alert criteria is that there are X or more files under the particular parent path that are at least Y days old (where X and Y are preset within the StorageService but can be overridden by changing the APPCONFIG file.)Two examples of events that can trigger the health alert are shown below, with the difference being their parent path.</span></span> <span data-ttu-id="90398-428">Una posibilidad está en recurso compartido de archivos del servicio web, mientras que la otra posibilidad es el directorio local de datos de aplicación de cada front-end.</span><span class="sxs-lookup"><span data-stu-id="90398-428">One possibility is under Web service file share, while the other possibility is the local Application Data directory of each front end.</span></span> <span data-ttu-id="90398-429">(por ejemplo c:\ProgramData\Microsoft\Skype Empresarial Server 2015\StorageService).</span><span class="sxs-lookup"><span data-stu-id="90398-429">(for example c:\ProgramData\Microsoft\Skype for Business Server 2015\StorageService).</span></span> <span data-ttu-id="90398-430">A continuación, el administrador ejecutará esta herramienta de reskit.</span><span class="sxs-lookup"><span data-stu-id="90398-430">The administrator will then run this reskit tool.</span></span>

<span data-ttu-id="90398-431">Esta herramienta aumentará la carga de CPU e E/S en el front-end en el que se ejecuta, y en otros front-end, en la situación en que los datos no son propiedad del front-end en el que se ejecuta la herramienta.</span><span class="sxs-lookup"><span data-stu-id="90398-431">This tool will increase CPU and IO load on the front end it is running on, and other front ends, in the situation that the data is not owned by the front end that the tool is executed on.</span></span> <span data-ttu-id="90398-432">Se recomienda ejecutar esta herramienta cuando los front-ends no estén bajo una gran carga de CPU e E/S, por ejemplo fuera de las horas pico.</span><span class="sxs-lookup"><span data-stu-id="90398-432">We recommend running this tool when front ends are not under heavy CPU and IO load, for example outside of peak hours.</span></span> <span data-ttu-id="90398-433">En segundo lugar, esta herramienta puede importar un archivo de datos de 2 a 3 minutos.</span><span class="sxs-lookup"><span data-stu-id="90398-433">Secondly, this tool can 2 to 3 minutes to import one data file.</span></span> <span data-ttu-id="90398-434">Ten esto en cuenta al calcular cuánto tiempo se va a ejecutar la herramienta.</span><span class="sxs-lookup"><span data-stu-id="90398-434">Keep this in mind when estimating how long tool will be running.</span></span> <span data-ttu-id="90398-435">El archivo de registro detallado generado por la herramienta aparecerá de forma predeterminada en el Almacén de archivos.</span><span class="sxs-lookup"><span data-stu-id="90398-435">The verbose log file generated by the tool will by default appear on the File Store.</span></span> <span data-ttu-id="90398-436">Elimínelo si no se han notificado errores, ya que el archivo de registro puede ser decenas de MB o más.</span><span class="sxs-lookup"><span data-stu-id="90398-436">Delete it if there are no errors reported, because the log file can be tens of MB or more.</span></span>

![Eventos de Storage de eventos del servidor de ejemplo.](../media/Reskit_2012_Tools_Documentation_Image1.jpg)

### <a name="requirements"></a><span data-ttu-id="90398-438">Requirements</span><span class="sxs-lookup"><span data-stu-id="90398-438">Requirements</span></span>

<span data-ttu-id="90398-439">Instale las Skype Empresarial Server kit de recursos de 2015.</span><span class="sxs-lookup"><span data-stu-id="90398-439">Install the Skype for Business Server 2015 Resource Kit tools.</span></span> <span data-ttu-id="90398-440">La herramienta se ejecuta en máquinas unidas a un dominio donde Skype Empresarial Server y Skype Empresarial Server Shell de administración están instalados.</span><span class="sxs-lookup"><span data-stu-id="90398-440">The tool runs on domain-joined machines where Skype for Business Server and Skype for Business Server Management Shell are installed.</span></span> <span data-ttu-id="90398-441">La herramienta usa un cmdlet del shell de administración para identificar todos los Front-End del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="90398-441">The tool uses a cmdlet from the management shell to identify all the Front-End servers in the pool.</span></span> <span data-ttu-id="90398-442">En segundo lugar, la herramienta debe ejecutarse desde una máquina del grupo que tenga instalada la base de datos **RtcLocal.**</span><span class="sxs-lookup"><span data-stu-id="90398-442">Secondly, the tool must be executed from a machine in the pool that has the **RtcLocal** database installed.</span></span> <span data-ttu-id="90398-443">Esta base de datos la usa la herramienta para recuperar la ubicación del recurso compartido de archivos WEBSERVICE para el grupo.</span><span class="sxs-lookup"><span data-stu-id="90398-443">This database is used by the tool to retrieve the location of the WEBSERVICE file share for the pool.</span></span> <span data-ttu-id="90398-444">Además, antes de usar la herramienta, cada servidor Front-End debe habilitar primero la comunicación remota de Windows PowerShell con **Enable-PSRemoting** en cada servidor Front-End y la máquina desde la que se ejecuta la herramienta.</span><span class="sxs-lookup"><span data-stu-id="90398-444">Additionally, before using the tool, each Front-End server must first enable Windows PowerShell Remoting using **Enable-PSRemoting** on each Front-End server, and the machine that the tool is executed from.</span></span> <span data-ttu-id="90398-445">De lo contrario, Windows PowerShell comandos remotos de esta herramienta producirán un error.</span><span class="sxs-lookup"><span data-stu-id="90398-445">Otherwise, remote Windows PowerShell commands from this tool will fail.</span></span> <span data-ttu-id="90398-446">Windows PowerShell La comunicación remota se puede desactivar en todos Front-End servidores del grupo una vez finalizada.</span><span class="sxs-lookup"><span data-stu-id="90398-446">Windows PowerShell Remoting can be turned off on all Front-End servers in the pool after it is finished.</span></span> <span data-ttu-id="90398-447">Por último, la cuenta o credencial que invoca la herramienta debe tener permiso de lectura y escritura para el recurso compartido de archivos de servicio web para el grupo en el que están ejecutando esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="90398-447">Finally, the account or credential invoking the tool must have read/write permission to the webservice file share for the pool they are executing this tool on.</span></span> <span data-ttu-id="90398-448">De lo contrario, la herramienta producirá un error con errores de permiso de E/S.</span><span class="sxs-lookup"><span data-stu-id="90398-448">Otherwise the tool will fail with IO Permission errors.</span></span>

> [!NOTE]
> <span data-ttu-id="90398-449">En Windows Server 2012, Windows PowerShell remoción está habilitada de forma predeterminada, pero no en el sistema operativo Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="90398-449">On Windows Server 2012, Windows PowerShell Remoting is enabled by default, but not on the Windows Server 2008 operating system.</span></span>

### <a name="examples"></a><span data-ttu-id="90398-450">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="90398-450">Examples</span></span>

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

## <a name="lcssync"></a><span data-ttu-id="90398-451">LCSSync</span><span class="sxs-lookup"><span data-stu-id="90398-451">LCSSync</span></span>
<span data-ttu-id="90398-452"><a name="LCSSync"> </a></span><span class="sxs-lookup"><span data-stu-id="90398-452"><a name="LCSSync"> </a></span></span>

<span data-ttu-id="90398-453">La herramienta LCSSync ayuda a implementar Skype Empresarial Server software de comunicaciones de 2015 en un entorno de varios bosques.</span><span class="sxs-lookup"><span data-stu-id="90398-453">The LCSSync tool helps to deploy Skype for Business Server 2015 communications software in a multi-forest environment.</span></span> <span data-ttu-id="90398-454">Esta herramienta se usa para sincronizar usuarios y grupos de diferentes bosques de usuarios como un objeto de contacto de Servicios de dominio de Active Directory con un bosque central donde Skype Empresarial Server 2015 está instalado.</span><span class="sxs-lookup"><span data-stu-id="90398-454">This tool is used to synchronize users and groups from different user forests as an Active Directory Domain Services contact object to a central forest where Skype for Business Server 2015 is installed.</span></span>

### <a name="description"></a><span data-ttu-id="90398-455">Descripción</span><span class="sxs-lookup"><span data-stu-id="90398-455">Description</span></span>

 <span data-ttu-id="90398-456">LCSSync usa los objetos de contacto sincronizados de Servicios de dominio de Active Directory en el bosque central para habilitar a los usuarios para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="90398-456">LCSSync uses the synchronized Active Directory Domain Services contact objects in the central forest to enable users for Skype for Business Server.</span></span> <span data-ttu-id="90398-457">Para proporcionar el inicio de sesión único, la cuenta de usuario principal debe asignarse al objeto de contacto servicios de dominio de Active Directory en el bosque central para Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="90398-457">To provide single sign in, the primary user account must be mapped to the Active Directory Domain Services contact object in the central forest for Skype for Business Server 2015.</span></span> <span data-ttu-id="90398-458">Esta herramienta ayuda a realizar esa asignación.</span><span class="sxs-lookup"><span data-stu-id="90398-458">This tool helps perform that mapping.</span></span> <span data-ttu-id="90398-459">Esta herramienta proporciona plantillas para crear agentes de administración en el Servidor de integración de identidades de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="90398-459">This tool provides templates for creating Management Agents in the Microsoft Identity Integration Server.</span></span>

### <a name="summary"></a><span data-ttu-id="90398-460">Resumen</span><span class="sxs-lookup"><span data-stu-id="90398-460">Summary</span></span>

<span data-ttu-id="90398-461">La herramienta LCSSync ayuda a implementar Skype Empresarial Server 2015 en un entorno de varios bosques.</span><span class="sxs-lookup"><span data-stu-id="90398-461">The LCSSync tool helps to deploy Skype for Business Server 2015 in a multi-forest environment.</span></span>

## <a name="lookup-user-console"></a><span data-ttu-id="90398-462">Consola de usuario de búsqueda</span><span class="sxs-lookup"><span data-stu-id="90398-462">Lookup User Console</span></span>
<span data-ttu-id="90398-463"><a name="LUC"> </a></span><span class="sxs-lookup"><span data-stu-id="90398-463"><a name="LUC"> </a></span></span>

<span data-ttu-id="90398-464">La herramienta LookupUserConsole muestra información Skype Empresarial Server de enrutamiento interna sobre usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="90398-464">The LookupUserConsole tool displays internal Skype for Business Server routing information about specific users.</span></span> <span data-ttu-id="90398-465">Esta información puede ser útil para que Microsoft admita personalmente en el diagnóstico de problemas de distribución y enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="90398-465">This information may be useful to Microsoft support personal in diagnosing deployment and routing problems.</span></span>

### <a name="description"></a><span data-ttu-id="90398-466">Descripción</span><span class="sxs-lookup"><span data-stu-id="90398-466">Description</span></span>

 <span data-ttu-id="90398-467">Al ejecutar LookupUserConsole.exe se abrirá un símbolo del sistema que acepta direcciones SIP e intenta mostrar información Skype Empresarial Server de enrutamiento que las relaciona.</span><span class="sxs-lookup"><span data-stu-id="90398-467">Executing LookupUserConsole.exe will open a command prompt that accepts SIP addresses and attempts to display internal Skype for Business Server routing information relating them.</span></span> <span data-ttu-id="90398-468">Escriba **exit** para salir de la herramienta LookupUserConsole.</span><span class="sxs-lookup"><span data-stu-id="90398-468">Type **exit** to quit the LookupUserConsole tool.</span></span>

### <a name="requirements"></a><span data-ttu-id="90398-469">Requirements</span><span class="sxs-lookup"><span data-stu-id="90398-469">Requirements</span></span>

<span data-ttu-id="90398-470">Instale el Skype Empresarial Server de recursos de 2015.</span><span class="sxs-lookup"><span data-stu-id="90398-470">Install the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="90398-471">La herramienta se ejecuta en máquinas unidas a un dominio donde Skype Empresarial Server está instalado.</span><span class="sxs-lookup"><span data-stu-id="90398-471">The tool runs on domain-joined machines where Skype for Business Server is installed.</span></span>

### <a name="examples"></a><span data-ttu-id="90398-472">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="90398-472">Examples</span></span>

<span data-ttu-id="90398-473">C:\Archivos de programa\Skype Empresarial Server 2015\ResKit \>LookupUserConsole.exe</span><span class="sxs-lookup"><span data-stu-id="90398-473">C:\Program Files\Skype for Business Server 2015\ResKit\>LookupUserConsole.exe</span></span>

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

## <a name="msturnping"></a><span data-ttu-id="90398-474">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="90398-474">MsTurnPing</span></span>
<span data-ttu-id="90398-475"><a name="MsTurnPing"> </a></span><span class="sxs-lookup"><span data-stu-id="90398-475"><a name="MsTurnPing"> </a></span></span>

<span data-ttu-id="90398-476">La herramienta MSTurnPing permite a un administrador del software de comunicaciones de Skype Empresarial Server 2015 comprobar el estado de los servidores que ejecutan el servidor perimetral de audio y vídeo, los servicios de autenticación de audio y vídeo y los servidores que ejecutan los Servicios de directivas de ancho de banda en la topología.</span><span class="sxs-lookup"><span data-stu-id="90398-476">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge, Audio/Video Authentication services, and the servers that are running Bandwidth Policy Services in the topology.</span></span>

### <a name="description"></a><span data-ttu-id="90398-477">Descripción</span><span class="sxs-lookup"><span data-stu-id="90398-477">Description</span></span>

<span data-ttu-id="90398-478">La herramienta MSTurnPing permite a un administrador del software de comunicaciones de Skype Empresarial Server 2015 comprobar el estado de los servidores que ejecutan el servidor perimetral de audio y vídeo, los servicios de autenticación de audio y vídeo y los servidores que ejecutan los Servicios de directivas de ancho de banda en la topología.</span><span class="sxs-lookup"><span data-stu-id="90398-478">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge, Audio/Video Authentication services, and the servers that are running Bandwidth Policy Services in the topology.</span></span>

<span data-ttu-id="90398-479">La herramienta permite al administrador realizar las siguientes pruebas:</span><span class="sxs-lookup"><span data-stu-id="90398-479">The tool allows the administrator to perform the following tests:</span></span>

1. <span data-ttu-id="90398-480">Prueba del servidor perimetral A/V: la herramienta realiza pruebas en todos los servidores perimetrales A/V de la topología mediante lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="90398-480">A/V Edge Server test: The tool performs tests against all A/V Edge Servers in the topology by doing the following:</span></span>

   - <span data-ttu-id="90398-481">Comprobar que el servicio Skype Empresarial Server de autenticación de audio y vídeo se ha iniciado y puede emitir las credenciales adecuadas.</span><span class="sxs-lookup"><span data-stu-id="90398-481">Verifying that the Skype for Business Server Audio/Video Authentication service is started and can issue proper credentials.</span></span>

   - <span data-ttu-id="90398-482">Comprobación de que el Skype Empresarial Server perimetral de audio y vídeo se inicia y puede asignar correctamente los recursos en el perímetro externo.</span><span class="sxs-lookup"><span data-stu-id="90398-482">Verifying that the Skype for Business Server Audio/Video Edge service is started and can allocate the resources on the external edge successfully.</span></span>

2. <span data-ttu-id="90398-483">Prueba del servicio de directivas de ancho de banda: la herramienta realiza pruebas en todos los servidores que ejecutan los Servicios de directivas de ancho de banda en la topología mediante lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="90398-483">Bandwidth Policy Service test: The tool performs tests against all the servers that are running the Bandwidth Policy Services in the topology by doing the following:</span></span>

   - <span data-ttu-id="90398-484">Comprobar que el servicio Skype Empresarial Server de directivas de ancho de banda (autenticación) se ha iniciado y puede emitir las credenciales adecuadas.</span><span class="sxs-lookup"><span data-stu-id="90398-484">Verifying that the Skype for Business Server Bandwidth Policy Service (Authentication) is started and can issue proper credentials.</span></span>

   - <span data-ttu-id="90398-485">Comprobar que el servicio Skype Empresarial Server de directivas de ancho de banda (Core) se ha iniciado y puede realizar la comprobación de ancho de banda correctamente.</span><span class="sxs-lookup"><span data-stu-id="90398-485">Verifying that the Skype for Business Server Bandwidth Policy Service (Core) is started and can perform the bandwidth check successfully.</span></span>

<span data-ttu-id="90398-486">Esta herramienta debe ejecutarse desde un equipo que forma parte de la topología y tiene instalado el almacén local.</span><span class="sxs-lookup"><span data-stu-id="90398-486">This tool must be run from a computer that is part of the topology and has the local store installed.</span></span>

### <a name="output"></a><span data-ttu-id="90398-487">Salida</span><span class="sxs-lookup"><span data-stu-id="90398-487">Output</span></span>

<span data-ttu-id="90398-488">La herramienta genera los resultados de cada una de las operaciones.</span><span class="sxs-lookup"><span data-stu-id="90398-488">The tool outputs the results of each of the operations.</span></span>

- <span data-ttu-id="90398-489">Si se **realiza la prueba AudioVideoEdgeServer,** los resultados de la herramienta son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="90398-489">If the **AudioVideoEdgeServer** test is performed, the tool outputs are the following:</span></span>

  - <span data-ttu-id="90398-490">Los resultados de la prueba de los equipos que proporcionan el Skype Empresarial Server de autenticación de audio y vídeo de 2015 en la topología</span><span class="sxs-lookup"><span data-stu-id="90398-490">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Authentication service in the topology</span></span>

  - <span data-ttu-id="90398-491">Los resultados de la prueba de los equipos que proporcionan el Skype Empresarial Server perimetral de audio y vídeo de 2015 en la topología</span><span class="sxs-lookup"><span data-stu-id="90398-491">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Edge service in the topology</span></span>

- <span data-ttu-id="90398-492">Si se realiza la prueba **BandwidthPolicyServer,** los resultados de la herramienta son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="90398-492">If the **BandwidthPolicyServer** test is performed, the tool outputs are the following:</span></span>

  - <span data-ttu-id="90398-493">Los resultados de la prueba de los equipos que proporcionan el Skype Empresarial Server de directivas de ancho de banda (autenticación) de 2015 en la topología</span><span class="sxs-lookup"><span data-stu-id="90398-493">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Authentication) in the topology</span></span>

  - <span data-ttu-id="90398-494">Resultados de prueba de los equipos que proporcionan el Skype Empresarial Server de directivas de ancho de banda (core) de 2015 en la topología</span><span class="sxs-lookup"><span data-stu-id="90398-494">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Core) in the topology</span></span>

### <a name="requirements"></a><span data-ttu-id="90398-495">Requirements</span><span class="sxs-lookup"><span data-stu-id="90398-495">Requirements</span></span>

- <span data-ttu-id="90398-496">Esta herramienta debe ejecutarse desde un equipo que se encuentra en la topología y que tiene el almacén local.</span><span class="sxs-lookup"><span data-stu-id="90398-496">This tool must be run from a computer that is in the topology and that has the local store.</span></span>

- <span data-ttu-id="90398-497">La herramienta debe ejecutarse como administrador que tenga acceso al almacén local.</span><span class="sxs-lookup"><span data-stu-id="90398-497">The tool must be run as an administrator who has access to the local store.</span></span>

### <a name="examples"></a><span data-ttu-id="90398-498">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="90398-498">Examples</span></span>

<span data-ttu-id="90398-499">A continuación se muestra un ejemplo de la entrada de la herramienta.</span><span class="sxs-lookup"><span data-stu-id="90398-499">The following is an example of the tool input.</span></span>

```console
MsTurnPing -ServerRole AudioVideoEdgeServer

MsTurnPing -ServerRole BandwidthPolicyServer
```

### <a name="summary"></a><span data-ttu-id="90398-500">Resumen</span><span class="sxs-lookup"><span data-stu-id="90398-500">Summary</span></span>

<span data-ttu-id="90398-501">Esta herramienta puede ser un recurso valioso para Skype Empresarial Server administradores de 2015 que desean comprobar el estado de los servidores que ejecutan servicios de directiva de audio/vídeo y ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="90398-501">This tool can be a valuable resource to Skype for Business Server 2015 administrators who want to check the status of the servers that are running audio/video and bandwidth policy services.</span></span>

## <a name="network-configuration-viewer"></a><span data-ttu-id="90398-502">Visor de configuración de red</span><span class="sxs-lookup"><span data-stu-id="90398-502">Network Configuration Viewer</span></span>
<span data-ttu-id="90398-503"><a name="NCV"> </a></span><span class="sxs-lookup"><span data-stu-id="90398-503"><a name="NCV"> </a></span></span>

<span data-ttu-id="90398-504">Los administradores de software de comunicaciones de Skype Empresarial Server 2015 pueden usar el Visor de configuración de red para ver la topología de red de control de admisión de llamadas (CAC) para una empresa que se aprovisiona para permitir sesiones de comunicación en tiempo real, como llamadas de voz o vídeo basadas en la capacidad de ancho de banda especificada.</span><span class="sxs-lookup"><span data-stu-id="90398-504">Network Configuration Viewer can be used by Skype for Business Server 2015 communications software administrators to view call admission control (CAC) network topology for an enterprise that is provisioned to allow real-time communication sessions, such as voice or video calls based on specified bandwidth capacity.</span></span> <span data-ttu-id="90398-505">Skype Empresarial Server 2015 define directivas de CAC, que son aplicadas por los servicios de directiva de ancho de banda que se instalan con Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="90398-505">Skype for Business Server 2015 administrators defines CAC policies, which are enforced by the Bandwidth Policy services that are installed with Skype for Business Server 2015.</span></span>

### <a name="description"></a><span data-ttu-id="90398-506">Descripción</span><span class="sxs-lookup"><span data-stu-id="90398-506">Description</span></span>

<span data-ttu-id="90398-507">El Visor de configuración de red (NetworkConfigurationViewer.exe) permite a los administradores realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="90398-507">Network Configuration Viewer (NetworkConfigurationViewer.exe) allows administrators to perform the following tasks:</span></span>

- <span data-ttu-id="90398-508">Cargue y vea la topología de red cac desde una Skype Empresarial Server de 2015 en un formato gráfico.</span><span class="sxs-lookup"><span data-stu-id="90398-508">Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format.</span></span>

- <span data-ttu-id="90398-509">Cargue y vea la topología de red de CAC desde un archivo de registro del servidor de directivas de ancho de banda en un formato gráfico.</span><span class="sxs-lookup"><span data-stu-id="90398-509">Load and view CAC network topology from a Bandwidth Policy Server log file in a graphical format.</span></span>

- <span data-ttu-id="90398-510">Guarde y almacene la topología de red cac en un formato XML en el disco.</span><span class="sxs-lookup"><span data-stu-id="90398-510">Save and store CAC network topology in an XML format on the disk.</span></span>

- <span data-ttu-id="90398-511">Guarde y almacene el diagrama de topología de red cac en formato JPG o BMP.</span><span class="sxs-lookup"><span data-stu-id="90398-511">Save and store CAC network topology diagram in JPG or BMP format.</span></span>

- <span data-ttu-id="90398-512">Ver los datos de configuración de topología de red cac.</span><span class="sxs-lookup"><span data-stu-id="90398-512">View CAC network topology configuration data.</span></span>

- <span data-ttu-id="90398-513">Ver la topología de red cac en un estilo de vista de árbol.</span><span class="sxs-lookup"><span data-stu-id="90398-513">View CAC network topology in a tree-view style.</span></span>

- <span data-ttu-id="90398-514">Defina conectores personalizados para vínculos de topología de red cac (por ejemplo, vínculos de sitio a región, de región a región y de sitio a sitio).</span><span class="sxs-lookup"><span data-stu-id="90398-514">Define custom connectors for CAC network topology links (for example, site-to-region, region-to-region, and site-to-site links).</span></span>

- <span data-ttu-id="90398-515">Vea la información del sitio de topología de red cac, la información de región y las directivas de ancho de banda aprovisionados y los vínculos de red.</span><span class="sxs-lookup"><span data-stu-id="90398-515">View CAC network topology site information, region Information, and provisioned bandwidth policies and network links.</span></span>

### <a name="purpose"></a><span data-ttu-id="90398-516">Objetivo</span><span class="sxs-lookup"><span data-stu-id="90398-516">Purpose</span></span>

<span data-ttu-id="90398-517">Vea los vínculos de topología de red cac de empresa en una interfaz gráfica.</span><span class="sxs-lookup"><span data-stu-id="90398-517">View enterprise CAC network topology links in a graphical interface.</span></span>

### <a name="examples"></a><span data-ttu-id="90398-518">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="90398-518">Examples</span></span>

 <span data-ttu-id="90398-519">Cargar y ver la topología de red cac desde una implementación de **Skype Empresarial Server 2015** en un formato gráfico: los administradores de Skype Empresarial Server 2015 pueden  cargar y ver la configuración de topología de red de CAC en cualquier equipo de Skype Empresarial Server 2015 mediante la opción Descargar configuración de red, como se muestra en la figura siguiente.</span><span class="sxs-lookup"><span data-stu-id="90398-519">**Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format**: Skype for Business Server 2015 administrators can load and view CAC network topology configuration on any Skype for Business Server 2015 computer by using the **Download Network Configuration** option as shown in the figure below.</span></span> <span data-ttu-id="90398-520">La herramienta no podrá descargar ni ver dicha configuración cuando se implemente en un equipo que no tenga conectividad con el almacén de configuración de Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="90398-520">The tool will fail to download or view such a configuration when deployed on a computer that does not have connectivity to the Skype for Business Server 2015 configuration store.</span></span>

![Descargar la configuración de red.](../media/Reskit_2012_Tools_Documentation_Image23.jpg)

 <span data-ttu-id="90398-522">Cargar y ver topología de red cac desde un archivo de registro de servidor de directivas de ancho de banda en un formato **gráfico:** Skype Empresarial Server 2015 Servidores de directivas de ancho de banda guarda la topología de red cac como parte del mecanismo de registro en la ubicación de recurso compartido de archivos de Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="90398-522">**Load and View CAC network topology from a Bandwidth Policy server log file in a graphical format:** Skype for Business Server 2015 Bandwidth Policy servers saves the CAC network topology as a part of the logging mechanism under the Skype for Business Server 2015 file share location.</span></span> <span data-ttu-id="90398-523">Skype Empresarial Server administradores de 2015 pueden ver dicho archivo en un formato gráfico mediante la opción Abrir configuración **de** red, como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="90398-523">Skype for Business Server 2015 administrators can view such a file in a graphical format by using the **Open Network Configuration** option as shown below.</span></span>

![Abrir un archivo de registro del servidor de directivas de ancho de banda.](../media/Reskit_2012_Tools_Documentation_Image24.jpg)

<span data-ttu-id="90398-525">Guarde y almacene la topología de red cac en un formato XML en el disco: los administradores de Skype Empresarial Server 2015 pueden guardar el archivo de configuración de topología de red cac en un formato XML mediante la opción Guardar una copia de configuración de red como se muestra **a** continuación.</span><span class="sxs-lookup"><span data-stu-id="90398-525">Save and store CAC network topology in an XML format on the disk: Skype for Business Server 2015 administrators can save the CAC network topology configuration file in an XML format by using the **Save a copy of Network Configuration** option as shown below.</span></span> <span data-ttu-id="90398-526">A continuación, el archivo de configuración guardado se puede usar sin conexión con fines de visualización gráfica.</span><span class="sxs-lookup"><span data-stu-id="90398-526">The saved configuration file can then be used offline for graphical viewing purposes.</span></span>

![Guardar la configuración de red como un archivo XML.](../media/Reskit_2012_Tools_Documentation_Image25.jpg)

<span data-ttu-id="90398-528">Guardar y almacenar el diagrama de topología de red cac en formato JPG o BMP: los administradores de Skype Empresarial Server 2015 pueden  guardar la configuración de topología de red cac en un formato gráfico (formatos de archivo JPG y BMP) mediante la opción Guardar diagrama de configuración de red como imagen, como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="90398-528">Save and Store CAC network topology diagram in JPG or BMP format: Skype for Business Server 2015 administrators can save the CAC network topology configuration in a graphical format (JPG and BMP file formats) by using the **Save Network Configuration diagram as picture** option as shown below.</span></span>

![Guardar la configuración de red como una imagen.](../media/Reskit_2012_Tools_Documentation_Image26.jpg)

 <span data-ttu-id="90398-530">Ver datos de configuración de topología de red <strong>cac:</strong>los administradores de Skype Empresarial Server 2015 pueden ver datos de configuración de red relacionados, como regiones de red, sitios de red, perfiles de ancho de banda y direcciones IP de subred de sitio en un formato textual mediante la opción Ver datos de configuración de red, como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="90398-530"><strong>View CAC network topology configuration data:</strong>Skype for Business Server 2015 administrators can view related network configuration data such as network regions, network sites, bandwidth profiles, and site subnet IP addresses in a textual format by using the View Network Configuration data option as shown below.</span></span>

![Visualización de datos de configuración de red.](../media/Reskit_2012_Tools_Documentation_Image27.jpg)

 <span data-ttu-id="90398-532">Ver la topología de red cac en un estilo de vista de **árbol:** los administradores de Skype Empresarial Server 2015 pueden ver los datos de configuración de red relacionados en un estilo de vista de árbol gráfico mediante el panel de control situado en el lado izquierdo de la ventana de herramientas, como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="90398-532">**View CAC network topology in a tree-view style:** Skype for Business Server 2015 administrators can view related network configuration data in a graphical tree view style by using the control panel on the left side of the tool window as shown below.</span></span>

![Visualización de datos de configuración de red en una vista de árbol.](../media/Reskit_2012_Tools_Documentation_Image28.jpg)

 <span data-ttu-id="90398-534">Definir conectores personalizados para vínculos de topología de red **cac (como vínculos** de sitio a región, de región a región y de sitio a sitio): los administradores de Skype Empresarial Server 2015 pueden definir conectores gráficos personalizados para vínculos WAN de configuración de red cac mediante la opción Configuración como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="90398-534">**Define custom connectors for CAC network topology links (such as site-to-region, region-to-region, and site-to-site links):** Skype for Business Server 2015 administrators can define custom graphical connectors for CAC network configuration WAN links by using the Settings option as shown below.</span></span> <span data-ttu-id="90398-535">Esto ayuda a diferenciar entre varios tipos de vínculos de red que se aprovisionan en la configuración de red.</span><span class="sxs-lookup"><span data-stu-id="90398-535">This helps differentiate between various types of network links that are provisioned in the network configuration.</span></span>

![Herramientas](../media/Reskit_2012_Tools_Documentation_Image29.jpg)

 <span data-ttu-id="90398-537">Ver la información del sitio de topología de red **cac,** la información de región y las directivas de ancho de banda aprovisionados: Skype Empresarial Server los administradores de 2015 pueden ver información de región de red cac relacionada, información del sitio e información de aprovisionamiento de ancho de banda de CAC mediante las opciones que se muestran a continuación.</span><span class="sxs-lookup"><span data-stu-id="90398-537">**View CAC network topology site information, region information, and provisioned bandwidth policies:** Skype for Business Server 2015 administrators can view related CAC network region information, site information, and CAC bandwidth provisioning information by using options shown below.</span></span> <span data-ttu-id="90398-538">(Por ejemplo, haga clic **en Información** en una región de red o un objeto de sitio de red).</span><span class="sxs-lookup"><span data-stu-id="90398-538">(For example, click **Info** in a network region or network site object.)</span></span>

![Definición de conectores personalizados para la red.](../media/Reskit_2012_Tools_Documentation_Image30.jpg)

### <a name="summary"></a><span data-ttu-id="90398-540">Resumen</span><span class="sxs-lookup"><span data-stu-id="90398-540">Summary</span></span>

<span data-ttu-id="90398-541">Esta herramienta puede ser un recurso valioso para Skype Empresarial Server administradores de 2015 que quieren ver la topología de red cac para su implementación en un formato gráfico.</span><span class="sxs-lookup"><span data-stu-id="90398-541">This tool can be a valuable resource to Skype for Business Server 2015 administrators who would like to view CAC network topology for their deployment in a graphical format.</span></span>

## <a name="response-group-agent-live"></a><span data-ttu-id="90398-542">Agente de grupo de respuesta en directo</span><span class="sxs-lookup"><span data-stu-id="90398-542">Response Group Agent Live</span></span>
<span data-ttu-id="90398-543"><a name="RGAL"> </a></span><span class="sxs-lookup"><span data-stu-id="90398-543"><a name="RGAL"> </a></span></span>

<span data-ttu-id="90398-544">La aplicación grupo de respuesta ofrece a los agentes la capacidad de obtener acceso a información útil en tiempo real mediante su servicio web integrado.</span><span class="sxs-lookup"><span data-stu-id="90398-544">The Response Group application gives agents the ability to access useful real-time information using its built-in Web service.</span></span> <span data-ttu-id="90398-545">Desafortunadamente, no hay ninguna vista gráfica de estos datos disponible fuera de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="90398-545">Unfortunately, no graphical view of this data is available outside the application.</span></span> <span data-ttu-id="90398-546">La herramienta Live Resource Kit del agente de grupo de respuesta resuelve este problema proporcionando una forma sencilla y gráfica de acceder a esta información, mejorada con información de software de comunicaciones Skype Empresarial en tiempo real, como la presencia de otros agentes.</span><span class="sxs-lookup"><span data-stu-id="90398-546">The Response Group Agent Live Resource Kit tool solves this issue by providing a simple and graphical way to access this information, enhanced with real-time Skype for Business communications software information such as the presence of other agents.</span></span>

### <a name="description"></a><span data-ttu-id="90398-547">Descripción</span><span class="sxs-lookup"><span data-stu-id="90398-547">Description</span></span>

<span data-ttu-id="90398-548">Response Group Agent Live es una aplicación de Windows que proporciona funciones de inicio de sesión y de inicio de sesión, así como información en tiempo real (como la pertenencia a grupos y el número actual de llamadas) a los agentes del grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="90398-548">Response Group Agent Live is a Windows application that provides sign-in and sign-out functionality and some real-time information (such as group membership and current number of calls) to Response Group agents.</span></span> <span data-ttu-id="90398-549">Está pensado para ser una versión mejorada de la página Grupos de agentes (accesible desde Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="90398-549">It is meant to be an enhanced version of the Agent Groups page (accessible from Skype for Business.</span></span>

### <a name="purpose"></a><span data-ttu-id="90398-550">Objetivo</span><span class="sxs-lookup"><span data-stu-id="90398-550">Purpose</span></span>

<span data-ttu-id="90398-551">La aplicación Grupo de respuesta pone en cola las llamadas entrantes y, a continuación, las enruta a grupos de agentes.</span><span class="sxs-lookup"><span data-stu-id="90398-551">The Response Group application queues incoming calls, and then routes them to agent groups.</span></span> <span data-ttu-id="90398-552">Para tomar decisiones fundamentadas sobre las llamadas al servicio, los agentes pueden obtener acceso a información en tiempo real sobre sus grupos de agentes, como qué otros agentes están disponibles y cuántas llamadas esperan en cada cola.</span><span class="sxs-lookup"><span data-stu-id="90398-552">To make informed decisions about which calls to service, agents can access real-time information about their agent groups, such as what other agents are available and how many calls are waiting in each queue.</span></span> <span data-ttu-id="90398-553">Esta información, accesible inicialmente solo a través del servicio grupo de respuesta, está disponible de forma intuitiva por el agente de grupo de respuesta Live.</span><span class="sxs-lookup"><span data-stu-id="90398-553">This information, initially accessible only through the Response Group service, is made available in an intuitive way by Response Group Agent Live.</span></span>

#### <a name="features"></a><span data-ttu-id="90398-554">Características</span><span class="sxs-lookup"><span data-stu-id="90398-554">Features</span></span>

<span data-ttu-id="90398-555">La herramienta Live del agente de grupo de respuesta se basa en el servicio grupo de respuesta y Skype Empresarial Server SDK de 2015.</span><span class="sxs-lookup"><span data-stu-id="90398-555">The Response Group Agent Live tool is built on the Response Group service and the Skype for Business Server 2015 SDK.</span></span> <span data-ttu-id="90398-556">Proporciona a los agentes del grupo de respuesta la información y las capacidades disponibles desde el servicio de grupo de respuesta (como la pertenencia a grupos, la presencia de otros agentes y el número de llamadas en espera).</span><span class="sxs-lookup"><span data-stu-id="90398-556">It provides Response Group agents the information and capabilities that are available from the Response Group service (such as group membership, presence of other agents, and number of waiting calls).</span></span>

<span data-ttu-id="90398-557">En la figura siguiente se muestra la interfaz principal de Response Group Agent Live.</span><span class="sxs-lookup"><span data-stu-id="90398-557">The figure below illustrates the main interface of Response Group Agent Live.</span></span>

![La herramienta Live del agente de grupo de respuesta.](../media/Reskit_2012_Tools_Documentation_Image37.JPG)

<span data-ttu-id="90398-559">Las tres características principales siguientes están disponibles para los agentes en Response Group Agent Live:</span><span class="sxs-lookup"><span data-stu-id="90398-559">The following three main features are available for agents in Response Group Agent Live:</span></span>

- <span data-ttu-id="90398-560">**Inicio y salida:** Contrario a la página Grupos de agentes (accesible desde Skype Empresarial Server 2015), Response Group Agent Live solo permite que los agentes inicien sesión o no en todos los grupos de agentes a la vez.</span><span class="sxs-lookup"><span data-stu-id="90398-560">**Sign-in/out:** Contrary to the Agent Groups page (accessible from Skype for Business Server 2015), Response Group Agent Live allows only agents to sign in or out of all agent groups at once.</span></span> <span data-ttu-id="90398-561">Esta aplicación proporciona tres formas rápidas para que los agentes inicien sesión o no:</span><span class="sxs-lookup"><span data-stu-id="90398-561">This application provides three quick ways for agents to sign in or out:</span></span>

  - <span data-ttu-id="90398-562">Haga clic en los botones De inicio y salida (verde y rojo) de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="90398-562">Click the Sign-in/out (green and red) buttons within the application.</span></span>

  - <span data-ttu-id="90398-563">Haga clic con el botón secundario en el icono de la bandeja del sistema y seleccione Iniciar o cerrar sesión.</span><span class="sxs-lookup"><span data-stu-id="90398-563">Right-click the system tray icon, and select sign in or sign out.</span></span>

  - <span data-ttu-id="90398-564">Uso de métodos abreviados de teclado configurables.</span><span class="sxs-lookup"><span data-stu-id="90398-564">Using configurable keyboard shortcuts.</span></span>

- <span data-ttu-id="90398-565">**Pertenencia a grupos:** Cuando se selecciona un grupo de agentes, Response Group Agent Live muestra la lista de agentes de este grupo en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="90398-565">**Group membership:** When an agent group is selected, Response Group Agent Live displays the list of agents in this group in the right pane.</span></span> <span data-ttu-id="90398-566">Si Skype Empresarial Server 2015 se ejecuta en el mismo equipo que esta aplicación, la información de presencia y la tarjeta de contacto se muestran en el agente de grupo de respuesta live.</span><span class="sxs-lookup"><span data-stu-id="90398-566">If Skype for Business Server 2015 is running on the same computer as this application, presence information and the contact card are displayed in the Response Group Agent Live.</span></span> <span data-ttu-id="90398-567">Los agentes pueden enviar una mensajería instantánea o llamar a otros agentes directamente desde allí.</span><span class="sxs-lookup"><span data-stu-id="90398-567">Agents can send an IM or call other agents directly from there.</span></span>

- <span data-ttu-id="90398-568">**Estadísticas en tiempo real:** Response Group Agent Live proporciona estadísticas en tiempo real para todos los grupos de agentes.</span><span class="sxs-lookup"><span data-stu-id="90398-568">**Real-time statistics:** Response Group Agent Live provides real-time statistics for all agent groups.</span></span> <span data-ttu-id="90398-569">La frecuencia de actualización es de un minuto.</span><span class="sxs-lookup"><span data-stu-id="90398-569">The update frequency is one minute.</span></span> <span data-ttu-id="90398-570">Cuando un grupo de respuesta responde a una llamada, se agrega un indicador visual junto al nombre del grupo con el número actual de llamadas en cola.</span><span class="sxs-lookup"><span data-stu-id="90398-570">When a call is answered by a Response Group, a visual indicator is added next to the group name with the current number of queued calls.</span></span> <span data-ttu-id="90398-571">Al pausar el puntero sobre un grupo también se muestra el tiempo de espera más largo.</span><span class="sxs-lookup"><span data-stu-id="90398-571">Pausing the pointer over a group also displays the longest waiting time.</span></span>

### <a name="requirements"></a><span data-ttu-id="90398-572">Requirements</span><span class="sxs-lookup"><span data-stu-id="90398-572">Requirements</span></span>

<span data-ttu-id="90398-573">Response Group Agent Live requiere la .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="90398-573">Response Group Agent Live requires the .NET Framework 4.0.</span></span> <span data-ttu-id="90398-574">Además, para aprovechar las características de la presencia y la tarjeta de contacto, Skype Empresarial debe instalarse localmente (y estar en ejecución).</span><span class="sxs-lookup"><span data-stu-id="90398-574">In addition, to take advantage of the presence and contact card features, Skype for Business must be installed locally (and be running).</span></span>

#### <a name="configuration"></a><span data-ttu-id="90398-575">Configuración</span><span class="sxs-lookup"><span data-stu-id="90398-575">Configuration</span></span>

<span data-ttu-id="90398-576">Response Group Agent Live se puede personalizar según las preferencias individuales mediante el cuadro de diálogo Opciones de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="90398-576">Response Group Agent Live can be customized to individual preferences by using the Options dialog box in the application.</span></span> <span data-ttu-id="90398-577">Además, el administrador puede definir la dirección host predeterminada editando directamente la propiedad defaultHostAddress del RGAgentLive.exe.config archivo.</span><span class="sxs-lookup"><span data-stu-id="90398-577">In addition, the administrator can define the default host address by editing directly the defaultHostAddress property of the RGAgentLive.exe.config file.</span></span>

<span data-ttu-id="90398-578">En la figura siguiente se muestra el cuadro de diálogo Opciones que los agentes pueden usar para configurar la dirección host y las teclas de método abreviado.</span><span class="sxs-lookup"><span data-stu-id="90398-578">The figure below illustrates the Options dialog box that agents can use to configure the host address and shortcut keys.</span></span> <span data-ttu-id="90398-579">Para obtener acceso a este cuadro de diálogo, haga clic en el botón Opciones situado en la parte superior derecha de la interfaz principal.</span><span class="sxs-lookup"><span data-stu-id="90398-579">This dialog is accessed by clicking the Options button on the top right of the main interface.</span></span>

![Cuadro de diálogo Opciones de live del agente de grupo de respuesta.](../media/Reskit_2012_Tools_Documentation_Image38.JPG)

<span data-ttu-id="90398-581">Las tres opciones de configuración siguientes se pueden personalizar en la configuración live del agente de grupo de respuesta:</span><span class="sxs-lookup"><span data-stu-id="90398-581">The following three different settings can be customized in the Response Group Agent Live configuration:</span></span>

- <span data-ttu-id="90398-582">Dirección de host: normalmente es el FQDN del grupo web que pertenece al grupo de servidores principal del agente.</span><span class="sxs-lookup"><span data-stu-id="90398-582">Host address: This is typically the web pool FQDN belonging to the agent's home pool.</span></span> <span data-ttu-id="90398-583">La dirección de servicio del grupo de respuesta exacta se deriva automáticamente en segundo plano de esta información (anexando la ruta de acceso correcta después del host).</span><span class="sxs-lookup"><span data-stu-id="90398-583">The exact Response Group service address is automatically derived in the background from this information (by appending the right path after the host).</span></span>

- <span data-ttu-id="90398-584">Accesos directos: se pueden personalizar los métodos abreviados exactos para iniciar/cerrar sesión.</span><span class="sxs-lookup"><span data-stu-id="90398-584">Shortcuts: The exact shortcuts to sign-in/out can be customized.</span></span> <span data-ttu-id="90398-585">La única limitación es que ambos accesos directos deben contener la clave "Windows Logotipo" (además de al menos otra clave).</span><span class="sxs-lookup"><span data-stu-id="90398-585">The only limitation is that both shortcuts must contain the "Windows Logo" key (in addition to at least another key).</span></span>

- <span data-ttu-id="90398-586">Comience con Windows: la aplicación se puede configurar para que se inicie automáticamente con Windows.</span><span class="sxs-lookup"><span data-stu-id="90398-586">Start with Windows: The application can be configured to start automatically with Windows.</span></span>

### <a name="examples"></a><span data-ttu-id="90398-587">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="90398-587">Examples</span></span>

<span data-ttu-id="90398-588">En la figura siguiente se muestra cómo llamar o enviar una mensajería instantánea a otro agente haciendo clic con el botón secundario en el contacto en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="90398-588">The figure below illustrates how to call or send an IM to another agent by right-clicking the contact in the right pane.</span></span>

![Realizar una llamada o enviar una mensajería instantánea.](../media/Reskit_2012_Tools_Documentation_Image39.JPG)

<span data-ttu-id="90398-590">En la figura siguiente se muestra cómo el agente de grupo de respuesta Live muestra el número actual de llamadas en la cola y el tiempo de espera más largo entre todas estas llamadas entrantes.</span><span class="sxs-lookup"><span data-stu-id="90398-590">The figure below illustrates how Response Group Agent Live displays the current number of calls in the queue and the longest waiting time among all these incoming calls.</span></span>

![Visualización de información de cola.](../media/Reskit_2012_Tools_Documentation_Image40.JPG)

### <a name="summary"></a><span data-ttu-id="90398-592">Resumen</span><span class="sxs-lookup"><span data-stu-id="90398-592">Summary</span></span>

<span data-ttu-id="90398-593">El inicio y cierre de sesión rápidos, la pertenencia a grupos y las estadísticas básicas en tiempo real son características de agente de grupo de respuesta interesantes que solo están disponibles fuera de la aplicación desde el servicio grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="90398-593">Fast sign in and sign out, group membership, and basic real-time statistics are interesting Response Group agent features that are only available outside the application from the Response Group service.</span></span> <span data-ttu-id="90398-594">Con la herramienta Kit de recursos en directo del agente de grupo de respuesta, los administradores de Skype Empresarial Server 2015 pueden proporcionar a sus agentes una aplicación Windows que les permita realizar tareas de forma más rápida y gráfica.</span><span class="sxs-lookup"><span data-stu-id="90398-594">With the Response Group Agent Live Resource Kit tool, Skype for Business Server 2015 administrators can provide their agents with a Windows application that allows them to perform tasks in a faster and graphical way.</span></span>

## <a name="sefautil"></a><span data-ttu-id="90398-595">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="90398-595">SEFAUtil</span></span>
<span data-ttu-id="90398-596"><a name="SEFAUtil"> </a></span><span class="sxs-lookup"><span data-stu-id="90398-596"><a name="SEFAUtil"> </a></span></span>

<span data-ttu-id="90398-597">SEFAUtil (activación de características de extensión secundaria) es una herramienta de línea de comandos que permite Skype Empresarial Server los administradores de software de comunicaciones de 2015 y los agentes de soporte técnico configurar la llamada de delegado, el reenvío de llamadas, las llamadas simultáneas, la configuración de llamadas de equipo y la recogida de llamadas de grupo en nombre de un usuario de Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="90398-597">SEFAUtil (secondary extension feature activation) is a command-line tool that enables Skype for Business Server 2015 communications software administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="90398-598">La herramienta también permite a los administradores consultar la configuración de enrutamiento de llamadas que se publica para un usuario determinado.</span><span class="sxs-lookup"><span data-stu-id="90398-598">The tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span> <span data-ttu-id="90398-599">La herramienta SEFAUtil permite al administrador habilitar,deshabilitar o modificar el reenvío de llamadas o la llamada simultáneamente en nombre del usuario.</span><span class="sxs-lookup"><span data-stu-id="90398-599">The SEFAUtil tool allows the administrator to enable/disable/modify call forwarding or simultaneously ringing on behalf of the user.</span></span> <span data-ttu-id="90398-600">El administrador puede especificar el destino (en forma de URI de SIP) o usar un destino que ya haya publicado el usuario.</span><span class="sxs-lookup"><span data-stu-id="90398-600">The administrator can specify the target (in the form of a SIP URI) or use a target that has already been published by the user.</span></span> <span data-ttu-id="90398-601">Esta herramienta también permite a los administradores agregar o quitar delegados o miembros del grupo de llamadas de grupo en nombre del usuario.</span><span class="sxs-lookup"><span data-stu-id="90398-601">This tool also allows administrators to add or remove delegates or team-call group members on behalf of the user.</span></span> <span data-ttu-id="90398-602">Esta herramienta se basa en microsoft Unified Communications Managed API (UCMA) 3.0 y requiere que los administradores creen una aplicación de confianza en el almacén de administración central para SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="90398-602">This tool is built on Microsoft Unified Communications Managed API (UCMA) 3.0 and requires that administrators create a trusted application in the Central Management store for SEFAUtil.</span></span>

<span data-ttu-id="90398-603">SEFAUtil (activación de características de extensión secundaria) permite Skype Empresarial Server los administradores y agentes de soporte técnico de 2015 configurar la llamada de delegado, el reenvío de llamadas, las llamadas simultáneas, la configuración de llamadas de grupo y la recogida de llamadas de grupo en nombre de un usuario de Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="90398-603">SEFAUtil (secondary extension feature activation) enables Skype for Business Server 2015 administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="90398-604">Esta herramienta también permite a los administradores consultar la configuración de enrutamiento de llamadas que se publica para un usuario determinado.</span><span class="sxs-lookup"><span data-stu-id="90398-604">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span>

### <a name="description"></a><span data-ttu-id="90398-605">Descripción</span><span class="sxs-lookup"><span data-stu-id="90398-605">Description</span></span>

<span data-ttu-id="90398-606">La versión actual de SEFAUtil es solo una herramienta de línea de comandos; no hay ninguna interfaz gráfica de usuario compatible.</span><span class="sxs-lookup"><span data-stu-id="90398-606">The current version of SEFAUtil is only a command-line tool; there is no supporting graphical user interface.</span></span> <span data-ttu-id="90398-607">Esta herramienta se basa en la API administrada de comunicaciones unificadas de Microsoft (UCMA) 3.0.</span><span class="sxs-lookup"><span data-stu-id="90398-607">This tool is based on Microsoft Unified Communications Managed API (UCMA) 3.0.</span></span> <span data-ttu-id="90398-608">Las características de esta herramienta permiten a los administradores y agentes de soporte técnico hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="90398-608">The features in this tool allow administrators and helpdesk agents to do the following:</span></span>

- <span data-ttu-id="90398-609">Ver todas las opciones de enrutamiento de llamadas de un usuario (incluye el reenvío de llamadas, la delegación, la llamada simultánea, la llamada de grupo y la recogida de llamadas de grupo)</span><span class="sxs-lookup"><span data-stu-id="90398-609">View all call routing settings for a user (includes call-forwarding, delegation, simultaneous ringing, team-call, and group call pickup)</span></span>

- <span data-ttu-id="90398-610">Habilitar/deshabilitar/modificar la configuración de reenvío de llamadas (incluye el temporizador de destino y sin respuesta)</span><span class="sxs-lookup"><span data-stu-id="90398-610">Enable/disable/modify call-forwarding setting (includes destination and no-answer timer)</span></span>

- <span data-ttu-id="90398-611">Habilitar/deshabilitar/modificar configuraciones inmediatas de reenvío de llamadas</span><span class="sxs-lookup"><span data-stu-id="90398-611">Enable/disable/modify call-forwarding immediate configurations</span></span>

- <span data-ttu-id="90398-612">Habilitar/deshabilitar/modificar la configuración de delegación</span><span class="sxs-lookup"><span data-stu-id="90398-612">Enable/disable/modify delegation settings</span></span>

- <span data-ttu-id="90398-613">Habilitar/deshabilitar/modificar la configuración del grupo de llamadas de equipo</span><span class="sxs-lookup"><span data-stu-id="90398-613">Enable/disable/modify team-call group settings</span></span>

    > [!NOTE]
    > <span data-ttu-id="90398-614">Nuevo en Skype Empresarial Server herramienta SEFAUtil de 2015</span><span class="sxs-lookup"><span data-stu-id="90398-614">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

- <span data-ttu-id="90398-615">Habilitar/deshabilitar/modificar la configuración de llamadas simultáneas (incluye el destino)</span><span class="sxs-lookup"><span data-stu-id="90398-615">Enable/disable/modify simultaneous ringing settings (includes destination)</span></span>

    > [!NOTE]
    > <span data-ttu-id="90398-616">Nuevo en Skype Empresarial Server herramienta SEFAUtil de 2015</span><span class="sxs-lookup"><span data-stu-id="90398-616">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

- <span data-ttu-id="90398-617">Habilitar/deshabilitar/modificar la configuración de recogida de llamadas de grupo</span><span class="sxs-lookup"><span data-stu-id="90398-617">Enable/disable/modify group call pickup settings</span></span>

    > [!CAUTION]
    > <span data-ttu-id="90398-618">Nuevo en Skype Empresarial Server herramienta SEFAUtil de 2015</span><span class="sxs-lookup"><span data-stu-id="90398-618">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

<span data-ttu-id="90398-619">Esta herramienta tiene las siguientes limitaciones:</span><span class="sxs-lookup"><span data-stu-id="90398-619">This tool has the following limitations:</span></span>

- <span data-ttu-id="90398-620">Solo se admite para usuarios que se alo Skype Empresarial Server grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="90398-620">Supported only for users homed in a Skype for Business Server pool</span></span>

- <span data-ttu-id="90398-621">No se admite la edición masiva de la configuración de enrutamiento de llamadas para varios usuarios</span><span class="sxs-lookup"><span data-stu-id="90398-621">Bulk-edit of call routing settings for several users is not supported</span></span>

### <a name="output"></a><span data-ttu-id="90398-622">Salida</span><span class="sxs-lookup"><span data-stu-id="90398-622">Output</span></span>

<span data-ttu-id="90398-623">La versión actual de esta herramienta solo proporciona resultados en la ventana del símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="90398-623">The current version of this tool provides output only in the Command Prompt window.</span></span> <span data-ttu-id="90398-624">Para obtener más información, vea la sección Ejemplos más adelante en este documento.</span><span class="sxs-lookup"><span data-stu-id="90398-624">For details, see the Examples section later in this document.</span></span>

### <a name="purpose"></a><span data-ttu-id="90398-625">Objetivo</span><span class="sxs-lookup"><span data-stu-id="90398-625">Purpose</span></span>

<span data-ttu-id="90398-626">Estos son algunos de los escenarios clave en los que se puede usar esta herramienta:</span><span class="sxs-lookup"><span data-stu-id="90398-626">Following are some of the key scenarios where this tool may be used:</span></span>

- <span data-ttu-id="90398-627">Bob es un ejecutivo y se ha movido a Skype Empresarial Server telefonía.</span><span class="sxs-lookup"><span data-stu-id="90398-627">Bob is an executive and has been moved to Skype for Business Server telephony.</span></span> <span data-ttu-id="90398-628">Tiene delegación en su sistema PBX existente.</span><span class="sxs-lookup"><span data-stu-id="90398-628">He has delegation on his existing PBX system.</span></span> <span data-ttu-id="90398-629">Como parte del traslado a Skype Empresarial Server 2015, el administrador puede configurar el enrutamiento de Bob para reflejar su configuración de delegación preexistida.</span><span class="sxs-lookup"><span data-stu-id="90398-629">As part of the move to Skype for Business Server 2015, the administrator is able to configure Bob's routing to reflect his pre-existing delegation configuration.</span></span>

- <span data-ttu-id="90398-630">Alicia está de viaje y se da cuenta de que espera una llamada importante de uno de sus clientes.</span><span class="sxs-lookup"><span data-stu-id="90398-630">Alice is traveling and realizes that she is expecting an important call from one of her customers.</span></span> <span data-ttu-id="90398-631">Sin embargo, está en un hotel y no tiene acceso a un equipo.</span><span class="sxs-lookup"><span data-stu-id="90398-631">However, she is in a hotel and has no access to a computer.</span></span> <span data-ttu-id="90398-632">Llama al departamento de soporte técnico y solicita que reenván a su número de teléfono móvil todas las llamadas realizadas a su número de trabajo.</span><span class="sxs-lookup"><span data-stu-id="90398-632">She calls the helpdesk and requests that they forward to her mobile number all the calls made to her work number.</span></span> <span data-ttu-id="90398-633">El personal del departamento de soporte técnico puede realizar la configuración en su nombre.</span><span class="sxs-lookup"><span data-stu-id="90398-633">The helpdesk personnel are able to do the configuration on her behalf.</span></span>

- <span data-ttu-id="90398-634">Las llamadas de Joe a su número de trabajo van a su correo de voz móvil siempre que esté en el trabajo; sin embargo, parece que las cosas funcionan correctamente en la mayoría de otras ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="90398-634">Joe's calls to his work number are going to his mobile voicemail whenever he is at work; however, things appear to be working correctly in most other locations.</span></span> <span data-ttu-id="90398-635">El técnico del departamento de soporte técnico puede ver la configuración de enrutamiento de Joe y descubre que Joe tiene llamadas simultáneas configuradas en su teléfono móvil.</span><span class="sxs-lookup"><span data-stu-id="90398-635">The helpdesk technician is able to view Joe's routing configuration and discovers that Joe has simultaneous ringing configured to his mobile phone.</span></span> <span data-ttu-id="90398-636">El técnico pregunta a Joe sobre la cobertura móvil en su oficina y puede determinar que la regla de llamada simultánea es lo que hace que las llamadas vayan al correo de voz móvil de Joe cuando su cobertura de red es mala.</span><span class="sxs-lookup"><span data-stu-id="90398-636">The technician asks Joe about the mobile coverage at his office and is able to determine that the simultaneous ringing rule is what is causing the calls to go to Joe's mobile voicemail when his network coverage is poor.</span></span>

- <span data-ttu-id="90398-637">Mike es un nuevo empleado de Contoso y se une a un nuevo equipo en el que todos los miembros están configurados para la llamada de equipo, cuando se habilita para Skype Empresarial Server 2015, el administrador puede establecer la configuración del grupo de llamadas de equipo para incluir todos los miembros de su nuevo equipo, además, el administrador agrega a Mike como miembro del grupo de llamadas de grupo para cada uno de los miembros de su equipo.</span><span class="sxs-lookup"><span data-stu-id="90398-637">Mike is a new employee at Contoso and he's joining a new team on which all members are configured for team-call, when being enabled for Skype for Business Server 2015, the administrator is able to set his team-call group settings to include all his new team members, additionally, the administrator adds Mike as a team-call group member for each of the members in his team.</span></span>

- <span data-ttu-id="90398-638">Una práctica de servicio al cliente en el departamento de recursos humanos de Contoso es proporcionar servicio personal para todos los autores de llamadas desde la primera llamada.</span><span class="sxs-lookup"><span data-stu-id="90398-638">A customer service practice in the human resources department at Contoso is to provide personal service for all callers since the first call.</span></span> <span data-ttu-id="90398-639">Dado que todos los miembros del departamento se sientan muy cerca unos de otros, hacer que todos los teléfonos suene al mismo tiempo con la llamada de equipo es perjudicial para el equipo.</span><span class="sxs-lookup"><span data-stu-id="90398-639">Given that all members of the department sit very close to each other, having all phones ringing at the same time with team-call is disruptive for the team.</span></span> <span data-ttu-id="90398-640">Para proporcionar el mejor servicio sin interrumpir a los miembros del equipo, el administrador de Skype Empresarial Server 2015 aprovecha la funcionalidad de recogida de llamadas en grupo.</span><span class="sxs-lookup"><span data-stu-id="90398-640">To provide the best service without disrupting the team members, the Skype for Business Server 2015 administrator takes advantage of the Group Call Pickup capability.</span></span> <span data-ttu-id="90398-641">El administrador agrega todos los miembros del departamento a un grupo de recogida y comunica al departamento el número de grupo de recogida.</span><span class="sxs-lookup"><span data-stu-id="90398-641">The administrator adds all department members to a pickup group and communicates to the department the pickup group number.</span></span> <span data-ttu-id="90398-642">Cuando Samantha está ausente de su escritorio, Joe observa su teléfono sonando y procede a responder la llamada desde su escritorio.</span><span class="sxs-lookup"><span data-stu-id="90398-642">When Samantha is absent from her desk, Joe notices her phone ringing and he proceeds to answer the call from his desk.</span></span>

### <a name="requirements"></a><span data-ttu-id="90398-643">Requirements</span><span class="sxs-lookup"><span data-stu-id="90398-643">Requirements</span></span>

<span data-ttu-id="90398-644">La herramienta SEFAUtil solo se puede ejecutar en un equipo que forma parte de un grupo de aplicaciones de confianza.</span><span class="sxs-lookup"><span data-stu-id="90398-644">The SEFAUtil tool can be run only on a computer that is a part of a Trusted Application Pool.</span></span> <span data-ttu-id="90398-645">UCMA 3.0 debe instalarse en ese equipo.</span><span class="sxs-lookup"><span data-stu-id="90398-645">UCMA 3.0 must be installed on that computer.</span></span> <span data-ttu-id="90398-646">Para ejecutar la herramienta, se debe crear una nueva aplicación de confianza con el identificador de aplicación SEFAUtil en ese grupo.</span><span class="sxs-lookup"><span data-stu-id="90398-646">To run the tool, a new Trusted Application with the SEFAUtil application ID must be created on that pool.</span></span>

### <a name="creating-a-new-trusted-application-for-the-sefautil-tool"></a><span data-ttu-id="90398-647">Creación de una nueva aplicación de confianza para la herramienta SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="90398-647">Creating a new Trusted Application for the SEFAUtil tool</span></span>

1. <span data-ttu-id="90398-648">La herramienta SEFAUTil solo se puede ejecutar en un equipo que forma parte de un grupo de aplicaciones de confianza.</span><span class="sxs-lookup"><span data-stu-id="90398-648">The SEFAUTil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="90398-649">Si es necesario, la adición de un grupo de servidores como un nuevo grupo de aplicaciones de confianza se puede realizar a través del Shell de administración de Skype Empresarial Server con el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="90398-649">If needed, adding a pool as a new trusted application pool can be done via the Skype for Business Server Management Shell with the following cmdlet:</span></span>

   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

    > [!NOTE]
    > <span data-ttu-id="90398-650">UCMA 3.0 debe instalarse en cualquier equipo que se usará para ejecutar la herramienta SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="90398-650">UCMA 3.0 must be installed on any computer that will be used to run the SEFAUtil tool.</span></span>

2. <span data-ttu-id="90398-651">Debe definirse una aplicación de confianza en la topología de la herramienta SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="90398-651">A trusted application needs to be defined in the topology for the SEFAUtil tool.</span></span> <span data-ttu-id="90398-652">Para definir SEFAUtil como una nueva aplicación de confianza, use el Shell de administración Skype Empresarial Server y ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="90398-652">To define SEFAUtil as a new trusted application, use the Skype for Business Server Management Shell and execute the following cmdlet:</span></span>

   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN> -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="90398-653">Se puede usar un puerto diferente si es necesario.</span><span class="sxs-lookup"><span data-stu-id="90398-653">A different port can be used if needed.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="90398-654">FQDN del grupo de servidores: el FQDN del servidor o grupo de servidores que hospedará la aplicación SEFAUtil Skype Empresarial (normalmente un servidor front-end > o grupo de servidores).</span><span class="sxs-lookup"><span data-stu-id="90398-654">Pool FQDN: The FQDN of the server or pool that will host the SEFAUtil application (usually a Skype for Business Front End server     > or pool).</span></span>
    > <span data-ttu-id="90398-655">FQDN del registrador de grupo: fqdn del servidor front-end o grupo de servidores Skype Empresarial asociado con este grupo de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="90398-655">Pool Registrar FQDN: The FQDN of the Skype for Business Front End server or pool associated with this application pool.</span></span>
    > <span data-ttu-id="90398-656">Sitio de grupo: el identificador de sitio del sitio en el que se encuentra este grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="90398-656">Pool Site: The Site ID of the site on which this pool is homed.</span></span>

3. <span data-ttu-id="90398-657">Los cambios de topología deben estar habilitados.</span><span class="sxs-lookup"><span data-stu-id="90398-657">The topology changes need to be enabled.</span></span> <span data-ttu-id="90398-658">La habilitación de los cambios en la topología se puede realizar a través del Shell de administración Skype Empresarial Server mediante la ejecución del siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="90398-658">Enabling the topology changes can be done via the Skype for Business Server Management Shell by executing the following cmdlet:</span></span>

   ```powershell
   Enable-CsToplogy
   ```

4. <span data-ttu-id="90398-659">Si es necesario, instale Skype Empresarial Server 2015 Resource Kit Tools en el servidor que se usará para ejecutar la herramienta SEFAUtil (el servidor debe formar parte de un grupo de aplicaciones de confianza).</span><span class="sxs-lookup"><span data-stu-id="90398-659">If needed, install the Skype for Business Server 2015 Resource Kit Tools in the server that will be used to run the SEFAUtil tool (the server must be part of a trusted application pool).</span></span>

5. <span data-ttu-id="90398-660">Compruebe que SEFAUtil se está ejecutando correctamente.</span><span class="sxs-lookup"><span data-stu-id="90398-660">Verify the SEFAUtil is running correctly.</span></span> <span data-ttu-id="90398-661">Para ello, ejecute la herramienta desde un símbolo del sistema de Windows con privilegios de administrador para mostrar la configuración de reenvío de llamadas de un usuario en la implementación.</span><span class="sxs-lookup"><span data-stu-id="90398-661">To do this, run the tool from a windows command prompt with administrator privileges to display the call forwarding settings of a user in the deployment.</span></span> <span data-ttu-id="90398-662">De forma predeterminada, la herramienta se ubicará en: "...\Archivos de programa\Skype Empresarial Server 2015\Reskit".</span><span class="sxs-lookup"><span data-stu-id="90398-662">By default the tool will be located in: "…\Program Files\Skype for Business Server 2015\Reskit".</span></span> <span data-ttu-id="90398-663">Para mostrar la configuración de reenvío de llamadas de un usuario, use el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="90398-663">To display the call forwarding settings of a user, use the following command:</span></span>

   ```console
   SEFAUtil.exe <user SIP address> /server:<Skype for Business Server/Pool FQDN>
   ```

    <span data-ttu-id="90398-664">Se debe mostrar la configuración de reenvío de llamadas del usuario.</span><span class="sxs-lookup"><span data-stu-id="90398-664">The call forwarding settings of the user should be displayed.</span></span>

#### <a name="group-call-pickup"></a><span data-ttu-id="90398-665">Atender llamada grupal</span><span class="sxs-lookup"><span data-stu-id="90398-665">Group Call Pickup</span></span>

<span data-ttu-id="90398-666">La recogida de llamadas de grupo requiere una configuración adicional en Skype Empresarial Server 2015 para que la funcionalidad esté totalmente habilitada.</span><span class="sxs-lookup"><span data-stu-id="90398-666">Group Call Pickup requires additional configuration in Skype for Business Server 2015 for the capability to be fully enabled.</span></span> <span data-ttu-id="90398-667">Antes de asignar grupos de recogida a los usuarios, consulte la documentación del producto de recogida de llamadas en grupo para ver los pasos de planeación e implementación de esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="90398-667">Before assigning pickup groups to users, refer to the Group Call Pickup product documentation for the planning and deployment steps of this capability.</span></span>

### <a name="examples"></a><span data-ttu-id="90398-668">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="90398-668">Examples</span></span>

#### <a name="display-current-call-handling-settings"></a><span data-ttu-id="90398-669">Mostrar el control de llamadas actual Configuración</span><span class="sxs-lookup"><span data-stu-id="90398-669">Display Current Call Handling Settings</span></span>

<span data-ttu-id="90398-670">El siguiente comando muestra el control de llamadas para el usuario.</span><span class="sxs-lookup"><span data-stu-id="90398-670">The following command displays the call handling for the user.</span></span>  `SEFAUtil.exe /server:SfBS2015server.contoso.com katarina@contoso.com`

> [!NOTE]
> <span data-ttu-id="90398-671">En este ejemplo se usa el modificador **/server** para especificar el Skype Empresarial Server al que conectarse.</span><span class="sxs-lookup"><span data-stu-id="90398-671">This example uses the **/server** switch to specify the Skype for Business Server to connect to.</span></span>

 <span data-ttu-id="90398-672">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="90398-672">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:20
Call Forward No Answer to: voicemail
```

#### <a name="set-the-call-forwardno-answer-destination"></a><span data-ttu-id="90398-673">Establecer el destino Desviado de llamada/Sin respuesta</span><span class="sxs-lookup"><span data-stu-id="90398-673">Set the Call Forward/No Answer Destination</span></span>

<span data-ttu-id="90398-674">En este ejemplo se establece el destino de la llamada directa o sin respuesta y el retraso del anillo.</span><span class="sxs-lookup"><span data-stu-id="90398-674">This example sets the call forward/no answer destination and the ring delay.</span></span> <span data-ttu-id="90398-675">Aquí, no se proporciona el modificador /server; SEFAUtil intenta detección automática del Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="90398-675">Here, the /server switch is not provided; SEFAUtil attempts to autodiscover the Skype for Business Server 2015.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+14255550126@contoso.com;user=phone
```

 <span data-ttu-id="90398-676">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="90398-676">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="enable-call-forwarding-immediately"></a><span data-ttu-id="90398-677">Habilitar el reenvío de llamadas inmediatamente</span><span class="sxs-lookup"><span data-stu-id="90398-677">Enable Call Forwarding Immediately</span></span>

<span data-ttu-id="90398-678">En este ejemplo se habilita inmediatamente el reenvío de llamadas a otro usuario.</span><span class="sxs-lookup"><span data-stu-id="90398-678">This example immediately enables call-forwarding to another user.</span></span>

```console
SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com
```

 <span data-ttu-id="90398-679">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="90398-679">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Forward immediate to: sip:anders@contoso.com
```

#### <a name="disable-call-forwarding-immediately"></a><span data-ttu-id="90398-680">Deshabilitar el reenvío de llamadas inmediatamente</span><span class="sxs-lookup"><span data-stu-id="90398-680">Disable Call Forwarding Immediately</span></span>

<span data-ttu-id="90398-681">En este ejemplo se deshabilita inmediatamente el reenvío de llamadas.</span><span class="sxs-lookup"><span data-stu-id="90398-681">This example immediately disables call forwarding.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com katarina@contoso.com /disablefwdimmediate
```

 <span data-ttu-id="90398-682">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="90398-682">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a><span data-ttu-id="90398-683">Agregar un usuario como delegado y configurar llamadas simultáneas de delegados</span><span class="sxs-lookup"><span data-stu-id="90398-683">Add a User as a Delegate and Set Up Simultaneous Ringing of Delegates</span></span>

<span data-ttu-id="90398-684">En este ejemplo se agrega un usuario como delegado y se configura la llamada simultánea de delegados.</span><span class="sxs-lookup"><span data-stu-id="90398-684">This example adds a user as a delegate and sets up simultaneous ringing of delegates.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates
```

 <span data-ttu-id="90398-685">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="90398-685">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simultaneously Ringing Delegates: sip:joe@contoso.com
```

#### <a name="change-simultaneous-ringing-rule-of-delegates"></a><span data-ttu-id="90398-686">Cambiar la regla de llamada simultánea de delegados</span><span class="sxs-lookup"><span data-stu-id="90398-686">Change Simultaneous Ringing Rule of Delegates</span></span>

<span data-ttu-id="90398-687">En este ejemplo se cambia la regla de llamada simultánea que se estableció en el ejemplo anterior a la regla de llamada retrasada.</span><span class="sxs-lookup"><span data-stu-id="90398-687">This example changes the simultaneous ringing rule that was set in the previous example to the delayed ringing rule.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10
```

 <span data-ttu-id="90398-688">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="90398-688">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com
```

#### <a name="remove-the-delegate"></a><span data-ttu-id="90398-689">Quitar el delegado</span><span class="sxs-lookup"><span data-stu-id="90398-689">Remove the Delegate</span></span>

<span data-ttu-id="90398-690">En este ejemplo se quita el delegado.</span><span class="sxs-lookup"><span data-stu-id="90398-690">This example removes the delegate.</span></span>

> [!NOTE]
> <span data-ttu-id="90398-691">Cuando se quita el último delegado, la llamada de delegado se deshabilita automáticamente.</span><span class="sxs-lookup"><span data-stu-id="90398-691">When the last delegate is removed, delegate ringing is automatically disabled.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com
```

 <span data-ttu-id="90398-692">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="90398-692">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a><span data-ttu-id="90398-693">Agregar un delegado y configurar el Call-Forward a la regla de delegados</span><span class="sxs-lookup"><span data-stu-id="90398-693">Add a Delegate and Set Up the Call-Forward to Delegates Rule</span></span>

<span data-ttu-id="90398-694">En este ejemplo se agrega un delegado y se configura la regla de reenvío de llamadas a los delegados.</span><span class="sxs-lookup"><span data-stu-id="90398-694">This example adds a delegate and sets up the call-forward to delegates rule.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates
```

 <span data-ttu-id="90398-695">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="90398-695">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Forwarding calls to Delegates: sip:anders@contoso.com
```

#### <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a><span data-ttu-id="90398-696">Habilitar la llamada simultánea y establecer un número de destino</span><span class="sxs-lookup"><span data-stu-id="90398-696">Enable Simultaneous Ringing and Set a Destination Number</span></span>

<span data-ttu-id="90398-697">En este ejemplo se habilitan las llamadas simultáneas y se establece un número de destino de llamada simultánea.</span><span class="sxs-lookup"><span data-stu-id="90398-697">This example enables simultaneous ringing and sets a simultaneous ringing destination number.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring
```

> [!NOTE]
> <span data-ttu-id="90398-698">Para cambiar el número de destino de llamada simultánea de un usuario que ya tiene habilitada la llamada simultánea, mantenga el comando con el modificador /enablesimulring, de lo contrario no se cambiará el número de destino.</span><span class="sxs-lookup"><span data-stu-id="90398-698">To change the simultaneous ringing destination number of a user that has already simultaneous ringing enabled, keep the command with the /enablesimulring switch, otherwise the destination number will not be changed.</span></span>

 <span data-ttu-id="90398-699">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="90398-699">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: True
Simul_Ringing to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="disable-simultaneous-ringing"></a><span data-ttu-id="90398-700">Deshabilitar la llamada simultánea</span><span class="sxs-lookup"><span data-stu-id="90398-700">Disable Simultaneous Ringing</span></span>

<span data-ttu-id="90398-701">En este ejemplo se deshabilita la llamada simultánea.</span><span class="sxs-lookup"><span data-stu-id="90398-701">This example disables simultaneous ringing.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablesimulring
```

 <span data-ttu-id="90398-702">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="90398-702">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a><span data-ttu-id="90398-703">Agregar un miembro de grupo para Team-Call y Configurar llamadas simultáneas al grupo Team-Call miembros</span><span class="sxs-lookup"><span data-stu-id="90398-703">Add a Team Member for Team-Call and Set up Simultaneous Ringing to the Team-Call Members Group</span></span>

<span data-ttu-id="90398-704">En este ejemplo se agrega un miembro del equipo al grupo de llamadas de grupo de un usuario y se habilita la llamada simultánea al grupo de llamadas de grupo.</span><span class="sxs-lookup"><span data-stu-id="90398-704">This example adds a team member to the team-call group of a user and enables simultaneous ringing to the team-call group.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="90398-705">Agregar un miembro al grupo de llamadas de grupo de un usuario cambiará automáticamente los grupos de llamadas simultáneas de los usuarios para que llamen simultáneamente a su grupo de llamadas de grupo.</span><span class="sxs-lookup"><span data-stu-id="90398-705">Adding a member to the team-call group of a user will automatically switch the simultaneous ringing settigs of the users to simultaneous ring his team-call group.</span></span>

 <span data-ttu-id="90398-706">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="90398-706">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Team ringing enabled. Team: sip:anders@contoso.com
```

#### <a name="remove-a-member-from-the-team-call-group"></a><span data-ttu-id="90398-707">Quitar un miembro del grupo Team-Call grupo</span><span class="sxs-lookup"><span data-stu-id="90398-707">Remove a Member from the Team-Call Group</span></span>

<span data-ttu-id="90398-708">En este ejemplo se quita un miembro del equipo del grupo de llamadas de grupo de un usuario.</span><span class="sxs-lookup"><span data-stu-id="90398-708">This example removes a team member of the team-call group of a user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com
```

> [!NOTE]
> <span data-ttu-id="90398-709">Si el miembro que se quita es el único miembro del grupo de llamadas de grupo, la llamada simultánea al grupo de llamadas de grupo se deshabilitará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="90398-709">If the member being removed is the only member of the team-call group, simultaneously ringing to the team-call group will be automatically disabled.</span></span>

 <span data-ttu-id="90398-710">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="90398-710">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="set-the-delayed-ring-to-the-team-call-group"></a><span data-ttu-id="90398-711">Establecer el anillo retrasado en el Team-Call grupo</span><span class="sxs-lookup"><span data-stu-id="90398-711">Set the Delayed Ring to the Team-Call Group</span></span>

<span data-ttu-id="90398-712">En este ejemplo se cambia el anillo retrasado a la configuración de tiempo de grupo de llamadas de grupo.</span><span class="sxs-lookup"><span data-stu-id="90398-712">This example changes the delayed ring to the team-call group time setting.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringteam:5
```

 <span data-ttu-id="90398-713">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="90398-713">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com
```

#### <a name="enable-team-call"></a><span data-ttu-id="90398-714">Habilitar Team-Call</span><span class="sxs-lookup"><span data-stu-id="90398-714">Enable Team-Call</span></span>

<span data-ttu-id="90398-715">En este ejemplo se habilita la llamada de equipo para un usuario determinado.</span><span class="sxs-lookup"><span data-stu-id="90398-715">This example enables team-call for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="90398-716">Si el grupo de llamadas de grupo del usuario no tiene miembros, la llamada de equipo no se habilitará.</span><span class="sxs-lookup"><span data-stu-id="90398-716">If the team-call group of the user has no members, team-call won't be enabled.</span></span>

 <span data-ttu-id="90398-717">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="90398-717">**Output**</span></span>

#### <a name="disable-team-call"></a><span data-ttu-id="90398-718">Deshabilitar Team-Call</span><span class="sxs-lookup"><span data-stu-id="90398-718">Disable Team-Call</span></span>

<span data-ttu-id="90398-719">En este ejemplo se deshabilita la llamada de equipo para un usuario determinado.</span><span class="sxs-lookup"><span data-stu-id="90398-719">This example disables team-call for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disableteamcall
```

 <span data-ttu-id="90398-720">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="90398-720">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a><span data-ttu-id="90398-721">Habilitar la recogida de llamadas de grupo y asignar un grupo de recogida a un usuario</span><span class="sxs-lookup"><span data-stu-id="90398-721">Enable Group Call Pickup and Assign a Pickup Group to a User</span></span>

<span data-ttu-id="90398-722">En este ejemplo se asigna un grupo de recogida a un usuario y se habilita la recogida de llamadas de grupo.</span><span class="sxs-lookup"><span data-stu-id="90398-722">This example assigns a pickup group to a user and enables Group Call Pickup.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199
```

 <span data-ttu-id="90398-723">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="90398-723">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Group Pickup Orbit: sip:199;phone-context=user-default@contoso.com;user=phone
```

#### <a name="disable-group-call-pickup"></a><span data-ttu-id="90398-724">Deshabilitar la recogida de llamadas de grupo</span><span class="sxs-lookup"><span data-stu-id="90398-724">Disable Group Call Pickup</span></span>

<span data-ttu-id="90398-725">En este ejemplo se deshabilita la recogida de llamadas de grupo para un usuario determinado.</span><span class="sxs-lookup"><span data-stu-id="90398-725">This example disables Group Call Pickup for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablegrouppickup
```

> [!NOTE]
> <span data-ttu-id="90398-726">Al deshabilitar la recogida de llamadas de grupo para un usuario, el número de grupo que se asignó al usuario no se conserva.</span><span class="sxs-lookup"><span data-stu-id="90398-726">When you disable Group Call Pickup for a user, the group number that was assigned to the user is not retained.</span></span> <span data-ttu-id="90398-727">Si posteriormente desea volver a habilitar la recogida de llamadas de grupo para ese usuario, debe asignar el número de grupo de nuevo con el modificador /enablegrouppickup.</span><span class="sxs-lookup"><span data-stu-id="90398-727">If you subsequently want to re-enable Group Call Pickup for that user, you must assign the group number again with the /enablegrouppickup switch.</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
```

## <a name="sysprepps1"></a><span data-ttu-id="90398-728">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="90398-728">SYSPrep.ps1</span></span>
<span data-ttu-id="90398-729"><a name="SYSPrep"> </a></span><span class="sxs-lookup"><span data-stu-id="90398-729"><a name="SYSPrep"> </a></span></span>

### <a name="description"></a><span data-ttu-id="90398-730">Descripción</span><span class="sxs-lookup"><span data-stu-id="90398-730">Description</span></span>

<span data-ttu-id="90398-731">SYSPrep.ps1 es un script Windows PowerShell que instalará los siguientes requisitos previos Skype Empresarial Server 2015 en el equipo del sistema operativo Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="90398-731">SYSPrep.ps1 is a Windows PowerShell script that will install the following Skype for Business Server 2015 prerequisites on your Windows Server 2008 operating system machine.</span></span>

- <span data-ttu-id="90398-732">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="90398-732">Microsoft .NET Framework 4.5</span></span>

- <span data-ttu-id="90398-733">Microsoft SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="90398-733">Microsoft SQL Server Express</span></span>

- <span data-ttu-id="90398-734">Windows PowerShell versión 3.0</span><span class="sxs-lookup"><span data-stu-id="90398-734">Windows PowerShell version 3.0</span></span>

- <span data-ttu-id="90398-735">Redistribuible de Visual C++ 2010</span><span class="sxs-lookup"><span data-stu-id="90398-735">Visual C++ 2010 Redistributable</span></span>

- <span data-ttu-id="90398-736">Actualizaciones de Internet Information Server</span><span class="sxs-lookup"><span data-stu-id="90398-736">Internet Information Server Updates</span></span>

- <span data-ttu-id="90398-737">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="90398-737">Windows Identity Foundation</span></span>

- <span data-ttu-id="90398-738">Skype Empresarial Server 2015 Core files</span><span class="sxs-lookup"><span data-stu-id="90398-738">Skype for Business Server 2015 Core files</span></span>

  <span data-ttu-id="90398-739">Aunque el nombre del script es similar a la Herramienta de preparación del sistema para los sistemas operativos de Microsoft Windows, son diferentes.</span><span class="sxs-lookup"><span data-stu-id="90398-739">While the script name is similar to the System Preparation Tool for the Microsoft Windows operating systems, they are different.</span></span> <span data-ttu-id="90398-740">Este script solo instalará los requisitos previos necesarios para Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="90398-740">This script will only install the required prerequisites for Skype for Business Server 2015.</span></span> <span data-ttu-id="90398-741">Una vez instalados estos requisitos previos, Windows la herramienta SYSPrep se puede usar para crear una imagen del servidor.</span><span class="sxs-lookup"><span data-stu-id="90398-741">Once those prerequisites are installed, the Windows SYSPrep tool can then be used to create an image of the server.</span></span>

### <a name="requirements"></a><span data-ttu-id="90398-742">Requirements</span><span class="sxs-lookup"><span data-stu-id="90398-742">Requirements</span></span>

<span data-ttu-id="90398-743">Antes de ejecutar el script SYSPrep.ps1, debe copiar los archivos de requisitos previos en una carpeta local en la máquina del sistema operativo Windows Server 2008 (por **ejemplo, D:\Setup).**</span><span class="sxs-lookup"><span data-stu-id="90398-743">Prior to running the SYSPrep.ps1 script, you must copy the prerequisite files to a local folder on the Windows Server 2008 operating system machine (for example **D:\Setup)**.</span></span> <span data-ttu-id="90398-744">Esta carpeta también debe incluir una copia de los archivos Skype Empresarial Server 2015, específicamente **Setup.exe.**</span><span class="sxs-lookup"><span data-stu-id="90398-744">This folder must also include a copy of the Skype for Business Server 2015 files, specifically **Setup.exe.**</span></span> <span data-ttu-id="90398-745">Los archivos de requisitos previos se pueden descargar desde las siguientes ubicaciones:</span><span class="sxs-lookup"><span data-stu-id="90398-745">The prerequisite files can be downloaded from the following locations:</span></span>


| <span data-ttu-id="90398-746">**Requisito previo**</span><span class="sxs-lookup"><span data-stu-id="90398-746">**Prerequisite**</span></span>                                | <span data-ttu-id="90398-747">**Location**</span><span class="sxs-lookup"><span data-stu-id="90398-747">**Location**</span></span>                                                            |
|:------------------------------------------------|:------------------------------------------------------------------------|
| <span data-ttu-id="90398-748">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="90398-748">Microsoft .NET Framework 4.5</span></span>  <br/>             | <https://go.microsoft.com/?linkid=9816306>  <br/>                       |
| <span data-ttu-id="90398-749">Microsoft SQL Server Express 2008 R2</span><span class="sxs-lookup"><span data-stu-id="90398-749">Microsoft SQL Server Express 2008 R2</span></span>  <br/>     | <https://www.microsoft.com/download/details.aspx?id=23650>  <br/> |
| <span data-ttu-id="90398-750">Windows PowerShell versión 3.0</span><span class="sxs-lookup"><span data-stu-id="90398-750">Windows PowerShell version 3.0</span></span>  <br/>           | <https://www.microsoft.com/download/details.aspx?id=34595>  <br/> |
| <span data-ttu-id="90398-751">Redistribuible de Visual C++ 2010</span><span class="sxs-lookup"><span data-stu-id="90398-751">Visual C++ 2010 Redistributable</span></span>  <br/>          | <https://www.microsoft.com/download/details.aspx?id=5555>  <br/>  |
| <span data-ttu-id="90398-752">Actualizaciones de Internet Information Server</span><span class="sxs-lookup"><span data-stu-id="90398-752">Internet Information Server Updates</span></span>  <br/>      | <https://www.microsoft.com/download/details.aspx?id=34869>  <br/> |
| <span data-ttu-id="90398-753">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="90398-753">Windows Identity Foundation</span></span>  <br/>              | <https://www.microsoft.com/download/details.aspx?id=17331>  <br/> |
| <span data-ttu-id="90398-754">Skype Empresarial Server 2015 Setup.exe</span><span class="sxs-lookup"><span data-stu-id="90398-754">Skype for Business Server 2015 Setup.exe</span></span>  <br/> | <span data-ttu-id="90398-755">Copiar desde Skype Empresarial Server multimedia de 2015</span><span class="sxs-lookup"><span data-stu-id="90398-755">Copy from Skype for Business Server 2015 media</span></span>  <br/>                   |

### <a name="parameter"></a><span data-ttu-id="90398-756">Parámetro</span><span class="sxs-lookup"><span data-stu-id="90398-756">Parameter</span></span>

<span data-ttu-id="90398-757">El **parámetro -SetupFolder** toma como argumento la ubicación del directorio de los archivos de requisitos previos</span><span class="sxs-lookup"><span data-stu-id="90398-757">The **-SetupFolder** parameter takes as an argument the directory location of the prerequisite files</span></span>

### <a name="examples"></a><span data-ttu-id="90398-758">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="90398-758">Examples</span></span>

<span data-ttu-id="90398-759">Para ejecutar el script SYSPrep.ps1 e instalar los requisitos previos de Skype Empresarial Server 2015, ejecute el siguiente comando desde un símbolo del sistema con privilegios elevados:</span><span class="sxs-lookup"><span data-stu-id="90398-759">To run the SYSPrep.ps1 script and install the Skype for Business Server 2015 prerequisites, run the following command from an elevated command prompt:</span></span>

```console
./SysPrep.PS1 -SetupFolder D:\Setup
```

## <a name="unassigned-number-announcements-migration"></a><span data-ttu-id="90398-760">Migración de anuncios de números sin asign</span><span class="sxs-lookup"><span data-stu-id="90398-760">Unassigned Number Announcements Migration</span></span>
<span data-ttu-id="90398-761"><a name="UNAM"> </a></span><span class="sxs-lookup"><span data-stu-id="90398-761"><a name="UNAM"> </a></span></span>

<span data-ttu-id="90398-762">La herramienta de migración de anuncios de números sin signo permite a un administrador de Skype Empresarial Server 2015 mover la configuración de números sinsignación a la que presta servicio la aplicación de anuncio desde un Skype Empresarial Server de origen o un grupo a un grupo de servidores o Skype Empresarial Server de destino.</span><span class="sxs-lookup"><span data-stu-id="90398-762">The Unassigned Number Announcements Migration tool enables a Skype for Business Server 2015 administrator to move the unassigned numbers configuration that is serviced by the announcement application from a source Skype for Business Server or Pool to a destination Skype for Business Server or Pool.</span></span>

### <a name="description"></a><span data-ttu-id="90398-763">Descripción</span><span class="sxs-lookup"><span data-stu-id="90398-763">Description</span></span>

<span data-ttu-id="90398-764">La herramienta de migración de anuncios de números sin signo es un script de Windows PowerShell que mueve la configuración de números sin signo a la que presta servicio la aplicación de anuncio de un servidor o grupo de servidores de origen a otro servidor o grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="90398-764">The Unassigned Number Announcements Migration tool is a Windows PowerShell script that moves the unassigned numbers configuration serviced by the announcement application of a source server or pool to a different server or pool.</span></span>

<span data-ttu-id="90398-765">Cuando se ejecuta, el script de migración Anuncios de números sinsignados realizará las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="90398-765">When executed, the Unassigned Number Announcements Migration script will perform the following operations:</span></span>

1. <span data-ttu-id="90398-766">Mueva todos los archivos de audio usados por los anuncios de números sin signo de la aplicación de anuncio hospedada en el servidor o grupo de servidores de origen al almacén de archivos del servidor o grupo de servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="90398-766">Move all the audio files used by the unassigned number announcements of the announcement application hosted in the source server or pool to the file store of the destination server or pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="90398-767">Los archivos de audio se quitan del grupo de origen una vez que se copian en el grupo de destino.</span><span class="sxs-lookup"><span data-stu-id="90398-767">The audio files are removed from the source pool once they're copied to the destination pool.</span></span>

2. <span data-ttu-id="90398-768">Mueva todos los anuncios de números sin signo configurados para la aplicación de anuncio hospedada en el servidor o grupo de servidores de origen al servidor o grupo de servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="90398-768">Move all unassigned number announcements configured for the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

3. <span data-ttu-id="90398-769">Reasignar todos los intervalos de números sin asignar que son atendidos por la aplicación de anuncio hospedada en el servidor o grupo de servidores de origen al servidor o grupo de destino.</span><span class="sxs-lookup"><span data-stu-id="90398-769">Reassign all the unassigned number ranges that are serviced by the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

<span data-ttu-id="90398-770">Después de ejecutar correctamente el script, el servidor de destino o el grupo de servidores atenderá ahora todos los intervalos de números sinsignar a los que presta servicio la aplicación de anuncio hospedada en el servidor o grupo de servidores de origen.</span><span class="sxs-lookup"><span data-stu-id="90398-770">After successfully running the script, all the unassigned number ranges that were serviced by the announcement application hosted in the source server or pool will now be serviced with the same configuration by the destination server or pool.</span></span>

### <a name="output"></a><span data-ttu-id="90398-771">Salida</span><span class="sxs-lookup"><span data-stu-id="90398-771">Output</span></span>

<span data-ttu-id="90398-772">El script **Move-CsAnnouncementConfiguration** indica en la ventana del Shell de administración de Skype Empresarial Server desde donde se ejecutó el éxito o error de la operación de migración.</span><span class="sxs-lookup"><span data-stu-id="90398-772">The **Move-CsAnnouncementConfiguration** script indicates in the Skype for Business Server Management Shell window from where it's executed the success or failure of the migration operation.</span></span>

<span data-ttu-id="90398-773">Si la ejecución de la operación se interrumpe por algún error, los intervalos de números sin signo que se movieron correctamente al destino permanecerán en el destino en un formulario operativo y el resto de los intervalos de números sinsignación que se migrarán permanecerán en el origen, así como en un formulario operativo.</span><span class="sxs-lookup"><span data-stu-id="90398-773">If the execution of the operation is interrupted by any error, the unassigned number ranges that were successfully moved to the destination will remain in the destination in an operational form and the rest of the unassigned number ranges to be migrated will remain in the source as well in an operational form.</span></span> <span data-ttu-id="90398-774">Para migrar completamente el resto de la configuración, vuelva a ejecutar el script después de solucionar el error.</span><span class="sxs-lookup"><span data-stu-id="90398-774">To fully migrate the rest of the configuration, rerun the script after addressing the error.</span></span>

### <a name="purpose"></a><span data-ttu-id="90398-775">Objetivo</span><span class="sxs-lookup"><span data-stu-id="90398-775">Purpose</span></span>

<span data-ttu-id="90398-776">El script de migración Anuncios de número sin signo se puede usar en los tres escenarios siguientes:</span><span class="sxs-lookup"><span data-stu-id="90398-776">The Unassigned Number Announcements Migration script can be used in the following three scenarios:</span></span>

- <span data-ttu-id="90398-777">**Migrar las opciones de configuración a una nueva versión de Skype Empresarial Server:** Contoso está en proceso de migración a Skype Empresarial Server 2015 y, como parte del proceso de migración, el administrador de Skype Empresarial Server desea mover la configuración de números sinsignar a la que presta servicio la aplicación de anuncio desde la implementación de Lync Server 2013 a la nueva implementación de Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="90398-777">**Migrating configuration settings to a new version of Skype for Business Server:** Contoso is in the process of migrating to Skype for Business Server 2015 and as part of the migration process the Skype for Business Server administrator would like to move the unassigned numbers configuration serviced by the announcement application from the Lync Server 2013 deployment to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="90398-778">Para mover las opciones de configuración, el Skype Empresarial Server usa la herramienta de migración de anuncios de números sin signo.</span><span class="sxs-lookup"><span data-stu-id="90398-778">To move the configuration settings, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool.</span></span>

- <span data-ttu-id="90398-779">**Revertir una implementación de Skype Empresarial Server 2015 a Lync Server 2013:** Debido a factores inesperados, Contoso tiene que revertir la migración a la nueva Skype Empresarial Server implementación de 2015.</span><span class="sxs-lookup"><span data-stu-id="90398-779">**Rolling back a deployment from Skype for Business Server 2015 to Lync Server 2013:** Due unexpected factors, Contoso has to roll back the migration to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="90398-780">Para minimizar las interrupciones en el servicio, el administrador de Skype Empresarial Server usa la herramienta de migración de anuncios de números sinsignar para revertir la configuración de la implementación de Skype Empresarial Server 2015 a la implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="90398-780">To minimize disruptions to the service, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool to roll back the configuration from the Skype for Business Server 2015 deployment to the Lync Server 2013 deployment.</span></span>

- <span data-ttu-id="90398-781">**Mover datos entre implementaciones:** Contoso está en el proceso de reemplazar todos los servidores de un grupo por servidores más recientes.</span><span class="sxs-lookup"><span data-stu-id="90398-781">**Moving data between deployments:** Contoso is in the process of replacing all the servers of one pool with newer servers.</span></span> <span data-ttu-id="90398-782">Su estrategia es implementar un nuevo grupo Skype Empresarial Server 2015, mover todos los datos del grupo antiguo al nuevo y, a continuación, desuso del grupo antiguo.</span><span class="sxs-lookup"><span data-stu-id="90398-782">Their strategy is to deploy a new Skype for Business Server 2015 pool, move all the data from the old to the new pool, and then deprecate the old pool.</span></span> <span data-ttu-id="90398-783">Una vez implementado el nuevo grupo de servidores, se usa la herramienta de migración Anuncios de números sinsignados para mover la configuración del grupo antiguo al nuevo.</span><span class="sxs-lookup"><span data-stu-id="90398-783">Once the new pool is deployed, the Unassigned Number Announcements Migration tool is used to move the configuration from the old pool to the new one.</span></span>

#### <a name="requirements"></a><span data-ttu-id="90398-784">Requirements</span><span class="sxs-lookup"><span data-stu-id="90398-784">Requirements</span></span>

<span data-ttu-id="90398-785">Estos son los requisitos principales necesarios para ejecutar correctamente la herramienta:</span><span class="sxs-lookup"><span data-stu-id="90398-785">The following are the main requirements needed to successfully run the tool:</span></span>

1. <span data-ttu-id="90398-786">El script debe ejecutarse desde un equipo que tenga Skype Empresarial Server Shell de administración instalado.</span><span class="sxs-lookup"><span data-stu-id="90398-786">The script must be run from a computer that has Skype for Business Server Management Shell installed.</span></span>

2. <span data-ttu-id="90398-787">La aplicación de anuncio debe implementarse correctamente en el origen y el destino Skype Empresarial servidores o grupos de servidores.</span><span class="sxs-lookup"><span data-stu-id="90398-787">The announcement application has to be successfully deployed in the source and destination Skype for Business Servers or Pools.</span></span>

#### <a name="move-csannouncementconfiguration-script"></a><span data-ttu-id="90398-788">Move-CsAnnouncementConfiguration script</span><span class="sxs-lookup"><span data-stu-id="90398-788">Move-CsAnnouncementConfiguration script</span></span>

<span data-ttu-id="90398-789">El Move-CsAnnouncementConfiguration script requiere los dos parámetros que se describen en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="90398-789">The Move-CsAnnouncementConfiguration script requires the two parameters that are described in the table below.</span></span>

![Move-CsAnnouncementConfiguration parámetros.](../media/Reskit_2012_Tools_Documentation_Image41.JPG)

### <a name="examples"></a><span data-ttu-id="90398-791">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="90398-791">Examples</span></span>

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-skype-for-business-server-2015-pool"></a><span data-ttu-id="90398-792">Mover la configuración de anuncios de números sin signo de un grupo de Lync Server 2013 a un grupo de servidores Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="90398-792">Moving the Unassigned Number Announcements Configuration from a Lync Server 2013 Pool to a Skype for Business Server 2015 Pool</span></span>

<span data-ttu-id="90398-793">En este ejemplo se mueven los anuncios de números sin signo del grupo de servidores de origen (Lync Server 2013) al grupo de servidores de destino (Skype Empresarial Server 2015).</span><span class="sxs-lookup"><span data-stu-id="90398-793">This example moves the unassigned number announcements from the source pool (Lync Server 2013) to the destination pool (Skype for Business Server 2015).</span></span>

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination SfBS2015Pool.contoso.com
```

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-skype-for-business-server-2015-pool-to-a-lync-server-2013-pool"></a><span data-ttu-id="90398-794">Mover la configuración de anuncios de números sin signo de un grupo de servidores Skype Empresarial Server 2015 a un grupo de servidores de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90398-794">Moving the Unassigned Number Announcements Configuration from a Skype for Business Server 2015 Pool to a Lync Server 2013 Pool</span></span>

<span data-ttu-id="90398-795">En este ejemplo se mueven los anuncios de números sin signo del grupo de servidores de origen (Skype Empresarial Server 2015) al grupo de servidores de destino (Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="90398-795">This example moves the unassigned number announcements from the source pool (Skype for Business Server 2015) to the destination pool (Lync Server 2013).</span></span>

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source SfBS2015Pool.contoso.com -Destination LS2013Pool.contoso.com
```

## <a name="web-conf-data"></a><span data-ttu-id="90398-796">Datos de Web Conf</span><span class="sxs-lookup"><span data-stu-id="90398-796">Web Conf Data</span></span>
<span data-ttu-id="90398-797"><a name="WebConfData"> </a></span><span class="sxs-lookup"><span data-stu-id="90398-797"><a name="WebConfData"> </a></span></span>

<span data-ttu-id="90398-798">La herramienta de datos Web Conf permite que un administrador de Skype Empresarial Server software de comunicaciones de 2015 tenga más control sobre los datos asociados con las conferencias web de un organizador.</span><span class="sxs-lookup"><span data-stu-id="90398-798">The Web Conf Data Tool allows an administrator of Skype for Business Server 2015 communications software to have more control over the data associated with an organizer's Web conferences.</span></span> <span data-ttu-id="90398-799">Los escenarios incluyen la capacidad de eliminar los datos de reunión de un usuario específico en función de un criterio de marca de tiempo.</span><span class="sxs-lookup"><span data-stu-id="90398-799">Scenarios include the ability to delete a specific user's meeting data based on a time stamp criteria.</span></span>

### <a name="description"></a><span data-ttu-id="90398-800">Descripción</span><span class="sxs-lookup"><span data-stu-id="90398-800">Description</span></span>

<span data-ttu-id="90398-801">Esta herramienta permite al administrador realizar las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="90398-801">This tool allows the administrator to perform the following operations:</span></span>

1. <span data-ttu-id="90398-802">Busque todos los datos de conferencia web asociados con un único usuario.</span><span class="sxs-lookup"><span data-stu-id="90398-802">Find all Web conferencing data associated with a single user.</span></span>

2. <span data-ttu-id="90398-803">Elimine todos los datos de conferencia web asociados con un único usuario.</span><span class="sxs-lookup"><span data-stu-id="90398-803">Delete all Web conferencing data associated with a single user.</span></span>

3. <span data-ttu-id="90398-804">Elimine todos los datos de conferencia web asociados a un único usuario con una fecha anterior a una fecha determinada.</span><span class="sxs-lookup"><span data-stu-id="90398-804">Delete all Web conferencing data associated with a single user that is older than a certain date.</span></span>

4. <span data-ttu-id="90398-805">Mueva todos los datos de conferencia web asociados a un único usuario cuando se mueva de un grupo a otro.</span><span class="sxs-lookup"><span data-stu-id="90398-805">Move all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span>

    > [!NOTE]
    > <span data-ttu-id="90398-806">Las herramientas del kit de recursos para Lync Server 2010 admiten el movimiento de todos los datos de conferencia web asociados con un único usuario cuando ese usuario se mueve de un grupo a otro.</span><span class="sxs-lookup"><span data-stu-id="90398-806">The Resource Kit Tools for Lync Server 2010 supported moving all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span> <span data-ttu-id="90398-807">Esa funcionalidad ahora está en desuso de esta herramienta en favor del parámetro **MoveConferenceData.**</span><span class="sxs-lookup"><span data-stu-id="90398-807">That functionality is now deprecated from this tool in favor of the **MoveConferenceData** parameter.</span></span> <span data-ttu-id="90398-808">Para obtener más información acerca de este parámetro, consulte el cmdlet [Move-CsUser.](/powershell/module/skype/move-csuser?)</span><span class="sxs-lookup"><span data-stu-id="90398-808">For details about this parameter, see the [Move-CsUser](/powershell/module/skype/move-csuser?) cmdlet.</span></span>

<span data-ttu-id="90398-809">La herramienta elimina los datos de reunión solo para las reuniones que están inactivas.</span><span class="sxs-lookup"><span data-stu-id="90398-809">The tool deletes meeting data only for meetings that are inactive.</span></span> <span data-ttu-id="90398-810">Las reuniones activas (o reuniones en sesiones) no se pueden eliminar.</span><span class="sxs-lookup"><span data-stu-id="90398-810">Active meetings (or meetings in sessions) cannot be deleted.</span></span>

<span data-ttu-id="90398-811">Esta herramienta debe ejecutarse desde un equipo que se encuentra en el mismo grupo que el usuario de destino.</span><span class="sxs-lookup"><span data-stu-id="90398-811">This tool must be run from a computer that is in the same pool as the target user.</span></span> <span data-ttu-id="90398-812">El usuario cuyos datos de contenido de reunión se administran mediante esta herramienta deben estar en el mismo grupo de usuarios.</span><span class="sxs-lookup"><span data-stu-id="90398-812">The user whose meeting content data is being managed by this tool must be homed in the same user pool.</span></span>

### <a name="output"></a><span data-ttu-id="90398-813">Salida</span><span class="sxs-lookup"><span data-stu-id="90398-813">Output</span></span>

<span data-ttu-id="90398-814">Esta herramienta genera los resultados de cada una de las operaciones:</span><span class="sxs-lookup"><span data-stu-id="90398-814">This tool outputs the results of each of the operations:</span></span>

- <span data-ttu-id="90398-815">Si se realiza una consulta, la herramienta genera la lista de todas las carpetas de datos de reunión inactivas que tienen al usuario como organizador.</span><span class="sxs-lookup"><span data-stu-id="90398-815">If a query is performed, the tool outputs the list of all inactive meeting data folders that have that user as an organizer.</span></span>

- <span data-ttu-id="90398-816">Si se realiza una eliminación, la herramienta genera la lista de todas las carpetas de datos de reunión cuyos datos se eliminarán.</span><span class="sxs-lookup"><span data-stu-id="90398-816">If a delete is performed, the tool outputs the list of all meeting data folders whose data will be deleted.</span></span>

### <a name="requirements"></a><span data-ttu-id="90398-817">Requirements</span><span class="sxs-lookup"><span data-stu-id="90398-817">Requirements</span></span>

<span data-ttu-id="90398-818">La herramienta debe ejecutarse en el mismo grupo en el que el organizador se encuentra actualmente.</span><span class="sxs-lookup"><span data-stu-id="90398-818">The tool needs to be run in the same pool where the organizer is currently homed.</span></span>

<span data-ttu-id="90398-819">La herramienta debe ejecutarse con privilegios de administrador con acceso al Almacén de archivos de contenido.</span><span class="sxs-lookup"><span data-stu-id="90398-819">The tool must be run using administrator privileges with access to the Content File Store.</span></span>

### <a name="examples"></a><span data-ttu-id="90398-820">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="90398-820">Examples</span></span>

<span data-ttu-id="90398-821">En la tabla siguiente se describen los parámetros, algunos de los cuales se usan en los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="90398-821">The following table describes the parameters, some of which are used in the examples.</span></span>

![Parámetros de la Herramienta de datos de Web Conf.](../media/Reskit_2012_Tools_Documentation_Image51.JPG)

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""
```

<span data-ttu-id="90398-823">En el ejemplo anterior se muestra cómo funcionaría un comando de consulta.</span><span class="sxs-lookup"><span data-stu-id="90398-823">The preceding example shows how a query command would work.</span></span> <span data-ttu-id="90398-824">El resultado de dicho comando sería una lista de todas las carpetas de contenido de reunión que se verían afectadas por esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="90398-824">The output of such a command would be a list of all meeting content folders that would be affected by this tool.</span></span>

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:delete
```

<span data-ttu-id="90398-825">El anterior es un ejemplo de un comando delete.</span><span class="sxs-lookup"><span data-stu-id="90398-825">The preceding is an example of a delete command.</span></span> <span data-ttu-id="90398-826">El comando delete quitará todas las carpetas de reuniones inactivas de este usuario.</span><span class="sxs-lookup"><span data-stu-id="90398-826">The delete command will remove all inactive meeting folders from this user.</span></span>

### <a name="summary"></a><span data-ttu-id="90398-827">Resumen</span><span class="sxs-lookup"><span data-stu-id="90398-827">Summary</span></span>

<span data-ttu-id="90398-828">Esta herramienta puede ser un recurso valioso para los administradores que necesitan un control más preciso sobre los datos de reuniones de conferencia.</span><span class="sxs-lookup"><span data-stu-id="90398-828">This tool can be a valuable resource to administrators who need more precise control over conference meeting data.</span></span>
