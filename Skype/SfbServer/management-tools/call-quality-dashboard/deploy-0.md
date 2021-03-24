---
title: Implementar panel de calidad de llamadas para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 287f64f5-0f8a-455a-8979-7b34bf0217bb
description: 'Resumen: obtenga información sobre el proceso de implementación del Panel de calidad de llamadas. Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: 1f59209575284035fcdca52e4f18220aa05337af
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114116"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server"></a><span data-ttu-id="6ea30-104">Implementar panel de calidad de llamadas para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="6ea30-104">Deploy Call Quality Dashboard for Skype for Business Server</span></span>
 
<span data-ttu-id="6ea30-105">**Resumen:** Obtenga información sobre el proceso de implementación del Panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="6ea30-105">**Summary:** Learn about the deployment process for Call Quality Dashboard.</span></span> <span data-ttu-id="6ea30-106">Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="6ea30-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
## <a name="deployment-overview"></a><span data-ttu-id="6ea30-107">Vista general de implementación</span><span class="sxs-lookup"><span data-stu-id="6ea30-107">Deployment Overview</span></span>

<span data-ttu-id="6ea30-108">El Panel de calidad de llamadas (CQD) consta de tres componentes principales:</span><span class="sxs-lookup"><span data-stu-id="6ea30-108">Call Quality Dashboard (CQD) consists of three major components:</span></span>
  
- <span data-ttu-id="6ea30-109">**Base de datos de** archivo , donde se replican y almacenan los datos de calidad de la experiencia (QoE).</span><span class="sxs-lookup"><span data-stu-id="6ea30-109">**Archive Database**, where the Quality of Experience (QoE) data is replicated and stored.</span></span>
    
- <span data-ttu-id="6ea30-110">**Cubo**, donde se agregan datos de la base de datos de archivos qoE para un acceso optimizado y rápido.</span><span class="sxs-lookup"><span data-stu-id="6ea30-110">**Cube**, where data from QoE Archive database is aggregated for optimized and fast access.</span></span>
    
- <span data-ttu-id="6ea30-111">**Portal**, donde los usuarios pueden consultar y visualizar fácilmente los datos de QoE.</span><span class="sxs-lookup"><span data-stu-id="6ea30-111">**Portal**, where users can easily query and visualize QoE data.</span></span>
    
