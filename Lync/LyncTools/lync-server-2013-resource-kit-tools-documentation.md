---
title: Documentación de las herramientas del kit de recursos de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server 2013 Resource Kit Tools Documentation
ms:assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945604(v=OCS.15)
ms:contentKeyID: 51541429
ms.date: 02/02/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1589285948bd9d3f82fae0ed7c7916029716514f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850757"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-resource-kit-tools-documentation"></a><span data-ttu-id="3a400-102">Documentación de las herramientas del kit de recursos de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3a400-102">Lync Server 2013 Resource Kit Tools Documentation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a400-103">_**Última modificación del tema:** 2014-01-09_</span><span class="sxs-lookup"><span data-stu-id="3a400-103">_**Topic Last Modified:** 2014-01-09_</span></span>

<span data-ttu-id="3a400-104">En este tema se describen las herramientas que forman parte del kit de recursos de Lync Server 2013, incluido el propósito de cada herramienta y ejemplos de su uso. Lync Server 2013, las herramientas del kit de recursos ayudan a simplificar las tareas rutinarias para los administradores de ti que implementan y administran Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3a400-104">This topic describes the tools that are part of the Lync Server 2013 Resource Kit, including the purpose of each tool, and examples of its use.The Lync Server 2013, Resource Kit Tools help to make routine tasks easier for IT administrators who deploy and manage Lync Server 2013.</span></span> <span data-ttu-id="3a400-105">Por ejemplo, la herramienta **Web Conf Data** se puede usar para controlar fácilmente los datos que suben los usuarios durante una reunión de Internet.</span><span class="sxs-lookup"><span data-stu-id="3a400-105">For example, the **Web Conf Data** tool can be used to easily control data that is uploaded by users during an online meeting.</span></span> <span data-ttu-id="3a400-106">La herramienta **SEFAUtil** se puede usar para delegar el desvío de llamadas y respuesta para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="3a400-106">The **SEFAUtil** tool can be used to set up delegate call forwarding and answering for users.</span></span> <span data-ttu-id="3a400-107">Recomendamos a los administradores de ti que usen estas herramientas para administrar de forma más eficaz Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3a400-107">We encourage IT administrators to use these tools to more effectively manage Lync Server 2013.</span></span>

