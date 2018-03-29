---
title: Implementar panel de calidad de la llamada de Skype para Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 287f64f5-0f8a-455a-8979-7b34bf0217bb
description: 'Resumen: Conozca el proceso de implementación para llamar al panel de calidad. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.'
ms.openlocfilehash: ff8f9bae2c292720bb3fd9943bc541a8eeb6759c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server-2015"></a><span data-ttu-id="f2846-104">Implementar panel de calidad de la llamada de Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="f2846-104">Deploy Call Quality Dashboard for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f2846-105">**Resumen:** Conozca el proceso de implementación para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="f2846-105">**Summary:** Learn about the deployment process for Call Quality Dashboard.</span></span> <span data-ttu-id="f2846-106">Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="f2846-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
## <a name="deployment-overview"></a><span data-ttu-id="f2846-107">Introducción a la implementación</span><span class="sxs-lookup"><span data-stu-id="f2846-107">Deployment Overview</span></span>

<span data-ttu-id="f2846-108">Panel de calidad de llamada (CQD) consta de tres componentes principales:</span><span class="sxs-lookup"><span data-stu-id="f2846-108">Call Quality Dashboard (CQD) consists of three major components:</span></span>
  
- <span data-ttu-id="f2846-109">**Base de datos de archivo**, donde se replica y se almacenan los datos de la calidad de la experiencia (QoE).</span><span class="sxs-lookup"><span data-stu-id="f2846-109">**Archive Database**, where the Quality of Experience (QoE) data is replicated and stored.</span></span>
    
- <span data-ttu-id="f2846-110">**Cubo**, donde se agregan los datos de base de datos de archivo de calidad para acceso rápido y optimizado.</span><span class="sxs-lookup"><span data-stu-id="f2846-110">**Cube**, where data from QoE Archive database is aggregated for optimized and fast access.</span></span>
    
- <span data-ttu-id="f2846-111">**Portal**, donde los usuarios pueden consultar y visualizar datos QoE fácilmente.</span><span class="sxs-lookup"><span data-stu-id="f2846-111">**Portal**, where users can easily query and visualize QoE data.</span></span>
    
