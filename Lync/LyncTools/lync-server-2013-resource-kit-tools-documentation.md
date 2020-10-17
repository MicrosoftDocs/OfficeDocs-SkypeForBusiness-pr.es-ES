---
title: Documentación de las herramientas del kit de recursos de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Resource Kit Tools Documentation
ms:assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945604(v=OCS.15)
ms:contentKeyID: 51541429
ms.date: 02/02/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60c2260f5729c45455596f0ab2477f7a190ef520
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509227"
---
# <a name="lync-server-2013-resource-kit-tools-documentation"></a><span data-ttu-id="7a9eb-102">Documentación de las herramientas del kit de recursos de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7a9eb-102">Lync Server 2013 Resource Kit Tools Documentation</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a9eb-103">_**Última modificación del tema:** 2014-01-09_</span><span class="sxs-lookup"><span data-stu-id="7a9eb-103">_**Topic Last Modified:** 2014-01-09_</span></span>

<span data-ttu-id="7a9eb-104">En este tema se describen las herramientas que forman parte del kit de recursos de Lync Server 2013, incluido el propósito de cada herramienta y ejemplos de su uso. Las herramientas del kit de recursos de Lync Server 2013, que ayudan a facilitar las tareas rutinarias a los administradores de ti que implementan y administran Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-104">This topic describes the tools that are part of the Lync Server 2013 Resource Kit, including the purpose of each tool, and examples of its use.The Lync Server 2013, Resource Kit Tools help to make routine tasks easier for IT administrators who deploy and manage Lync Server 2013.</span></span> <span data-ttu-id="7a9eb-105">Por ejemplo, la herramienta de **datos Web conf** puede usarse para controlar fácilmente los datos cargados por los usuarios durante una reunión en línea.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-105">For example, the **Web Conf Data** tool can be used to easily control data that is uploaded by users during an online meeting.</span></span> <span data-ttu-id="7a9eb-106">La herramienta **SEFAUtil** se puede usar para configurar el desvío de llamadas de delegado y responder para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-106">The **SEFAUtil** tool can be used to set up delegate call forwarding and answering for users.</span></span> <span data-ttu-id="7a9eb-107">Recomendamos a los administradores de ti que usen estas herramientas para administrar de forma más eficaz Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-107">We encourage IT administrators to use these tools to more effectively manage Lync Server 2013.</span></span>

<div>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="7a9eb-108">Instalación de las herramientas del kit de recursos</span><span class="sxs-lookup"><span data-stu-id="7a9eb-108">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="7a9eb-109">Para instalar las herramientas del kit de recursos de Lync Server 2013, descargue **OCSReskit.msi**.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-109">To install the Lync Server 2013, Resource Kit Tools, download **OCSReskit.msi**.</span></span> <span data-ttu-id="7a9eb-110">Puede descargar el instalador de las herramientas del kit de recursos desde el centro de descarga en [https://go.microsoft.com/fwlink/p/?LinkID=330429](https://go.microsoft.com/fwlink/p/?linkid=330429) .</span><span class="sxs-lookup"><span data-stu-id="7a9eb-110">You can download the Resource Kit Tools installer from the Download Center at [https://go.microsoft.com/fwlink/p/?LinkID=330429](https://go.microsoft.com/fwlink/p/?linkid=330429).</span></span>

<span data-ttu-id="7a9eb-111">Ejecute **OCSResKit.msi** para realizar una instalación sencilla.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-111">Run **OCSResKit.msi** to do a simple installation.</span></span> <span data-ttu-id="7a9eb-112">El archivo. msi instala todas las herramientas en la siguiente ruta de acceso: **% Program Files% \\ Microsoft Lync Server 2013 \\ reskit**.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-112">The .msi installs all the tools in the following path: **%Program Files%\\Microsoft Lync Server 2013\\ResKit**.</span></span> <span data-ttu-id="7a9eb-113">Las herramientas que son ejecutables independientes se encuentran en esta carpeta.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-113">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="7a9eb-114">Las herramientas que también tienen archivos se encuentran en sus propias subcarpetas.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-114">Tools that also have files are in their own subfolders.</span></span>

</div>

<div>

## <a name="supported-environments"></a><span data-ttu-id="7a9eb-115">Entornos compatibles</span><span class="sxs-lookup"><span data-stu-id="7a9eb-115">Supported Environments</span></span>

<span data-ttu-id="7a9eb-116">Para obtener un rendimiento óptimo, debe instalar las herramientas del kit de recursos de Lync Server 2013 en el mismo entorno y con las mismas especificaciones necesarias para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-116">For optimal performance, the Lync Server 2013, Resource Kit Tools should be installed in the same environment and with the same specifications that are required for Lync Server 2013.</span></span>

</div>

<div>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="7a9eb-117">Introducción a las herramientas del kit de recursos</span><span class="sxs-lookup"><span data-stu-id="7a9eb-117">Resource Kit Tools Overview</span></span>

<span data-ttu-id="7a9eb-118">En la siguiente lista se describen las herramientas que se proporcionan en el kit de recursos de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-118">The following list describes the tools that are provided in the Lync Server 2013 Resource Kit.</span></span> <span data-ttu-id="7a9eb-119">En la siguiente sección se describe una descripción de cada herramienta, incluidos los requisitos y el uso de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-119">A description of each tool, including the requirements and example usage is covered in the following section.</span></span>

  - <span data-ttu-id="7a9eb-120">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="7a9eb-120">ABSConfig</span></span>

  - <span data-ttu-id="7a9eb-121">Monitor del servicio de directiva de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="7a9eb-121">Bandwidth Policy Service Monitor</span></span>

  - <span data-ttu-id="7a9eb-122">Analizador de uso de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="7a9eb-122">Bandwidth Utilization Analyzer</span></span>

  - <span data-ttu-id="7a9eb-123">Llamar a Parkometer</span><span class="sxs-lookup"><span data-stu-id="7a9eb-123">Call Parkometer</span></span>

  - <span data-ttu-id="7a9eb-124">CleanupStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="7a9eb-124">CleanupStorageServiceData</span></span>

  - <span data-ttu-id="7a9eb-125">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="7a9eb-125">DBAnalyze</span></span>

  - <span data-ttu-id="7a9eb-126">ImportStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="7a9eb-126">ImportStorageServiceData</span></span>

  - <span data-ttu-id="7a9eb-127">LCSSync</span><span class="sxs-lookup"><span data-stu-id="7a9eb-127">LCSSync</span></span>

  - <span data-ttu-id="7a9eb-128">LookupUserConsole</span><span class="sxs-lookup"><span data-stu-id="7a9eb-128">LookupUserConsole</span></span>

  - <span data-ttu-id="7a9eb-129">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="7a9eb-129">MsTurnPing</span></span>

  - <span data-ttu-id="7a9eb-130">Visor de configuración de red</span><span class="sxs-lookup"><span data-stu-id="7a9eb-130">Network Configuration Viewer</span></span>

  - <span data-ttu-id="7a9eb-131">Response Group Agent Live</span><span class="sxs-lookup"><span data-stu-id="7a9eb-131">Response Group Agent Live</span></span>

  - <span data-ttu-id="7a9eb-132">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="7a9eb-132">SEFAUtil</span></span>

  - <span data-ttu-id="7a9eb-133">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="7a9eb-133">SYSPrep.ps1</span></span>

  - <span data-ttu-id="7a9eb-134">Número de anuncios no asignados a la migración</span><span class="sxs-lookup"><span data-stu-id="7a9eb-134">Unassigned Number Announcements Migration</span></span>

  - <span data-ttu-id="7a9eb-135">Datos de conf de Web</span><span class="sxs-lookup"><span data-stu-id="7a9eb-135">Web Conf Data</span></span>

</div>

<div>

## <a name="absconfig"></a><span data-ttu-id="7a9eb-136">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="7a9eb-136">ABSConfig</span></span>

<span data-ttu-id="7a9eb-137">La herramienta de configuración del servicio de libreta de direcciones (ABSConfig) es una herramienta administrativa que ayuda a los administradores a personalizar la configuración del servicio de libreta de direcciones en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-137">The Address Book Service Configuration tool (ABSConfig) is an administrative tool that helps administrators customize Address Book Service configuration in Lync Server 2013.</span></span> <span data-ttu-id="7a9eb-138">Esta herramienta también permite a los administradores de Lync Server 2013 restaurar la configuración predeterminada del servicio de libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-138">This tool also enables Lync Server 2013 administrators to restore the default Address Book Service settings.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="7a9eb-139">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a9eb-139">Description</span></span>

<span data-ttu-id="7a9eb-140">ABSConfig es una aplicación de interfaz de usuario gráfica que permite a los administradores configurar los atributos de servicios de dominio de Active Directory relacionados con el servicio de libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-140">ABSConfig is a graphical user interface application that enables administrators to configure Active Directory Domain Services attributes that are related to Address Book Service.</span></span>

<span data-ttu-id="7a9eb-141">Los escenarios principales de la herramienta son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="7a9eb-141">The primary scenarios for the tool are the following:</span></span>

  - <span data-ttu-id="7a9eb-142">Permitir a los administradores asignar atributos en los servicios de dominio de Active Directory a los atributos para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-142">To enable administrators to map attributes in Active Directory Domain Services to the attributes for Lync Server 2013.</span></span>

  - <span data-ttu-id="7a9eb-143">Permitir a los administradores especificar el atributo de servicios de dominio de Active Directory que se va a incluir o excluir en los archivos del servicio de libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-143">To enable administrators to specify the Active Directory Domain Services attribute to be included or excluded in the Address Book Service files.</span></span>

  - <span data-ttu-id="7a9eb-144">Para permitir a los administradores restaurar la configuración predeterminada del servicio de libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-144">To enable administrators to restore default Address Book Service settings.</span></span>

<span data-ttu-id="7a9eb-145">La herramienta ABSConfig se puede iniciar mediante el archivo absConfig.exe.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-145">The ABSConfig tool can be started by using the absConfig.exe file.</span></span> <span data-ttu-id="7a9eb-146">La herramienta se abre en la ficha **configurar atributos** . Esta tabla tiene opciones para asignar atributos de servicios de dominio de Active Directory a los campos de atributo de Lync Server 2013 y para especificar qué usuarios se deben incluir o excluir en los archivos del servicio de libreta de direcciones basándose en filtros de atributo específicos.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-146">The tool opens to the **Configure Attributes** tab. This table has options to map Active Directory Domain Services attributes to the attribute fields for Lync Server 2013 and to specify which users to include or exclude in Address Book Service files based on specific attribute filters.</span></span> <span data-ttu-id="7a9eb-147">También tiene opciones para personalizar el valor del número de teléfono que se incluirá en el archivo de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-147">It also has options to customize which value of the phone number to be included in the Address Book file.</span></span> <span data-ttu-id="7a9eb-148">La opción **Restaurar valores predeterminados** permite a los administradores restaurar la configuración del servicio de libreta de direcciones en los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-148">The **Restore Defaults** option enables administrators to restore Address Book Service settings to default values.</span></span>

</div>

<div>

## <a name="changes-from-lync-server-2010"></a><span data-ttu-id="7a9eb-149">Cambios de Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="7a9eb-149">Changes from Lync Server 2010</span></span>

<span data-ttu-id="7a9eb-150">En la herramienta de configuración del ABS de Lync Server 2013, es posible quitar atributos (filas) desactivando la casilla "habilitar" del atributo.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-150">In Lync Server 2013 ABS Configuration tool, attributes (rows) may be removed by unchecking the “enable” checkbox for the attribute.</span></span> <span data-ttu-id="7a9eb-151">Esto tiene el mismo efecto que eliminar la fila en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-151">This has the same effect as deleting the row in Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7a9eb-152">La casilla de verificación Habilitar está en la columna situada en el extremo derecho; es posible que deba desplazarse hacia la derecha para ver la columna</span><span class="sxs-lookup"><span data-stu-id="7a9eb-152">The enable checkbox is in the far right column; you may need to scroll right to see the column</span></span>



</div>

</div>

<div>

## <a name="output"></a><span data-ttu-id="7a9eb-153">Output</span><span class="sxs-lookup"><span data-stu-id="7a9eb-153">Output</span></span>

<span data-ttu-id="7a9eb-154">ABSConfig almacena la configuración del servicio de libreta de direcciones en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-154">ABSConfig stores the Address Book Service configuration in the database.</span></span>

    Path: %ProgramFiles%\Microsoft Lync Server 2013\Reskit

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="7a9eb-155">Finalidad</span><span class="sxs-lookup"><span data-stu-id="7a9eb-155">Purpose</span></span>

<span data-ttu-id="7a9eb-156">ABSConfig proporciona una forma rápida y sencilla de personalizar el servicio de libreta de direcciones de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-156">ABSConfig provides a quick and easy way to customize Lync Server 2013 Address Book Service.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="7a9eb-157">Requirements</span><span class="sxs-lookup"><span data-stu-id="7a9eb-157">Requirements</span></span>

<div>

## <a name="computer"></a><span data-ttu-id="7a9eb-158">Equipo</span><span class="sxs-lookup"><span data-stu-id="7a9eb-158">Computer</span></span>

<span data-ttu-id="7a9eb-159">ABSConfig solo puede ejecutarse desde un equipo unido a un dominio que tenga instalado Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-159">ABSConfig can be run only from a domain-joined computer that has Lync Server 2013 installed.</span></span> <span data-ttu-id="7a9eb-160">En el caso de Lync Server 2013, Enterprise Edition, esta herramienta se puede ejecutar en cualquier servidor front-end que tenga habilitado el servicio de libreta de direcciones durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-160">In the case of Lync Server 2013, Enterprise Edition, this tool can be run on any Front End servers that have the Address Book Service enabled during setup.</span></span>

</div>

<div>

## <a name="network"></a><span data-ttu-id="7a9eb-161">Red</span><span class="sxs-lookup"><span data-stu-id="7a9eb-161">Network</span></span>

<span data-ttu-id="7a9eb-162">El equipo debe ser capaz de conectarse al grupo de servidores front-end y a la base de datos back-end.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-162">The computer should be able to connect to the Front End pool and back-end database.</span></span>

</div>

<div>

## <a name="software"></a><span data-ttu-id="7a9eb-163">Software</span><span class="sxs-lookup"><span data-stu-id="7a9eb-163">Software</span></span>

<span data-ttu-id="7a9eb-164">Los siguientes componentes de software deben instalarse antes de ejecutar la herramienta ABSConfig:</span><span class="sxs-lookup"><span data-stu-id="7a9eb-164">The following software components must be installed before running the ABSConfig tool:</span></span>

  - <span data-ttu-id="7a9eb-165">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7a9eb-165">Microsoft Lync Server 2013</span></span>

</div>

<div>

## <a name="users"></a><span data-ttu-id="7a9eb-166">Usuarios</span><span class="sxs-lookup"><span data-stu-id="7a9eb-166">Users</span></span>

<span data-ttu-id="7a9eb-167">Administradores que tienen los permisos necesarios para actualizar la implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-167">Administrators who have the permissions required to update the Lync Server 2013 deployment.</span></span>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="7a9eb-168">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="7a9eb-168">Examples</span></span>

<span data-ttu-id="7a9eb-169">ABSConfig se puede iniciar escribiendo **ABSConfig.exe** en un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-169">ABSConfig can be started by typing **ABSConfig.exe** at a command prompt.</span></span> <span data-ttu-id="7a9eb-170">A continuación se muestra la interfaz de usuario de la herramienta ABSConfig.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-170">Shown below is the ABSConfig tool user interface.</span></span>