![Componentes de CQD](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
<span data-ttu-id="6ea30-113">El proceso de instalación de QoE Archive implica la creación de la base de datos de archivos qoE, la implementación de un procedimiento almacenado de SQL Server que moverá los datos de la base de datos de métricas qoE de origen a la base de datos de archivo qoE y la configuración del trabajo del agente de SQL Server para ejecutar el procedimiento almacenado en un intervalo regular.</span><span class="sxs-lookup"><span data-stu-id="6ea30-113">The setup process for QoE Archive involves creating the QoE Archive database, deploying a SQL Server stored procedure that will move the data from the source QoE Metrics database into QoE Archive database, and setting up the SQL Server Agent job to execute the stored procedure at a regular interval.</span></span> 
  
<span data-ttu-id="6ea30-114">La implementación de cubos obtiene información del usuario sobre dónde se encuentra el archivo QoE, implementa el cubo y configura un trabajo de agente de SQL Server normal que actualizará el cubo en un intervalo regular.</span><span class="sxs-lookup"><span data-stu-id="6ea30-114">Cube deployment gets information from the user on where the QoE Archive is located, deploys the cube, and sets up a regular SQL Server agent job that will refresh the cube at a regular interval.</span></span>
  
<span data-ttu-id="6ea30-115">La instalación del portal crea una base de datos de repositorio que almacena la asignación de usuarios de CQD a los informes o consultas de cada usuario.</span><span class="sxs-lookup"><span data-stu-id="6ea30-115">Portal install creates a Repository database that stores the mapping of CQD users to each user's reports/queries.</span></span> <span data-ttu-id="6ea30-116">A continuación, configura una aplicación web de IIS que es el panel donde los usuarios pueden ver un conjunto predefinido de informes, así como personalizar y crear sus propias consultas para visualizar los datos del cubo.</span><span class="sxs-lookup"><span data-stu-id="6ea30-116">It then sets up an IIS web application which is the dashboard where users can see a pre-defined set of reports as well as customize and create their own queries to visualize data from the cube.</span></span> <span data-ttu-id="6ea30-117">La instalación del portal crea dos aplicaciones web adicionales que exponen las API para que los usuarios accedan mediante programación al repositorio y al cubo.</span><span class="sxs-lookup"><span data-stu-id="6ea30-117">The portal install creates two additional web applications that exposes APIs for users to programmatically access the repository and the cube.</span></span> <span data-ttu-id="6ea30-118">(El panel también usa internamente estas API).</span><span class="sxs-lookup"><span data-stu-id="6ea30-118">(These APIs are used internally by the dashboard as well.)</span></span>
  

|<span data-ttu-id="6ea30-119">**Fase**</span><span class="sxs-lookup"><span data-stu-id="6ea30-119">**Phase**</span></span>|<span data-ttu-id="6ea30-120">**Pasos**</span><span class="sxs-lookup"><span data-stu-id="6ea30-120">**Steps**</span></span>|<span data-ttu-id="6ea30-121">**Roles y pertenencia a grupos**</span><span class="sxs-lookup"><span data-stu-id="6ea30-121">**Roles and group membership**</span></span>|<span data-ttu-id="6ea30-122">**Documentación**</span><span class="sxs-lookup"><span data-stu-id="6ea30-122">**Documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6ea30-123">Instalar hardware y software previos.</span><span class="sxs-lookup"><span data-stu-id="6ea30-123">Install prerequisite hardware and software.</span></span>  <br/> |<span data-ttu-id="6ea30-124">Decida la configuración de CQD y elija una SQL Server desde la que realizar la instalación.</span><span class="sxs-lookup"><span data-stu-id="6ea30-124">Decide on the CQD configuration, and choose a SQL Server from which to perform the install.</span></span>  <br/> |<span data-ttu-id="6ea30-125">Usuario de dominio que es miembro del grupo de administradores locales.</span><span class="sxs-lookup"><span data-stu-id="6ea30-125">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="6ea30-126">Sección "Requisitos de instalación previa" en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="6ea30-126">"Pre-install Requirements" section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="6ea30-127">Instale CQD.</span><span class="sxs-lookup"><span data-stu-id="6ea30-127">Install CQD.</span></span>  <br/> |<span data-ttu-id="6ea30-128">Ejecute msi siguiendo el documento de implementación.</span><span class="sxs-lookup"><span data-stu-id="6ea30-128">Run the MSI following the deployment document.</span></span>  <br/> |<span data-ttu-id="6ea30-129">Para realizar la instalación, la cuenta de instalación debe ser un usuario de dominio que sea miembro del grupo de administradores locales y tenga acceso de lectura a la base de datos de métricas de QoE en el servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="6ea30-129">To perform the setup, the installing account must be a domain user who is a member of the local administrators group and have read access to QoE Metrics database on the Monitoring Server.</span></span>  <br/> |<span data-ttu-id="6ea30-130">Secciones "Cuentas y pasos de implementación" en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="6ea30-130">"Accounts and Deployment Steps" sections in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="6ea30-131">Conceder acceso de usuario.</span><span class="sxs-lookup"><span data-stu-id="6ea30-131">Grant user access.</span></span>  <br/> |<span data-ttu-id="6ea30-132">Para administrar la autorización de usuario en el Portal, se recomienda usar la autorización de dirección URL, que se introdujo en IIS 7.0.</span><span class="sxs-lookup"><span data-stu-id="6ea30-132">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="6ea30-133">Para obtener más información, vea [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span><span class="sxs-lookup"><span data-stu-id="6ea30-133">For more information, see [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>  <br/> |<span data-ttu-id="6ea30-134">Usuario de dominio que es miembro del grupo de administradores locales.</span><span class="sxs-lookup"><span data-stu-id="6ea30-134">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="6ea30-135">Administración del acceso de usuario para la sección Portal en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="6ea30-135">Managing User Access for the Portal section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="6ea30-136">Opcional: proporcione información de asignación de subred.</span><span class="sxs-lookup"><span data-stu-id="6ea30-136">Optional: Provide subnet mapping information.</span></span>  <br/> |<span data-ttu-id="6ea30-137">Rellene las tablas de asignación de red y de creación en la base de datos de archivos qoE.</span><span class="sxs-lookup"><span data-stu-id="6ea30-137">Populate network and building mapping tables in QoE Archive database.</span></span>  <br/> |<span data-ttu-id="6ea30-138">Una cuenta con acceso de escritura a la base de datos de archivos QoE.</span><span class="sxs-lookup"><span data-stu-id="6ea30-138">An account with write access to the QoE Archive database.</span></span>  <br/> |<span data-ttu-id="6ea30-139">Sección "Suministro de información de subred" en la documentación del usuario.</span><span class="sxs-lookup"><span data-stu-id="6ea30-139">"Supplying Subnet Information" section in the user documentation.</span></span>  <br/> |
   


<span data-ttu-id="6ea30-140">La implementación del Panel de calidad de llamadas implica configurar la infraestructura e instalar el software.</span><span class="sxs-lookup"><span data-stu-id="6ea30-140">Deployment of Call Quality Dashboard involves setting up the infrastructure and installing the software.</span></span> <span data-ttu-id="6ea30-141">El siguiente procedimiento describe el proceso.</span><span class="sxs-lookup"><span data-stu-id="6ea30-141">The following procedure outlines the process.</span></span>
  
## <a name="deployment-steps"></a><span data-ttu-id="6ea30-142">Pasos de implementación</span><span class="sxs-lookup"><span data-stu-id="6ea30-142">Deployment Steps</span></span>

1. <span data-ttu-id="6ea30-143">Copie el CallQualityDashboard.msi en el equipo donde se va a instalar el componente de base de datos de archivo de CQD (este es el equipo que SQL Server instalado).</span><span class="sxs-lookup"><span data-stu-id="6ea30-143">Copy the CallQualityDashboard.msi to the machine where the archive database component of CQD is to be installed (this is the machine that has SQL Server installed).</span></span> 
    
2. <span data-ttu-id="6ea30-144">Ejecute msi (Windows pedirá que se ejecute con privilegios de administrador, así que).</span><span class="sxs-lookup"><span data-stu-id="6ea30-144">Execute the MSI (Windows will prompt to run with administrator privilege, do so).</span></span> 
    
3. <span data-ttu-id="6ea30-145">Aceptar el CLUF.</span><span class="sxs-lookup"><span data-stu-id="6ea30-145">Accept the EULA.</span></span>
    
4. <span data-ttu-id="6ea30-146">Seleccione la carpeta de destino donde se ubicarán los archivos relacionados con los componentes del Panel de calidad de llamadas o acepte la ubicación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="6ea30-146">Select the destination folder where files related to Call Quality Dashboard components will be located or accept the default location.</span></span>
    
5. <span data-ttu-id="6ea30-147">Seleccione todas las características.</span><span class="sxs-lookup"><span data-stu-id="6ea30-147">Select all features.</span></span>
    
6. <span data-ttu-id="6ea30-148">En la página Configuración de archivo qoE, proporcione la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="6ea30-148">At the QoE Archive Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="6ea30-149">**Métricas de QoE SQL Server:** SQL Server de instancia para el lugar donde se encuentra la base de datos de métricas qoE (este será el origen de datos).</span><span class="sxs-lookup"><span data-stu-id="6ea30-149">**QoE Metrics SQL Server:** SQL Server instance name for where the QoE Metrics DB is located (this will be the data source).</span></span>
    
   - <span data-ttu-id="6ea30-150">**Nombre de archivo SQL Server QoE:** Este campo es de solo lectura y se fija en el nombre de dominio completo del equipo local.</span><span class="sxs-lookup"><span data-stu-id="6ea30-150">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="6ea30-151">La base de datos de archivo solo se puede instalar en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="6ea30-151">Archive DB can be installed only on the local machine.</span></span>
    
   - <span data-ttu-id="6ea30-152">**Instancia de archivo SQL Server QoE:** Un nombre SQL Server instancia local para donde se va a crear la base de datos de archivo.</span><span class="sxs-lookup"><span data-stu-id="6ea30-152">**QoE Archive SQL Server Instance:** A local SQL Server instance name for where the Archive DB is to be created.</span></span> <span data-ttu-id="6ea30-153">Para usar una instancia SQL Server predeterminada, deje este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="6ea30-153">To use a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="6ea30-154">Para usar una instancia SQL Server nombre, especifique el nombre de instancia (por ejemplo, el nombre después de " \" ).</span><span class="sxs-lookup"><span data-stu-id="6ea30-154">To use a named SQL Server instance, specify the instance name (e.g. the name after the "\").</span></span>
    
   - <span data-ttu-id="6ea30-155">**Base de datos de archivos QoE:** De forma predeterminada, esta opción se establece en "Crear nueva base de datos".</span><span class="sxs-lookup"><span data-stu-id="6ea30-155">**QoE Archive Database:** By default, this option is set to "Create new database".</span></span> <span data-ttu-id="6ea30-156">Dado que no se admite la actualización de la base de datos de archivo, la única circunstancia en la que se puede usar la opción "Usar base de datos existente" es si la base de datos de archivo existente tiene el mismo esquema que la compilación que se va a instalar.</span><span class="sxs-lookup"><span data-stu-id="6ea30-156">Since Archive DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Archive database has the same schema as the build to be installed.</span></span>
    
   - <span data-ttu-id="6ea30-157">**Directorio de archivos de base de datos:** Ruta de acceso a donde deben colocarse los archivos de base de datos (.mdf y .ldf) de la base de datos de archivo.</span><span class="sxs-lookup"><span data-stu-id="6ea30-157">**Database File Directory:** Path to where the database files (.mdf and .ldf) for the Archive DB should be placed.</span></span> <span data-ttu-id="6ea30-158">Debe estar en una unidad (HDD2 en la configuración de hardware recomendada) independiente del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="6ea30-158">This should be on a drive (HDD2 in the recommended hardware configuration) separate from the OS.</span></span> <span data-ttu-id="6ea30-159">Tenga en cuenta que, dado que los nombres de archivo están fijos en la instalación, para evitar posibles conflictos, se recomienda usar un directorio en blanco sin archivos.</span><span class="sxs-lookup"><span data-stu-id="6ea30-159">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="6ea30-160">**Usar varias particiones:** El valor predeterminado se establece en "Partición múltiple", que requiere business intelligence edition o enterprise edition de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6ea30-160">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="6ea30-161">En Standard edition, selecciona la opción "Partición única".</span><span class="sxs-lookup"><span data-stu-id="6ea30-161">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="6ea30-162">Tenga en cuenta que el rendimiento del procesamiento del cubo puede afectarse si se usa una sola partición.</span><span class="sxs-lookup"><span data-stu-id="6ea30-162">Note that cube processing performance may be impacted if Single Partition is used.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="6ea30-163">La selección de la opción Usar varias particiones no se puede cambiar una vez completada la instalación.</span><span class="sxs-lookup"><span data-stu-id="6ea30-163">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="6ea30-164">Para cambiarla, la característica Cubo debe desinstalarse primero y volver a instalarse con la opción "Cambiar" en el Panel de control.</span><span class="sxs-lookup"><span data-stu-id="6ea30-164">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span> 
  
   - <span data-ttu-id="6ea30-165">**Directorio de archivos de partición:** Ruta de acceso a donde deben colocarse las particiones de la base de datos de archivos qoE.</span><span class="sxs-lookup"><span data-stu-id="6ea30-165">**Partition File Directory:** Path to where the partitions for the QoE Archive database should be placed.</span></span> <span data-ttu-id="6ea30-166">Debe estar en una unidad (HDD3 en la configuración de hardware recomendada) independiente de la unidad del sistema operativo y de SQL de archivos de registro de base de datos.</span><span class="sxs-lookup"><span data-stu-id="6ea30-166">This should be on a drive (HDD3 in the recommended hardware configuration) separate from the OS drive and SQL database log files drive.</span></span> <span data-ttu-id="6ea30-167">Tenga en cuenta que, dado que los nombres de archivo están fijos en la instalación, para evitar posibles conflictos, se recomienda usar un directorio en blanco sin archivos.</span><span class="sxs-lookup"><span data-stu-id="6ea30-167">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="6ea30-168">**SQL de trabajo del agente: nombre de usuario &amp; Contraseña:** nombre de cuenta de servicio de dominio y contraseña (enmascarada) que se usarán para ejecutar el paso "Datos de archivo qoE" del trabajo del agente de SQL Server (que ejecutará el procedimiento almacenado para capturar datos de la base de datos de métricas de QoE en la base de datos de archivo, por lo que esta cuenta debe tener acceso de lectura a la base de datos de métricas de QoE, tal como se indica en la sección Cuentas.</span><span class="sxs-lookup"><span data-stu-id="6ea30-168">**SQL Agent Job User - User Name &amp; Password:** Domain service account name and password (masked) that will be used to run the "QoE Archive Data" step of the SQL Server Agent job (which will run the stored procedure to fetch data from QoE Metrics DB into Archive DB, so this account must have read access to QoE Metrics DB, as indicated under Accounts section.</span></span> <span data-ttu-id="6ea30-169">Esta cuenta también debe tener un inicio de sesión en la instancia de QoE Archive SQL Server Instance).</span><span class="sxs-lookup"><span data-stu-id="6ea30-169">This account also needs to have a login in the QoE Archive SQL Server Instance).</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="6ea30-170">La cuenta en la que se ejecuta la instancia de SQL Server, como NT SERVICE\MSSQLSERVER, debe tener acceso o permiso a los directorios anteriores para que la instalación se ejecute correctamente.</span><span class="sxs-lookup"><span data-stu-id="6ea30-170">The account that the SQL Server instance is running under, such as NT SERVICE\MSSQLSERVER, must have access/permission to the directories given above for the installation to succeed.</span></span> <span data-ttu-id="6ea30-171">Para obtener más información, vea [Configure File System Permissions for Database Engine Access](/previous-versions/sql/sql-server-2012/jj219062(v=sql.110))</span><span class="sxs-lookup"><span data-stu-id="6ea30-171">For details, see [Configure File System Permissions for Database Engine Access](/previous-versions/sql/sql-server-2012/jj219062(v=sql.110))</span></span>
  
7. <span data-ttu-id="6ea30-172">Al hacer clic en siguiente, el instalador realizará comprobaciones de requisitos previos e informe si se encuentra algún problema.</span><span class="sxs-lookup"><span data-stu-id="6ea30-172">Upon clicking next, the installer will perform pre-requisite checks and report if any issues are encountered.</span></span> <span data-ttu-id="6ea30-173">Cuando pasen todas las comprobaciones previas, el instalador irá a la página Configuración del cubo.</span><span class="sxs-lookup"><span data-stu-id="6ea30-173">When all pre-requisite checks pass, the installer will go to the Cube Configuration page.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="6ea30-174">Si el instalador muestra un mensaje de advertencia de que el servicio de agente de SQL Server para la instancia de QoE Archive SQL Server actualmente no se está ejecutando, la instalación puede continuar, pero después de la instalación, asegúrese de que se está ejecutando el servicio de agente de SQL y establezca el tipo de inicio en Automático para que se ejecute el trabajo programado.</span><span class="sxs-lookup"><span data-stu-id="6ea30-174">If the installer shows a warning message that the SQL Server Agent service for the QoE Archive SQL Server instance is currently not running, installation can proceed, but post installation please make sure that SQL Agent service is running and set the Startup type to Automatic so that the scheduled Job runs.</span></span> 
  
8. <span data-ttu-id="6ea30-175">En la página Configuración del cubo, proporcione la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="6ea30-175">At Cube Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="6ea30-176">**Nombre de archivo SQL Server QoE:** Este campo es de solo lectura y se fija en el nombre de dominio completo del equipo local.</span><span class="sxs-lookup"><span data-stu-id="6ea30-176">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="6ea30-177">El cubo solo se puede instalar desde la máquina que tiene la base de datos de archivos qoE (nota.</span><span class="sxs-lookup"><span data-stu-id="6ea30-177">Cube can be installed only from the machine that has QoE Archive database (Note.</span></span> <span data-ttu-id="6ea30-178">El cubo en sí puede instalarse en un equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="6ea30-178">Cube itself may be installed on a remote machine.</span></span> <span data-ttu-id="6ea30-179">Vea a continuación)</span><span class="sxs-lookup"><span data-stu-id="6ea30-179">See below)</span></span>
    
   - <span data-ttu-id="6ea30-180">**Instancia de archivo SQL Server QoE:** SQL Server de instancia para el lugar donde se encuentra la base de datos de archivo qoE.</span><span class="sxs-lookup"><span data-stu-id="6ea30-180">**QoE Archive SQL Server Instance:** SQL Server instance name for where the QoE Archive DB is located.</span></span> <span data-ttu-id="6ea30-181">Para especificar una instancia SQL Server predeterminada, deje este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="6ea30-181">To specify a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="6ea30-182">Para especificar una instancia SQL Server nombre, escriba el nombre de instancia (por ejemplo, el nombre después de " \" ).</span><span class="sxs-lookup"><span data-stu-id="6ea30-182">To specify a named SQL Server instance, enter the instance name (e.g. the name after the "\").</span></span> <span data-ttu-id="6ea30-183">Si se seleccionó el componente de archivo qoE para la instalación, este campo se rellenará previamente con el valor proporcionado en la página Configuración de archivo de QoE.</span><span class="sxs-lookup"><span data-stu-id="6ea30-183">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
   - <span data-ttu-id="6ea30-184">**Cube Analysis Server:** SQL Server de instancia de Analysis Service para donde se va a crear el cubo.</span><span class="sxs-lookup"><span data-stu-id="6ea30-184">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is to be created.</span></span> <span data-ttu-id="6ea30-185">Puede ser un equipo diferente, pero el usuario de instalación debe ser miembro de los administradores de servidor de la instancia de SQL Server Analysis Service de destino.</span><span class="sxs-lookup"><span data-stu-id="6ea30-185">This can be a different machine but the installing user has to be a member of Server administrators of the target SQL Server Analysis Service instance.</span></span>
    
     > [!NOTE]
     >  <span data-ttu-id="6ea30-186">Para obtener más información acerca de la configuración de permisos de administrador de Analysis Services Server, vea [Grant Server Administrator Permissions (Analysis Services)](/analysis-services/instances/grant-server-admin-rights-to-an-analysis-services-instance?viewFallbackFrom=sql-server-ver15)</span><span class="sxs-lookup"><span data-stu-id="6ea30-186">For more information about configuring Analysis Services Server Administrator Permissions, see [Grant Server Administrator Permissions (Analysis Services)](/analysis-services/instances/grant-server-admin-rights-to-an-analysis-services-instance?viewFallbackFrom=sql-server-ver15)</span></span>
  
   - <span data-ttu-id="6ea30-187">**Usar varias particiones:** El valor predeterminado se establece en "Partición múltiple", que requiere business intelligence edition o enterprise edition de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6ea30-187">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="6ea30-188">En Standard edition, selecciona la opción "Partición única".</span><span class="sxs-lookup"><span data-stu-id="6ea30-188">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="6ea30-189">Tenga en cuenta que el rendimiento del procesamiento del cubo puede afectar si se usa una sola partición .</span><span class="sxs-lookup"><span data-stu-id="6ea30-189">Note that cube processing performance may be impacted if Single Partition is used .</span></span>
    
     > [!NOTE]
     >  <span data-ttu-id="6ea30-190">La selección de la opción Usar varias particiones no se puede cambiar una vez completada la instalación.</span><span class="sxs-lookup"><span data-stu-id="6ea30-190">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="6ea30-191">Para cambiarla, la característica Cubo debe desinstalarse primero y volver a instalarse con la opción "Cambiar" en el Panel de control.</span><span class="sxs-lookup"><span data-stu-id="6ea30-191">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span>
  
   - <span data-ttu-id="6ea30-192">**Usuario del cubo: nombre de usuario &amp; Contraseña: nombre** de cuenta de servicio de dominio y contraseña (enmascarada) que desencadenarán el procesamiento del cubo.</span><span class="sxs-lookup"><span data-stu-id="6ea30-192">**Cube User - User Name &amp; Password:** Domain service account name and password (masked) that will trigger the cube processing.</span></span> <span data-ttu-id="6ea30-193">Si se seleccionó el componente archivo qoE para la instalación, este campo se rellenará previamente con el valor proporcionado en la página Configuración de archivo para el usuario de trabajo del agente de SQL, pero se recomienda especificar una cuenta de servicio de dominio diferente para que el programa de instalación pueda concederle el privilegio menos necesario.</span><span class="sxs-lookup"><span data-stu-id="6ea30-193">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the Archive Configuration page for the SQL Agent Job User, but we recommend specifying a different domain service account so that Setup can grant the least required privilege to it.</span></span>
    
9. <span data-ttu-id="6ea30-194">Al hacer clic en siguiente, se realizará otra ronda de validación y se notifica cualquier problema.</span><span class="sxs-lookup"><span data-stu-id="6ea30-194">When clicking next, another round of validation will be performed and any issue will be reported.</span></span> <span data-ttu-id="6ea30-195">Una vez completada correctamente la validación, el instalador irá a la página Configuración del portal.</span><span class="sxs-lookup"><span data-stu-id="6ea30-195">Upon successful completion of the validation, the installer will go to the Portal Configuration page.</span></span> 
    
10. <span data-ttu-id="6ea30-196">En la página Configuración del portal, proporcione la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="6ea30-196">At Portal Configuration page, provide the following information:</span></span>
    
    - <span data-ttu-id="6ea30-197">**QoE Archive SQL Server:** SQL Server de instancia para dónde se encuentra la base de datos de archivos qoE.</span><span class="sxs-lookup"><span data-stu-id="6ea30-197">**QoE Archive SQL Server:** SQL Server instance name for where the QoE Archive database is located.</span></span> <span data-ttu-id="6ea30-198">Tenga en cuenta que, a diferencia de la página Configuración de archivo de QoE y la página Configuración del cubo, el nombre de la máquina no es fijo y debe proporcionarse.</span><span class="sxs-lookup"><span data-stu-id="6ea30-198">Note that unlike the QoE Archive Configuration page and the Cube Configuration page, the machine name is not fixed and must be provided.</span></span> <span data-ttu-id="6ea30-199">Si se seleccionó el componente de archivo qoE para la instalación, este campo se rellenará previamente con el valor proporcionado en la página Configuración de archivo de QoE.</span><span class="sxs-lookup"><span data-stu-id="6ea30-199">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
    - <span data-ttu-id="6ea30-200">**Cube Analysis Server:** SQL Server de instancia de Analysis Service para el lugar donde se encuentra el cubo.</span><span class="sxs-lookup"><span data-stu-id="6ea30-200">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is located.</span></span> <span data-ttu-id="6ea30-201">Si se seleccionó el componente Cube para la instalación, este campo se rellenará previamente con el valor proporcionado en la página Configuración del cubo.</span><span class="sxs-lookup"><span data-stu-id="6ea30-201">If Cube component was selected for the install, this field will be pre-populated with the value provided on the Cube Configuration page.</span></span>
    
    - <span data-ttu-id="6ea30-202">**Repositorio SQL Server:** SQL Server de instancia donde se va a crear la base de datos de repositorio.</span><span class="sxs-lookup"><span data-stu-id="6ea30-202">**Repository SQL Server:** SQL Server instance name where the Repository database is to be created.</span></span> <span data-ttu-id="6ea30-203">Si el nombre de instancia de SQL Server donde se encuentra la base de datos de archivos qoE se ha proporcionado anteriormente en la instalación (en otros componentes), este campo se rellenará previamente con el nombre de instancia de archivo de QoE SQL Server instancia.</span><span class="sxs-lookup"><span data-stu-id="6ea30-203">If the SQL Server instance name for where the QoE Archive database is located has been provided earlier in the setup (in other components), this field will be pre-populated with the QoE Archive DB SQL Server instance name.</span></span> <span data-ttu-id="6ea30-204">Puede ser cualquier SQL Server instancia.</span><span class="sxs-lookup"><span data-stu-id="6ea30-204">This can be any SQL Server instance.</span></span>
    
    - <span data-ttu-id="6ea30-205">**Base de datos de repositorio:** De forma predeterminada, la opción se establece en "Crear nueva base de datos".</span><span class="sxs-lookup"><span data-stu-id="6ea30-205">**Repository Database:** By default the option is set to "Create new database".</span></span> <span data-ttu-id="6ea30-206">Dado que no se admite la actualización de base de datos de repositorio, la única circunstancia en la que se puede usar la opción "Usar base de datos existente" es si la base de datos de repositorio existente tiene el mismo esquema que la compilación que se va a instalar.</span><span class="sxs-lookup"><span data-stu-id="6ea30-206">Since Repository DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Repository DB has the same schema as the build to be installed.</span></span>
    
    - <span data-ttu-id="6ea30-207">**Usuario del grupo de aplicaciones de IIS: nombre de usuario &amp; Contraseña: la** cuenta en la que debe ejecutarse el grupo de aplicaciones de IIS.</span><span class="sxs-lookup"><span data-stu-id="6ea30-207">**IIS App Pool User - User Name &amp; Password:** The account that the IIS application pool should execute under.</span></span> <span data-ttu-id="6ea30-208">Los campos Nombre de usuario y Contraseña se atenuarán si se seleccionan cuentas del sistema integradas.</span><span class="sxs-lookup"><span data-stu-id="6ea30-208">The User Name and Password fields will be grayed out if built-in system accounts are selected.</span></span> <span data-ttu-id="6ea30-209">Estos campos solo se habilitarán si "Other" está seleccionado en el cuadro desplegable para que el usuario pueda escribir la información de la cuenta de servicio de dominio.</span><span class="sxs-lookup"><span data-stu-id="6ea30-209">These fields will only be enabled if "Other" is selected from the drop down box so the user can enter the domain service account information.</span></span>
    
11. <span data-ttu-id="6ea30-210">Al hacer clic en siguiente, se realizará la última ronda de validación para asegurarse de que las instancias SQL Server son accesibles con las credenciales proporcionadas y que IIS está disponible en el equipo.</span><span class="sxs-lookup"><span data-stu-id="6ea30-210">When clicking next, the final round of validation will be done to ensure that the SQL Server instances are accessible using the credentials provided and that IIS is available on the machine.</span></span> <span data-ttu-id="6ea30-211">Una vez completada correctamente la validación, el instalador continuará con la instalación.</span><span class="sxs-lookup"><span data-stu-id="6ea30-211">Upon successful completion of the validation, the installer will proceed with the setup.</span></span> 
    
<span data-ttu-id="6ea30-212">Cuando el instalador haya terminado, lo más probable es que el trabajo SQL Server agente esté en curso, realizando la carga inicial de los datos de QoE y el procesamiento del cubo.</span><span class="sxs-lookup"><span data-stu-id="6ea30-212">When the installer is done, most likely the SQL Server Agent job will be in progress, doing the initial load of the QoE data and the cube processing.</span></span> <span data-ttu-id="6ea30-213">Según la cantidad de datos de QoE, el portal no tendrá datos disponibles para su visualización todavía.</span><span class="sxs-lookup"><span data-stu-id="6ea30-213">Depending on the amount of data in QoE, the portal will not have data available for viewing yet.</span></span> <span data-ttu-id="6ea30-214">Para comprobar el estado de la carga de datos y el procesamiento del cubo, vaya a  `http://<machinename>/CQD/#/Health` .</span><span class="sxs-lookup"><span data-stu-id="6ea30-214">To check on the status of the data load and cube processing, go to  `http://<machinename>/CQD/#/Health`.</span></span> 
> [!NOTE]
> <span data-ttu-id="6ea30-215">Tenga en cuenta que la dirección URL para comprobar el estado del procesamiento del cubo de descarga distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="6ea30-215">Note that the URL for checking the status of the download cube processing is case sensitive.</span></span> <span data-ttu-id="6ea30-216">Si escribe "estado", la dirección URL no funcionará.</span><span class="sxs-lookup"><span data-stu-id="6ea30-216">If you enter 'health' the URL will not work.</span></span> <span data-ttu-id="6ea30-217">Debe escribir "Estado" al final de la dirección URL con una H mayúscula.</span><span class="sxs-lookup"><span data-stu-id="6ea30-217">You must enter 'Health' at the end of the URL with a capital H.</span></span> 
  
<span data-ttu-id="6ea30-218">Los mensajes de registro detallados se mostrarán si el modo de depuración está habilitado.</span><span class="sxs-lookup"><span data-stu-id="6ea30-218">Detailed log messages will be shown if debug mode is enabled.</span></span> <span data-ttu-id="6ea30-219">Para habilitar el modo de depuración, vaya a **%SYSTEMDRIVE%\Program Files\Skype For Business 2015 CQD\QoEDataService\web.config** y actualice la siguiente línea para que el valor se establezca en **True**:</span><span class="sxs-lookup"><span data-stu-id="6ea30-219">To enable debug mode, go to **%SYSTEMDRIVE%\Program Files\Skype For Business 2015 CQD\QoEDataService\web.config**, and update the following line so the value is set to **True**:</span></span>

```xml
<add key="QoEDataLib.DebugMode" value="True" /> 
```

<span data-ttu-id="6ea30-220">Se puede acceder a la página del portal principal a través  `http://<machinename>/CQD` de .</span><span class="sxs-lookup"><span data-stu-id="6ea30-220">The main portal page is accessible via  `http://<machinename>/CQD`.</span></span> 
## <a name="managing-user-access-for-the-portal"></a><span data-ttu-id="6ea30-221">Administración del acceso de usuarios para el portal</span><span class="sxs-lookup"><span data-stu-id="6ea30-221">Managing User Access for the Portal</span></span>

<span data-ttu-id="6ea30-222">Para administrar la autorización de usuario en el Portal, se recomienda usar la autorización de dirección URL, que se introdujo en IIS 7.0.</span><span class="sxs-lookup"><span data-stu-id="6ea30-222">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="6ea30-223">Para obtener más información sobre la seguridad de IIS, vea [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span><span class="sxs-lookup"><span data-stu-id="6ea30-223">For more information on IIS security, see [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>
  
<span data-ttu-id="6ea30-224">Cualquier sitio web o aplicación web hereda la autorización de dirección URL predeterminada configurada para todo IIS, que suele ser "Permitir todos los usuarios".</span><span class="sxs-lookup"><span data-stu-id="6ea30-224">Any web site or web application inherit the default URL Authorization configured for the entire IIS, which is typically "Allow All Users".</span></span> <span data-ttu-id="6ea30-225">Si el acceso al Portal debe ser más restrictivo, los administradores solo pueden conceder acceso al grupo específico de usuarios editando las "Reglas de autorización".</span><span class="sxs-lookup"><span data-stu-id="6ea30-225">If access to the Portal needs to be more restrictive, then administrators can grant access to only the specific group of users by editing the "Authorization Rules".</span></span>
  
![Implementar calidad de llamadas: reglas de autorización en IIS](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> <span data-ttu-id="6ea30-227">El icono Reglas de autorización no debe confundirse con la "Autorización de.NET" en la sección ASP.NET, que es un mecanismo de autorización diferente.</span><span class="sxs-lookup"><span data-stu-id="6ea30-227">The Authorization Rules icon is not to be confused with the ".NET Authorization" under the ASP.NET section, which is a different authorization mechanism.</span></span> 
  
<span data-ttu-id="6ea30-228">Los administradores deben quitar primero la regla heredada "Permitir todos los usuarios".</span><span class="sxs-lookup"><span data-stu-id="6ea30-228">Administrators should first remove the inherited "Allow All Users" rule.</span></span> <span data-ttu-id="6ea30-229">Esto impide que los usuarios no autorizados accedan al Portal.</span><span class="sxs-lookup"><span data-stu-id="6ea30-229">This prevents any non-authorized users from accessing the Portal.</span></span>
  
![Implementar CQD](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
<span data-ttu-id="6ea30-231">A continuación, los administradores deben agregar nuevas reglas de permiso y conceder a usuarios específicos el permiso para acceder al Portal.</span><span class="sxs-lookup"><span data-stu-id="6ea30-231">Next, administrators should add new Allow Rules and give specific users the permission to access the Portal.</span></span> <span data-ttu-id="6ea30-232">Se recomienda crear un grupo local denominado "CQDPortalUsers" para administrar los usuarios.</span><span class="sxs-lookup"><span data-stu-id="6ea30-232">It is recommended that a local Group called "CQDPortalUsers" be created to manage the users.</span></span>
  
![Implementar el panel de calidad de llamadas](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
<span data-ttu-id="6ea30-234">Los detalles de configuración se almacenan en el web.config ubicado en el directorio físico del portal.</span><span class="sxs-lookup"><span data-stu-id="6ea30-234">The configuration details are stored in the web.config located at the Portal's physical directory.</span></span>
  
```xml
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

<span data-ttu-id="6ea30-235">El siguiente paso es configurar el panel del CQD.</span><span class="sxs-lookup"><span data-stu-id="6ea30-235">The next step is to configure the dashboard of the CQD.</span></span> <span data-ttu-id="6ea30-236">Una vez que IIS autentique a los usuarios, tendrán que tener permisos de archivo en el directorio CQD para tener acceso al contenido del portal web.</span><span class="sxs-lookup"><span data-stu-id="6ea30-236">After users are authenticated by IIS, they will have to have file permissions on the CQD directory in order to access the web portal content.</span></span> <span data-ttu-id="6ea30-237">Es posible cambiar las ACL a través de la pestaña de seguridad de las propiedades del directorio CQD para agregar usuarios o grupos individuales; sin embargo, el enfoque recomendado es dejar los permisos de archivo intactos.</span><span class="sxs-lookup"><span data-stu-id="6ea30-237">It is possible to change the ACLs through the security tab of the CQD directory properties to add individual users or groups; however the recommended approach is to leave the file permissions untouched.</span></span> <span data-ttu-id="6ea30-238">En su lugar, cambie la configuración de IIS para usar el proceso de trabajo de IIS para obtener acceso al directorio CQD independientemente del usuario autenticado.</span><span class="sxs-lookup"><span data-stu-id="6ea30-238">Instead, change the IIS setting to use the IIS worker process to access the CQD directory no matter which user is authenticated.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="6ea30-239">Es importante cambiar solo esta configuración para la aplicación CQD y no para las dos aplicaciones de API: QoEDataService y QoERepositoryService.</span><span class="sxs-lookup"><span data-stu-id="6ea30-239">It is important to only change this setting for the CQD application, and not for the two API applications: QoEDataService and QoERepositoryService.</span></span> 
  
## <a name="configuring-file-access-for-the-cqd-dashboard"></a><span data-ttu-id="6ea30-240">Configuración del acceso a archivos para el CQD (panel)</span><span class="sxs-lookup"><span data-stu-id="6ea30-240">Configuring File Access for the CQD (Dashboard)</span></span>

1. <span data-ttu-id="6ea30-241">Abra el Editor de configuración para CQD.</span><span class="sxs-lookup"><span data-stu-id="6ea30-241">Open the Configuration Editor for CQD.</span></span>
    
     ![Implementar el panel de calidad de llamadas](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. <span data-ttu-id="6ea30-243">En Sección, elija **system.webServer/serverRuntime**.</span><span class="sxs-lookup"><span data-stu-id="6ea30-243">Under Section, choose **system.webServer/serverRuntime**.</span></span>
    
     ![Implementar el panel de calidad de llamadas](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. <span data-ttu-id="6ea30-245">Cambie authenticatedUserOverride a **UseWorkerProcessUser**.</span><span class="sxs-lookup"><span data-stu-id="6ea30-245">Change authenticatedUserOverride to **UseWorkerProcessUser**.</span></span>
    
     ![Implementar panel de calidad de llamadas: Editor de configuración](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. <span data-ttu-id="6ea30-247">Haga **clic en** Aplicar en el lado derecho de la página.</span><span class="sxs-lookup"><span data-stu-id="6ea30-247">Click **Apply** on the right-hand side of the page.</span></span>
    
## <a name="known-issues"></a><span data-ttu-id="6ea30-248">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="6ea30-248">Known Issues</span></span>

### <a name="the-cqd-shows-no-data-after-deployment"></a><span data-ttu-id="6ea30-249">El CQD no muestra datos después de la implementación</span><span class="sxs-lookup"><span data-stu-id="6ea30-249">The CQD shows no data after deployment</span></span>

<span data-ttu-id="6ea30-250">Es posible que reciba el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="6ea30-250">You may receive the following error:</span></span>

<span data-ttu-id="6ea30-251">*No se pudo realizar la consulta mientras se ejecutaba en el cubo. Use el Editor de consultas para modificar la consulta y solucionar cualquier problema. Asegúrese también de que el cubo es accesible.*</span><span class="sxs-lookup"><span data-stu-id="6ea30-251">*We couldn’t perform the query while running it on the Cube. Use the Query Editor to modify the query and fix any issues. Also make sure that the Cube is accessible.*</span></span>

<span data-ttu-id="6ea30-252">Esto significa que el cubo debe procesarse en SQL Server Analysis Services antes de usarse en CQD.</span><span class="sxs-lookup"><span data-stu-id="6ea30-252">This means that the cube must be processed in SQL Server Analysis Services prior to being used in CQD.</span></span> <span data-ttu-id="6ea30-253">Para resolver esto, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="6ea30-253">You can resolve this by following these steps:</span></span>

1. <span data-ttu-id="6ea30-254">Abra SQL Management Studio y seleccione **Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="6ea30-254">Open SQL Management Studio and select **Analysis Services**.</span></span>

2. <span data-ttu-id="6ea30-255">Expanda el **objeto QoECube,** seleccione **QoE Metric**, haga clic con el botón secundario y, a continuación, elija **Examinar**.</span><span class="sxs-lookup"><span data-stu-id="6ea30-255">Expand the **QoECube** object, select **QoE Metric**, right-click, and then choose **Browse**.</span></span> 

    <span data-ttu-id="6ea30-256">Si devuelve el explorador vacío, el cubo aún no se ha realizado.</span><span class="sxs-lookup"><span data-stu-id="6ea30-256">If this returns empty browser, the cube hasn’t been proceed yet.</span></span>

3. <span data-ttu-id="6ea30-257">Haga clic con el botón **secundario en Angain métrica qoE** y elija **Procesar**.</span><span class="sxs-lookup"><span data-stu-id="6ea30-257">Right-click **QoE Metric** angain and choose **Process**.</span></span>

4. <span data-ttu-id="6ea30-258">Cuando se complete el procesamiento, haga clic con el botón secundario en el objeto de nuevo y elija **Examinar** para confirmar que la página del explorador muestra ahora datos.</span><span class="sxs-lookup"><span data-stu-id="6ea30-258">When processing is complete, right-click the object again, and choose **Browse** to confirm that the browser page now shows data.</span></span> 


### <a name="users-have-trouble-logging-in-because-installer-fails-to-create-the-correct-settings-in-iis"></a><span data-ttu-id="6ea30-259">Los usuarios tienen problemas para iniciar sesión porque el instalador no puede crear la configuración correcta en IIS</span><span class="sxs-lookup"><span data-stu-id="6ea30-259">Users have trouble logging in because installer fails to create the correct settings in IIS</span></span>

<span data-ttu-id="6ea30-260">En raras ocasiones, el instalador no puede crear la configuración correcta en IIS.</span><span class="sxs-lookup"><span data-stu-id="6ea30-260">In rare cases, the installer fails to create the correct settings in IIS.</span></span> <span data-ttu-id="6ea30-261">El cambio manual es necesario para permitir que los usuarios inicien sesión en el CQD.</span><span class="sxs-lookup"><span data-stu-id="6ea30-261">Manual change is required to allow users to log into the CQD.</span></span> <span data-ttu-id="6ea30-262">Si los usuarios tienen problemas para iniciar sesión, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="6ea30-262">If users are having trouble logging in, please follow these steps:</span></span>
  
1. <span data-ttu-id="6ea30-263">Abra el Administrador de IIS y vaya a Sitio web predeterminado.</span><span class="sxs-lookup"><span data-stu-id="6ea30-263">Open up IIS Manager, and navigate to Default Web Site.</span></span>
    
     ![Implementar el panel de calidad de llamadas](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. <span data-ttu-id="6ea30-265">Haga clic en "Autenticación".</span><span class="sxs-lookup"><span data-stu-id="6ea30-265">Click on "Authentication".</span></span> <span data-ttu-id="6ea30-266">Si "Autenticación anónima", "suplantación de ASP.NET", "Autenticación de formulario" y "Autenticación de Windows" no coinciden con la configuración que se muestra a continuación, cámbienlas manualmente para que coincidan con la configuración siguiente.</span><span class="sxs-lookup"><span data-stu-id="6ea30-266">If the "Anonymous Authentication", "ASP.NET Impersonation", "Form Authentication", and "Windows Authentication" do not match the settings shown below, manually change them to match the settings below.</span></span> <span data-ttu-id="6ea30-267">Todos los demás mecanismos de autenticación deben deshabilitarse.</span><span class="sxs-lookup"><span data-stu-id="6ea30-267">All other authentication mechanisms should be disabled.</span></span>
    
     ![Implementar el panel de calidad de llamadas](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. <span data-ttu-id="6ea30-269">Para "Autenticación de Windows", haz clic en Configuración avanzada en el lado derecho.</span><span class="sxs-lookup"><span data-stu-id="6ea30-269">For "Windows Authentication", click on Advanced Settings on the right-hand side.</span></span>
    
     ![Implementar el panel de calidad de llamadas](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. <span data-ttu-id="6ea30-271">Establezca "Protección extendida" en Aceptar y active la casilla "Habilitar autenticación en modo kernel".</span><span class="sxs-lookup"><span data-stu-id="6ea30-271">Set "Extended Protection" to Accept and check the "Enable Kernel-mode authentication" box.</span></span>
    
     ![Implementar el panel de calidad de llamadas](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. <span data-ttu-id="6ea30-273">Repita los pasos anteriores para cada una de las entradas "CQD", "QoEDataService" y "QoERepositoryService" debajo de "Sitio web predeterminado".</span><span class="sxs-lookup"><span data-stu-id="6ea30-273">Repeat the above steps for each of the "CQD", "QoEDataService", and "QoERepositoryService" entries below "Default Web Site".</span></span>
    
<span data-ttu-id="6ea30-274">Para los enlaces de puerto HTTP y HTTPS, el instalador creará enlaces de puerto en los números de puerto predeterminados (puerto 80 para HTTP y puerto 443 para HTTPS).</span><span class="sxs-lookup"><span data-stu-id="6ea30-274">For HTTP and HTTPS port bindings the installer will create port bindings on the default port numbers (port 80 for HTTP and port 443 for HTTPS).</span></span> <span data-ttu-id="6ea30-275">Si hay otro sitio web en la máquina que usa estos enlaces, habrá un conflicto y no se puede predecir el comportamiento de IIS.</span><span class="sxs-lookup"><span data-stu-id="6ea30-275">If there is another website on the machine that uses these bindings, there will be a conflict and the IIS behavior cannot be predicted.</span></span> <span data-ttu-id="6ea30-276">La mejor manera de evitar este problema es asegurarse de que ningún otro sitio web esté asignado a los puertos 80 y 443 antes de instalar CQD.</span><span class="sxs-lookup"><span data-stu-id="6ea30-276">The best way to avoid this problem is to make sure that no other websites are mapped to ports 80 and 443 before installing CQD.</span></span> 
  
<span data-ttu-id="6ea30-277">Para habilitar SSL/TLS en IIS y forzar a los usuarios a conectarse a través de HTTPS seguro en lugar de HTTP:</span><span class="sxs-lookup"><span data-stu-id="6ea30-277">To enable SSL/TLS in IIS and force users to connect via secure HTTPS instead of HTTP:</span></span>
  
1. <span data-ttu-id="6ea30-278">Configure Secure Sockets Layer in IIS, consulte [Configuring Secure Sockets Layer in IIS 7](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc771438(v=ws.10)).</span><span class="sxs-lookup"><span data-stu-id="6ea30-278">Configure Secure Sockets Layer in IIS, see [Configuring Secure Sockets Layer in IIS 7](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc771438(v=ws.10)).</span></span> <span data-ttu-id="6ea30-279">Una vez terminado, reemplace  `http` por `https` .</span><span class="sxs-lookup"><span data-stu-id="6ea30-279">Once done, replace  `http` with `https`.</span></span>
    
2. <span data-ttu-id="6ea30-280">Para obtener instrucciones sobre cómo habilitar TLS en las conexiones SQL Server, vea [How to enable SSL encryption for an instance of SQL Server by using Microsoft Management Console](https://support.microsoft.com/kb/316898/).</span><span class="sxs-lookup"><span data-stu-id="6ea30-280">For instructions on enabling TLS in the SQL Server connections, see [How to enable SSL encryption for an instance of SQL Server by using Microsoft Management Console](https://support.microsoft.com/kb/316898/).</span></span>
    
## <a name="cube-sync-fails"></a><span data-ttu-id="6ea30-281">Error en la sincronización de cubos</span><span class="sxs-lookup"><span data-stu-id="6ea30-281">Cube Sync Fails</span></span>

<span data-ttu-id="6ea30-282">QoEMetrics puede contener algunos registros no válidos en función de los relojes del usuario final.</span><span class="sxs-lookup"><span data-stu-id="6ea30-282">QoEMetrics may contain some invalid records based on end user clocks.</span></span> <span data-ttu-id="6ea30-283">Si el sesgo de tiempo es mayor que 60 años, se producirá un error en la importación del cubo.</span><span class="sxs-lookup"><span data-stu-id="6ea30-283">If the time skew is greater than 60 yrs, the cube import will fail.</span></span>
  
 <span data-ttu-id="6ea30-284">Comprueba Min y Max StartTime/EndTime con las selecciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="6ea30-284">Check the Min and Max StartTime/EndTime using the selections below.</span></span> <span data-ttu-id="6ea30-285">Busque y elimine registros en el futuro lejano y muy lejano, se pueden ignorar y romperán los procesos de sincronización.</span><span class="sxs-lookup"><span data-stu-id="6ea30-285">Look for and delete records in the far past and very distant future, they can be disregarded and they will break up the sync processes.</span></span>
  
- <span data-ttu-id="6ea30-286">Seleccionar MIN(StartTime) FROM CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="6ea30-286">Select MIN(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="6ea30-287">Seleccionar MAX(StartTime) FROM CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="6ea30-287">Select MAX(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="6ea30-288">Seleccionar MIN(EndTime) FROM CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="6ea30-288">Select MIN(EndTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="6ea30-289">Seleccionar MAX(EndTime) FROM CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="6ea30-289">Select MAX(EndTime) FROM CqdPartitionedStreamView</span></span>
    
## <a name="post-install-tasks"></a><span data-ttu-id="6ea30-290">Tareas posteriores a la instalación</span><span class="sxs-lookup"><span data-stu-id="6ea30-290">Post-install tasks</span></span>

### <a name="importing-buildings-and-networks"></a><span data-ttu-id="6ea30-291">Importar edificios y redes</span><span class="sxs-lookup"><span data-stu-id="6ea30-291">Importing Buildings and Networks</span></span>

<span data-ttu-id="6ea30-292">Después de instalar CQD, realice las siguientes tareas de configuración:</span><span class="sxs-lookup"><span data-stu-id="6ea30-292">After Installing CQD, perform the following configuration tasks:</span></span>
  
1. <span data-ttu-id="6ea30-293">Definir tipos de creación (recomendado)</span><span class="sxs-lookup"><span data-stu-id="6ea30-293">Define Building types (recommended)</span></span>
    
2. <span data-ttu-id="6ea30-294">Definir tipos de propiedad de edificio (recomendado)</span><span class="sxs-lookup"><span data-stu-id="6ea30-294">Define Building Ownership types (recommended)</span></span>
    
3. <span data-ttu-id="6ea30-295">Definir tipos de red (muy recomendado)</span><span class="sxs-lookup"><span data-stu-id="6ea30-295">Define Network types (highly recommended)</span></span>
    
4. <span data-ttu-id="6ea30-296">Importar edificios (recomendado)</span><span class="sxs-lookup"><span data-stu-id="6ea30-296">Import Buildings (recommended)</span></span>
    
5. <span data-ttu-id="6ea30-297">Importar subredes (recomendado)</span><span class="sxs-lookup"><span data-stu-id="6ea30-297">Import Subnets (recommended)</span></span>
    
### <a name="define-building-types"></a><span data-ttu-id="6ea30-298">Definir tipos de creación</span><span class="sxs-lookup"><span data-stu-id="6ea30-298">Define Building Types</span></span>

<span data-ttu-id="6ea30-299">Los tipos de creación se usan para describir las diferentes definiciones o tipos de edificios de la organización.</span><span class="sxs-lookup"><span data-stu-id="6ea30-299">Building types are used to describe the different buildings definitions or types within your organization.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6ea30-300">Este paso es opcional, pero recomendado.</span><span class="sxs-lookup"><span data-stu-id="6ea30-300">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="6ea30-301">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="6ea30-301">Examples</span></span>
  
- <span data-ttu-id="6ea30-302">Headquarters</span><span class="sxs-lookup"><span data-stu-id="6ea30-302">Headquarters</span></span>
    
- <span data-ttu-id="6ea30-303">Oficina remota</span><span class="sxs-lookup"><span data-stu-id="6ea30-303">Remote Office</span></span>
    
- <span data-ttu-id="6ea30-304">Ubicación de la empresa conjunta</span><span class="sxs-lookup"><span data-stu-id="6ea30-304">Joint-venture location</span></span>
    
  <span data-ttu-id="6ea30-305">**Sintaxis SQL ejemplo**</span><span class="sxs-lookup"><span data-stu-id="6ea30-305">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO
[dbo].[CqdBuildingType]
([BuildingTypeId],
[BuildingTypeDesc])
VALUES
(1, 
'Headquarters')   
```

<span data-ttu-id="6ea30-306">Los parámetros BuildingTypeId y BuildingTypeDesc son necesarios.</span><span class="sxs-lookup"><span data-stu-id="6ea30-306">The BuildingTypeId and BuildingTypeDesc parameters are required.</span></span>
  
### <a name="define-building-ownership-types"></a><span data-ttu-id="6ea30-307">Definir tipos de propiedad de creación</span><span class="sxs-lookup"><span data-stu-id="6ea30-307">Define Building Ownership Types</span></span>

<span data-ttu-id="6ea30-308">Los tipos de propiedad se usan para distinguir los activos de propiedad frente a los arrendados.</span><span class="sxs-lookup"><span data-stu-id="6ea30-308">Ownership types are used to distinguish owned vs leased assets.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6ea30-309">Este paso es opcional, pero recomendado.</span><span class="sxs-lookup"><span data-stu-id="6ea30-309">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="6ea30-310">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="6ea30-310">Examples</span></span>
  
- <span data-ttu-id="6ea30-311">Contoso Leased non-RE &amp; F</span><span class="sxs-lookup"><span data-stu-id="6ea30-311">Contoso Leased non-RE&amp;F</span></span>
    
- <span data-ttu-id="6ea30-312">Contoso Leased RE &amp; F</span><span class="sxs-lookup"><span data-stu-id="6ea30-312">Contoso Leased RE&amp;F</span></span>
    
- <span data-ttu-id="6ea30-313">Contoso Owned</span><span class="sxs-lookup"><span data-stu-id="6ea30-313">Contoso Owned</span></span>
    
- <span data-ttu-id="6ea30-314">Subsidiaria arrendada</span><span class="sxs-lookup"><span data-stu-id="6ea30-314">Subsidiary Leased</span></span>
    
  <span data-ttu-id="6ea30-315">**Sintaxis SQL ejemplo**</span><span class="sxs-lookup"><span data-stu-id="6ea30-315">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO
[dbo].[CqdBuildingOwnershipType]
([OwnershipTypeId],
[OwnershipTypeDesc]
)

VALUES
(1,
'Contoso Owned'
)
```

<span data-ttu-id="6ea30-316">Los parámetros OwnershipTypeId y OwnershipTypeDesc son necesarios.</span><span class="sxs-lookup"><span data-stu-id="6ea30-316">The OwnershipTypeId and OwnershipTypeDesc parameters are required.</span></span> 
  
### <a name="define-network-names"></a><span data-ttu-id="6ea30-317">Definir nombres de red</span><span class="sxs-lookup"><span data-stu-id="6ea30-317">Define Network Names</span></span>

<span data-ttu-id="6ea30-318">Los tipos de red se usan para describir diferentes tipos de redes dentro de la organización.</span><span class="sxs-lookup"><span data-stu-id="6ea30-318">Network Types are used to describe different types of networks within the organization.</span></span> <span data-ttu-id="6ea30-319">Esto le permite filtrar (o filtrar) tipos de red específicos.</span><span class="sxs-lookup"><span data-stu-id="6ea30-319">This gives you the ability to filter on (or filter out) specific Network Types.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6ea30-320">Se recomienda definir nombres de red, pero es opcional.</span><span class="sxs-lookup"><span data-stu-id="6ea30-320">It is highly recommended to define Network Names, but it is optional.</span></span> <span data-ttu-id="6ea30-321">Si decide no definir nombres de red, asegúrese de que cada entrada CqdNetwork tiene un BuildingId de 0.</span><span class="sxs-lookup"><span data-stu-id="6ea30-321">If you decide to not define network names, ensure the each CqdNetwork entry has a BuildingId of 0.</span></span> 
  
<span data-ttu-id="6ea30-322">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="6ea30-322">Examples</span></span>
  
- <span data-ttu-id="6ea30-323">VPN</span><span class="sxs-lookup"><span data-stu-id="6ea30-323">VPN</span></span>
    
- <span data-ttu-id="6ea30-324">LAB</span><span class="sxs-lookup"><span data-stu-id="6ea30-324">LAB</span></span>
    
  <span data-ttu-id="6ea30-325">**Sintaxis SQL ejemplo**</span><span class="sxs-lookup"><span data-stu-id="6ea30-325">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

<span data-ttu-id="6ea30-326">Los parámetros NetworkNameID y NetworkName son necesarios, el parámetro NetworkType es opcional pero recomendado.</span><span class="sxs-lookup"><span data-stu-id="6ea30-326">The NetworkNameID and NetworkName parameters are required, the NetworkType parameter is optional but recommended.</span></span>
  
### <a name="import-buildings"></a><span data-ttu-id="6ea30-327">Importar edificios</span><span class="sxs-lookup"><span data-stu-id="6ea30-327">Import Buildings</span></span>

<span data-ttu-id="6ea30-328">Importar edificios le ofrece la capacidad de obtener información específica de la creación (llamadas deficientes por edificio en WiFi/Wired, etc.).</span><span class="sxs-lookup"><span data-stu-id="6ea30-328">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6ea30-329">Este paso es opcional, pero recomendado.</span><span class="sxs-lookup"><span data-stu-id="6ea30-329">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="6ea30-330">Antes de importar un nuevo edificio, ya debería tener una buildingKey predefinida identificada.</span><span class="sxs-lookup"><span data-stu-id="6ea30-330">Before you Import a new building you should already have a predefined BuildingKey identified.</span></span> <span data-ttu-id="6ea30-331">Para ello, emita el comando "SELECT MAX(BuildingKey) FROM CqdBuilding" SQL para identificar el valor actual y agregar 1 al resultado.</span><span class="sxs-lookup"><span data-stu-id="6ea30-331">To do that, issue the "SELECT MAX(BuildingKey) FROM CqdBuilding" SQL command to identify the current value and add 1 to the result.</span></span>
  
 <span data-ttu-id="6ea30-332">**Sintaxis SQL ejemplo**</span><span class="sxs-lookup"><span data-stu-id="6ea30-332">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdBuilding] 
( [BuildingKey]
,[BuildingName]
,[BuildingShortName]
,[OwnershipTypeId],
[BuildingTypeId]
)
VALUES
(2, 'Ann Arbor', 'AA', 0, 0)
```

<span data-ttu-id="6ea30-333">Los parámetros BuildingKey, BuildingName, BuildingShortName, OwnershipTypeId, BuildingTypeId son necesarios y los demás parámetros son opcionales.</span><span class="sxs-lookup"><span data-stu-id="6ea30-333">The BuildingKey, BuildingName, BuildingShortName, OwnershipTypeId, BuildingTypeId parameters are required, the other parameters are optional.</span></span>
  
### <a name="import-subnets"></a><span data-ttu-id="6ea30-334">Importar subredes</span><span class="sxs-lookup"><span data-stu-id="6ea30-334">Import Subnets</span></span>

<span data-ttu-id="6ea30-335">Importar edificios le ofrece la capacidad de obtener información específica de la creación (llamadas deficientes por edificio en WiFi/Wired, etc.).</span><span class="sxs-lookup"><span data-stu-id="6ea30-335">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6ea30-336">Este paso es opcional, pero recomendado.</span><span class="sxs-lookup"><span data-stu-id="6ea30-336">This step is optional, but recommended.</span></span>
  
<span data-ttu-id="6ea30-337">Importe subredes y asignelas a los edificios importados en el último paso.</span><span class="sxs-lookup"><span data-stu-id="6ea30-337">Import Subnets and map them to the Buildings imported in the last step.</span></span> <span data-ttu-id="6ea30-338">Si decidió no rellenar NetworkName, asegúrese de que cada entrada de esta tabla usa un NetworkNameID de 0.</span><span class="sxs-lookup"><span data-stu-id="6ea30-338">If you decided not to populate NetworkName, ensure each entry in this table uses a NetworkNameID of 0.</span></span> <span data-ttu-id="6ea30-339">Para obtener más información SQL sintaxis y parámetros para el Panel de calidad de llamadas, vea [Use Call Quality Dashboard for Skype for Business Server](./use.md).</span><span class="sxs-lookup"><span data-stu-id="6ea30-339">For more information on SQL syntax and parameters for the Call Quality Dashboard, see [Use Call Quality Dashboard for Skype for Business Server](./use.md).</span></span>
  
 <span data-ttu-id="6ea30-340">**Sintaxis SQL ejemplo**</span><span class="sxs-lookup"><span data-stu-id="6ea30-340">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdNetwork] 
([Network]
,[NetworkRange]
,[NetworkNameID]
,[BuildingKey]
,[UpdatedDate]
)

VALUES
 ('172.16.254.0',32,0,1,'2015-11-11')
```

<span data-ttu-id="6ea30-341">Los parámetros Network y UpdatedDate son necesarios, los otros parámetros son opcionales.</span><span class="sxs-lookup"><span data-stu-id="6ea30-341">The Network, and UpdatedDate parameters are required, the other parameters are optional.</span></span>
  
### <a name="optional-bssid"></a><span data-ttu-id="6ea30-342">Opcional: BSSID</span><span class="sxs-lookup"><span data-stu-id="6ea30-342">Optional: BSSID</span></span>

<span data-ttu-id="6ea30-343">Rellenar información BSSID le proporciona una correlación de secuencias WiFi adicional por controlador o radio.</span><span class="sxs-lookup"><span data-stu-id="6ea30-343">Populating BSSID information gives you additional WiFi stream correlation by controller or radio.</span></span> <span data-ttu-id="6ea30-344">Esto se suma al filtrado mediante la creación o subred.</span><span class="sxs-lookup"><span data-stu-id="6ea30-344">This is in addition to filtering by building or subnet.</span></span> 
  
 <span data-ttu-id="6ea30-345">**Sintaxis SQL ejemplo**</span><span class="sxs-lookup"><span data-stu-id="6ea30-345">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdBssid]
([Ap],
[Bss],
[Building],
[ess],
[phy]
)
VALUES
('AP1','00-00-00-00-00-00','Aruba AP 1','Controller1','bgn')
```

<span data-ttu-id="6ea30-346">**Detalles de CqdBssidTable**</span><span class="sxs-lookup"><span data-stu-id="6ea30-346">**CqdBssidTable Details**</span></span>

|<span data-ttu-id="6ea30-347">**Como se muestra en CQD**</span><span class="sxs-lookup"><span data-stu-id="6ea30-347">**As shown in CQD**</span></span>|<span data-ttu-id="6ea30-348">**Tabla CQDBssid**</span><span class="sxs-lookup"><span data-stu-id="6ea30-348">**CQDBssid Table**</span></span>|<span data-ttu-id="6ea30-349">**Entradas de ejemplo**</span><span class="sxs-lookup"><span data-stu-id="6ea30-349">**Example inputs**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6ea30-350">Ap NName</span><span class="sxs-lookup"><span data-stu-id="6ea30-350">Ap NName</span></span>  <br/> |<span data-ttu-id="6ea30-351">AP</span><span class="sxs-lookup"><span data-stu-id="6ea30-351">AP</span></span>  <br/> |<span data-ttu-id="6ea30-352">AP1</span><span class="sxs-lookup"><span data-stu-id="6ea30-352">AP1</span></span>  <br/> |
|<span data-ttu-id="6ea30-353">BBssid</span><span class="sxs-lookup"><span data-stu-id="6ea30-353">BBssid</span></span>  <br/> |<span data-ttu-id="6ea30-354">BSS</span><span class="sxs-lookup"><span data-stu-id="6ea30-354">BSS</span></span>  <br/> |<span data-ttu-id="6ea30-355">00-00-00-00-00-00 (debe usar el fformat delimitado)</span><span class="sxs-lookup"><span data-stu-id="6ea30-355">00-00-00-00-00-00 (you must use the delimited fformat)</span></span>  <br/> |
|<span data-ttu-id="6ea30-356">Controlador</span><span class="sxs-lookup"><span data-stu-id="6ea30-356">Controller</span></span>  <br/> |<span data-ttu-id="6ea30-357">Creación</span><span class="sxs-lookup"><span data-stu-id="6ea30-357">Building</span></span>  <br/> |<span data-ttu-id="6ea30-358">Aruba AP 7</span><span class="sxs-lookup"><span data-stu-id="6ea30-358">Aruba AP 7</span></span>  <br/> |
|<span data-ttu-id="6ea30-359">Dispositivo</span><span class="sxs-lookup"><span data-stu-id="6ea30-359">Device</span></span>  <br/> |<span data-ttu-id="6ea30-360">ess</span><span class="sxs-lookup"><span data-stu-id="6ea30-360">ess</span></span>  <br/> |<span data-ttu-id="6ea30-361">Controlador1</span><span class="sxs-lookup"><span data-stu-id="6ea30-361">Controller1</span></span>  <br/> |
|<span data-ttu-id="6ea30-362">Radio</span><span class="sxs-lookup"><span data-stu-id="6ea30-362">Radio</span></span>  <br/> |<span data-ttu-id="6ea30-363">phy</span><span class="sxs-lookup"><span data-stu-id="6ea30-363">phy</span></span>  <br/> |<span data-ttu-id="6ea30-364">bgn</span><span class="sxs-lookup"><span data-stu-id="6ea30-364">bgn</span></span>  <br/> |
   
### <a name="processing-the-imported-data"></a><span data-ttu-id="6ea30-365">Procesamiento de los datos importados</span><span class="sxs-lookup"><span data-stu-id="6ea30-365">Processing the imported data</span></span>

<span data-ttu-id="6ea30-366">De forma predeterminada, después de importar datos de creación o red, solo se aplicará a los registros generados después de ese momento.</span><span class="sxs-lookup"><span data-stu-id="6ea30-366">By default, after you import building/network data it will only apply to records generated after that point in time.</span></span> 
  
<span data-ttu-id="6ea30-367">Para etiquetar todos los registros anteriores con estos nuevos datos, deberá ejecutar el procedimiento almacenado CqdUpdateBuilding como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="6ea30-367">To tag all the previous records with this new data, you will need to run the CqdUpdateBuilding stored procedure as shown below:</span></span> 
  
<span data-ttu-id="6ea30-368">Déle la fecha del primer registro (identifique que mediante el comando Seleccionar MIN(StartTime) FROM CqdPartitionedStreamView SQL ), un EndDate de mañana y, a continuación, NULL para los dos últimos valores.</span><span class="sxs-lookup"><span data-stu-id="6ea30-368">Give it the date of your first record (identify that using the Select MIN(StartTime) FROM CqdPartitionedStreamView SQL command ), an EndDate of tomorrow, then NULL for the last two values.</span></span>
  
<span data-ttu-id="6ea30-369">Una vez que los datos están asociados con datos de secuencia, el cubo SSIS debe volver a procesar todos los registros.</span><span class="sxs-lookup"><span data-stu-id="6ea30-369">Once the data is associated with stream data, the SSIS Cube needs to reprocess all records.</span></span> <span data-ttu-id="6ea30-370">Esto también se aplica al agregar datos BSSID/ISP en masa.</span><span class="sxs-lookup"><span data-stu-id="6ea30-370">This also applies when bulk adding BSSID/ISP data.</span></span> <span data-ttu-id="6ea30-371">Asegúrese de que "Process Full" está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="6ea30-371">Ensure that "Process Full" is selected.</span></span>