![Componentes de CQD](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
<span data-ttu-id="f2846-113">El proceso de instalación para el archivo QoE implica la creación de la base de datos de archivo de calidad de la experiencia, implementar un procedimiento de SQL Server almacenan que moverá los datos desde el origen de base de datos de métricas de calidad de la experiencia en base de datos de archivo de calidad de la experiencia y configurar el trabajo de agente de SQL Server para ejecutar el almacenado procedimiento a intervalos regulares.</span><span class="sxs-lookup"><span data-stu-id="f2846-113">The setup process for QoE Archive involves creating the QoE Archive database, deploying a SQL Server stored procedure that will move the data from the source QoE Metrics database into QoE Archive database, and setting up the SQL Server Agent job to execute the stored procedure at a regular interval.</span></span> 
  
<span data-ttu-id="f2846-114">Implementación del cubo obtiene información del usuario en donde el archivo QoE se encuentra, implementa el cubo y configura un trabajo del Agente SQL Server normal que actualice el cubo a intervalos regulares.</span><span class="sxs-lookup"><span data-stu-id="f2846-114">Cube deployment gets information from the user on where the QoE Archive is located, deploys the cube, and sets up a regular SQL Server agent job that will refresh the cube at a regular interval.</span></span>
  
<span data-ttu-id="f2846-115">Instalar portal crea una base de datos que almacena la asignación de usuarios CQD, informes y consultas de cada usuario.</span><span class="sxs-lookup"><span data-stu-id="f2846-115">Portal install creates a Repository database that stores the mapping of CQD users to each user's reports/queries.</span></span> <span data-ttu-id="f2846-116">A continuación, configura una aplicación web IIS que es el panel donde los usuarios pueden ver un conjunto de informes predefinido, así como personalizar y crear sus propias consultas para visualizar los datos del cubo.</span><span class="sxs-lookup"><span data-stu-id="f2846-116">It then sets up an IIS web application which is the dashboard where users can see a pre-defined set of reports as well as customize and create their own queries to visualize data from the cube.</span></span> <span data-ttu-id="f2846-117">La instalación del portal crea dos aplicaciones web adicionales que expone las API para que los usuarios obtener acceso mediante programación al repositorio y el cubo.</span><span class="sxs-lookup"><span data-stu-id="f2846-117">The portal install creates two additional web applications that exposes APIs for users to programmatically access the repository and the cube.</span></span> <span data-ttu-id="f2846-118">(Estas API se utilizan internamente por el tablero de mandos).</span><span class="sxs-lookup"><span data-stu-id="f2846-118">(These APIs are used internally by the dashboard as well.)</span></span>
  

|<span data-ttu-id="f2846-119">**Fase**</span><span class="sxs-lookup"><span data-stu-id="f2846-119">**Phase**</span></span>|<span data-ttu-id="f2846-120">**Pasos**</span><span class="sxs-lookup"><span data-stu-id="f2846-120">**Steps**</span></span>|<span data-ttu-id="f2846-121">**Funciones y pertenencia a grupos**</span><span class="sxs-lookup"><span data-stu-id="f2846-121">**Roles and group membership**</span></span>|<span data-ttu-id="f2846-122">**Documentación**</span><span class="sxs-lookup"><span data-stu-id="f2846-122">**Documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f2846-123">Instalar software y hardware necesario.</span><span class="sxs-lookup"><span data-stu-id="f2846-123">Install prerequisite hardware and software.</span></span>  <br/> |<span data-ttu-id="f2846-124">Decida la configuración CQD y elija un SQL Server desde el que se va a realizar la instalación.</span><span class="sxs-lookup"><span data-stu-id="f2846-124">Decide on the CQD configuration, and choose a SQL Server from which to perform the install.</span></span>  <br/> |<span data-ttu-id="f2846-125">Usuario de dominio que es miembro del grupo de administradores locales.</span><span class="sxs-lookup"><span data-stu-id="f2846-125">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="f2846-126">Sección "Previamente instalar requisitos" en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="f2846-126">"Pre-install Requirements" section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="f2846-127">Instalar CQD.</span><span class="sxs-lookup"><span data-stu-id="f2846-127">Install CQD.</span></span>  <br/> |<span data-ttu-id="f2846-128">Ejecute el MSI siguiendo el documento de implementación.</span><span class="sxs-lookup"><span data-stu-id="f2846-128">Run the MSI following the deployment document.</span></span>  <br/> |<span data-ttu-id="f2846-129">Para realizar la instalación, la cuenta de instalación debe ser un usuario de dominio que sea miembro del grupo local Administradores y tener acceso de lectura a la base de datos de métricas de calidad en el servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="f2846-129">To perform the setup, the installing account must be a domain user who is a member of the local administrators group and have read access to QoE Metrics database on the Monitoring Server.</span></span>  <br/> |<span data-ttu-id="f2846-130">Secciones "Cuentas y pasos de implementación" en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="f2846-130">"Accounts and Deployment Steps" sections in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="f2846-131">Conceder acceso de usuario.</span><span class="sxs-lookup"><span data-stu-id="f2846-131">Grant user access.</span></span>  <br/> |<span data-ttu-id="f2846-132">Para administrar la autorización del usuario en el Portal, se recomienda utilizar la autorización de direcciones URL, que se introdujo en IIS 7.0.</span><span class="sxs-lookup"><span data-stu-id="f2846-132">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="f2846-133">Para obtener más información, vea [Autorización de direcciones URL de descripción IIS 7.0](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span><span class="sxs-lookup"><span data-stu-id="f2846-133">For more information, see [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>  <br/> |<span data-ttu-id="f2846-134">Usuario de dominio que es miembro del grupo de administradores locales.</span><span class="sxs-lookup"><span data-stu-id="f2846-134">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="f2846-135">Administrar el acceso de usuario a la sección de Portal en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="f2846-135">Managing User Access for the Portal section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="f2846-136">Opcional: Proporcionar la información de asignación de subred.</span><span class="sxs-lookup"><span data-stu-id="f2846-136">Optional: Provide subnet mapping information.</span></span>  <br/> |<span data-ttu-id="f2846-137">Llenar tablas de asignación de creación de base de datos de archivo de calidad y de red.</span><span class="sxs-lookup"><span data-stu-id="f2846-137">Populate network and building mapping tables in QoE Archive database.</span></span>  <br/> |<span data-ttu-id="f2846-138">Una cuenta con acceso de escritura a la base de datos de archivo de calidad.</span><span class="sxs-lookup"><span data-stu-id="f2846-138">An account with write access to the QoE Archive database.</span></span>  <br/> |<span data-ttu-id="f2846-139">Sección "Proporcionar información de subred" en la documentación del usuario.</span><span class="sxs-lookup"><span data-stu-id="f2846-139">"Supplying Subnet Information" section in the user documentation.</span></span>  <br/> |
   
## 

<span data-ttu-id="f2846-140">Implementación de llamar al panel de calidad implica configurar la infraestructura e instalar el software.</span><span class="sxs-lookup"><span data-stu-id="f2846-140">Deployment of Call Quality Dashboard involves setting up the infrastructure and installing the software.</span></span> <span data-ttu-id="f2846-141">El siguiente procedimiento describe el proceso.</span><span class="sxs-lookup"><span data-stu-id="f2846-141">The following procedure outlines the process.</span></span>
  
### <a name="deployment-steps"></a><span data-ttu-id="f2846-142">Pasos de implementación</span><span class="sxs-lookup"><span data-stu-id="f2846-142">Deployment Steps</span></span>

1. <span data-ttu-id="f2846-143">Copie el CallQualityDashboard.msi en el equipo donde el componente de base de datos de archivo de CQD debe ser instalado (es decir, el equipo que tiene SQL Server instalado).</span><span class="sxs-lookup"><span data-stu-id="f2846-143">Copy the CallQualityDashboard.msi to the machine where the archive database component of CQD is to be installed (this is the machine that has SQL Server installed).</span></span> 
    
2. <span data-ttu-id="f2846-144">Ejecute el archivo MSI (Windows le pedirá que se ejecutan con privilegios de administrador, hágalo).</span><span class="sxs-lookup"><span data-stu-id="f2846-144">Execute the MSI (Windows will prompt to run with administrator privilege, do so).</span></span> 
    
3. <span data-ttu-id="f2846-145">Aceptar al CLUF.</span><span class="sxs-lookup"><span data-stu-id="f2846-145">Accept the EULA.</span></span>
    
4. <span data-ttu-id="f2846-146">Seleccione la carpeta de destino donde se encuentra o acepte la ubicación predeterminada archivos relacionados con componentes de panel de calidad llamar.</span><span class="sxs-lookup"><span data-stu-id="f2846-146">Select the destination folder where files related to Call Quality Dashboard components will be located or accept the default location.</span></span>
    
5. <span data-ttu-id="f2846-147">Seleccione todas las funciones.</span><span class="sxs-lookup"><span data-stu-id="f2846-147">Select all features.</span></span>
    
6. <span data-ttu-id="f2846-148">En la página Configuración de archiving QoE, proporcione la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="f2846-148">At the QoE Archive Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="f2846-149">**De SQL Server de métricas de calidad:** Nombre de la instancia de SQL Server de donde se encuentra la base de datos de métricas de calidad (Esto será el origen de datos).</span><span class="sxs-lookup"><span data-stu-id="f2846-149">**QoE Metrics SQL Server:** SQL Server instance name for where the QoE Metrics DB is located (this will be the data source).</span></span>
    
   - <span data-ttu-id="f2846-150">**Archivo QoE SQL Server nombre:** Esto es el campo de sólo lectura y se fija como el nombre de dominio completo del equipo local.</span><span class="sxs-lookup"><span data-stu-id="f2846-150">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="f2846-151">Archivo DB puede instalarse sólo en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="f2846-151">Archive DB can be installed only on the local machine.</span></span>
    
   - <span data-ttu-id="f2846-152">**Archivo QoE SQL Server instancia:** Un nombre de instancia de SQL Server local para que la base de datos de archivo debe ser creado.</span><span class="sxs-lookup"><span data-stu-id="f2846-152">**QoE Archive SQL Server Instance:** A local SQL Server instance name for where the Archive DB is to be created.</span></span> <span data-ttu-id="f2846-153">Para utilizar una instancia predeterminada de SQL Server, deje este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="f2846-153">To use a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="f2846-154">Para utilizar una instancia con nombre de SQL Server, especifique el nombre de instancia (por ejemplo, el nombre después de la "\").</span><span class="sxs-lookup"><span data-stu-id="f2846-154">To use a named SQL Server instance, specify the instance name (e.g. the name after the "\").</span></span>
    
   - <span data-ttu-id="f2846-155">**QoE Archivar base de datos:** De forma predeterminada, esta opción se establece en "Crear nueva base de datos".</span><span class="sxs-lookup"><span data-stu-id="f2846-155">**QoE Archive Database:** By default, this option is set to "Create new database".</span></span> <span data-ttu-id="f2846-156">Dado que no se admite la actualización de archivo DB, la única circunstancia en que puede utilizarse la opción "Usar la base de datos existente" es si la base de datos de archivo existente tiene el mismo esquema que la compilación para instalarse.</span><span class="sxs-lookup"><span data-stu-id="f2846-156">Since Archive DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Archive database has the same schema as the build to be installed.</span></span>
    
   - <span data-ttu-id="f2846-157">**Directorio del archivo de base de datos:** Ruta de acceso donde se colocarán los archivos de base de datos (.mdf y .ldf) de la base de datos de archivo.</span><span class="sxs-lookup"><span data-stu-id="f2846-157">**Database File Directory:** Path to where the database files (.mdf and .ldf) for the Archive DB should be placed.</span></span> <span data-ttu-id="f2846-158">Esto debe estar en una unidad independiente (HDD2 en la configuración de hardware recomendada) desde el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="f2846-158">This should be on a drive (HDD2 in the recommended hardware configuration) separate from the OS.</span></span> <span data-ttu-id="f2846-159">Tenga en cuenta que dado que los nombres de archivo se corrigen en la instalación, para evitar posibles conflictos, se recomienda que se utilice un directorio no tiene archivos en blanco.</span><span class="sxs-lookup"><span data-stu-id="f2846-159">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="f2846-160">**Utilizar varias particiones:** El valor predeterminado se establece en "Partición múltiples", que no requiere edición Business Intelligence o Enterprise edition de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f2846-160">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="f2846-161">Para Standard edition, seleccione la opción de "Partición única".</span><span class="sxs-lookup"><span data-stu-id="f2846-161">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="f2846-162">Tenga en cuenta que el rendimiento de procesamiento del cubo puede verse afectado si se utiliza una única partición.</span><span class="sxs-lookup"><span data-stu-id="f2846-162">Note that cube processing performance may be impacted if Single Partition is used.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f2846-163">No se puede cambiar la selección de la opción de usar varias particiones una vez finalizada la instalación.</span><span class="sxs-lookup"><span data-stu-id="f2846-163">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="f2846-164">Para cambiarlo, el cubo característica debe ser la primera desinstala y vuelve a instalar utilizando la opción "Cambiar" Panel de Control.</span><span class="sxs-lookup"><span data-stu-id="f2846-164">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span> 
  
   - <span data-ttu-id="f2846-165">**Crear particiones de directorio de archivo:** Ruta de acceso que se deben colocar las particiones de la base de datos de archivo de calidad.</span><span class="sxs-lookup"><span data-stu-id="f2846-165">**Partition File Directory:** Path to where the partitions for the QoE Archive database should be placed.</span></span> <span data-ttu-id="f2846-166">Esto debe estar en una unidad independiente (HDD3 en la configuración de hardware recomendada) de la unidad de sistema operativo y la unidad de archivos de registro de base de datos SQL.</span><span class="sxs-lookup"><span data-stu-id="f2846-166">This should be on a drive (HDD3 in the recommended hardware configuration) separate from the OS drive and SQL database log files drive.</span></span> <span data-ttu-id="f2846-167">Tenga en cuenta que dado que los nombres de archivo se corrigen en la instalación, para evitar posibles conflictos, se recomienda que se utilice un directorio no tiene archivos en blanco.</span><span class="sxs-lookup"><span data-stu-id="f2846-167">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="f2846-168">**Usuario de trabajo del Agente SQL - nombre de usuario &amp; contraseña:** Nombre de cuenta de servicio de dominio y la contraseña (máscara) que se utilizará para ejecutar el paso de "Datos de archivo de la calidad" del trabajo del agente de SQL Server (que se ejecutará el procedimiento almacenado para recuperar datos la base de datos de métricas de calidad de la experiencia en archivo DB, por lo que esta cuenta debe tener acceso de lectura a DB de métricas de calidad,  como se indica en la sección de cuentas.</span><span class="sxs-lookup"><span data-stu-id="f2846-168">**SQL Agent Job User - User Name &amp; Password:** Domain service account name and password (masked) that will be used to run the "QoE Archive Data" step of the SQL Server Agent job (which will run the stored procedure to fetch data from QoE Metrics DB into Archive DB, so this account must have read access to QoE Metrics DB, as indicated under Accounts section.</span></span> <span data-ttu-id="f2846-169">Esta cuenta debe tener también un inicio de sesión en la instancia de SQL Server de QoE Archive).</span><span class="sxs-lookup"><span data-stu-id="f2846-169">This account also needs to have a login in the QoE Archive SQL Server Instance).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f2846-170">La cuenta que se está ejecutando la instancia de SQL Server, como SERVICE\MSSQLSERVER de NT, debe tener acceso a los directorios mencionados para que la instalación se realice correctamente.</span><span class="sxs-lookup"><span data-stu-id="f2846-170">The account that the SQL Server instance is running under, such as NT SERVICE\MSSQLSERVER, must have access/permission to the directories given above for the installation to succeed.</span></span> <span data-ttu-id="f2846-171">Para obtener información detallada, vea [Configurar permisos de sistema de archivos para obtener acceso al motor de base de datos](https://msdn.microsoft.com/en-us/library/jj219062%28v=sql.110%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f2846-171">For details, see [Configure File System Permissions for Database Engine Access](https://msdn.microsoft.com/en-us/library/jj219062%28v=sql.110%29.aspx)</span></span>
  
7. <span data-ttu-id="f2846-172">Al hacer clic en siguiente, el programa de instalación llevará a cabo comprobaciones de requisitos previos e informe si se produjeran problemas.</span><span class="sxs-lookup"><span data-stu-id="f2846-172">Upon clicking next, the installer will perform pre-requisite checks and report if any issues are encountered.</span></span> <span data-ttu-id="f2846-173">Cuando comprueba todo son un requisito previo paso, el programa de instalación se vaya a la página de configuración de cubo.</span><span class="sxs-lookup"><span data-stu-id="f2846-173">When all pre-requisite checks pass, the installer will go to the Cube Configuration page.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="f2846-174">Si el programa de instalación muestra un mensaje de advertencia que el servicio Agente de SQL Server para la instancia de SQL Server archivo QoE no se está ejecutando actualmente, la instalación puede continuar, pero posterior a la instalación, asegúrese que el servicio Agente SQL está ejecutando y establece el tipo de inicio en Automática para que se ejecute la tarea programada.</span><span class="sxs-lookup"><span data-stu-id="f2846-174">If the installer shows a warning message that the SQL Server Agent service for the QoE Archive SQL Server instance is currently not running, installation can proceed, but post installation please make sure that SQL Agent service is running and set the Startup type to Automatic so that the scheduled Job runs.</span></span> 
  
8. <span data-ttu-id="f2846-175">En la página de configuración de cubo, proporcione la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="f2846-175">At Cube Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="f2846-176">**Archivo QoE SQL Server nombre:** Esto es el campo de sólo lectura y se fija como el nombre de dominio completo del equipo local.</span><span class="sxs-lookup"><span data-stu-id="f2846-176">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="f2846-177">Cubo puede instalarse sólo desde el equipo que tiene la base de datos de archivo de calidad (Nota.</span><span class="sxs-lookup"><span data-stu-id="f2846-177">Cube can be installed only from the machine that has QoE Archive database (Note.</span></span> <span data-ttu-id="f2846-178">Cubo puede instalarse en un equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="f2846-178">Cube itself may be installed on a remote machine.</span></span> <span data-ttu-id="f2846-179">Vea a continuación)</span><span class="sxs-lookup"><span data-stu-id="f2846-179">See below)</span></span>
    
   - <span data-ttu-id="f2846-180">**Archivo QoE SQL Server instancia:** Nombre de la instancia de SQL Server de donde se encuentra la base de datos de archivo QoE.</span><span class="sxs-lookup"><span data-stu-id="f2846-180">**QoE Archive SQL Server Instance:** SQL Server instance name for where the QoE Archive DB is located.</span></span> <span data-ttu-id="f2846-181">Para especificar una instancia de SQL Server predeterminada, deje este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="f2846-181">To specify a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="f2846-182">Para especificar una instancia con nombre de SQL Server, escriba el nombre de instancia (por ejemplo, el nombre después de la "\").</span><span class="sxs-lookup"><span data-stu-id="f2846-182">To specify a named SQL Server instance, enter the instance name (e.g. the name after the "\").</span></span> <span data-ttu-id="f2846-183">Si el componente de archiving QoE fue seleccionado para la instalación, este campo se rellenará previamente con el valor proporcionado en la página Configuración de archiving QoE.</span><span class="sxs-lookup"><span data-stu-id="f2846-183">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
   - <span data-ttu-id="f2846-184">**De cubo Analysis Server:** Nombre de la instancia de SQL Server Analysis Services para donde es necesario crear el cubo.</span><span class="sxs-lookup"><span data-stu-id="f2846-184">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is to be created.</span></span> <span data-ttu-id="f2846-185">Esto puede ser un equipo diferente, pero el usuario que instala debe ser un miembro del grupo Administradores de servidor de la instancia de Analysis Services de SQL Server de destino.</span><span class="sxs-lookup"><span data-stu-id="f2846-185">This can be a different machine but the installing user has to be a member of Server administrators of the target SQL Server Analysis Service instance.</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="f2846-186">Para obtener más información acerca de cómo configurar permisos de administrador de servidor de servicios de análisis, vea [Conceder permisos de administrador del servidor (Analysis Services)](https://msdn.microsoft.com/en-us/library/ms174561.aspx)</span><span class="sxs-lookup"><span data-stu-id="f2846-186">For more information about configuring Analysis Services Server Administrator Permissions, see [Grant Server Administrator Permissions (Analysis Services)](https://msdn.microsoft.com/en-us/library/ms174561.aspx)</span></span>
  
   - <span data-ttu-id="f2846-187">**Utilizar varias particiones:** El valor predeterminado se establece en "Partición múltiples", que no requiere edición Business Intelligence o Enterprise edition de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f2846-187">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="f2846-188">Para Standard edition, seleccione la opción de "Partición única".</span><span class="sxs-lookup"><span data-stu-id="f2846-188">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="f2846-189">Tenga en cuenta que el rendimiento de procesamiento del cubo puede verse afectado si se utiliza una única partición.</span><span class="sxs-lookup"><span data-stu-id="f2846-189">Note that cube processing performance may be impacted if Single Partition is used .</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="f2846-190">No se puede cambiar la selección de la opción de usar varias particiones una vez finalizada la instalación.</span><span class="sxs-lookup"><span data-stu-id="f2846-190">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="f2846-191">Para cambiarlo, el cubo característica debe ser la primera desinstala y vuelve a instalar utilizando la opción "Cambiar" Panel de Control.</span><span class="sxs-lookup"><span data-stu-id="f2846-191">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span>
  
   - <span data-ttu-id="f2846-192">**Usuario - nombre de usuario de cubo &amp; contraseña:** Nombre de cuenta de servicio de dominio y una contraseña (máscara) que desencadene el procesamiento del cubo.</span><span class="sxs-lookup"><span data-stu-id="f2846-192">**Cube User - User Name &amp; Password:** Domain service account name and password (masked) that will trigger the cube processing.</span></span> <span data-ttu-id="f2846-193">Si el componente de archiving QoE fue seleccionado para la instalación, este campo se rellenará previamente con el valor proporcionado en la página de configuración de archivo para el usuario de trabajo del Agente SQL, pero es recomendable que especifique una cuenta de servicio de dominio diferente para que el programa de instalación puede conceder la privilegios necesarios mínimos a él.</span><span class="sxs-lookup"><span data-stu-id="f2846-193">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the Archive Configuration page for the SQL Agent Job User, but we recommend specifying a different domain service account so that Setup can grant the least required privilege to it.</span></span>
    
9. <span data-ttu-id="f2846-194">Al hacer clic en siguiente, se realizará otra ronda de validación y notificará cualquier problema.</span><span class="sxs-lookup"><span data-stu-id="f2846-194">When clicking next, another round of validation will be performed and any issue will be reported.</span></span> <span data-ttu-id="f2846-195">Tras completar correctamente la validación, el instalador se vaya a la página de configuración del Portal.</span><span class="sxs-lookup"><span data-stu-id="f2846-195">Upon successful completion of the validation, the installer will go to the Portal Configuration page.</span></span> 
    
10. <span data-ttu-id="f2846-196">En la página Configuración de Portal, proporcione la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="f2846-196">At Portal Configuration page, provide the following information:</span></span>
    
    - <span data-ttu-id="f2846-197">**Archivo QoE SQL Server:** Nombre de la instancia de SQL Server de donde se encuentra la base de datos de archivo de calidad.</span><span class="sxs-lookup"><span data-stu-id="f2846-197">**QoE Archive SQL Server:** SQL Server instance name for where the QoE Archive database is located.</span></span> <span data-ttu-id="f2846-198">Tenga en cuenta que, a diferencia de la página de configuración de archivo de calidad de la experiencia y la página de configuración de cubo, el nombre del equipo no es fijo y se debe proporcionar.</span><span class="sxs-lookup"><span data-stu-id="f2846-198">Note that unlike the QoE Archive Configuration page and the Cube Configuration page, the machine name is not fixed and must be provided.</span></span> <span data-ttu-id="f2846-199">Si el componente de archiving QoE fue seleccionado para la instalación, este campo se rellenará previamente con el valor proporcionado en la página Configuración de archiving QoE.</span><span class="sxs-lookup"><span data-stu-id="f2846-199">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
    - <span data-ttu-id="f2846-200">**De cubo Analysis Server:** Nombre de la instancia de SQL Server Analysis Services para donde se encuentra el cubo.</span><span class="sxs-lookup"><span data-stu-id="f2846-200">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is located.</span></span> <span data-ttu-id="f2846-201">Si se selecciona el componente de cubo para la instalación, este campo se rellenará previamente con el valor proporcionado en la página Configuración de cubo.</span><span class="sxs-lookup"><span data-stu-id="f2846-201">If Cube component was selected for the install, this field will be pre-populated with the value provided on the Cube Configuration page.</span></span>
    
    - <span data-ttu-id="f2846-202">**Repositorio de SQL Server:** Donde es la base de datos de repositorio que se cree el nombre de la instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f2846-202">**Repository SQL Server:** SQL Server instance name where the Repository database is to be created.</span></span> <span data-ttu-id="f2846-203">Si se ha proporcionado el nombre de la instancia de SQL Server de donde se encuentra la base de datos de archivo QoE anteriormente en el programa de instalación (en otros componentes), este campo se rellenará previamente con el nombre de instancia QoE archivo base de datos SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f2846-203">If the SQL Server instance name for where the QoE Archive database is located has been provided earlier in the setup (in other components), this field will be pre-populated with the QoE Archive DB SQL Server instance name.</span></span> <span data-ttu-id="f2846-204">Puede tratarse de cualquier instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f2846-204">This can be any SQL Server instance.</span></span>
    
    - <span data-ttu-id="f2846-205">**Base de datos de repositorio:** De forma predeterminada la opción se establece en "Crear nueva base de datos".</span><span class="sxs-lookup"><span data-stu-id="f2846-205">**Repository Database:** By default the option is set to "Create new database".</span></span> <span data-ttu-id="f2846-206">Dado que no se admite la actualización de la base de datos de repositorio, la única circunstancia en que puede utilizarse la opción "Usar la base de datos existente" es si la base de datos de repositorio existente tiene el mismo esquema que la compilación para instalarse.</span><span class="sxs-lookup"><span data-stu-id="f2846-206">Since Repository DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Repository DB has the same schema as the build to be installed.</span></span>
    
    - <span data-ttu-id="f2846-207">**Grupo de aplicaciones IIS usuario - nombre de usuario &amp; contraseña:** La cuenta que se debe ejecutar en el grupo de aplicaciones IIS.</span><span class="sxs-lookup"><span data-stu-id="f2846-207">**IIS App Pool User - User Name &amp; Password:** The account that the IIS application pool should execute under.</span></span> <span data-ttu-id="f2846-208">Los campos nombre de usuario y la contraseña aparecerá atenuados si se seleccionan las cuentas del sistema integrado.</span><span class="sxs-lookup"><span data-stu-id="f2846-208">The User Name and Password fields will be grayed out if built-in system accounts are selected.</span></span> <span data-ttu-id="f2846-209">Estos campos sólo se habilitará si "Otros" está seleccionada en el cuadro desplegable para que el usuario puede escribir la información de cuenta de servicio de dominio.</span><span class="sxs-lookup"><span data-stu-id="f2846-209">These fields will only be enabled if "Other" is selected from the drop down box so the user can enter the domain service account information.</span></span>
    
11. <span data-ttu-id="f2846-210">Al hacer clic en siguiente, se realizará la Ronda final de validación para asegurarse de que las instancias de SQL Server son accesibles mediante las credenciales proporcionadas y que está disponible en el equipo IIS.</span><span class="sxs-lookup"><span data-stu-id="f2846-210">When clicking next, the final round of validation will be done to ensure that the SQL Server instances are accessible using the credentials provided and that IIS is available on the machine.</span></span> <span data-ttu-id="f2846-211">Tras completar correctamente la validación, el programa de instalación continuará con la instalación.</span><span class="sxs-lookup"><span data-stu-id="f2846-211">Upon successful completion of the validation, the installer will proceed with the setup.</span></span> 
    
<span data-ttu-id="f2846-212">Cuando el instalador haya finalizado, más probable es que el trabajo del agente de SQL Server será en curso, realizando la carga inicial de los datos de la calidad y el procesamiento del cubo.</span><span class="sxs-lookup"><span data-stu-id="f2846-212">When the installer is done, most likely the SQL Server Agent job will be in progress, doing the initial load of the QoE data and the cube processing.</span></span> <span data-ttu-id="f2846-213">Dependiendo de la cantidad de datos de calidad, el portal no tendrá datos disponibles para su visualización aún.</span><span class="sxs-lookup"><span data-stu-id="f2846-213">Depending on the amount of data in QoE, the portal will not have data available for viewing yet.</span></span> <span data-ttu-id="f2846-214">Para comprobar el estado de la carga de datos y el procesamiento del cubo, vaya a `http://<machinename>/CQD/#/Health`.</span><span class="sxs-lookup"><span data-stu-id="f2846-214">To check on the status of the data load and cube processing, go to  `http://<machinename>/CQD/#/Health`.</span></span> 
> [!NOTE]
> <span data-ttu-id="f2846-215">Tenga en cuenta que la dirección URL para comprobar el estado de la descarga de procesamiento de cubos distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="f2846-215">Note that the URL for checking the status of the download cube processing is case sensitive.</span></span> <span data-ttu-id="f2846-216">Si escribe la dirección URL no funciona ' estado'.</span><span class="sxs-lookup"><span data-stu-id="f2846-216">If you enter 'health' the URL will not work.</span></span> <span data-ttu-id="f2846-217">Debe especificar 'Estado' al final de la dirección URL con una mayúscula H.</span><span class="sxs-lookup"><span data-stu-id="f2846-217">You must enter 'Health' at the end of the URL with a capital H.</span></span> 
  
<span data-ttu-id="f2846-218">Mensajes de registro detallado se mostrará si está habilitado el modo de depuración.</span><span class="sxs-lookup"><span data-stu-id="f2846-218">Detailed log messages will be shown if debug mode is enabled.</span></span> <span data-ttu-id="f2846-219">Para habilitar el modo de depuración, vaya a **%SYSTEMDRIVE%\Program Files\Skype para negocios 2015 CQD\QoEDataService\web.config**y actualizar la siguiente línea, por lo que el valor se establece en **True**:</span><span class="sxs-lookup"><span data-stu-id="f2846-219">To enable debug mode, go to **%SYSTEMDRIVE%\Program Files\Skype For Business 2015 CQD\QoEDataService\web.config**, and update the following line so the value is set to **True**:</span></span>

```
<add key="QoEDataLib.DebugMode" value="True" /> 
```

<span data-ttu-id="f2846-220">Es accesible a través de la página principal del portal `http://<machinename>/CQD`.</span><span class="sxs-lookup"><span data-stu-id="f2846-220">The main portal page is accessible via  `http://<machinename>/CQD`.</span></span> 
## <a name="managing-user-access-for-the-portal"></a><span data-ttu-id="f2846-221">Administración del acceso de usuario para el Portal</span><span class="sxs-lookup"><span data-stu-id="f2846-221">Managing User Access for the Portal</span></span>

<span data-ttu-id="f2846-222">Para administrar la autorización del usuario en el Portal, se recomienda utilizar la autorización de direcciones URL, que se introdujo en IIS 7.0.</span><span class="sxs-lookup"><span data-stu-id="f2846-222">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="f2846-223">Para obtener más información acerca de la seguridad IIS, vea [Autorización de direcciones URL de descripción IIS 7.0 ](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span><span class="sxs-lookup"><span data-stu-id="f2846-223">For more information on IIS security, see [Understanding IIS 7.0 URL Authorization ](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>
  
<span data-ttu-id="f2846-224">Cualquier aplicación de web o sitio web heredan el valor predeterminado configurado para todo IIS, que normalmente es "Permitir que todos los usuarios" de autorización de direcciones URL.</span><span class="sxs-lookup"><span data-stu-id="f2846-224">Any web site or web application inherit the default URL Authorization configured for the entire IIS, which is typically "Allow All Users".</span></span> <span data-ttu-id="f2846-225">Si necesita acceso al Portal para que sea más restrictivo, a continuación, los administradores pueden conceder acceso a sólo el grupo de usuarios específico mediante la modificación de las reglas de autorización"".</span><span class="sxs-lookup"><span data-stu-id="f2846-225">If access to the Portal needs to be more restrictive, then administrators can grant access to only the specific group of users by editing the "Authorization Rules".</span></span>
  
![Implementar la calidad de llamadas: reglas de autorización en IIS](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> <span data-ttu-id="f2846-227">El icono de las reglas de autorización no es se debe confundir con la "autorización. NET" en la sección ASP.NET, que es un mecanismo de autorización diferente.</span><span class="sxs-lookup"><span data-stu-id="f2846-227">The Authorization Rules icon is not to be confused with the ".NET Authorization" under the ASP.NET section, which is a different authorization mechanism.</span></span> 
  
<span data-ttu-id="f2846-228">Los administradores deben quitar primero la regla heredada "permitir que todos los usuarios".</span><span class="sxs-lookup"><span data-stu-id="f2846-228">Administrators should first remove the inherited "Allow All Users" rule.</span></span> <span data-ttu-id="f2846-229">Esto impide que los usuarios no autorizados accedan al Portal.</span><span class="sxs-lookup"><span data-stu-id="f2846-229">This prevents any non-authorized users from accessing the Portal.</span></span>
  
![Implementar CQD](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
<span data-ttu-id="f2846-231">A continuación, los administradores deben agregar nuevas reglas permitir y conceder el permiso para acceder al Portal de usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="f2846-231">Next, administrators should add new Allow Rules and give specific users the permission to access the Portal.</span></span> <span data-ttu-id="f2846-232">Se recomienda que un grupo local llamado "CQDPortalUsers" se crea para administrar los usuarios.</span><span class="sxs-lookup"><span data-stu-id="f2846-232">It is recommended that a local Group called "CQDPortalUsers" be created to manage the users.</span></span>
  
![Implementar el panel de calidad de llamadas](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
<span data-ttu-id="f2846-234">Los detalles de configuración se almacenan en el archivo web.config ubicado en el directorio físico del Portal.</span><span class="sxs-lookup"><span data-stu-id="f2846-234">The configuration details are stored in the web.config located at the Portal's physical directory.</span></span>
  
```
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

<span data-ttu-id="f2846-235">El siguiente paso es configurar el panel de la CQD.</span><span class="sxs-lookup"><span data-stu-id="f2846-235">The next step is to configure the dashboard of the CQD.</span></span> <span data-ttu-id="f2846-236">Después de que IIS autentica a los usuarios, deberán tener permisos de archivo en el directorio CQD para acceder al contenido de portal web.</span><span class="sxs-lookup"><span data-stu-id="f2846-236">After users are authenticated by IIS, they will have to have file permissions on the CQD directory in order to access the web portal content.</span></span> <span data-ttu-id="f2846-237">Es posible cambiar las ACL a través de la ficha de seguridad de las propiedades del directorio CQD para agregar usuarios individuales o grupos; Sin embargo, el enfoque recomendado es dejar intactos los permisos de archivo.</span><span class="sxs-lookup"><span data-stu-id="f2846-237">It is possible to change the ACLs through the security tab of the CQD directory properties to add individual users or groups; however the recommended approach is to leave the file permissions untouched.</span></span> <span data-ttu-id="f2846-238">En su lugar, cambie la configuración de IIS para utilizar el proceso de trabajo IIS para tener acceso al directorio CQD, independientemente de que el usuario está autenticado.</span><span class="sxs-lookup"><span data-stu-id="f2846-238">Instead, change the IIS setting to use the IIS worker process to access the CQD directory no matter which user is authenticated.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="f2846-239">Es importante que sólo cambiar esta configuración para la aplicación de CQD y no para las dos aplicaciones API: QoEDataService y QoERepositoryService.</span><span class="sxs-lookup"><span data-stu-id="f2846-239">It is important to only change this setting for the CQD application, and not for the two API applications: QoEDataService and QoERepositoryService.</span></span> 
  
### <a name="configuring-file-access-for-the-cqd-dashboard"></a><span data-ttu-id="f2846-240">Configuración de acceso de archivo para el CQD (escritorio)</span><span class="sxs-lookup"><span data-stu-id="f2846-240">Configuring File Access for the CQD (Dashboard)</span></span>

1. <span data-ttu-id="f2846-241">Abra el Editor de configuración para CQD.</span><span class="sxs-lookup"><span data-stu-id="f2846-241">Open the Configuration Editor for CQD.</span></span>
    
     ![Implementar el panel de calidad de llamadas](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. <span data-ttu-id="f2846-243">En la sección, elija **system.webServer/serverRuntime**.</span><span class="sxs-lookup"><span data-stu-id="f2846-243">Under Section, choose **system.webServer/serverRuntime**.</span></span>
    
     ![Implementar el panel de calidad de llamadas](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. <span data-ttu-id="f2846-245">Cambie authenticatedUserOverride a **UseWorkerProcessUser**.</span><span class="sxs-lookup"><span data-stu-id="f2846-245">Change authenticatedUserOverride to **UseWorkerProcessUser**.</span></span>
    
     ![Implementar el panel de calidad de llamadas: editor de configuración](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. <span data-ttu-id="f2846-247">Haga clic en **Aplicar** en el lado derecho de la página.</span><span class="sxs-lookup"><span data-stu-id="f2846-247">Click **Apply** on the right-hand side of the page.</span></span>
    
## <a name="known-issues"></a><span data-ttu-id="f2846-248">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="f2846-248">Known Issues</span></span>

<span data-ttu-id="f2846-249">En raras ocasiones, el programa de instalación no puede crear la configuración correcta en IIS.</span><span class="sxs-lookup"><span data-stu-id="f2846-249">In rare cases, the installer fails to create the correct settings in IIS.</span></span> <span data-ttu-id="f2846-250">Cambio manual es necesaria para permitir a los usuarios iniciar sesión en el CQD.</span><span class="sxs-lookup"><span data-stu-id="f2846-250">Manual change is required to allow users to log into the CQD.</span></span> <span data-ttu-id="f2846-251">Si los usuarios tienen problemas para iniciar sesión, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="f2846-251">If users are having trouble logging in, please follow these steps:</span></span>
  
1. <span data-ttu-id="f2846-252">Abra el Administrador de IIS y vaya al sitio Web predeterminado.</span><span class="sxs-lookup"><span data-stu-id="f2846-252">Open up IIS Manager, and navigate to Default Web Site.</span></span>
    
     ![Implementar el panel de calidad de llamadas](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. <span data-ttu-id="f2846-254">Haga clic en "Autenticación".</span><span class="sxs-lookup"><span data-stu-id="f2846-254">Click on "Authentication".</span></span> <span data-ttu-id="f2846-255">Si la "Autenticación anónima", "Suplantación de ASP.NET", "Autenticación mediante formularios" y "Autenticación de Windows" no coincide con la mostrada a continuación, cámbielos manualmente para que coincida con la siguiente configuración.</span><span class="sxs-lookup"><span data-stu-id="f2846-255">If the "Anonymous Authentication", "ASP.NET Impersonation", "Form Authentication", and "Windows Authentication" do not match the settings shown below, manually change them to match the settings below.</span></span> <span data-ttu-id="f2846-256">Todos los otros mecanismos de autenticación deben estar deshabilitadas.</span><span class="sxs-lookup"><span data-stu-id="f2846-256">All other authentication mechanisms should be disabled.</span></span>
    
     ![Implementar el panel de calidad de llamadas](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. <span data-ttu-id="f2846-258">"Autenticación de Windows", haga clic en Configuración avanzada en el lado derecho.</span><span class="sxs-lookup"><span data-stu-id="f2846-258">For "Windows Authentication", click on Advanced Settings on the right-hand side.</span></span>
    
     ![Implementar el panel de calidad de llamadas](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. <span data-ttu-id="f2846-260">Establecer "Protección ampliada" para aceptar y Active la casilla de "autenticación de modo Kernel habilitar".</span><span class="sxs-lookup"><span data-stu-id="f2846-260">Set "Extended Protection" to Accept and check the "Enable Kernel-mode authentication" box.</span></span>
    
     ![Implementar el panel de calidad de llamadas](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. <span data-ttu-id="f2846-262">Repita los pasos anteriores para cada una de las entradas de "CQD", "QoEDataService" y "QoERepositoryService" debajo de "sitio Web predeterminado".</span><span class="sxs-lookup"><span data-stu-id="f2846-262">Repeat the above steps for each of the "CQD", "QoEDataService", and "QoERepositoryService" entries below "Default Web Site".</span></span>
    
<span data-ttu-id="f2846-263">Para los enlaces de puerto HTTP y HTTPS, el instalador creará enlaces de puertos en los números de puerto predeterminado (puerto 80 para HTTP) y el puerto 443 para HTTPS.</span><span class="sxs-lookup"><span data-stu-id="f2846-263">For HTTP and HTTPS port bindings the installer will create port bindings on the default port numbers (port 80 for HTTP and port 443 for HTTPS).</span></span> <span data-ttu-id="f2846-264">Si hay otro sitio Web en el equipo que utiliza estos enlaces, habrá un conflicto y no se puede predecir el comportamiento IIS.</span><span class="sxs-lookup"><span data-stu-id="f2846-264">If there is another website on the machine that uses these bindings, there will be a conflict and the IIS behavior cannot be predicted.</span></span> <span data-ttu-id="f2846-265">La mejor manera de evitar este problema es asegurarse de que no hay otros sitios Web se asigna a los puertos 80 y 443 antes de instalar CQD.</span><span class="sxs-lookup"><span data-stu-id="f2846-265">The best way to avoid this problem is to make sure that no other websites are mapped to ports 80 and 443 before installing CQD.</span></span> 
  
<span data-ttu-id="f2846-266">Para habilitar SSL/TLS en IIS y obligar a los usuarios conectarse a través de HTTPS seguro en lugar de HTTP:</span><span class="sxs-lookup"><span data-stu-id="f2846-266">To enable SSL/TLS in IIS and force users to connect via secure HTTPS instead of HTTP:</span></span>
  
1. <span data-ttu-id="f2846-267">Configurar Secure Sockets Layer en IIS, vea [Configuring Secure Sockets Layer in IIS 7](https://technet.microsoft.com/en-us/library/cc771438%28v=ws.10%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="f2846-267">Configure Secure Sockets Layer in IIS, see [Configuring Secure Sockets Layer in IIS 7](https://technet.microsoft.com/en-us/library/cc771438%28v=ws.10%29.aspx).</span></span> <span data-ttu-id="f2846-268">Una vez hecho esto, reemplace `http` con `https`.</span><span class="sxs-lookup"><span data-stu-id="f2846-268">Once done, replace  `http` with `https`.</span></span>
    
2. <span data-ttu-id="f2846-269">Para obtener instrucciones acerca de cómo habilitar TLS en las conexiones de SQL Server, vea [cómo habilitar el cifrado SSL para una instancia de SQL Server utilizando Microsoft Management Console ](https://support.microsoft.com/en-us/kb/316898/).</span><span class="sxs-lookup"><span data-stu-id="f2846-269">For instructions on enabling TLS in the SQL Server connections, see [How to enable SSL encryption for an instance of SQL Server by using Microsoft Management Console ](https://support.microsoft.com/en-us/kb/316898/).</span></span>
    
### <a name="cube-sync-fails"></a><span data-ttu-id="f2846-270">Error de sincronización de cubo</span><span class="sxs-lookup"><span data-stu-id="f2846-270">Cube Sync Fails</span></span>

<span data-ttu-id="f2846-271">QoEMetrics puede contener algunos registros no válidos tomando como base los relojes del usuario final.</span><span class="sxs-lookup"><span data-stu-id="f2846-271">QoEMetrics may contain some invalid records based on end user clocks.</span></span> <span data-ttu-id="f2846-272">Si el desfase temporal es mayor que 60 años, se producirá un error en la importación de cubo.</span><span class="sxs-lookup"><span data-stu-id="f2846-272">If the time skew is greater than 60 yrs, the cube import will fail.</span></span>
  
 <span data-ttu-id="f2846-273">Compruebe el Min y Max StartTime y EndTime mediante las siguientes selecciones.</span><span class="sxs-lookup"><span data-stu-id="f2846-273">Check the Min and Max StartTime/EndTime using the selections below.</span></span> <span data-ttu-id="f2846-274">Buscar y eliminar registros en el futuro ahora, pasado y muy distante, puede tenerse y se romperán los procesos de sincronización.</span><span class="sxs-lookup"><span data-stu-id="f2846-274">Look for and delete records in the far past and very distant future, they can be disregarded and they will break up the sync processes.</span></span>
  
- <span data-ttu-id="f2846-275">Seleccione MIN(StartTime) de CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="f2846-275">Select MIN(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="f2846-276">Seleccione MAX(StartTime) de CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="f2846-276">Select MAX(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="f2846-277">Seleccione MIN(EndTime) de CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="f2846-277">Select MIN(EndTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="f2846-278">Seleccione MAX(EndTime) de CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="f2846-278">Select MAX(EndTime) FROM CqdPartitionedStreamView</span></span>
    
## <a name="post-install-tasks"></a><span data-ttu-id="f2846-279">Tareas posteriores a la instalación</span><span class="sxs-lookup"><span data-stu-id="f2846-279">Post-install tasks</span></span>

### <a name="importing-buildings-and-networks"></a><span data-ttu-id="f2846-280">Importación de edificios y redes</span><span class="sxs-lookup"><span data-stu-id="f2846-280">Importing Buildings and Networks</span></span>

<span data-ttu-id="f2846-281">Después de instalar CQD, realice las siguientes tareas de configuración:</span><span class="sxs-lookup"><span data-stu-id="f2846-281">After Installing CQD, perform the following configuration tasks:</span></span>
  
1. <span data-ttu-id="f2846-282">Definir tipos de edificio (recomendados)</span><span class="sxs-lookup"><span data-stu-id="f2846-282">Define Building types (recommended)</span></span>
    
2. <span data-ttu-id="f2846-283">Definir los tipos de propiedad del edificio (recomendados)</span><span class="sxs-lookup"><span data-stu-id="f2846-283">Define Building Ownership types (recommended)</span></span>
    
3. <span data-ttu-id="f2846-284">Definir los tipos de red (altamente recomendados)</span><span class="sxs-lookup"><span data-stu-id="f2846-284">Define Network types (highly recommended)</span></span>
    
4. <span data-ttu-id="f2846-285">Edificios de importación (recomendado)</span><span class="sxs-lookup"><span data-stu-id="f2846-285">Import Buildings (recommended)</span></span>
    
5. <span data-ttu-id="f2846-286">Subredes de importación (recomendadas)</span><span class="sxs-lookup"><span data-stu-id="f2846-286">Import Subnets (recommended)</span></span>
    
### <a name="define-building-types"></a><span data-ttu-id="f2846-287">Definir tipos de edificios</span><span class="sxs-lookup"><span data-stu-id="f2846-287">Define Building Types</span></span>

<span data-ttu-id="f2846-288">Tipos de construcción se utilizan para describir las definiciones de diferentes edificios o tipos dentro de su organización.</span><span class="sxs-lookup"><span data-stu-id="f2846-288">Building types are used to describe the different buildings definitions or types within your organization.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f2846-289">Este paso es opcional, pero recomendado.</span><span class="sxs-lookup"><span data-stu-id="f2846-289">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="f2846-290">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="f2846-290">Examples</span></span>
  
- <span data-ttu-id="f2846-291">Sede central</span><span class="sxs-lookup"><span data-stu-id="f2846-291">Headquarters</span></span>
    
- <span data-ttu-id="f2846-292">Oficina remota</span><span class="sxs-lookup"><span data-stu-id="f2846-292">Remote Office</span></span>
    
- <span data-ttu-id="f2846-293">Ubicación de la empresa conjunta</span><span class="sxs-lookup"><span data-stu-id="f2846-293">Joint-venture location</span></span>
    
 <span data-ttu-id="f2846-294">**Sintaxis de SQL de ejemplo**</span><span class="sxs-lookup"><span data-stu-id="f2846-294">**Sample SQL Syntax**</span></span>
  
```
INSERT INTO
[dbo].[CqdBuildingType]
([BuildingTypeId],
[BuildingTypeDesc])
VALUES
(1, 
'Headquarters') 
  
```

<span data-ttu-id="f2846-295">Los parámetros BuildingTypeId y BuildingTypeDesc son necesarios.</span><span class="sxs-lookup"><span data-stu-id="f2846-295">The BuildingTypeId and BuildingTypeDesc parameters are required.</span></span>
  
### <a name="define-building-ownership-types"></a><span data-ttu-id="f2846-296">Definir los tipos de propiedad de edificio</span><span class="sxs-lookup"><span data-stu-id="f2846-296">Define Building Ownership Types</span></span>

<span data-ttu-id="f2846-297">Tipos de propiedad se utilizan para distinguir los activos arrendados propietario vs.</span><span class="sxs-lookup"><span data-stu-id="f2846-297">Ownership types are used to distinguish owned vs leased assets.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f2846-298">Este paso es opcional, pero recomendado.</span><span class="sxs-lookup"><span data-stu-id="f2846-298">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="f2846-299">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="f2846-299">Examples</span></span>
  
- <span data-ttu-id="f2846-300">Contoso arrendado no-RE&amp;F</span><span class="sxs-lookup"><span data-stu-id="f2846-300">Contoso Leased non-RE&amp;F</span></span>
    
- <span data-ttu-id="f2846-301">Contoso arrendado RE&amp;F</span><span class="sxs-lookup"><span data-stu-id="f2846-301">Contoso Leased RE&amp;F</span></span>
    
- <span data-ttu-id="f2846-302">Propiedad de Contoso</span><span class="sxs-lookup"><span data-stu-id="f2846-302">Contoso Owned</span></span>
    
- <span data-ttu-id="f2846-303">Filial arrendado</span><span class="sxs-lookup"><span data-stu-id="f2846-303">Subsidiary Leased</span></span>
    
 <span data-ttu-id="f2846-304">**Sintaxis de SQL de ejemplo**</span><span class="sxs-lookup"><span data-stu-id="f2846-304">**Sample SQL Syntax**</span></span>
  
```
INSERT INTO
[dbo].[CqdBuildingOwnershipType]
([OwnershipTypeId],
[OwnershipTypeDesc],
)

VALUES
(1,
'Contoso Owned',
)
```

<span data-ttu-id="f2846-305">Los parámetros OwnershipTypeId y OwnershipTypeDesc son necesarios.</span><span class="sxs-lookup"><span data-stu-id="f2846-305">The OwnershipTypeId and OwnershipTypeDesc parameters are required.</span></span> 
  
### <a name="define-network-names"></a><span data-ttu-id="f2846-306">Definir nombres de red</span><span class="sxs-lookup"><span data-stu-id="f2846-306">Define Network Names</span></span>

<span data-ttu-id="f2846-307">Tipos de red se utilizan para describir los diferentes tipos de redes en la organización.</span><span class="sxs-lookup"><span data-stu-id="f2846-307">Network Types are used to describe different types of networks within the organization.</span></span> <span data-ttu-id="f2846-308">Esto le da la capacidad de filtrar (o filtrar) los tipos de red específicos.</span><span class="sxs-lookup"><span data-stu-id="f2846-308">This gives you the ability to filter on (or filter out) specific Network Types.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f2846-309">Se recomienda definir los nombres de red, pero es opcional.</span><span class="sxs-lookup"><span data-stu-id="f2846-309">It is highly recommended to define Network Names, but it is optional.</span></span> <span data-ttu-id="f2846-310">Si decide no definir nombres de red, asegúrese de que cada entrada de CqdNetwork tiene un BuildingId de 0.</span><span class="sxs-lookup"><span data-stu-id="f2846-310">If you decide to not define network names, ensure the each CqdNetwork entry has a BuildingId of 0.</span></span> 
  
<span data-ttu-id="f2846-311">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="f2846-311">Examples</span></span>
  
- <span data-ttu-id="f2846-312">VPN</span><span class="sxs-lookup"><span data-stu-id="f2846-312">VPN</span></span>
    
- <span data-ttu-id="f2846-313">LABORATORIO</span><span class="sxs-lookup"><span data-stu-id="f2846-313">LAB</span></span>
    
 <span data-ttu-id="f2846-314">**Sintaxis de SQL de ejemplo**</span><span class="sxs-lookup"><span data-stu-id="f2846-314">**Sample SQL Syntax**</span></span>
  
```
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

<span data-ttu-id="f2846-315">Los parámetros NetworkNameID y NetworkName son necesarios, el parámetro NetworkType es opcional pero se recomienda.</span><span class="sxs-lookup"><span data-stu-id="f2846-315">The NetworkNameID and NetworkName parameters are required, the NetworkType parameter is optional but recommended.</span></span>
  
### <a name="import-buildings"></a><span data-ttu-id="f2846-316">Edificios de importación</span><span class="sxs-lookup"><span data-stu-id="f2846-316">Import Buildings</span></span>

<span data-ttu-id="f2846-317">Importación de edificios permite obtener creación de conocimientos específicos (llamadas deficientes por edificio en WiFi o por cable, etcetera.).</span><span class="sxs-lookup"><span data-stu-id="f2846-317">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f2846-318">Este paso es opcional, pero recomendado.</span><span class="sxs-lookup"><span data-stu-id="f2846-318">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="f2846-319">Antes de importar un edificio nuevo ya debería tener un BuildingKey predefinido identificado.</span><span class="sxs-lookup"><span data-stu-id="f2846-319">Before you Import a new building you should already have a predefined BuildingKey identified.</span></span> <span data-ttu-id="f2846-320">Para ello, ejecute el comando "Seleccionar MAX(BuildingKey) de CqdBuilding" SQL para identificar el valor actual y agregar 1 al resultado.</span><span class="sxs-lookup"><span data-stu-id="f2846-320">To do that, issue the "SELECT MAX(BuildingKey) FROM CqdBuilding" SQL command to identify the current value and add 1 to the result.</span></span>
  
 <span data-ttu-id="f2846-321">**Sintaxis de SQL de ejemplo**</span><span class="sxs-lookup"><span data-stu-id="f2846-321">**Sample SQL Syntax**</span></span>
  
```
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

<span data-ttu-id="f2846-322">El BuildingKey, nombredeedificio, BuildingShortName, OwnershipTypeId, se requieren los parámetros BuildingTypeId, los otros parámetros son opcionales.</span><span class="sxs-lookup"><span data-stu-id="f2846-322">The BuildingKey, BuildingName, BuildingShortName, OwnershipTypeId, BuildingTypeId parameters are required, the other parameters are optional.</span></span>
  
### <a name="import-subnets"></a><span data-ttu-id="f2846-323">Importar subredes</span><span class="sxs-lookup"><span data-stu-id="f2846-323">Import Subnets</span></span>

<span data-ttu-id="f2846-324">Importación de edificios permite obtener creación de conocimientos específicos (llamadas deficientes por edificio en WiFi o por cable, etcetera.).</span><span class="sxs-lookup"><span data-stu-id="f2846-324">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f2846-325">Este paso es opcional, pero recomendado.</span><span class="sxs-lookup"><span data-stu-id="f2846-325">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="f2846-326">Importar subredes y asignarlos a los edificios importados en el último paso.</span><span class="sxs-lookup"><span data-stu-id="f2846-326">Import Subnets and map them to the Buildings imported in the last step.</span></span> <span data-ttu-id="f2846-327">Si ha decidido no llenar NetworkName, asegúrese de que cada entrada en esta tabla utiliza un NetworkNameID de 0.</span><span class="sxs-lookup"><span data-stu-id="f2846-327">If you decided not to populate NetworkName, ensure each entry in this table uses a NetworkNameID of 0.</span></span>
  
 <span data-ttu-id="f2846-328">**Sintaxis de SQL de ejemplo**</span><span class="sxs-lookup"><span data-stu-id="f2846-328">**Sample SQL Syntax**</span></span>
  
```
INSERT INTO [dbo].[CqdNetwork] 
([Network]
,[NetworkNameID]
,[BuildingKey]
,[UpdatedDate]
)

VALUES
 ('172.16.254.0',0,1,'2015-11-11')
```

<span data-ttu-id="f2846-329">La red y se requieren parámetros de UpdatedDate, los otros parámetros son opcionales.</span><span class="sxs-lookup"><span data-stu-id="f2846-329">The Network, and UpdatedDate parameters are required, the other parameters are optional.</span></span>
  
### <a name="optional-bssid"></a><span data-ttu-id="f2846-330">Opcional: BSSID</span><span class="sxs-lookup"><span data-stu-id="f2846-330">Optional: BSSID</span></span>

<span data-ttu-id="f2846-331">Rellenar información de BSSID proporciona correlación de secuencia WiFi adicional por el regulador o el radio.</span><span class="sxs-lookup"><span data-stu-id="f2846-331">Populating BSSID information gives you additional WiFi stream correlation by controller or radio.</span></span> <span data-ttu-id="f2846-332">Se trata además de filtrar por edificio o subred.</span><span class="sxs-lookup"><span data-stu-id="f2846-332">This is in addition to filtering by building or subnet.</span></span> 
  
 <span data-ttu-id="f2846-333">**Sintaxis de SQL de ejemplo**</span><span class="sxs-lookup"><span data-stu-id="f2846-333">**Sample SQL Syntax**</span></span>
  
```
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

<span data-ttu-id="f2846-334">**Detalles de CqdBssidTable**</span><span class="sxs-lookup"><span data-stu-id="f2846-334">**CqdBssidTable Details**</span></span>

|<span data-ttu-id="f2846-335">**Como se muestra en CQD**</span><span class="sxs-lookup"><span data-stu-id="f2846-335">**As shown in CQD**</span></span>|<span data-ttu-id="f2846-336">**Tabla CQDBssid**</span><span class="sxs-lookup"><span data-stu-id="f2846-336">**CQDBssid Table**</span></span>|<span data-ttu-id="f2846-337">**Entradas de ejemplo**</span><span class="sxs-lookup"><span data-stu-id="f2846-337">**Example inputs**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f2846-338">AP NName</span><span class="sxs-lookup"><span data-stu-id="f2846-338">Ap NName</span></span>  <br/> |<span data-ttu-id="f2846-339">PA</span><span class="sxs-lookup"><span data-stu-id="f2846-339">AP</span></span>  <br/> |<span data-ttu-id="f2846-340">AP1</span><span class="sxs-lookup"><span data-stu-id="f2846-340">AP1</span></span>  <br/> |
|<span data-ttu-id="f2846-341">BBssid</span><span class="sxs-lookup"><span data-stu-id="f2846-341">BBssid</span></span>  <br/> |<span data-ttu-id="f2846-342">BSS</span><span class="sxs-lookup"><span data-stu-id="f2846-342">BSS</span></span>  <br/> |<span data-ttu-id="f2846-343">00-00-00-00-00-00 (debe utilizar el formato delimitado)</span><span class="sxs-lookup"><span data-stu-id="f2846-343">00-00-00-00-00-00 (you must use the delimited fformat)</span></span>  <br/> |
|<span data-ttu-id="f2846-344">Controlador</span><span class="sxs-lookup"><span data-stu-id="f2846-344">Controller</span></span>  <br/> |<span data-ttu-id="f2846-345">Building</span><span class="sxs-lookup"><span data-stu-id="f2846-345">Building</span></span>  <br/> |<span data-ttu-id="f2846-346">Aruba PA 7</span><span class="sxs-lookup"><span data-stu-id="f2846-346">Aruba AP 7</span></span>  <br/> |
|<span data-ttu-id="f2846-347">Dispositivo</span><span class="sxs-lookup"><span data-stu-id="f2846-347">Device</span></span>  <br/> |<span data-ttu-id="f2846-348">ess</span><span class="sxs-lookup"><span data-stu-id="f2846-348">ess</span></span>  <br/> |<span data-ttu-id="f2846-349">Controlador1</span><span class="sxs-lookup"><span data-stu-id="f2846-349">Controller1</span></span>  <br/> |
|<span data-ttu-id="f2846-350">Radio</span><span class="sxs-lookup"><span data-stu-id="f2846-350">Radio</span></span>  <br/> |<span data-ttu-id="f2846-351">phy</span><span class="sxs-lookup"><span data-stu-id="f2846-351">phy</span></span>  <br/> |<span data-ttu-id="f2846-352">BGN</span><span class="sxs-lookup"><span data-stu-id="f2846-352">bgn</span></span>  <br/> |
   
### <a name="processing-the-imported-data"></a><span data-ttu-id="f2846-353">Procesamiento de los datos importados</span><span class="sxs-lookup"><span data-stu-id="f2846-353">Processing the imported data</span></span>

<span data-ttu-id="f2846-354">De forma predeterminada, después de importar datos de construcción/red se aplicarán sólo a los registros generados después de que el punto en el tiempo.</span><span class="sxs-lookup"><span data-stu-id="f2846-354">By default, after you import building/network data it will only apply to records generated after that point in time.</span></span> 
  
<span data-ttu-id="f2846-355">Para etiquetar todos los registros anteriores con estos nuevos datos, debe ejecutar el procedimiento almacenado de CqdUpdateBuilding como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="f2846-355">To tag all the previous records with this new data, you will need to run the CqdUpdateBuilding stored procedure as shown below:</span></span> 
  
<span data-ttu-id="f2846-356">Dar la fecha de su primer registro (identificar que con el comando Seleccionar MIN(StartTime) de SQL de CqdPartitionedStreamView), un EndDate del mañana, NULL para los dos últimos valores.</span><span class="sxs-lookup"><span data-stu-id="f2846-356">Give it the date of your first record( identify that using the Select MIN(StartTime) FROM CqdPartitionedStreamView SQL command ), an EndDate of tomorrow, then NULL for the last two values.</span></span>
  
<span data-ttu-id="f2846-357">Una vez que los datos están asociados con los datos de la secuencia, el cubo de SSIS debe volver a procesar todos los registros.</span><span class="sxs-lookup"><span data-stu-id="f2846-357">Once the data is associated with stream data, the SSIS Cube needs to reprocess all records.</span></span> <span data-ttu-id="f2846-358">Esto aplica también cuando masiva agregar datos BSSID-ISP.</span><span class="sxs-lookup"><span data-stu-id="f2846-358">This also applies when bulk adding BSSID/ISP data.</span></span> <span data-ttu-id="f2846-359">Asegúrese de que está seleccionado "Proceso completo".</span><span class="sxs-lookup"><span data-stu-id="f2846-359">Ensure that "Process Full" is selected.</span></span>
  