<span data-ttu-id="7a9eb-171">![La herramienta de ABSConfig.exe.](images/JJ945604.6fb63a70-7b63-4b8b-b7d1-82fe9aa2028f(OCS.15).jpg "La herramienta de ABSConfig.exe.")</span><span class="sxs-lookup"><span data-stu-id="7a9eb-171">![The ABSConfig.exe tool.](images/JJ945604.6fb63a70-7b63-4b8b-b7d1-82fe9aa2028f(OCS.15).jpg "The ABSConfig.exe tool.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="7a9eb-172">Resumen</span><span class="sxs-lookup"><span data-stu-id="7a9eb-172">Summary</span></span>

<span data-ttu-id="7a9eb-173">La herramienta ABSConfig proporciona a los administradores una herramienta rápida y fácil de usar para personalizar el servicio de libreta de direcciones de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-173">The ABSConfig tool provides administrators a quick and easy to use tool to customize Lync Server 2013 Address Book Service.</span></span>

</div>

</div>

<div>

## <a name="bandwidth-policy-service-monitor"></a><span data-ttu-id="7a9eb-174">Monitor del servicio de directiva de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="7a9eb-174">Bandwidth Policy Service Monitor</span></span>

<span data-ttu-id="7a9eb-175">La herramienta de supervisión del servicio de directiva de ancho de banda está diseñada para permitir a los administradores ver una lista de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="7a9eb-175">The Bandwidth Policy Service Monitor tool is intended to allow administrators to view a list of the following:</span></span>

1.  <span data-ttu-id="7a9eb-176">Todos los servicios de directiva de ancho de banda de Lync Server 2013 (autenticación y núcleo) configurados en la topología</span><span class="sxs-lookup"><span data-stu-id="7a9eb-176">All the configured Lync Server 2013 Bandwidth Policy services (Authentication and Core) in the topology</span></span>

2.  <span data-ttu-id="7a9eb-177">Las conexiones que realiza cada servicio a otros servicios de directiva de ancho de banda y a los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-177">The connections that each service makes to other Bandwidth Policy services and to the Edge servers</span></span>

3.  <span data-ttu-id="7a9eb-178">Todos los vínculos configurados en el documento de configuración de red y el uso de ancho de banda en tiempo real tal y como lo indica cada uno de los servicios de directiva de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="7a9eb-178">All the links that are configured in the Network configuration document and real-time bandwidth usage as reported by each of the Bandwidth Policy services</span></span>

<div>

## <a name="description"></a><span data-ttu-id="7a9eb-179">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a9eb-179">Description</span></span>

<span data-ttu-id="7a9eb-180">La herramienta de supervisión del servicio de directiva de ancho de banda se implementa como una aplicación basada en GUI.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-180">The Bandwidth Policy Service Monitor tool is implemented as a GUI-based application.</span></span> <span data-ttu-id="7a9eb-181">Los administradores inician la herramienta mediante la ejecución de PDPMonUI.exe.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-181">Administrators start the tool by running PDPMonUI.exe.</span></span>

<span data-ttu-id="7a9eb-182">Cuando se inicia la herramienta, intenta descubrir la lista de servicios de directivas de ancho de banda en la topología.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-182">When the tool starts, it attempts to discover the list of Bandwidth Policy services in the topology.</span></span> <span data-ttu-id="7a9eb-183">Una vez realizada la actualización inicial, el panel de la izquierda de la ventana se rellena con una lista de servicios agrupados por los clústeres a los que pertenecen.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-183">After the initial update is done, the pane to the left of the window is populated with a list of services that are grouped by the clusters that they belong to.</span></span>

<span data-ttu-id="7a9eb-184">Cuando los administradores seleccionan un servicio de directiva de ancho de banda en particular, el panel de la derecha muestra la información sobre ese servicio en particular.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-184">When administrators select a particular Bandwidth Policy Service, the pane on the right displays the information about that particular service.</span></span> <span data-ttu-id="7a9eb-185">Ese panel también tiene dos pestañas principales que muestran información.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-185">That pane also has two main tabs that display information.</span></span>

<div>

## <a name="machine-info-tab"></a><span data-ttu-id="7a9eb-186">Ficha información del equipo</span><span class="sxs-lookup"><span data-stu-id="7a9eb-186">Machine Info Tab</span></span>

<span data-ttu-id="7a9eb-187">La ficha **información del equipo** muestra los detalles del servicio de directiva de ancho de banda seleccionado y la lista y el estado de todas las conexiones realizadas por el servicio de directiva de ancho de banda seleccionado a otros servicios.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-187">The **Machine Info** tab shows the details of the Bandwidth Policy Service that is selected and the list and state of all the connections that are made by the selected Bandwidth Policy Service to other services.</span></span>

</div>

<div>

## <a name="topology-info-tab"></a><span data-ttu-id="7a9eb-188">Pestaña información de topología</span><span class="sxs-lookup"><span data-stu-id="7a9eb-188">Topology Info Tab</span></span>

<span data-ttu-id="7a9eb-189">La ficha **información de topología** muestra una lista de todos los vínculos que se configuran en las opciones de configuración de red.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-189">The **Topology Info** tab shows a list of all the links that are configured in the Network configuration settings.</span></span> <span data-ttu-id="7a9eb-190">Para cada vínculo, se muestra la capacidad de ancho de banda de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-190">For each link, the audio and video bandwidth capacity is displayed.</span></span> <span data-ttu-id="7a9eb-191">Además, se muestra el ancho de banda utilizado actualmente, tanto en Kbps como en un porcentaje de la capacidad.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-191">Additionally, the currently utilized bandwidth is displayed, both in Kbps and as a percentage of the capacity.</span></span> <span data-ttu-id="7a9eb-192">La herramienta usa código de colores para resaltar los vínculos que tienen un uso similar al de la capacidad, lo que permite a los administradores aislar rápidamente estos vínculos.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-192">The tool uses color-coding to highlight links that have utilization that is close to the capacity—this allows administrators to quickly isolate such links.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7a9eb-193">Si la herramienta de supervisión del servicio de directiva de ancho de banda experimenta errores cuando se conecta a cualquiera de los servicios de directiva de ancho de banda configurados, la información de las fichas información del <STRONG>equipo</STRONG> y información de la <STRONG>topología</STRONG> no se rellenará.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-193">If the Bandwidth Policy Service Monitor tool experiences failure when it connects to any of the configured Bandwidth Policy services, the information in the <STRONG>Machine Info</STRONG> and the <STRONG>Topology Info</STRONG> tabs won’t be populated.</span></span> <span data-ttu-id="7a9eb-194">Sin embargo, es posible que la herramienta se conecte inicialmente pero que pierda su conexión al servicio.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-194">However, it is possible that the tool might connect initially but subsequently lose its connection to the service.</span></span> <span data-ttu-id="7a9eb-195">En estos casos, los administradores pueden ver información obsoleta.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-195">In such cases, administrators might see outdated information.</span></span> <span data-ttu-id="7a9eb-196">Hay una marca de hora de <STRONG>última actualización</STRONG> en cada una de las pestañas que permite a los administradores ver cuándo se actualizó por última vez los datos de un servicio de directivas de ancho de banda determinado.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-196">There is a <STRONG>Last Updated</STRONG> time stamp on each of the tabs that can allow administrators to see when the data was last updated for a particular Bandwidth Policy Service.</span></span>



</div>

</div>

</div>

<div>

## <a name="output"></a><span data-ttu-id="7a9eb-197">Output</span><span class="sxs-lookup"><span data-stu-id="7a9eb-197">Output</span></span>

<span data-ttu-id="7a9eb-198">No hay resultados en la línea de comandos; la salida del programa está contenida en la interfaz gráfica de usuario (GUI) principal.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-198">There is no command-line output; the program output is contained within the main graphical user interface (GUI).</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="7a9eb-199">Finalidad</span><span class="sxs-lookup"><span data-stu-id="7a9eb-199">Purpose</span></span>

<span data-ttu-id="7a9eb-200">La finalidad de la herramienta de supervisión del servicio de directiva de ancho de banda es permitir a los administradores ver el estado de cada uno de los servicios de directivas de ancho de banda que se definen en la topología.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-200">The purpose of the Bandwidth Policy Service Monitor tool is to allow administrators visibility into the state of each of the Bandwidth Policy services that are defined in the topology.</span></span> <span data-ttu-id="7a9eb-201">Además, los administradores pueden ver el uso de ancho de banda en tiempo real para todos los vínculos definidos en el documento de configuración de red.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-201">In addition, administrators can see real-time bandwidth usage for all the links that are defined in the Network configuration document.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="7a9eb-202">Requirements</span><span class="sxs-lookup"><span data-stu-id="7a9eb-202">Requirements</span></span>

<span data-ttu-id="7a9eb-203">La herramienta de supervisión del servicio de directiva de ancho de banda debe ejecutarse en un equipo que forme parte de la topología de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-203">The Bandwidth Policy Service Monitor tool needs to be run on a computer that is part of the Lync Server topology.</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="7a9eb-204">Resumen</span><span class="sxs-lookup"><span data-stu-id="7a9eb-204">Summary</span></span>

<span data-ttu-id="7a9eb-205">La herramienta de supervisión del servicio de directiva de ancho de banda puede ser un recurso valioso para los administradores, de modo que puedan inspeccionar el estado de todos los servicios de directivas de ancho de banda de la topología y, lo que sea más importante, puedan obtener un uso de ancho de banda en tiempo real para los vínculos definidos en las opciones de configuración de red.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-205">The Bandwidth Policy Service Monitor tool can be a valuable resource to administrators so they can inspect the state of all the Bandwidth Policy services in the topology—and more importantly—they can obtain real-time bandwidth utilization for the links that are defined in the Network configuration settings.</span></span>

</div>

</div>

<div>

## <a name="bandwidth-utilization-analyzer"></a><span data-ttu-id="7a9eb-206">Analizador de uso de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="7a9eb-206">Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="7a9eb-207">El analizador de uso de ancho de banda es una herramienta que crea informes sobre diversas vistas de consumo de ancho de banda por los puntos de conexión de UC a través de vínculos WAN en la red empresarial.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-207">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network.</span></span> <span data-ttu-id="7a9eb-208">Estos informes se pueden usar para comprender el patrón de consumo de ancho de banda actual y para ayudar a planear la capacidad de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-208">These reports can be used to understand the current bandwidth consumption pattern and to aid in bandwidth capacity planning.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="7a9eb-209">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a9eb-209">Description</span></span>

<span data-ttu-id="7a9eb-210">El analizador de uso de ancho de banda se implementa como una aplicación basada en la interfaz gráfica de usuario.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-210">Bandwidth Utilization Analyzer is implemented as a GUI-based application.</span></span> <span data-ttu-id="7a9eb-211">Esta herramienta genera informes específicos para el uso de audio en la red y ayuda a planear la capacidad.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-211">This tool generates reports specifically for audio utilization across the network and helps with capacity planning.</span></span> <span data-ttu-id="7a9eb-212">También recorre en iteración la capacidad de ancho de banda asignada a varios vínculos.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-212">It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="7a9eb-213">Output</span><span class="sxs-lookup"><span data-stu-id="7a9eb-213">Output</span></span>

<span data-ttu-id="7a9eb-214">El analizador de uso de ancho de banda proporciona gráficos al al de la capacidad de ancho de banda y utilización de audio para todos los vínculos WAN configurados en el sistema.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-214">Bandwidth Utilization Analyzer provides graphic al plots of bandwidth capacity and utilization for audio for all the WAN links that are configured in the system.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="7a9eb-215">Finalidad</span><span class="sxs-lookup"><span data-stu-id="7a9eb-215">Purpose</span></span>

<span data-ttu-id="7a9eb-216">En cualquier implementación de voz y vídeo, es fundamental supervisar y comprender la tendencia del uso de ancho de banda del tráfico multimedia en toda la red de la empresa.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-216">In any voice and video deployment, it’s critical to monitor and understand the trend of bandwidth utilization of media traffic across the enterprise network.</span></span> <span data-ttu-id="7a9eb-217">La herramienta analizador de uso de ancho de banda permite que un administrador logre exactamente eso.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-217">The Bandwidth Utilization Analyzer tool allows an administrator to achieve just that.</span></span> <span data-ttu-id="7a9eb-218">Esta herramienta hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7a9eb-218">This tool does the following:</span></span>

  - <span data-ttu-id="7a9eb-219">Genera informes específicos para el uso de audio en la red</span><span class="sxs-lookup"><span data-stu-id="7a9eb-219">Generates specific reports for audio utilization across the network</span></span>

  - <span data-ttu-id="7a9eb-220">Ayuda a planear y iterar la capacidad con mayor eficacia en la capacidad de ancho de banda asignada a varios vínculos</span><span class="sxs-lookup"><span data-stu-id="7a9eb-220">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="7a9eb-221">El analizador de uso de ancho de banda puede generar trazados gráficos de la capacidad de ancho de banda e informes de utilización; son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="7a9eb-221">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and utilization reports; they are as follows:</span></span>

  - <span data-ttu-id="7a9eb-222">Todos los vínculos WAN en la red empresarial</span><span class="sxs-lookup"><span data-stu-id="7a9eb-222">All the WAN links in the enterprise network</span></span>

  - <span data-ttu-id="7a9eb-223">Filtrados por los vínculos WAN seleccionados que se han elegido</span><span class="sxs-lookup"><span data-stu-id="7a9eb-223">Filtered by selected WAN links that have been chosen</span></span>

  - <span data-ttu-id="7a9eb-224">Filtrados por los vínculos WAN que han superado la capacidad de vínculo</span><span class="sxs-lookup"><span data-stu-id="7a9eb-224">Filtered by WAN links that have exceeded link capacity</span></span>

  - <span data-ttu-id="7a9eb-225">Filtrados por los vínculos WAN que han estado bajo el uso del ancho de banda aprovisionado</span><span class="sxs-lookup"><span data-stu-id="7a9eb-225">Filtered by WAN links that have been under-utilizing the provisioned bandwidth</span></span>

  - <span data-ttu-id="7a9eb-226">Filtra por vínculos WAN que han alcanzado niveles críticos (un uso de ancho de banda superior al 90% de la capacidad de ancho de banda del vínculo WAN)</span><span class="sxs-lookup"><span data-stu-id="7a9eb-226">Filter by WAN links that have been reaching critical levels (a bandwidth utilization that is greater than 90% of bandwidth capacity of the WAN link)</span></span>

  - <span data-ttu-id="7a9eb-227">Filtrados por tipo de vínculo WAN: vínculos de sitios de red, vínculos interregionales y vínculos dentro de un sitio</span><span class="sxs-lookup"><span data-stu-id="7a9eb-227">Filtered by WAN link type—network-site links, interregional links, and links within a site</span></span>

  - <span data-ttu-id="7a9eb-228">Filtrados por región de red</span><span class="sxs-lookup"><span data-stu-id="7a9eb-228">Filtered by network region</span></span>

<div>

## <a name="applications"></a><span data-ttu-id="7a9eb-229">Aplicaciones</span><span class="sxs-lookup"><span data-stu-id="7a9eb-229">Applications</span></span>

<span data-ttu-id="7a9eb-230">El analizador de uso de ancho de banda tiene las dos aplicaciones siguientes (herramientas):</span><span class="sxs-lookup"><span data-stu-id="7a9eb-230">Bandwidth Utilization Analyzer has the following two applications (tools):</span></span>

  - <span data-ttu-id="7a9eb-231">**WanLinkLogCollector.exe**     Esta herramienta permite al usuario especificar la información necesaria.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-231">**WanLinkLogCollector.exe**   This tool enables its user to input the required information.</span></span>

  - <span data-ttu-id="7a9eb-232">**BandwidthUtilizationAnalyzer.xlsm**    WanLinkLogCollector.exe inicia automáticamente un informe de software de hoja de cálculo de Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-232">**BandwidthUtilizationAnalyzer.xlsm**  A Microsoft Excel spreadsheet software report is automatically launched by WanLinkLogCollector.exe.</span></span> <span data-ttu-id="7a9eb-233">Esta aplicación permite al usuario aplicar filtros al informe, tal como se muestra más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-233">This application allows the user to apply filters to the report as shown later in this article.</span></span>

</div>

<div>

## <a name="phases-of-using-bandwidth-utilization-analyzer"></a><span data-ttu-id="7a9eb-234">Fases del uso del analizador de uso de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="7a9eb-234">Phases of Using Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="7a9eb-235">Hay dos fases al usar el analizador de uso de ancho de banda:</span><span class="sxs-lookup"><span data-stu-id="7a9eb-235">There are two phases when using Bandwidth Utilization Analyzer:</span></span>

  - <span data-ttu-id="7a9eb-236">Recopilar registros, que se realiza mediante WanLinkLogCollector.exe</span><span class="sxs-lookup"><span data-stu-id="7a9eb-236">Collect logs, which is performed by using WanLinkLogCollector.exe</span></span>

  - <span data-ttu-id="7a9eb-237">Personalización de informes, que se realiza con BandwidthUtilizationAnalyzer.xlsm</span><span class="sxs-lookup"><span data-stu-id="7a9eb-237">Customize reports, which is performed by using BandwidthUtilizationAnalyzer.xlsm</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7a9eb-238">Se recomienda encarecidamente que BandwidthUtilizationAnalyzer.xlsm no sea iniciado manualmente por los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-238">We strongly recommend that BandwidthUtilizationAnalyzer.xlsm not be manually launched by end users.</span></span>



</div>

</div>

<div>

## <a name="starting-bandwidth-utilization-analyzer"></a><span data-ttu-id="7a9eb-239">Inicio del analizador de uso de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="7a9eb-239">Starting Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="7a9eb-240">Inicie WanLinkLogCollector.exe en el símbolo del sistema o con el explorador de Windows.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-240">Start WanLinkLogCollector.exe at the command prompt or by using Windows Explorer.</span></span>

<span data-ttu-id="7a9eb-241">**Uso de WanLinkLogCollector.exe**</span><span class="sxs-lookup"><span data-stu-id="7a9eb-241">**Using WanLinkLogCollector.exe**</span></span>

<span data-ttu-id="7a9eb-242">Hay tres pasos para usar WanLinkLogCollector.exe:</span><span class="sxs-lookup"><span data-stu-id="7a9eb-242">There are three steps to using WanLinkLogCollector.exe:</span></span>

1.  <span data-ttu-id="7a9eb-243">**Registrar la escala de tiempo**     Proporcionar la escala de tiempo que debe generarse el informe para</span><span class="sxs-lookup"><span data-stu-id="7a9eb-243">**Log the timeline**   Provide the timeline that the report needs to be generated for</span></span>

2.  <span data-ttu-id="7a9eb-244">**Especificar los directorios**     de archivos Proporcionar información de ubicación de archivos</span><span class="sxs-lookup"><span data-stu-id="7a9eb-244">**Specify the file directories**   Provide file location information</span></span>

3.  <span data-ttu-id="7a9eb-245">**Recopilar los registros e iniciar el visor**    de informes Ejecutar el comando para generar el informe</span><span class="sxs-lookup"><span data-stu-id="7a9eb-245">**Collect the logs and launch the report viewer**  Execute the command to generate the report</span></span>

<div>

## <a name="step-1---log-the-timeline"></a><span data-ttu-id="7a9eb-246">Paso 1: registrar la escala de tiempo</span><span class="sxs-lookup"><span data-stu-id="7a9eb-246">Step 1 - Log the timeline</span></span>

<span data-ttu-id="7a9eb-247">El registro de la escala de tiempo permite que el usuario de la herramienta especifique lo siguiente, tal como se muestra en la figura siguiente.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-247">Logging the timeline allows the tool user to specify the following as shown in the figure below.</span></span>

1.  <span data-ttu-id="7a9eb-248">**Fecha de inicio** Esta es la fecha de inicio de la escala de tiempo para la que se generará el informe; por ejemplo, 1 de agosto de 2010.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-248">**Start date** This is the start date of the timeline that the report is to be generated for; for example, August 1, 2010.</span></span>

2.  <span data-ttu-id="7a9eb-249">**Fecha de finalización** Esta es la fecha de finalización de la escala de tiempo para la que se generará el informe; por ejemplo, 30 de septiembre de 2010.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-249">**End date** This is the end date of the timeline that the report is to be generated for; for example, September 30, 2010.</span></span>
    
    <span data-ttu-id="7a9eb-250">![Fechas de inicio y finalización en el uso del ancho de banda](images/JJ945604.2c597cfc-3372-4d41-816b-26202f607ad8(OCS.15).jpg "Fechas de inicio y finalización en el uso del ancho de banda")</span><span class="sxs-lookup"><span data-stu-id="7a9eb-250">![Start and End dates in the Bandwidth Utilization A](images/JJ945604.2c597cfc-3372-4d41-816b-26202f607ad8(OCS.15).jpg "Start and End dates in the Bandwidth Utilization A")</span></span>  

</div>

<div>

## <a name="step-2---specify-the-file-directories"></a><span data-ttu-id="7a9eb-251">Paso 2: especificar los directorios de archivos</span><span class="sxs-lookup"><span data-stu-id="7a9eb-251">Step 2 - Specify the file directories</span></span>

<span data-ttu-id="7a9eb-252">El usuario puede especificar los siguientes directorios de archivos, tal y como se muestra.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-252">The following file directories can be specified by the user as shown.</span></span>

  - <span data-ttu-id="7a9eb-253">**Ubicación de los archivos de registro del servidor** La ubicación de la carpeta donde se almacenan los registros del servidor de directivas de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-253">**Server log files location** The folder location where Bandwidth policy server logs are stored.</span></span> <span data-ttu-id="7a9eb-254">Suele estar en \<fileserver\> \\ \<choice of FE\> \\ PDP de AppServerFiles \\ .</span><span class="sxs-lookup"><span data-stu-id="7a9eb-254">This is typically in \<fileserver\>\\\<choice of FE\>\\AppServerFiles\\PDP.</span></span>

  - <span data-ttu-id="7a9eb-255">**Ubicación de almacenamiento de archivos temporales** Ubicación del archivo temporal donde se almacenan los archivos intermedios mientras se genera el informe.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-255">**Temporary file storage location** The temporary file location where intermediate files are stored while the report is being generated.</span></span>

<span data-ttu-id="7a9eb-256">![Directorios de archivos en el banda de uso de ancho de banda](images/JJ945604.d66daeac-1669-45e3-932d-3f6782840c2a(OCS.15).jpg "Directorios de archivos en el banda de uso de ancho de banda")</span><span class="sxs-lookup"><span data-stu-id="7a9eb-256">![File directories in the Bandwidth Utilization Anal](images/JJ945604.d66daeac-1669-45e3-932d-3f6782840c2a(OCS.15).jpg "File directories in the Bandwidth Utilization Anal")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7a9eb-257">Asegúrese de que el acceso a los registros del servidor y la carpeta de almacén de archivos temporales sea suficiente para el usuario de la herramienta.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-257">Ensure that sufficient file access to the server logs and the temporary file store folder is provided to the tool user.</span></span>



</div>

</div>

<div>

## <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a><span data-ttu-id="7a9eb-258">Paso 3: recopilar los registros e iniciar el visor de informes</span><span class="sxs-lookup"><span data-stu-id="7a9eb-258">Step 3 - Collect the logs and start the report viewer</span></span>

<span data-ttu-id="7a9eb-259">Para recopilar los registros e iniciar el visor de informes, haga clic en **Ejecutar** como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-259">To collect the logs and start the report viewer, click **Execute** as shown below.</span></span> <span data-ttu-id="7a9eb-260">Este paso recopila los datos necesarios.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-260">This step collects the required data.</span></span>

<span data-ttu-id="7a9eb-261">![Recopilar datos en el banda de uso de ancho de banda](images/JJ945604.0019cb2c-7c01-4dc9-ac90-ac47c47d1bfd(OCS.15).jpg "Recopilar datos en el banda de uso de ancho de banda")</span><span class="sxs-lookup"><span data-stu-id="7a9eb-261">![Collecting data in the Bandwidth Utilization Analy](images/JJ945604.0019cb2c-7c01-4dc9-ac90-ac47c47d1bfd(OCS.15).jpg "Collecting data in the Bandwidth Utilization Analy")</span></span>

<span data-ttu-id="7a9eb-262">Cuando la validación de entrada es correcta, se muestra el mensaje que se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-262">When the input validation is successful, the message shown below is displayed.</span></span>

<span data-ttu-id="7a9eb-263">![Registros recopilados de la notificación en el uso de ancho de banda](images/JJ945604.eda91da8-3285-4eab-8ccb-c6d89c8cc221(OCS.15).jpg "Registros recopilados de la notificación en el uso de ancho de banda")</span><span class="sxs-lookup"><span data-stu-id="7a9eb-263">![Logs collected notification in the Bandwidth Utili](images/JJ945604.eda91da8-3285-4eab-8ccb-c6d89c8cc221(OCS.15).jpg "Logs collected notification in the Bandwidth Utili")</span></span>

<span data-ttu-id="7a9eb-264">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-264">Click **OK**.</span></span> <span data-ttu-id="7a9eb-265">BandwidthUtilizationAnalyzer.xlsm se inicia automáticamente.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-265">BandwidthUtilizationAnalyzer.xlsm is automatically started.</span></span> <span data-ttu-id="7a9eb-266">Siga las instrucciones del cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-266">Follow the instructions in the message box.</span></span> <span data-ttu-id="7a9eb-267">Para obtener información detallada, consulte **Using BandwidthUtilizationAnalyzer.xlsm** en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-267">For details, see **Using BandwidthUtilizationAnalyzer.xlsm** in the next section.</span></span>

</div>

<div>


<span data-ttu-id="7a9eb-268">**Uso de BandwidthUtilizationAnalyzer.xlsm**</span><span class="sxs-lookup"><span data-stu-id="7a9eb-268">**Using BandwidthUtilizationAnalyzer.xlsm**</span></span>

1.  <span data-ttu-id="7a9eb-269">Cuando se inicie BandwidthUtilizationAnalyzer.xlsm automáticamente, haga clic en **Actualizar** como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-269">When BandwidthUtilizationAnalyzer.xlsm is automatically started, click **Refresh** as shown below.</span></span>
    
    <span data-ttu-id="7a9eb-270">![BandwidthUtilizationAnalyzer.xlsm](images/JJ945604.c4e675b9-1671-400e-a712-6db82d731b39(OCS.15).jpg "BandwidthUtilizationAnalyzer.xlsm")</span><span class="sxs-lookup"><span data-stu-id="7a9eb-270">![BandwidthUtilizationAnalyzer.xlsm](images/JJ945604.c4e675b9-1671-400e-a712-6db82d731b39(OCS.15).jpg "BandwidthUtilizationAnalyzer.xlsm")</span></span>

2.  <span data-ttu-id="7a9eb-271">Cuando se abre una carpeta de archivos, seleccione consolidated.csv de la ubicación especificada en el cuadro de mensaje como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-271">When a file folder is opened, select consolidated.csv from the location that is specified in the message box as shown below.</span></span> <span data-ttu-id="7a9eb-272">También se muestra la ubicación como **C: \\ temp**.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-272">It also shows the location as **C:\\Temp**.</span></span>
    
    <span data-ttu-id="7a9eb-273">![Abrir una carpeta en BandwidthUtilizationAnalyzer.](images/JJ945604.601cc572-cee9-45fb-9ed1-c4b96a2fa21e(OCS.15).jpg "Abrir una carpeta en BandwidthUtilizationAnalyzer.")</span><span class="sxs-lookup"><span data-stu-id="7a9eb-273">![Opening a folder in BandwidthUtilizationAnalyzer.](images/JJ945604.601cc572-cee9-45fb-9ed1-c4b96a2fa21e(OCS.15).jpg "Opening a folder in BandwidthUtilizationAnalyzer.")</span></span>

3.  <span data-ttu-id="7a9eb-274">Haga clic en **Importar**.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-274">Click **Import**.</span></span>

4.  <span data-ttu-id="7a9eb-275">El trazado gráfico se genera automáticamente.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-275">The graphical plot is automatically generated.</span></span> <span data-ttu-id="7a9eb-276">Está disponible cuando desaparece el puntero de trabajo en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-276">It is available when the working-in-the-background pointer disappears.</span></span>
    
    <span data-ttu-id="7a9eb-277">![Aplicar filtros en la vista informe.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Aplicar filtros en la vista informe.")</span><span class="sxs-lookup"><span data-stu-id="7a9eb-277">![Applying filters in Report View.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Applying filters in Report View.")</span></span>

</div>

<div>

## <a name="applying-filters-to-the-report-view"></a><span data-ttu-id="7a9eb-278">Aplicación de filtros a la vista de informe</span><span class="sxs-lookup"><span data-stu-id="7a9eb-278">Applying Filters to the Report View</span></span>

<span data-ttu-id="7a9eb-279">Los filtros que se pueden aplicar a la vista informes, tal como se muestra a continuación, se describen a continuación:</span><span class="sxs-lookup"><span data-stu-id="7a9eb-279">The filters that can be applied to the report view as shown below are described as follows:</span></span>

<span data-ttu-id="7a9eb-280">![Aplicar filtros en la vista informe.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Aplicar filtros en la vista informe.")</span><span class="sxs-lookup"><span data-stu-id="7a9eb-280">![Applying filters in Report View.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Applying filters in Report View.")</span></span>

1.  <span data-ttu-id="7a9eb-281">**Nombre** de Filtrar por vínculos WAN (el filtro está en el lado derecho del gráfico). El prefijo denota los siguientes tipos de vínculos; Vea el cuadro vertical (azul):</span><span class="sxs-lookup"><span data-stu-id="7a9eb-281">**Name** Filter by WAN links (the filter is on the right side of the graph).The prefix denotes the following link types; see the vertical (blue) box:</span></span>
    
      - <span data-ttu-id="7a9eb-282">**Sitio S** Vínculo WAN de un sitio de red a una región de red</span><span class="sxs-lookup"><span data-stu-id="7a9eb-282">**S Site** The WAN link from a network site to a network region</span></span>
    
      - <span data-ttu-id="7a9eb-283">**Es entre sitios** El vínculo WAN entre dos sitios de red</span><span class="sxs-lookup"><span data-stu-id="7a9eb-283">**IS Inter-Site** The WAN link between two network sites</span></span>
    
      - <span data-ttu-id="7a9eb-284">**R inter-region** El vínculo WAN entre dos regiones de red</span><span class="sxs-lookup"><span data-stu-id="7a9eb-284">**R Inter-Region** The WAN link between two network region</span></span>

2.  <span data-ttu-id="7a9eb-285">**Límite superado** Filtra por vínculos WAN cuyo uso de ancho de banda es mayor que la capacidad de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="7a9eb-285">**Exceeded limit** Filter by WAN links whose bandwidth utilization is more than the bandwidth capacity</span></span>

3.  <span data-ttu-id="7a9eb-286">**Niveles críticos** Filtra por vínculos WAN cuyo uso de ancho de banda ha alcanzado el 90% o más de la capacidad de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="7a9eb-286">**Critical levels** Filter by WAN links whose bandwidth utilization has reached 90% or more than the bandwidth capacity</span></span>

4.  <span data-ttu-id="7a9eb-287">**Subutilizado** Filtra por vínculos WAN cuyo uso de ancho de banda ha sido inferior al 25% de la capacidad de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="7a9eb-287">**Under-utilized** Filter by WAN links whose bandwidth utilization has been less than 25% of the bandwidth capacity</span></span>

5.  <span data-ttu-id="7a9eb-288">**Tipo de vínculo** Filtrar por los siguientes tipos de vínculos WAN:</span><span class="sxs-lookup"><span data-stu-id="7a9eb-288">**Link type** Filter by the following WAN links types:</span></span>
    
      - <span data-ttu-id="7a9eb-289">Tipo de **sitio de red**</span><span class="sxs-lookup"><span data-stu-id="7a9eb-289">**Network site** type</span></span>
    
      - <span data-ttu-id="7a9eb-290">Tipo **entre sitios**</span><span class="sxs-lookup"><span data-stu-id="7a9eb-290">**Inter-site** type</span></span>
    
      - <span data-ttu-id="7a9eb-291">Tipo **de vínculo entre regiones**</span><span class="sxs-lookup"><span data-stu-id="7a9eb-291">**Inter-Region link** type</span></span>

6.  <span data-ttu-id="7a9eb-292">**Región** Filtrar por región de red</span><span class="sxs-lookup"><span data-stu-id="7a9eb-292">**Region** Filter by network region</span></span>

<span data-ttu-id="7a9eb-293">Las figuras siguientes muestran los filtros descritos anteriormente.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-293">The following figures show the previously described filters.</span></span>

<span data-ttu-id="7a9eb-294">Filtrar por **nombre**.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-294">Filter by **Name**.</span></span> <span data-ttu-id="7a9eb-295">Seleccione la lista de vínculos que deben mostrarse en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-295">Select the list of links that need to be displayed in the graph.</span></span>

<span data-ttu-id="7a9eb-296">![Filtrado por nombre en BandwidthUtilizationAnalyzer.](images/JJ945604.002b7c8e-f0da-48ce-9e1a-5c34d2cab063(OCS.15).jpg "Filtrado por nombre en BandwidthUtilizationAnalyzer.")</span><span class="sxs-lookup"><span data-stu-id="7a9eb-296">![Filtering by Name in BandwidthUtilizationAnalyzer.](images/JJ945604.002b7c8e-f0da-48ce-9e1a-5c34d2cab063(OCS.15).jpg "Filtering by Name in BandwidthUtilizationAnalyzer.")</span></span>

<span data-ttu-id="7a9eb-297">Filtrar por **límite superado**.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-297">Filter by **Exceeded limit**.</span></span> <span data-ttu-id="7a9eb-298">Seleccione **true** para aplicar el filtro.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-298">Select **True** to enforce the filter.</span></span>

<span data-ttu-id="7a9eb-299">![Filtrado por límite superado.](images/JJ945604.5946c95e-76ce-46ca-8f3e-a79be1e5c527(OCS.15).jpg "Filtrado por límite superado.")</span><span class="sxs-lookup"><span data-stu-id="7a9eb-299">![Filtering by Exceeded Limit.](images/JJ945604.5946c95e-76ce-46ca-8f3e-a79be1e5c527(OCS.15).jpg "Filtering by Exceeded Limit.")</span></span>

<span data-ttu-id="7a9eb-300">Filtrar por **niveles críticos**.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-300">Filter by **Critical levels**.</span></span> <span data-ttu-id="7a9eb-301">Seleccione **true** para aplicar el filtro.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-301">Select **True** to enforce the filter.</span></span>

<span data-ttu-id="7a9eb-302">![Filtrado por niveles críticos.](images/JJ945604.60771a52-d8ba-4cb9-a02d-d6c888cb5505(OCS.15).jpg "Filtrado por niveles críticos.")</span><span class="sxs-lookup"><span data-stu-id="7a9eb-302">![Filtering by Critical Levels.](images/JJ945604.60771a52-d8ba-4cb9-a02d-d6c888cb5505(OCS.15).jpg "Filtering by Critical Levels.")</span></span>

<span data-ttu-id="7a9eb-303">Filtrar por **en uso**.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-303">Filter by **Under utilized**.</span></span> <span data-ttu-id="7a9eb-304">Seleccione **true** para aplicar el filtro.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-304">Select **True** to enforce the filter.</span></span>

<span data-ttu-id="7a9eb-305">![Filtrado por en uso.](images/JJ945604.95a2bf01-5aba-4927-af47-1ad3c459d791(OCS.15).jpg "Filtrado por en uso.")</span><span class="sxs-lookup"><span data-stu-id="7a9eb-305">![Filtering by Under Utilized.](images/JJ945604.95a2bf01-5aba-4927-af47-1ad3c459d791(OCS.15).jpg "Filtering by Under Utilized.")</span></span>

<span data-ttu-id="7a9eb-306">Filtra por **tipo de vínculo**.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-306">Filter by **Link Type**.</span></span> <span data-ttu-id="7a9eb-307">Seleccione el tipo o tipos que deben mostrarse.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-307">Select the type or types that need to be displayed.</span></span>

<span data-ttu-id="7a9eb-308">![Filtrado por tipo de vínculo.](images/JJ945604.08757949-06bd-4cf3-809f-d81fd23a6639(OCS.15).jpg "Filtrado por tipo de vínculo.")</span><span class="sxs-lookup"><span data-stu-id="7a9eb-308">![Filtering by Link Type.](images/JJ945604.08757949-06bd-4cf3-809f-d81fd23a6639(OCS.15).jpg "Filtering by Link Type.")</span></span>

<span data-ttu-id="7a9eb-309">Filtrar por **región**.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-309">Filter by **Region**.</span></span> <span data-ttu-id="7a9eb-310">Seleccione una lista de regiones cuyos vínculos se deben mostrar.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-310">Select a list of regions whose links need to be displayed.</span></span>

<span data-ttu-id="7a9eb-311">![Filtrado por región.](images/JJ945604.5de4cec4-6c09-48bb-98c7-b56f7bdb3d5a(OCS.15).jpg "Filtrado por región.")</span><span class="sxs-lookup"><span data-stu-id="7a9eb-311">![Filtering by Region.](images/JJ945604.5de4cec4-6c09-48bb-98c7-b56f7bdb3d5a(OCS.15).jpg "Filtering by Region.")</span></span>

</div>

</div>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="7a9eb-312">Requirements</span><span class="sxs-lookup"><span data-stu-id="7a9eb-312">Requirements</span></span>

  - <span data-ttu-id="7a9eb-313">.NET Framework 3,5</span><span class="sxs-lookup"><span data-stu-id="7a9eb-313">The .NET Framework 3.5</span></span>

  - <span data-ttu-id="7a9eb-314">Microsoft Excel 2010 o Excel 2007</span><span class="sxs-lookup"><span data-stu-id="7a9eb-314">Microsoft Excel 2010 or Excel 2007</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="7a9eb-315">Resumen</span><span class="sxs-lookup"><span data-stu-id="7a9eb-315">Summary</span></span>

<span data-ttu-id="7a9eb-316">El analizador de uso de ancho de banda se usa para trazar el uso del ancho de banda de audio para tráfico de comunicaciones unificadas en la red.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-316">Bandwidth Utilization Analyzer is used to plot the audio bandwidth utilization for UC traffic across the network.</span></span> <span data-ttu-id="7a9eb-317">Esta herramienta se puede usar también para informar del uso de ancho de banda de vídeo en la red.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-317">This tool can be used to report the utilization of video bandwidth on the network as well.</span></span>

</div>

</div>

<div>

## <a name="call-parkometer"></a><span data-ttu-id="7a9eb-318">Llamar a Parkometer</span><span class="sxs-lookup"><span data-stu-id="7a9eb-318">Call Parkometer</span></span>

<span data-ttu-id="7a9eb-319">Call Parkometer es una aplicación de línea de comandos que proporciona acceso sencillo a la base de datos de órbitas de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-319">Call Parkometer is a command-line application that provides easy access to the Call Park orbit database.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="7a9eb-320">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a9eb-320">Description</span></span>

<span data-ttu-id="7a9eb-321">Call Parkometer es una herramienta para realizar un seguimiento de las llamadas estacionadas actualmente.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-321">Call Parkometer is a tool to track currently parked calls.</span></span> <span data-ttu-id="7a9eb-322">También recopila estadísticas sobre las órbitas y el uso del servidor de estacionamiento de llamadas (CPS).</span><span class="sxs-lookup"><span data-stu-id="7a9eb-322">It also collects statistics about orbits and Call Park Server (CPS) usage.</span></span> <span data-ttu-id="7a9eb-323">Esta herramienta de línea de comandos proporciona acceso de lectura y escritura a la base de datos de SQL Server de CPS de la órbita desde un equipo conectado local o remoto.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-323">This command-line tool provides both read and write-access to the CPS orbit SQL Server database from a local or remotely connected computer.</span></span>

<span data-ttu-id="7a9eb-324">Todas las opciones se excluyen mutuamente.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-324">All options are mutually exclusive.</span></span> <span data-ttu-id="7a9eb-325">La sintaxis de la línea de comandos es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="7a9eb-325">Command-line syntax is as follows:</span></span>

  - <span data-ttu-id="7a9eb-326">parámetro **– o** : enumera todos los intervalos de órbita configurados para este grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-326">**–o** parameter—lists all orbit ranges configured for this pool.</span></span>

  - <span data-ttu-id="7a9eb-327">parámetro **– n** : enumera todas las órbitas usadas actualmente en este grupo.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-327">**–n** parameter—lists all currently used orbits in this pool.</span></span> <span data-ttu-id="7a9eb-328">La información mostrada es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="7a9eb-328">The information displayed is as follows:</span></span>
    
      - <span data-ttu-id="7a9eb-329">Identificador uniforme de recursos (URI) de SIP del parque y Estacionador.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-329">SIP Uniform Resource Identifier (URI) of the parkee and parker.</span></span>
    
      - <span data-ttu-id="7a9eb-330">Nombre de host de la CPS donde se estaciona la llamada.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-330">Host name of the CPS where the call is parked.</span></span>
    
      - <span data-ttu-id="7a9eb-331">Marca de tiempo del momento en el que se estaciona la llamada.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-331">Time stamp of when the call was parked.</span></span>

  - <span data-ttu-id="7a9eb-332">**– f** parámetro: enumera el número de órbitas libres actualmente en el grupo.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-332">**–f** parameter—lists the number of currently free orbits in the pool.</span></span>

  - <span data-ttu-id="7a9eb-333">\*\*– r \<n\> \*\* parámetro: muestra las \<n\> últimas llamadas estacionadas.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-333">**–r \<n\>** parameter—lists the \<n\> last parked calls.</span></span> <span data-ttu-id="7a9eb-334">La información mostrada es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="7a9eb-334">The information displayed is as follows:</span></span>
    
      - <span data-ttu-id="7a9eb-335">URI del SIP estacionado.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-335">Parkee SIP URI.</span></span>
    
      - <span data-ttu-id="7a9eb-336">URI del SIP Estacionador.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-336">Parker SIP URI.</span></span>
    
      - <span data-ttu-id="7a9eb-337">Nombre de host de la CPS en la que se estaciona la llamada.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-337">Host name of the CPS where the call was parked.</span></span>
    
      - <span data-ttu-id="7a9eb-338">Marca de tiempo de Cuándo se recuperó o se quitó la llamada.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-338">Time stamp of when the call was retrieved or dropped.</span></span>

  - <span data-ttu-id="7a9eb-339">\*\*-t \<n\> \*\* parámetro: comprueba la reserva de una órbita en la base de datos para mostrar la aleatoriedad de los números de órbitas asignados.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-339">**-t\<n\>** parameter - tests reserving an orbit in the database to show the randomness of the assigned orbit numbers.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="7a9eb-340">Output</span><span class="sxs-lookup"><span data-stu-id="7a9eb-340">Output</span></span>

<span data-ttu-id="7a9eb-341">En función de los parámetros de entrada que se especifiquen en un símbolo del sistema, Call Parkometer muestra el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="7a9eb-341">Depending on the input parameters that are specified at a command prompt, Call Parkometer displays the following output:</span></span>

  - <span data-ttu-id="7a9eb-342">Todos los intervalos de órbitas que están configurados para este grupo</span><span class="sxs-lookup"><span data-stu-id="7a9eb-342">All orbit ranges that are configured for this pool</span></span>

  - <span data-ttu-id="7a9eb-343">Llamadas estacionadas actualmente</span><span class="sxs-lookup"><span data-stu-id="7a9eb-343">Currently parked calls</span></span>

  - <span data-ttu-id="7a9eb-344">Número de órbitas libres (disponibles)</span><span class="sxs-lookup"><span data-stu-id="7a9eb-344">Number of free (available) orbits</span></span>

  - <span data-ttu-id="7a9eb-345">Llamadas estacionadas recientemente</span><span class="sxs-lookup"><span data-stu-id="7a9eb-345">Recently parked calls</span></span>

  - <span data-ttu-id="7a9eb-346">Órbitas reservadas para probar valores de órbitas uniformes y aleatorios</span><span class="sxs-lookup"><span data-stu-id="7a9eb-346">Reserved orbits for testing uniform and random orbit values</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="7a9eb-347">Finalidad</span><span class="sxs-lookup"><span data-stu-id="7a9eb-347">Purpose</span></span>

<span data-ttu-id="7a9eb-348">La finalidad de la herramienta CPS es proporcionar acceso desde la línea de comandos a la base de datos de CPS.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-348">The purpose of the CPS tool is to provide command-line access to the CPS database.</span></span> <span data-ttu-id="7a9eb-349">El administrador puede ver el uso de CPS y determinar el número de órbitas asignadas a un grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-349">The administrator can view the CPS usage and determine the number of orbits assigned to a pool.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="7a9eb-350">Requirements</span><span class="sxs-lookup"><span data-stu-id="7a9eb-350">Requirements</span></span>

<span data-ttu-id="7a9eb-351">No hay requisitos si esta herramienta se ejecuta en el mismo equipo que ejecuta CPS.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-351">There are no requirements if this tool is run on the same computer that is running CPS.</span></span> <span data-ttu-id="7a9eb-352">Si esta herramienta se ejecuta en un equipo remoto, la base de datos de SQL Server que usa Lync Server 2013 debe estar configurada para permitir el acceso remoto.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-352">If this tool is run on a remote computer, the SQL Server database used by Lync Server 2013 must be configured to allow remote access.</span></span> <span data-ttu-id="7a9eb-353">Llamar a Parkometer debe configurarse con una cadena de conexión de base de datos de SQL Server para conectarse al servidor SQL Server del grupo.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-353">Call Parkometer must be configured with a SQL Server database connection string to connect to the pool’s SQL Server.</span></span> <span data-ttu-id="7a9eb-354">Esta cadena de conexión de base de datos de SQL Server se define en el archivo de configuración, **parkometer.exe.config**. Debe colocarse en el mismo directorio en el que se encuentra parkometer.exe.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-354">This SQL Server database connection string is defined in the configuration file, **parkometer.exe.config**. It must be placed in the same directory where parkometer.exe is located.</span></span> <span data-ttu-id="7a9eb-355">El siguiente archivo XML es un ejemplo de parkometer.exe.config. Los parámetros que deben configurarse son el nombre de usuario (por ejemplo, administrador de dominio \\ ), la contraseña (por ejemplo, contraseña) y el nombre de host (por ejemplo, mi servidor).</span><span class="sxs-lookup"><span data-stu-id="7a9eb-355">The following XML file is an example of a parkometer.exe.config. The parameters that must be configured are user name (for example, mydomain\\Administrator), password (for example, mypassword), and host name (for example, myserver).</span></span>

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

## <a name="examples"></a><span data-ttu-id="7a9eb-356">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="7a9eb-356">Examples</span></span>

<span data-ttu-id="7a9eb-357">Intervalos de órbita implementados: el parámetro – o muestra todos los intervalos de órbitas que están configurados para este grupo de servidores, tal y como se muestra.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-357">Deployed orbit ranges: the –o parameter lists all orbit ranges that are configured for this pool as shown</span></span>

<span data-ttu-id="7a9eb-358">![Intervalos de órbita en llamada Parkometer.](images/JJ945604.9ede64cb-29d9-4782-a34b-b76c42fbdcad(OCS.15).jpg "Intervalos de órbita en llamada Parkometer.")</span><span class="sxs-lookup"><span data-stu-id="7a9eb-358">![Orbit ranges in Call Parkometer.](images/JJ945604.9ede64cb-29d9-4782-a34b-b76c42fbdcad(OCS.15).jpg "Orbit ranges in Call Parkometer.")</span></span>

<span data-ttu-id="7a9eb-359">Llamadas estacionadas actualmente: el parámetro – n enumera todas las órbitas usadas actualmente en este grupo de servidores, tal como se muestra</span><span class="sxs-lookup"><span data-stu-id="7a9eb-359">Currently parked calls: the –n parameter lists all currently used orbits on this pool as shown</span></span>

<span data-ttu-id="7a9eb-360">![Llamadas estacionadas actualmente en Call Parkometer.](images/JJ945604.07a7eec4-7999-4c92-93f0-95525b244b4c(OCS.15).jpg "Llamadas estacionadas actualmente en Call Parkometer.")</span><span class="sxs-lookup"><span data-stu-id="7a9eb-360">![Currently-parked calls in Call Parkometer.](images/JJ945604.07a7eec4-7999-4c92-93f0-95525b244b4c(OCS.15).jpg "Currently-parked calls in Call Parkometer.")</span></span>

<span data-ttu-id="7a9eb-361">Número de órbitas libres: el parámetro – f enumera el número de órbitas libres actualmente en el grupo, tal como se muestra</span><span class="sxs-lookup"><span data-stu-id="7a9eb-361">Number of free orbits: the –f parameter lists the number of currently free orbits in the pool as shown</span></span>

<span data-ttu-id="7a9eb-362">![Órbitas libres en llamadas Parkometer.](images/JJ945604.ecc1d621-0ca0-4ecf-a579-08b41c6f08ed(OCS.15).jpg "Órbitas libres en llamadas Parkometer.")</span><span class="sxs-lookup"><span data-stu-id="7a9eb-362">![Free orbits in Call Parkometer.](images/JJ945604.ecc1d621-0ca0-4ecf-a579-08b41c6f08ed(OCS.15).jpg "Free orbits in Call Parkometer.")</span></span>

<span data-ttu-id="7a9eb-363">Llamadas estacionadas recientemente: el parámetro – r \<n\> enumera las \<n\> últimas llamadas estacionadas, como se muestra</span><span class="sxs-lookup"><span data-stu-id="7a9eb-363">Recently parked calls: the –r \<n\> parameter lists the \<n\> last parked calls as shown</span></span>

<span data-ttu-id="7a9eb-364">![Llamadas estacionadas recientemente en Call Parkometer.](images/JJ945604.1c5eb27d-faa1-491b-b4aa-b484255c3353(OCS.15).jpg "Llamadas estacionadas recientemente en Call Parkometer.")</span><span class="sxs-lookup"><span data-stu-id="7a9eb-364">![Recently-parked calls in Call Parkometer.](images/JJ945604.1c5eb27d-faa1-491b-b4aa-b484255c3353(OCS.15).jpg "Recently-parked calls in Call Parkometer.")</span></span>

<span data-ttu-id="7a9eb-365">Prueba de reserva orbital: el parámetro – t comprueba la reserva \<n\> de una órbita en la base de datos tal como se muestra.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-365">Test orbit reservation: the –t \<n\> parameter tests reserving an orbit in the database as shown</span></span>

<span data-ttu-id="7a9eb-366">![Pruebe las reservas de órbitas en Call Parkometer.](images/JJ945604.84c9b69e-7af0-4224-8711-a43a28f08691(OCS.15).jpg "Pruebe las reservas de órbitas en Call Parkometer.")</span><span class="sxs-lookup"><span data-stu-id="7a9eb-366">![Test orbit reservations in Call Parkometer.](images/JJ945604.84c9b69e-7af0-4224-8711-a43a28f08691(OCS.15).jpg "Test orbit reservations in Call Parkometer.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="7a9eb-367">Resumen</span><span class="sxs-lookup"><span data-stu-id="7a9eb-367">Summary</span></span>

<span data-ttu-id="7a9eb-368">Call Parkometer es una herramienta de línea de comandos que proporciona información detallada sobre el servidor de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-368">Call Parkometer is a command-line tool that provides detailed information about the Call Park Server.</span></span>

</div>

</div>

<div>

## <a name="cleanupstorageservicedata"></a><span data-ttu-id="7a9eb-369">CleanupStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="7a9eb-369">CleanupStorageServiceData</span></span>

<span data-ttu-id="7a9eb-370">La herramienta del kit de recursos de CleanupStorageServiceData permite eliminar datos huérfanos de la base de datos usada por el servicio de almacenamiento de Lync Server (LYSS).</span><span class="sxs-lookup"><span data-stu-id="7a9eb-370">The CleanupStorageServiceData resource kit tool allows for deleting of orphaned data from the database used by the Lync Server Storage Service (LYSS).</span></span> <span data-ttu-id="7a9eb-371">Una función del servicio de almacenamiento es almacenar en búfer la comunicación entre Lync Server y varios extremos de almacenamiento de datos back-end, como SQL Server y Exchange.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-371">One function of the storage service is to buffer communication between Lync Server and various back-end data storage endpoints, like SQL Server and Exchange.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="7a9eb-372">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a9eb-372">Description</span></span>

<span data-ttu-id="7a9eb-373">Para admitir la alta disponibilidad, LYSS acepta y guarda copias de los datos en varios servidores front-end del grupo de servidores temporalmente y quita esos datos una vez que se han entregado a su ubicación de almacenamiento de largo plazo final.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-373">To support high availability, LYSS accepts and saves copies of the data on multiple front end servers in the pool temporarily, and removes that data once it has been delivered to its final long-term storage location.</span></span> <span data-ttu-id="7a9eb-374">Hay situaciones inusuales que se pueden producir durante otro funcionamiento normal, cuando un servidor puede bloquear o experimentar un problema de procesamiento, y es posible que algunos datos no se limpien correctamente.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-374">There are unusual situations which may occur during otherwise normal operation, when a server might crash or experience a processing issue, and some data might not get cleaned up properly.</span></span> <span data-ttu-id="7a9eb-375">Estos datos son inocuos, pero consumen recursos de procesamiento limitados.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-375">This data is harmless, but it does consume limited processing resources.</span></span> <span data-ttu-id="7a9eb-376">Gran parte del mantenimiento de datos normal es automatizado, pero esta herramienta permite la identificación segura y la eliminación de datos huérfanos cuando no es posible la eliminación automática.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-376">Much of the normal required data maintenance is automated, but this tool allows for the safe identification and removal of such orphaned data when automated removal is not possible.</span></span> <span data-ttu-id="7a9eb-377">El uso de esta herramienta se indica cuando se genera una alerta de System Center Operations Manager (SCOM) de supervisión de estado que pide al administrador que quite los datos innecesarios de las bases de datos de LYSS locales del grupo.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-377">Usage of this tool is indicated when a health monitoring System Center Operations Manager (SCOM) alert is raised which asks the administrator to remove the unneeded data from the local LYSS databases in the pool.</span></span> <span data-ttu-id="7a9eb-378">Habrá un evento correspondiente en el registro de eventos en el servidor front-end que activó la alerta.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-378">There will be a corresponding event in the event log on the front end which triggered the alert.</span></span> <span data-ttu-id="7a9eb-379">Los detalles del evento contendrán información sobre la cantidad de datos huérfanos contenidos en el front-end y se produce cuando dichos datos superen determinados umbrales previos a la determinación</span><span class="sxs-lookup"><span data-stu-id="7a9eb-379">The event details will contain information about the amount of orphaned data contained on the front end, and is raised when that data exceeds certain pre-determine thresholds</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="7a9eb-380">Requirements</span><span class="sxs-lookup"><span data-stu-id="7a9eb-380">Requirements</span></span>

<span data-ttu-id="7a9eb-381">Instale las herramientas del kit de recursos de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-381">Install the Lync Server 2013, Resource Kit Tools.</span></span> <span data-ttu-id="7a9eb-382">La herramienta se ejecuta en equipos Unidos a un dominio en los que se han instalado Lync Server y Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-382">The tool runs on domain-joined machines where Lync Server and Lync Server 2013 Management Shell are installed.</span></span> <span data-ttu-id="7a9eb-383">La herramienta usa un cmdlet desde el shell de administración para identificar todos los servidores front-end del grupo.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-383">The tool uses a cmdlet from the management shell to identify all Front End servers in the pool.</span></span> <span data-ttu-id="7a9eb-384">En segundo lugar, la herramienta debe ejecutarse desde un equipo en el grupo de servidores que tenga instalada la base de datos **RtcLocal** .</span><span class="sxs-lookup"><span data-stu-id="7a9eb-384">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="7a9eb-385">Esta base de datos se usa con la herramienta CleanupStorageServiceData para obtener los detalles de conexión necesarios para comunicarse con el servicio de enrutamiento de Lync Server. por último, la cuenta o credencial que invoca la herramienta debe tener permiso de lectura y escritura en el recurso compartido de archivos en el que desea escribir el registro de salida. Además, esta herramienta depende de que el grupo esté en un estado estable.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-385">This database is used by the CleanupStorageServiceData tool to get the connection details needed to communicate with the Lync Server Routing Service.Finally, the account or credential invoking the tool must have read/write permission to the file share to which they want to write the output log.Also, this tool depends on the pool being in a stable state.</span></span> <span data-ttu-id="7a9eb-386">En esencia, esto significa que cada servidor front-end debe estar activo y en funcionamiento, la instancia de SQL Server LYNCLOCAL y la base de datos LYSS deben poder conectarse a y cada grupo de enrutamiento debe tener un conjunto completo de 1 servidor front-end principal y 2 servidores front-end secundarios.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-386">In essence this means that every Front End server is expected to be up and running, the SQL Server LYNCLOCAL instance and LYSS database must be able to be connected to, and each routing group must have a complete set of 1 primary Front End servers and 2 secondary Front End servers.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="7a9eb-387">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="7a9eb-387">Examples</span></span>

<span data-ttu-id="7a9eb-388">C: \\ archivos de programa \\ Microsoft Lync Server 2013 \\ reskit \\ StorageService \> ImportStorageServiceData.exe</span><span class="sxs-lookup"><span data-stu-id="7a9eb-388">C:\\Program Files\\Microsoft Lync Server 2013\\ResKit\\StorageService\> ImportStorageServiceData.exe</span></span>

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

## <a name="dbanalyze"></a><span data-ttu-id="7a9eb-389">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="7a9eb-389">DBAnalyze</span></span>

<div>

## <a name="description"></a><span data-ttu-id="7a9eb-390">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a9eb-390">Description</span></span>

<span data-ttu-id="7a9eb-391">DBAnalyze es una herramienta de línea de comandos que ayuda a los administradores a recopilar informes de análisis sobre las bases de datos de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-391">DBAnalyze is a command-line tool that helps administrators to gather analysis reports about the Lync Server 2013 databases.</span></span> <span data-ttu-id="7a9eb-392">DBAnalyze tiene los siguientes modos: diagnóstico, datos de usuario, Conferencia, MCU y fragmentación de disco:</span><span class="sxs-lookup"><span data-stu-id="7a9eb-392">DBAnalyze has the following modes: diagnostic, user data, conference, MCUs, and disk fragmentation:</span></span>

  - <span data-ttu-id="7a9eb-393">**Modo**     de diagnóstico Crea un informe que incluye información sobre tablas (el número de registros, la fragmentación, el tamaño de los datos y el tamaño del índice), los tamaños de los archivos de registro y de datos. el último tiempo de copia de seguridad, la distribución de contactos entre servidores que ejecutan Microsoft Office Communications Server, el número promedio de permisos, contactos, contenedores, suscripciones, publicaciones, extremos por usuario, los usuarios alojados incorrectamente, los usuarios que no se pueden enrutar, el número medio de conferencias organizadas por usuario, conferencias programadas, conferencias activas y la versión</span><span class="sxs-lookup"><span data-stu-id="7a9eb-393">**Diagnostic mode**   Creates a report that includes information about tables (number of records, fragmentation, data size, and index size), data and log file sizes, the last back-up time, contact distribution among servers that are running Microsoft Office Communications Server, the average number of permissions, contacts, containers, subscriptions, publications, endpoints per user, any improperly homed users, users that can’t be routed, the average number of conferences organized per user, scheduled conferences, active conferences, and the database version.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7a9eb-394">El modo de diagnóstico en ejecución puede afectar al rendimiento del servidor.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-394">Running diagnostic mode can affect server performance.</span></span>

    
    </div>

  - <span data-ttu-id="7a9eb-395">Modo de datos de **usuario**   Informa sobre los datos del contacto, el contenedor, la suscripción, la publicación, el permiso y el grupo de contactos para un usuario específico o para los usuarios que tienen ese usuario en sus listas de contactos y permisos.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-395">**User data mode**  Reports contact, container, subscription, publication, permission, and contact-group data for a specified user or for users who have that user in their contact and permission lists.</span></span> <span data-ttu-id="7a9eb-396">Este modo también informa de los datos de Resumen de las conferencias a las que un usuario organiza o al que está invitado.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-396">This mode also reports summary data for conferences that a user organizes or is invited to.</span></span>

  - <span data-ttu-id="7a9eb-397">**Modo**     de conferencia Informa de datos detallados para una conferencia específica, incluidos todos los detalles de tiempo de programación de la Conferencia, la lista de invitados, la lista de tipos de medios permitidos para la Conferencia, las MCU activas (unidades de control multipunto), la lista de participantes activos y el estado de señalización de cada participante.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-397">**Conference mode**   Reports detailed data for a specific conference, including all schedule-time details for the conference, the invitee list, the list of media types allowed for the conference, active MCUs (multipoint control units), the active participant list, and each participant’s signaling state.</span></span>

  - <span data-ttu-id="7a9eb-398">IDENTIFICADOR de reunión de **descodificación**    Descodifica un identificador de reunión de la red telefónica conmutada (RTC) que especifica el conmutador **/pstnid** pero no se conecta al back-end para obtener información detallada.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-398">**Decode Meeting ID**  Decodes a public switched telephone network (PSTN) meeting ID that is specified by the **/pstnid** switch but does not connect to the back end for detailed information.</span></span>

  - <span data-ttu-id="7a9eb-399">**Resolver Conferencia**     Descodifica un identificador de reunión RTC especificado por el modificador **/pstnid** y muestra información sobre la Conferencia indicada por el identificador.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-399">**Resolve conference**   Decodes a PSTN meeting ID that is specified by the **/pstnid** switch and displays information about the conference indicated by the ID.</span></span>

  - <span data-ttu-id="7a9eb-400">**Modo MCU**    Informa del identificador, el tipo de medio, la dirección URL, el estado de latido, la carga de conferencia y la carga de participantes de cada MCU del grupo.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-400">**MCUs mode**  Reports the ID, media type, URL, heartbeat status, conference load, and participant load for each MCU in the pool.</span></span>

  - <span data-ttu-id="7a9eb-401">Modo de fragmentación de **disco**    Muestra el estado de fragmentación de todos los discos.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-401">**Disk fragmentation mode**  Displays the fragmentation status of all disks.</span></span>

<span data-ttu-id="7a9eb-402">Esta herramienta se puede usar para diagnosticar varios problemas o ayudar a los administradores con la planeación de la capacidad.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-402">This tool can be used to diagnose various problems or to assist administrators with capacity planning.</span></span> <span data-ttu-id="7a9eb-403">Por ejemplo, si la mayoría de los usuarios hospedados en el servidor A eligen a los usuarios hospedados en el servidor B como sus contactos, el administrador puede mover a los usuarios del servidor a al servidor B para reducir el tráfico entre servidores.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-403">For example, if most of the users homed on server A choose users homed on server B as their contacts, the administrator can move the users on server A to server B to reduce cross-server traffic.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="7a9eb-404">Output</span><span class="sxs-lookup"><span data-stu-id="7a9eb-404">Output</span></span>

<span data-ttu-id="7a9eb-405">Esta herramienta genera informes predefinidos sobre la base de datos de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-405">This tool outputs predefined reports about the Lync Server 2013 database.</span></span> <span data-ttu-id="7a9eb-406">**Ruta de acceso:** % ProgramFiles% \\ Microsoft Lync Server 2013 \\ reskit</span><span class="sxs-lookup"><span data-stu-id="7a9eb-406">**Path:** %ProgramFiles%\\Microsoft Lync Server 2013\\Reskit</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="7a9eb-407">Finalidad</span><span class="sxs-lookup"><span data-stu-id="7a9eb-407">Purpose</span></span>

<span data-ttu-id="7a9eb-408">Para instalar Dbanalyze.exe, cópielo en una carpeta local y, a continuación, ejecute la herramienta.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-408">To install Dbanalyze.exe, copy it to a local folder and then run the tool.</span></span> <span data-ttu-id="7a9eb-409">Para usar la herramienta, ejecute el siguiente comando desde la línea de comandos.`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`</span><span class="sxs-lookup"><span data-stu-id="7a9eb-409">To use the tool, run the following command from the command line.`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`</span></span> <span data-ttu-id="7a9eb-410">A continuación se muestran las descripciones de las opciones de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-410">The descriptions for the command-line options are shown below.</span></span>

<span data-ttu-id="7a9eb-411">![Opciones de la línea de comandos para Dbanalyze.exe.](images/JJ945604.22bf3432-af6d-495b-8f48-d94c5d259523(OCS.15).jpg "Opciones de la línea de comandos para Dbanalyze.exe.")</span><span class="sxs-lookup"><span data-stu-id="7a9eb-411">![Command line options for Dbanalyze.exe.](images/JJ945604.22bf3432-af6d-495b-8f48-d94c5d259523(OCS.15).jpg "Command line options for Dbanalyze.exe.")</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="7a9eb-412">Requirements</span><span class="sxs-lookup"><span data-stu-id="7a9eb-412">Requirements</span></span>

<span data-ttu-id="7a9eb-413">**Equipo** DBAnalyze solo puede ejecutarse desde un equipo unido a un dominio que tenga instalado Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-413">**Computer** DBAnalyze can be run only from a domain-joined computer that has Lync Server 2013 installed.</span></span>

<span data-ttu-id="7a9eb-414">**Red** El equipo debe ser capaz de conectarse a la base de datos back-end.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-414">**Network** The computer should be able to connect to the back-end database.</span></span>

<span data-ttu-id="7a9eb-415">**Software** de Los componentes de software de Lync Server 2013 deben estar instalados antes de ejecutar DBAnalyze.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-415">**Software** Lync Server 2013 software components must be installed before running DBAnalyze.</span></span>

<span data-ttu-id="7a9eb-416">**Usuarios** de En la tabla siguiente se muestran los administradores que tienen los permisos necesarios para acceder a las bases de datos de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-416">**Users**The table below shows the administrators who have the necessary permissions to access Lync Server 2013 databases.</span></span>

<span data-ttu-id="7a9eb-417">![Tabla de permisos para obtener Dbanalyze.exe.](images/JJ945604.b8931e9e-834e-4dec-8a84-2fc47d1613e9(OCS.15).jpg "Tabla de permisos para obtener Dbanalyze.exe.")</span><span class="sxs-lookup"><span data-stu-id="7a9eb-417">![Permissions table for Dbanalyze.exe.](images/JJ945604.b8931e9e-834e-4dec-8a84-2fc47d1613e9(OCS.15).jpg "Permissions table for Dbanalyze.exe.")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7a9eb-418">Se requiere una cuenta de administrador local para <STRONG>/Report:</STRONG> modo de disco.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-418">A local administrator account is required for <STRONG>/report:disk</STRONG> mode.</span></span>



</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="7a9eb-419">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="7a9eb-419">Examples</span></span>

<span data-ttu-id="7a9eb-420">Los siguientes son ejemplos de comandos de Dbanalyze.exe válidos:</span><span class="sxs-lookup"><span data-stu-id="7a9eb-420">The following are examples of valid Dbanalyze.exe commands:</span></span>

    dbanalyze.exe /report:diag
    dbanalyze.exe /report:user /user:usera@domainb.com
    dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
    dbanalyze.exe /report:resolve /pstnid:12345
    dbanalyze.exe /report:mcus
    dbanalyze.exe /report:disk

</div>

<div>

## <a name="summary"></a><span data-ttu-id="7a9eb-421">Resumen</span><span class="sxs-lookup"><span data-stu-id="7a9eb-421">Summary</span></span>

<span data-ttu-id="7a9eb-422">DBAnalyzer proporciona a los administradores un análisis rápido y sencillo de las bases de datos de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-422">DBAnalyzer provides administrators a quick and easy to analyze Lync Server 2013 databases.</span></span>

</div>

</div>

<div>

## <a name="importstorageservicedata"></a><span data-ttu-id="7a9eb-423">ImportStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="7a9eb-423">ImportStorageServiceData</span></span>

<span data-ttu-id="7a9eb-424">La herramienta del kit de recursos de ImportStorageServiceData permite volver a importar datos de cola y de extremo que se han vaciado del servicio de almacenamiento (LYSS) de nuevo en el servicio de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-424">The ImportStorageServiceData resource kit tool allows for re-importing Queue and Endpoint data that was flushed out of the Storage Service (LYSS) back into the Storage Service.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="7a9eb-425">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a9eb-425">Description</span></span>

<span data-ttu-id="7a9eb-426">Los datos vaciados del servicio de almacenamiento podrían haber sido automáticos (periódicos) según el estado de los elementos de la cola o la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-426">The data flushed out of the Storage Service could have been automatic (periodic) based on Queue Item status or database size.</span></span> <span data-ttu-id="7a9eb-427">Podría haber sucedido debido a la invocación manual del cmdlet de conmutación por error del grupo o al cmdlet StorageServiceFullFlush (que invoca el cmdlet de conmutación por error del grupo de servidores).</span><span class="sxs-lookup"><span data-stu-id="7a9eb-427">It could have happened due to the manual invocation of the pool failover cmdlet, or the StorageServiceFullFlush cmdlet (which the pool failover cmdlet invokes).</span></span> <span data-ttu-id="7a9eb-428">Tenga en cuenta que los datos no deberían volver a importarse si el tamaño de la base de datos del servicio de almacenamiento (LYSS) de los servidores front-end es superior al nivel normal, ya que, por lo tanto, es probable que solo se exporten más datos hacia atrás. Además, los problemas que podrían haber contribuido a errores que provocaron el crecimiento de la cola del servicio de almacenamiento deberían resolverse en primer lugar (por ejemplo, errores de punto de conexión de Exchange, problemas de red u otros problemas).</span><span class="sxs-lookup"><span data-stu-id="7a9eb-428">Note that data should ideally not be re-imported if any of the Storage Service (LYSS ) database size on the front ends is above the normal level, because doing so will likely just cause more data to be exported back out. Furthermore, any problems which could have contributed to errors that caused the Storage Service Queue to grow should first be resolved (for example Exchange endpoint errors, network issues, or other problems).</span></span>

<span data-ttu-id="7a9eb-429">**Escenario 1:** durante la conmutación por error del grupo, es posible que los archivos se vacíen del servicio de almacenamiento para cada front-end.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-429">**Scenario 1:** during pool failover, files may be flushed out from storage service for each front end.</span></span> <span data-ttu-id="7a9eb-430">Una vez completada la conmutación por error, debe ejecutarse la herramienta para volver a importar los datos.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-430">After failover is completed, the tool should be run to re-import the data.</span></span>

<span data-ttu-id="7a9eb-431">**Escenario 2:** los datos se vacían automáticamente cada día o en respuesta a la base de datos del servicio de almacenamiento que supera determinados umbrales de tamaño (por ejemplo, 60%, 80%, 90% completo).</span><span class="sxs-lookup"><span data-stu-id="7a9eb-431">**Scenario 2:** data is being flushed automatically each day or in response to Storage Service database exceeding certain size thresholds ( for example 60%, 80%, 90% full ).</span></span> <span data-ttu-id="7a9eb-432">El administrador debe volver a importar periódicamente los datos vaciados de forma automática.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-432">This automatically flushed data should be re-imported routinely by the administrator.</span></span> <span data-ttu-id="7a9eb-433">En la situación anterior, si no se implementa el paquete SCOM de supervisión, hay eventos para el servicio de almacenamiento de Lync Server relacionados con los datos que se vacían del servicio de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-433">In the above situation, if the monitoring SCOM pack is not deployed, there are events for Lync Server Storage Service relating to data being flushed from the Storage Service.</span></span> <span data-ttu-id="7a9eb-434">Se han iniciado los identificadores de evento de 32075 (operación de vaciado completa), 32076 (vaciado completo), 32082 (se inició el vaciado de nivel de mantenimiento), 32083 (vaciado de nivel de mantenimiento completo), 32089 (vaciado debido a rellenar la base de datos).</span><span class="sxs-lookup"><span data-stu-id="7a9eb-434">Event IDs of 32075 (full flush operation is started), 32076 (full flush has completed), 32082 (maintenance level flush started), 32083 (maintenance level flush complete), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="7a9eb-435">Nota estos identificadores de evento corresponden a la versión RTM.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-435">Note these event Ids correspond to the RTM release.</span></span> <span data-ttu-id="7a9eb-436">Cuando un administrador ve estos eventos, significa que hay archivos que se han vaciado. Estos datos deben volver a importarse rutinariamente con esta herramienta, por ejemplo, una vez por semana.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-436">When an administrator sees these events, it means that there are files that have been flushed out. This data should routinely be imported back using this tool, for example once per week.</span></span>

<span data-ttu-id="7a9eb-437">Para la versión de servicio en línea, si se implementa el paquete SCOM de supervisión de mantenimiento de Lync Server, hay nuevas alertas que se pueden plantear y que piden al administrador que vuelva a importar los datos vaciados en el servicio de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-437">For the Online Service release, if health monitoring SCOM pack for Lync Server is deployed, there are new alerts which may be raised which ask the administrator to re-import the flushed data back into Storage Service.</span></span> <span data-ttu-id="7a9eb-438">Habrá un evento correspondiente en el registro de eventos del servidor front-end que activó la alerta.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-438">There will be a corresponding event in the event log on the Front End server which triggered the alert.</span></span> <span data-ttu-id="7a9eb-439">El evento proporcionará una descripción de la ruta de acceso principal en la que se ubican los archivos de datos vaciados, así como el número de archivos que cumplen los criterios de alerta.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-439">The event will give a description of the Parent path under which the flushed data files are located, as well as how many files there are which meet the alert criteria.</span></span> <span data-ttu-id="7a9eb-440">Los criterios de alerta son que hay X o más archivos en la ruta de acceso del elemento primario concreta que tienen al menos días Y de antigüedad (donde X e Y están preestablecidos en el StorageService, pero se pueden invalidar cambiando el archivo APPCONFIG). A continuación, se muestran dos ejemplos de eventos que pueden desencadenar la alerta de mantenimiento, con la diferencia de que la ruta de acceso principal.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-440">The alert criteria is that there are X or more files under the particular parent path which are at least Y days old ( where X and Y are preset within the StorageService but can be overridden by changing the APPCONFIG file.)Two examples of events which can trigger the health alert are shown below, with the difference being their parent path.</span></span> <span data-ttu-id="7a9eb-441">Una posibilidad está en el uso compartido de archivos del servicio Web, mientras que la otra posibilidad es el directorio de datos de la aplicación local de cada front-end.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-441">One possibility is under Web service file share, while the other possibility is the local Application Data directory of each front end.</span></span> <span data-ttu-id="7a9eb-442">(por ejemplo, c: \\ ProgramData \\ Microsoft \\ Lync Server \\ StorageService).</span><span class="sxs-lookup"><span data-stu-id="7a9eb-442">( for example c:\\ProgramData\\Microsoft\\Lync Server\\StorageService ).</span></span> <span data-ttu-id="7a9eb-443">A continuación, el administrador ejecutará esta herramienta de reskit.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-443">The administrator will then run this reskit tool.</span></span>

<span data-ttu-id="7a9eb-444">Esta herramienta aumentará la carga de la CPU y de e/s en el front-end en el que se ejecuta, así como otros front-end, en la situación en que los datos no son propiedad del servidor front-end en el que se ejecuta la herramienta.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-444">This tool will increase CPU and IO load on the front end it is running on, as well as other front ends, in the situation that the data is not owned by the front end that the tool is executed on.</span></span> <span data-ttu-id="7a9eb-445">Se recomienda ejecutar esta herramienta cuando los servidores front-end no tienen una carga de CPU y de e/s intensa, por ejemplo, fuera de las horas pico.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-445">We recommend runng this tool when front ends are not under heavy CPU and IO load, for example outside of peak hours.</span></span> <span data-ttu-id="7a9eb-446">En segundo lugar, esta herramienta puede tener entre 2 y 3 minutos para importar un archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-446">Secondly, this tool can 2 to 3 minutes to import one data file.</span></span> <span data-ttu-id="7a9eb-447">Tenga esto en cuenta al estimar cuánto tiempo se ejecutará la herramienta. El archivo de registro detallado generado por la herramienta aparecerá de forma predeterminada en el almacén de archivos.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-447">Keep this in mind when estimating how long tool will be running.The verbose log file generated by the tool will by default appear on the File Store.</span></span> <span data-ttu-id="7a9eb-448">Elimínelo si no se han notificado errores, ya que el archivo de registro puede tener decenas de MB o más.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-448">Delete it if there are no errors reported, because the log file can be tens of MB or more.</span></span>

<span data-ttu-id="7a9eb-449">![Ejemplo de eventos del registro de eventos del servidor de almacenamiento.](images/JJ945604.3a903ef7-ea8a-4606-8229-a3e32f13af3a(OCS.15).jpg "Ejemplo de eventos del registro de eventos del servidor de almacenamiento.")</span><span class="sxs-lookup"><span data-stu-id="7a9eb-449">![Sample Storage Server event log events.](images/JJ945604.3a903ef7-ea8a-4606-8229-a3e32f13af3a(OCS.15).jpg "Sample Storage Server event log events.")</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="7a9eb-450">Requirements</span><span class="sxs-lookup"><span data-stu-id="7a9eb-450">Requirements</span></span>

<span data-ttu-id="7a9eb-451">Instale las herramientas del kit de recursos de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-451">Install the Lync Server 2013, Resource Kit Tools.</span></span> <span data-ttu-id="7a9eb-452">La herramienta se ejecuta en equipos Unidos a un dominio donde se instalan Lync Server y Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-452">The tool runs on domain-joined machines where Lync Server and Lync Server Management Shell are installed.</span></span> <span data-ttu-id="7a9eb-453">La herramienta usa un cmdlet desde el shell de administración para identificar todos los servidores front-end del grupo.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-453">The tool uses a cmdlet from the management shell to identify all the Front End servers in the pool.</span></span> <span data-ttu-id="7a9eb-454">En segundo lugar, la herramienta debe ejecutarse desde un equipo en el grupo de servidores que tenga instalada la base de datos **RtcLocal** .</span><span class="sxs-lookup"><span data-stu-id="7a9eb-454">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="7a9eb-455">Esta base de datos la usa la herramienta para recuperar la ubicación del recurso compartido de archivos WebService para el grupo de servidores. Además, antes de usar la herramienta, cada servidor front-end debe habilitar la comunicación remota de Windows PowerShell con **enable-PSRemoting** en cada servidor front-end, así como el equipo desde el que se ejecuta la herramienta.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-455">This database is used by the tool to retrieve the location of the WEBSERVICE file share for the pool.Additionally, before using the tool, each Front End server must first enable Windows PowerShell Remoting using **Enable-PSRemoting** on each Front End server, as well as the machine that the tool is executed from.</span></span> <span data-ttu-id="7a9eb-456">De lo contrario, se producirá un error en los comandos remotos de Windows PowerShell de esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-456">Otherwise, remote Windows PowerShell commands from this tool will fail.</span></span> <span data-ttu-id="7a9eb-457">La comunicación remota de Windows PowerShell puede desactivarse en todos los servidores front-end del grupo una vez finalizado.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-457">Windows PowerShell Remoting can be turned off on all Front End servers in the pool after it is finished.</span></span> <span data-ttu-id="7a9eb-458">Por último, la cuenta o credencial que invoca la herramienta debe tener permiso de lectura y escritura en el recurso compartido de archivos WebService para el grupo en el que está ejecutando esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-458">Finally, the account or credential invoking the tool must have read/write permission to the webservice file share for the pool they are executing this tool on.</span></span> <span data-ttu-id="7a9eb-459">De lo contrario, la herramienta producirá errores de permiso de e/s.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-459">Otherwise the tool will fail with IO Permission errors.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7a9eb-460">En Windows Server 2012, la comunicación remota de Windows PowerShell está habilitada de forma predeterminada, pero no en el sistema operativo Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-460">On Windows Server 2012, Windows PowerShell Remoting is enabled by default, but not on the Windows Server 2008 operating system.</span></span>



</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="7a9eb-461">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="7a9eb-461">Examples</span></span>

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

## <a name="lcssync"></a><span data-ttu-id="7a9eb-462">LCSSync</span><span class="sxs-lookup"><span data-stu-id="7a9eb-462">LCSSync</span></span>

<span data-ttu-id="7a9eb-463">La herramienta LCSSync ayuda a implementar el software de comunicaciones de Lync Server 2013 en un entorno de varios bosques.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-463">The LCSSync tool helps to deploy Lync Server 2013 communications software in a multi-forest environment.</span></span> <span data-ttu-id="7a9eb-464">Esta herramienta se usa para sincronizar usuarios y grupos de bosques de usuarios diferentes como un objeto de contacto de servicios de dominio de Active Directory para un bosque central en el que Lync Server 2013 está instalado.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-464">This tool is used to synchronize users and groups from different user forests as an Active Directory Domain Services contact object to a central forest where Lync Server 2013 is installed.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="7a9eb-465">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a9eb-465">Description</span></span>

<span data-ttu-id="7a9eb-466">LCSSync usa los objetos de contacto de los servicios de dominio de Active Directory sincronizados en el bosque central para habilitar a los usuarios para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-466">LCSSync uses the synchronized Active Directory Domain Services contact objects in the central forest to enable users for Lync Server.</span></span> <span data-ttu-id="7a9eb-467">Para proporcionar un inicio de sesión único, la cuenta de usuario principal debe estar asignada al objeto de contacto de servicios de dominio de Active Directory en el bosque central de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-467">To provide single sign-in, the primary user account must be mapped to the Active Directory Domain Services contact object in the central forest for Lync Server 2013.</span></span> <span data-ttu-id="7a9eb-468">Esta herramienta ayuda a realizar esa asignación.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-468">This tool helps perform that mapping.</span></span> <span data-ttu-id="7a9eb-469">Esta herramienta proporciona plantillas para crear agentes de administración en Microsoft Identity Integration Server.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-469">This tool provides templates for creating Management Agents in the Microsoft Identity Integration Server.</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="7a9eb-470">Resumen</span><span class="sxs-lookup"><span data-stu-id="7a9eb-470">Summary</span></span>

<span data-ttu-id="7a9eb-471">La herramienta LCSSync ayuda a implementar Lync Server en un entorno de varios bosques.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-471">The LCSSync tool helps to deploy Lync Server in a multi-forest environment.</span></span>

</div>

</div>

<div>

## <a name="lookupuserconsole"></a><span data-ttu-id="7a9eb-472">LookupUserConsole</span><span class="sxs-lookup"><span data-stu-id="7a9eb-472">LookupUserConsole</span></span>

<span data-ttu-id="7a9eb-473">La herramienta LookupUserConsole muestra información de enrutamiento de Lync Server interno sobre usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-473">The LookupUserConsole tool displays internal Lync Server routing information about specific users.</span></span> <span data-ttu-id="7a9eb-474">Esta información puede ser útil para que Microsoft admita personal en el diagnóstico de problemas de implementación y enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-474">This information may be useful to Microsoft support personal in diagnosing deployment and routing problems.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="7a9eb-475">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a9eb-475">Description</span></span>

<span data-ttu-id="7a9eb-476">Al ejecutar LookupUserConsole.exe se abrirá un símbolo del sistema que acepta direcciones SIP e intenta Mostrar información de enrutamiento de Lync Server interna relacionada.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-476">Executing LookupUserConsole.exe will open a command prompt that accepts SIP addresses and attempts to display internal Lync Server routing information relating them.</span></span> <span data-ttu-id="7a9eb-477">Escriba **Exit** para salir de la herramienta LookupUserConsole.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-477">Type **exit** to quit the LookupUserConsole tool.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="7a9eb-478">Requirements</span><span class="sxs-lookup"><span data-stu-id="7a9eb-478">Requirements</span></span>

<span data-ttu-id="7a9eb-479">Instale las herramientas del kit de recursos de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-479">Install the Lync Server 2013, Resource Kit Tools.</span></span> <span data-ttu-id="7a9eb-480">La herramienta se ejecuta en equipos Unidos a un dominio donde Lync Server está instalado</span><span class="sxs-lookup"><span data-stu-id="7a9eb-480">The tool runs on domain-joined machines where Lync Server is installed</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="7a9eb-481">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="7a9eb-481">Examples</span></span>

<span data-ttu-id="7a9eb-482">C: \\ archivos de programa \\ Microsoft Lync Server 2013 \\ reskit \>LookupUserConsole.exe</span><span class="sxs-lookup"><span data-stu-id="7a9eb-482">C:\\Program Files\\Microsoft Lync Server 2013\\ResKit\>LookupUserConsole.exe</span></span>

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

## <a name="msturnping"></a><span data-ttu-id="7a9eb-483">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="7a9eb-483">MsTurnPing</span></span>

<span data-ttu-id="7a9eb-484">La herramienta MSTurnPing permite a un administrador del software de comunicaciones Microsoft Lync Server 2013 comprobar el estado de los servidores que ejecutan el servidor perimetral de audio y vídeo y los servicios de autenticación de audio y vídeo, así como los servidores que ejecutan los servicios de directivas de ancho de banda en la topología.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-484">The MSTurnPing tool allows an administrator of Microsoft Lync Server 2013 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="7a9eb-485">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a9eb-485">Description</span></span>

<span data-ttu-id="7a9eb-486">La herramienta MSTurnPing permite a un administrador del software de comunicaciones Lync Server 2013 comprobar el estado de los servidores que ejecutan el servidor perimetral de audio y vídeo y los servicios de autenticación de audio y vídeo, así como los servidores que ejecutan los servicios de directivas de ancho de banda en la topología.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-486">The MSTurnPing tool allows an administrator of Lync Server 2013 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

<span data-ttu-id="7a9eb-487">La herramienta permite al administrador realizar las siguientes pruebas:</span><span class="sxs-lookup"><span data-stu-id="7a9eb-487">The tool allows the administrator to perform the following tests:</span></span>

1.  <span data-ttu-id="7a9eb-488">Prueba del servidor perimetral a/V: la herramienta realiza pruebas en todos los servidores perimetrales A/V de la topología mediante el siguiente procedimiento:</span><span class="sxs-lookup"><span data-stu-id="7a9eb-488">A/V Edge Server test: The tool performs tests against all A/V Edge Servers in the topology by doing the following:</span></span>
    
      - <span data-ttu-id="7a9eb-489">Comprobando que el servicio de autenticación de audio y vídeo de Lync Server se ha iniciado y que puede emitir las credenciales correctas.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-489">Verifying that the Lync Server Audio/Video Authentication service is started and can issue proper credentials.</span></span>
    
      - <span data-ttu-id="7a9eb-490">Comprobando que el servicio perimetral de audio y vídeo de Lync Server se ha iniciado y que puede asignar correctamente los recursos en el servidor perimetral externo.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-490">Verifying that the Lync Server Audio/Video Edge service is started and can allocate the resources on the external edge successfully.</span></span>

2.  <span data-ttu-id="7a9eb-491">Prueba del servicio de directiva de ancho de banda: la herramienta realiza pruebas en todos los servidores que ejecutan los servicios de directiva de ancho de banda de la topología haciendo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7a9eb-491">Bandwidth Policy Service test: The tool performs tests against all the servers that are running the Bandwidth Policy Services in the topology by doing the following:</span></span>
    
      - <span data-ttu-id="7a9eb-492">Comprobar que el servicio de directiva de ancho de banda (autenticación) de Lync Server se ha iniciado y puede emitir las credenciales correctas.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-492">Verifying that the Lync Server Bandwidth Policy Service (Authentication) is started and can issue proper credentials.</span></span>
    
      - <span data-ttu-id="7a9eb-493">Comprobando que el servicio de directiva de ancho de banda (principal) de Lync Server se ha iniciado y puede realizar la comprobación de ancho de banda correctamente.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-493">Verifying that the Lync Server Bandwidth Policy Service (Core) is started and can perform the bandwidth check successfully.</span></span>

<span data-ttu-id="7a9eb-494">Esta herramienta debe ejecutarse desde un equipo que forme parte de la topología y tenga instalado el almacén local.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-494">This tool must be run from a computer that is part of the topology and has the local store installed.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="7a9eb-495">Output</span><span class="sxs-lookup"><span data-stu-id="7a9eb-495">Output</span></span>

<span data-ttu-id="7a9eb-496">La herramienta genera los resultados de cada una de las operaciones.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-496">The tool outputs the results of each of the operations.</span></span>

  - <span data-ttu-id="7a9eb-497">Si se realiza la prueba **AudioVideoEdgeServer** , los resultados de la herramienta son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="7a9eb-497">If the **AudioVideoEdgeServer** test is performed, the tool outputs are the following:</span></span>
    
      - <span data-ttu-id="7a9eb-498">Los resultados de la prueba de los equipos que proporcionan el servicio de autenticación de audio y vídeo de Lync Server en la topología</span><span class="sxs-lookup"><span data-stu-id="7a9eb-498">The test results of the computers that provide the Lync Server Audio/Video Authentication service in the topology</span></span>
    
      - <span data-ttu-id="7a9eb-499">Los resultados de la prueba de los equipos que proporcionan el servicio perimetral de audio y vídeo de Lync Server en la topología</span><span class="sxs-lookup"><span data-stu-id="7a9eb-499">The test results of the computers that provide the Lync Server Audio/Video Edge service in the topology</span></span>

  - <span data-ttu-id="7a9eb-500">Si se realiza la prueba **BandwidthPolicyServer** , los resultados de la herramienta son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="7a9eb-500">If the **BandwidthPolicyServer** test is performed, the tool outputs are the following:</span></span>
    
      - <span data-ttu-id="7a9eb-501">Los resultados de la prueba de los equipos que proporcionan el servicio de directiva de ancho de banda (autenticación) de Lync Server en la topología</span><span class="sxs-lookup"><span data-stu-id="7a9eb-501">The test results of the computers that provide the Lync Server Bandwidth Policy Service (Authentication) in the topology</span></span>
    
      - <span data-ttu-id="7a9eb-502">Los resultados de la prueba de los equipos que proporcionan el servicio de directiva de ancho de banda (principal) de Lync Server en la topología</span><span class="sxs-lookup"><span data-stu-id="7a9eb-502">The test results of the computers that provide the Lync Server Bandwidth Policy Service (Core) in the topology</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="7a9eb-503">Requirements</span><span class="sxs-lookup"><span data-stu-id="7a9eb-503">Requirements</span></span>

  - <span data-ttu-id="7a9eb-504">Esta herramienta debe ejecutarse desde un equipo que esté en la topología y que tenga el almacén local.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-504">This tool must be run from a computer that is in the topology and that has the local store.</span></span>

  - <span data-ttu-id="7a9eb-505">La herramienta debe ejecutarse como un administrador que tenga acceso al almacén local.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-505">The tool must be run as an administrator who has access to the local store.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="7a9eb-506">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="7a9eb-506">Examples</span></span>

<span data-ttu-id="7a9eb-507">El siguiente es un ejemplo de la entrada de la herramienta.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-507">The following is an example of the tool input.</span></span>

    MsTurnPing -ServerRole AudioVideoEdgeServer
    
    MsTurnPing -ServerRole BandwidthPolicyServer

</div>

<div>

## <a name="summary"></a><span data-ttu-id="7a9eb-508">Resumen</span><span class="sxs-lookup"><span data-stu-id="7a9eb-508">Summary</span></span>

<span data-ttu-id="7a9eb-509">Esta herramienta puede ser un recurso valioso para los administradores de Lync Server 2013 que quieran comprobar el estado de los servidores que ejecutan los servicios de directivas de audio y vídeo y de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-509">This tool can be a valuable resource to Lync Server 2013 administrators who want to check the status of the servers that are running audio/video and bandwidth policy services.</span></span>

</div>

</div>

<div>

## <a name="network-configuration-viewer"></a><span data-ttu-id="7a9eb-510">Visor de configuración de red</span><span class="sxs-lookup"><span data-stu-id="7a9eb-510">Network Configuration Viewer</span></span>

<span data-ttu-id="7a9eb-511">Los administradores de software de comunicaciones de Microsoft Lync Server 2013 pueden usar el visor de configuración de red para ver la topología de red de control de admisión de llamadas (CAC) para una empresa que se aprovisiona para permitir sesiones de comunicación en tiempo real, como llamadas de voz o vídeo basadas en la capacidad de ancho de banda especificada.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-511">Network Configuration Viewer can be used by Microsoft Lync Server 2013 communications software administrators to view call admission control (CAC) network topology for an enterprise that is provisioned to allow real-time communication sessions, such as voice or video calls based on specified bandwidth capacity.</span></span> <span data-ttu-id="7a9eb-512">Lync Server 2013 los administradores definen directivas de CAC, que aplican los servicios de directivas de ancho de banda que se instalan con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-512">Lync Server 2013 administrators define CAC policies, which are enforced by the Bandwidth Policy services that are installed with Lync Server 2013.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="7a9eb-513">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a9eb-513">Description</span></span>

<span data-ttu-id="7a9eb-514">El visor de configuración de red (NetworkConfigurationViewer.exe) permite a los administradores realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="7a9eb-514">Network Configuration Viewer (NetworkConfigurationViewer.exe) allows administrators to perform the following tasks:</span></span>

  - <span data-ttu-id="7a9eb-515">Cargar y ver la topología de red de CAC de una implementación de Lync Server 2013 en un formato gráfico.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-515">Load and view CAC network topology from a Lync Server 2013 deployment in a graphical format.</span></span>

  - <span data-ttu-id="7a9eb-516">Cargar y ver la topología de red de CAC de un archivo de registro de servidor de directivas de ancho de banda en un formato gráfico.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-516">Load and view CAC network topology from a Bandwidth Policy Server log file in a graphical format.</span></span>

  - <span data-ttu-id="7a9eb-517">Guarde y almacene la topología de red de CAC en formato XML en el disco.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-517">Save and store CAC network topology in an XML format on the disk.</span></span>

  - <span data-ttu-id="7a9eb-518">Guarde y almacene el diagrama de topología de red de CAC en formato JPG o BMP.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-518">Save and store CAC network topology diagram in JPG or BMP format.</span></span>

  - <span data-ttu-id="7a9eb-519">Ver los datos de configuración de la topología de red de CAC.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-519">View CAC network topology configuration data.</span></span>

  - <span data-ttu-id="7a9eb-520">Ver la topología de red de CAC en un estilo de vista de árbol.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-520">View CAC network topology in a tree-view style.</span></span>

  - <span data-ttu-id="7a9eb-521">Defina los conectores personalizados para los vínculos de topología de red de CAC (por ejemplo, vínculos de sitio a región, de región a región y de sitio a sitio).</span><span class="sxs-lookup"><span data-stu-id="7a9eb-521">Define custom connectors for CAC network topology links (for example, site-to-region, region-to-region, and site-to-site links).</span></span>

  - <span data-ttu-id="7a9eb-522">Ver información del sitio de la topología de red de CAC, información de región y directivas de ancho de banda aprovisionadas y vínculos de red.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-522">View CAC network topology site information, region Information, and provisioned bandwidth policies and network links.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="7a9eb-523">Finalidad</span><span class="sxs-lookup"><span data-stu-id="7a9eb-523">Purpose</span></span>

<span data-ttu-id="7a9eb-524">Ver los vínculos de topología de red CAC empresarial en una interfaz gráfica.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-524">View enterprise CAC network topology links in a graphical interface.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="7a9eb-525">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="7a9eb-525">Examples</span></span>

<span data-ttu-id="7a9eb-526">**Cargar y ver la topología de red de CAC desde una implementación de Lync Server 2013 en formato gráfico:** Lync Server 2013 los administradores pueden cargar y ver la configuración de la topología de red de CAC en cualquier equipo de Lync Server 2013 mediante la opción **Descargar configuración de red** , tal como se muestra en la figura siguiente.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-526">**Load and view CAC network topology from a Lync Server 2013 deployment in a graphical format:** Lync Server 2013 administrators can load and view CAC network topology configuration on any Lync Server 2013 computer by using the **Download Network Configuration** option as shown in the figure below.</span></span> <span data-ttu-id="7a9eb-527">La herramienta no podrá descargar ni ver dicha configuración cuando se implemente en un equipo que no tiene conectividad con el almacén de configuración de Lync.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-527">The tool will fail to download or view such a configuration when deployed on a computer that does not have connectivity to the Lync configuration store.</span></span>

<span data-ttu-id="7a9eb-528">![Descargar la configuración de red.](images/JJ945604.8d126d3f-2545-4f13-a244-974f09614982(OCS.15).jpg "Descargar la configuración de red.")</span><span class="sxs-lookup"><span data-stu-id="7a9eb-528">![Downloading the network configuration.](images/JJ945604.8d126d3f-2545-4f13-a244-974f09614982(OCS.15).jpg "Downloading the network configuration.")</span></span>

<span data-ttu-id="7a9eb-529">**Cargar y ver la topología de red de CAC de un archivo de registro de servidor de directivas de ancho de banda en formato gráfico:** Los servidores de directivas de ancho de banda de Lync Server 2013 guardan la topología de red de CAC como parte del mecanismo de registro en la ubicación del recurso compartido de archivos de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-529">**Load and View CAC network topology from a Bandwidth Policy server log file in a graphical format:** Lync Server 2013 Bandwidth Policy servers save the CAC network topology as a part of the logging mechanism under the Lync Server 2013 file share location.</span></span> <span data-ttu-id="7a9eb-530">Los administradores de Lync Server pueden ver este archivo en un formato gráfico con la opción **abrir configuración de red** , tal como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-530">Lync Server administrators can view such a file in a graphical format by using the **Open Network Configuration** option as shown below.</span></span>

<span data-ttu-id="7a9eb-531">![Abrir un archivo de registro de servidor de directivas de ancho de banda.](images/JJ945604.3e503e92-aacb-4921-a8d2-23f860fe2df6(OCS.15).jpg "Abrir un archivo de registro de servidor de directivas de ancho de banda.")</span><span class="sxs-lookup"><span data-stu-id="7a9eb-531">![Opening a Bandwidth Policy Server log file.](images/JJ945604.3e503e92-aacb-4921-a8d2-23f860fe2df6(OCS.15).jpg "Opening a Bandwidth Policy Server log file.")</span></span>

<span data-ttu-id="7a9eb-532">Guarde y almacene la topología de red de CAC en formato XML en el disco: Lync Server 2013 los administradores pueden guardar el archivo de configuración de la topología de red CAC en formato XML mediante la opción **guardar una copia de la configuración de red** , tal como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-532">Save and store CAC network topology in an XML format on the disk: Lync Server 2013 administrators can save the CAC network topology configuration file in an XML format by using the **Save a copy of Network Configuration** option as shown below.</span></span> <span data-ttu-id="7a9eb-533">El archivo de configuración guardado puede usarse sin conexión para fines de visualización gráfica.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-533">The saved configuration file can then be used offline for graphical viewing purposes.</span></span>

<span data-ttu-id="7a9eb-534">![Guardar la configuración de red como un archivo XML.](images/JJ945604.6eeef3b0-78b5-4ee6-8d94-1a4ddf3d8676(OCS.15).jpg "Guardar la configuración de red como un archivo XML.")</span><span class="sxs-lookup"><span data-stu-id="7a9eb-534">![Saving the network configuration as an XML file.](images/JJ945604.6eeef3b0-78b5-4ee6-8d94-1a4ddf3d8676(OCS.15).jpg "Saving the network configuration as an XML file.")</span></span>

<span data-ttu-id="7a9eb-535">Guarde y almacene el diagrama de topología de red de CAC en formato JPG o BMP: Lync Server 2013 los administradores pueden guardar la configuración de la topología de red de CAC en formato gráfico (formatos de archivo JPG y BMP) mediante la opción **Guardar diagrama de configuración de red como imagen** , como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-535">Save and Store CAC network topology diagram in JPG or BMP format: Lync Server 2013 administrators can save the CAC network topology configuration in a graphical format (JPG and BMP file formats) by using the **Save Network Configuration diagram as picture** option as shown below.</span></span>

<span data-ttu-id="7a9eb-536">![Guardar la configuración de red como una imagen.](images/JJ945604.145a6fb9-58b1-46b1-bbd5-a661ceba07b4(OCS.15).jpg "Guardar la configuración de red como una imagen.")</span><span class="sxs-lookup"><span data-stu-id="7a9eb-536">![Saving the network configuration as a picture.](images/JJ945604.145a6fb9-58b1-46b1-bbd5-a661ceba07b4(OCS.15).jpg "Saving the network configuration as a picture.")</span></span>

<span data-ttu-id="7a9eb-537">**Ver los datos de configuración de la topología de red de CAC:** Lync Server 2013 los administradores pueden ver los datos de configuración de red relacionados, como regiones de red, sitios de red, perfiles de ancho de banda y direcciones IP de subred de sitio en formato de texto, mediante la opción ver datos de configuración de red, tal como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-537">**View CAC network topology configuration data:** Lync Server 2013 administrators can view related network configuration data such as network regions, network sites, bandwidth profiles, and site subnet IP addresses in a textual format by using the View Network Configuration data option as shown below.</span></span>

<span data-ttu-id="7a9eb-538">![Ver los datos de configuración de la red.](images/JJ945604.b72a4c21-a042-4d91-bf96-fcb396af0679(OCS.15).jpg "Ver los datos de configuración de la red.")</span><span class="sxs-lookup"><span data-stu-id="7a9eb-538">![Viewing network configuration data.](images/JJ945604.b72a4c21-a042-4d91-bf96-fcb396af0679(OCS.15).jpg "Viewing network configuration data.")</span></span>

<span data-ttu-id="7a9eb-539">**Ver la topología de red de CAC en un estilo de vista de árbol:** Lync Server 2013 los administradores pueden ver los datos de configuración de red relacionados en un estilo de vista de árbol gráfico usando el panel de control en el lado izquierdo de la ventana de herramientas, tal como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-539">**View CAC network topology in a tree-view style:** Lync Server 2013 administrators can view related network configuration data in a graphical tree view style by using the control panel on the left side of the tool window as shown below.</span></span>

<span data-ttu-id="7a9eb-540">![Ver los datos de configuración de red en una vista de árbol.](images/JJ945604.4d924ac9-fd96-430f-b211-ee35b7ef9a23(OCS.15).jpg "Ver los datos de configuración de red en una vista de árbol.")</span><span class="sxs-lookup"><span data-stu-id="7a9eb-540">![Viewing network configuration data in a tree-view.](images/JJ945604.4d924ac9-fd96-430f-b211-ee35b7ef9a23(OCS.15).jpg "Viewing network configuration data in a tree-view.")</span></span>

<span data-ttu-id="7a9eb-541">**Definir conectores personalizados para los vínculos de topología de red de CAC (como vínculos de sitio a región, de región a región y de sitio a sitio):** Lync Server 2013 los administradores pueden definir conectores gráficos personalizados para los vínculos WAN de configuración de red de CAC mediante la opción configuración, tal como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-541">**Define custom connectors for CAC network topology links (such as site-to-region, region-to-region, and site-to-site links):** Lync Server 2013 administrators can define custom graphical connectors for CAC network configuration WAN links by using the Settings option as shown below.</span></span> <span data-ttu-id="7a9eb-542">Esto ayuda a diferenciar entre varios tipos de vínculos de red que se aprovisionan en la configuración de red.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-542">This helps differentiate between various types of network links that are provisioned in the network configuration.</span></span>

<span data-ttu-id="7a9eb-543">![Definir conectores personalizados para la topología de red de CAC](images/JJ945604.b20bea67-c8e1-453e-b1dd-e2aa17b62566(OCS.15).jpg "Definir conectores personalizados para la topología de red de CAC")</span><span class="sxs-lookup"><span data-stu-id="7a9eb-543">![Define custom connectors for CAC network topology](images/JJ945604.b20bea67-c8e1-453e-b1dd-e2aa17b62566(OCS.15).jpg "Define custom connectors for CAC network topology")</span></span>

<span data-ttu-id="7a9eb-544">**Ver la información del sitio de la topología de red de CAC, información de región y directivas de ancho de banda aprovisionadas:** Lync Server 2013 los administradores pueden ver la información de región de red CAC, la información del sitio y la información de aprovisionamiento de ancho de banda de CAC relacionadas mediante las opciones que se muestran a continuación.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-544">**View CAC network topology site information, region information, and provisioned bandwidth policies:** Lync Server 2013 administrators can view related CAC network region information, site information, and CAC bandwidth provisioning information by using options shown below.</span></span> <span data-ttu-id="7a9eb-545">(Por ejemplo, haga clic en **información** en una región de red o un objeto de sitio de red).</span><span class="sxs-lookup"><span data-stu-id="7a9eb-545">(For example, click **Info** in a network region or network site object.)</span></span>

<span data-ttu-id="7a9eb-546">![Definir conectores personalizados para la red.](images/JJ945604.26262c75-4342-41c3-bc98-1793aa6a7713(OCS.15).jpg "Definir conectores personalizados para la red.")</span><span class="sxs-lookup"><span data-stu-id="7a9eb-546">![Defining custom connectors for your network.](images/JJ945604.26262c75-4342-41c3-bc98-1793aa6a7713(OCS.15).jpg "Defining custom connectors for your network.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="7a9eb-547">Resumen</span><span class="sxs-lookup"><span data-stu-id="7a9eb-547">Summary</span></span>

<span data-ttu-id="7a9eb-548">Esta herramienta puede ser un recurso valioso para los administradores de Lync Server 2013 que quieran ver la topología de red de CAC para su implementación en un formato gráfico.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-548">This tool can be a valuable resource to Lync Server 2013 administrators who would like to view CAC network topology for their deployment in a graphical format.</span></span>

</div>

</div>

<div>

## <a name="response-group-agent-live"></a><span data-ttu-id="7a9eb-549">Response Group Agent Live</span><span class="sxs-lookup"><span data-stu-id="7a9eb-549">Response Group Agent Live</span></span>

<span data-ttu-id="7a9eb-550">La aplicación de grupo de respuesta ofrece a los agentes la capacidad de tener acceso a información útil en tiempo real mediante su servicio Web integrado.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-550">The Response Group application gives agents the ability to access useful real-time information using its built-in Web service.</span></span> <span data-ttu-id="7a9eb-551">Desafortunadamente, no hay ninguna vista gráfica de estos datos disponibles fuera de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-551">Unfortunately, no graphical view of this data is available outside the application.</span></span> <span data-ttu-id="7a9eb-552">La herramienta de kit de recursos Live Response Agent Live Report resuelve este problema proporcionando una forma sencilla y gráfica para obtener acceso a esta información, mejorada con información de software de comunicaciones en tiempo real de Microsoft Lync 2013, como la presencia de otros agentes.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-552">The Response Group Agent Live Resource Kit tool solves this issue by providing a simple and graphical way to access this information, enhanced with real-time Microsoft Lync 2013 communications software information such as the presence of other agents.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="7a9eb-553">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a9eb-553">Description</span></span>

<span data-ttu-id="7a9eb-554">Response Group Agent Live es una aplicación de Windows que proporciona la funcionalidad de inicio y cierre de sesión, así como información en tiempo real (como la pertenencia a grupos y el número actual de llamadas) a los agentes del grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-554">Response Group Agent Live is a Windows application that provides sign-in and sign-out functionality and some real-time information (such as group membership and current number of calls) to Response Group agents.</span></span> <span data-ttu-id="7a9eb-555">Está diseñada para ser una versión mejorada de la página grupos de agentes (accesible desde Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-555">It is meant to be an enhanced version of the Agent Groups page (accessible from Lync 2013.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="7a9eb-556">Finalidad</span><span class="sxs-lookup"><span data-stu-id="7a9eb-556">Purpose</span></span>

<span data-ttu-id="7a9eb-557">La aplicación de grupo de respuesta pone en cola las llamadas entrantes y, a continuación, las enruta a los grupos de agentes.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-557">The Response Group application queues incoming calls, and then routes them to agent groups.</span></span> <span data-ttu-id="7a9eb-558">Para tomar decisiones informadas sobre las llamadas al servicio, los agentes pueden obtener acceso a información en tiempo real sobre sus grupos de agentes, como qué otros agentes están disponibles y cuántas llamadas están esperando en cada cola.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-558">To make informed decisions about which calls to service, agents can access real-time information about their agent groups, such as what other agents are available and how many calls are waiting in each queue.</span></span> <span data-ttu-id="7a9eb-559">Esta información, inicialmente accesible solo a través del servicio de grupo de respuesta, está disponible de forma intuitiva mediante Response Group Agent Live.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-559">This information, initially accessible only through the Response Group service, is made available in an intuitive way by Response Group Agent Live.</span></span>

<div>

## <a name="features"></a><span data-ttu-id="7a9eb-560">Características</span><span class="sxs-lookup"><span data-stu-id="7a9eb-560">Features</span></span>

<span data-ttu-id="7a9eb-561">La herramienta Response Group Agent Live se basa en el servicio de grupo de respuesta y el SDK de Microsoft Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-561">The Response Group Agent Live tool is built on the Response Group service and the Microsoft Lync 2013 SDK.</span></span> <span data-ttu-id="7a9eb-562">Proporciona agentes de grupo de respuesta información y capacidades que están disponibles en el servicio de grupo de respuesta (como la pertenencia a grupos, la presencia de otros agentes y el número de llamadas en espera).</span><span class="sxs-lookup"><span data-stu-id="7a9eb-562">It provides Response Group agents the information and capabilities that are available from the Response Group service (such as group membership, presence of other agents, and number of waiting calls).</span></span>

<span data-ttu-id="7a9eb-563">La ilustración siguiente muestra la interfaz principal de Response Group Agent Live.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-563">The figure below illustrates the main interface of Response Group Agent Live.</span></span>

<span data-ttu-id="7a9eb-564">![La herramienta Response Group Agent Live.](images/JJ945604.63cb0374-a6ef-4a59-b60e-bec86a880d09(OCS.15).jpg "La herramienta Response Group Agent Live.")</span><span class="sxs-lookup"><span data-stu-id="7a9eb-564">![The Response Group Agent Live tool.](images/JJ945604.63cb0374-a6ef-4a59-b60e-bec86a880d09(OCS.15).jpg "The Response Group Agent Live tool.")</span></span>

<span data-ttu-id="7a9eb-565">Las siguientes tres características principales están disponibles para los agentes en Response Group Agent Live:</span><span class="sxs-lookup"><span data-stu-id="7a9eb-565">The following three main features are available for agents in Response Group Agent Live:</span></span>

  - <span data-ttu-id="7a9eb-566">**Iniciar/cerrar sesión:** Al contrario que la página grupos de agentes (accesible desde Lync 2013), el agente de grupo de respuesta Live permite que solo los agentes inicien o salgan de todos los grupos de agentes a la vez.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-566">**Sign-in/out:** Contrary to the Agent Groups page (accessible from Lync 2013), Response Group Agent Live allows only agents to sign-in or out of all agent groups at once.</span></span> <span data-ttu-id="7a9eb-567">Esta aplicación proporciona tres métodos rápidos para que los agentes inicien o cierren sesión:</span><span class="sxs-lookup"><span data-stu-id="7a9eb-567">This application provides three quick ways for agents to sign in or out:</span></span>
    
      - <span data-ttu-id="7a9eb-568">Haga clic en los botones de inicio y cierre de sesión (verde y rojo) dentro de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-568">Click the Sign-in/out (green and red) buttons within the application.</span></span>
    
      - <span data-ttu-id="7a9eb-569">Haga clic con el botón derecho en el icono de la bandeja del sistema y seleccione iniciar sesión o cerrar sesión.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-569">Right-click the system tray icon, and select sign in or sign out.</span></span>
    
      - <span data-ttu-id="7a9eb-570">Usar métodos abreviados de teclado configurables.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-570">Using configurable keyboard shortcuts.</span></span>

  - <span data-ttu-id="7a9eb-571">**Pertenencia a grupos:** Cuando se selecciona un grupo de agentes, Response Group Agent Live muestra la lista de agentes de este grupo en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-571">**Group membership:** When an agent group is selected, Response Group Agent Live displays the list of agents in this group in the right pane.</span></span> <span data-ttu-id="7a9eb-572">Si Lync 2013 se está ejecutando en el mismo equipo que esta aplicación, la información de presencia y la tarjeta de contacto se muestran en el Group Response Agent Live.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-572">If Lync 2013 is running on the same computer as this application, presence information and the contact card are displayed in the Response Group Agent Live.</span></span> <span data-ttu-id="7a9eb-573">Los agentes pueden enviar un mensaje instantáneo o llamar a otros agentes directamente desde allí.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-573">Agents can send an IM or call other agents directly from there.</span></span>

  - <span data-ttu-id="7a9eb-574">**Estadísticas en tiempo real:** Response Group Agent Live proporciona estadísticas en tiempo real para todos los grupos de agentes.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-574">**Real-time statistics:** Response Group Agent Live provides real-time statistics for all agent groups.</span></span> <span data-ttu-id="7a9eb-575">La frecuencia de actualización es un minuto.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-575">The update frequency is one minute.</span></span> <span data-ttu-id="7a9eb-576">Cuando un grupo de respuesta responde a una llamada, se agrega un indicador visual junto al nombre del grupo con el número actual de llamadas en cola.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-576">When a call is answered by a Response Group, a visual indicator is added next to the group name with the current number of queued calls.</span></span> <span data-ttu-id="7a9eb-577">Al pausar el puntero sobre un grupo, también se muestra el tiempo de espera más largo.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-577">Pausing the pointer over a group also displays the longest waiting time.</span></span>

</div>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="7a9eb-578">Requirements</span><span class="sxs-lookup"><span data-stu-id="7a9eb-578">Requirements</span></span>

<span data-ttu-id="7a9eb-579">Response Group Agent Live requiere .NET Framework 4,0.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-579">Response Group Agent Live requires the .NET Framework 4.0.</span></span> <span data-ttu-id="7a9eb-580">Además, para aprovechar las características de presencia y tarjeta de contacto, Lync 2013 debe estar instalado de forma local (y estar en ejecución).</span><span class="sxs-lookup"><span data-stu-id="7a9eb-580">In addition, to take advantage of the presence and contact card features, Lync 2013 must be installed locally (and be running).</span></span>

<div>

## <a name="configuration"></a><span data-ttu-id="7a9eb-581">Configuración</span><span class="sxs-lookup"><span data-stu-id="7a9eb-581">Configuration</span></span>

<span data-ttu-id="7a9eb-582">Response Group Agent Live puede personalizarse según las preferencias individuales mediante el cuadro de diálogo Opciones de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-582">Response Group Agent Live can be customized to individual preferences by using the Options dialog box in the application.</span></span> <span data-ttu-id="7a9eb-583">Además, el administrador puede definir la dirección de host predeterminada editando directamente la propiedad defaultHostAddress del archivo de RGAgentLive.exe.config.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-583">In addition, the administrator can define the default host address by editing directly the defaultHostAddress property of the RGAgentLive.exe.config file.</span></span>

<span data-ttu-id="7a9eb-584">La ilustración siguiente muestra el cuadro de diálogo Opciones que los agentes pueden usar para configurar las teclas de acceso directo y dirección de host.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-584">The figure below illustrates the Options dialog box that agents can use to configure the host address and shortcut keys.</span></span> <span data-ttu-id="7a9eb-585">Para obtener acceso a este cuadro de diálogo, haga clic en el botón Opciones de la parte superior derecha de la interfaz principal.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-585">This dialog is accessed by clicking the Options button on the top right of the main interface.</span></span>

<span data-ttu-id="7a9eb-586">![El cuadro de diálogo Opciones del agente de respuesta dinámica del grupo de respuesta.](images/JJ945604.3cc15e29-8699-45ab-90c3-e1565fa6ebf6(OCS.15).jpg "El cuadro de diálogo Opciones del agente de respuesta dinámica del grupo de respuesta.")</span><span class="sxs-lookup"><span data-stu-id="7a9eb-586">![The Response Group Agent Live Options dialog box.](images/JJ945604.3cc15e29-8699-45ab-90c3-e1565fa6ebf6(OCS.15).jpg "The Response Group Agent Live Options dialog box.")</span></span>

<span data-ttu-id="7a9eb-587">Las siguientes tres opciones de configuración distintas se pueden personalizar en la configuración de agente de grupo de respuesta:</span><span class="sxs-lookup"><span data-stu-id="7a9eb-587">The following three different settings can be customized in the Response Group Agent Live configuration:</span></span>

  - <span data-ttu-id="7a9eb-588">Dirección de host: suele ser el FQDN del grupo de servidores web que pertenece al grupo principal del agente.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-588">Host address: This is typically the web pool FQDN belonging to the agent’s home pool.</span></span> <span data-ttu-id="7a9eb-589">La dirección exacta del servicio del grupo de respuesta se deriva automáticamente en segundo plano a partir de esta información (anexando la ruta de acceso correcta después del host).</span><span class="sxs-lookup"><span data-stu-id="7a9eb-589">The exact Response Group service address is automatically derived in the background from this information (by appending the right path after the host).</span></span>

  - <span data-ttu-id="7a9eb-590">Accesos directos: los métodos abreviados exactos para iniciar y cerrar sesión pueden personalizarse.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-590">Shortcuts: The exact shortcuts to sign-in/out can be customized.</span></span> <span data-ttu-id="7a9eb-591">La única limitación es que ambos métodos abreviados deben contener la tecla del logotipo de Windows (además de, al menos, otra tecla).</span><span class="sxs-lookup"><span data-stu-id="7a9eb-591">The only limitation is that both shortcuts must contain the “Windows Logo” key (in addition to at least another key).</span></span>

  - <span data-ttu-id="7a9eb-592">Iniciar con Windows: la aplicación se puede configurar para iniciarse automáticamente con Windows.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-592">Start with Windows: The application can be configured to start automatically with Windows.</span></span>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="7a9eb-593">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="7a9eb-593">Examples</span></span>

<span data-ttu-id="7a9eb-594">En la siguiente figura se muestra cómo llamar o enviar un mensaje instantáneo a otro agente haciendo clic con el botón secundario en el contacto en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-594">The figure below illustrates how to call or send an IM to another agent by right-clicking the contact in the right pane.</span></span>

<span data-ttu-id="7a9eb-595">![Hacer una llamada o enviar un mensaje instantáneo.](images/JJ945604.009cebe0-5a93-4745-89c3-8a16c7c13009(OCS.15).jpg "Hacer una llamada o enviar un mensaje instantáneo.")</span><span class="sxs-lookup"><span data-stu-id="7a9eb-595">![Making a call or sending an IM.](images/JJ945604.009cebe0-5a93-4745-89c3-8a16c7c13009(OCS.15).jpg "Making a call or sending an IM.")</span></span>

<span data-ttu-id="7a9eb-596">La ilustración siguiente muestra cómo Response Group Agent Live muestra el número actual de llamadas en la cola y el tiempo de espera más largo entre todas estas llamadas entrantes.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-596">The figure below illustrates how Response Group Agent Live displays the current number of calls in the queue and the longest waiting time among all these incoming calls.</span></span>

<span data-ttu-id="7a9eb-597">![Ver información de cola.](images/JJ945604.131d7f79-b7ed-41f5-a9da-ffc556e31037(OCS.15).jpg "Ver información de cola.")</span><span class="sxs-lookup"><span data-stu-id="7a9eb-597">![Viewing queue information.](images/JJ945604.131d7f79-b7ed-41f5-a9da-ffc556e31037(OCS.15).jpg "Viewing queue information.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="7a9eb-598">Resumen</span><span class="sxs-lookup"><span data-stu-id="7a9eb-598">Summary</span></span>

<span data-ttu-id="7a9eb-599">La rapidez en el inicio y el cierre de sesión, la pertenencia a grupos y las estadísticas básicas en tiempo real son características interesantes del agente de grupo de respuesta que solo están disponibles fuera de la aplicación desde el servicio de grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-599">Fast sign-in and sign-out, group membership, and basic real-time statistics are interesting Response Group agent features that are only available outside the application from the Response Group service.</span></span> <span data-ttu-id="7a9eb-600">Con la herramienta del kit de recursos del agente de grupo de respuesta Live, los administradores de Lync pueden proporcionar a sus agentes una aplicación de Windows que les permita realizar tareas de una manera gráfica y rápida.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-600">With the Response Group Agent Live Resource Kit tool, Lync administrators can provide their agents with a Windows application that allows them to perform tasks in a faster and graphical way.</span></span>

</div>

</div>

<div>

## <a name="sefautil"></a><span data-ttu-id="7a9eb-601">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="7a9eb-601">SEFAUtil</span></span>

<span data-ttu-id="7a9eb-602">SEFAUtil (la activación de características de extensión secundaria) es una herramienta de línea de comandos que permite a los administradores de software de comunicaciones de Microsoft Lync Server 2013 y a los agentes de asistencia técnica configurar las llamadas delegadas, el desvío de llamadas, las llamadas simultáneas, la configuración de llamada de equipo y la recogida de llamadas de grupo en nombre de un usuario de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-602">SEFAUtil (secondary extension feature activation) is a command-line tool that enables Microsoft Lync Server 2013 communications software administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Lync Server 2013 user.</span></span> <span data-ttu-id="7a9eb-603">La herramienta también permite a los administradores consultar la configuración de enrutamiento de llamadas publicada para un usuario en particular. La herramienta SEFAUtil permite al administrador habilitar/deshabilitar/modificar el desvío de llamadas o las llamadas simultáneas en nombre del usuario.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-603">The tool also allows administrators to query the call-routing settings that are published for a particular user.The SEFAUtil tool allows the administrator to enable/disable/modify call forwarding or simultaneously ringing on behalf of the user.</span></span> <span data-ttu-id="7a9eb-604">El administrador puede especificar el destino (en forma de URI de SIP) o usar un destino ya publicado por el usuario.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-604">The administrator can specify the target (in the form of a SIP URI) or use a target that has already been published by the user.</span></span> <span data-ttu-id="7a9eb-605">Esta herramienta también permite a los administradores agregar o quitar delegados o miembros del grupo de llamada de equipo en nombre del usuario. Esta herramienta se basa en la API administrada de comunicaciones unificadas de Microsoft (UCMA) 3,0 y requiere que los administradores creen una aplicación de confianza en el almacén de administración central para SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="7a9eb-605">This tool also allows administrators to add or remove delegates or team-call group members on behalf of the user.This tool is built on Microsoft Unified Communications Managed API (UCMA) 3.0 and requires that administrators create a trusted application in the Central Management store for SEFAUtil</span></span>

<span data-ttu-id="7a9eb-606">SEFAUtil (activación de características de extensión secundaria) permite a los administradores y los agentes del Departamento de soporte técnico de Lync Server 2013 configurar llamadas delegadas, el desvío de llamadas, las llamadas simultáneas, la configuración de llamada de equipo y la recogida de llamadas de grupo en nombre de un usuario de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-606">SEFAUtil (secondary extension feature activation) enables Lync Server 2013 administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Lync Server 2013 user.</span></span> <span data-ttu-id="7a9eb-607">Esta herramienta también permite a los administradores consultar la configuración de enrutamiento de llamadas publicada para un usuario en particular.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-607">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="7a9eb-608">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a9eb-608">Description</span></span>

<span data-ttu-id="7a9eb-609">La versión actual de SEFAUtil es solo una herramienta de línea de comandos; no hay ninguna interfaz gráfica de usuario compatible.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-609">The current version of SEFAUtil is only a command-line tool; there is no supporting graphical user interface.</span></span> <span data-ttu-id="7a9eb-610">Esta herramienta se basa en la API administrada de comunicaciones unificadas de Microsoft (UCMA) 3,0.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-610">This tool is based on Microsoft Unified Communications Managed API (UCMA) 3.0.</span></span> <span data-ttu-id="7a9eb-611">Las características de esta herramienta permiten que los administradores y los agentes del Departamento de soporte técnico hagan lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7a9eb-611">The features in this tool allow administrators and helpdesk agents to do the following:</span></span>

  - <span data-ttu-id="7a9eb-612">Ver toda la configuración de enrutamiento de llamadas de un usuario (incluye el desvío de llamadas, la delegación, las llamadas simultáneas, la llamada de equipo y la atención de llamadas de grupo)</span><span class="sxs-lookup"><span data-stu-id="7a9eb-612">View all call routing settings for a user (includes call-forwarding, delegation, simultaneous ringing, team-call and group call pickup)</span></span>

  - <span data-ttu-id="7a9eb-613">Habilitar/deshabilitar/modificar la configuración de desvío de llamadas (incluye el destino y el temporizador sin respuesta)</span><span class="sxs-lookup"><span data-stu-id="7a9eb-613">Enable/disable/modify call-forwarding setting (includes destination and no-answer timer)</span></span>

  - <span data-ttu-id="7a9eb-614">Habilitar/deshabilitar/modificar las configuraciones inmediatas de reenvío de llamadas</span><span class="sxs-lookup"><span data-stu-id="7a9eb-614">Enable/disable/modify call-forwarding immediate configurations</span></span>

  - <span data-ttu-id="7a9eb-615">Habilitar/deshabilitar/modificar la configuración de la delegación</span><span class="sxs-lookup"><span data-stu-id="7a9eb-615">Enable/disable/modify delegation settings</span></span>

  - <span data-ttu-id="7a9eb-616">Habilitar/deshabilitar/modificar la configuración de grupo de llamada de equipo</span><span class="sxs-lookup"><span data-stu-id="7a9eb-616">Enable/disable/modify team-call group settings</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7a9eb-617">Nueva en Lync Server 2013 herramienta SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="7a9eb-617">New in Lync Server 2013 SEFAUtil tool</span></span>

    
    </div>

  - <span data-ttu-id="7a9eb-618">Habilitar/deshabilitar/modificar la configuración de llamadas simultáneas (incluye el destino)</span><span class="sxs-lookup"><span data-stu-id="7a9eb-618">Enable/disable/modify simultaneous ringing settings (includes destination)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7a9eb-619">Nueva en Lync Server 2013 herramienta SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="7a9eb-619">New in Lync Server 2013 SEFAUtil tool</span></span>

    
    </div>

  - <span data-ttu-id="7a9eb-620">Habilitar/deshabilitar/modificar la configuración de RECALL de llamadas de grupo</span><span class="sxs-lookup"><span data-stu-id="7a9eb-620">Enable/disable/modify group call pickup settings</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="7a9eb-621">Nueva en Lync Server 2013 herramienta SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="7a9eb-621">New in Lync Server 2013 SEFAUtil tool</span></span>

    
    </div>

<span data-ttu-id="7a9eb-622">Esta herramienta tiene las siguientes limitaciones:</span><span class="sxs-lookup"><span data-stu-id="7a9eb-622">This tool has the following limitations:</span></span>

  - <span data-ttu-id="7a9eb-623">Compatible solo para usuarios hospedados en un grupo de servidores de Lync Server</span><span class="sxs-lookup"><span data-stu-id="7a9eb-623">Supported only for users homed in a Lync Server pool</span></span>

  - <span data-ttu-id="7a9eb-624">No se admite la edición en masa de la configuración de enrutamiento de llamadas para varios usuarios</span><span class="sxs-lookup"><span data-stu-id="7a9eb-624">Bulk-edit of call routing settings for several users is not supported</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="7a9eb-625">Output</span><span class="sxs-lookup"><span data-stu-id="7a9eb-625">Output</span></span>

<span data-ttu-id="7a9eb-626">La versión actual de esta herramienta proporciona resultados sólo en la ventana del símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-626">The current version of this tool provides output only in the Command Prompt window.</span></span> <span data-ttu-id="7a9eb-627">Para obtener más información, vea la sección ejemplos más adelante en este documento.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-627">For details, see the Examples section later in this document.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="7a9eb-628">Finalidad</span><span class="sxs-lookup"><span data-stu-id="7a9eb-628">Purpose</span></span>

<span data-ttu-id="7a9eb-629">A continuación se muestran algunos de los escenarios clave en los que se puede usar esta herramienta:</span><span class="sxs-lookup"><span data-stu-id="7a9eb-629">Following are some of the key scenarios where this tool may be used:</span></span>

  - <span data-ttu-id="7a9eb-630">Bob es un ejecutivo y se ha movido a la telefonía de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-630">Bob is an executive and has been moved to Lync Server telephony.</span></span> <span data-ttu-id="7a9eb-631">Ha delegado en su sistema PBX existente.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-631">He has delegation on his existing PBX system.</span></span> <span data-ttu-id="7a9eb-632">Como parte de la migración a Lync, el administrador puede configurar el enrutamiento de Bob para reflejar su configuración de delegación preexistente.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-632">As part of the move to Lync, the administrator is able to configure Bob’s routing to reflect his pre-existing delegation configuration.</span></span>

  - <span data-ttu-id="7a9eb-633">Alicia está viajando y se da cuenta de que espera una llamada importante de uno de sus clientes.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-633">Alice is travelling and realizes that she is expecting an important call from one of her customers.</span></span> <span data-ttu-id="7a9eb-634">Sin embargo, se encuentra en un hotel y no tiene acceso a un equipo.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-634">However, she is in a hotel and has no access to a computer.</span></span> <span data-ttu-id="7a9eb-635">Llama al Departamento de soporte técnico y solicita que se reenvíen a su número de teléfono móvil todas las llamadas realizadas a su número de trabajo.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-635">She calls the helpdesk and requests that they forward to her mobile number all the calls made to her work number.</span></span> <span data-ttu-id="7a9eb-636">El personal del Departamento de soporte técnico puede realizar la configuración en su nombre.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-636">The helpdesk personnel are able to do the configuration on her behalf.</span></span>

  - <span data-ttu-id="7a9eb-637">Las llamadas de Joe a su número de trabajo van a su correo de voz móvil siempre que esté en el trabajo; sin embargo, las cosas parecen funcionar correctamente en la mayoría de las demás ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-637">Joe’s calls to his work number are going to his mobile voicemail whenever he is at work; however, things appear to be working correctly in most other locations.</span></span> <span data-ttu-id="7a9eb-638">El técnico del Departamento de soporte técnico puede ver la configuración de enrutamiento de Joe y detecta que José ha configurado las llamadas simultáneas a su teléfono móvil.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-638">The helpdesk technician is able to view Joe’s routing configuration and discovers that Joe has simultaneous ringing configured to his mobile phone.</span></span> <span data-ttu-id="7a9eb-639">El técnico pregunta a Joe sobre la cobertura móvil en su oficina y puede determinar que la regla de timbre simultáneo es lo que está causando que las llamadas se desplazan al correo de voz móvil de Joe cuando su cobertura de red es deficiente.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-639">The technician asks Joe about the mobile coverage at his office and is able to determine that the simultaneous ringing rule is what is causing the calls to go to Joe’s mobile voicemail when his network coverage is poor.</span></span>

  - <span data-ttu-id="7a9eb-640">Mike es un nuevo empleado de Contoso y se une a un nuevo equipo en el que todos los miembros están configurados para la llamada de equipo, cuando se habilita para Microsoft Lync, el administrador puede establecer la configuración del grupo de llamada de equipo para incluir a todos los nuevos miembros del equipo, además, el administrador agrega Mike como miembro del grupo de llamada de equipo para cada miembro de su equipo</span><span class="sxs-lookup"><span data-stu-id="7a9eb-640">Mike is a new employee at Contoso and he’s joining a new team on which all members are configured for team-call, when being enabled for Microsoft Lync, the administrator is able to set his team-call group settings to include all his new team members, additionally, the administrator adds Mike as a team-call group member for each of the members in his team.</span></span>

  - <span data-ttu-id="7a9eb-641">Una práctica de servicio al cliente en el Departamento de recursos humanos de Contoso es proporcionar servicio personal para todos los autores de llamadas desde la primera llamada.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-641">A customer service practice in the human resources department at Contoso is to provide personal service for all callers since the first call.</span></span> <span data-ttu-id="7a9eb-642">Dado que todos los miembros del Departamento se encuentran muy cercanos entre sí, tener todos los teléfonos que suenen al mismo tiempo con la llamada de equipo es muy disruptiva para el equipo.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-642">Given that all members of the department sit very close to each other, having all phones ringing at the same time with team-call is very disruptive for the team.</span></span> <span data-ttu-id="7a9eb-643">Para proporcionar el mejor servicio sin interrumpir a los miembros del equipo, el administrador de Lync aprovecha la capacidad de RECALL de llamadas grupales.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-643">To provide the best service without disrupting the team members, the Lync administrator takes advantage of the Group Call Pickup capability.</span></span> <span data-ttu-id="7a9eb-644">El administrador agrega todos los miembros del Departamento a un grupo de recogida y se comunica con el número de grupo de recogida del Departamento.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-644">The administrator adds all department members to a pickup group and communicates to the department the pickup group number.</span></span> <span data-ttu-id="7a9eb-645">Cuando Samantha no está en su escritorio, Joe detecta su timbre telefónico y continúa respondiendo a la llamada desde su escritorio.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-645">When Samantha is absent from her desk, Joe notices her phone ringing and he proceeds to answer the call from his desk.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="7a9eb-646">Requirements</span><span class="sxs-lookup"><span data-stu-id="7a9eb-646">Requirements</span></span>

<span data-ttu-id="7a9eb-647">La herramienta SEFAUtil solo puede ejecutarse en un equipo que forme parte de un grupo de aplicaciones de confianza.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-647">The SEFAUtil tool can be run only on a computer that is a part of a Trusted Application Pool.</span></span> <span data-ttu-id="7a9eb-648">UCMA 3,0 debe estar instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-648">UCMA 3.0 must be installed on that computer.</span></span> <span data-ttu-id="7a9eb-649">Para ejecutar la herramienta, se debe crear una nueva aplicación de confianza con el identificador de la aplicación SEFAUtil en ese grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-649">To run the tool, a new Trusted Application with the SEFAUtil application ID must be created on that pool.</span></span>

<span data-ttu-id="7a9eb-650">**Creación de una nueva aplicación de confianza para la herramienta SEFAUtil**</span><span class="sxs-lookup"><span data-stu-id="7a9eb-650">**Creating a new Trusted Application for the SEFAUtil tool**</span></span>

1.  <span data-ttu-id="7a9eb-651">La herramienta SEFAUTil solo puede ejecutarse en un equipo que forme parte de un grupo de aplicaciones de confianza.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-651">The SEFAUTil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="7a9eb-652">Si es necesario, puede Agregar un grupo de servidores como un nuevo grupo de aplicaciones de confianza mediante el shell de administración de Lync Server con el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="7a9eb-652">If needed, adding a pool as a new trusted application pool can be done via the Lync Server Management Shell with the following cmdlet:</span></span>
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7a9eb-653">UCMA 3,0 debe instalarse en cualquier equipo que se use para ejecutar la herramienta SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-653">UCMA 3.0 must be installed on any computer that will be used to run the SEFAUtil tool.</span></span>

    
    </div>

2.  <span data-ttu-id="7a9eb-654">Una aplicación de confianza debe definirse en la topología de la herramienta SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-654">A trusted application needs to be defined in the topology for the SEFAUtil tool.</span></span> <span data-ttu-id="7a9eb-655">Para definir SEFAUtil como una nueva aplicación de confianza, use el shell de administración de Lync Server y ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="7a9eb-655">To define SEFAUtil as a new trusted application, use the Lync Server Management Shell and execute the following cmdlet:</span></span>
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7a9eb-656">Si es necesario, se puede usar un puerto diferente.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-656">A different port can be used if needed.</span></span>

    
    </div>

3.  <span data-ttu-id="7a9eb-657">Los cambios en la topología deben estar habilitados.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-657">The topology changes need to be enabled.</span></span> <span data-ttu-id="7a9eb-658">La habilitación de los cambios en la topología se puede realizar mediante el shell de administración de Lync Server ejecutando el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="7a9eb-658">Enabling the topology changes can be done via the Lync Server Management Shell by executing the following cmdlet:</span></span>
    
        Enable-CsToplogy

4.  <span data-ttu-id="7a9eb-659">Si es necesario, instale las herramientas del kit de recursos de Lync Server 2013 en el servidor que se usará para ejecutar la herramienta SEFAUtil (el servidor debe formar parte de un grupo de aplicaciones de confianza).</span><span class="sxs-lookup"><span data-stu-id="7a9eb-659">If needed, install the Lync Server 2013 Resource Kit Tools in the server that will be used to run the SEFAUtil tool (the server must be part of a trusted application pool).</span></span>

5.  <span data-ttu-id="7a9eb-660">Compruebe que la SEFAUtil se está ejecutando correctamente.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-660">Verify the SEFAUtil is running correctly.</span></span> <span data-ttu-id="7a9eb-661">Para ello, ejecute la herramienta desde un símbolo del sistema de Windows con privilegios de administrador para mostrar la configuración de desvío de llamadas de un usuario en la implementación.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-661">To do this, run the tool from a windows command prompt with administrator privileges to display the call forwarding settings of a user in the deployment.</span></span> <span data-ttu-id="7a9eb-662">De forma predeterminada, la herramienta estará ubicada en: "... \\ Archivos de programa \\ Microsoft Lync Server 2013 \\ reskit ".</span><span class="sxs-lookup"><span data-stu-id="7a9eb-662">By default the tool will be located in: “…\\Program Files\\Microsoft Lync Server 2013\\Reskit”.</span></span> <span data-ttu-id="7a9eb-663">Para mostrar la configuración de desvío de llamadas de un usuario, use el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="7a9eb-663">To display the call forwarding settings of a user, use the following command:</span></span>
    
        SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
    
    <span data-ttu-id="7a9eb-664">Se debe mostrar la configuración de desvío de llamadas del usuario.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-664">The call forwarding settings of the user should be displayed.</span></span>

<div>

## <a name="group-call-pickup"></a><span data-ttu-id="7a9eb-665">Atender llamada grupal</span><span class="sxs-lookup"><span data-stu-id="7a9eb-665">Group Call Pickup</span></span>

<span data-ttu-id="7a9eb-666">La atención de llamadas grupales requiere una configuración adicional en Lync Server para que la capacidad esté totalmente habilitada.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-666">Group Call Pickup requires additional configuration in Lync Server for the capability to be fully enabled.</span></span> <span data-ttu-id="7a9eb-667">Antes de asignar grupos de recogida a los usuarios, consulte la documentación del producto de recogida de llamadas de grupo para conocer los pasos de planeación e implementación de esta función.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-667">Before assigning pickup groups to users, refer to the Group Call Pickup product documentation for the planning and deployment steps of this capability.</span></span>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="7a9eb-668">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="7a9eb-668">Examples</span></span>

<div>

## <a name="display-current-call-handling-settings"></a><span data-ttu-id="7a9eb-669">Mostrar la configuración de control de llamadas actual</span><span class="sxs-lookup"><span data-stu-id="7a9eb-669">Display Current Call Handling Settings</span></span>

<span data-ttu-id="7a9eb-670">El siguiente comando muestra el control de llamadas del usuario.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-670">The following command displays the call handling for the user.</span></span> `SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com`

<div>


> [!NOTE]  
> <span data-ttu-id="7a9eb-671">En este ejemplo se usa el modificador <STRONG>/Server</STRONG> para especificar el servidor de Lync al que se va a conectar.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-671">This example uses the <STRONG>/server</STRONG> switch to specify the Lync Server to connect to.</span></span>



</div>

<span data-ttu-id="7a9eb-672">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="7a9eb-672">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:20
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-call-forwardno-answer-destination"></a><span data-ttu-id="7a9eb-673">Establecer el destino de desvío de llamadas/sin respuesta</span><span class="sxs-lookup"><span data-stu-id="7a9eb-673">Set the Call Forward/No Answer Destination</span></span>

<span data-ttu-id="7a9eb-674">En este ejemplo se establece el destino de desvío de llamadas y de no respuesta y el retraso del timbre.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-674">This example sets the call forward/no answer destination and the ring delay.</span></span> <span data-ttu-id="7a9eb-675">Aquí no se proporciona el modificador/Server; SEFAUtil intenta detectar automáticamente el Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-675">Here, the /server switch is not provided; SEFAUtil attempts to autodiscover the Lync Server.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone

<span data-ttu-id="7a9eb-676">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="7a9eb-676">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="enable-call-forwarding-immediately"></a><span data-ttu-id="7a9eb-677">Habilitar el desvío de llamadas inmediatamente</span><span class="sxs-lookup"><span data-stu-id="7a9eb-677">Enable Call Forwarding Immediately</span></span>

<span data-ttu-id="7a9eb-678">En este ejemplo se habilita inmediatamente el desvío de llamadas a otro usuario.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-678">This example immediately enables call-forwarding to another user.</span></span>

    SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com

<span data-ttu-id="7a9eb-679">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="7a9eb-679">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Forward immediate to: sip:anders@contoso.com

</div>

<div>

## <a name="disable-call-forwarding-immediately"></a><span data-ttu-id="7a9eb-680">Deshabilitar el desvío de llamadas inmediatamente</span><span class="sxs-lookup"><span data-stu-id="7a9eb-680">Disable Call Forwarding Immediately</span></span>

<span data-ttu-id="7a9eb-681">En este ejemplo se deshabilita inmediatamente el desvío de llamadas.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-681">This example immediately disables call forwarding.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com  /disablefwdimmediate

<span data-ttu-id="7a9eb-682">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="7a9eb-682">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a><span data-ttu-id="7a9eb-683">Adición de un usuario como delegado y configuración de llamadas simultáneas de delegados</span><span class="sxs-lookup"><span data-stu-id="7a9eb-683">Add a User as a Delegate and Set Up Simultaneous Ringing of Delegates</span></span>

<span data-ttu-id="7a9eb-684">En este ejemplo se agrega un usuario como delegado y se configura la llamada simultánea de los delegados.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-684">This example adds a user as a delegate and sets up simultaneous ringing of delegates.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates

<span data-ttu-id="7a9eb-685">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="7a9eb-685">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simultaneously Ringing Delegates: sip:joe@contoso.com

</div>

<div>

## <a name="change-simultaneous-ringing-rule-of-delegates"></a><span data-ttu-id="7a9eb-686">Cambiar la regla de llamadas simultáneas de delegados</span><span class="sxs-lookup"><span data-stu-id="7a9eb-686">Change Simultaneous Ringing Rule of Delegates</span></span>

<span data-ttu-id="7a9eb-687">En este ejemplo se cambia la regla de llamadas simultáneas que se estableció en el ejemplo anterior por la regla de timbre aplazado.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-687">This example changes the simultaneous ringing rule that was set in the previous example to the delayed ringing rule.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10

<span data-ttu-id="7a9eb-688">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="7a9eb-688">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com

</div>

<div>

## <a name="remove-the-delegate"></a><span data-ttu-id="7a9eb-689">Quitar el delegado</span><span class="sxs-lookup"><span data-stu-id="7a9eb-689">Remove the Delegate</span></span>

<span data-ttu-id="7a9eb-690">En este ejemplo se quita el delegado.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-690">This example removes the delegate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7a9eb-691">Cuando se quita el último delegado, se deshabilita automáticamente el timbre de delegación.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-691">When the last delegate is removed, delegate ringing is automatically disabled.</span></span>



</div>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com

<span data-ttu-id="7a9eb-692">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="7a9eb-692">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a><span data-ttu-id="7a9eb-693">Adición de un delegado y configuración de la regla de Call-Forward a delegados</span><span class="sxs-lookup"><span data-stu-id="7a9eb-693">Add a Delegate and Set Up the Call-Forward to Delegates Rule</span></span>

<span data-ttu-id="7a9eb-694">En este ejemplo se agrega un delegado y se configura la regla de desvío de llamadas a delegados.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-694">This example adds a delegate and sets up the call-forward to delegates rule.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates

<span data-ttu-id="7a9eb-695">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="7a9eb-695">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Forwarding calls to Delegates: sip:anders@contoso.com

</div>

<div>

## <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a><span data-ttu-id="7a9eb-696">Habilitar llamadas simultáneas y establecer un número de destino</span><span class="sxs-lookup"><span data-stu-id="7a9eb-696">Enable Simultaneous Ringing and Set a Destination Number</span></span>

<span data-ttu-id="7a9eb-697">En este ejemplo se habilitan las llamadas simultáneas y se establece un número de destino de llamadas simultáneas.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-697">This example enables simultaneous ringing and sets a simultaneous ringing destination number.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring

<div>


> [!NOTE]  
> <span data-ttu-id="7a9eb-698">Para cambiar el número de destino de llamadas simultáneas de un usuario que ya tiene habilitada la llamada simultánea, mantenga el comando con el modificador/enablesimulring; de lo contrario, no se cambiará el número de destino.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-698">To change the simultaneous ringing destination number of a user that has already simultaneous ringing enabled, keep the command with the /enablesimulring switch, otherwise the destination number will not be changed.</span></span>



</div>

<span data-ttu-id="7a9eb-699">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="7a9eb-699">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: True
    Simul_Ringing to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="disable-simultaneous-ringing"></a><span data-ttu-id="7a9eb-700">Deshabilitar las llamadas simultáneas</span><span class="sxs-lookup"><span data-stu-id="7a9eb-700">Disable Simultaneous Ringing</span></span>

<span data-ttu-id="7a9eb-701">En este ejemplo se deshabilita la característica de llamadas simultáneas.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-701">This example disables simultaneous ringing.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablesimulring

<span data-ttu-id="7a9eb-702">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="7a9eb-702">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a><span data-ttu-id="7a9eb-703">Adición de un integrante del grupo para Team-Call y configuración de llamadas simultáneas al grupo miembros del Team-Call</span><span class="sxs-lookup"><span data-stu-id="7a9eb-703">Add a Team Member for Team-Call and Set up Simultaneous Ringing to the Team-Call Members Group</span></span>

<span data-ttu-id="7a9eb-704">En este ejemplo se agrega un integrante del grupo al grupo de llamada de equipo de un usuario y se habilita la característica de llamadas simultáneas al grupo de llamada de equipo.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-704">This example adds a team member to the team-call group of a user and enables simultaneous ringing to the team-call group.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam

<div>


> [!NOTE]  
> <span data-ttu-id="7a9eb-705">Al agregar un miembro al grupo de llamada de equipo de un usuario, se cambiará automáticamente el configuración de llamadas simultáneas de los usuarios para situaciones su grupo de llamada de equipo.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-705">Adding a member to the team-call group of a user will automatically switch the simultaneous ringing settigs of the users to simulring his team-call group.</span></span>



</div>

<span data-ttu-id="7a9eb-706">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="7a9eb-706">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Team ringing enabled. Team: sip:anders@contoso.com

</div>

<div>

## <a name="remove-a-member-from-the-team-call-group"></a><span data-ttu-id="7a9eb-707">Quitar un miembro del grupo de Team-Call</span><span class="sxs-lookup"><span data-stu-id="7a9eb-707">Remove a Member from the Team-Call Group</span></span>

<span data-ttu-id="7a9eb-708">En este ejemplo se quita un miembro del equipo del grupo de llamada de equipo de un usuario.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-708">This example removes a team member of the team-call group of a user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com

<div>


> [!NOTE]  
> <span data-ttu-id="7a9eb-709">Si el miembro que se va a quitar es el único miembro del grupo de llamada de equipo, las llamadas simultáneas al grupo de llamada de equipo se deshabilitarán de forma automática.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-709">If the member being removed is the only member of the team-call group, simultaneously ringing to the team-call group will be automatically disabled.</span></span>



</div>

<span data-ttu-id="7a9eb-710">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="7a9eb-710">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-delayed-ring-to-the-team-call-group"></a><span data-ttu-id="7a9eb-711">Establecer el anillo retrasado en el grupo de Team-Call</span><span class="sxs-lookup"><span data-stu-id="7a9eb-711">Set the Delayed Ring to the Team-Call Group</span></span>

<span data-ttu-id="7a9eb-712">En este ejemplo se cambia el timbre retrasado a la configuración de hora de grupo de llamada de equipo.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-712">This example changes the delayed ring to the team-call group time setting.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringteam:5

<span data-ttu-id="7a9eb-713">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="7a9eb-713">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com

</div>

<div>

## <a name="enable-team-call"></a><span data-ttu-id="7a9eb-714">Habilitar Team-Call</span><span class="sxs-lookup"><span data-stu-id="7a9eb-714">Enable Team-Call</span></span>

<span data-ttu-id="7a9eb-715">En este ejemplo se habilita la llamada de equipo para un usuario determinado.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-715">This example enables team-call for a given user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /simulringteam

<div>


> [!NOTE]  
> <span data-ttu-id="7a9eb-716">Si el grupo de llamada de equipo del usuario no tiene miembros, la llamada de equipo no se habilitará.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-716">If the team-call group of the user has no members, team-call won’t be enabled.</span></span>



</div>

<span data-ttu-id="7a9eb-717">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="7a9eb-717">**Output**</span></span>

</div>

<div>

## <a name="disable-team-call"></a><span data-ttu-id="7a9eb-718">Deshabilitar Team-Call</span><span class="sxs-lookup"><span data-stu-id="7a9eb-718">Disable Team-Call</span></span>

<span data-ttu-id="7a9eb-719">En este ejemplo se deshabilita la llamada de equipo para un usuario determinado.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-719">This example disables team-call for a given user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disableteamcall

<span data-ttu-id="7a9eb-720">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="7a9eb-720">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a><span data-ttu-id="7a9eb-721">Habilitar la atención de llamadas grupales y asignar un grupo de recogida a un usuario</span><span class="sxs-lookup"><span data-stu-id="7a9eb-721">Enable Group Call Pickup and Assign a Pickup Group to a User</span></span>

<span data-ttu-id="7a9eb-722">En este ejemplo se asigna un grupo de recogida a un usuario y se habilita la recogida de llamadas grupales.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-722">This example assigns a pickup group to a user and enables Group Call Pickup.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199

<span data-ttu-id="7a9eb-723">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="7a9eb-723">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone

</div>

<div>

## <a name="disable-group-call-pickup"></a><span data-ttu-id="7a9eb-724">Deshabilitar la recogida de llamadas de grupo</span><span class="sxs-lookup"><span data-stu-id="7a9eb-724">Disable Group Call Pickup</span></span>

<span data-ttu-id="7a9eb-725">En este ejemplo se deshabilita la llamada de llamadas grupales para un usuario determinado.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-725">This example disables Group Call Pickup for a given user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablegrouppickup

<div>


> [!NOTE]  
> <span data-ttu-id="7a9eb-726">Cuando se deshabilita la recepción de llamadas de grupo para un usuario, no se conserva el número de grupo que se asignó al usuario.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-726">When you disable Group Call Pickup for a user, the group number that was assigned to the user is not retained.</span></span> <span data-ttu-id="7a9eb-727">Si, posteriormente, desea volver a habilitar la atención de llamadas grupales para ese usuario, debe volver a asignar el número de grupo con el modificador/enablegrouppickup.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-727">If you subsequently want to re-enable Group Call Pickup for that user, you must assign the group number again with the /enablegrouppickup switch.</span></span>



</div>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True

</div>

</div>

</div>

<div>

## <a name="sysprepps1"></a><span data-ttu-id="7a9eb-728">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="7a9eb-728">SYSPrep.ps1</span></span>

<div>

## <a name="description"></a><span data-ttu-id="7a9eb-729">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a9eb-729">Description</span></span>

<span data-ttu-id="7a9eb-730">SYSPrep.ps1 es un script de Windows PowerShell que instalará los siguientes requisitos previos de Lync Server 2013 en el equipo del sistema operativo Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-730">SYSPrep.ps1 is a Windows PowerShell script that will install the following Lync Server 2013 prerequisites on your Windows Server 2008 operating system machine.</span></span>

  - <span data-ttu-id="7a9eb-731">Microsoft .NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="7a9eb-731">Microsoft .Net Framework 4.5</span></span>

  - <span data-ttu-id="7a9eb-732">Microsoft SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="7a9eb-732">Microsoft SQL Server Express</span></span>

  - <span data-ttu-id="7a9eb-733">Windows PowerShell versión 3,0</span><span class="sxs-lookup"><span data-stu-id="7a9eb-733">Windows Powershell version 3.0</span></span>

  - <span data-ttu-id="7a9eb-734">Paquete redistribuible de Visual C++ 2010</span><span class="sxs-lookup"><span data-stu-id="7a9eb-734">Visual C++ 2010 Redistributable</span></span>

  - <span data-ttu-id="7a9eb-735">Actualizaciones de Internet Information Server</span><span class="sxs-lookup"><span data-stu-id="7a9eb-735">Internet Information Server Updates</span></span>

  - <span data-ttu-id="7a9eb-736">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="7a9eb-736">Windows Identity Foundation</span></span>

  - <span data-ttu-id="7a9eb-737">Lync Server 2013 archivos principales</span><span class="sxs-lookup"><span data-stu-id="7a9eb-737">Lync Server 2013 Core files</span></span>

<span data-ttu-id="7a9eb-738">Aunque el nombre del script es similar a la herramienta de preparación del sistema para los sistemas operativos de Microsoft Windows, son diferentes.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-738">While the script name is similar to the System Preparation Tool for the Microsoft Windows operating systems, they are different.</span></span> <span data-ttu-id="7a9eb-739">Este script solo instalará los requisitos previos necesarios para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-739">This script will only install the required prerequisites for Lync Server 2013.</span></span> <span data-ttu-id="7a9eb-740">Una vez instalados estos requisitos previos, puede usar la herramienta SYSPrep de Windows para crear una imagen del servidor.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-740">Once those prerequisites are installed, the Windows SYSPrep tool can then be used to create an image of the server.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="7a9eb-741">Requirements</span><span class="sxs-lookup"><span data-stu-id="7a9eb-741">Requirements</span></span>

<span data-ttu-id="7a9eb-742">Antes de ejecutar el script de SYSPrep.ps1, debe copiar los archivos de requisitos previos en una carpeta local del equipo del sistema operativo Windows Server 2008 (por ejemplo, **D: \\ Setup)**.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-742">Prior to running the SYSPrep.ps1 script, you must copy the prerequisite files to a local folder on the Windows Server 2008 operating system machine (for example **D:\\Setup)**.</span></span> <span data-ttu-id="7a9eb-743">Esta carpeta también debe incluir una copia de los archivos de Lync Server 2013, en concreto **Setup.exe.**</span><span class="sxs-lookup"><span data-stu-id="7a9eb-743">This folder must also include a copy of the Lync Server 2013 files, specifically **Setup.exe.**</span></span> <span data-ttu-id="7a9eb-744">Los archivos de requisitos previos se pueden descargar desde las siguientes ubicaciones:</span><span class="sxs-lookup"><span data-stu-id="7a9eb-744">The prerequisite files can be downloaded from the following locations:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7a9eb-745">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="7a9eb-745">Prerequisite</span></span></th>
<th><span data-ttu-id="7a9eb-746">Ubicación</span><span class="sxs-lookup"><span data-stu-id="7a9eb-746">Location</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7a9eb-747">Microsoft .NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="7a9eb-747">Microsoft .Net Framework 4.5</span></span></p></td>
<td><p>https://go.microsoft.com/?linkid=9816306</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a9eb-748">Microsoft SQL Server Express 2008 R2</span><span class="sxs-lookup"><span data-stu-id="7a9eb-748">Microsoft SQL Server Express 2008 R2</span></span></p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=23650</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a9eb-749">Windows PowerShell versión 3,0</span><span class="sxs-lookup"><span data-stu-id="7a9eb-749">Windows Powershell version 3.0</span></span></p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=34595</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a9eb-750">Paquete redistribuible de Visual C++ 2010</span><span class="sxs-lookup"><span data-stu-id="7a9eb-750">Visual C++ 2010 Redistributable</span></span></p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=5555</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a9eb-751">Actualizaciones de Internet Information Server</span><span class="sxs-lookup"><span data-stu-id="7a9eb-751">Internet Information Server Updates</span></span></p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=34869</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a9eb-752">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="7a9eb-752">Windows Identity Foundation</span></span></p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=17331</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a9eb-753">Lync Server 2013 Setup.exe</span><span class="sxs-lookup"><span data-stu-id="7a9eb-753">Lync Server 2013 Setup.exe</span></span></p></td>
<td><p><span data-ttu-id="7a9eb-754">Copiar desde medios de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7a9eb-754">Copy from Lync Server 2013 media</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="parameter"></a><span data-ttu-id="7a9eb-755">Parámetro</span><span class="sxs-lookup"><span data-stu-id="7a9eb-755">Parameter</span></span>

<span data-ttu-id="7a9eb-756">El parámetro **– SetupFolder** toma como argumento la ubicación del directorio de los archivos de requisitos previos</span><span class="sxs-lookup"><span data-stu-id="7a9eb-756">The **–SetupFolder** parameter takes as an argument the directory location of the prerequisite files</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="7a9eb-757">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="7a9eb-757">Examples</span></span>

<span data-ttu-id="7a9eb-758">Para ejecutar el script de SYSPrep.ps1 e instalar los requisitos previos de Lync Server 2013, ejecute el siguiente comando desde un símbolo del sistema con privilegios elevados:</span><span class="sxs-lookup"><span data-stu-id="7a9eb-758">To run the SYSPrep.ps1 script and install the Lync Server 2013 prerequisites, run the following command from an elevated command prompt:</span></span>

    ./SysPrep.PS1 -SetupFolder D:\Setup

</div>

</div>

<div>

## <a name="unassigned-number-announcements-migration"></a><span data-ttu-id="7a9eb-759">Número de anuncios no asignados a la migración</span><span class="sxs-lookup"><span data-stu-id="7a9eb-759">Unassigned Number Announcements Migration</span></span>

<span data-ttu-id="7a9eb-760">La herramienta de migración de anuncios de números sin asignar permite que un administrador de Lync mueva la configuración de números sin asignar a la que presta servicio la aplicación de anuncio de un servidor o grupo de Lync de origen a un servidor o grupo de servidores de Lync de destino.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-760">The Unassigned Number Announcements Migration tool enables a Lync administrator to move the unassigned numbers configuration that is serviced by the announcement application from a source Lync Server or Pool to a destination Lync Server or Pool.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="7a9eb-761">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a9eb-761">Description</span></span>

<span data-ttu-id="7a9eb-762">La herramienta de migración de anuncios de números sin asignar es un script de Windows PowerShell que mueve la configuración de números sin asignar que recibe el servicio de la aplicación de anuncio de un servidor o grupo de origen a otro servidor o grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-762">The Unassigned Number Announcements Migration tool is a Windows PowerShell script that moves the unassigned numbers configuration serviced by the announcement application of a source server or pool to a different server or pool.</span></span>

<span data-ttu-id="7a9eb-763">Cuando se ejecuta, el script de migración de números sin asignar de anuncios realizará las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="7a9eb-763">When executed, the Unassigned Number Announcements Migration script will perform the following operations:</span></span>

1.  <span data-ttu-id="7a9eb-764">Mueva todos los archivos de audio usados por los anuncios de números sin asignar de la aplicación de anuncio hospedada en el servidor o grupo de origen al almacén de archivos del servidor o grupo de destino.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-764">Move all the audio files used by the unassigned number announcements of the announcement application hosted in the source server or pool to the file store of the destination server or pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7a9eb-765">los archivos de audio se quitan del grupo de origen una vez que se copian en el grupo de servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-765">the audio files are removed from the source pool once they’re copied to the destination pool.</span></span>

    
    </div>

2.  <span data-ttu-id="7a9eb-766">Se mueven todos los anuncios de números sin asignar configurados para la aplicación de anuncio hospedada en el servidor o grupo de origen al servidor o grupo de destino.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-766">Move all unassigned number announcements configured for the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

3.  <span data-ttu-id="7a9eb-767">Reasignar todos los intervalos de números no asignados que reciben servicio de la aplicación de anuncio hospedada en el servidor o grupo de origen al servidor o grupo de destino.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-767">Reassign all the unassigned number ranges that are serviced by the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

<span data-ttu-id="7a9eb-768">Después de ejecutar correctamente el script, todos los intervalos de números sin asignar que provienen de la aplicación de anuncio hospedada en el servidor o grupo de servidores de origen se proporcionarán con la misma configuración que el servidor o el grupo de destino.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-768">After successfully running the script, all the unassigned number ranges that were serviced by the announcement application hosted in the source server or pool will now be serviced with the same configuration by the destination server or pool.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="7a9eb-769">Output</span><span class="sxs-lookup"><span data-stu-id="7a9eb-769">Output</span></span>

<span data-ttu-id="7a9eb-770">El script **Move-CsAnnouncementConfiguration** indica en la ventana del shell de administración de Lync desde donde se ejecuta el éxito o el fracaso de la operación de migración.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-770">The **Move-CsAnnouncementConfiguration** script indicates in the Lync Management Shell window from where it’s executed the success or failure of the migration operation.</span></span>

<span data-ttu-id="7a9eb-771">Si cualquier error interrumpe la ejecución de la operación, los intervalos de números sin asignar que se movieron correctamente al destino permanecerán en el destino en un formulario operativo y el resto de los intervalos de números sin asignar que se van a migrar permanecerán en el origen también en un formulario operativo.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-771">If the execution of the operation is interrupted by any error, the unassigned number ranges that were successfully moved to the destination will remain in the destination in an operational form and the rest of the unassigned number ranges to be migrated will remain in the source as well in an operational form.</span></span> <span data-ttu-id="7a9eb-772">Para migrar por completo el resto de la configuración, vuelva a ejecutar el script después de solucionar el error.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-772">To fully migrate the rest of the configuration, rerun the script after addressing the error.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="7a9eb-773">Finalidad</span><span class="sxs-lookup"><span data-stu-id="7a9eb-773">Purpose</span></span>

<span data-ttu-id="7a9eb-774">Se puede usar el script de migración de anuncios de números sin asignar en los tres escenarios siguientes:</span><span class="sxs-lookup"><span data-stu-id="7a9eb-774">The Unassigned Number Announcements Migration script can be used in the following three scenarios:</span></span>

  - <span data-ttu-id="7a9eb-775">**Migrar las opciones de configuración a una nueva versión de Lync Server:** Contoso está en proceso de migrar a Lync Server 2013 y, como parte del proceso de migración, el administrador de Lync Server desearía mover la configuración de números no asignados a la que el anuncio ha dado servicio desde la implementación de Lync Server 2010 a la nueva implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-775">**Migrating configuration settings to a new version of Lync Server:** Contoso is in the process of migrating to Lync Server 2013 and as part of the migration process the Lync Server administrator would like to move the unassigned numbers configuration serviced by the announcement application from the Lync Server 2010 deployment to the new Lync Server 2013 deployment.</span></span> <span data-ttu-id="7a9eb-776">Para mover las opciones de configuración, el administrador de Lync Server usa la herramienta de migración de anuncios de números sin asignar.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-776">To move the configuration settings, the Lync Server administrator uses the Unassigned Number Announcements Migration tool.</span></span>

  - <span data-ttu-id="7a9eb-777">**Revertir una implementación de Lync server 2013 a Lync server 2010:** Debido a los factores inesperados, Contoso tiene que revertir la migración a la nueva implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-777">**Rolling back a deployment from Lync Server 2013 to Lync Server 2010:** Due unexpected factors, Contoso has to roll back the migration to the new Lync Server 2013 deployment.</span></span> <span data-ttu-id="7a9eb-778">Para minimizar las interrupciones en el servicio, el administrador de Lync Server usa la herramienta de migración de anuncios de números sin asignar para revertir la configuración de la implementación de Lync Server 2013 a la implementación de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-778">To minimize disruptions to the service, the Lync Server administrator uses the Unassigned Number Announcements Migration tool to roll back the configuration from the Lync Server 2013 deployment to the Lync Server 2010 deployment.</span></span>

  - <span data-ttu-id="7a9eb-779">**Movimiento de datos entre implementaciones de Lync:** Contoso está en proceso de reemplazar todos los servidores de un grupo por los nuevos servidores.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-779">**Moving data between Lync deployments:** Contoso is in the process of replacing all the servers of one pool with newer servers.</span></span> <span data-ttu-id="7a9eb-780">Su estrategia es implementar un nuevo grupo de servidores de Lync Server 2013, mover todos los datos del antiguo al nuevo y, a continuación, deshacer el grupo anterior.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-780">Their strategy is to deploy a new Lync Server 2013 pool, move all the data from the old to the new pool, and then deprecate the old pool.</span></span> <span data-ttu-id="7a9eb-781">Una vez que se haya implementado el nuevo grupo de servidores, se usará la herramienta de migración de anuncios de números sin asignar para mover la configuración del grupo anterior al nuevo.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-781">Once the new pool is deployed, the Unassigned Number Announcements Migration tool is used to move the configuration from the old pool to the new one.</span></span>

<div>

## <a name="requirements"></a><span data-ttu-id="7a9eb-782">Requirements</span><span class="sxs-lookup"><span data-stu-id="7a9eb-782">Requirements</span></span>

<span data-ttu-id="7a9eb-783">Los siguientes son los requisitos principales necesarios para ejecutar correctamente la herramienta:</span><span class="sxs-lookup"><span data-stu-id="7a9eb-783">The following are the main requirements needed to successfully run the tool:</span></span>

1.  <span data-ttu-id="7a9eb-784">El script debe ejecutarse desde un equipo que tenga instalado el shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-784">The script must be run from a computer that has Lync Server 2013 Management Shell installed.</span></span>

2.  <span data-ttu-id="7a9eb-785">La aplicación de anuncio tiene que implementarse correctamente en los servidores o grupos de Lync de origen y de destino.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-785">The announcement application has to be successfully deployed in the source and destination Lync Servers or Pools.</span></span>

<div>

## <a name="move-csannouncementconfiguration-script"></a><span data-ttu-id="7a9eb-786">Script de Move-CsAnnouncementConfiguration</span><span class="sxs-lookup"><span data-stu-id="7a9eb-786">Move-CsAnnouncementConfiguration script</span></span>

<span data-ttu-id="7a9eb-787">La secuencia de comandos Move-CsAnnouncementConfiguration requiere los dos parámetros que se describen en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-787">The Move-CsAnnouncementConfiguration script requires the two parameters that are described in the table below.</span></span>

<span data-ttu-id="7a9eb-788">![Parámetros Move-CsAnnouncementConfiguration.](images/JJ945604.7ab66ad3-d0db-4d77-8b93-ebccf0cb0663(OCS.15).jpg "Parámetros de Move-CsAnnouncementConfiguration.")</span><span class="sxs-lookup"><span data-stu-id="7a9eb-788">![Move-CsAnnouncementConfiguration parameters.](images/JJ945604.7ab66ad3-d0db-4d77-8b93-ebccf0cb0663(OCS.15).jpg "Move-CsAnnouncementConfiguration parameters.")</span></span>

</div>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="7a9eb-789">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="7a9eb-789">Examples</span></span>

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2010-pool-to-a-lync-server-2013-pool"></a><span data-ttu-id="7a9eb-790">Mover la configuración de anuncios de números sin asignar de un grupo de servidores de Lync Server 2010 a un grupo de servidores de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7a9eb-790">Moving the Unassigned Number Announcements Configuration from a Lync Server 2010 Pool to a Lync Server 2013 Pool</span></span>

<span data-ttu-id="7a9eb-791">En este ejemplo se mueven los anuncios de números sin asignar del grupo de origen (Lync Server 2010) al grupo de servidores de destino (Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="7a9eb-791">This example moves the unassigned number announcements from the source pool (Lync Server 2010) to the destination pool (Lync Server 2013).</span></span>

    Move-CsAnnouncementConfiguration.ps1 -Source LS2010Pool.contoso.com -Destination LS2013Pool.contoso.com

</div>

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-lync-server-2010-pool"></a><span data-ttu-id="7a9eb-792">Mover la configuración de anuncios de números sin asignar de un grupo de servidores de Lync Server 2013 a un grupo de servidores de Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="7a9eb-792">Moving the Unassigned Number Announcements Configuration from a Lync Server 2013 Pool to a Lync Server 2010 Pool</span></span>

<span data-ttu-id="7a9eb-793">En este ejemplo se mueven los anuncios de números sin asignar del grupo de origen (Lync Server 2013) al grupo de servidores de destino (Lync Server 2010).</span><span class="sxs-lookup"><span data-stu-id="7a9eb-793">This example moves the unassigned number announcements from the source pool (Lync Server 2013) to the destination pool (Lync Server 2010).</span></span>

    Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination LS2010Pool.contoso.com

</div>

</div>

</div>

<div>

## <a name="web-conf-data"></a><span data-ttu-id="7a9eb-794">Datos de conf de Web</span><span class="sxs-lookup"><span data-stu-id="7a9eb-794">Web Conf Data</span></span>

<span data-ttu-id="7a9eb-795">La herramienta de datos Web conf permite que un administrador del software de comunicaciones Lync Server 2013 tenga más control sobre los datos asociados con las conferencias web del organizador.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-795">The Web Conf Data Tool allows an administrator of Lync Server 2013 communications software to have more control over the data associated with an organizer’s Web conferences.</span></span> <span data-ttu-id="7a9eb-796">Los escenarios incluyen la capacidad de eliminar los datos específicos de una reunión de un usuario en función de los criterios de marca de tiempo.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-796">Scenarios include the ability to delete a specific user’s meeting data based on a time stamp criteria.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="7a9eb-797">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a9eb-797">Description</span></span>

<span data-ttu-id="7a9eb-798">Esta herramienta permite al administrador realizar las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="7a9eb-798">This tool allows the administrator to perform the following operations:</span></span>

1.  <span data-ttu-id="7a9eb-799">Buscar todos los datos de conferencias web asociados con un único usuario.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-799">Find all Web conferencing data associated with a single user.</span></span>

2.  <span data-ttu-id="7a9eb-800">Eliminar todos los datos de conferencias web asociados con un único usuario.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-800">Delete all Web conferencing data associated with a single user.</span></span>

3.  <span data-ttu-id="7a9eb-801">Elimine todos los datos de conferencias web asociados con un único usuario que sea anterior a una fecha concreta.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-801">Delete all Web conferencing data associated with a single user that is older than a certain date.</span></span>

4.  <span data-ttu-id="7a9eb-802">Se mueven todos los datos de conferencias web asociados con un usuario único cuando este usuario se mueve de un grupo de servidores a otro.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-802">Move all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7a9eb-803">Las herramientas del kit de recursos para Lync Server 2010 admiten el traslado de todos los datos de conferencias web asociados con un usuario único cuando se mueve a ese usuario de un grupo de servidores a otro.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-803">The Resource Kit Tools for Lync Server 2010 supported moving all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span> <span data-ttu-id="7a9eb-804">Esa funcionalidad ahora está en desuso de esta herramienta en favor del parámetro <STRONG>MoveConferenceData</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="7a9eb-804">That functionality is now deprecated from this tool in favor of the <STRONG>MoveConferenceData</STRONG> parameter.</span></span> <span data-ttu-id="7a9eb-805">Para obtener más información sobre este parámetro, consulte el cmdlet <A href="https://technet.microsoft.com/library/gg398528(v=ocs.15)">Move-CsUser</A> .</span><span class="sxs-lookup"><span data-stu-id="7a9eb-805">For details about this parameter, see the <A href="https://technet.microsoft.com/library/gg398528(v=ocs.15)">Move-CsUser</A> cmdlet.</span></span>



</div>

<span data-ttu-id="7a9eb-806">La herramienta elimina los datos de la reunión solo para las reuniones inactivas.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-806">The tool deletes meeting data only for meetings that are inactive.</span></span> <span data-ttu-id="7a9eb-807">Las reuniones activas (o reuniones en sesiones) no se pueden eliminar.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-807">Active meetings (or meetings in sessions) cannot be deleted.</span></span>

<span data-ttu-id="7a9eb-808">Esta herramienta debe ejecutarse desde un equipo que esté en el mismo grupo de servidores que el usuario de destino.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-808">This tool must be run from a computer that is in the same pool as the target user.</span></span> <span data-ttu-id="7a9eb-809">El usuario cuyos datos de contenido de reunión se administran mediante esta herramienta debe estar hospedado en el mismo grupo de usuarios.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-809">The user whose meeting content data is being managed by this tool must be homed in the same user pool.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="7a9eb-810">Output</span><span class="sxs-lookup"><span data-stu-id="7a9eb-810">Output</span></span>

<span data-ttu-id="7a9eb-811">Esta herramienta genera los resultados de cada una de las operaciones:</span><span class="sxs-lookup"><span data-stu-id="7a9eb-811">This tool outputs the results of each of the operations:</span></span>

  - <span data-ttu-id="7a9eb-812">Si se realiza una consulta, la herramienta genera la lista de todas las carpetas de datos de reuniones inactivas que el usuario tiene como organizador.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-812">If a query is performed, the tool outputs the list of all inactive meeting data folders that have that user as an organizer.</span></span>

  - <span data-ttu-id="7a9eb-813">Si se realiza una eliminación, la herramienta genera la lista de todas las carpetas de datos de la reunión cuyos datos se eliminarán.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-813">If a delete is performed, the tool outputs the list of all meeting data folders whose data will be deleted.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="7a9eb-814">Requirements</span><span class="sxs-lookup"><span data-stu-id="7a9eb-814">Requirements</span></span>

<span data-ttu-id="7a9eb-815">La herramienta debe ejecutarse en el mismo grupo de servidores donde está hospedada actualmente el organizador.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-815">The tool needs to be run in the same pool where the organizer is currently homed.</span></span>

<span data-ttu-id="7a9eb-816">La herramienta debe ejecutarse con privilegios de administrador con acceso al almacén de archivos de contenido.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-816">The tool must be run using administrator privileges with access to the Content File Store.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="7a9eb-817">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="7a9eb-817">Examples</span></span>

<span data-ttu-id="7a9eb-818">En la tabla siguiente se describen los parámetros, algunos de los cuales se usan en los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-818">The following table describes the parameters, some of which are used in the examples.</span></span>

<span data-ttu-id="7a9eb-819">![Parámetros de la herramienta de datos Web conf.](images/JJ945604.a733c1c6-5dfc-4874-a74f-bfdee81c1401(OCS.15).jpg "Parámetros de la herramienta de datos Web conf.")</span><span class="sxs-lookup"><span data-stu-id="7a9eb-819">![Web Conf Data Tool parameters.](images/JJ945604.a733c1c6-5dfc-4874-a74f-bfdee81c1401(OCS.15).jpg "Web Conf Data Tool parameters.")</span></span>

    WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""

<span data-ttu-id="7a9eb-820">En el ejemplo anterior se muestra el funcionamiento de un comando de consulta.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-820">The preceding example shows how a query command would work.</span></span> <span data-ttu-id="7a9eb-821">El resultado de un comando de este tipo sería una lista de todas las carpetas de contenido de reuniones que se verían afectadas por esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-821">The output of such a command would be a list of all meeting content folders that would be affected by this tool.</span></span>

    WebConfDataTool.exe /User:user0@contoso.com /Action:delete

<span data-ttu-id="7a9eb-822">El ejemplo anterior es un ejemplo de un comando DELETE.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-822">The preceding is an example of a delete command.</span></span> <span data-ttu-id="7a9eb-823">El comando eliminar quitará todas las carpetas de reuniones inactivas de este usuario.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-823">The delete command will remove all inactive meeting folders from this user.</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="7a9eb-824">Resumen</span><span class="sxs-lookup"><span data-stu-id="7a9eb-824">Summary</span></span>

<span data-ttu-id="7a9eb-825">Esta herramienta puede ser un recurso útil para los administradores que necesitan un control más preciso sobre los datos de las reuniones de conferencia.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-825">This tool can be a valuable resource to administrators who need more precise control over conference meeting data.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>