<div>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="3a400-108">Instalación de las herramientas del kit de recursos</span><span class="sxs-lookup"><span data-stu-id="3a400-108">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="3a400-109">Para instalar Lync Server 2013, herramientas del kit de recursos, descargue **OCSReskit. msi**.</span><span class="sxs-lookup"><span data-stu-id="3a400-109">To install the Lync Server 2013, Resource Kit Tools, download **OCSReskit.msi**.</span></span> <span data-ttu-id="3a400-110">Puede descargar el instalador de herramientas del kit de recursos en el centro [http://go.microsoft.com/fwlink/p/?LinkID=330429](http://go.microsoft.com/fwlink/p/?linkid=330429)de descarga en.</span><span class="sxs-lookup"><span data-stu-id="3a400-110">You can download the Resource Kit Tools installer from the Download Center at [http://go.microsoft.com/fwlink/p/?LinkID=330429](http://go.microsoft.com/fwlink/p/?linkid=330429).</span></span>

<span data-ttu-id="3a400-111">Ejecute **OCSResKit.msi** para hacer una instalación sencilla.</span><span class="sxs-lookup"><span data-stu-id="3a400-111">Run **OCSResKit.msi** to do a simple installation.</span></span> <span data-ttu-id="3a400-112">El. msi instala todas las herramientas en la siguiente ruta de acceso: **% archivos de\\programa% Microsoft Lync\\Server 2013 reskit**.</span><span class="sxs-lookup"><span data-stu-id="3a400-112">The .msi installs all the tools in the following path: **%Program Files%\\Microsoft Lync Server 2013\\ResKit**.</span></span> <span data-ttu-id="3a400-113">Las herramientas que son ejecutables independientes se encuentran en esta carpeta.</span><span class="sxs-lookup"><span data-stu-id="3a400-113">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="3a400-114">Las herramientas que también tienen archivos están en sus propias subcarpetas.</span><span class="sxs-lookup"><span data-stu-id="3a400-114">Tools that also have files are in their own subfolders.</span></span>

</div>

<div>

## <a name="supported-environments"></a><span data-ttu-id="3a400-115">Entornos compatibles</span><span class="sxs-lookup"><span data-stu-id="3a400-115">Supported Environments</span></span>

<span data-ttu-id="3a400-116">Para obtener un rendimiento óptimo, Lync Server 2013, las herramientas del kit de recursos deben instalarse en el mismo entorno y con las mismas especificaciones necesarias para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3a400-116">For optimal performance, the Lync Server 2013, Resource Kit Tools should be installed in the same environment and with the same specifications that are required for Lync Server 2013.</span></span>

</div>

<div>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="3a400-117">Información general sobre las herramientas del kit de recursos</span><span class="sxs-lookup"><span data-stu-id="3a400-117">Resource Kit Tools Overview</span></span>

<span data-ttu-id="3a400-118">En la siguiente lista se describen las herramientas que se proporcionan en el kit de recursos de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3a400-118">The following list describes the tools that are provided in the Lync Server 2013 Resource Kit.</span></span> <span data-ttu-id="3a400-119">En la siguiente sección se describe una descripción de cada herramienta, incluidos los requisitos y el uso de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="3a400-119">A description of each tool, including the requirements and example usage is covered in the following section.</span></span>

  - <span data-ttu-id="3a400-120">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="3a400-120">ABSConfig</span></span>

  - <span data-ttu-id="3a400-121">Bandwidth Policy Service Monitor (Monitor del servicio de directiva de ancho de banda)</span><span class="sxs-lookup"><span data-stu-id="3a400-121">Bandwidth Policy Service Monitor</span></span>

  - <span data-ttu-id="3a400-122">Bandwidth Utilization Analyzer (Analizador de uso de ancho de banda)</span><span class="sxs-lookup"><span data-stu-id="3a400-122">Bandwidth Utilization Analyzer</span></span>

  - <span data-ttu-id="3a400-123">Call Parkometer (Estacionamiento de llamadas)</span><span class="sxs-lookup"><span data-stu-id="3a400-123">Call Parkometer</span></span>

  - <span data-ttu-id="3a400-124">CleanupStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="3a400-124">CleanupStorageServiceData</span></span>

  - <span data-ttu-id="3a400-125">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="3a400-125">DBAnalyze</span></span>

  - <span data-ttu-id="3a400-126">ImportStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="3a400-126">ImportStorageServiceData</span></span>

  - <span data-ttu-id="3a400-127">LCSSync</span><span class="sxs-lookup"><span data-stu-id="3a400-127">LCSSync</span></span>

  - <span data-ttu-id="3a400-128">LookupUserConsole</span><span class="sxs-lookup"><span data-stu-id="3a400-128">LookupUserConsole</span></span>

  - <span data-ttu-id="3a400-129">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="3a400-129">MsTurnPing</span></span>

  - <span data-ttu-id="3a400-130">Network Configuration Viewer (Visor de configuración de red)</span><span class="sxs-lookup"><span data-stu-id="3a400-130">Network Configuration Viewer</span></span>

  - <span data-ttu-id="3a400-131">Response Group Agent Live (Información en vivo del agente del grupo de respuesta)</span><span class="sxs-lookup"><span data-stu-id="3a400-131">Response Group Agent Live</span></span>

  - <span data-ttu-id="3a400-132">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="3a400-132">SEFAUtil</span></span>

  - <span data-ttu-id="3a400-133">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="3a400-133">SYSPrep.ps1</span></span>

  - <span data-ttu-id="3a400-134">Unassigned Number Announcements Migration (Migración de anuncios de números sin asignar)</span><span class="sxs-lookup"><span data-stu-id="3a400-134">Unassigned Number Announcements Migration</span></span>

  - <span data-ttu-id="3a400-135">Web Conf Data</span><span class="sxs-lookup"><span data-stu-id="3a400-135">Web Conf Data</span></span>

</div>

<div>

## <a name="absconfig"></a><span data-ttu-id="3a400-136">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="3a400-136">ABSConfig</span></span>

<span data-ttu-id="3a400-137">La herramienta de configuración del servicio de libreta de direcciones (ABSConfig) es una herramienta administrativa que ayuda a los administradores a personalizar la configuración del servicio de libreta de direcciones en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3a400-137">The Address Book Service Configuration tool (ABSConfig) is an administrative tool that helps administrators customize Address Book Service configuration in Lync Server 2013.</span></span> <span data-ttu-id="3a400-138">Esta herramienta también permite a los administradores de Lync Server 2013 restaurar la configuración predeterminada del servicio de libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="3a400-138">This tool also enables Lync Server 2013 administrators to restore the default Address Book Service settings.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="3a400-139">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a400-139">Description</span></span>

<span data-ttu-id="3a400-140">ABSConfig es una aplicación de interfaz gráfica de usuario que permite a los administradores configurar atributos de servicios de dominio de Active Directory relacionados con el servicio de libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="3a400-140">ABSConfig is a graphical user interface application that enables administrators to configure Active Directory Domain Services attributes that are related to Address Book Service.</span></span>

<span data-ttu-id="3a400-141">Los escenarios principales para la herramienta son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="3a400-141">The primary scenarios for the tool are the following:</span></span>

  - <span data-ttu-id="3a400-142">Para permitir a los administradores asignar atributos de los servicios de dominio de Active Directory a los atributos de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3a400-142">To enable administrators to map attributes in Active Directory Domain Services to the attributes for Lync Server 2013.</span></span>

  - <span data-ttu-id="3a400-143">Permitir a los administradores especificar el atributo de Active Directory Domain Services que se incluirá o excluirá en los archivos del Servicio de libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="3a400-143">To enable administrators to specify the Active Directory Domain Services attribute to be included or excluded in the Address Book Service files.</span></span>

  - <span data-ttu-id="3a400-144">Permitir a los administradores restaurar la configuración predeterminada del Servicio de libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="3a400-144">To enable administrators to restore default Address Book Service settings.</span></span>

<span data-ttu-id="3a400-145">La herramienta ABSConfig se puede iniciar mediante el archivo absConfig. exe.</span><span class="sxs-lookup"><span data-stu-id="3a400-145">The ABSConfig tool can be started by using the absConfig.exe file.</span></span> <span data-ttu-id="3a400-146">La herramienta se abre en la ficha **configurar atributos** . Esta tabla tiene opciones para asignar atributos de servicios de dominio de Active Directory a los campos de atributo de Lync Server 2013 y para especificar qué usuarios desea incluir o excluir en archivos del servicio de libreta de direcciones basándose en filtros de atributos específicos.</span><span class="sxs-lookup"><span data-stu-id="3a400-146">The tool opens to the **Configure Attributes** tab. This table has options to map Active Directory Domain Services attributes to the attribute fields for Lync Server 2013 and to specify which users to include or exclude in Address Book Service files based on specific attribute filters.</span></span> <span data-ttu-id="3a400-147">También tiene opciones para personalizar el valor del número de teléfono que se incluirá en el archivo de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="3a400-147">It also has options to customize which value of the phone number to be included in the Address Book file.</span></span> <span data-ttu-id="3a400-148">La opción **Restaurar valores predeterminados** permite a los administradores restaurar la configuración del Servicio de libreta de direcciones a los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="3a400-148">The **Restore Defaults** option enables administrators to restore Address Book Service settings to default values.</span></span>

</div>

<div>

## <a name="changes-from-lync-server-2010"></a><span data-ttu-id="3a400-149">Cambios de Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="3a400-149">Changes from Lync Server 2010</span></span>

<span data-ttu-id="3a400-150">En la herramienta de configuración ABS de Lync Server 2013, se pueden quitar los atributos (filas) desmarcando la casilla "habilitar" del atributo.</span><span class="sxs-lookup"><span data-stu-id="3a400-150">In Lync Server 2013 ABS Configuration tool, attributes (rows) may be removed by unchecking the “enable” checkbox for the attribute.</span></span> <span data-ttu-id="3a400-151">Esto tiene el mismo efecto que eliminar la fila de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3a400-151">This has the same effect as deleting the row in Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3a400-152">La casilla habilitar se encuentra en la columna del extremo derecho; es posible que tenga que desplazarse hacia la derecha para ver la columna</span><span class="sxs-lookup"><span data-stu-id="3a400-152">The enable checkbox is in the far right column; you may need to scroll right to see the column</span></span>



</div>

</div>

<div>

## <a name="output"></a><span data-ttu-id="3a400-153">Salida</span><span class="sxs-lookup"><span data-stu-id="3a400-153">Output</span></span>

<span data-ttu-id="3a400-154">ABSConfig guarda la configuración del Servicio de libreta de direcciones en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="3a400-154">ABSConfig stores the Address Book Service configuration in the database.</span></span>

    Path: %ProgramFiles%\Microsoft Lync Server 2013\Reskit

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="3a400-155">Finalidad</span><span class="sxs-lookup"><span data-stu-id="3a400-155">Purpose</span></span>

<span data-ttu-id="3a400-156">ABSConfig ofrece una manera rápida y sencilla de personalizar el servicio de libreta de direcciones de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3a400-156">ABSConfig provides a quick and easy way to customize Lync Server 2013 Address Book Service.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="3a400-157">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3a400-157">Requirements</span></span>

<div>

## <a name="computer"></a><span data-ttu-id="3a400-158">Equipo</span><span class="sxs-lookup"><span data-stu-id="3a400-158">Computer</span></span>

<span data-ttu-id="3a400-159">ABSConfig solo puede ejecutarse desde un equipo unido a un dominio que tenga instalado Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3a400-159">ABSConfig can be run only from a domain-joined computer that has Lync Server 2013 installed.</span></span> <span data-ttu-id="3a400-160">En el caso de Lync Server 2013, Enterprise Edition, esta herramienta se puede ejecutar en cualquier servidor front-end que tenga habilitado el servicio de libreta de direcciones durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="3a400-160">In the case of Lync Server 2013, Enterprise Edition, this tool can be run on any Front End servers that have the Address Book Service enabled during setup.</span></span>

</div>

<div>

## <a name="network"></a><span data-ttu-id="3a400-161">Red</span><span class="sxs-lookup"><span data-stu-id="3a400-161">Network</span></span>

<span data-ttu-id="3a400-162">El equipo debe ser capaz de conectarse al grupo de servidores front-end y a la base de datos back-end.</span><span class="sxs-lookup"><span data-stu-id="3a400-162">The computer should be able to connect to the Front End pool and back-end database.</span></span>

</div>

<div>

## <a name="software"></a><span data-ttu-id="3a400-163">Software</span><span class="sxs-lookup"><span data-stu-id="3a400-163">Software</span></span>

<span data-ttu-id="3a400-164">Antes de ejecutar la herramienta ABSConfig es necesario instalar los siguientes componentes de software:</span><span class="sxs-lookup"><span data-stu-id="3a400-164">The following software components must be installed before running the ABSConfig tool:</span></span>

  - <span data-ttu-id="3a400-165">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3a400-165">Microsoft Lync Server 2013</span></span>

</div>

<div>

## <a name="users"></a><span data-ttu-id="3a400-166">Usuarios</span><span class="sxs-lookup"><span data-stu-id="3a400-166">Users</span></span>

<span data-ttu-id="3a400-167">Administradores que tienen los permisos necesarios para actualizar la implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3a400-167">Administrators who have the permissions required to update the Lync Server 2013 deployment.</span></span>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="3a400-168">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="3a400-168">Examples</span></span>

<span data-ttu-id="3a400-p109">Para iniciar ABSConfig, escriba **ABSConfig.exe** en un símbolo del sistema. A continuación se muestra la interfaz de usuario de la herramienta ABSConfig.</span><span class="sxs-lookup"><span data-stu-id="3a400-p109">ABSConfig can be started by typing **ABSConfig.exe** at a command prompt. Shown below is the ABSConfig tool user interface.</span></span>

<span data-ttu-id="3a400-171">![La herramienta ABSConfig. exe.] (images/JJ945604.6fb63a70-7b63-4b8b-b7d1-82fe9aa2028f(OCS.15).jpg "La herramienta ABSConfig. exe.")</span><span class="sxs-lookup"><span data-stu-id="3a400-171">![The ABSConfig.exe tool.](images/JJ945604.6fb63a70-7b63-4b8b-b7d1-82fe9aa2028f(OCS.15).jpg "The ABSConfig.exe tool.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="3a400-172">Resumen</span><span class="sxs-lookup"><span data-stu-id="3a400-172">Summary</span></span>

<span data-ttu-id="3a400-173">La herramienta ABSConfig proporciona a los administradores una herramienta rápida y fácil de usar para personalizar el servicio de libreta de direcciones de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3a400-173">The ABSConfig tool provides administrators a quick and easy to use tool to customize Lync Server 2013 Address Book Service.</span></span>

</div>

</div>

<div>

## <a name="bandwidth-policy-service-monitor"></a><span data-ttu-id="3a400-174">Bandwidth Policy Service Monitor (Monitor del servicio de directiva de ancho de banda)</span><span class="sxs-lookup"><span data-stu-id="3a400-174">Bandwidth Policy Service Monitor</span></span>

<span data-ttu-id="3a400-175">La herramienta Bandwidth Policy Service Monitor permite a los administradores ver una lista de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3a400-175">The Bandwidth Policy Service Monitor tool is intended to allow administrators to view a list of the following:</span></span>

1.  <span data-ttu-id="3a400-176">Todos los servicios de directiva de ancho de banda de Lync Server 2013 (autenticación y núcleo) configurados en la topología</span><span class="sxs-lookup"><span data-stu-id="3a400-176">All the configured Lync Server 2013 Bandwidth Policy services (Authentication and Core) in the topology</span></span>

2.  <span data-ttu-id="3a400-177">Las conexiones que realiza cada servicio con otros servicios de directivas de ancho de banda y a los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="3a400-177">The connections that each service makes to other Bandwidth Policy services and to the Edge servers</span></span>

3.  <span data-ttu-id="3a400-178">Todos los vínculos configurados en el documento de configuración de red y el uso de ancho de banda en tiempo real informado por los servicios de directiva de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="3a400-178">All the links that are configured in the Network configuration document and real-time bandwidth usage as reported by each of the Bandwidth Policy services</span></span>

<div>

## <a name="description"></a><span data-ttu-id="3a400-179">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a400-179">Description</span></span>

<span data-ttu-id="3a400-p110">La herramienta Bandwidth Policy Service Monitor se implementa como una aplicación basada en GUI. Los administradores pueden ejecutar la herramienta mediante PDPMonUI.exe.</span><span class="sxs-lookup"><span data-stu-id="3a400-p110">The Bandwidth Policy Service Monitor tool is implemented as a GUI-based application. Administrators start the tool by running PDPMonUI.exe.</span></span>

<span data-ttu-id="3a400-p111">Al iniciar la aplicación, esta intenta detectar la lista de servicios de directiva de ancho de banda en la topología. Después de completar la actualización inicial, en el panel de la izquierda de la ventana se muestra una lista de servicios agrupados por los clústeres a los que pertenecen.</span><span class="sxs-lookup"><span data-stu-id="3a400-p111">When the tool starts, it attempts to discover the list of Bandwidth Policy services in the topology. After the initial update is done, the pane to the left of the window is populated with a list of services that are grouped by the clusters that they belong to.</span></span>

<span data-ttu-id="3a400-p112">Cuando los administradores seleccionan un servicio de directiva de ancho de banda concreto, en el panel de la derecha se muestra información sobre dicho servicio. Además, el panel también contiene dos pestañas principales con información.</span><span class="sxs-lookup"><span data-stu-id="3a400-p112">When administrators select a particular Bandwidth Policy Service, the pane on the right displays the information about that particular service. That pane also has two main tabs that display information.</span></span>

<div>

## <a name="machine-info-tab"></a><span data-ttu-id="3a400-186">Pestaña Información de equipo</span><span class="sxs-lookup"><span data-stu-id="3a400-186">Machine Info Tab</span></span>

<span data-ttu-id="3a400-187">La pestaña **Información de equipo** contiene información detallada sobre el servicio de directiva de ancho de banda seleccionado, además de la lista y el estado de todas las conexiones realizadas por dicho servicio de directiva de ancho de banda seleccionado con otros servicios.</span><span class="sxs-lookup"><span data-stu-id="3a400-187">The **Machine Info** tab shows the details of the Bandwidth Policy Service that is selected and the list and state of all the connections that are made by the selected Bandwidth Policy Service to other services.</span></span>

</div>

<div>

## <a name="topology-info-tab"></a><span data-ttu-id="3a400-188">Pestaña Información de topología</span><span class="sxs-lookup"><span data-stu-id="3a400-188">Topology Info Tab</span></span>

<span data-ttu-id="3a400-p113">En la pestaña **Información de topología** se muestra una lista de todos los vínculos configurados en las opciones de red. Para cada vínculo se muestra la capacidad de ancho de banda de audio y de vídeo. Además, también se muestra el ancho de banda utilizado actualmente, tanto en kbps como en porcentaje de capacidad. La herramienta utiliza códigos de color para resaltar vínculos cuyo uso está próximo al límite de capacidad, lo que permite a los administradores aislarlos rápidamente.</span><span class="sxs-lookup"><span data-stu-id="3a400-p113">The **Topology Info** tab shows a list of all the links that are configured in the Network configuration settings. For each link, the audio and video bandwidth capacity is displayed. Additionally, the currently utilized bandwidth is displayed, both in Kbps and as a percentage of the capacity. The tool uses color-coding to highlight links that have utilization that is close to the capacity—this allows administrators to quickly isolate such links.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3a400-p114"> Si la herramienta Bandwidth Policy Service Monitor genera errores al conectarse a alguno de los servicios de directiva de ancho de banda, no se rellenará la información en las pestañas <STRONG>Información de equipo</STRONG> e <STRONG>Información de topología</STRONG>. Sin embargo, es posible que la herramienta pueda conectarse de forma inicial, pero que posteriormente pierda la conexión al servicio. En estos casos, los administradores podrían ver información desactualizada. En las pestañas hay una marca de tiempo <STRONG>Última actualización</STRONG> que permite a los administradores ver cuándo se actualizó por última vez un servicio de directiva de ancho de banda concreto.</span><span class="sxs-lookup"><span data-stu-id="3a400-p114">If the Bandwidth Policy Service Monitor tool experiences failure when it connects to any of the configured Bandwidth Policy services, the information in the <STRONG>Machine Info</STRONG> and the <STRONG>Topology Info</STRONG> tabs won’t be populated. However, it is possible that the tool might connect initially but subsequently lose its connection to the service. In such cases, administrators might see outdated information. There is a <STRONG>Last Updated</STRONG> time stamp on each of the tabs that can allow administrators to see when the data was last updated for a particular Bandwidth Policy Service.</span></span>



</div>

</div>

</div>

<div>

## <a name="output"></a><span data-ttu-id="3a400-197">Salida</span><span class="sxs-lookup"><span data-stu-id="3a400-197">Output</span></span>

<span data-ttu-id="3a400-198">No hay salida de línea de comandos; la salida del programa está contenida en la interfaz gráfica de usuario (GUI) principal.</span><span class="sxs-lookup"><span data-stu-id="3a400-198">There is no command-line output; the program output is contained within the main graphical user interface (GUI).</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="3a400-199">Finalidad</span><span class="sxs-lookup"><span data-stu-id="3a400-199">Purpose</span></span>

<span data-ttu-id="3a400-p115">El objetivo de la herramienta Bandwidth Policy Service Monitor es permitir a los administradores ver el estado de los servicios de directiva de ancho de banda definidos en la topología. Además, los administradores pueden ver el uso de ancho de banda en tiempo real de todos los vínculos definidos en el documento de configuración de red.</span><span class="sxs-lookup"><span data-stu-id="3a400-p115">The purpose of the Bandwidth Policy Service Monitor tool is to allow administrators visibility into the state of each of the Bandwidth Policy services that are defined in the topology. In addition, administrators can see real-time bandwidth usage for all the links that are defined in the Network configuration document.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="3a400-202">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3a400-202">Requirements</span></span>

<span data-ttu-id="3a400-203">La herramienta Monitor de servicio de directivas de ancho de banda debe ejecutarse en un equipo que forme parte de la topología de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3a400-203">The Bandwidth Policy Service Monitor tool needs to be run on a computer that is part of the Lync Server topology.</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="3a400-204">Resumen</span><span class="sxs-lookup"><span data-stu-id="3a400-204">Summary</span></span>

<span data-ttu-id="3a400-205">La herramienta Bandwidth Policy Service Monitor puede ser un recurso útil para los administradores, ya que permite inspeccionar el estado de todos los servicios de directiva de ancho de banda en la topología y, lo que es aún más importante, les permite conocer el uso de ancho de banda en tiempo real de los vínculos definidos en las opciones de configuración de red.</span><span class="sxs-lookup"><span data-stu-id="3a400-205">The Bandwidth Policy Service Monitor tool can be a valuable resource to administrators so they can inspect the state of all the Bandwidth Policy services in the topology—and more importantly—they can obtain real-time bandwidth utilization for the links that are defined in the Network configuration settings.</span></span>

</div>

</div>

<div>

## <a name="bandwidth-utilization-analyzer"></a><span data-ttu-id="3a400-206">Bandwidth Utilization Analyzer (Analizador de uso de ancho de banda)</span><span class="sxs-lookup"><span data-stu-id="3a400-206">Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="3a400-p116">Bandwidth Utilization Analyzer es una herramienta que genera informes sobre diferentes vistas de consumo de ancho de banda por los puntos de conexión de comunicaciones unificadas en vínculos WAN de la red empresarial. Estos informes pueden utilizarse para conocer el patrón de consumo de ancho de banda y ayudar a planificar la capacidad de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="3a400-p116">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network. These reports can be used to understand the current bandwidth consumption pattern and to aid in bandwidth capacity planning.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="3a400-209">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a400-209">Description</span></span>

<span data-ttu-id="3a400-p117">El analizador de uso de ancho de banda se implementa como una aplicación basada en GUI. Esta herramienta genera informes específicos para el uso de audio en la red y ayuda a planificar la capacidad. Además, también itera en la capacidad de ancho de banda asignada a diferentes vínculos.</span><span class="sxs-lookup"><span data-stu-id="3a400-p117">Bandwidth Utilization Analyzer is implemented as a GUI-based application. This tool generates reports specifically for audio utilization across the network and helps with capacity planning. It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="3a400-213">Salida</span><span class="sxs-lookup"><span data-stu-id="3a400-213">Output</span></span>

<span data-ttu-id="3a400-214">El analizador de uso de ancho de banda proporciona representaciones gráficas de la capacidad de ancho de banda y el consumo de audio para todos los vínculos WAN configurados en el sistema.</span><span class="sxs-lookup"><span data-stu-id="3a400-214">Bandwidth Utilization Analyzer provides graphic al plots of bandwidth capacity and utilization for audio for all the WAN links that are configured in the system.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="3a400-215">Finalidad</span><span class="sxs-lookup"><span data-stu-id="3a400-215">Purpose</span></span>

<span data-ttu-id="3a400-p118">En cualquier implementación de voz y vídeo es muy importante supervisar y comprender la tendencia de uso de ancho de banda del tráfico multimedia en la red empresarial. La herramienta Bandwidth Utilization Analyzer permite a los administradores conseguir justo eso. Esta herramienta hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3a400-p118">In any voice and video deployment, it’s critical to monitor and understand the trend of bandwidth utilization of media traffic across the enterprise network. The Bandwidth Utilization Analyzer tool allows an administrator to achieve just that. This tool does the following:</span></span>

  - <span data-ttu-id="3a400-219">Genera informes específicos para el uso de audio en la red</span><span class="sxs-lookup"><span data-stu-id="3a400-219">Generates specific reports for audio utilization across the network</span></span>

  - <span data-ttu-id="3a400-220">Mejora la eficacia de planificación de capacidad y la iteración en la capacidad de ancho de banda asignada a diferentes vínculos</span><span class="sxs-lookup"><span data-stu-id="3a400-220">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="3a400-221">El analizador de uso de ancho de banda puede generar las siguientes representaciones gráficas de capacidad de ancho de banda e informes de uso:</span><span class="sxs-lookup"><span data-stu-id="3a400-221">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and utilization reports; they are as follows:</span></span>

  - <span data-ttu-id="3a400-222">Todos los vínculos WAN en la red empresarial</span><span class="sxs-lookup"><span data-stu-id="3a400-222">All the WAN links in the enterprise network</span></span>

  - <span data-ttu-id="3a400-223">Filtrados por los vínculos WAN seleccionados</span><span class="sxs-lookup"><span data-stu-id="3a400-223">Filtered by selected WAN links that have been chosen</span></span>

  - <span data-ttu-id="3a400-224">Filtrados por los vínculos WAN que han superado la capacidad de vínculos</span><span class="sxs-lookup"><span data-stu-id="3a400-224">Filtered by WAN links that have exceeded link capacity</span></span>

  - <span data-ttu-id="3a400-225">Filtrados por los vínculos WAN que no han utilizado toda la capacidad de ancho de banda proporcionada</span><span class="sxs-lookup"><span data-stu-id="3a400-225">Filtered by WAN links that have been under-utilizing the provisioned bandwidth</span></span>

  - <span data-ttu-id="3a400-226">Filtrados por los vínculos WAN que han alcanzado niveles críticos (un uso de ancho de banda superior al 90 % de capacidad de ancho de banda del vínculo WAN)</span><span class="sxs-lookup"><span data-stu-id="3a400-226">Filter by WAN links that have been reaching critical levels (a bandwidth utilization that is greater than 90% of bandwidth capacity of the WAN link)</span></span>

  - <span data-ttu-id="3a400-227">Filtrados por tipo de vínculo WAN: vínculos de sitios de red, vínculos interregionales y vínculos dentro de un sitio</span><span class="sxs-lookup"><span data-stu-id="3a400-227">Filtered by WAN link type—network-site links, interregional links, and links within a site</span></span>

  - <span data-ttu-id="3a400-228">Filtrados por región de red</span><span class="sxs-lookup"><span data-stu-id="3a400-228">Filtered by network region</span></span>

<div>

## <a name="applications"></a><span data-ttu-id="3a400-229">Aplicaciones</span><span class="sxs-lookup"><span data-stu-id="3a400-229">Applications</span></span>

<span data-ttu-id="3a400-230">El analizador de uso de ancho de banda incluye las siguientes dos aplicaciones (herramientas):</span><span class="sxs-lookup"><span data-stu-id="3a400-230">Bandwidth Utilization Analyzer has the following two applications (tools):</span></span>

  - <span data-ttu-id="3a400-231">**WanLinkLogCollector. exe**   esta herramienta permite al usuario introducir la información requerida.</span><span class="sxs-lookup"><span data-stu-id="3a400-231">**WanLinkLogCollector.exe**   This tool enables its user to input the required information.</span></span>

  - <span data-ttu-id="3a400-232">**BandwidthUtilizationAnalyzer. xlsm**  el informe de software de hoja de cálculo de Microsoft Excel se inicia automáticamente mediante WanLinkLogCollector. exe.</span><span class="sxs-lookup"><span data-stu-id="3a400-232">**BandwidthUtilizationAnalyzer.xlsm**  A Microsoft Excel spreadsheet software report is automatically launched by WanLinkLogCollector.exe.</span></span> <span data-ttu-id="3a400-233">Esta aplicación permite al usuario aplicar filtros al informe, como se muestra posteriormente en este artículo.</span><span class="sxs-lookup"><span data-stu-id="3a400-233">This application allows the user to apply filters to the report as shown later in this article.</span></span>

</div>

<div>

## <a name="phases-of-using-bandwidth-utilization-analyzer"></a><span data-ttu-id="3a400-234">Fases de uso de Bandwidth Utilization Analyzer</span><span class="sxs-lookup"><span data-stu-id="3a400-234">Phases of Using Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="3a400-235">Existen dos fases al usar el analizador de uso de ancho de banda:</span><span class="sxs-lookup"><span data-stu-id="3a400-235">There are two phases when using Bandwidth Utilization Analyzer:</span></span>

  - <span data-ttu-id="3a400-236">Recopilar registros, que se realiza automáticamente mediante WanLinkLogCollector.exe</span><span class="sxs-lookup"><span data-stu-id="3a400-236">Collect logs, which is performed by using WanLinkLogCollector.exe</span></span>

  - <span data-ttu-id="3a400-237">Personalizar informes, que se realiza mediante BandwidthUtilizationAnalyzer.xlsm</span><span class="sxs-lookup"><span data-stu-id="3a400-237">Customize reports, which is performed by using BandwidthUtilizationAnalyzer.xlsm</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3a400-238">No se recomienda que los usuarios finales inicien BandwidthUtilizationAnalyzer.xlsm de forma manual.</span><span class="sxs-lookup"><span data-stu-id="3a400-238">We strongly recommend that BandwidthUtilizationAnalyzer.xlsm not be manually launched by end users.</span></span>



</div>

</div>

<div>

## <a name="starting-bandwidth-utilization-analyzer"></a><span data-ttu-id="3a400-239">Inicio del analizador de uso de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="3a400-239">Starting Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="3a400-240">Inicie WanLinkLogCollector.exe en el símbolo del sistema o mediante el Explorador de Windows.</span><span class="sxs-lookup"><span data-stu-id="3a400-240">Start WanLinkLogCollector.exe at the command prompt or by using Windows Explorer.</span></span>

<span data-ttu-id="3a400-241">**Uso de WanLinkLogCollector.exe**</span><span class="sxs-lookup"><span data-stu-id="3a400-241">**Using WanLinkLogCollector.exe**</span></span>

<span data-ttu-id="3a400-242">Hay tres pasos para usar WanLinkLogCollector.exe:</span><span class="sxs-lookup"><span data-stu-id="3a400-242">There are three steps to using WanLinkLogCollector.exe:</span></span>

1.  <span data-ttu-id="3a400-243">**Registrar la escala de tiempo**   proporcionar la escala de tiempo en la que debe generarse el informe</span><span class="sxs-lookup"><span data-stu-id="3a400-243">**Log the timeline**   Provide the timeline that the report needs to be generated for</span></span>

2.  <span data-ttu-id="3a400-244">**Especificar los directorios**   de archivos proporcionar información de ubicación de archivos</span><span class="sxs-lookup"><span data-stu-id="3a400-244">**Specify the file directories**   Provide file location information</span></span>

3.  <span data-ttu-id="3a400-245">**Recopilar los registros e iniciar el visor**  de informes ejecute el comando para generar el informe</span><span class="sxs-lookup"><span data-stu-id="3a400-245">**Collect the logs and launch the report viewer**  Execute the command to generate the report</span></span>

<div>

## <a name="step-1---log-the-timeline"></a><span data-ttu-id="3a400-246">Paso 1: registrar la escala de tiempo</span><span class="sxs-lookup"><span data-stu-id="3a400-246">Step 1 - Log the timeline</span></span>

<span data-ttu-id="3a400-247">Al registrar la escala de tiempo, el usuario de la herramienta puede especificar lo siguiente como se muestra en la ilustración siguiente. </span><span class="sxs-lookup"><span data-stu-id="3a400-247">Logging the timeline allows the tool user to specify the following as shown in the figure below.</span></span>

1.  <span data-ttu-id="3a400-248">**Fecha de inicio** Es la fecha de inicio de la escala de tiempo para la que se genera el informe; por ejemplo, 1 de agosto de 2010.</span><span class="sxs-lookup"><span data-stu-id="3a400-248">**Start date** This is the start date of the timeline that the report is to be generated for; for example, August 1, 2010.</span></span>

2.  <span data-ttu-id="3a400-249">**Fecha de finalización** Es la fecha de finalización de la escala de tiempo para la que se genera el informe; por ejemplo, 30 de septiembre de 2010.</span><span class="sxs-lookup"><span data-stu-id="3a400-249">**End date** This is the end date of the timeline that the report is to be generated for; for example, September 30, 2010.</span></span>
    
    <span data-ttu-id="3a400-250">![Fechas de inicio y finalización en el uso de ancho de banda] (images/JJ945604.2c597cfc-3372-4d41-816b-26202f607ad8(OCS.15).jpg "Fechas de inicio y finalización en el uso de ancho de banda")</span><span class="sxs-lookup"><span data-stu-id="3a400-250">![Start and End dates in the Bandwidth Utilization A](images/JJ945604.2c597cfc-3372-4d41-816b-26202f607ad8(OCS.15).jpg "Start and End dates in the Bandwidth Utilization A")</span></span>  

</div>

<div>

## <a name="step-2---specify-the-file-directories"></a><span data-ttu-id="3a400-251">Paso 2: especificar los directorios de archivos</span><span class="sxs-lookup"><span data-stu-id="3a400-251">Step 2 - Specify the file directories</span></span>

<span data-ttu-id="3a400-252">El usuario puede especificar los directorios de archivos siguientes, como se muestra.</span><span class="sxs-lookup"><span data-stu-id="3a400-252">The following file directories can be specified by the user as shown.</span></span>

  - <span data-ttu-id="3a400-253">**Ubicación de los archivos de registro del servidor** La ubicación de la carpeta donde se almacenan los registros del servidor de directivas de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="3a400-253">**Server log files location** The folder location where Bandwidth policy server logs are stored.</span></span> <span data-ttu-id="3a400-254">Esto suele estar en \<el\>\\\<fileserver de\>\\la\\elección de fe AppServerFiles PDP.</span><span class="sxs-lookup"><span data-stu-id="3a400-254">This is typically in \<fileserver\>\\\<choice of FE\>\\AppServerFiles\\PDP.</span></span>

  - <span data-ttu-id="3a400-255">**Ubicación de almacenamiento temporal de archivos** Ubicación del archivo temporal donde se almacenan los archivos intermedios mientras se genera el informe.</span><span class="sxs-lookup"><span data-stu-id="3a400-255">**Temporary file storage location** The temporary file location where intermediate files are stored while the report is being generated.</span></span>

<span data-ttu-id="3a400-256">![Directorios de archivos en la anal de uso del ancho de banda] (images/JJ945604.d66daeac-1669-45e3-932d-3f6782840c2a(OCS.15).jpg "Directorios de archivos en la anal de uso del ancho de banda")</span><span class="sxs-lookup"><span data-stu-id="3a400-256">![File directories in the Bandwidth Utilization Anal](images/JJ945604.d66daeac-1669-45e3-932d-3f6782840c2a(OCS.15).jpg "File directories in the Bandwidth Utilization Anal")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3a400-257">Compruebe que el usuario de la herramienta posee acceso a los archivos de los registros del servidor y a la carpeta donde se almacenan los archivos temporales.</span><span class="sxs-lookup"><span data-stu-id="3a400-257">Ensure that sufficient file access to the server logs and the temporary file store folder is provided to the tool user.</span></span>



</div>

</div>

<div>

## <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a><span data-ttu-id="3a400-258">Paso 3: recopilar los registros e iniciar el visor de informes</span><span class="sxs-lookup"><span data-stu-id="3a400-258">Step 3 - Collect the logs and start the report viewer</span></span>

<span data-ttu-id="3a400-p121">Para recopilar los registros e iniciar el visor de informes, haga clic en **Ejecutar** como se indica a continuación. Este paso recopila todos los datos necesarios.</span><span class="sxs-lookup"><span data-stu-id="3a400-p121">To collect the logs and start the report viewer, click **Execute** as shown below. This step collects the required data.</span></span>

<span data-ttu-id="3a400-261">![Recopilar datos en el uso de ancho de Analy] (images/JJ945604.0019cb2c-7c01-4dc9-ac90-ac47c47d1bfd(OCS.15).jpg "Recopilar datos en el uso de ancho de Analy")</span><span class="sxs-lookup"><span data-stu-id="3a400-261">![Collecting data in the Bandwidth Utilization Analy](images/JJ945604.0019cb2c-7c01-4dc9-ac90-ac47c47d1bfd(OCS.15).jpg "Collecting data in the Bandwidth Utilization Analy")</span></span>

<span data-ttu-id="3a400-262">Cuando la validación de entrada es correcta, se muestra el mensaje que aparece a continuación.</span><span class="sxs-lookup"><span data-stu-id="3a400-262">When the input validation is successful, the message shown below is displayed.</span></span>

<span data-ttu-id="3a400-263">![Registra la notificación recopilada en el uso de ancho de banda] (images/JJ945604.eda91da8-3285-4eab-8ccb-c6d89c8cc221(OCS.15).jpg "Registra la notificación recopilada en el uso de ancho de banda")</span><span class="sxs-lookup"><span data-stu-id="3a400-263">![Logs collected notification in the Bandwidth Utili](images/JJ945604.eda91da8-3285-4eab-8ccb-c6d89c8cc221(OCS.15).jpg "Logs collected notification in the Bandwidth Utili")</span></span>

<span data-ttu-id="3a400-p122">Haga clic en **Aceptar**. BandwidthUtilizationAnalyzer.xlsm se iniciará automáticamente. Siga las instrucciones del cuadro de mensaje. Para obtener más información, consulte **Uso de BandwidthUtilizationAnalyzer.xlsm** en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="3a400-p122">Click **OK**. BandwidthUtilizationAnalyzer.xlsm is automatically started. Follow the instructions in the message box. For details, see **Using BandwidthUtilizationAnalyzer.xlsm** in the next section.</span></span>

</div>

<div>


<span data-ttu-id="3a400-268">**Uso de BandwidthUtilizationAnalyzer.xlsm**</span><span class="sxs-lookup"><span data-stu-id="3a400-268">**Using BandwidthUtilizationAnalyzer.xlsm**</span></span>

1.  <span data-ttu-id="3a400-269">Cuando BandwidthUtilizationAnalyzer.xlsm se inicie automáticamente, haga clic en **Actualizar** como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="3a400-269">When BandwidthUtilizationAnalyzer.xlsm is automatically started, click **Refresh** as shown below.</span></span>
    
    <span data-ttu-id="3a400-270">![BandwidthUtilizationAnalyzer. xlsm] (images/JJ945604.c4e675b9-1671-400e-a712-6db82d731b39(OCS.15).jpg "BandwidthUtilizationAnalyzer. xlsm")</span><span class="sxs-lookup"><span data-stu-id="3a400-270">![BandwidthUtilizationAnalyzer.xlsm](images/JJ945604.c4e675b9-1671-400e-a712-6db82d731b39(OCS.15).jpg "BandwidthUtilizationAnalyzer.xlsm")</span></span>

2.  <span data-ttu-id="3a400-271">Al abrir una carpeta de archivos, seleccione consolidated.csv de la ubicación especificada en el cuadro de mensaje, como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="3a400-271">When a file folder is opened, select consolidated.csv from the location that is specified in the message box as shown below.</span></span> <span data-ttu-id="3a400-272">También muestra la ubicación como **C:\\Temp**.</span><span class="sxs-lookup"><span data-stu-id="3a400-272">It also shows the location as **C:\\Temp**.</span></span>
    
    <span data-ttu-id="3a400-273">![Abrir una carpeta en BandwidthUtilizationAnalyzer.] (images/JJ945604.601cc572-cee9-45fb-9ed1-c4b96a2fa21e(OCS.15).jpg "Abrir una carpeta en BandwidthUtilizationAnalyzer.")</span><span class="sxs-lookup"><span data-stu-id="3a400-273">![Opening a folder in BandwidthUtilizationAnalyzer.](images/JJ945604.601cc572-cee9-45fb-9ed1-c4b96a2fa21e(OCS.15).jpg "Opening a folder in BandwidthUtilizationAnalyzer.")</span></span>

3.  <span data-ttu-id="3a400-274">Haga clic en **Importar**.</span><span class="sxs-lookup"><span data-stu-id="3a400-274">Click **Import**.</span></span>

4.  <span data-ttu-id="3a400-p124">Se generará automáticamente la representación gráfica. Está disponible cuando desaparece el puntero que indica un proceso en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="3a400-p124">The graphical plot is automatically generated. It is available when the working-in-the-background pointer disappears.</span></span>
    
    <span data-ttu-id="3a400-277">![Aplicar filtros en la vista informe.] (images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Aplicar filtros en la vista informe.")</span><span class="sxs-lookup"><span data-stu-id="3a400-277">![Applying filters in Report View.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Applying filters in Report View.")</span></span>

</div>

<div>

## <a name="applying-filters-to-the-report-view"></a><span data-ttu-id="3a400-278">Aplicar filtros a la vista de informes</span><span class="sxs-lookup"><span data-stu-id="3a400-278">Applying Filters to the Report View</span></span>

<span data-ttu-id="3a400-279">Los filtros que se pueden aplicar a la vista de informes son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="3a400-279">The filters that can be applied to the report view as shown below are described as follows:</span></span>

<span data-ttu-id="3a400-280">![Aplicar filtros en la vista informe.] (images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Aplicar filtros en la vista informe.")</span><span class="sxs-lookup"><span data-stu-id="3a400-280">![Applying filters in Report View.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Applying filters in Report View.")</span></span>

1.  <span data-ttu-id="3a400-281">**Nombre** Filtra por vínculos WAN (el filtro se encuentra en la parte derecha del gráfico). El prefijo indica los siguientes tipos de vínculos; consulte el cuadro vertical (azul):</span><span class="sxs-lookup"><span data-stu-id="3a400-281">**Name** Filter by WAN links (the filter is on the right side of the graph).The prefix denotes the following link types; see the vertical (blue) box:</span></span>
    
      - <span data-ttu-id="3a400-282">**Sitio S** El vínculo WAN de un sitio de red con una región de red</span><span class="sxs-lookup"><span data-stu-id="3a400-282">**S Site** The WAN link from a network site to a network region</span></span>
    
      - <span data-ttu-id="3a400-283">**ES entre sitios** El vínculo WAN entre dos sitios de red</span><span class="sxs-lookup"><span data-stu-id="3a400-283">**IS Inter-Site** The WAN link between two network sites</span></span>
    
      - <span data-ttu-id="3a400-284">**Interregional R** El vínculo WAN entre dos regiones de red</span><span class="sxs-lookup"><span data-stu-id="3a400-284">**R Inter-Region** The WAN link between two network region</span></span>

2.  <span data-ttu-id="3a400-285">**Límite superado** Filtra por vínculos WAN cuyo uso de ancho de banda supera la capacidad de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="3a400-285">**Exceeded limit** Filter by WAN links whose bandwidth utilization is more than the bandwidth capacity</span></span>

3.  <span data-ttu-id="3a400-286">**Niveles críticos** Filtra por vínculos WAN cuyo uso de ancho de banda ha alcanzado el 90 % o más de la capacidad de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="3a400-286">**Critical levels** Filter by WAN links whose bandwidth utilization has reached 90% or more than the bandwidth capacity</span></span>

4.  <span data-ttu-id="3a400-287">**Infrautilizados** Filtra por vínculos WAN cuyo uso de ancho de banda ha sido inferior al 25 % de la capacidad de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="3a400-287">**Under-utilized** Filter by WAN links whose bandwidth utilization has been less than 25% of the bandwidth capacity</span></span>

5.  <span data-ttu-id="3a400-288">**Tipo de vínculo** Filtra por los siguientes tipos de vínculos WAN:</span><span class="sxs-lookup"><span data-stu-id="3a400-288">**Link type** Filter by the following WAN links types:</span></span>
    
      - <span data-ttu-id="3a400-289">
            Tipo **sitio de red**</span><span class="sxs-lookup"><span data-stu-id="3a400-289">**Network site** type</span></span>
    
      - <span data-ttu-id="3a400-290">
            Tipo **entre sitios**</span><span class="sxs-lookup"><span data-stu-id="3a400-290">**Inter-site** type</span></span>
    
      - <span data-ttu-id="3a400-291">
            Tipo \*\*vínculo entre regiones**</span><span class="sxs-lookup"><span data-stu-id="3a400-291">**Inter-Region link** type</span></span>

6.  <span data-ttu-id="3a400-292">**Región** Filtra por región de red</span><span class="sxs-lookup"><span data-stu-id="3a400-292">**Region** Filter by network region</span></span>

<span data-ttu-id="3a400-293">En las ilustraciones siguientes se muestran los filtros descritos anteriormente.</span><span class="sxs-lookup"><span data-stu-id="3a400-293">The following figures show the previously described filters.</span></span>

<span data-ttu-id="3a400-p125">Filtrar por **Nombre**. Seleccione la lista de vínculos que han de mostrarse en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="3a400-p125">Filter by **Name**. Select the list of links that need to be displayed in the graph.</span></span>

<span data-ttu-id="3a400-296">![Filtrar por nombre en BandwidthUtilizationAnalyzer.] (images/JJ945604.002b7c8e-f0da-48ce-9e1a-5c34d2cab063(OCS.15).jpg "Filtrar por nombre en BandwidthUtilizationAnalyzer.")</span><span class="sxs-lookup"><span data-stu-id="3a400-296">![Filtering by Name in BandwidthUtilizationAnalyzer.](images/JJ945604.002b7c8e-f0da-48ce-9e1a-5c34d2cab063(OCS.15).jpg "Filtering by Name in BandwidthUtilizationAnalyzer.")</span></span>

<span data-ttu-id="3a400-297">Filtrar por **Límite superado**.</span><span class="sxs-lookup"><span data-stu-id="3a400-297">Filter by **Exceeded limit**.</span></span> <span data-ttu-id="3a400-298">Seleccione **True** para aplicar el filtro.</span><span class="sxs-lookup"><span data-stu-id="3a400-298">Select **True** to enforce the filter.</span></span>

<span data-ttu-id="3a400-299">![Filtrar por exceder el límite.] (images/JJ945604.5946c95e-76ce-46ca-8f3e-a79be1e5c527(OCS.15).jpg "Filtrar por exceder el límite.")</span><span class="sxs-lookup"><span data-stu-id="3a400-299">![Filtering by Exceeded Limit.](images/JJ945604.5946c95e-76ce-46ca-8f3e-a79be1e5c527(OCS.15).jpg "Filtering by Exceeded Limit.")</span></span>

<span data-ttu-id="3a400-300">Filtrar por **Niveles críticos**.</span><span class="sxs-lookup"><span data-stu-id="3a400-300">Filter by **Critical levels**.</span></span> <span data-ttu-id="3a400-301">Seleccione **True** para aplicar el filtro.</span><span class="sxs-lookup"><span data-stu-id="3a400-301">Select **True** to enforce the filter.</span></span>

<span data-ttu-id="3a400-302">![Filtrar por niveles críticos.] (images/JJ945604.60771a52-d8ba-4cb9-a02d-d6c888cb5505(OCS.15).jpg "Filtrar por niveles críticos.")</span><span class="sxs-lookup"><span data-stu-id="3a400-302">![Filtering by Critical Levels.](images/JJ945604.60771a52-d8ba-4cb9-a02d-d6c888cb5505(OCS.15).jpg "Filtering by Critical Levels.")</span></span>

<span data-ttu-id="3a400-303">Filtrar por **Infrautilizado**.</span><span class="sxs-lookup"><span data-stu-id="3a400-303">Filter by **Under utilized**.</span></span> <span data-ttu-id="3a400-304">Seleccione **True** para aplicar el filtro.</span><span class="sxs-lookup"><span data-stu-id="3a400-304">Select **True** to enforce the filter.</span></span>

<span data-ttu-id="3a400-305">![Filtrar por en uso.] (images/JJ945604.95a2bf01-5aba-4927-af47-1ad3c459d791(OCS.15).jpg "Filtrar por en uso.")</span><span class="sxs-lookup"><span data-stu-id="3a400-305">![Filtering by Under Utilized.](images/JJ945604.95a2bf01-5aba-4927-af47-1ad3c459d791(OCS.15).jpg "Filtering by Under Utilized.")</span></span>

<span data-ttu-id="3a400-306">Filtrar por **Tipo de vínculo**.</span><span class="sxs-lookup"><span data-stu-id="3a400-306">Filter by **Link Type**.</span></span> <span data-ttu-id="3a400-307">Seleccione el tipo o tipos que desee mostrar.</span><span class="sxs-lookup"><span data-stu-id="3a400-307">Select the type or types that need to be displayed.</span></span>

<span data-ttu-id="3a400-308">![Filtrar por tipo de vínculo.] (images/JJ945604.08757949-06bd-4cf3-809f-d81fd23a6639(OCS.15).jpg "Filtrar por tipo de vínculo.")</span><span class="sxs-lookup"><span data-stu-id="3a400-308">![Filtering by Link Type.](images/JJ945604.08757949-06bd-4cf3-809f-d81fd23a6639(OCS.15).jpg "Filtering by Link Type.")</span></span>

<span data-ttu-id="3a400-309">Filtrar por **Región**.</span><span class="sxs-lookup"><span data-stu-id="3a400-309">Filter by **Region**.</span></span> <span data-ttu-id="3a400-310">Seleccione una lista de regiones cuyos vínculos desee mostrar.</span><span class="sxs-lookup"><span data-stu-id="3a400-310">Select a list of regions whose links need to be displayed.</span></span>

<span data-ttu-id="3a400-311">![Filtrar por región.] (images/JJ945604.5de4cec4-6c09-48bb-98c7-b56f7bdb3d5a(OCS.15).jpg "Filtrar por región.")</span><span class="sxs-lookup"><span data-stu-id="3a400-311">![Filtering by Region.](images/JJ945604.5de4cec4-6c09-48bb-98c7-b56f7bdb3d5a(OCS.15).jpg "Filtering by Region.")</span></span>

</div>

</div>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="3a400-312">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3a400-312">Requirements</span></span>

  - <span data-ttu-id="3a400-313">.NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="3a400-313">The .NET Framework 3.5</span></span>

  - <span data-ttu-id="3a400-314">Microsoft Excel 2010 o Excel 2007</span><span class="sxs-lookup"><span data-stu-id="3a400-314">Microsoft Excel 2010 or Excel 2007</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="3a400-315">Resumen</span><span class="sxs-lookup"><span data-stu-id="3a400-315">Summary</span></span>

<span data-ttu-id="3a400-p131">El analizador de uso de ancho de banda se utiliza para representar el uso de ancho de banda de audio para el tráfico de comunicaciones unificadas en la red. Esta herramienta también se puede utilizar para informar sobre el uso de ancho de banda de vídeo en la red.</span><span class="sxs-lookup"><span data-stu-id="3a400-p131">Bandwidth Utilization Analyzer is used to plot the audio bandwidth utilization for UC traffic across the network. This tool can be used to report the utilization of video bandwidth on the network as well.</span></span>

</div>

</div>

<div>

## <a name="call-parkometer"></a><span data-ttu-id="3a400-318">Call Parkometer (Estacionamiento de llamadas)</span><span class="sxs-lookup"><span data-stu-id="3a400-318">Call Parkometer</span></span>

<span data-ttu-id="3a400-319">Call Parkometer es una aplicación de línea de comandos que proporciona acceso rápido a la base de datos de órbitas de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="3a400-319">Call Parkometer is a command-line application that provides easy access to the Call Park orbit database.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="3a400-320">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a400-320">Description</span></span>

<span data-ttu-id="3a400-321">Call Parkometer es una herramienta que se utiliza para realizar un seguimiento de las llamadas estacionadas actualmente.</span><span class="sxs-lookup"><span data-stu-id="3a400-321">Call Parkometer is a tool to track currently parked calls.</span></span> <span data-ttu-id="3a400-322">También recopila estadísticas sobre el uso de órbitas y el servidor de estacionamiento de llamadas (CPS).</span><span class="sxs-lookup"><span data-stu-id="3a400-322">It also collects statistics about orbits and Call Park Server (CPS) usage.</span></span> <span data-ttu-id="3a400-323">Esta herramienta de línea de comandos proporciona acceso de lectura y escritura a la base de datos de SQL Server de CPS a partir de un equipo conectado local o remoto.</span><span class="sxs-lookup"><span data-stu-id="3a400-323">This command-line tool provides both read and write-access to the CPS orbit SQL Server database from a local or remotely connected computer.</span></span>

<span data-ttu-id="3a400-p133">Todas las opciones se excluyen mutuamente. La sintaxis de línea de comandos es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="3a400-p133">All options are mutually exclusive. Command-line syntax is as follows:</span></span>

  - <span data-ttu-id="3a400-326">
            Parámetro \*\*–o\*\*: genera una lista de todos los intervalos de órbitas configurados para este grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="3a400-326">**–o** parameter—lists all orbit ranges configured for this pool.</span></span>

  - <span data-ttu-id="3a400-p134">
            Parámetro \*\*–n\*\*: genera una lista de las órbitas utilizadas actualmente en este grupo. La información que se muestra es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="3a400-p134">**–n** parameter—lists all currently used orbits in this pool. The information displayed is as follows:</span></span>
    
      - <span data-ttu-id="3a400-329">Identificador uniforme de recursos (URI) de SIP del estacionado y el estacionador.</span><span class="sxs-lookup"><span data-stu-id="3a400-329">SIP Uniform Resource Identifier (URI) of the parkee and parker.</span></span>
    
      - <span data-ttu-id="3a400-330">Nombre de host del CPS donde se ha estacionado la llamada.</span><span class="sxs-lookup"><span data-stu-id="3a400-330">Host name of the CPS where the call is parked.</span></span>
    
      - <span data-ttu-id="3a400-331">Marca de tiempo correspondiente al momento en que se estacionó la llamada.</span><span class="sxs-lookup"><span data-stu-id="3a400-331">Time stamp of when the call was parked.</span></span>

  - <span data-ttu-id="3a400-332">
            Parámetro \*\*–f\*\*: genera una lista del número de órbitas libres actualmente en el grupo.</span><span class="sxs-lookup"><span data-stu-id="3a400-332">**–f** parameter—lists the number of currently free orbits in the pool.</span></span>

  - <span data-ttu-id="3a400-333">**– parámetro \<-\> r n** : enumera \<las\> n últimas llamadas estacionadas.</span><span class="sxs-lookup"><span data-stu-id="3a400-333">**–r \<n\>** parameter—lists the \<n\> last parked calls.</span></span> <span data-ttu-id="3a400-334">La información mostrada es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="3a400-334">The information displayed is as follows:</span></span>
    
      - <span data-ttu-id="3a400-335">URI de SIP del estacionado.</span><span class="sxs-lookup"><span data-stu-id="3a400-335">Parkee SIP URI.</span></span>
    
      - <span data-ttu-id="3a400-336">URI de SIP del estacionador.</span><span class="sxs-lookup"><span data-stu-id="3a400-336">Parker SIP URI.</span></span>
    
      - <span data-ttu-id="3a400-337">Nombre de host del CPS donde se estacionó la llamada.</span><span class="sxs-lookup"><span data-stu-id="3a400-337">Host name of the CPS where the call was parked.</span></span>
    
      - <span data-ttu-id="3a400-338">Marca de tiempo correspondiente al momento en que se recuperó o finalizó la llamada.</span><span class="sxs-lookup"><span data-stu-id="3a400-338">Time stamp of when the call was retrieved or dropped.</span></span>

  - <span data-ttu-id="3a400-339">\*\*-t\<n\> \*\* parámetro-prueba para reservar una órbita en la base de datos para mostrar la aleatoriedad de los números de órbita asignados.</span><span class="sxs-lookup"><span data-stu-id="3a400-339">**-t\<n\>** parameter - tests reserving an orbit in the database to show the randomness of the assigned orbit numbers.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="3a400-340">Salida</span><span class="sxs-lookup"><span data-stu-id="3a400-340">Output</span></span>

<span data-ttu-id="3a400-341">Según los parámetros de entrada especificados en el símbolo del sistema, Call Parkometer muestra la salida siguiente:</span><span class="sxs-lookup"><span data-stu-id="3a400-341">Depending on the input parameters that are specified at a command prompt, Call Parkometer displays the following output:</span></span>

  - <span data-ttu-id="3a400-342">Todos los intervalos de órbitas configurados para este grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="3a400-342">All orbit ranges that are configured for this pool</span></span>

  - <span data-ttu-id="3a400-343">Llamadas estacionadas actualmente</span><span class="sxs-lookup"><span data-stu-id="3a400-343">Currently parked calls</span></span>

  - <span data-ttu-id="3a400-344">Número de órbitas libres (disponibles)</span><span class="sxs-lookup"><span data-stu-id="3a400-344">Number of free (available) orbits</span></span>

  - <span data-ttu-id="3a400-345">Llamadas estacionadas recientemente</span><span class="sxs-lookup"><span data-stu-id="3a400-345">Recently parked calls</span></span>

  - <span data-ttu-id="3a400-346">Órbitas reservadas para comprobar valores de órbitas uniformes y aleatorias</span><span class="sxs-lookup"><span data-stu-id="3a400-346">Reserved orbits for testing uniform and random orbit values</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="3a400-347">Finalidad</span><span class="sxs-lookup"><span data-stu-id="3a400-347">Purpose</span></span>

<span data-ttu-id="3a400-p136">El objetivo de la herramienta CPS es proporcionar acceso mediante línea de comandos a la base de datos de CPS. El administrador puede ver el uso de CPS y determinar el número de órbitas asignadas a un grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="3a400-p136">The purpose of the CPS tool is to provide command-line access to the CPS database. The administrator can view the CPS usage and determine the number of orbits assigned to a pool.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="3a400-350">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3a400-350">Requirements</span></span>

<span data-ttu-id="3a400-351">No hay requisitos si esta herramienta se ejecuta en el mismo equipo que ejecuta CPS.</span><span class="sxs-lookup"><span data-stu-id="3a400-351">There are no requirements if this tool is run on the same computer that is running CPS.</span></span> <span data-ttu-id="3a400-352">Si se ejecuta esta herramienta en un equipo remoto, la base de datos de SQL Server usada por Lync Server 2013 debe estar configurada para permitir el acceso remoto.</span><span class="sxs-lookup"><span data-stu-id="3a400-352">If this tool is run on a remote computer, the SQL Server database used by Lync Server 2013 must be configured to allow remote access.</span></span> <span data-ttu-id="3a400-353">Llame a Parkometer debe estar configurado con una cadena de conexión de base de datos de SQL Server para conectarse al servidor SQL Server del grupo.</span><span class="sxs-lookup"><span data-stu-id="3a400-353">Call Parkometer must be configured with a SQL Server database connection string to connect to the pool’s SQL Server.</span></span> <span data-ttu-id="3a400-354">Esta cadena de conexión de base de datos de SQL Server se define en el archivo de configuración **parkometer. exe. config**. Debe colocarse en el mismo directorio donde se encuentra parkometer. exe.</span><span class="sxs-lookup"><span data-stu-id="3a400-354">This SQL Server database connection string is defined in the configuration file, **parkometer.exe.config**. It must be placed in the same directory where parkometer.exe is located.</span></span> <span data-ttu-id="3a400-355">El siguiente archivo XML es un ejemplo de parkometer. exe. config. Los parámetros que deben configurarse son el nombre de usuario (por ejemplo\\, administrador de dominio), la contraseña (por ejemplo, contraseña) y el nombre de host (por ejemplo, mydomain).</span><span class="sxs-lookup"><span data-stu-id="3a400-355">The following XML file is an example of a parkometer.exe.config. The parameters that must be configured are user name (for example, mydomain\\Administrator), password (for example, mypassword), and host name (for example, myserver).</span></span>

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

</div>

<div>

## <a name="examples"></a><span data-ttu-id="3a400-356">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="3a400-356">Examples</span></span>

<span data-ttu-id="3a400-357">Intervalos de órbitas implementadas: el parámetro –o genera una lista de todos los intervalos de órbitas configurados para este grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="3a400-357">Deployed orbit ranges: the –o parameter lists all orbit ranges that are configured for this pool as shown</span></span>

<span data-ttu-id="3a400-358">![Intervalos orbitales en llamadas Parkometer.] (images/JJ945604.9ede64cb-29d9-4782-a34b-b76c42fbdcad(OCS.15).jpg "Intervalos orbitales en llamadas Parkometer.")</span><span class="sxs-lookup"><span data-stu-id="3a400-358">![Orbit ranges in Call Parkometer.](images/JJ945604.9ede64cb-29d9-4782-a34b-b76c42fbdcad(OCS.15).jpg "Orbit ranges in Call Parkometer.")</span></span>

<span data-ttu-id="3a400-359">Llamadas estacionadas actualmente: el parámetro –n genera una lista de todas las órbitas utilizadas actualmente en este grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="3a400-359">Currently parked calls: the –n parameter lists all currently used orbits on this pool as shown</span></span>

<span data-ttu-id="3a400-360">![Llamadas estacionadas actualmente en Call Parkometer.] (images/JJ945604.07a7eec4-7999-4c92-93f0-95525b244b4c(OCS.15).jpg "Llamadas estacionadas actualmente en Call Parkometer.")</span><span class="sxs-lookup"><span data-stu-id="3a400-360">![Currently-parked calls in Call Parkometer.](images/JJ945604.07a7eec4-7999-4c92-93f0-95525b244b4c(OCS.15).jpg "Currently-parked calls in Call Parkometer.")</span></span>

<span data-ttu-id="3a400-361">Número de órbitas libres: el parámetro –f genera una lista de todas las órbitas libres actualmente en el grupo.</span><span class="sxs-lookup"><span data-stu-id="3a400-361">Number of free orbits: the –f parameter lists the number of currently free orbits in the pool as shown</span></span>

<span data-ttu-id="3a400-362">![Órbitas gratis en el Parkometer de llamadas.] (images/JJ945604.ecc1d621-0ca0-4ecf-a579-08b41c6f08ed(OCS.15).jpg "Órbitas gratis en el Parkometer de llamadas.")</span><span class="sxs-lookup"><span data-stu-id="3a400-362">![Free orbits in Call Parkometer.](images/JJ945604.ecc1d621-0ca0-4ecf-a579-08b41c6f08ed(OCS.15).jpg "Free orbits in Call Parkometer.")</span></span>

<span data-ttu-id="3a400-363">Llamadas aparcadas recientemente: el parámetro \<–\> r n enumera \<las\> n últimas llamadas estacionadas, como se muestra.</span><span class="sxs-lookup"><span data-stu-id="3a400-363">Recently parked calls: the –r \<n\> parameter lists the \<n\> last parked calls as shown</span></span>

<span data-ttu-id="3a400-364">![Llamadas aparcadas recientemente en Call Parkometer.] (images/JJ945604.1c5eb27d-faa1-491b-b4aa-b484255c3353(OCS.15).jpg "Llamadas aparcadas recientemente en Call Parkometer.")</span><span class="sxs-lookup"><span data-stu-id="3a400-364">![Recently-parked calls in Call Parkometer.](images/JJ945604.1c5eb27d-faa1-491b-b4aa-b484255c3353(OCS.15).jpg "Recently-parked calls in Call Parkometer.")</span></span>

<span data-ttu-id="3a400-365">Prueba de reserva orbital: el parámetro \<–\> t n prueba la reserva de una órbita en la base de datos tal como se muestra</span><span class="sxs-lookup"><span data-stu-id="3a400-365">Test orbit reservation: the –t \<n\> parameter tests reserving an orbit in the database as shown</span></span>

<span data-ttu-id="3a400-366">![Probar las reservas de órbita en Call Parkometer.] (images/JJ945604.84c9b69e-7af0-4224-8711-a43a28f08691(OCS.15).jpg "Probar las reservas de órbita en Call Parkometer.")</span><span class="sxs-lookup"><span data-stu-id="3a400-366">![Test orbit reservations in Call Parkometer.](images/JJ945604.84c9b69e-7af0-4224-8711-a43a28f08691(OCS.15).jpg "Test orbit reservations in Call Parkometer.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="3a400-367">Resumen</span><span class="sxs-lookup"><span data-stu-id="3a400-367">Summary</span></span>

<span data-ttu-id="3a400-368">Call Parkometer es una herramienta de línea de comandos que proporciona información detallada sobre el servidor de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="3a400-368">Call Parkometer is a command-line tool that provides detailed information about the Call Park Server.</span></span>

</div>

</div>

<div>

## <a name="cleanupstorageservicedata"></a><span data-ttu-id="3a400-369">CleanupStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="3a400-369">CleanupStorageServiceData</span></span>

<span data-ttu-id="3a400-370">La herramienta del kit de recursos de CleanupStorageServiceData permite eliminar datos huérfanos de la base de datos que usa el servicio de almacenamiento de Lync Server (LYSS).</span><span class="sxs-lookup"><span data-stu-id="3a400-370">The CleanupStorageServiceData resource kit tool allows for deleting of orphaned data from the database used by the Lync Server Storage Service (LYSS).</span></span> <span data-ttu-id="3a400-371">Una de las funciones del servicio almacenamiento es para almacenar en búfer la comunicación entre Lync Server y los distintos extremos de almacenamiento de datos back-end, como SQL Server y Exchange.</span><span class="sxs-lookup"><span data-stu-id="3a400-371">One function of the storage service is to buffer communication between Lync Server and various back-end data storage endpoints, like SQL Server and Exchange.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="3a400-372">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a400-372">Description</span></span>

<span data-ttu-id="3a400-373">Para admitir una alta disponibilidad, LYSS acepta y guarda copias de los datos en varios servidores front-end en el grupo temporalmente y elimina esos datos una vez que se hayan entregado en su ubicación de almacenamiento de larga duración.</span><span class="sxs-lookup"><span data-stu-id="3a400-373">To support high availability, LYSS accepts and saves copies of the data on multiple front end servers in the pool temporarily, and removes that data once it has been delivered to its final long-term storage location.</span></span> <span data-ttu-id="3a400-374">Hay situaciones inusuales que pueden ocurrir durante cualquier otra operación normal, cuando un servidor puede bloquearse o experimentar un problema de procesamiento, y algunos datos podrían no limpiarse correctamente.</span><span class="sxs-lookup"><span data-stu-id="3a400-374">There are unusual situations which may occur during otherwise normal operation, when a server might crash or experience a processing issue, and some data might not get cleaned up properly.</span></span> <span data-ttu-id="3a400-375">Estos datos son inofensivos, pero consumen recursos de procesamiento limitados.</span><span class="sxs-lookup"><span data-stu-id="3a400-375">This data is harmless, but it does consume limited processing resources.</span></span> <span data-ttu-id="3a400-376">Gran parte del mantenimiento de datos obligatorio normal se automatiza, pero esta herramienta permite la identificación y eliminación segura de datos huérfanos cuando no es posible la eliminación automática.</span><span class="sxs-lookup"><span data-stu-id="3a400-376">Much of the normal required data maintenance is automated, but this tool allows for the safe identification and removal of such orphaned data when automated removal is not possible.</span></span> <span data-ttu-id="3a400-377">El uso de esta herramienta se indica cuando se genera una alerta de System Center Operations Manager (SCOM) de supervisión de estado que pide al administrador que quite los datos innecesarios de las bases de datos de LYSS locales del grupo.</span><span class="sxs-lookup"><span data-stu-id="3a400-377">Usage of this tool is indicated when a health monitoring System Center Operations Manager (SCOM) alert is raised which asks the administrator to remove the unneeded data from the local LYSS databases in the pool.</span></span> <span data-ttu-id="3a400-378">Habrá un evento correspondiente en el registro de eventos de la parte frontal que activó la alerta.</span><span class="sxs-lookup"><span data-stu-id="3a400-378">There will be a corresponding event in the event log on the front end which triggered the alert.</span></span> <span data-ttu-id="3a400-379">Los detalles del evento contendrán información sobre la cantidad de datos huérfanos contenidos en el front-end, y se genera cuando esos datos superen determinados umbrales previos a la determinación</span><span class="sxs-lookup"><span data-stu-id="3a400-379">The event details will contain information about the amount of orphaned data contained on the front end, and is raised when that data exceeds certain pre-determine thresholds</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="3a400-380">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3a400-380">Requirements</span></span>

<span data-ttu-id="3a400-381">Instale Lync Server 2013, herramientas del kit de recursos.</span><span class="sxs-lookup"><span data-stu-id="3a400-381">Install the Lync Server 2013, Resource Kit Tools.</span></span> <span data-ttu-id="3a400-382">La herramienta se ejecuta en máquinas Unidas al dominio en las que están instaladas el shell de administración de Lync Server y Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3a400-382">The tool runs on domain-joined machines where Lync Server and Lync Server 2013 Management Shell are installed.</span></span> <span data-ttu-id="3a400-383">La herramienta usa un cmdlet del shell de administración para identificar todos los servidores front-end del grupo.</span><span class="sxs-lookup"><span data-stu-id="3a400-383">The tool uses a cmdlet from the management shell to identify all Front End servers in the pool.</span></span> <span data-ttu-id="3a400-384">En segundo lugar, la herramienta debe ejecutarse desde un equipo del grupo en el que está instalada la base de datos **RtcLocal** .</span><span class="sxs-lookup"><span data-stu-id="3a400-384">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="3a400-385">Esta base de datos la usa la herramienta CleanupStorageServiceData para obtener los detalles de conexión necesarios para comunicarse con el servicio de enrutamiento de Lync Server. por último, la cuenta o credencial que invoca la herramienta debe tener permiso de lectura y escritura en el recurso compartido de archivos en el que quieren escribir el registro de salida. Además, esta herramienta depende de si el grupo está en un estado estable.</span><span class="sxs-lookup"><span data-stu-id="3a400-385">This database is used by the CleanupStorageServiceData tool to get the connection details needed to communicate with the Lync Server Routing Service.Finally, the account or credential invoking the tool must have read/write permission to the file share to which they want to write the output log.Also, this tool depends on the pool being in a stable state.</span></span> <span data-ttu-id="3a400-386">En esencia, esto significa que se espera que todos los servidores front-end estén funcionando, que la instancia de SQL Server LYNCLOCAL y la base de datos LYSS deben poder conectarse, y cada grupo de enrutamiento debe tener un conjunto completo de 1 servidor front-end principal y 2 frontales secundarios ervers.</span><span class="sxs-lookup"><span data-stu-id="3a400-386">In essence this means that every Front End server is expected to be up and running, the SQL Server LYNCLOCAL instance and LYSS database must be able to be connected to, and each routing group must have a complete set of 1 primary Front End servers and 2 secondary Front End servers.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="3a400-387">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="3a400-387">Examples</span></span>

<span data-ttu-id="3a400-388">C:\\archivos\\de programa Microsoft Lync Server\\2013 reskit\\StorageService\> ImportStorageServiceData. exe</span><span class="sxs-lookup"><span data-stu-id="3a400-388">C:\\Program Files\\Microsoft Lync Server 2013\\ResKit\\StorageService\> ImportStorageServiceData.exe</span></span>

    Description:
    This tool will remove orphaned data from the Storage Service database
    for a pool. You are required to run this tool on a machine inside the
    pool which has the Lync Server Management Shell installed and has RtcLocal database installed.
    Usage: Default behavior is to clean up orphaned data from the all the 
           Storage Service databases in the current pool.
    Additional Options:
    -Verbose    : Turn verbose output on.
    -LogPath    : The UNC path to which to write the log.
    ------------------------------------------------------------------------------
    Please wait while we initialize...
    Found 4 front end servers
    Replica Instances for LYSS Service
    Address: server2.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server1.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server3.vdomain.com - Primaries: 7 Secondaries: 14
    Primary Total Count = 28, Secondary Total Count = 56
    Finding and removing orphaned data for 28 routing groups
    Removing 1 stale groups from FE server.vdomain.com
    No stale routing groups detected on FE server2.vdomain.com
    No stale routing groups detected on FE server1.vdomain.com
    No stale routing groups detected on FE server3.vdomain.com
    Searching for stale queue items
    Removed 20 stale queue items for routing group 17D5435AE40259F7BBDF1866776386E4
    No stale queue items found for routing group 1975349662315F90B119DACB4F2AE3AD
    No stale queue items found for routing group 1A23E3D58BDB5A458A0B73F34AB7ACBE
    No stale queue items found for routing group 1AC91E3A1029535A80123121989CEADC
    No stale queue items found for routing group 3313935458E35B9B9759E08A15D251E6
    No stale queue items found for routing group 39BB0035B06B5427873FC6099720462A
    No stale queue items found for routing group 40721948E7B55CE893A53E911F76D185
    No stale queue items found for routing group 4501E04EAE4856059346949FF817C220
    No stale queue items found for routing group 4D833C98801F546F8E45E417EE028E2E
    No stale queue items found for routing group 5AD77443AD955A22A876749BE66D5317
    No stale queue items found for routing group 69844A271E6C5633A1F2B46A42287DD6
    No stale queue items found for routing group 69DA3BE407A95C7284EB4B1337718C93
    No stale queue items found for routing group 8437358AB34A5CC8967D5EF39494AB8D
    No stale queue items found for routing group 8ED455B1789655359816E1C5BF4C430F
    No stale queue items found for routing group 904F6C9B8AC951AE8B3C86684D3832E4
    No stale queue items found for routing group 90AAB3AE9A1950E0ADE7809A27021D63
    No stale queue items found for routing group 944F5724C65C5F93900DC1C8C898B102
    No stale queue items found for routing group 9E8A2630250C51769E39F63F0FB552BA
    No stale queue items found for routing group A11E27AE439A582288D4657EDA86B565
    No stale queue items found for routing group A9B10C76E764556FAEA3E47301EDF518
    No stale queue items found for routing group AEA2699E74ED59848ACEA7896699430D
    No stale queue items found for routing group B269961603E75065AFDA4F4F006DA5E4
    No stale queue items found for routing group BB873D9A3DA959DAB2FD743E5AA619F7
    No stale queue items found for routing group BCC6A48FBA2454B79B9EDB276657A404
    No stale queue items found for routing group C8EF4805722B5F6C876EBC0440B420FD
    No stale queue items found for routing group CA38EBDAC4845489ACE208C2240E4056
    No stale queue items found for routing group F5921887DB025C5F908CE42DB7F1AEE8
    No stale queue items found for routing group F9E606A825395422B3BF7A01ECBB7B1F
    Writing log: M:\Dev\Server\ResKit\StorageService\CleanupStorageServiceData.Log_20121009_151040
    Tool has finished execution.  Errors encountered: 0
    C:\Program Files\Microsoft Lync Server 2013\ResKit\StorageService>

</div>

</div>

<div>

## <a name="dbanalyze"></a><span data-ttu-id="3a400-389">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="3a400-389">DBAnalyze</span></span>

<div>

## <a name="description"></a><span data-ttu-id="3a400-390">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a400-390">Description</span></span>

<span data-ttu-id="3a400-391">DBAnalyze es una herramienta de línea de comandos que permite a los administradores recopilar informes de análisis sobre las bases de datos de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3a400-391">DBAnalyze is a command-line tool that helps administrators to gather analysis reports about the Lync Server 2013 databases.</span></span> <span data-ttu-id="3a400-392">DBAnalyze tiene los modos siguientes: diagnóstico, datos de usuario, conferencia, MCU y fragmentación de disco:</span><span class="sxs-lookup"><span data-stu-id="3a400-392">DBAnalyze has the following modes: diagnostic, user data, conference, MCUs, and disk fragmentation:</span></span>

  - <span data-ttu-id="3a400-393">**El modo**   de diagnóstico crea un informe que incluye información sobre las tablas (número de registros, fragmentación, tamaño de datos y tamaño del índice), tamaños de los archivos de registro y datos, la última vez que se hizo la copia de seguridad, la distribución de contactos entre los servidores que ejecutan Microsoft. Office Communications Server, el número promedio de permisos, contactos, contenedores, suscripciones, publicaciones, puntos de conexión por usuario, cualquier usuario no alojado correctamente, usuarios que no se pueden enrutar, el número promedio de conferencias organizadas por usuario, programadas conferencias, conferencias activas y versión de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="3a400-393">**Diagnostic mode**   Creates a report that includes information about tables (number of records, fragmentation, data size, and index size), data and log file sizes, the last back-up time, contact distribution among servers that are running Microsoft Office Communications Server, the average number of permissions, contacts, containers, subscriptions, publications, endpoints per user, any improperly homed users, users that can’t be routed, the average number of conferences organized per user, scheduled conferences, active conferences, and the database version.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3a400-394">La ejecución en modo de diagnóstico puede afectar al rendimiento del servidor.</span><span class="sxs-lookup"><span data-stu-id="3a400-394">Running diagnostic mode can affect server performance.</span></span>

    
    </div>

  - <span data-ttu-id="3a400-395">**Modo de datos de usuario**  Notifica los datos de contacto, contenedor, suscripción, publicación, permisos y grupo de contactos de un usuario específico o de los usuarios que tienen ese usuario en sus listas de contactos y permisos.</span><span class="sxs-lookup"><span data-stu-id="3a400-395">**User data mode**  Reports contact, container, subscription, publication, permission, and contact-group data for a specified user or for users who have that user in their contact and permission lists.</span></span> <span data-ttu-id="3a400-396">Este modo también proporciona datos de resumen para conferencias que un usuario organice o a las que esté invitado.</span><span class="sxs-lookup"><span data-stu-id="3a400-396">This mode also reports summary data for conferences that a user organizes or is invited to.</span></span>

  - <span data-ttu-id="3a400-397">**El modo**   de conferencia informa de datos detallados para una conferencia determinada, incluidos todos los detalles de tiempo de programación de la Conferencia, la lista de invitados, la lista de tipos de medios permitidos para la Conferencia, los MCU activos (unidades de control multipunto), el Active lista de participantes y estado de señalización de cada participante.</span><span class="sxs-lookup"><span data-stu-id="3a400-397">**Conference mode**   Reports detailed data for a specific conference, including all schedule-time details for the conference, the invitee list, the list of media types allowed for the conference, active MCUs (multipoint control units), the active participant list, and each participant’s signaling state.</span></span>

  - <span data-ttu-id="3a400-398">\*\*\*\*  Descodificar el identificador de reunión descodifica un identificador de reunión de red de telefonía pública conmutada (RTC) especificado por el modificador **/pstnid** , pero no se conecta al back-end para obtener información detallada.</span><span class="sxs-lookup"><span data-stu-id="3a400-398">**Decode Meeting ID**  Decodes a public switched telephone network (PSTN) meeting ID that is specified by the **/pstnid** switch but does not connect to the back end for detailed information.</span></span>

  - <span data-ttu-id="3a400-399">**Resolver una conferencia**   descodifica un identificador de reunión RTC especificado por el modificador **/pstnid** y muestra información sobre la Conferencia indicada por el identificador.</span><span class="sxs-lookup"><span data-stu-id="3a400-399">**Resolve conference**   Decodes a PSTN meeting ID that is specified by the **/pstnid** switch and displays information about the conference indicated by the ID.</span></span>

  - <span data-ttu-id="3a400-400">**El modo**  MCU informa de la identificación, el tipo de medio, la dirección URL, el estado de latido, la carga de conferencia y la carga de participantes de cada MCU de la agrupación.</span><span class="sxs-lookup"><span data-stu-id="3a400-400">**MCUs mode**  Reports the ID, media type, URL, heartbeat status, conference load, and participant load for each MCU in the pool.</span></span>

  - <span data-ttu-id="3a400-401">**El modo**  de fragmentación de disco muestra el estado de fragmentación de todos los discos.</span><span class="sxs-lookup"><span data-stu-id="3a400-401">**Disk fragmentation mode**  Displays the fragmentation status of all disks.</span></span>

<span data-ttu-id="3a400-p143">Esta herramienta puede utilizarse para diagnosticar diferentes problemas o para ayudar a los administradores con la planificación de capacidad. Por ejemplo, si la mayoría de los usuarios alojados en el servidor A eligen a usuarios alojados en el servidor B como sus contactos, el administrador puede mover los usuarios del servidor A al servidor B para reducir el tráfico entre servidores.</span><span class="sxs-lookup"><span data-stu-id="3a400-p143">This tool can be used to diagnose various problems or to assist administrators with capacity planning. For example, if most of the users homed on server A choose users homed on server B as their contacts, the administrator can move the users on server A to server B to reduce cross-server traffic.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="3a400-404">Salida</span><span class="sxs-lookup"><span data-stu-id="3a400-404">Output</span></span>

<span data-ttu-id="3a400-405">Esta herramienta genera informes predefinidos sobre la base de datos de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3a400-405">This tool outputs predefined reports about the Lync Server 2013 database.</span></span> <span data-ttu-id="3a400-406">**Ruta de acceso:** %\\ProgramFiles% Microsoft Lync\\Server 2013 reskit</span><span class="sxs-lookup"><span data-stu-id="3a400-406">**Path:** %ProgramFiles%\\Microsoft Lync Server 2013\\Reskit</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="3a400-407">Finalidad</span><span class="sxs-lookup"><span data-stu-id="3a400-407">Purpose</span></span>

<span data-ttu-id="3a400-408">Para instalar Dbanalyze.exe, copie el archivo en una carpeta local y, a continuación, ejecute la herramienta.</span><span class="sxs-lookup"><span data-stu-id="3a400-408">To install Dbanalyze.exe, copy it to a local folder and then run the tool.</span></span> <span data-ttu-id="3a400-409">Para usar la herramienta, ejecute el comando siguiente desde la línea de comandos.`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`</span><span class="sxs-lookup"><span data-stu-id="3a400-409">To use the tool, run the following command from the command line.`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`</span></span> <span data-ttu-id="3a400-410">A continuación encontrará las descripciones de las opciones de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="3a400-410">The descriptions for the command-line options are shown below.</span></span>

<span data-ttu-id="3a400-411">![Opciones de la línea de comandos para Dbanalyze. exe.] (images/JJ945604.22bf3432-af6d-495b-8f48-d94c5d259523(OCS.15).jpg "Opciones de la línea de comandos para Dbanalyze. exe.")</span><span class="sxs-lookup"><span data-stu-id="3a400-411">![Command line options for Dbanalyze.exe.](images/JJ945604.22bf3432-af6d-495b-8f48-d94c5d259523(OCS.15).jpg "Command line options for Dbanalyze.exe.")</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="3a400-412">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3a400-412">Requirements</span></span>

<span data-ttu-id="3a400-413">**Equipo informático** DBAnalyze solo puede ejecutarse desde un equipo unido a un dominio que tenga instalado Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3a400-413">**Computer** DBAnalyze can be run only from a domain-joined computer that has Lync Server 2013 installed.</span></span>

<span data-ttu-id="3a400-414">**Red** El equipo debe ser capaz de conectarse a la base de datos back-end.</span><span class="sxs-lookup"><span data-stu-id="3a400-414">**Network** The computer should be able to connect to the back-end database.</span></span>

<span data-ttu-id="3a400-415">**Software** Los componentes del software Lync Server 2013 deben instalarse antes de ejecutar DBAnalyze.</span><span class="sxs-lookup"><span data-stu-id="3a400-415">**Software** Lync Server 2013 software components must be installed before running DBAnalyze.</span></span>

<span data-ttu-id="3a400-416">**Usuarios** En la tabla siguiente se muestran los administradores que tienen los permisos necesarios para acceder a bases de datos de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3a400-416">**Users**The table below shows the administrators who have the necessary permissions to access Lync Server 2013 databases.</span></span>

<span data-ttu-id="3a400-417">![Tabla de permisos de Dbanalyze. exe.] (images/JJ945604.b8931e9e-834e-4dec-8a84-2fc47d1613e9(OCS.15).jpg "Tabla de permisos de Dbanalyze. exe.")</span><span class="sxs-lookup"><span data-stu-id="3a400-417">![Permissions table for Dbanalyze.exe.](images/JJ945604.b8931e9e-834e-4dec-8a84-2fc47d1613e9(OCS.15).jpg "Permissions table for Dbanalyze.exe.")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3a400-418">Para el modo <STRONG>/report:disk</STRONG> se necesita una cuenta de administrador local.</span><span class="sxs-lookup"><span data-stu-id="3a400-418">A local administrator account is required for <STRONG>/report:disk</STRONG> mode.</span></span>



</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="3a400-419">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="3a400-419">Examples</span></span>

<span data-ttu-id="3a400-420">A continuación se muestran varios ejemplos de comandos de Dbanalyze.exe válidos:</span><span class="sxs-lookup"><span data-stu-id="3a400-420">The following are examples of valid Dbanalyze.exe commands:</span></span>

    dbanalyze.exe /report:diag
    dbanalyze.exe /report:user /user:usera@domainb.com
    dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
    dbanalyze.exe /report:resolve /pstnid:12345
    dbanalyze.exe /report:mcus
    dbanalyze.exe /report:disk

</div>

<div>

## <a name="summary"></a><span data-ttu-id="3a400-421">Resumen</span><span class="sxs-lookup"><span data-stu-id="3a400-421">Summary</span></span>

<span data-ttu-id="3a400-422">DBAnalyzer proporciona a los administradores una forma rápida y sencilla de analizar bases de datos de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3a400-422">DBAnalyzer provides administrators a quick and easy to analyze Lync Server 2013 databases.</span></span>

</div>

</div>

<div>

## <a name="importstorageservicedata"></a><span data-ttu-id="3a400-423">ImportStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="3a400-423">ImportStorageServiceData</span></span>

<span data-ttu-id="3a400-424">La herramienta de kit de recursos ImportStorageServiceData permite reimportar datos de colas y puntos de conexión que hayan sido vaciados del servicio de almacenamiento (LYSS) de nuevo en el servicio de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="3a400-424">The ImportStorageServiceData resource kit tool allows for re-importing Queue and Endpoint data that was flushed out of the Storage Service (LYSS) back into the Storage Service.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="3a400-425">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a400-425">Description</span></span>

<span data-ttu-id="3a400-426">Los datos del servicio de almacenamiento pueden haber sido vaciados de forma automática (periódica) según el estado del elemento de cola o el tamaño de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="3a400-426">The data flushed out of the Storage Service could have been automatic (periodic) based on Queue Item status or database size.</span></span> <span data-ttu-id="3a400-427">Puede haber ocurrido debido a la invocación manual del cmdlet de la conmutación por error del grupo de servidores o por el cmdlet StorageServiceFullFlush (invocado por el cmdlet de conmutación por error del grupo de servidores).</span><span class="sxs-lookup"><span data-stu-id="3a400-427">It could have happened due to the manual invocation of the pool failover cmdlet, or the StorageServiceFullFlush cmdlet (which the pool failover cmdlet invokes).</span></span> <span data-ttu-id="3a400-428">Tenga en cuenta que, idealmente, los datos no se volverán a importar si cualquiera de los servidores de aplicaciones para el usuario del servicio de almacenamiento (LYSS) se encuentra por encima del nivel normal, ya que, por lo tanto, es probable que se vuelvan a exportar más datos. Además, los problemas que podrían haber contribuido a errores que provocaban el aumento de la cola del servicio de almacenamiento (por ejemplo, errores de puntos de conexión de Exchange, problemas de red u otros problemas).</span><span class="sxs-lookup"><span data-stu-id="3a400-428">Note that data should ideally not be re-imported if any of the Storage Service (LYSS ) database size on the front ends is above the normal level, because doing so will likely just cause more data to be exported back out. Furthermore, any problems which could have contributed to errors that caused the Storage Service Queue to grow should first be resolved (for example Exchange endpoint errors, network issues, or other problems).</span></span>

<span data-ttu-id="3a400-429">**Escenario 1:** durante la conmutación por error del grupo de servidores, los archivos pueden vaciarse del servicio de almacenamiento para cada front-end.</span><span class="sxs-lookup"><span data-stu-id="3a400-429">**Scenario 1:** during pool failover, files may be flushed out from storage service for each front end.</span></span> <span data-ttu-id="3a400-430">Después de completar la conmutación por error, debe ejecutarse la herramienta para volver a importar los datos.</span><span class="sxs-lookup"><span data-stu-id="3a400-430">After failover is completed, the tool should be run to re-import the data.</span></span>

<span data-ttu-id="3a400-431">**Escenario 2:** los datos se vacían automáticamente todos los días o cuando el tamaño de la base de datos del servicio de almacenamiento supera determinados umbrales (por ejemplo, 60 %, 80 %, 90 %).</span><span class="sxs-lookup"><span data-stu-id="3a400-431">**Scenario 2:** data is being flushed automatically each day or in response to Storage Service database exceeding certain size thresholds ( for example 60%, 80%, 90% full ).</span></span> <span data-ttu-id="3a400-432">El administrador debe volver a importar de forma periódica los datos que hayan sido vaciados de forma automática.</span><span class="sxs-lookup"><span data-stu-id="3a400-432">This automatically flushed data should be re-imported routinely by the administrator.</span></span> <span data-ttu-id="3a400-433">En la situación anterior, si el paquete SCOM con supervisión no se ha implementado, hay eventos para el servicio de almacenamiento de Lync Server relacionados con los datos que se han vaciado del servicio de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="3a400-433">In the above situation, if the monitoring SCOM pack is not deployed, there are events for Lync Server Storage Service relating to data being flushed from the Storage Service.</span></span> <span data-ttu-id="3a400-434">Los id. de evento son 32075 (se ha iniciado una operación de vaciado completo), 32076 (se ha completado el vaciado completo), 32082 (se ha iniciado el vaciado de nivel de mantenimiento), 32083 (se ha completado el vaciado de nivel de mantenimiento) y 32089 (se ha producido un vaciado porque se ha llenado la base de datos).</span><span class="sxs-lookup"><span data-stu-id="3a400-434">Event IDs of 32075 (full flush operation is started), 32076 (full flush has completed), 32082 (maintenance level flush started), 32083 (maintenance level flush complete), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="3a400-435">Estos identificadores de evento se corresponden con la versión RTM.</span><span class="sxs-lookup"><span data-stu-id="3a400-435">Note these event Ids correspond to the RTM release.</span></span> <span data-ttu-id="3a400-436">Cuando un administrador ve estos eventos, significa que hay archivos que se han vaciado. Estos datos deberían importarse rutinariamente con esta herramienta, por ejemplo, una vez por semana.</span><span class="sxs-lookup"><span data-stu-id="3a400-436">When an administrator sees these events, it means that there are files that have been flushed out. This data should routinely be imported back using this tool, for example once per week.</span></span>

<span data-ttu-id="3a400-437">En el caso de la versión de servicio en línea, si se implementa el paquete SCOM para la supervisión de estado SCOM para Lync Server, hay nuevas alertas que se pueden generar y que piden al administrador que vuelva a importar los datos vaciados en el servicio de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="3a400-437">For the Online Service release, if health monitoring SCOM pack for Lync Server is deployed, there are new alerts which may be raised which ask the administrator to re-import the flushed data back into Storage Service.</span></span> <span data-ttu-id="3a400-438">Existirá un evento correspondiente en el registro de eventos del servidor front-end que haya activado la alerta.</span><span class="sxs-lookup"><span data-stu-id="3a400-438">There will be a corresponding event in the event log on the Front End server which triggered the alert.</span></span> <span data-ttu-id="3a400-439">El evento ofrecerá una descripción de la ruta de acceso principal donde se encuentran los archivos de los datos vaciados, así como el número de archivos que cumplen con los criterios de alerta.</span><span class="sxs-lookup"><span data-stu-id="3a400-439">The event will give a description of the Parent path under which the flushed data files are located, as well as how many files there are which meet the alert criteria.</span></span> <span data-ttu-id="3a400-440">Los criterios de alerta es que haya X o más archivos en la ruta de acceso primaria con un mínimo de Y días (donde X e Y están predefinidos en el servicio de almacenamiento, pero pueden reemplazarse si se cambia el archivo APPCONFIG).</span><span class="sxs-lookup"><span data-stu-id="3a400-440">The alert criteria is that there are X or more files under the particular parent path which are at least Y days old ( where X and Y are preset within the StorageService but can be overridden by changing the APPCONFIG file.)Two examples of events which can trigger the health alert are shown below, with the difference being their parent path.</span></span> <span data-ttu-id="3a400-441">A continuación se muestran dos ejemplos de eventos que pueden activar la alerta de estado, cuya diferencia es la ruta de acceso primaria.</span><span class="sxs-lookup"><span data-stu-id="3a400-441">One possibility is under Web service file share, while the other possibility is the local Application Data directory of each front end.</span></span> <span data-ttu-id="3a400-442">(por ejemplo, c\\:\\ProgramData\\Microsoft Lync\\Server StorageService).</span><span class="sxs-lookup"><span data-stu-id="3a400-442">( for example c:\\ProgramData\\Microsoft\\Lync Server\\StorageService ).</span></span> <span data-ttu-id="3a400-443">A continuación, el administrador ejecutará esta herramienta de kit de recursos.</span><span class="sxs-lookup"><span data-stu-id="3a400-443">The administrator will then run this reskit tool.</span></span>

<span data-ttu-id="3a400-444">Esta herramienta aumentará la carga de CPU y de E/S en el front-end donde se ejecute, así como en otros front-end, si los datos no son propiedad del front-end donde se ejecuta la herramienta.</span><span class="sxs-lookup"><span data-stu-id="3a400-444">This tool will increase CPU and IO load on the front end it is running on, as well as other front ends, in the situation that the data is not owned by the front end that the tool is executed on.</span></span> <span data-ttu-id="3a400-445">Se recomienda ejecutar esta herramienta cuando los front-end no estén sometidos a cargas elevadas de CPU y de E/S (por ejemplo, en horas de poca actividad).</span><span class="sxs-lookup"><span data-stu-id="3a400-445">We recommend runng this tool when front ends are not under heavy CPU and IO load, for example outside of peak hours.</span></span> <span data-ttu-id="3a400-446">En segundo lugar, esta herramienta puede tardar entre 2 y 3 minutos para importar un archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="3a400-446">Secondly, this tool can 2 to 3 minutes to import one data file.</span></span> <span data-ttu-id="3a400-447">Ten esto en cuenta al estimar cuánto tiempo se ejecutará la herramienta. El archivo de registro detallado generado por la herramienta aparecerá de forma predeterminada en el almacén de archivos.</span><span class="sxs-lookup"><span data-stu-id="3a400-447">Keep this in mind when estimating how long tool will be running.The verbose log file generated by the tool will by default appear on the File Store.</span></span> <span data-ttu-id="3a400-448">Elimínelo si no se detectan errores, ya que el tamaño del archivo de registro puede ser de varias decenas de MB o más.</span><span class="sxs-lookup"><span data-stu-id="3a400-448">Delete it if there are no errors reported, because the log file can be tens of MB or more.</span></span>

<span data-ttu-id="3a400-449">![Eventos de registro de eventos del servidor de almacenamiento de ejemplo.] (images/JJ945604.3a903ef7-ea8a-4606-8229-a3e32f13af3a(OCS.15).jpg "Eventos de registro de eventos del servidor de almacenamiento de ejemplo.")</span><span class="sxs-lookup"><span data-stu-id="3a400-449">![Sample Storage Server event log events.](images/JJ945604.3a903ef7-ea8a-4606-8229-a3e32f13af3a(OCS.15).jpg "Sample Storage Server event log events.")</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="3a400-450">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3a400-450">Requirements</span></span>

<span data-ttu-id="3a400-451">Instale Lync Server 2013, herramientas del kit de recursos.</span><span class="sxs-lookup"><span data-stu-id="3a400-451">Install the Lync Server 2013, Resource Kit Tools.</span></span> <span data-ttu-id="3a400-452">La herramienta se ejecuta en máquinas Unidas al dominio donde se instalan Lync Server y el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3a400-452">The tool runs on domain-joined machines where Lync Server and Lync Server Management Shell are installed.</span></span> <span data-ttu-id="3a400-453">La herramienta usa un cmdlet del shell de administración para identificar todos los servidores front-end del grupo.</span><span class="sxs-lookup"><span data-stu-id="3a400-453">The tool uses a cmdlet from the management shell to identify all the Front End servers in the pool.</span></span> <span data-ttu-id="3a400-454">En segundo lugar, la herramienta debe ejecutarse desde un equipo del grupo en el que está instalada la base de datos **RtcLocal** .</span><span class="sxs-lookup"><span data-stu-id="3a400-454">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="3a400-455">Esta base de datos la usa la herramienta para recuperar la ubicación del recurso compartido de archivos WebService para el grupo. Además, antes de usar la herramienta, cada servidor front-end debe habilitar la comunicación remota de Windows PowerShell con **enable-PSRemoting** en cada servidor front-end, así como en el equipo desde el que se ejecuta la herramienta.</span><span class="sxs-lookup"><span data-stu-id="3a400-455">This database is used by the tool to retrieve the location of the WEBSERVICE file share for the pool.Additionally, before using the tool, each Front End server must first enable Windows PowerShell Remoting using **Enable-PSRemoting** on each Front End server, as well as the machine that the tool is executed from.</span></span> <span data-ttu-id="3a400-456">De lo contrario, los comandos remotos de Windows PowerShell de esta herramienta producirán errores.</span><span class="sxs-lookup"><span data-stu-id="3a400-456">Otherwise, remote Windows PowerShell commands from this tool will fail.</span></span> <span data-ttu-id="3a400-457">La comunicación remota de Windows PowerShell puede desactivarse en todos los servidores front-end del grupo después de que haya terminado.</span><span class="sxs-lookup"><span data-stu-id="3a400-457">Windows PowerShell Remoting can be turned off on all Front End servers in the pool after it is finished.</span></span> <span data-ttu-id="3a400-458">Por último, la cuenta o credencial que invoca la herramienta debe tener permiso de lectura y escritura para el recurso compartido de archivos WebService para el grupo en el que están ejecutando esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="3a400-458">Finally, the account or credential invoking the tool must have read/write permission to the webservice file share for the pool they are executing this tool on.</span></span> <span data-ttu-id="3a400-459">En caso contrario, la herramienta generará errores de permisos de e/s.</span><span class="sxs-lookup"><span data-stu-id="3a400-459">Otherwise the tool will fail with IO Permission errors.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3a400-460">En Windows Server 2012, el servicio remoto de Windows PowerShell está habilitado de forma predeterminada, pero no en el sistema operativo Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="3a400-460">On Windows Server 2012, Windows PowerShell Remoting is enabled by default, but not on the Windows Server 2008 operating system.</span></span>



</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="3a400-461">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="3a400-461">Examples</span></span>

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

</div>

</div>

<div>

## <a name="lcssync"></a><span data-ttu-id="3a400-462">LCSSync</span><span class="sxs-lookup"><span data-stu-id="3a400-462">LCSSync</span></span>

<span data-ttu-id="3a400-463">La herramienta LCSSync ayuda a implementar el software de comunicaciones de Lync Server 2013 en un entorno de varios bosques.</span><span class="sxs-lookup"><span data-stu-id="3a400-463">The LCSSync tool helps to deploy Lync Server 2013 communications software in a multi-forest environment.</span></span> <span data-ttu-id="3a400-464">Esta herramienta se usa para sincronizar usuarios y grupos de distintos bosques de usuario como un objeto de contacto de los servicios de dominio de Active Directory con un bosque central donde se instala Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3a400-464">This tool is used to synchronize users and groups from different user forests as an Active Directory Domain Services contact object to a central forest where Lync Server 2013 is installed.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="3a400-465">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a400-465">Description</span></span>

<span data-ttu-id="3a400-466">LCSSync usa los objetos de contacto de los servicios de dominio de Active Directory sincronizados en el bosque central para habilitar usuarios para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3a400-466">LCSSync uses the synchronized Active Directory Domain Services contact objects in the central forest to enable users for Lync Server.</span></span> <span data-ttu-id="3a400-467">Para proporcionar un inicio de sesión único, la cuenta de usuario principal debe estar asignada al objeto de contacto de los servicios de dominio de Active Directory en el bosque central de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3a400-467">To provide single sign-in, the primary user account must be mapped to the Active Directory Domain Services contact object in the central forest for Lync Server 2013.</span></span> <span data-ttu-id="3a400-468">Esta herramienta ayuda a realizar esa asignación.</span><span class="sxs-lookup"><span data-stu-id="3a400-468">This tool helps perform that mapping.</span></span> <span data-ttu-id="3a400-469">Esta herramienta proporciona plantillas para crear agentes de administración en Microsoft Identity Integration Server.</span><span class="sxs-lookup"><span data-stu-id="3a400-469">This tool provides templates for creating Management Agents in the Microsoft Identity Integration Server.</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="3a400-470">Resumen</span><span class="sxs-lookup"><span data-stu-id="3a400-470">Summary</span></span>

<span data-ttu-id="3a400-471">La herramienta LCSSync ayuda a implementar Lync Server en un entorno de varios bosques.</span><span class="sxs-lookup"><span data-stu-id="3a400-471">The LCSSync tool helps to deploy Lync Server in a multi-forest environment.</span></span>

</div>

</div>

<div>

## <a name="lookupuserconsole"></a><span data-ttu-id="3a400-472">LookupUserConsole</span><span class="sxs-lookup"><span data-stu-id="3a400-472">LookupUserConsole</span></span>

<span data-ttu-id="3a400-473">La herramienta LookupUserConsole muestra información de enrutamiento de Lync Server interno sobre usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="3a400-473">The LookupUserConsole tool displays internal Lync Server routing information about specific users.</span></span> <span data-ttu-id="3a400-474">Esta información puede ser útil para que el personal de soporte de Microsoft pueda diagnosticar problemas de implementación y enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="3a400-474">This information may be useful to Microsoft support personal in diagnosing deployment and routing problems.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="3a400-475">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a400-475">Description</span></span>

<span data-ttu-id="3a400-476">La ejecución de LookupUserConsole. exe abrirá un símbolo del sistema que acepta direcciones SIP e intenta mostrar la información de enrutamiento de Lync Server interna relacionada.</span><span class="sxs-lookup"><span data-stu-id="3a400-476">Executing LookupUserConsole.exe will open a command prompt that accepts SIP addresses and attempts to display internal Lync Server routing information relating them.</span></span> <span data-ttu-id="3a400-477">Escriba **exit** para salir de la herramienta LookupUserConsole.</span><span class="sxs-lookup"><span data-stu-id="3a400-477">Type **exit** to quit the LookupUserConsole tool.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="3a400-478">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3a400-478">Requirements</span></span>

<span data-ttu-id="3a400-479">Instale Lync Server 2013, herramientas del kit de recursos.</span><span class="sxs-lookup"><span data-stu-id="3a400-479">Install the Lync Server 2013, Resource Kit Tools.</span></span> <span data-ttu-id="3a400-480">La herramienta se ejecuta en máquinas Unidas al dominio donde Lync Server está instalado</span><span class="sxs-lookup"><span data-stu-id="3a400-480">The tool runs on domain-joined machines where Lync Server is installed</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="3a400-481">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="3a400-481">Examples</span></span>

<span data-ttu-id="3a400-482">C:\\archivos\\de programa Microsoft Lync Server\\2013 reskit\>LookupUserConsole. exe</span><span class="sxs-lookup"><span data-stu-id="3a400-482">C:\\Program Files\\Microsoft Lync Server 2013\\ResKit\>LookupUserConsole.exe</span></span>

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

</div>

</div>

<div>

## <a name="msturnping"></a><span data-ttu-id="3a400-483">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="3a400-483">MsTurnPing</span></span>

<span data-ttu-id="3a400-484">La herramienta MSTurnPing permite al administrador del software de comunicaciones Microsoft Lync Server 2013 comprobar el estado de los servidores que ejecutan el perímetro de audio/vídeo y los servicios de autenticación de audio y vídeo, así como los servidores que ejecutan la Directiva de ancho de banda. Servicios de la topología.</span><span class="sxs-lookup"><span data-stu-id="3a400-484">The MSTurnPing tool allows an administrator of Microsoft Lync Server 2013 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="3a400-485">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a400-485">Description</span></span>

<span data-ttu-id="3a400-486">La herramienta MSTurnPing permite al administrador del software de comunicaciones Lync Server 2013 comprobar el estado de los servidores que ejecutan el perímetro de audio/vídeo y los servicios de autenticación de audio y vídeo, así como los servidores que ejecutan servicios de directiva de ancho de banda en el topología.</span><span class="sxs-lookup"><span data-stu-id="3a400-486">The MSTurnPing tool allows an administrator of Lync Server 2013 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

<span data-ttu-id="3a400-487">La herramienta permite a los administradores realizar las pruebas siguientes:</span><span class="sxs-lookup"><span data-stu-id="3a400-487">The tool allows the administrator to perform the following tests:</span></span>

1.  <span data-ttu-id="3a400-488">Prueba de servidor perimetral de A/V: la herramienta realiza las siguientes pruebas contra todos los servidores perimetrales de A/V en la topología:</span><span class="sxs-lookup"><span data-stu-id="3a400-488">A/V Edge Server test: The tool performs tests against all A/V Edge Servers in the topology by doing the following:</span></span>
    
      - <span data-ttu-id="3a400-489">Comprobar que el servicio de autenticación de audio y vídeo de Lync Server se ha iniciado y puede emitir las credenciales correctas.</span><span class="sxs-lookup"><span data-stu-id="3a400-489">Verifying that the Lync Server Audio/Video Authentication service is started and can issue proper credentials.</span></span>
    
      - <span data-ttu-id="3a400-490">Comprobando que el servicio perimetral de audio/vídeo de Lync Server se ha iniciado y puede asignar los recursos en el borde externo correctamente.</span><span class="sxs-lookup"><span data-stu-id="3a400-490">Verifying that the Lync Server Audio/Video Edge service is started and can allocate the resources on the external edge successfully.</span></span>

2.  <span data-ttu-id="3a400-491">Prueba del servicio de directiva de ancho de banda: la herramienta realiza las pruebas siguientes contra todos los servidores que ejecutan los servicios de directiva de ancho de banda en la topología:</span><span class="sxs-lookup"><span data-stu-id="3a400-491">Bandwidth Policy Service test: The tool performs tests against all the servers that are running the Bandwidth Policy Services in the topology by doing the following:</span></span>
    
      - <span data-ttu-id="3a400-492">Comprobar que el servicio de directivas de ancho de banda (autenticación) de Lync Server se ha iniciado y puede emitir las credenciales correctas.</span><span class="sxs-lookup"><span data-stu-id="3a400-492">Verifying that the Lync Server Bandwidth Policy Service (Authentication) is started and can issue proper credentials.</span></span>
    
      - <span data-ttu-id="3a400-493">Comprobar que el servicio de directivas de ancho de banda (principal) de Lync Server se ha iniciado y puede realizar la comprobación de ancho de banda correctamente.</span><span class="sxs-lookup"><span data-stu-id="3a400-493">Verifying that the Lync Server Bandwidth Policy Service (Core) is started and can perform the bandwidth check successfully.</span></span>

<span data-ttu-id="3a400-494">Esta herramienta debe ejecutarse en un equipo que forme parte de la topología y que tenga instalado el almacén local. </span><span class="sxs-lookup"><span data-stu-id="3a400-494">This tool must be run from a computer that is part of the topology and has the local store installed.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="3a400-495">Salida</span><span class="sxs-lookup"><span data-stu-id="3a400-495">Output</span></span>

<span data-ttu-id="3a400-496">La herramienta genera los resultados de todas las operaciones.</span><span class="sxs-lookup"><span data-stu-id="3a400-496">The tool outputs the results of each of the operations.</span></span>

  - <span data-ttu-id="3a400-497">Si se ejecuta la prueba **AudioVideoEdgeServer**, los resultados de la herramienta son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="3a400-497">If the **AudioVideoEdgeServer** test is performed, the tool outputs are the following:</span></span>
    
      - <span data-ttu-id="3a400-498">Los resultados de prueba de los equipos que proporcionan el servicio de autenticación de audio y vídeo de Lync Server en la topología</span><span class="sxs-lookup"><span data-stu-id="3a400-498">The test results of the computers that provide the Lync Server Audio/Video Authentication service in the topology</span></span>
    
      - <span data-ttu-id="3a400-499">Los resultados de prueba de los equipos que proporcionan el servicio perimetral de audio/vídeo de Lync Server en la topología</span><span class="sxs-lookup"><span data-stu-id="3a400-499">The test results of the computers that provide the Lync Server Audio/Video Edge service in the topology</span></span>

  - <span data-ttu-id="3a400-500">Si se ejecuta la prueba **BandwidthPolicyServer**, los resultados de la herramienta son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="3a400-500">If the **BandwidthPolicyServer** test is performed, the tool outputs are the following:</span></span>
    
      - <span data-ttu-id="3a400-501">Los resultados de prueba de los equipos que proporcionan el servicio de directivas de ancho de banda de Lync Server en la topología</span><span class="sxs-lookup"><span data-stu-id="3a400-501">The test results of the computers that provide the Lync Server Bandwidth Policy Service (Authentication) in the topology</span></span>
    
      - <span data-ttu-id="3a400-502">Los resultados de prueba de los equipos que proporcionan el servicio de directivas de ancho de banda de Lync Server (núcleo) en la topología</span><span class="sxs-lookup"><span data-stu-id="3a400-502">The test results of the computers that provide the Lync Server Bandwidth Policy Service (Core) in the topology</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="3a400-503">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3a400-503">Requirements</span></span>

  - <span data-ttu-id="3a400-504">Esta herramienta debe ejecutarse en un equipo que se encuentre en la topología y que tenga el almacén local.</span><span class="sxs-lookup"><span data-stu-id="3a400-504">This tool must be run from a computer that is in the topology and that has the local store.</span></span>

  - <span data-ttu-id="3a400-505">La herramienta debe ejecutarse como un administrador con acceso al almacén local.</span><span class="sxs-lookup"><span data-stu-id="3a400-505">The tool must be run as an administrator who has access to the local store.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="3a400-506">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="3a400-506">Examples</span></span>

<span data-ttu-id="3a400-507">A continuación se muestra un ejemplo de la entrada de la herramienta.</span><span class="sxs-lookup"><span data-stu-id="3a400-507">The following is an example of the tool input.</span></span>

    MsTurnPing -ServerRole AudioVideoEdgeServer
    
    MsTurnPing -ServerRole BandwidthPolicyServer

</div>

<div>

## <a name="summary"></a><span data-ttu-id="3a400-508">Resumen</span><span class="sxs-lookup"><span data-stu-id="3a400-508">Summary</span></span>

<span data-ttu-id="3a400-509">Esta herramienta puede ser un valioso recurso para los administradores de Lync Server 2013 que desean comprobar el estado de los servidores que ejecutan los servicios de directiva de audio/vídeo y de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="3a400-509">This tool can be a valuable resource to Lync Server 2013 administrators who want to check the status of the servers that are running audio/video and bandwidth policy services.</span></span>

</div>

</div>

<div>

## <a name="network-configuration-viewer"></a><span data-ttu-id="3a400-510">Network Configuration Viewer (Visor de configuración de red</span><span class="sxs-lookup"><span data-stu-id="3a400-510">Network Configuration Viewer</span></span>

<span data-ttu-id="3a400-511">El visor de software de comunicaciones de Microsoft Lync Server 2013 puede usar el visor de configuración de red para obtener una topología de red de control de admisión de llamadas (CAC) para una empresa que se suministra para permitir sesiones de comunicación en tiempo real, como voz o videollamadas basadas en la capacidad de ancho de banda especificada.</span><span class="sxs-lookup"><span data-stu-id="3a400-511">Network Configuration Viewer can be used by Microsoft Lync Server 2013 communications software administrators to view call admission control (CAC) network topology for an enterprise that is provisioned to allow real-time communication sessions, such as voice or video calls based on specified bandwidth capacity.</span></span> <span data-ttu-id="3a400-512">Los administradores de Lync Server 2013 definen directivas CAC, que exigen los servicios de directivas de ancho de banda que se instalan con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3a400-512">Lync Server 2013 administrators define CAC policies, which are enforced by the Bandwidth Policy services that are installed with Lync Server 2013.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="3a400-513">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a400-513">Description</span></span>

<span data-ttu-id="3a400-514">El visor de configuración de red (NetworkConfigurationViewer.exe) permite a los administradores realizar las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="3a400-514">Network Configuration Viewer (NetworkConfigurationViewer.exe) allows administrators to perform the following tasks:</span></span>

  - <span data-ttu-id="3a400-515">Cargue y vea la topología de red CAC desde una implementación de Lync Server 2013 en un formato gráfico.</span><span class="sxs-lookup"><span data-stu-id="3a400-515">Load and view CAC network topology from a Lync Server 2013 deployment in a graphical format.</span></span>

  - <span data-ttu-id="3a400-516">Cargar y ver la topología de red de CAC de un archivo de registro de servidor de directiva de ancho de banda en un formato gráfico.</span><span class="sxs-lookup"><span data-stu-id="3a400-516">Load and view CAC network topology from a Bandwidth Policy Server log file in a graphical format.</span></span>

  - <span data-ttu-id="3a400-517">Guardar y almacenar la topología de red de CAC en formato XML en el disco.</span><span class="sxs-lookup"><span data-stu-id="3a400-517">Save and store CAC network topology in an XML format on the disk.</span></span>

  - <span data-ttu-id="3a400-518">Guardar y almacenar el diagrama de topología de red de CAC en formato JP o BMP.</span><span class="sxs-lookup"><span data-stu-id="3a400-518">Save and store CAC network topology diagram in JPG or BMP format.</span></span>

  - <span data-ttu-id="3a400-519">Ver los datos de configuración de la topología de red de CAC.</span><span class="sxs-lookup"><span data-stu-id="3a400-519">View CAC network topology configuration data.</span></span>

  - <span data-ttu-id="3a400-520">Ver la topología de red de CAC en estilo de vista de árbol.</span><span class="sxs-lookup"><span data-stu-id="3a400-520">View CAC network topology in a tree-view style.</span></span>

  - <span data-ttu-id="3a400-521">Definir conectores personalizados para vínculos de topología de red de CAC (por ejemplo, vínculos de sitio a región, de región a región y de sitio a sitio).</span><span class="sxs-lookup"><span data-stu-id="3a400-521">Define custom connectors for CAC network topology links (for example, site-to-region, region-to-region, and site-to-site links).</span></span>

  - <span data-ttu-id="3a400-522">Ver información de sitio de topología de red de CAC, información de región y directivas de ancho de banda y vínculos de red proporcionados.</span><span class="sxs-lookup"><span data-stu-id="3a400-522">View CAC network topology site information, region Information, and provisioned bandwidth policies and network links.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="3a400-523">Finalidad</span><span class="sxs-lookup"><span data-stu-id="3a400-523">Purpose</span></span>

<span data-ttu-id="3a400-524">Ver vínculos de topología de red de CAC de empresa en una interfaz gráfica.</span><span class="sxs-lookup"><span data-stu-id="3a400-524">View enterprise CAC network topology links in a graphical interface.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="3a400-525">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="3a400-525">Examples</span></span>

<span data-ttu-id="3a400-526">**Cargue y vea la topología de red CAC desde una implementación de Lync Server 2013 en un formato gráfico:** Los administradores de Lync Server 2013 pueden cargar y ver la configuración de topología de red de CAC en cualquier equipo de Lync \*\*\*\* Server 2013, como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="3a400-526">**Load and view CAC network topology from a Lync Server 2013 deployment in a graphical format:** Lync Server 2013 administrators can load and view CAC network topology configuration on any Lync Server 2013 computer by using the **Download Network Configuration** option as shown in the figure below.</span></span> <span data-ttu-id="3a400-527">La herramienta no puede descargar ni ver una configuración de este tipo cuando se implementa en un equipo que no tiene conectividad con el almacén de configuración de Lync.</span><span class="sxs-lookup"><span data-stu-id="3a400-527">The tool will fail to download or view such a configuration when deployed on a computer that does not have connectivity to the Lync configuration store.</span></span>

<span data-ttu-id="3a400-528">![Descargando la configuración de red.] (images/JJ945604.8d126d3f-2545-4f13-a244-974f09614982(OCS.15).jpg "Descargando la configuración de red.")</span><span class="sxs-lookup"><span data-stu-id="3a400-528">![Downloading the network configuration.](images/JJ945604.8d126d3f-2545-4f13-a244-974f09614982(OCS.15).jpg "Downloading the network configuration.")</span></span>

<span data-ttu-id="3a400-529">**Cargar y ver la topología de red de CAC desde un archivo de registro de servidor de directivas de ancho de banda en un formato gráfico:** Servidores de directivas de ancho de banda 2013 de Lync Server guarde la topología de red CAC como parte del mecanismo de registro en la ubicación del recurso compartido de archivos de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3a400-529">**Load and View CAC network topology from a Bandwidth Policy server log file in a graphical format:** Lync Server 2013 Bandwidth Policy servers save the CAC network topology as a part of the logging mechanism under the Lync Server 2013 file share location.</span></span> <span data-ttu-id="3a400-530">Los administradores de Lync Server pueden ver un archivo con formato gráfico con la opción de **configuración de red abierta** , como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="3a400-530">Lync Server administrators can view such a file in a graphical format by using the **Open Network Configuration** option as shown below.</span></span>

<span data-ttu-id="3a400-531">![Abrir un archivo de registro del servidor de directivas de ancho de banda.] (images/JJ945604.3e503e92-aacb-4921-a8d2-23f860fe2df6(OCS.15).jpg "Abrir un archivo de registro del servidor de directivas de ancho de banda.")</span><span class="sxs-lookup"><span data-stu-id="3a400-531">![Opening a Bandwidth Policy Server log file.](images/JJ945604.3e503e92-aacb-4921-a8d2-23f860fe2df6(OCS.15).jpg "Opening a Bandwidth Policy Server log file.")</span></span>

<span data-ttu-id="3a400-532">Guarde y almacene la topología de red de CAC en formato XML en el disco: los administradores de Lync Server 2013 pueden guardar el archivo de configuración de topología de red CAC en formato XML con la opción **guardar una copia de configuración de red** , tal como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="3a400-532">Save and store CAC network topology in an XML format on the disk: Lync Server 2013 administrators can save the CAC network topology configuration file in an XML format by using the **Save a copy of Network Configuration** option as shown below.</span></span> <span data-ttu-id="3a400-533">El archivo de configuración guardado puede utilizarse para ver una representación gráfica en un entorno sin conexión.</span><span class="sxs-lookup"><span data-stu-id="3a400-533">The saved configuration file can then be used offline for graphical viewing purposes.</span></span>

<span data-ttu-id="3a400-534">![Guardar la configuración de red como un archivo XML.] (images/JJ945604.6eeef3b0-78b5-4ee6-8d94-1a4ddf3d8676(OCS.15).jpg "Guardar la configuración de red como un archivo XML.")</span><span class="sxs-lookup"><span data-stu-id="3a400-534">![Saving the network configuration as an XML file.](images/JJ945604.6eeef3b0-78b5-4ee6-8d94-1a4ddf3d8676(OCS.15).jpg "Saving the network configuration as an XML file.")</span></span>

<span data-ttu-id="3a400-535">Guardar y almacenar un diagrama de topología de red de CAC en formato JPG o BMP: los administradores de Lync Server 2013 pueden guardar la configuración de topología de red CAC en un formato gráfico (formatos de archivo JPG y BMP) mediante el **Diagrama guardar configuración de red como imagen** como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="3a400-535">Save and Store CAC network topology diagram in JPG or BMP format: Lync Server 2013 administrators can save the CAC network topology configuration in a graphical format (JPG and BMP file formats) by using the **Save Network Configuration diagram as picture** option as shown below.</span></span>

<span data-ttu-id="3a400-536">![Guardar la configuración de red como una imagen.] (images/JJ945604.145a6fb9-58b1-46b1-bbd5-a661ceba07b4(OCS.15).jpg "Guardar la configuración de red como una imagen.")</span><span class="sxs-lookup"><span data-stu-id="3a400-536">![Saving the network configuration as a picture.](images/JJ945604.145a6fb9-58b1-46b1-bbd5-a661ceba07b4(OCS.15).jpg "Saving the network configuration as a picture.")</span></span>

<span data-ttu-id="3a400-537">**Ver datos de configuración de topología de red CAC:** Los administradores de Lync Server 2013 pueden ver datos de configuración de red relacionados, como regiones de red, sitios de red, perfiles de ancho de banda y direcciones IP de subred de sitio en formato de texto, tal y como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="3a400-537">**View CAC network topology configuration data:** Lync Server 2013 administrators can view related network configuration data such as network regions, network sites, bandwidth profiles, and site subnet IP addresses in a textual format by using the View Network Configuration data option as shown below.</span></span>

<span data-ttu-id="3a400-538">![Visualización de datos de configuración de red.] (images/JJ945604.b72a4c21-a042-4d91-bf96-fcb396af0679(OCS.15).jpg "Visualización de datos de configuración de red.")</span><span class="sxs-lookup"><span data-stu-id="3a400-538">![Viewing network configuration data.](images/JJ945604.b72a4c21-a042-4d91-bf96-fcb396af0679(OCS.15).jpg "Viewing network configuration data.")</span></span>

<span data-ttu-id="3a400-539">**Ver la topología de red CAC en un estilo de vista de árbol:** Los administradores de Lync Server 2013 pueden ver los datos de configuración de red relacionados en un estilo de vista de árbol gráfico mediante el panel de control en el lado izquierdo de la ventana de herramientas, como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="3a400-539">**View CAC network topology in a tree-view style:** Lync Server 2013 administrators can view related network configuration data in a graphical tree view style by using the control panel on the left side of the tool window as shown below.</span></span>

<span data-ttu-id="3a400-540">![Visualización de datos de configuración de red en una vista de árbol.] (images/JJ945604.4d924ac9-fd96-430f-b211-ee35b7ef9a23(OCS.15).jpg "Visualización de datos de configuración de red en una vista de árbol.")</span><span class="sxs-lookup"><span data-stu-id="3a400-540">![Viewing network configuration data in a tree-view.](images/JJ945604.4d924ac9-fd96-430f-b211-ee35b7ef9a23(OCS.15).jpg "Viewing network configuration data in a tree-view.")</span></span>

<span data-ttu-id="3a400-541">**Defina conectores personalizados para los vínculos de topología de red CAC (como vínculos de sitio a región, de región a región y de sitio a sitio):** Los administradores de Lync Server 2013 pueden definir conectores gráficos personalizados para los vínculos WAN de configuración de red CAC con la opción configuración tal como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="3a400-541">**Define custom connectors for CAC network topology links (such as site-to-region, region-to-region, and site-to-site links):** Lync Server 2013 administrators can define custom graphical connectors for CAC network configuration WAN links by using the Settings option as shown below.</span></span> <span data-ttu-id="3a400-542">Esto ayuda a diferenciar entre diferentes tipos de vínculos de red proporcionados en la configuración de red.</span><span class="sxs-lookup"><span data-stu-id="3a400-542">This helps differentiate between various types of network links that are provisioned in the network configuration.</span></span>

<span data-ttu-id="3a400-543">![Definir conectores personalizados para topología de red CAC] (images/JJ945604.b20bea67-c8e1-453e-b1dd-e2aa17b62566(OCS.15).jpg "Definir conectores personalizados para topología de red CAC")</span><span class="sxs-lookup"><span data-stu-id="3a400-543">![Define custom connectors for CAC network topology](images/JJ945604.b20bea67-c8e1-453e-b1dd-e2aa17b62566(OCS.15).jpg "Define custom connectors for CAC network topology")</span></span>

<span data-ttu-id="3a400-544">**Ver la información del sitio de la topología CAC, la información de la región y las directivas de ancho de banda aprovisionado:** Los administradores de Lync Server 2013 pueden ver la información de la región de red CAC, la información del sitio y la información de aprovisionamiento de ancho de banda de CAC usando las opciones que se muestran a continuación.</span><span class="sxs-lookup"><span data-stu-id="3a400-544">**View CAC network topology site information, region information, and provisioned bandwidth policies:** Lync Server 2013 administrators can view related CAC network region information, site information, and CAC bandwidth provisioning information by using options shown below.</span></span> <span data-ttu-id="3a400-545">(Por ejemplo, haga clic en **información** en una región de red o un objeto de sitio de red).</span><span class="sxs-lookup"><span data-stu-id="3a400-545">(For example, click **Info** in a network region or network site object.)</span></span>

<span data-ttu-id="3a400-546">![Definir conectores personalizados para su red.] (images/JJ945604.26262c75-4342-41c3-bc98-1793aa6a7713(OCS.15).jpg "Definir conectores personalizados para su red.")</span><span class="sxs-lookup"><span data-stu-id="3a400-546">![Defining custom connectors for your network.](images/JJ945604.26262c75-4342-41c3-bc98-1793aa6a7713(OCS.15).jpg "Defining custom connectors for your network.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="3a400-547">Resumen</span><span class="sxs-lookup"><span data-stu-id="3a400-547">Summary</span></span>

<span data-ttu-id="3a400-548">Esta herramienta puede ser un valioso recurso para los administradores de Lync Server 2013 que desean ver la topología de red CAC para su implementación en un formato gráfico.</span><span class="sxs-lookup"><span data-stu-id="3a400-548">This tool can be a valuable resource to Lync Server 2013 administrators who would like to view CAC network topology for their deployment in a graphical format.</span></span>

</div>

</div>

<div>

## <a name="response-group-agent-live"></a><span data-ttu-id="3a400-549">Response Group Agent Live (Información en vivo del agente del grupo de respuesta)</span><span class="sxs-lookup"><span data-stu-id="3a400-549">Response Group Agent Live</span></span>

<span data-ttu-id="3a400-550">La aplicación de grupo de respuesta permite a los agentes acceder en tiempo real a información útil mediante el servicio web integrado.</span><span class="sxs-lookup"><span data-stu-id="3a400-550">The Response Group application gives agents the ability to access useful real-time information using its built-in Web service.</span></span> <span data-ttu-id="3a400-551">Desafortunadamente, no hay disponible una vista gráfica de estos datos fuera de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3a400-551">Unfortunately, no graphical view of this data is available outside the application.</span></span> <span data-ttu-id="3a400-552">La herramienta del kit de recursos del agente de grupo de respuesta soluciona este problema proporcionando una forma sencilla y gráfica para acceder a esta información, mejorada con información sobre el software de comunicaciones de Microsoft Lync 2013 en tiempo real, como la presencia de otros agentes.</span><span class="sxs-lookup"><span data-stu-id="3a400-552">The Response Group Agent Live Resource Kit tool solves this issue by providing a simple and graphical way to access this information, enhanced with real-time Microsoft Lync 2013 communications software information such as the presence of other agents.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="3a400-553">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a400-553">Description</span></span>

<span data-ttu-id="3a400-554">Response Group Agent Live es una aplicación para Windows que proporciona funciones de inicio y cierre de sesión, así como determinada información en tiempo real (como pertenencia a grupo y número actual de llamadas) a los agentes del grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="3a400-554">Response Group Agent Live is a Windows application that provides sign-in and sign-out functionality and some real-time information (such as group membership and current number of calls) to Response Group agents.</span></span> <span data-ttu-id="3a400-555">Está pensado para ser una versión mejorada de la página grupos de agentes (accesible desde Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="3a400-555">It is meant to be an enhanced version of the Agent Groups page (accessible from Lync 2013.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="3a400-556">Finalidad</span><span class="sxs-lookup"><span data-stu-id="3a400-556">Purpose</span></span>

<span data-ttu-id="3a400-p165">La aplicación de grupo de respuesta envía las llamadas entrantes a una cola y, a continuación, las redirige a grupos de agentes. Para poder tomar decisiones fundamentadas sobre las llamadas que deben atenderse, los agentes pueden acceder a información en tiempo real sobre sus grupos de agentes, como los agentes disponibles y el número de llamadas que espera en cada cola. Esta información, inicialmente accesible solo mediante el servicio de grupo de respuesta, es facilitada de forma intuitiva por la herramienta Response Group Agent Live.</span><span class="sxs-lookup"><span data-stu-id="3a400-p165">The Response Group application queues incoming calls, and then routes them to agent groups. To make informed decisions about which calls to service, agents can access real-time information about their agent groups, such as what other agents are available and how many calls are waiting in each queue. This information, initially accessible only through the Response Group service, is made available in an intuitive way by Response Group Agent Live.</span></span>

<div>

## <a name="features"></a><span data-ttu-id="3a400-560">Características</span><span class="sxs-lookup"><span data-stu-id="3a400-560">Features</span></span>

<span data-ttu-id="3a400-561">La herramienta agente de grupo de respuesta está integrada en el servicio de grupo de respuesta y en el SDK de Microsoft Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="3a400-561">The Response Group Agent Live tool is built on the Response Group service and the Microsoft Lync 2013 SDK.</span></span> <span data-ttu-id="3a400-562">Proporciona a los agentes de grupo de respuesta la información y las funciones disponibles del servicio de grupo de respuesta (como pertenencia a grupo, presencia de otros agentes y número de llamadas en espera).</span><span class="sxs-lookup"><span data-stu-id="3a400-562">It provides Response Group agents the information and capabilities that are available from the Response Group service (such as group membership, presence of other agents, and number of waiting calls).</span></span>

<span data-ttu-id="3a400-563">En la ilustración siguiente se muestra la interfaz principal de la herramienta Response Group Agent Live.</span><span class="sxs-lookup"><span data-stu-id="3a400-563">The figure below illustrates the main interface of Response Group Agent Live.</span></span>

<span data-ttu-id="3a400-564">![La herramienta agente de grupo de respuesta.] (images/JJ945604.63cb0374-a6ef-4a59-b60e-bec86a880d09(OCS.15).jpg "La herramienta agente de grupo de respuesta.")</span><span class="sxs-lookup"><span data-stu-id="3a400-564">![The Response Group Agent Live tool.](images/JJ945604.63cb0374-a6ef-4a59-b60e-bec86a880d09(OCS.15).jpg "The Response Group Agent Live tool.")</span></span>

<span data-ttu-id="3a400-565">Las tres características principales que aparecen a continuación están disponibles para los agentes en Response Group Agent Live:</span><span class="sxs-lookup"><span data-stu-id="3a400-565">The following three main features are available for agents in Response Group Agent Live:</span></span>

  - <span data-ttu-id="3a400-566">**Iniciar y cerrar sesión:** En oposición a la página de grupos de agentes (accesible desde Lync 2013), el agente de grupo de respuesta permite que solo los agentes inicien sesión o salgan de todos los grupos de agentes a la vez.</span><span class="sxs-lookup"><span data-stu-id="3a400-566">**Sign-in/out:** Contrary to the Agent Groups page (accessible from Lync 2013), Response Group Agent Live allows only agents to sign-in or out of all agent groups at once.</span></span> <span data-ttu-id="3a400-567">Esta aplicación proporciona tres formas rápidas para que los agentes inicien sesión o salgan:</span><span class="sxs-lookup"><span data-stu-id="3a400-567">This application provides three quick ways for agents to sign in or out:</span></span>
    
      - <span data-ttu-id="3a400-568">Hacer clic en los botones de inicio y cierre de sesión (verde y rojo) en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3a400-568">Click the Sign-in/out (green and red) buttons within the application.</span></span>
    
      - <span data-ttu-id="3a400-569">Hacer clic en el icono de la bandeja del sistema y seleccionar iniciar sesión o cerrar sesión.</span><span class="sxs-lookup"><span data-stu-id="3a400-569">Right-click the system tray icon, and select sign in or sign out.</span></span>
    
      - <span data-ttu-id="3a400-570">Usar los métodos abreviados de teclado configurables.</span><span class="sxs-lookup"><span data-stu-id="3a400-570">Using configurable keyboard shortcuts.</span></span>

  - <span data-ttu-id="3a400-571">**Pertenencia a grupos:** Cuando se selecciona un grupo de agentes, el agente de grupo de respuesta muestra la lista de agentes en este grupo en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="3a400-571">**Group membership:** When an agent group is selected, Response Group Agent Live displays the list of agents in this group in the right pane.</span></span> <span data-ttu-id="3a400-572">Si Lync 2013 se está ejecutando en el mismo equipo que esta aplicación, la información de presencia y la tarjeta de contacto se muestran en el grupo de respuesta Agent Live.</span><span class="sxs-lookup"><span data-stu-id="3a400-572">If Lync 2013 is running on the same computer as this application, presence information and the contact card are displayed in the Response Group Agent Live.</span></span> <span data-ttu-id="3a400-573">Los agentes pueden enviar un mensaje instantáneo o llamar a otros agentes directamente desde allí.</span><span class="sxs-lookup"><span data-stu-id="3a400-573">Agents can send an IM or call other agents directly from there.</span></span>

  - <span data-ttu-id="3a400-p169">**Estadísticas en tiempo real:** Response Group Agent Live proporciona estadísticas en tiempo real para todos los grupos de agentes. La frecuencia de actualización es de un minuto. Cuando un grupo de respuesta responde a una llamada, se añade un indicador visual junto al nombre del grupo con el número actual de llamadas en cola. Al detener el puntero sobre un grupo, también se muestra el tiempo de espera más largo.</span><span class="sxs-lookup"><span data-stu-id="3a400-p169">**Real-time statistics:** Response Group Agent Live provides real-time statistics for all agent groups. The update frequency is one minute. When a call is answered by a Response Group, a visual indicator is added next to the group name with the current number of queued calls. Pausing the pointer over a group also displays the longest waiting time.</span></span>

</div>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="3a400-578">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3a400-578">Requirements</span></span>

<span data-ttu-id="3a400-579">Response Group Agent Live requiere .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="3a400-579">Response Group Agent Live requires the .NET Framework 4.0.</span></span> <span data-ttu-id="3a400-580">Además, para aprovechar las características de presencia y tarjeta de contacto, Lync 2013 debe estar instalado de forma local (y estar en ejecución).</span><span class="sxs-lookup"><span data-stu-id="3a400-580">In addition, to take advantage of the presence and contact card features, Lync 2013 must be installed locally (and be running).</span></span>

<div>

## <a name="configuration"></a><span data-ttu-id="3a400-581">Configuración</span><span class="sxs-lookup"><span data-stu-id="3a400-581">Configuration</span></span>

<span data-ttu-id="3a400-p171">Response Group Agent Live puede personalizarse según preferencias individuales mediante el cuadro de diálogo de opciones de la aplicación. Además, el administrador puede definir la dirección de host predeterminada al editar directamente la propiedad defaultHostAddress del archivo RGAgentLive.exe.config.</span><span class="sxs-lookup"><span data-stu-id="3a400-p171">Response Group Agent Live can be customized to individual preferences by using the Options dialog box in the application. In addition, the administrator can define the default host address by editing directly the defaultHostAddress property of the RGAgentLive.exe.config file.</span></span>

<span data-ttu-id="3a400-p172">En la ilustración siguiente se muestra el cuadro de diálogo de opciones que los agentes pueden usar para configurar la dirección de host y las teclas de método abreviado. Para acceder a este cuadro de diálogo, haga clic en el botón Opciones de la parte superior derecha de la interfaz principal.</span><span class="sxs-lookup"><span data-stu-id="3a400-p172">The figure below illustrates the Options dialog box that agents can use to configure the host address and shortcut keys. This dialog is accessed by clicking the Options button on the top right of the main interface.</span></span>

<span data-ttu-id="3a400-586">![Cuadro de diálogo Opciones del agente de grupo de respuesta.] (images/JJ945604.3cc15e29-8699-45ab-90c3-e1565fa6ebf6(OCS.15).jpg "Cuadro de diálogo Opciones del agente de grupo de respuesta.")</span><span class="sxs-lookup"><span data-stu-id="3a400-586">![The Response Group Agent Live Options dialog box.](images/JJ945604.3cc15e29-8699-45ab-90c3-e1565fa6ebf6(OCS.15).jpg "The Response Group Agent Live Options dialog box.")</span></span>

<span data-ttu-id="3a400-587">Las tres opciones siguientes pueden personalizarse en la configuración de Response Group Agent Live:</span><span class="sxs-lookup"><span data-stu-id="3a400-587">The following three different settings can be customized in the Response Group Agent Live configuration:</span></span>

  - <span data-ttu-id="3a400-p173">Dirección de host: suele ser el FQDN del grupo web que pertenece al grupo de servidores principales del agente. La dirección exacta del servicio de grupo de respuesta se obtiene automáticamente en segundo plano a partir de esta información (al añadir la ruta de acceso correcta después del host).</span><span class="sxs-lookup"><span data-stu-id="3a400-p173">Host address: This is typically the web pool FQDN belonging to the agent’s home pool. The exact Response Group service address is automatically derived in the background from this information (by appending the right path after the host).</span></span>

  - <span data-ttu-id="3a400-p174">Métodos abreviados de teclado: los métodos abreviados de teclado exactos para iniciar/cerrar sesión se pueden personalizar. La única limitación es que ambos deben contener la tecla del logotipo de Windows (además de al menos otra tecla).</span><span class="sxs-lookup"><span data-stu-id="3a400-p174">Shortcuts: The exact shortcuts to sign-in/out can be customized. The only limitation is that both shortcuts must contain the “Windows Logo” key (in addition to at least another key).</span></span>

  - <span data-ttu-id="3a400-592">Iniciar con Windows: la aplicación puede configurarse para iniciarse automáticamente con Windows.</span><span class="sxs-lookup"><span data-stu-id="3a400-592">Start with Windows: The application can be configured to start automatically with Windows.</span></span>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="3a400-593">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="3a400-593">Examples</span></span>

<span data-ttu-id="3a400-594">En la ilustración siguiente se muestra cómo llamar o enviar un mensaje instantáneo a otro agente; para ello es necesario hacer clic con el botón derecho en el contacto del panel derecho.</span><span class="sxs-lookup"><span data-stu-id="3a400-594">The figure below illustrates how to call or send an IM to another agent by right-clicking the contact in the right pane.</span></span>

<span data-ttu-id="3a400-595">![Hacer una llamada o enviar un mensaje instantáneo.] (images/JJ945604.009cebe0-5a93-4745-89c3-8a16c7c13009(OCS.15).jpg "Hacer una llamada o enviar un mensaje instantáneo.")</span><span class="sxs-lookup"><span data-stu-id="3a400-595">![Making a call or sending an IM.](images/JJ945604.009cebe0-5a93-4745-89c3-8a16c7c13009(OCS.15).jpg "Making a call or sending an IM.")</span></span>

<span data-ttu-id="3a400-596">En la ilustración siguiente aparece cómo Response Group Agent Live muestra el número de llamadas en la cola y el tiempo de espera más largo de todas las llamadas entrantes.</span><span class="sxs-lookup"><span data-stu-id="3a400-596">The figure below illustrates how Response Group Agent Live displays the current number of calls in the queue and the longest waiting time among all these incoming calls.</span></span>

<span data-ttu-id="3a400-597">![Ver información de la cola.] (images/JJ945604.131d7f79-b7ed-41f5-a9da-ffc556e31037(OCS.15).jpg "Ver información de la cola.")</span><span class="sxs-lookup"><span data-stu-id="3a400-597">![Viewing queue information.](images/JJ945604.131d7f79-b7ed-41f5-a9da-ffc556e31037(OCS.15).jpg "Viewing queue information.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="3a400-598">Resumen</span><span class="sxs-lookup"><span data-stu-id="3a400-598">Summary</span></span>

<span data-ttu-id="3a400-599">Inicio y cierre de sesión rápidos, pertenencia a grupos y estadísticas básicas en tiempo real son algunas de las características interesantes del agente del grupo de respuesta que solo están disponibles fuera de la aplicación del servicio de grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="3a400-599">Fast sign-in and sign-out, group membership, and basic real-time statistics are interesting Response Group agent features that are only available outside the application from the Response Group service.</span></span> <span data-ttu-id="3a400-600">Con la herramienta del kit de recursos del agente de grupo de respuesta, los administradores de Lync pueden proporcionar a sus agentes una aplicación de Windows que les permita realizar tareas de forma más rápida y gráfica.</span><span class="sxs-lookup"><span data-stu-id="3a400-600">With the Response Group Agent Live Resource Kit tool, Lync administrators can provide their agents with a Windows application that allows them to perform tasks in a faster and graphical way.</span></span>

</div>

</div>

<div>

## <a name="sefautil"></a><span data-ttu-id="3a400-601">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="3a400-601">SEFAUtil</span></span>

<span data-ttu-id="3a400-602">SEFAUtil (la activación de características de extensión secundaria) es una herramienta de línea de comandos que permite a los administradores de software de comunicaciones de Microsoft Lync Server 2013 y a los agentes del Departamento de soporte técnico configurar el timbre delegado, el desvío de llamadas, las llamadas simultáneas, la llamada de equipo configuración y recogida de llamadas grupales en nombre de un usuario de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3a400-602">SEFAUtil (secondary extension feature activation) is a command-line tool that enables Microsoft Lync Server 2013 communications software administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Lync Server 2013 user.</span></span> <span data-ttu-id="3a400-603">La herramienta también permite a los administradores consultar la configuración de enrutamiento de llamadas publicada para un usuario en particular. La herramienta SEFAUtil permite al administrador habilitar/deshabilitar/modificar el desvío de llamadas o el timbre simultáneo en nombre del usuario.</span><span class="sxs-lookup"><span data-stu-id="3a400-603">The tool also allows administrators to query the call-routing settings that are published for a particular user.The SEFAUtil tool allows the administrator to enable/disable/modify call forwarding or simultaneously ringing on behalf of the user.</span></span> <span data-ttu-id="3a400-604">El administrador puede especificar el destino (en forma de URI del SIP) o usar un destino ya publicado por el usuario.</span><span class="sxs-lookup"><span data-stu-id="3a400-604">The administrator can specify the target (in the form of a SIP URI) or use a target that has already been published by the user.</span></span> <span data-ttu-id="3a400-605">Esta herramienta también permite a los administradores agregar o quitar delegados o miembros del grupo de llamada de equipo en nombre del usuario. Esta herramienta está integrada en la API administrada de comunicaciones unificadas de Microsoft (UCMA) 3,0 y requiere que los administradores creen una aplicación de confianza en el almacén de administración central para SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="3a400-605">This tool also allows administrators to add or remove delegates or team-call group members on behalf of the user.This tool is built on Microsoft Unified Communications Managed API (UCMA) 3.0 and requires that administrators create a trusted application in the Central Management store for SEFAUtil</span></span>

<span data-ttu-id="3a400-606">SEFAUtil (la activación de características de extensión secundaria) permite a los administradores y los agentes del servicio de asistencia de Lync Server 2013 configurar la llamada de delegación, el desvío de llamadas, las llamadas simultáneas, la configuración de llamada de equipo y la recogida de llamadas de grupo en nombre de un usuario de Lync Server 2013 .</span><span class="sxs-lookup"><span data-stu-id="3a400-606">SEFAUtil (secondary extension feature activation) enables Lync Server 2013 administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Lync Server 2013 user.</span></span> <span data-ttu-id="3a400-607">Esta herramienta también permite a los administradores consultar la configuración de enrutamiento de llamadas que se haya publicado para un usuario concreto.</span><span class="sxs-lookup"><span data-stu-id="3a400-607">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="3a400-608">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a400-608">Description</span></span>

<span data-ttu-id="3a400-609">La versión actual de SEFAUtil es tan solo una herramienta de línea de comandos; no dispone de una interfaz gráfica de usuario.</span><span class="sxs-lookup"><span data-stu-id="3a400-609">The current version of SEFAUtil is only a command-line tool; there is no supporting graphical user interface.</span></span> <span data-ttu-id="3a400-610">Esta herramienta se basa en la API administrada de Microsoft Unified Communications (UCMA) 3,0.</span><span class="sxs-lookup"><span data-stu-id="3a400-610">This tool is based on Microsoft Unified Communications Managed API (UCMA) 3.0.</span></span> <span data-ttu-id="3a400-611">Las características de esta herramienta permiten a los administradores y agentes del departamento de soporte técnico realizar las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="3a400-611">The features in this tool allow administrators and helpdesk agents to do the following:</span></span>

  - <span data-ttu-id="3a400-612">Ver todas las opciones de configuración de enrutamiento de llamadas para un usuario (incluidos el desvío de llamadas, la delegación, llamadas simultáneas, llamadas de equipo y respuestas de llamada de grupo)</span><span class="sxs-lookup"><span data-stu-id="3a400-612">View all call routing settings for a user (includes call-forwarding, delegation, simultaneous ringing, team-call and group call pickup)</span></span>

  - <span data-ttu-id="3a400-613">Habilitar/deshabilitar/modificar la configuración del desvío de llamadas (incluidos el destino y el temporizador de llamadas sin respuesta)</span><span class="sxs-lookup"><span data-stu-id="3a400-613">Enable/disable/modify call-forwarding setting (includes destination and no-answer timer)</span></span>

  - <span data-ttu-id="3a400-614">Habilitar/deshabilitar/modificar las configuraciones inmediatas de desvío de llamadas</span><span class="sxs-lookup"><span data-stu-id="3a400-614">Enable/disable/modify call-forwarding immediate configurations</span></span>

  - <span data-ttu-id="3a400-615">Habilitar/deshabilitar/modificar la configuración de delegación</span><span class="sxs-lookup"><span data-stu-id="3a400-615">Enable/disable/modify delegation settings</span></span>

  - <span data-ttu-id="3a400-616">Habilitar/deshabilitar/modificar la configuración de grupo de llamada de equipo</span><span class="sxs-lookup"><span data-stu-id="3a400-616">Enable/disable/modify team-call group settings</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3a400-617">Novedades de la herramienta SEFAUtil de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3a400-617">New in Lync Server 2013 SEFAUtil tool</span></span>

    
    </div>

  - <span data-ttu-id="3a400-618">Habilitar/deshabilitar/modificar la configuración de llamadas simultáneas (incluido el destino)</span><span class="sxs-lookup"><span data-stu-id="3a400-618">Enable/disable/modify simultaneous ringing settings (includes destination)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3a400-619">Novedades de la herramienta SEFAUtil de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3a400-619">New in Lync Server 2013 SEFAUtil tool</span></span>

    
    </div>

  - <span data-ttu-id="3a400-620">Habilitar/deshabilitar/modificar la configuración de respuesta a llamada grupal</span><span class="sxs-lookup"><span data-stu-id="3a400-620">Enable/disable/modify group call pickup settings</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="3a400-621">Novedades de la herramienta SEFAUtil de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3a400-621">New in Lync Server 2013 SEFAUtil tool</span></span>

    
    </div>

<span data-ttu-id="3a400-622">Esta herramienta tiene las limitaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="3a400-622">This tool has the following limitations:</span></span>

  - <span data-ttu-id="3a400-623">Compatible solo para usuarios alojados en un grupo de servidores de Lync</span><span class="sxs-lookup"><span data-stu-id="3a400-623">Supported only for users homed in a Lync Server pool</span></span>

  - <span data-ttu-id="3a400-624">No admite la edición en masa de las opciones de configuración de enrutamiento de llamadas para varios usuarios</span><span class="sxs-lookup"><span data-stu-id="3a400-624">Bulk-edit of call routing settings for several users is not supported</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="3a400-625">Salida</span><span class="sxs-lookup"><span data-stu-id="3a400-625">Output</span></span>

<span data-ttu-id="3a400-p179">La versión actual de esta herramienta solo ofrece resultados en la ventana del símbolo del sistema. Para obtener más información, consulte la sección Ejemplos más adelante en este documento.</span><span class="sxs-lookup"><span data-stu-id="3a400-p179">The current version of this tool provides output only in the Command Prompt window. For details, see the Examples section later in this document.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="3a400-628">Finalidad</span><span class="sxs-lookup"><span data-stu-id="3a400-628">Purpose</span></span>

<span data-ttu-id="3a400-629">A continuación se describen algunos de los escenarios donde puede utilizarse esta herramienta:</span><span class="sxs-lookup"><span data-stu-id="3a400-629">Following are some of the key scenarios where this tool may be used:</span></span>

  - <span data-ttu-id="3a400-630">Bob es ejecutivo y se ha movido a la telefonía de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3a400-630">Bob is an executive and has been moved to Lync Server telephony.</span></span> <span data-ttu-id="3a400-631">Ha configurado la delegación en su sistema PBX existente.</span><span class="sxs-lookup"><span data-stu-id="3a400-631">He has delegation on his existing PBX system.</span></span> <span data-ttu-id="3a400-632">Como parte del movimiento a Lync, el administrador puede configurar el enrutamiento de Bob para que refleje la configuración de delegación preexistente.</span><span class="sxs-lookup"><span data-stu-id="3a400-632">As part of the move to Lync, the administrator is able to configure Bob’s routing to reflect his pre-existing delegation configuration.</span></span>

  - <span data-ttu-id="3a400-p181">Alicia está de viaje y se da cuenta de que está esperando una llamada importante de uno de sus clientes. Sin embargo, está en un hotel y no tiene acceso a un PC. Entonces, llama al departamento de soporte técnico y solicita que se desvíen a su número de teléfono móvil todas las llamadas realizadas a su número de trabajo. El personal de soporte técnico puede realizar la configuración en su nombre.</span><span class="sxs-lookup"><span data-stu-id="3a400-p181">Alice is travelling and realizes that she is expecting an important call from one of her customers. However, she is in a hotel and has no access to a computer. She calls the helpdesk and requests that they forward to her mobile number all the calls made to her work number. The helpdesk personnel are able to do the configuration on her behalf.</span></span>

  - <span data-ttu-id="3a400-p182">Las llamadas de Jorge a su número de trabajo están desviadas a su correo de voz del teléfono móvil cuando está en el trabajo; sin embargo, en el resto de ubicaciones todo parece funcionar correctamente. El agente de soporte técnico puede ver la configuración de enrutamiento de Jorge y descubre que ha configurado las llamadas simultáneas a su teléfono móvil. El técnico pregunta a Jorge acerca de la cobertura móvil en su oficina y determina que la regla de llamadas simultáneas es lo que está causando que las llamadas vayan al correo de voz del teléfono móvil de Jorge cuando la cobertura de la red es insuficiente.</span><span class="sxs-lookup"><span data-stu-id="3a400-p182">Joe’s calls to his work number are going to his mobile voicemail whenever he is at work; however, things appear to be working correctly in most other locations. The helpdesk technician is able to view Joe’s routing configuration and discovers that Joe has simultaneous ringing configured to his mobile phone. The technician asks Joe about the mobile coverage at his office and is able to determine that the simultaneous ringing rule is what is causing the calls to go to Joe’s mobile voicemail when his network coverage is poor.</span></span>

  - <span data-ttu-id="3a400-640">Mike es un nuevo empleado de Contoso y se ha unido a un nuevo equipo en el que todos los miembros están configurados para la llamada de equipo, cuando está habilitado para Microsoft Lync, el administrador puede establecer la configuración del grupo de llamada de equipo para incluir a todos los nuevos miembros del equipo, además, el el administrador agrega Mike como miembro del grupo de llamada de equipo para cada uno de los miembros de su equipo.</span><span class="sxs-lookup"><span data-stu-id="3a400-640">Mike is a new employee at Contoso and he’s joining a new team on which all members are configured for team-call, when being enabled for Microsoft Lync, the administrator is able to set his team-call group settings to include all his new team members, additionally, the administrator adds Mike as a team-call group member for each of the members in his team.</span></span>

  - <span data-ttu-id="3a400-641">Uno de los procedimientos de atención al cliente en el departamento de recursos humanos de Contoso es proporcionar personal de servicio para todos los autores de llamadas desde la primera llamada.</span><span class="sxs-lookup"><span data-stu-id="3a400-641">A customer service practice in the human resources department at Contoso is to provide personal service for all callers since the first call.</span></span> <span data-ttu-id="3a400-642">Debido a que todos los miembros del departamento se sientan muy cerca unos de otros, tener todos los teléfonos sonando de forma simultánea con llamadas de equipo es muy molesto para el equipo.</span><span class="sxs-lookup"><span data-stu-id="3a400-642">Given that all members of the department sit very close to each other, having all phones ringing at the same time with team-call is very disruptive for the team.</span></span> <span data-ttu-id="3a400-643">Para proporcionar el mejor servicio sin interrumpir a los miembros del equipo, el administrador de Lync aprovecha la capacidad de recogida de llamadas grupales.</span><span class="sxs-lookup"><span data-stu-id="3a400-643">To provide the best service without disrupting the team members, the Lync administrator takes advantage of the Group Call Pickup capability.</span></span> <span data-ttu-id="3a400-644">El administrador agrega a todos los miembros del departamento al número de respuesta.</span><span class="sxs-lookup"><span data-stu-id="3a400-644">The administrator adds all department members to a pickup group and communicates to the department the pickup group number.</span></span> <span data-ttu-id="3a400-645">Cuando Sandra no está en su escritorio, Jorge se da cuenta de que suena el teléfono de Sandra y responde a la llamada desde su escritorio.</span><span class="sxs-lookup"><span data-stu-id="3a400-645">When Samantha is absent from her desk, Joe notices her phone ringing and he proceeds to answer the call from his desk.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="3a400-646">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3a400-646">Requirements</span></span>

<span data-ttu-id="3a400-p184">La herramienta SEFAUtil solo puede ejecutarse desde un equipo que forme parte de un grupo de aplicaciones de confianza. UCMA 3.0 debe instalarse en dicho equipo. Para ejecutar la herramienta es necesario crear un id. de aplicación de SEFAUtil en el grupo.</span><span class="sxs-lookup"><span data-stu-id="3a400-p184">The SEFAUtil tool can be run only on a computer that is a part of a Trusted Application Pool. UCMA 3.0 must be installed on that computer. To run the tool, a new Trusted Application with the SEFAUtil application ID must be created on that pool.</span></span>

<span data-ttu-id="3a400-650">**Crear una nueva aplicación de confianza para la herramienta SEFAUtil**</span><span class="sxs-lookup"><span data-stu-id="3a400-650">**Creating a new Trusted Application for the SEFAUtil tool**</span></span>

1.  <span data-ttu-id="3a400-651">La herramienta SEFAUTil solo puede ejecutarse en un equipo que pertenezca a un grupo de aplicaciones de confianza.</span><span class="sxs-lookup"><span data-stu-id="3a400-651">The SEFAUTil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="3a400-652">Si es necesario, se puede Agregar un grupo como un nuevo grupo de aplicaciones de confianza mediante el shell de administración de Lync Server con el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3a400-652">If needed, adding a pool as a new trusted application pool can be done via the Lync Server Management Shell with the following cmdlet:</span></span>
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3a400-653">UCMA 3.0 debe estar instalado en todos los equipos que se utilicen para ejecutar la herramienta SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="3a400-653">UCMA 3.0 must be installed on any computer that will be used to run the SEFAUtil tool.</span></span>

    
    </div>

2.  <span data-ttu-id="3a400-654">Es necesario definir una aplicación de confianza en la topología para la herramienta SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="3a400-654">A trusted application needs to be defined in the topology for the SEFAUtil tool.</span></span> <span data-ttu-id="3a400-655">Para definir SEFAUtil como una nueva aplicación de confianza, use el shell de administración de Lync Server y ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3a400-655">To define SEFAUtil as a new trusted application, use the Lync Server Management Shell and execute the following cmdlet:</span></span>
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3a400-656">Si fuera necesario, puede utilizarse un puerto distinto.</span><span class="sxs-lookup"><span data-stu-id="3a400-656">A different port can be used if needed.</span></span>

    
    </div>

3.  <span data-ttu-id="3a400-657">Es necesario habilitar los cambios de topología.</span><span class="sxs-lookup"><span data-stu-id="3a400-657">The topology changes need to be enabled.</span></span> <span data-ttu-id="3a400-658">La habilitación de los cambios de topología se puede realizar mediante el shell de administración de Lync Server ejecutando el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3a400-658">Enabling the topology changes can be done via the Lync Server Management Shell by executing the following cmdlet:</span></span>
    
        Enable-CsToplogy

4.  <span data-ttu-id="3a400-659">Si es necesario, instale las herramientas del kit de recursos de Lync Server 2013 en el servidor que se usará para ejecutar la herramienta SEFAUtil (el servidor debe formar parte de un grupo de aplicaciones de confianza).</span><span class="sxs-lookup"><span data-stu-id="3a400-659">If needed, install the Lync Server 2013 Resource Kit Tools in the server that will be used to run the SEFAUtil tool (the server must be part of a trusted application pool).</span></span>

5.  <span data-ttu-id="3a400-660">Compruebe si SEFAUtil se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="3a400-660">Verify the SEFAUtil is running correctly.</span></span> <span data-ttu-id="3a400-661">Para ello, ejecute la herramienta desde un símbolo del sistema de Windows con privilegios de administrador para mostrar la configuración de desvío de llamadas de un usuario en la implementación.</span><span class="sxs-lookup"><span data-stu-id="3a400-661">To do this, run the tool from a windows command prompt with administrator privileges to display the call forwarding settings of a user in the deployment.</span></span> <span data-ttu-id="3a400-662">De forma predeterminada, la herramienta se ubicará en: "... \\Archivos\\de programa Microsoft Lync Server\\2013 reskit ".</span><span class="sxs-lookup"><span data-stu-id="3a400-662">By default the tool will be located in: “…\\Program Files\\Microsoft Lync Server 2013\\Reskit”.</span></span> <span data-ttu-id="3a400-663">Para mostrar la configuración de desvío de llamadas de un usuario, utilice el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="3a400-663">To display the call forwarding settings of a user, use the following command:</span></span>
    
        SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
    
    <span data-ttu-id="3a400-664">Se mostrará la configuración de desvío de llamadas del usuario.</span><span class="sxs-lookup"><span data-stu-id="3a400-664">The call forwarding settings of the user should be displayed.</span></span>

<div>

## <a name="group-call-pickup"></a><span data-ttu-id="3a400-665">Respuesta de llamadas grupales</span><span class="sxs-lookup"><span data-stu-id="3a400-665">Group Call Pickup</span></span>

<span data-ttu-id="3a400-666">La recogida de llamadas grupales requiere una configuración adicional en Lync Server para poder habilitarla por completo.</span><span class="sxs-lookup"><span data-stu-id="3a400-666">Group Call Pickup requires additional configuration in Lync Server for the capability to be fully enabled.</span></span> <span data-ttu-id="3a400-667">Antes de asignar grupos de respuesta a los usuarios, consulte los pasos de planificación e implementación de esta función en la documentación del producto de respuesta de llamadas grupales.</span><span class="sxs-lookup"><span data-stu-id="3a400-667">Before assigning pickup groups to users, refer to the Group Call Pickup product documentation for the planning and deployment steps of this capability.</span></span>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="3a400-668">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="3a400-668">Examples</span></span>

<div>

## <a name="display-current-call-handling-settings"></a><span data-ttu-id="3a400-669">Mostrar la configuración administración de llamadas actual</span><span class="sxs-lookup"><span data-stu-id="3a400-669">Display Current Call Handling Settings</span></span>

<span data-ttu-id="3a400-670">El comando siguiente muestra la administración de llamadas para el usuario.</span><span class="sxs-lookup"><span data-stu-id="3a400-670">The following command displays the call handling for the user.</span></span> `SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com`

<div>


> [!NOTE]  
> <span data-ttu-id="3a400-671">En este ejemplo se usa el modificador <STRONG>/Server</STRONG> para especificar el servidor de Lync al que se conectará.</span><span class="sxs-lookup"><span data-stu-id="3a400-671">This example uses the <STRONG>/server</STRONG> switch to specify the Lync Server to connect to.</span></span>



</div>

<span data-ttu-id="3a400-672">**Salida**</span><span class="sxs-lookup"><span data-stu-id="3a400-672">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:20
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-call-forwardno-answer-destination"></a><span data-ttu-id="3a400-673">Establecer el desvío de llamadas/destino sin respuesta</span><span class="sxs-lookup"><span data-stu-id="3a400-673">Set the Call Forward/No Answer Destination</span></span>

<span data-ttu-id="3a400-674">En este ejemplo se establece el desvío de llamadas/destino sin respuesta y la demora de timbre.</span><span class="sxs-lookup"><span data-stu-id="3a400-674">This example sets the call forward/no answer destination and the ring delay.</span></span> <span data-ttu-id="3a400-675">Aquí no se proporciona el modificador/Server; SEFAUtil intenta descubrir la detección automática del servidor de Lync.</span><span class="sxs-lookup"><span data-stu-id="3a400-675">Here, the /server switch is not provided; SEFAUtil attempts to autodiscover the Lync Server.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone

<span data-ttu-id="3a400-676">**Salida**</span><span class="sxs-lookup"><span data-stu-id="3a400-676">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="enable-call-forwarding-immediately"></a><span data-ttu-id="3a400-677">Habilitar desvío de llamadas inmediatamente</span><span class="sxs-lookup"><span data-stu-id="3a400-677">Enable Call Forwarding Immediately</span></span>

<span data-ttu-id="3a400-678">En este ejemplo se habilita el desvío de llamadas inmediatamente a otro usuario.</span><span class="sxs-lookup"><span data-stu-id="3a400-678">This example immediately enables call-forwarding to another user.</span></span>

    SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com

<span data-ttu-id="3a400-679">**Salida**</span><span class="sxs-lookup"><span data-stu-id="3a400-679">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Forward immediate to: sip:anders@contoso.com

</div>

<div>

## <a name="disable-call-forwarding-immediately"></a><span data-ttu-id="3a400-680">Deshabilitar desvío de llamadas inmediatamente</span><span class="sxs-lookup"><span data-stu-id="3a400-680">Disable Call Forwarding Immediately</span></span>

<span data-ttu-id="3a400-681">En este ejemplo se deshabilita automáticamente el desvío de llamadas.</span><span class="sxs-lookup"><span data-stu-id="3a400-681">This example immediately disables call forwarding.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com  /disablefwdimmediate

<span data-ttu-id="3a400-682">**Salida**</span><span class="sxs-lookup"><span data-stu-id="3a400-682">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a><span data-ttu-id="3a400-683">Agregar un usuario como delegado y configurar las llamadas simultáneas de delegados</span><span class="sxs-lookup"><span data-stu-id="3a400-683">Add a User as a Delegate and Set Up Simultaneous Ringing of Delegates</span></span>

<span data-ttu-id="3a400-684">En este ejemplo se agrega un usuario como delegado y se configuran las llamadas simultáneas de delegados.</span><span class="sxs-lookup"><span data-stu-id="3a400-684">This example adds a user as a delegate and sets up simultaneous ringing of delegates.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates

<span data-ttu-id="3a400-685">**Salida**</span><span class="sxs-lookup"><span data-stu-id="3a400-685">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simultaneously Ringing Delegates: sip:joe@contoso.com

</div>

<div>

## <a name="change-simultaneous-ringing-rule-of-delegates"></a><span data-ttu-id="3a400-686">Cambiar la regla de llamadas simultáneas de delegados</span><span class="sxs-lookup"><span data-stu-id="3a400-686">Change Simultaneous Ringing Rule of Delegates</span></span>

<span data-ttu-id="3a400-687">En este ejemplo se cambia la regla de llamadas simultáneas configurada en el ejemplo anterior a la regla de demora de timbre.</span><span class="sxs-lookup"><span data-stu-id="3a400-687">This example changes the simultaneous ringing rule that was set in the previous example to the delayed ringing rule.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10

<span data-ttu-id="3a400-688">**Salida**</span><span class="sxs-lookup"><span data-stu-id="3a400-688">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com

</div>

<div>

## <a name="remove-the-delegate"></a><span data-ttu-id="3a400-689">Quitar al delegado</span><span class="sxs-lookup"><span data-stu-id="3a400-689">Remove the Delegate</span></span>

<span data-ttu-id="3a400-690">En este ejemplo se quita el delegado.</span><span class="sxs-lookup"><span data-stu-id="3a400-690">This example removes the delegate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3a400-691">Al quitar el último delegado, se deshabilita automáticamente la llamada a delegados.</span><span class="sxs-lookup"><span data-stu-id="3a400-691">When the last delegate is removed, delegate ringing is automatically disabled.</span></span>



</div>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com

<span data-ttu-id="3a400-692">**Salida**</span><span class="sxs-lookup"><span data-stu-id="3a400-692">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a><span data-ttu-id="3a400-693">Agregar un delegado y configurar la regla de desvío de llamadas a delegados</span><span class="sxs-lookup"><span data-stu-id="3a400-693">Add a Delegate and Set Up the Call-Forward to Delegates Rule</span></span>

<span data-ttu-id="3a400-694">En este ejemplo se agrega un delegado y se configura la regla de desvío de llamadas a delegados.</span><span class="sxs-lookup"><span data-stu-id="3a400-694">This example adds a delegate and sets up the call-forward to delegates rule.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates

<span data-ttu-id="3a400-695">**Salida**</span><span class="sxs-lookup"><span data-stu-id="3a400-695">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Forwarding calls to Delegates: sip:anders@contoso.com

</div>

<div>

## <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a><span data-ttu-id="3a400-696">Habilitar las llamadas simultáneas y establecer un número de destino</span><span class="sxs-lookup"><span data-stu-id="3a400-696">Enable Simultaneous Ringing and Set a Destination Number</span></span>

<span data-ttu-id="3a400-697">En este ejemplo se habilitan las llamadas simultáneas y se establece un número de destino de llamadas simultáneas.</span><span class="sxs-lookup"><span data-stu-id="3a400-697">This example enables simultaneous ringing and sets a simultaneous ringing destination number.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring

<div>


> [!NOTE]  
> <span data-ttu-id="3a400-698">Para cambiar el número de destino de las llamadas simultáneas de un usuario que ya tenga habilitadas las llamadas simultáneas, mantenga el comando con el modificador /enablesimulring, ya que en caso contrario no se cambiaría el número de destino.</span><span class="sxs-lookup"><span data-stu-id="3a400-698">To change the simultaneous ringing destination number of a user that has already simultaneous ringing enabled, keep the command with the /enablesimulring switch, otherwise the destination number will not be changed.</span></span>



</div>

<span data-ttu-id="3a400-699">**Salida**</span><span class="sxs-lookup"><span data-stu-id="3a400-699">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: True
    Simul_Ringing to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="disable-simultaneous-ringing"></a><span data-ttu-id="3a400-700">Deshabilitar llamadas simultáneas</span><span class="sxs-lookup"><span data-stu-id="3a400-700">Disable Simultaneous Ringing</span></span>

<span data-ttu-id="3a400-701">En este ejemplo se deshabilitan las llamadas simultáneas.</span><span class="sxs-lookup"><span data-stu-id="3a400-701">This example disables simultaneous ringing.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablesimulring

<span data-ttu-id="3a400-702">**Salida**</span><span class="sxs-lookup"><span data-stu-id="3a400-702">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a><span data-ttu-id="3a400-703">Agregar un miembro para llamada de equipo y configurar las llamadas simultáneas en el grupo de miembros de llamada de equipo</span><span class="sxs-lookup"><span data-stu-id="3a400-703">Add a Team Member for Team-Call and Set up Simultaneous Ringing to the Team-Call Members Group</span></span>

<span data-ttu-id="3a400-704">En este ejemplo se agrega un miembro de equipo al grupo de llamada de equipo de un usuario y se habilitan las llamadas simultáneas al grupo de llamada de equipo.</span><span class="sxs-lookup"><span data-stu-id="3a400-704">This example adds a team member to the team-call group of a user and enables simultaneous ringing to the team-call group.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam

<div>


> [!NOTE]  
> <span data-ttu-id="3a400-705">Al agregar a un miembro a un grupo de llamada de equipo de un usuario se cambiará automáticamente a la configuración de llamadas simultáneas de los usuarios para llamar simultáneamente a su grupo de llamada de equipo.</span><span class="sxs-lookup"><span data-stu-id="3a400-705">Adding a member to the team-call group of a user will automatically switch the simultaneous ringing settigs of the users to simulring his team-call group.</span></span>



</div>

<span data-ttu-id="3a400-706">**Salida**</span><span class="sxs-lookup"><span data-stu-id="3a400-706">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Team ringing enabled. Team: sip:anders@contoso.com

</div>

<div>

## <a name="remove-a-member-from-the-team-call-group"></a><span data-ttu-id="3a400-707">Quitar a un miembro del grupo de llamada de equipo</span><span class="sxs-lookup"><span data-stu-id="3a400-707">Remove a Member from the Team-Call Group</span></span>

<span data-ttu-id="3a400-708">En este ejemplo se quita a un miembro del equipo del grupo de llamada de equipo de un usuario.</span><span class="sxs-lookup"><span data-stu-id="3a400-708">This example removes a team member of the team-call group of a user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com

<div>


> [!NOTE]  
> <span data-ttu-id="3a400-709">Si el miembro que va a quitarse es el único miembro del grupo de llamada de equipo, se deshabilitarán automáticamente las llamadas simultáneas al grupo de llamada de equipo.</span><span class="sxs-lookup"><span data-stu-id="3a400-709">If the member being removed is the only member of the team-call group, simultaneously ringing to the team-call group will be automatically disabled.</span></span>



</div>

<span data-ttu-id="3a400-710">**Salida**</span><span class="sxs-lookup"><span data-stu-id="3a400-710">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-delayed-ring-to-the-team-call-group"></a><span data-ttu-id="3a400-711">Establecer la demora de timbre al grupo de llamada de equipo</span><span class="sxs-lookup"><span data-stu-id="3a400-711">Set the Delayed Ring to the Team-Call Group</span></span>

<span data-ttu-id="3a400-712">En este ejemplo se cambia la configuración de hora de demora de timbre al grupo de llamada de equipo.</span><span class="sxs-lookup"><span data-stu-id="3a400-712">This example changes the delayed ring to the team-call group time setting.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringteam:5

<span data-ttu-id="3a400-713">**Salida**</span><span class="sxs-lookup"><span data-stu-id="3a400-713">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com

</div>

<div>

## <a name="enable-team-call"></a><span data-ttu-id="3a400-714">Habilitar llamada de equipo</span><span class="sxs-lookup"><span data-stu-id="3a400-714">Enable Team-Call</span></span>

<span data-ttu-id="3a400-715">En este ejemplo se habilita la llamada de equipo para un usuario concreto.</span><span class="sxs-lookup"><span data-stu-id="3a400-715">This example enables team-call for a given user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /simulringteam

<div>


> [!NOTE]  
> <span data-ttu-id="3a400-716">Si el grupo de llamada de equipo del usuario no tiene ningún miembro, no se habilitará la llamada de equipo.</span><span class="sxs-lookup"><span data-stu-id="3a400-716">If the team-call group of the user has no members, team-call won’t be enabled.</span></span>



</div>

<span data-ttu-id="3a400-717">**Salida**</span><span class="sxs-lookup"><span data-stu-id="3a400-717">**Output**</span></span>

</div>

<div>

## <a name="disable-team-call"></a><span data-ttu-id="3a400-718">Deshabilitar la llamada de equipo</span><span class="sxs-lookup"><span data-stu-id="3a400-718">Disable Team-Call</span></span>

<span data-ttu-id="3a400-719">En este ejemplo se deshabilita la llamada de equipo para un usuario concreto.</span><span class="sxs-lookup"><span data-stu-id="3a400-719">This example disables team-call for a given user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disableteamcall

<span data-ttu-id="3a400-720">**Salida**</span><span class="sxs-lookup"><span data-stu-id="3a400-720">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a><span data-ttu-id="3a400-721">Habilitar la respuesta de llamadas grupales y asignar un grupo de respuesta a un usuario</span><span class="sxs-lookup"><span data-stu-id="3a400-721">Enable Group Call Pickup and Assign a Pickup Group to a User</span></span>

<span data-ttu-id="3a400-722">En este ejemplo se asigna un grupo de respuesta a un usuario y se habilita la respuesta de llamadas grupales.</span><span class="sxs-lookup"><span data-stu-id="3a400-722">This example assigns a pickup group to a user and enables Group Call Pickup.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199

<span data-ttu-id="3a400-723">**Salida**</span><span class="sxs-lookup"><span data-stu-id="3a400-723">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone

</div>

<div>

## <a name="disable-group-call-pickup"></a><span data-ttu-id="3a400-724">Deshabilitar la respuesta de llamadas grupales</span><span class="sxs-lookup"><span data-stu-id="3a400-724">Disable Group Call Pickup</span></span>

<span data-ttu-id="3a400-725">En este ejemplo se deshabilita la respuesta de llamadas grupales para un usuario concreto.</span><span class="sxs-lookup"><span data-stu-id="3a400-725">This example disables Group Call Pickup for a given user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablegrouppickup

<div>


> [!NOTE]  
> <span data-ttu-id="3a400-p191">Cuando se deshabilita la respuesta de llamadas grupales para un usuario, no se conserva el número de grupo que se asignó al usuario. Si posteriormente quiere volver a habilitar la respuesta de llamadas grupales para ese usuario, deberá volver a asignar el número de grupo con el modificador /enablegrouppickup.</span><span class="sxs-lookup"><span data-stu-id="3a400-p191">When you disable Group Call Pickup for a user, the group number that was assigned to the user is not retained. If you subsequently want to re-enable Group Call Pickup for that user, you must assign the group number again with the /enablegrouppickup switch.</span></span>



</div>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True

</div>

</div>

</div>

<div>

## <a name="sysprepps1"></a><span data-ttu-id="3a400-728">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="3a400-728">SYSPrep.ps1</span></span>

<div>

## <a name="description"></a><span data-ttu-id="3a400-729">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a400-729">Description</span></span>

<span data-ttu-id="3a400-730">SYSPrep. PS1 es un script de Windows PowerShell que instalará los siguientes requisitos previos de Lync Server 2013 en el sistema operativo Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="3a400-730">SYSPrep.ps1 is a Windows PowerShell script that will install the following Lync Server 2013 prerequisites on your Windows Server 2008 operating system machine.</span></span>

  - <span data-ttu-id="3a400-731">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="3a400-731">Microsoft .Net Framework 4.5</span></span>

  - <span data-ttu-id="3a400-732">Microsoft SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="3a400-732">Microsoft SQL Server Express</span></span>

  - <span data-ttu-id="3a400-733">Windows Powershell versión 3.0</span><span class="sxs-lookup"><span data-stu-id="3a400-733">Windows Powershell version 3.0</span></span>

  - <span data-ttu-id="3a400-734">Paquete redistribuible de Visual C++ 2010</span><span class="sxs-lookup"><span data-stu-id="3a400-734">Visual C++ 2010 Redistributable</span></span>

  - <span data-ttu-id="3a400-735">Actualizaciones de Internet Information Server</span><span class="sxs-lookup"><span data-stu-id="3a400-735">Internet Information Server Updates</span></span>

  - <span data-ttu-id="3a400-736">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="3a400-736">Windows Identity Foundation</span></span>

  - <span data-ttu-id="3a400-737">Archivos principales de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3a400-737">Lync Server 2013 Core files</span></span>

<span data-ttu-id="3a400-738">Aunque el nombre del script es parecido a la herramienta de preparación del sistema de los sistemas operativos Microsoft Windows, en realidad son distintos.</span><span class="sxs-lookup"><span data-stu-id="3a400-738">While the script name is similar to the System Preparation Tool for the Microsoft Windows operating systems, they are different.</span></span> <span data-ttu-id="3a400-739">Este script solo instalará los requisitos previos necesarios para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3a400-739">This script will only install the required prerequisites for Lync Server 2013.</span></span> <span data-ttu-id="3a400-740">Después de instalar estos requisitos previos, puede utilizarse la herramienta SYSPrep de Windows para crear una imagen del servidor.</span><span class="sxs-lookup"><span data-stu-id="3a400-740">Once those prerequisites are installed, the Windows SYSPrep tool can then be used to create an image of the server.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="3a400-741">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3a400-741">Requirements</span></span>

<span data-ttu-id="3a400-742">Antes de ejecutar el script SYSPrep. ps1, debe copiar los archivos necesarios en una carpeta local del equipo del sistema operativo Windows Server 2008 (por ejemplo, **D:\\Setup)**.</span><span class="sxs-lookup"><span data-stu-id="3a400-742">Prior to running the SYSPrep.ps1 script, you must copy the prerequisite files to a local folder on the Windows Server 2008 operating system machine (for example **D:\\Setup)**.</span></span> <span data-ttu-id="3a400-743">Esta carpeta también debe incluir una copia de los archivos de Lync Server 2013, en concreto **setup. exe.**</span><span class="sxs-lookup"><span data-stu-id="3a400-743">This folder must also include a copy of the Lync Server 2013 files, specifically **Setup.exe.**</span></span> <span data-ttu-id="3a400-744">Los archivos de requisitos previos pueden descargarse desde las ubicaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="3a400-744">The prerequisite files can be downloaded from the following locations:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3a400-745">Requisito previo</span><span class="sxs-lookup"><span data-stu-id="3a400-745">Prerequisite</span></span></th>
<th><span data-ttu-id="3a400-746">Ubicación</span><span class="sxs-lookup"><span data-stu-id="3a400-746">Location</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3a400-747">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="3a400-747">Microsoft .Net Framework 4.5</span></span></p></td>
<td><p>http://go.microsoft.com/?linkid=9816306</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a400-748">Microsoft SQL Server Express 2008 R2</span><span class="sxs-lookup"><span data-stu-id="3a400-748">Microsoft SQL Server Express 2008 R2</span></span></p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=23650</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a400-749">Windows Powershell versión 3.0</span><span class="sxs-lookup"><span data-stu-id="3a400-749">Windows Powershell version 3.0</span></span></p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=34595</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a400-750">Paquete redistribuible de Visual C++ 2010</span><span class="sxs-lookup"><span data-stu-id="3a400-750">Visual C++ 2010 Redistributable</span></span></p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=5555</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a400-751">Actualizaciones de Internet Information Server</span><span class="sxs-lookup"><span data-stu-id="3a400-751">Internet Information Server Updates</span></span></p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=34869</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a400-752">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="3a400-752">Windows Identity Foundation</span></span></p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=17331</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a400-753">Instalar. exe de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3a400-753">Lync Server 2013 Setup.exe</span></span></p></td>
<td><p><span data-ttu-id="3a400-754">Copiar desde multimedia de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3a400-754">Copy from Lync Server 2013 media</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="parameter"></a><span data-ttu-id="3a400-755">Parámetro</span><span class="sxs-lookup"><span data-stu-id="3a400-755">Parameter</span></span>

<span data-ttu-id="3a400-756">El parámetro **–SetupFolder** toma como argumento la ubicación del directorio de los archivos de requisitos previos</span><span class="sxs-lookup"><span data-stu-id="3a400-756">The **–SetupFolder** parameter takes as an argument the directory location of the prerequisite files</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="3a400-757">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="3a400-757">Examples</span></span>

<span data-ttu-id="3a400-758">Para ejecutar el script SYSPrep. PS1 e instalar los requisitos previos de Lync Server 2013, ejecute el siguiente comando desde un símbolo del sistema con privilegios elevados:</span><span class="sxs-lookup"><span data-stu-id="3a400-758">To run the SYSPrep.ps1 script and install the Lync Server 2013 prerequisites, run the following command from an elevated command prompt:</span></span>

    ./SysPrep.PS1 -SetupFolder D:\Setup

</div>

</div>

<div>

## <a name="unassigned-number-announcements-migration"></a><span data-ttu-id="3a400-759">Unassigned Number Announcements Migration (Migración de anuncios de números sin asignar)</span><span class="sxs-lookup"><span data-stu-id="3a400-759">Unassigned Number Announcements Migration</span></span>

<span data-ttu-id="3a400-760">La herramienta de migración anuncios de números no asignados permite a un administrador de Lync mover la configuración de los números no asignados que es atendida por la aplicación de presentación de un servidor o grupo de servidores de Lync de origen a un servidor o grupo de servidores de Lync de destino.</span><span class="sxs-lookup"><span data-stu-id="3a400-760">The Unassigned Number Announcements Migration tool enables a Lync administrator to move the unassigned numbers configuration that is serviced by the announcement application from a source Lync Server or Pool to a destination Lync Server or Pool.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="3a400-761">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a400-761">Description</span></span>

<span data-ttu-id="3a400-762">La herramienta Unassigned Number Announcements Migration es un script de Windows PowerShell script que mueve la configuración de los números sin asignar de la aplicación del anuncio desde un servidor o grupo de origen a un servidor o grupo distinto.</span><span class="sxs-lookup"><span data-stu-id="3a400-762">The Unassigned Number Announcements Migration tool is a Windows PowerShell script that moves the unassigned numbers configuration serviced by the announcement application of a source server or pool to a different server or pool.</span></span>

<span data-ttu-id="3a400-763">Al ejecutar el script Unassigned Number Announcements Migration realizará las operaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="3a400-763">When executed, the Unassigned Number Announcements Migration script will perform the following operations:</span></span>

1.  <span data-ttu-id="3a400-764">Mueve todos los archivos de audio utilizados en los anuncios de números sin asignar de la aplicación del anuncio hospedada en el servidor o grupo de origen al almacén de archivos del servidor o grupo de destino.</span><span class="sxs-lookup"><span data-stu-id="3a400-764">Move all the audio files used by the unassigned number announcements of the announcement application hosted in the source server or pool to the file store of the destination server or pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3a400-765">los archivos de audio se eliminan del grupo de origen una vez que se copian en el grupo de destino.</span><span class="sxs-lookup"><span data-stu-id="3a400-765">the audio files are removed from the source pool once they’re copied to the destination pool.</span></span>

    
    </div>

2.  <span data-ttu-id="3a400-766">Mueve todos los anuncios de números sin asignar configurados para la aplicación del anuncio hospedada en el servidor o grupo de origen al servidor o grupo de destino.</span><span class="sxs-lookup"><span data-stu-id="3a400-766">Move all unassigned number announcements configured for the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

3.  <span data-ttu-id="3a400-767">Reasigna todos los intervalos de números sin asignar de la aplicación del anuncio hospedada en el servidor o grupo de origen al servidor o grupo de destino.</span><span class="sxs-lookup"><span data-stu-id="3a400-767">Reassign all the unassigned number ranges that are serviced by the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

<span data-ttu-id="3a400-768">Después de ejecutar correctamente el script, todos los intervalos de números sin asignar de la aplicación del anuncio hospedada en el servidor o grupo de origen serán atendidos por la misma configuración por el destino o grupo de destino.</span><span class="sxs-lookup"><span data-stu-id="3a400-768">After successfully running the script, all the unassigned number ranges that were serviced by the announcement application hosted in the source server or pool will now be serviced with the same configuration by the destination server or pool.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="3a400-769">Salida</span><span class="sxs-lookup"><span data-stu-id="3a400-769">Output</span></span>

<span data-ttu-id="3a400-770">La secuencia de comandos **Move-CsAnnouncementConfiguration** indica en la ventana del shell de administración de Lync desde donde se ejecuta el éxito o el fracaso de la operación de migración.</span><span class="sxs-lookup"><span data-stu-id="3a400-770">The **Move-CsAnnouncementConfiguration** script indicates in the Lync Management Shell window from where it’s executed the success or failure of the migration operation.</span></span>

<span data-ttu-id="3a400-p194">Si la ejecución de la operación es interrumpida por algún error, los intervalos de números sin asignar que se hayan movido correctamente al destino permanecerán en este de forma operativa, mientras que el resto de intervalos de números sin asignar que aún no hayan sido migrados permanecerán en el origen también de forma operativa. Para completar la migración del resto de la configuración, vuelva a ejecutar el script después de corregir el error.</span><span class="sxs-lookup"><span data-stu-id="3a400-p194">If the execution of the operation is interrupted by any error, the unassigned number ranges that were successfully moved to the destination will remain in the destination in an operational form and the rest of the unassigned number ranges to be migrated will remain in the source as well in an operational form. To fully migrate the rest of the configuration, rerun the script after addressing the error.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="3a400-773">Finalidad</span><span class="sxs-lookup"><span data-stu-id="3a400-773">Purpose</span></span>

<span data-ttu-id="3a400-774">El script Unassigned Number Announcements Migration puede utilizarse en los tres casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="3a400-774">The Unassigned Number Announcements Migration script can be used in the following three scenarios:</span></span>

  - <span data-ttu-id="3a400-775">**Migrar las opciones de configuración a una nueva versión de Lync Server:** Contoso está en proceso de migrar a Lync Server 2013 y, como parte del proceso de migración, el administrador de Lync Server desea mover la configuración de los números no asignados atendida por la aplicación de presentación de la implementación de Lync Server 2010 a la nueva implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3a400-775">**Migrating configuration settings to a new version of Lync Server:** Contoso is in the process of migrating to Lync Server 2013 and as part of the migration process the Lync Server administrator would like to move the unassigned numbers configuration serviced by the announcement application from the Lync Server 2010 deployment to the new Lync Server 2013 deployment.</span></span> <span data-ttu-id="3a400-776">Para mover la configuración, el administrador de Lync Server usa la herramienta de migración anuncios de números no asignados.</span><span class="sxs-lookup"><span data-stu-id="3a400-776">To move the configuration settings, the Lync Server administrator uses the Unassigned Number Announcements Migration tool.</span></span>

  - <span data-ttu-id="3a400-777">**Deshacer una implementación de Lync server 2013 a Lync server 2010:** Debido a los factores inesperados, Contoso tiene que revertir la migración a la nueva implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3a400-777">**Rolling back a deployment from Lync Server 2013 to Lync Server 2010:** Due unexpected factors, Contoso has to roll back the migration to the new Lync Server 2013 deployment.</span></span> <span data-ttu-id="3a400-778">Para minimizar las interrupciones en el servicio, el administrador de Lync Server usa la herramienta de migración anuncios de números no asignados para revertir la configuración de la implementación de Lync Server 2013 a la implementación de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3a400-778">To minimize disruptions to the service, the Lync Server administrator uses the Unassigned Number Announcements Migration tool to roll back the configuration from the Lync Server 2013 deployment to the Lync Server 2010 deployment.</span></span>

  - <span data-ttu-id="3a400-779">**Mover datos entre implementaciones de Lync:** Contoso está en proceso de reemplazar todos los servidores de un grupo por servidores más nuevos.</span><span class="sxs-lookup"><span data-stu-id="3a400-779">**Moving data between Lync deployments:** Contoso is in the process of replacing all the servers of one pool with newer servers.</span></span> <span data-ttu-id="3a400-780">Su estrategia es implementar un nuevo grupo de servidores de Lync Server 2013, mover todos los datos del antiguo al nuevo grupo y, después, dejar de usar el antiguo grupo.</span><span class="sxs-lookup"><span data-stu-id="3a400-780">Their strategy is to deploy a new Lync Server 2013 pool, move all the data from the old to the new pool, and then deprecate the old pool.</span></span> <span data-ttu-id="3a400-781">Después de implementar el nuevo grupo de servidores, la herramienta Unassigned Number Announcements Migration se utiliza para mover la configuración del grupo anterior al nuevo.</span><span class="sxs-lookup"><span data-stu-id="3a400-781">Once the new pool is deployed, the Unassigned Number Announcements Migration tool is used to move the configuration from the old pool to the new one.</span></span>

<div>

## <a name="requirements"></a><span data-ttu-id="3a400-782">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3a400-782">Requirements</span></span>

<span data-ttu-id="3a400-783">Estos son los requisitos principales para ejecutar correctamente la herramienta:</span><span class="sxs-lookup"><span data-stu-id="3a400-783">The following are the main requirements needed to successfully run the tool:</span></span>

1.  <span data-ttu-id="3a400-784">El script debe ejecutarse desde un equipo que tenga instalado el shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3a400-784">The script must be run from a computer that has Lync Server 2013 Management Shell installed.</span></span>

2.  <span data-ttu-id="3a400-785">La aplicación de anuncios debe implementarse correctamente en los servidores o agrupaciones de Lync de origen y destino.</span><span class="sxs-lookup"><span data-stu-id="3a400-785">The announcement application has to be successfully deployed in the source and destination Lync Servers or Pools.</span></span>

<div>

## <a name="move-csannouncementconfiguration-script"></a><span data-ttu-id="3a400-786">Script Move-CsAnnouncementConfiguration</span><span class="sxs-lookup"><span data-stu-id="3a400-786">Move-CsAnnouncementConfiguration script</span></span>

<span data-ttu-id="3a400-787">El script Move-CsAnnouncementConfiguration requiere los dos parámetros descritos en la tabla siguiente. </span><span class="sxs-lookup"><span data-stu-id="3a400-787">The Move-CsAnnouncementConfiguration script requires the two parameters that are described in the table below.</span></span>

<span data-ttu-id="3a400-788">![Parámetros Move-CsAnnouncementConfiguration.] (images/JJ945604.7ab66ad3-d0db-4d77-8b93-ebccf0cb0663(OCS.15).jpg "Parámetros Move-CsAnnouncementConfiguration.")</span><span class="sxs-lookup"><span data-stu-id="3a400-788">![Move-CsAnnouncementConfiguration parameters.](images/JJ945604.7ab66ad3-d0db-4d77-8b93-ebccf0cb0663(OCS.15).jpg "Move-CsAnnouncementConfiguration parameters.")</span></span>

</div>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="3a400-789">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="3a400-789">Examples</span></span>

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2010-pool-to-a-lync-server-2013-pool"></a><span data-ttu-id="3a400-790">Mover la configuración de anuncios de números sin asignar de un grupo de servidores de Lync Server 2010 a un grupo de servidores de Lync 2013</span><span class="sxs-lookup"><span data-stu-id="3a400-790">Moving the Unassigned Number Announcements Configuration from a Lync Server 2010 Pool to a Lync Server 2013 Pool</span></span>

<span data-ttu-id="3a400-791">En este ejemplo se mueven los anuncios de números sin asignar del grupo de origen (Lync Server 2010) al grupo de destino (Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="3a400-791">This example moves the unassigned number announcements from the source pool (Lync Server 2010) to the destination pool (Lync Server 2013).</span></span>

    Move-CsAnnouncementConfiguration.ps1 -Source LS2010Pool.contoso.com -Destination LS2013Pool.contoso.com

</div>

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-lync-server-2010-pool"></a><span data-ttu-id="3a400-792">Mover la configuración de anuncios de números sin asignar de un grupo de servidores de Lync Server 2013 a un grupo de servidores de Lync 2010</span><span class="sxs-lookup"><span data-stu-id="3a400-792">Moving the Unassigned Number Announcements Configuration from a Lync Server 2013 Pool to a Lync Server 2010 Pool</span></span>

<span data-ttu-id="3a400-793">En este ejemplo se mueven los anuncios de números sin asignar del grupo de origen (Lync Server 2013) al grupo de destino (Lync Server 2010).</span><span class="sxs-lookup"><span data-stu-id="3a400-793">This example moves the unassigned number announcements from the source pool (Lync Server 2013) to the destination pool (Lync Server 2010).</span></span>

    Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination LS2010Pool.contoso.com

</div>

</div>

</div>

<div>

## <a name="web-conf-data"></a><span data-ttu-id="3a400-794">Web Conf Data</span><span class="sxs-lookup"><span data-stu-id="3a400-794">Web Conf Data</span></span>

<span data-ttu-id="3a400-795">La herramienta de datos Web conf permite que un administrador del software de comunicaciones de Lync Server 2013 tenga más control sobre los datos asociados a las conferencias web del organizador.</span><span class="sxs-lookup"><span data-stu-id="3a400-795">The Web Conf Data Tool allows an administrator of Lync Server 2013 communications software to have more control over the data associated with an organizer’s Web conferences.</span></span> <span data-ttu-id="3a400-796">En algunos casos se pueden eliminar los datos de reuniones de un usuario concreto según criterios de marca de tiempo.</span><span class="sxs-lookup"><span data-stu-id="3a400-796">Scenarios include the ability to delete a specific user’s meeting data based on a time stamp criteria.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="3a400-797">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a400-797">Description</span></span>

<span data-ttu-id="3a400-798">Esta herramienta permite al administrador realizar las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="3a400-798">This tool allows the administrator to perform the following operations:</span></span>

1.  <span data-ttu-id="3a400-799">Buscar todos los datos de conferencias web asociados con un usuario concreto.</span><span class="sxs-lookup"><span data-stu-id="3a400-799">Find all Web conferencing data associated with a single user.</span></span>

2.  <span data-ttu-id="3a400-800">Eliminar todos los datos de conferencias web asociados con un usuario concreto.</span><span class="sxs-lookup"><span data-stu-id="3a400-800">Delete all Web conferencing data associated with a single user.</span></span>

3.  <span data-ttu-id="3a400-801">Eliminar todos los datos de conferencias web asociados con un usuario concreto anteriores a una fecha concreta</span><span class="sxs-lookup"><span data-stu-id="3a400-801">Delete all Web conferencing data associated with a single user that is older than a certain date.</span></span>

4.  <span data-ttu-id="3a400-802">Mover todos los datos de conferencias web asociados con un usuario concreto al mover a dicho usuario desde un grupo a otro.</span><span class="sxs-lookup"><span data-stu-id="3a400-802">Move all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3a400-803">Las herramientas del kit de recursos para Lync Server 2010 admiten el traslado de todos los datos de conferencias web asociados con un solo usuario cuando este se mueve de un grupo a otro.</span><span class="sxs-lookup"><span data-stu-id="3a400-803">The Resource Kit Tools for Lync Server 2010 supported moving all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span> <span data-ttu-id="3a400-804">Dicha funcionalidad ya no se utiliza en favor del parámetro <STRONG>MoveConferenceData</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="3a400-804">That functionality is now deprecated from this tool in favor of the <STRONG>MoveConferenceData</STRONG> parameter.</span></span> <span data-ttu-id="3a400-805">Para obtener más información sobre este parámetro, vea el cmdlet <A href="https://technet.microsoft.com/en-us/library/gg398528(v=ocs.15)">Move-CsUser</A> .</span><span class="sxs-lookup"><span data-stu-id="3a400-805">For details about this parameter, see the <A href="https://technet.microsoft.com/en-us/library/gg398528(v=ocs.15)">Move-CsUser</A> cmdlet.</span></span>



</div>

<span data-ttu-id="3a400-p200">Esta herramienta elimina únicamente los datos de las reuniones inactivas. Las reuniones activas (o reuniones en sesiones) no se pueden eliminar.</span><span class="sxs-lookup"><span data-stu-id="3a400-p200">The tool deletes meeting data only for meetings that are inactive. Active meetings (or meetings in sessions) cannot be deleted.</span></span>

<span data-ttu-id="3a400-p201">Esta herramienta debe ejecutarse desde un equipo que se encuentre en el mismo grupo que el usuario de destino. El usuario cuyos datos de contenidos de reuniones vayan a ser administrados por esta herramienta ha de ser hospedado en el mismo grupo de usuarios.</span><span class="sxs-lookup"><span data-stu-id="3a400-p201">This tool must be run from a computer that is in the same pool as the target user. The user whose meeting content data is being managed by this tool must be homed in the same user pool.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="3a400-810">Salida</span><span class="sxs-lookup"><span data-stu-id="3a400-810">Output</span></span>

<span data-ttu-id="3a400-811">Esta herramienta informa de los resultados de todas las operaciones:</span><span class="sxs-lookup"><span data-stu-id="3a400-811">This tool outputs the results of each of the operations:</span></span>

  - <span data-ttu-id="3a400-812">Si se realiza una consulta, la herramienta genera una lista de todas las carpetas de datos de reuniones inactivas que tengan al usuario como organizador.</span><span class="sxs-lookup"><span data-stu-id="3a400-812">If a query is performed, the tool outputs the list of all inactive meeting data folders that have that user as an organizer.</span></span>

  - <span data-ttu-id="3a400-813">Si se eliminan datos, la herramienta genera una lista de todas las carpetas de datos de reuniones cuyos datos se eliminarán.</span><span class="sxs-lookup"><span data-stu-id="3a400-813">If a delete is performed, the tool outputs the list of all meeting data folders whose data will be deleted.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="3a400-814">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3a400-814">Requirements</span></span>

<span data-ttu-id="3a400-815">La herramienta ha de ejecutarse en el mismo grupo donde esté hospedado actualmente el organizador.</span><span class="sxs-lookup"><span data-stu-id="3a400-815">The tool needs to be run in the same pool where the organizer is currently homed.</span></span>

<span data-ttu-id="3a400-816">La herramienta debe ejecutarse con privilegios de administrador con acceso al almacén de archivos de contenido.</span><span class="sxs-lookup"><span data-stu-id="3a400-816">The tool must be run using administrator privileges with access to the Content File Store.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="3a400-817">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="3a400-817">Examples</span></span>

<span data-ttu-id="3a400-818">En la tabla siguiente se describen los parámetros, algunos de los cuales se han utilizado en los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="3a400-818">The following table describes the parameters, some of which are used in the examples.</span></span>

<span data-ttu-id="3a400-819">![Parámetros de la herramienta de datos Web conf.] (images/JJ945604.a733c1c6-5dfc-4874-a74f-bfdee81c1401(OCS.15).jpg "Parámetros de la herramienta de datos Web conf.")</span><span class="sxs-lookup"><span data-stu-id="3a400-819">![Web Conf Data Tool parameters.](images/JJ945604.a733c1c6-5dfc-4874-a74f-bfdee81c1401(OCS.15).jpg "Web Conf Data Tool parameters.")</span></span>

    WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""

<span data-ttu-id="3a400-p202">En el ejemplo anterior se mostraba el funcionamiento de un comando de consulta. La salida de dicho comando sería una lista de todas las carpetas de contenido de reuniones que serían afectadas por esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="3a400-p202">The preceding example shows how a query command would work. The output of such a command would be a list of all meeting content folders that would be affected by this tool.</span></span>

    WebConfDataTool.exe /User:user0@contoso.com /Action:delete

<span data-ttu-id="3a400-p203">En el ejemplo anterior se muestra el comando delete. Este comando elimina todas las carpetas de reuniones inactivas de este usuario.</span><span class="sxs-lookup"><span data-stu-id="3a400-p203">The preceding is an example of a delete command. The delete command will remove all inactive meeting folders from this user.</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="3a400-824">Resumen</span><span class="sxs-lookup"><span data-stu-id="3a400-824">Summary</span></span>

<span data-ttu-id="3a400-825">Esta herramienta puede ser un recurso útil para administradores que necesiten un control más preciso en los datos de reuniones de conferencias.</span><span class="sxs-lookup"><span data-stu-id="3a400-825">This tool can be a valuable resource to administrators who need more precise control over conference meeting data.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>
