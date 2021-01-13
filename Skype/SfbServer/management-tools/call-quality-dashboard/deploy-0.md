---
title: Implementar el panel de calidad de llamadas para Skype Empresarial Server
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
description: 'Resumen: obtenga información sobre el proceso de implementación del Panel de calidad de llamadas. El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: 797288428530a055987d8b0a8e1ebf6a9e8b9dcd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832720"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server"></a><span data-ttu-id="a39a6-104">Implementar el panel de calidad de llamadas para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="a39a6-104">Deploy Call Quality Dashboard for Skype for Business Server</span></span>
 
<span data-ttu-id="a39a6-105">**Resumen:** Obtenga información sobre el proceso de implementación del Panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="a39a6-105">**Summary:** Learn about the deployment process for Call Quality Dashboard.</span></span> <span data-ttu-id="a39a6-106">El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="a39a6-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
## <a name="deployment-overview"></a><span data-ttu-id="a39a6-107">Vista general de implementación</span><span class="sxs-lookup"><span data-stu-id="a39a6-107">Deployment Overview</span></span>

<span data-ttu-id="a39a6-108">El Panel de calidad de llamadas (CQD) consta de tres componentes principales:</span><span class="sxs-lookup"><span data-stu-id="a39a6-108">Call Quality Dashboard (CQD) consists of three major components:</span></span>
  
- <span data-ttu-id="a39a6-109">**Base de datos** de archivo, donde se replican y almacenan los datos de calidad de la experiencia (QoE).</span><span class="sxs-lookup"><span data-stu-id="a39a6-109">**Archive Database**, where the Quality of Experience (QoE) data is replicated and stored.</span></span>
    
- <span data-ttu-id="a39a6-110">**Cubo,** donde los datos de la base de datos de archivo de QoE se agregan para un acceso optimizado y rápido.</span><span class="sxs-lookup"><span data-stu-id="a39a6-110">**Cube**, where data from QoE Archive database is aggregated for optimized and fast access.</span></span>
    
- <span data-ttu-id="a39a6-111">**Portal,** donde los usuarios pueden consultar y visualizar fácilmente los datos de QoE.</span><span class="sxs-lookup"><span data-stu-id="a39a6-111">**Portal**, where users can easily query and visualize QoE data.</span></span>
    
![Componentes de CQD](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
<span data-ttu-id="a39a6-113">El proceso de instalación de QoE Archive implica la creación de la base de datos de archivo de QoE, la implementación de un procedimiento almacenado de SQL Server que moverá los datos de la base de datos métricas de QoE de origen a la base de datos de archivo de QoE y la configuración del trabajo del agente de SQL Server para ejecutar el procedimiento almacenado a intervalos regulares.</span><span class="sxs-lookup"><span data-stu-id="a39a6-113">The setup process for QoE Archive involves creating the QoE Archive database, deploying a SQL Server stored procedure that will move the data from the source QoE Metrics database into QoE Archive database, and setting up the SQL Server Agent job to execute the stored procedure at a regular interval.</span></span> 
  
<span data-ttu-id="a39a6-114">La implementación de cubos obtiene información del usuario sobre dónde se encuentra el archivo qoE, implementa el cubo y configura un trabajo de agente de SQL Server normal que actualizará el cubo a intervalos regulares.</span><span class="sxs-lookup"><span data-stu-id="a39a6-114">Cube deployment gets information from the user on where the QoE Archive is located, deploys the cube, and sets up a regular SQL Server agent job that will refresh the cube at a regular interval.</span></span>
  
<span data-ttu-id="a39a6-115">La instalación del portal crea una base de datos de repositorio que almacena la asignación de usuarios de CQD a los informes o consultas de cada usuario.</span><span class="sxs-lookup"><span data-stu-id="a39a6-115">Portal install creates a Repository database that stores the mapping of CQD users to each user's reports/queries.</span></span> <span data-ttu-id="a39a6-116">A continuación, configura una aplicación web de IIS que es el panel donde los usuarios pueden ver un conjunto predefinido de informes, así como personalizar y crear sus propias consultas para visualizar los datos del cubo.</span><span class="sxs-lookup"><span data-stu-id="a39a6-116">It then sets up an IIS web application which is the dashboard where users can see a pre-defined set of reports as well as customize and create their own queries to visualize data from the cube.</span></span> <span data-ttu-id="a39a6-117">La instalación del portal crea dos aplicaciones web adicionales que exponen las API para que los usuarios accedan mediante programación al repositorio y al cubo.</span><span class="sxs-lookup"><span data-stu-id="a39a6-117">The portal install creates two additional web applications that exposes APIs for users to programmatically access the repository and the cube.</span></span> <span data-ttu-id="a39a6-118">(El panel también usa estas API internamente).</span><span class="sxs-lookup"><span data-stu-id="a39a6-118">(These APIs are used internally by the dashboard as well.)</span></span>
  

|<span data-ttu-id="a39a6-119">**Fase**</span><span class="sxs-lookup"><span data-stu-id="a39a6-119">**Phase**</span></span>|<span data-ttu-id="a39a6-120">**Pasos**</span><span class="sxs-lookup"><span data-stu-id="a39a6-120">**Steps**</span></span>|<span data-ttu-id="a39a6-121">**Roles y pertenencia a grupos**</span><span class="sxs-lookup"><span data-stu-id="a39a6-121">**Roles and group membership**</span></span>|<span data-ttu-id="a39a6-122">**Documentación**</span><span class="sxs-lookup"><span data-stu-id="a39a6-122">**Documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a39a6-123">Instalar hardware y software de requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="a39a6-123">Install prerequisite hardware and software.</span></span>  <br/> |<span data-ttu-id="a39a6-124">Decide la configuración del CQD y elige una SQL Server desde la que realizar la instalación.</span><span class="sxs-lookup"><span data-stu-id="a39a6-124">Decide on the CQD configuration, and choose a SQL Server from which to perform the install.</span></span>  <br/> |<span data-ttu-id="a39a6-125">Usuario de dominio que es miembro del grupo de administradores locales.</span><span class="sxs-lookup"><span data-stu-id="a39a6-125">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="a39a6-126">Sección "Requisitos previos a la instalación" en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="a39a6-126">"Pre-install Requirements" section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="a39a6-127">Instale el CQD.</span><span class="sxs-lookup"><span data-stu-id="a39a6-127">Install CQD.</span></span>  <br/> |<span data-ttu-id="a39a6-128">Ejecute el MSI después del documento de implementación.</span><span class="sxs-lookup"><span data-stu-id="a39a6-128">Run the MSI following the deployment document.</span></span>  <br/> |<span data-ttu-id="a39a6-129">Para realizar la instalación, la cuenta de instalación debe ser un usuario de dominio que sea miembro del grupo de administradores locales y tenga acceso de lectura a la base de datos de métricas de QoE en el servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="a39a6-129">To perform the setup, the installing account must be a domain user who is a member of the local administrators group and have read access to QoE Metrics database on the Monitoring Server.</span></span>  <br/> |<span data-ttu-id="a39a6-130">Secciones "Cuentas y pasos de implementación" en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="a39a6-130">"Accounts and Deployment Steps" sections in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="a39a6-131">Conceder acceso de usuario.</span><span class="sxs-lookup"><span data-stu-id="a39a6-131">Grant user access.</span></span>  <br/> |<span data-ttu-id="a39a6-132">Para administrar la autorización de usuario en el portal, se recomienda usar la autorización de url, que se introdujo en IIS 7.0.</span><span class="sxs-lookup"><span data-stu-id="a39a6-132">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="a39a6-133">Para obtener más información, vea Descripción de la autorización de direcciones [URL de IIS 7.0.](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization)</span><span class="sxs-lookup"><span data-stu-id="a39a6-133">For more information, see [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>  <br/> |<span data-ttu-id="a39a6-134">Usuario de dominio que es miembro del grupo de administradores locales.</span><span class="sxs-lookup"><span data-stu-id="a39a6-134">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="a39a6-135">Administración del acceso de usuarios para la sección Portal en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="a39a6-135">Managing User Access for the Portal section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="a39a6-136">Opcional: proporcionar información de asignación de subred.</span><span class="sxs-lookup"><span data-stu-id="a39a6-136">Optional: Provide subnet mapping information.</span></span>  <br/> |<span data-ttu-id="a39a6-137">Rellene las tablas de asignación de red y creación en la base de datos de archivo QoE.</span><span class="sxs-lookup"><span data-stu-id="a39a6-137">Populate network and building mapping tables in QoE Archive database.</span></span>  <br/> |<span data-ttu-id="a39a6-138">Una cuenta con acceso de escritura a la base de datos de archivo QoE.</span><span class="sxs-lookup"><span data-stu-id="a39a6-138">An account with write access to the QoE Archive database.</span></span>  <br/> |<span data-ttu-id="a39a6-139">Sección "Suministro de información de subred" en la documentación del usuario.</span><span class="sxs-lookup"><span data-stu-id="a39a6-139">"Supplying Subnet Information" section in the user documentation.</span></span>  <br/> |
   


<span data-ttu-id="a39a6-140">La implementación del Panel de calidad de llamadas implica la configuración de la infraestructura y la instalación del software.</span><span class="sxs-lookup"><span data-stu-id="a39a6-140">Deployment of Call Quality Dashboard involves setting up the infrastructure and installing the software.</span></span> <span data-ttu-id="a39a6-141">El siguiente procedimiento describe el proceso.</span><span class="sxs-lookup"><span data-stu-id="a39a6-141">The following procedure outlines the process.</span></span>
  
## <a name="deployment-steps"></a><span data-ttu-id="a39a6-142">Pasos de implementación</span><span class="sxs-lookup"><span data-stu-id="a39a6-142">Deployment Steps</span></span>

1. <span data-ttu-id="a39a6-143">Copia el CallQualityDashboard.msi en el equipo donde se va a instalar el componente de base de datos de archivo del CQD (este es el equipo que SQL Server instalado).</span><span class="sxs-lookup"><span data-stu-id="a39a6-143">Copy the CallQualityDashboard.msi to the machine where the archive database component of CQD is to be installed (this is the machine that has SQL Server installed).</span></span> 
    
2. <span data-ttu-id="a39a6-144">Ejecute el MSI (Windows pedirá que se ejecute con privilegios de administrador, así que).</span><span class="sxs-lookup"><span data-stu-id="a39a6-144">Execute the MSI (Windows will prompt to run with administrator privilege, do so).</span></span> 
    
3. <span data-ttu-id="a39a6-145">Acepta el CLUF.</span><span class="sxs-lookup"><span data-stu-id="a39a6-145">Accept the EULA.</span></span>
    
4. <span data-ttu-id="a39a6-146">Seleccione la carpeta de destino donde se ubicarán los archivos relacionados con los componentes del Panel de calidad de llamadas o acepte la ubicación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a39a6-146">Select the destination folder where files related to Call Quality Dashboard components will be located or accept the default location.</span></span>
    
5. <span data-ttu-id="a39a6-147">Seleccione todas las características.</span><span class="sxs-lookup"><span data-stu-id="a39a6-147">Select all features.</span></span>
    
6. <span data-ttu-id="a39a6-148">En la página Configuración de archivo de QoE, proporcione la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="a39a6-148">At the QoE Archive Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="a39a6-149">**Métricas de QoE SQL Server:** SQL Server de instancia para el lugar donde se encuentra la base de datos de métricas de QoE (este será el origen de datos).</span><span class="sxs-lookup"><span data-stu-id="a39a6-149">**QoE Metrics SQL Server:** SQL Server instance name for where the QoE Metrics DB is located (this will be the data source).</span></span>
    
   - <span data-ttu-id="a39a6-150">**Nombre de archivo SQL Server QoE:** Este campo es de solo lectura y se ha corregido con el nombre de dominio completo del equipo local.</span><span class="sxs-lookup"><span data-stu-id="a39a6-150">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="a39a6-151">La base de datos de archivo solo se puede instalar en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="a39a6-151">Archive DB can be installed only on the local machine.</span></span>
    
   - <span data-ttu-id="a39a6-152">**Instancia de archivo SQL Server QoE:** Un nombre SQL Server instancia local para el lugar donde se va a crear la base de datos de archivo.</span><span class="sxs-lookup"><span data-stu-id="a39a6-152">**QoE Archive SQL Server Instance:** A local SQL Server instance name for where the Archive DB is to be created.</span></span> <span data-ttu-id="a39a6-153">Para usar una instancia SQL Server predeterminada, deje este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="a39a6-153">To use a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="a39a6-154">Para usar una instancia SQL Server nombre, especifique el nombre de la instancia (por ejemplo, el nombre después de " \" ).</span><span class="sxs-lookup"><span data-stu-id="a39a6-154">To use a named SQL Server instance, specify the instance name (e.g. the name after the "\").</span></span>
    
   - <span data-ttu-id="a39a6-155">**Base de datos de archivo QoE:** De forma predeterminada, esta opción se establece en "Crear nueva base de datos".</span><span class="sxs-lookup"><span data-stu-id="a39a6-155">**QoE Archive Database:** By default, this option is set to "Create new database".</span></span> <span data-ttu-id="a39a6-156">Dado que no se admite la actualización de la base de datos de archivo, la única circunstancia en la que se puede usar la opción "Usar base de datos existente" es si la base de datos de archivo existente tiene el mismo esquema que la compilación que se va a instalar.</span><span class="sxs-lookup"><span data-stu-id="a39a6-156">Since Archive DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Archive database has the same schema as the build to be installed.</span></span>
    
   - <span data-ttu-id="a39a6-157">**Directorio de archivos de base de datos:** Ruta de acceso donde se deben colocar los archivos de base de datos (.mdf y .ldf) para la base de datos de archivo.</span><span class="sxs-lookup"><span data-stu-id="a39a6-157">**Database File Directory:** Path to where the database files (.mdf and .ldf) for the Archive DB should be placed.</span></span> <span data-ttu-id="a39a6-158">Debe estar en una unidad (HDD2 en la configuración de hardware recomendada) independiente del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="a39a6-158">This should be on a drive (HDD2 in the recommended hardware configuration) separate from the OS.</span></span> <span data-ttu-id="a39a6-159">Tenga en cuenta que, dado que los nombres de archivo se han corregido en la instalación, para evitar posibles conflictos, se recomienda usar un directorio en blanco sin archivos.</span><span class="sxs-lookup"><span data-stu-id="a39a6-159">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="a39a6-160">**Use varias particiones:** El valor predeterminado se establece en "Partición múltiple", que requiere business intelligence edition o Enterprise edition de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a39a6-160">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="a39a6-161">Para standard edition, seleccione la opción "Partición única".</span><span class="sxs-lookup"><span data-stu-id="a39a6-161">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="a39a6-162">Tenga en cuenta que el rendimiento del procesamiento del cubo se puede ver afectado si se usa una partición única.</span><span class="sxs-lookup"><span data-stu-id="a39a6-162">Note that cube processing performance may be impacted if Single Partition is used.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="a39a6-163">La selección de la opción Usar varias particiones no se puede cambiar una vez completada la instalación.</span><span class="sxs-lookup"><span data-stu-id="a39a6-163">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="a39a6-164">Para cambiarla, la característica Cubo primero debe desinstalarse y volver a instalarse con la opción "Cambiar" en el Panel de control.</span><span class="sxs-lookup"><span data-stu-id="a39a6-164">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span> 
  
   - <span data-ttu-id="a39a6-165">**Directorio de archivos de partición:** Ruta de acceso a la que se deben colocar las particiones de la base de datos de archivo QoE.</span><span class="sxs-lookup"><span data-stu-id="a39a6-165">**Partition File Directory:** Path to where the partitions for the QoE Archive database should be placed.</span></span> <span data-ttu-id="a39a6-166">Debe estar en una unidad (HDD3 en la configuración de hardware recomendada) independiente de la unidad del sistema operativo y de SQL de archivos de registro de base de datos.</span><span class="sxs-lookup"><span data-stu-id="a39a6-166">This should be on a drive (HDD3 in the recommended hardware configuration) separate from the OS drive and SQL database log files drive.</span></span> <span data-ttu-id="a39a6-167">Tenga en cuenta que, dado que los nombres de archivo se han corregido en la instalación, para evitar posibles conflictos, se recomienda usar un directorio en blanco sin archivos.</span><span class="sxs-lookup"><span data-stu-id="a39a6-167">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="a39a6-168">**SQL de trabajo del agente de cliente: nombre de usuario &amp; Contraseña:** nombre de cuenta de servicio de dominio y contraseña (enmascarado) que se usarán para ejecutar el paso "Datos de archivo qoE" del trabajo del agente de SQL Server (que ejecutará el procedimiento almacenado para capturar datos de la base de datos de métricas de QoE en la base de datos de archivo, por lo que esta cuenta debe tener acceso de lectura a la base de datos de métricas de QoE, tal como se indica en la sección Cuentas.</span><span class="sxs-lookup"><span data-stu-id="a39a6-168">**SQL Agent Job User - User Name &amp; Password:** Domain service account name and password (masked) that will be used to run the "QoE Archive Data" step of the SQL Server Agent job (which will run the stored procedure to fetch data from QoE Metrics DB into Archive DB, so this account must have read access to QoE Metrics DB, as indicated under Accounts section.</span></span> <span data-ttu-id="a39a6-169">Esta cuenta también debe tener un inicio de sesión en el archivo de QoE SQL Server instancia).</span><span class="sxs-lookup"><span data-stu-id="a39a6-169">This account also needs to have a login in the QoE Archive SQL Server Instance).</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="a39a6-170">La cuenta en la que se ejecuta la instancia de SQL Server, como NT SERVICE\MSSQLSERVER, debe tener acceso o permiso a los directorios indicados anteriormente para que la instalación se ejecute correctamente.</span><span class="sxs-lookup"><span data-stu-id="a39a6-170">The account that the SQL Server instance is running under, such as NT SERVICE\MSSQLSERVER, must have access/permission to the directories given above for the installation to succeed.</span></span> <span data-ttu-id="a39a6-171">Para obtener más información, vea [Configurar permisos del sistema de archivos para el acceso al motor de base de datos](https://msdn.microsoft.com/library/jj219062%28v=sql.110%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a39a6-171">For details, see [Configure File System Permissions for Database Engine Access](https://msdn.microsoft.com/library/jj219062%28v=sql.110%29.aspx)</span></span>
  
7. <span data-ttu-id="a39a6-172">Al hacer clic a continuación, el instalador realizará comprobaciones de requisitos previos e informará si se han detectado problemas.</span><span class="sxs-lookup"><span data-stu-id="a39a6-172">Upon clicking next, the installer will perform pre-requisite checks and report if any issues are encountered.</span></span> <span data-ttu-id="a39a6-173">Cuando se pasen todas las comprobaciones de requisitos previos, el instalador irá a la página Configuración del cubo.</span><span class="sxs-lookup"><span data-stu-id="a39a6-173">When all pre-requisite checks pass, the installer will go to the Cube Configuration page.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="a39a6-174">Si el instalador muestra un mensaje de advertencia de que el servicio de agente de SQL Server para la instancia de qoE Archive SQL Server no se está ejecutando actualmente, la instalación puede continuar, pero después de la instalación asegúrese de que el servicio de agente de SQL se está ejecutando y establezca el tipo de inicio en Automático para que se ejecute el trabajo programado.</span><span class="sxs-lookup"><span data-stu-id="a39a6-174">If the installer shows a warning message that the SQL Server Agent service for the QoE Archive SQL Server instance is currently not running, installation can proceed, but post installation please make sure that SQL Agent service is running and set the Startup type to Automatic so that the scheduled Job runs.</span></span> 
  
8. <span data-ttu-id="a39a6-175">En la página Configuración del cubo, proporcione la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="a39a6-175">At Cube Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="a39a6-176">**Nombre de archivo SQL Server QoE:** Este campo es de solo lectura y se ha corregido con el nombre de dominio completo del equipo local.</span><span class="sxs-lookup"><span data-stu-id="a39a6-176">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="a39a6-177">El cubo solo se puede instalar desde el equipo que tiene una base de datos de archivo qoE (nota.</span><span class="sxs-lookup"><span data-stu-id="a39a6-177">Cube can be installed only from the machine that has QoE Archive database (Note.</span></span> <span data-ttu-id="a39a6-178">El propio cubo se puede instalar en un equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="a39a6-178">Cube itself may be installed on a remote machine.</span></span> <span data-ttu-id="a39a6-179">Consulta a continuación)</span><span class="sxs-lookup"><span data-stu-id="a39a6-179">See below)</span></span>
    
   - <span data-ttu-id="a39a6-180">**Instancia de archivo SQL Server QoE:** SQL Server de instancia para el lugar donde se encuentra la base de datos de archivo de QoE.</span><span class="sxs-lookup"><span data-stu-id="a39a6-180">**QoE Archive SQL Server Instance:** SQL Server instance name for where the QoE Archive DB is located.</span></span> <span data-ttu-id="a39a6-181">Para especificar una instancia SQL Server predeterminada, deje este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="a39a6-181">To specify a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="a39a6-182">Para especificar una instancia SQL Server nombre, escriba el nombre de la instancia (por ejemplo, el nombre después de " \" ).</span><span class="sxs-lookup"><span data-stu-id="a39a6-182">To specify a named SQL Server instance, enter the instance name (e.g. the name after the "\").</span></span> <span data-ttu-id="a39a6-183">Si se seleccionó el componente de archivo de QoE para la instalación, este campo se rellenará previamente con el valor proporcionado en la página Configuración de archivo de QoE.</span><span class="sxs-lookup"><span data-stu-id="a39a6-183">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
   - <span data-ttu-id="a39a6-184">**Cube Analysis Server:** SQL Server de instancia de Analysis Service para el lugar donde se va a crear el cubo.</span><span class="sxs-lookup"><span data-stu-id="a39a6-184">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is to be created.</span></span> <span data-ttu-id="a39a6-185">Puede ser un equipo diferente, pero el usuario que instala debe ser miembro de los administradores de servidor de la instancia de SQL Server Analysis Service de destino.</span><span class="sxs-lookup"><span data-stu-id="a39a6-185">This can be a different machine but the installing user has to be a member of Server administrators of the target SQL Server Analysis Service instance.</span></span>
    
     > [!NOTE]
     >  <span data-ttu-id="a39a6-186">Para obtener más información acerca de la configuración de permisos de administrador de Analysis Services Server, vea Concesión de permisos de administrador [del servidor (Analysis Services)](https://msdn.microsoft.com/library/ms174561.aspx)</span><span class="sxs-lookup"><span data-stu-id="a39a6-186">For more information about configuring Analysis Services Server Administrator Permissions, see [Grant Server Administrator Permissions (Analysis Services)](https://msdn.microsoft.com/library/ms174561.aspx)</span></span>
  
   - <span data-ttu-id="a39a6-187">**Use varias particiones:** El valor predeterminado se establece en "Partición múltiple", que requiere business intelligence edition o Enterprise edition de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a39a6-187">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="a39a6-188">Para standard edition, seleccione la opción "Partición única".</span><span class="sxs-lookup"><span data-stu-id="a39a6-188">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="a39a6-189">Tenga en cuenta que el rendimiento del procesamiento del cubo se puede ver afectado si se usa una partición única.</span><span class="sxs-lookup"><span data-stu-id="a39a6-189">Note that cube processing performance may be impacted if Single Partition is used .</span></span>
    
     > [!NOTE]
     >  <span data-ttu-id="a39a6-190">La selección de la opción Usar varias particiones no se puede cambiar una vez completada la instalación.</span><span class="sxs-lookup"><span data-stu-id="a39a6-190">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="a39a6-191">Para cambiarla, la característica Cubo primero debe desinstalarse y volver a instalarse con la opción "Cambiar" en el Panel de control.</span><span class="sxs-lookup"><span data-stu-id="a39a6-191">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span>
  
   - <span data-ttu-id="a39a6-192">**Usuario del cubo: nombre de usuario &amp; Contraseña: nombre** de cuenta de servicio de dominio y contraseña (enmascarada) que desencadenarán el procesamiento del cubo.</span><span class="sxs-lookup"><span data-stu-id="a39a6-192">**Cube User - User Name &amp; Password:** Domain service account name and password (masked) that will trigger the cube processing.</span></span> <span data-ttu-id="a39a6-193">Si se seleccionó el componente archivo qoE para la instalación, este campo se rellenará previamente con el valor proporcionado en la página Configuración de archivo para el usuario de trabajo de agente de SQL, pero se recomienda especificar una cuenta de servicio de dominio diferente para que el programa de instalación pueda concederle el privilegio menos necesario.</span><span class="sxs-lookup"><span data-stu-id="a39a6-193">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the Archive Configuration page for the SQL Agent Job User, but we recommend specifying a different domain service account so that Setup can grant the least required privilege to it.</span></span>
    
9. <span data-ttu-id="a39a6-194">Al hacer clic en siguiente, se realizará otra ronda de validación y se mostrará cualquier problema.</span><span class="sxs-lookup"><span data-stu-id="a39a6-194">When clicking next, another round of validation will be performed and any issue will be reported.</span></span> <span data-ttu-id="a39a6-195">Una vez completada correctamente la validación, el instalador irá a la página Configuración del portal.</span><span class="sxs-lookup"><span data-stu-id="a39a6-195">Upon successful completion of the validation, the installer will go to the Portal Configuration page.</span></span> 
    
10. <span data-ttu-id="a39a6-196">En la página Configuración del portal, proporcione la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="a39a6-196">At Portal Configuration page, provide the following information:</span></span>
    
    - <span data-ttu-id="a39a6-197">**Archivos qoE SQL Server:** SQL Server de instancia para el lugar donde se encuentra la base de datos de archivo de QoE.</span><span class="sxs-lookup"><span data-stu-id="a39a6-197">**QoE Archive SQL Server:** SQL Server instance name for where the QoE Archive database is located.</span></span> <span data-ttu-id="a39a6-198">Tenga en cuenta que, a diferencia de la página Configuración de archivo de QoE y la página Configuración del cubo, el nombre de la máquina no es fijo y debe proporcionarse.</span><span class="sxs-lookup"><span data-stu-id="a39a6-198">Note that unlike the QoE Archive Configuration page and the Cube Configuration page, the machine name is not fixed and must be provided.</span></span> <span data-ttu-id="a39a6-199">Si se seleccionó el componente de archivo de QoE para la instalación, este campo se rellenará previamente con el valor proporcionado en la página Configuración de archivo de QoE.</span><span class="sxs-lookup"><span data-stu-id="a39a6-199">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
    - <span data-ttu-id="a39a6-200">**Cube Analysis Server:** SQL Server de instancia de Analysis Service para el lugar donde se encuentra el cubo.</span><span class="sxs-lookup"><span data-stu-id="a39a6-200">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is located.</span></span> <span data-ttu-id="a39a6-201">Si se seleccionó el componente Cubo para la instalación, este campo se rellenará previamente con el valor proporcionado en la página Configuración del cubo.</span><span class="sxs-lookup"><span data-stu-id="a39a6-201">If Cube component was selected for the install, this field will be pre-populated with the value provided on the Cube Configuration page.</span></span>
    
    - <span data-ttu-id="a39a6-202">**Repositorio SQL Server:** SQL Server de instancia donde se va a crear la base de datos repositorio.</span><span class="sxs-lookup"><span data-stu-id="a39a6-202">**Repository SQL Server:** SQL Server instance name where the Repository database is to be created.</span></span> <span data-ttu-id="a39a6-203">Si el nombre de instancia de SQL Server donde se encuentra la base de datos de qoE se ha proporcionado anteriormente en la instalación (en otros componentes), este campo se rellenará previamente con el nombre de instancia de base de datos de archivo de QoE SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a39a6-203">If the SQL Server instance name for where the QoE Archive database is located has been provided earlier in the setup (in other components), this field will be pre-populated with the QoE Archive DB SQL Server instance name.</span></span> <span data-ttu-id="a39a6-204">Puede ser cualquier instancia SQL Server de datos.</span><span class="sxs-lookup"><span data-stu-id="a39a6-204">This can be any SQL Server instance.</span></span>
    
    - <span data-ttu-id="a39a6-205">**Base de datos de repositorio:** De forma predeterminada, la opción se establece en "Crear nueva base de datos".</span><span class="sxs-lookup"><span data-stu-id="a39a6-205">**Repository Database:** By default the option is set to "Create new database".</span></span> <span data-ttu-id="a39a6-206">Dado que no se admite la actualización de la base de datos de repositorio, la única circunstancia en la que se puede usar la opción "Usar base de datos existente" es si la base de datos de repositorio existente tiene el mismo esquema que la compilación que se va a instalar.</span><span class="sxs-lookup"><span data-stu-id="a39a6-206">Since Repository DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Repository DB has the same schema as the build to be installed.</span></span>
    
    - <span data-ttu-id="a39a6-207">**Usuario del grupo de aplicaciones de IIS: nombre de usuario &amp; Contraseña: la** cuenta en la que debe ejecutarse el grupo de aplicaciones de IIS.</span><span class="sxs-lookup"><span data-stu-id="a39a6-207">**IIS App Pool User - User Name &amp; Password:** The account that the IIS application pool should execute under.</span></span> <span data-ttu-id="a39a6-208">Los campos Nombre de usuario y Contraseña aparecerán atenuados si se seleccionan cuentas integradas del sistema.</span><span class="sxs-lookup"><span data-stu-id="a39a6-208">The User Name and Password fields will be grayed out if built-in system accounts are selected.</span></span> <span data-ttu-id="a39a6-209">Estos campos solo se habilitarán si se selecciona "Otros" en el cuadro desplegable para que el usuario pueda escribir la información de la cuenta de servicio de dominio.</span><span class="sxs-lookup"><span data-stu-id="a39a6-209">These fields will only be enabled if "Other" is selected from the drop down box so the user can enter the domain service account information.</span></span>
    
11. <span data-ttu-id="a39a6-210">Al hacer clic en siguiente, se realizará la ronda final de validación para garantizar que las instancias de SQL Server son accesibles con las credenciales proporcionadas y que IIS está disponible en el equipo.</span><span class="sxs-lookup"><span data-stu-id="a39a6-210">When clicking next, the final round of validation will be done to ensure that the SQL Server instances are accessible using the credentials provided and that IIS is available on the machine.</span></span> <span data-ttu-id="a39a6-211">Una vez completada correctamente la validación, el instalador continuará con la configuración.</span><span class="sxs-lookup"><span data-stu-id="a39a6-211">Upon successful completion of the validation, the installer will proceed with the setup.</span></span> 
    
<span data-ttu-id="a39a6-212">Cuando el instalador haya terminado, lo más probable es que el trabajo del agente de SQL Server esté en curso, realizando la carga inicial de los datos de QoE y el procesamiento del cubo.</span><span class="sxs-lookup"><span data-stu-id="a39a6-212">When the installer is done, most likely the SQL Server Agent job will be in progress, doing the initial load of the QoE data and the cube processing.</span></span> <span data-ttu-id="a39a6-213">Según la cantidad de datos de QoE, el portal no tendrá datos disponibles para su visualización todavía.</span><span class="sxs-lookup"><span data-stu-id="a39a6-213">Depending on the amount of data in QoE, the portal will not have data available for viewing yet.</span></span> <span data-ttu-id="a39a6-214">Para comprobar el estado de la carga de datos y el procesamiento del cubo, vaya a  `http://<machinename>/CQD/#/Health` .</span><span class="sxs-lookup"><span data-stu-id="a39a6-214">To check on the status of the data load and cube processing, go to  `http://<machinename>/CQD/#/Health`.</span></span> 
> [!NOTE]
> <span data-ttu-id="a39a6-215">Tenga en cuenta que la dirección URL para comprobar el estado del procesamiento del cubo de descarga distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="a39a6-215">Note that the URL for checking the status of the download cube processing is case sensitive.</span></span> <span data-ttu-id="a39a6-216">Si escribe "health", la dirección URL no funcionará.</span><span class="sxs-lookup"><span data-stu-id="a39a6-216">If you enter 'health' the URL will not work.</span></span> <span data-ttu-id="a39a6-217">Debe escribir "Health" al final de la dirección URL con una H mayúscula.</span><span class="sxs-lookup"><span data-stu-id="a39a6-217">You must enter 'Health' at the end of the URL with a capital H.</span></span> 
  
<span data-ttu-id="a39a6-218">Si el modo de depuración está habilitado, se mostrarán mensajes de registro detallados.</span><span class="sxs-lookup"><span data-stu-id="a39a6-218">Detailed log messages will be shown if debug mode is enabled.</span></span> <span data-ttu-id="a39a6-219">Para habilitar el modo de depuración, vaya a **%SYSTEMDRIVE%\Archivos de programa\Skype Empresarial 2015 CQD\QoEDataService\web.config** y actualice la siguiente línea para que el valor se establezca en **True:**</span><span class="sxs-lookup"><span data-stu-id="a39a6-219">To enable debug mode, go to **%SYSTEMDRIVE%\Program Files\Skype For Business 2015 CQD\QoEDataService\web.config**, and update the following line so the value is set to **True**:</span></span>

```xml
<add key="QoEDataLib.DebugMode" value="True" /> 
```

<span data-ttu-id="a39a6-220">Se puede acceder a la página del portal principal a través  `http://<machinename>/CQD` de .</span><span class="sxs-lookup"><span data-stu-id="a39a6-220">The main portal page is accessible via  `http://<machinename>/CQD`.</span></span> 
## <a name="managing-user-access-for-the-portal"></a><span data-ttu-id="a39a6-221">Administración del acceso de usuarios para el portal</span><span class="sxs-lookup"><span data-stu-id="a39a6-221">Managing User Access for the Portal</span></span>

<span data-ttu-id="a39a6-222">Para administrar la autorización de usuario en el portal, se recomienda usar la autorización de url, que se introdujo en IIS 7.0.</span><span class="sxs-lookup"><span data-stu-id="a39a6-222">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="a39a6-223">Para obtener más información sobre la seguridad de IIS, vea Descripción de la autorización de direcciones URL de [IIS 7.0.](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization)</span><span class="sxs-lookup"><span data-stu-id="a39a6-223">For more information on IIS security, see [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>
  
<span data-ttu-id="a39a6-224">Cualquier sitio web o aplicación web hereda la autorización de dirección URL predeterminada configurada para todo IIS, que normalmente es "Permitir todos los usuarios".</span><span class="sxs-lookup"><span data-stu-id="a39a6-224">Any web site or web application inherit the default URL Authorization configured for the entire IIS, which is typically "Allow All Users".</span></span> <span data-ttu-id="a39a6-225">Si el acceso al Portal debe ser más restrictivo, los administradores pueden conceder acceso solo al grupo específico de usuarios editando las "Reglas de autorización".</span><span class="sxs-lookup"><span data-stu-id="a39a6-225">If access to the Portal needs to be more restrictive, then administrators can grant access to only the specific group of users by editing the "Authorization Rules".</span></span>
  
![Implementar calidad de llamadas: reglas de autorización en IIS](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> <span data-ttu-id="a39a6-227">El icono de reglas de autorización no debe confundirse con la "Autorización de .NET" en la sección ASP.NET, que es un mecanismo de autorización diferente.</span><span class="sxs-lookup"><span data-stu-id="a39a6-227">The Authorization Rules icon is not to be confused with the ".NET Authorization" under the ASP.NET section, which is a different authorization mechanism.</span></span> 
  
<span data-ttu-id="a39a6-228">En primer lugar, los administradores deben quitar la regla heredada "Permitir todos los usuarios".</span><span class="sxs-lookup"><span data-stu-id="a39a6-228">Administrators should first remove the inherited "Allow All Users" rule.</span></span> <span data-ttu-id="a39a6-229">Esto impide que los usuarios no autorizados accedan al Portal.</span><span class="sxs-lookup"><span data-stu-id="a39a6-229">This prevents any non-authorized users from accessing the Portal.</span></span>
  
![Implementar CQD](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
<span data-ttu-id="a39a6-231">A continuación, los administradores deben agregar nuevas reglas de permiso y conceder a usuarios específicos permiso para acceder al Portal.</span><span class="sxs-lookup"><span data-stu-id="a39a6-231">Next, administrators should add new Allow Rules and give specific users the permission to access the Portal.</span></span> <span data-ttu-id="a39a6-232">Se recomienda crear un grupo local denominado "CQDPortalUsers" para administrar los usuarios.</span><span class="sxs-lookup"><span data-stu-id="a39a6-232">It is recommended that a local Group called "CQDPortalUsers" be created to manage the users.</span></span>
  
![Implementar el panel de calidad de llamadas](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
<span data-ttu-id="a39a6-234">Los detalles de configuración se almacenan en el web.config ubicado en el directorio físico del portal.</span><span class="sxs-lookup"><span data-stu-id="a39a6-234">The configuration details are stored in the web.config located at the Portal's physical directory.</span></span>
  
```xml
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

<span data-ttu-id="a39a6-235">El siguiente paso es configurar el panel del CQD.</span><span class="sxs-lookup"><span data-stu-id="a39a6-235">The next step is to configure the dashboard of the CQD.</span></span> <span data-ttu-id="a39a6-236">Después de que IIS autentique a los usuarios, tendrán que tener permisos de archivo en el directorio CQD para tener acceso al contenido del portal web.</span><span class="sxs-lookup"><span data-stu-id="a39a6-236">After users are authenticated by IIS, they will have to have file permissions on the CQD directory in order to access the web portal content.</span></span> <span data-ttu-id="a39a6-237">Es posible cambiar las ACL a través de la pestaña de seguridad de las propiedades del directorio CQD para agregar usuarios o grupos individuales; sin embargo, el enfoque recomendado es dejar los permisos de archivo intactos.</span><span class="sxs-lookup"><span data-stu-id="a39a6-237">It is possible to change the ACLs through the security tab of the CQD directory properties to add individual users or groups; however the recommended approach is to leave the file permissions untouched.</span></span> <span data-ttu-id="a39a6-238">En su lugar, cambie la configuración de IIS para usar el proceso de trabajo de IIS para tener acceso al directorio CQD independientemente del usuario autenticado.</span><span class="sxs-lookup"><span data-stu-id="a39a6-238">Instead, change the IIS setting to use the IIS worker process to access the CQD directory no matter which user is authenticated.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="a39a6-239">Es importante cambiar solo esta configuración para la aplicación CQD y no para las dos aplicaciones api: QoEDataService y QoERepositoryService.</span><span class="sxs-lookup"><span data-stu-id="a39a6-239">It is important to only change this setting for the CQD application, and not for the two API applications: QoEDataService and QoERepositoryService.</span></span> 
  
## <a name="configuring-file-access-for-the-cqd-dashboard"></a><span data-ttu-id="a39a6-240">Configuración del acceso a archivos para el CQD (panel)</span><span class="sxs-lookup"><span data-stu-id="a39a6-240">Configuring File Access for the CQD (Dashboard)</span></span>

1. <span data-ttu-id="a39a6-241">Abra el Editor de configuración para CQD.</span><span class="sxs-lookup"><span data-stu-id="a39a6-241">Open the Configuration Editor for CQD.</span></span>
    
     ![Implementar el panel de calidad de llamadas](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. <span data-ttu-id="a39a6-243">En Sección, elija **system.webServer/serverRuntime**.</span><span class="sxs-lookup"><span data-stu-id="a39a6-243">Under Section, choose **system.webServer/serverRuntime**.</span></span>
    
     ![Implementar el panel de calidad de llamadas](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. <span data-ttu-id="a39a6-245">Cambie authenticatedUserOverride a **UseWorkerProcessUser**.</span><span class="sxs-lookup"><span data-stu-id="a39a6-245">Change authenticatedUserOverride to **UseWorkerProcessUser**.</span></span>
    
     ![Implementar panel de calidad de llamadas: Editor de configuración](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. <span data-ttu-id="a39a6-247">Haga **clic** en Aplicar en el lado derecho de la página.</span><span class="sxs-lookup"><span data-stu-id="a39a6-247">Click **Apply** on the right-hand side of the page.</span></span>
    
## <a name="known-issues"></a><span data-ttu-id="a39a6-248">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="a39a6-248">Known Issues</span></span>

### <a name="the-cqd-shows-no-data-after-deployment"></a><span data-ttu-id="a39a6-249">El CQD no muestra datos después de la implementación</span><span class="sxs-lookup"><span data-stu-id="a39a6-249">The CQD shows no data after deployment</span></span>

<span data-ttu-id="a39a6-250">Es posible que reciba el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="a39a6-250">You may receive the following error:</span></span>

<span data-ttu-id="a39a6-251">*No se pudo realizar la consulta mientras se ejecutaba en el cubo. Use el Editor de consultas para modificar la consulta y solucionar los problemas. Asegúrese también de que el cubo sea accesible.*</span><span class="sxs-lookup"><span data-stu-id="a39a6-251">*We couldn’t perform the query while running it on the Cube. Use the Query Editor to modify the query and fix any issues. Also make sure that the Cube is accessible.*</span></span>

<span data-ttu-id="a39a6-252">Esto significa que el cubo debe procesarse en SQL Server Analysis Services antes de usarse en el CQD.</span><span class="sxs-lookup"><span data-stu-id="a39a6-252">This means that the cube must be processed in SQL Server Analysis Services prior to being used in CQD.</span></span> <span data-ttu-id="a39a6-253">Puede resolver esto siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="a39a6-253">You can resolve this by following these steps:</span></span>

1. <span data-ttu-id="a39a6-254">Abra SQL Management Studio y seleccione **Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="a39a6-254">Open SQL Management Studio and select **Analysis Services**.</span></span>

2. <span data-ttu-id="a39a6-255">Expanda el **objeto QoECube,** seleccione **Métrica qoE,** haga clic con el botón secundario y, a continuación, **elija Examinar**.</span><span class="sxs-lookup"><span data-stu-id="a39a6-255">Expand the **QoECube** object, select **QoE Metric**, right-click, and then choose **Browse**.</span></span> 

    <span data-ttu-id="a39a6-256">Si devuelve un explorador vacío, el cubo aún no se ha realizado.</span><span class="sxs-lookup"><span data-stu-id="a39a6-256">If this returns empty browser, the cube hasn’t been proceed yet.</span></span>

3. <span data-ttu-id="a39a6-257">Haga clic con el **botón secundario en la métrica QoE** y elija **Proceso**.</span><span class="sxs-lookup"><span data-stu-id="a39a6-257">Right-click **QoE Metric** angain and choose **Process**.</span></span>

4. <span data-ttu-id="a39a6-258">Una vez completado el procesamiento, haga clic  con el botón secundario en el objeto de nuevo y elija Examinar para confirmar que la página del explorador muestra ahora los datos.</span><span class="sxs-lookup"><span data-stu-id="a39a6-258">When processing is complete, right-click the object again, and choose **Browse** to confirm that the browser page now shows data.</span></span> 


### <a name="users-have-trouble-logging-in-because-installer-fails-to-create-the-correct-settings-in-iis"></a><span data-ttu-id="a39a6-259">Los usuarios tienen problemas para iniciar sesión porque el instalador no puede crear la configuración correcta en IIS</span><span class="sxs-lookup"><span data-stu-id="a39a6-259">Users have trouble logging in because installer fails to create the correct settings in IIS</span></span>

<span data-ttu-id="a39a6-260">En raras ocasiones, el instalador no puede crear la configuración correcta en IIS.</span><span class="sxs-lookup"><span data-stu-id="a39a6-260">In rare cases, the installer fails to create the correct settings in IIS.</span></span> <span data-ttu-id="a39a6-261">Se requiere un cambio manual para permitir que los usuarios inicien sesión en el CQD.</span><span class="sxs-lookup"><span data-stu-id="a39a6-261">Manual change is required to allow users to log into the CQD.</span></span> <span data-ttu-id="a39a6-262">Si los usuarios tienen problemas para iniciar sesión, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="a39a6-262">If users are having trouble logging in, please follow these steps:</span></span>
  
1. <span data-ttu-id="a39a6-263">Abra el Administrador de IIS y vaya al sitio web predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a39a6-263">Open up IIS Manager, and navigate to Default Web Site.</span></span>
    
     ![Implementar el panel de calidad de llamadas](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. <span data-ttu-id="a39a6-265">Haga clic en "Autenticación".</span><span class="sxs-lookup"><span data-stu-id="a39a6-265">Click on "Authentication".</span></span> <span data-ttu-id="a39a6-266">Si las opciones "Autenticación anónima", "suplantación de ASP.NET", "Autenticación de formulario" y "Autenticación de Windows" no coinciden con la configuración que se muestra a continuación, cámbilas manualmente para que coincidan con la siguiente configuración.</span><span class="sxs-lookup"><span data-stu-id="a39a6-266">If the "Anonymous Authentication", "ASP.NET Impersonation", "Form Authentication", and "Windows Authentication" do not match the settings shown below, manually change them to match the settings below.</span></span> <span data-ttu-id="a39a6-267">Todos los demás mecanismos de autenticación deben deshabilitarse.</span><span class="sxs-lookup"><span data-stu-id="a39a6-267">All other authentication mechanisms should be disabled.</span></span>
    
     ![Implementar el panel de calidad de llamadas](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. <span data-ttu-id="a39a6-269">Para "Autenticación de Windows", haga clic en Configuración avanzada en el lado derecho.</span><span class="sxs-lookup"><span data-stu-id="a39a6-269">For "Windows Authentication", click on Advanced Settings on the right-hand side.</span></span>
    
     ![Implementar el panel de calidad de llamadas](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. <span data-ttu-id="a39a6-271">Establece "Protección ampliada" en Aceptar y activa la casilla "Habilitar autenticación en modo kernel".</span><span class="sxs-lookup"><span data-stu-id="a39a6-271">Set "Extended Protection" to Accept and check the "Enable Kernel-mode authentication" box.</span></span>
    
     ![Implementar el panel de calidad de llamadas](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. <span data-ttu-id="a39a6-273">Repita los pasos anteriores para cada una de las entradas "CQD", "QoEDataService" y "QoERepositoryService" debajo de "Sitio web predeterminado".</span><span class="sxs-lookup"><span data-stu-id="a39a6-273">Repeat the above steps for each of the "CQD", "QoEDataService", and "QoERepositoryService" entries below "Default Web Site".</span></span>
    
<span data-ttu-id="a39a6-274">Para los enlaces de puerto HTTP y HTTPS, el instalador creará enlaces de puerto en los números de puerto predeterminados (puerto 80 para HTTP y puerto 443 para HTTPS).</span><span class="sxs-lookup"><span data-stu-id="a39a6-274">For HTTP and HTTPS port bindings the installer will create port bindings on the default port numbers (port 80 for HTTP and port 443 for HTTPS).</span></span> <span data-ttu-id="a39a6-275">Si hay otro sitio web en el equipo que usa estos enlaces, habrá un conflicto y no se puede predecir el comportamiento de IIS.</span><span class="sxs-lookup"><span data-stu-id="a39a6-275">If there is another website on the machine that uses these bindings, there will be a conflict and the IIS behavior cannot be predicted.</span></span> <span data-ttu-id="a39a6-276">La mejor manera de evitar este problema es asegurarse de que ningún otro sitio web esté asignado a los puertos 80 y 443 antes de instalar el CQD.</span><span class="sxs-lookup"><span data-stu-id="a39a6-276">The best way to avoid this problem is to make sure that no other websites are mapped to ports 80 and 443 before installing CQD.</span></span> 
  
<span data-ttu-id="a39a6-277">Para habilitar SSL/TLS en IIS y forzar a los usuarios a conectarse a través de HTTPS seguro en lugar de HTTP:</span><span class="sxs-lookup"><span data-stu-id="a39a6-277">To enable SSL/TLS in IIS and force users to connect via secure HTTPS instead of HTTP:</span></span>
  
1. <span data-ttu-id="a39a6-278">Configure Secure Sockets Layer in IIS, consulte [Configuring Secure Sockets Layer in IIS 7](https://technet.microsoft.com/library/cc771438%28v=ws.10%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="a39a6-278">Configure Secure Sockets Layer in IIS, see [Configuring Secure Sockets Layer in IIS 7](https://technet.microsoft.com/library/cc771438%28v=ws.10%29.aspx).</span></span> <span data-ttu-id="a39a6-279">Una vez hecho esto, reemplace  `http` por `https` .</span><span class="sxs-lookup"><span data-stu-id="a39a6-279">Once done, replace  `http` with `https`.</span></span>
    
2. <span data-ttu-id="a39a6-280">Para obtener instrucciones sobre cómo habilitar TLS en las conexiones SQL Server, consulte Cómo habilitar el cifrado SSL para una instancia de SQL Server mediante [Microsoft Management Console](https://support.microsoft.com/kb/316898/).</span><span class="sxs-lookup"><span data-stu-id="a39a6-280">For instructions on enabling TLS in the SQL Server connections, see [How to enable SSL encryption for an instance of SQL Server by using Microsoft Management Console](https://support.microsoft.com/kb/316898/).</span></span>
    
## <a name="cube-sync-fails"></a><span data-ttu-id="a39a6-281">Error en la sincronización de cubos</span><span class="sxs-lookup"><span data-stu-id="a39a6-281">Cube Sync Fails</span></span>

<span data-ttu-id="a39a6-282">QoEMetrics puede contener algunos registros no válidos basados en los relojes del usuario final.</span><span class="sxs-lookup"><span data-stu-id="a39a6-282">QoEMetrics may contain some invalid records based on end user clocks.</span></span> <span data-ttu-id="a39a6-283">Si el sesgo de tiempo es mayor que 60 yrs, se producirá un error en la importación del cubo.</span><span class="sxs-lookup"><span data-stu-id="a39a6-283">If the time skew is greater than 60 yrs, the cube import will fail.</span></span>
  
 <span data-ttu-id="a39a6-284">Comprueba Min y Max StartTime/EndTime con las selecciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="a39a6-284">Check the Min and Max StartTime/EndTime using the selections below.</span></span> <span data-ttu-id="a39a6-285">Busque y elimine registros en el futuro muy remoto y en el pasado, se pueden ignorar y dividirán los procesos de sincronización.</span><span class="sxs-lookup"><span data-stu-id="a39a6-285">Look for and delete records in the far past and very distant future, they can be disregarded and they will break up the sync processes.</span></span>
  
- <span data-ttu-id="a39a6-286">Seleccionar MIN(StartTime) FROM CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="a39a6-286">Select MIN(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="a39a6-287">Seleccionar MAX(StartTime) FROM CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="a39a6-287">Select MAX(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="a39a6-288">Seleccionar MIN(EndTime) FROM CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="a39a6-288">Select MIN(EndTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="a39a6-289">Seleccionar MAX(EndTime) FROM CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="a39a6-289">Select MAX(EndTime) FROM CqdPartitionedStreamView</span></span>
    
## <a name="post-install-tasks"></a><span data-ttu-id="a39a6-290">Tareas posteriores a la instalación</span><span class="sxs-lookup"><span data-stu-id="a39a6-290">Post-install tasks</span></span>

### <a name="importing-buildings-and-networks"></a><span data-ttu-id="a39a6-291">Importación de edificios y redes</span><span class="sxs-lookup"><span data-stu-id="a39a6-291">Importing Buildings and Networks</span></span>

<span data-ttu-id="a39a6-292">Después de instalar el CQD, realice las siguientes tareas de configuración:</span><span class="sxs-lookup"><span data-stu-id="a39a6-292">After Installing CQD, perform the following configuration tasks:</span></span>
  
1. <span data-ttu-id="a39a6-293">Definir tipos de creación (recomendado)</span><span class="sxs-lookup"><span data-stu-id="a39a6-293">Define Building types (recommended)</span></span>
    
2. <span data-ttu-id="a39a6-294">Definir tipos de propiedad del edificio (recomendado)</span><span class="sxs-lookup"><span data-stu-id="a39a6-294">Define Building Ownership types (recommended)</span></span>
    
3. <span data-ttu-id="a39a6-295">Definir tipos de red (altamente recomendado)</span><span class="sxs-lookup"><span data-stu-id="a39a6-295">Define Network types (highly recommended)</span></span>
    
4. <span data-ttu-id="a39a6-296">Importar edificios (recomendado)</span><span class="sxs-lookup"><span data-stu-id="a39a6-296">Import Buildings (recommended)</span></span>
    
5. <span data-ttu-id="a39a6-297">Importar subredes (recomendado)</span><span class="sxs-lookup"><span data-stu-id="a39a6-297">Import Subnets (recommended)</span></span>
    
### <a name="define-building-types"></a><span data-ttu-id="a39a6-298">Definir tipos de creación</span><span class="sxs-lookup"><span data-stu-id="a39a6-298">Define Building Types</span></span>

<span data-ttu-id="a39a6-299">Los tipos de creación se usan para describir las diferentes definiciones o tipos de edificios de la organización.</span><span class="sxs-lookup"><span data-stu-id="a39a6-299">Building types are used to describe the different buildings definitions or types within your organization.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a39a6-300">Este paso es opcional, pero se recomienda.</span><span class="sxs-lookup"><span data-stu-id="a39a6-300">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="a39a6-301">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="a39a6-301">Examples</span></span>
  
- <span data-ttu-id="a39a6-302">Headquarters</span><span class="sxs-lookup"><span data-stu-id="a39a6-302">Headquarters</span></span>
    
- <span data-ttu-id="a39a6-303">Office remoto</span><span class="sxs-lookup"><span data-stu-id="a39a6-303">Remote Office</span></span>
    
- <span data-ttu-id="a39a6-304">Ubicación de unión</span><span class="sxs-lookup"><span data-stu-id="a39a6-304">Joint-venture location</span></span>
    
  <span data-ttu-id="a39a6-305">**Sintaxis de SQL ejemplo**</span><span class="sxs-lookup"><span data-stu-id="a39a6-305">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO
[dbo].[CqdBuildingType]
([BuildingTypeId],
[BuildingTypeDesc])
VALUES
(1, 
'Headquarters')   
```

<span data-ttu-id="a39a6-306">Los parámetros BuildingTypeId y BuildingTypeDesc son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="a39a6-306">The BuildingTypeId and BuildingTypeDesc parameters are required.</span></span>
  
### <a name="define-building-ownership-types"></a><span data-ttu-id="a39a6-307">Definir tipos de propiedad de creación</span><span class="sxs-lookup"><span data-stu-id="a39a6-307">Define Building Ownership Types</span></span>

<span data-ttu-id="a39a6-308">Los tipos de propiedad se usan para distinguir los activos propiedad frente a los alquilados.</span><span class="sxs-lookup"><span data-stu-id="a39a6-308">Ownership types are used to distinguish owned vs leased assets.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a39a6-309">Este paso es opcional, pero se recomienda.</span><span class="sxs-lookup"><span data-stu-id="a39a6-309">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="a39a6-310">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="a39a6-310">Examples</span></span>
  
- <span data-ttu-id="a39a6-311">Contoso Leased non-RE &amp; F</span><span class="sxs-lookup"><span data-stu-id="a39a6-311">Contoso Leased non-RE&amp;F</span></span>
    
- <span data-ttu-id="a39a6-312">Contoso Leased RE &amp; F</span><span class="sxs-lookup"><span data-stu-id="a39a6-312">Contoso Leased RE&amp;F</span></span>
    
- <span data-ttu-id="a39a6-313">Contoso Owned</span><span class="sxs-lookup"><span data-stu-id="a39a6-313">Contoso Owned</span></span>
    
- <span data-ttu-id="a39a6-314">Subsidiaria alquilada</span><span class="sxs-lookup"><span data-stu-id="a39a6-314">Subsidiary Leased</span></span>
    
  <span data-ttu-id="a39a6-315">**Sintaxis de SQL ejemplo**</span><span class="sxs-lookup"><span data-stu-id="a39a6-315">**Sample SQL Syntax**</span></span>
  
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

<span data-ttu-id="a39a6-316">Los parámetros OwnershipTypeId y OwnershipTypeDesc son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="a39a6-316">The OwnershipTypeId and OwnershipTypeDesc parameters are required.</span></span> 
  
### <a name="define-network-names"></a><span data-ttu-id="a39a6-317">Definir nombres de red</span><span class="sxs-lookup"><span data-stu-id="a39a6-317">Define Network Names</span></span>

<span data-ttu-id="a39a6-318">Los tipos de red se usan para describir diferentes tipos de redes dentro de la organización.</span><span class="sxs-lookup"><span data-stu-id="a39a6-318">Network Types are used to describe different types of networks within the organization.</span></span> <span data-ttu-id="a39a6-319">Esto te ofrece la posibilidad de filtrar (o filtrar) tipos de red específicos.</span><span class="sxs-lookup"><span data-stu-id="a39a6-319">This gives you the ability to filter on (or filter out) specific Network Types.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a39a6-320">Se recomienda definir nombres de red, pero es opcional.</span><span class="sxs-lookup"><span data-stu-id="a39a6-320">It is highly recommended to define Network Names, but it is optional.</span></span> <span data-ttu-id="a39a6-321">Si decide no definir nombres de red, asegúrese de que cada entrada de CqdNetwork tenga un BuildingId de 0.</span><span class="sxs-lookup"><span data-stu-id="a39a6-321">If you decide to not define network names, ensure the each CqdNetwork entry has a BuildingId of 0.</span></span> 
  
<span data-ttu-id="a39a6-322">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="a39a6-322">Examples</span></span>
  
- <span data-ttu-id="a39a6-323">VPN</span><span class="sxs-lookup"><span data-stu-id="a39a6-323">VPN</span></span>
    
- <span data-ttu-id="a39a6-324">LABORATORIO</span><span class="sxs-lookup"><span data-stu-id="a39a6-324">LAB</span></span>
    
  <span data-ttu-id="a39a6-325">**Sintaxis de SQL ejemplo**</span><span class="sxs-lookup"><span data-stu-id="a39a6-325">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

<span data-ttu-id="a39a6-326">Los parámetros NetworkNameID y NetworkName son necesarios, el parámetro NetworkType es opcional pero se recomienda.</span><span class="sxs-lookup"><span data-stu-id="a39a6-326">The NetworkNameID and NetworkName parameters are required, the NetworkType parameter is optional but recommended.</span></span>
  
### <a name="import-buildings"></a><span data-ttu-id="a39a6-327">Importar edificios</span><span class="sxs-lookup"><span data-stu-id="a39a6-327">Import Buildings</span></span>

<span data-ttu-id="a39a6-328">La importación de edificios te ofrece la posibilidad de obtener información específica sobre la creación (llamadas deficientes por edificio en WiFi/Cable, etc.).</span><span class="sxs-lookup"><span data-stu-id="a39a6-328">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a39a6-329">Este paso es opcional, pero se recomienda.</span><span class="sxs-lookup"><span data-stu-id="a39a6-329">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="a39a6-330">Antes de importar un nuevo edificio, ya debe tener una clave de creación predefinida identificada.</span><span class="sxs-lookup"><span data-stu-id="a39a6-330">Before you Import a new building you should already have a predefined BuildingKey identified.</span></span> <span data-ttu-id="a39a6-331">Para ello, emita el comando "SELECT MAX(BuildingKey) FROM CqdBuilding" SQL para identificar el valor actual y agregar 1 al resultado.</span><span class="sxs-lookup"><span data-stu-id="a39a6-331">To do that, issue the "SELECT MAX(BuildingKey) FROM CqdBuilding" SQL command to identify the current value and add 1 to the result.</span></span>
  
 <span data-ttu-id="a39a6-332">**Sintaxis de SQL ejemplo**</span><span class="sxs-lookup"><span data-stu-id="a39a6-332">**Sample SQL Syntax**</span></span>
  
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

<span data-ttu-id="a39a6-333">Los parámetros BuildingKey, BuildingName, BuildingShortName, OwnershipTypeId y BuildingTypeId son obligatorios y los demás parámetros son opcionales.</span><span class="sxs-lookup"><span data-stu-id="a39a6-333">The BuildingKey, BuildingName, BuildingShortName, OwnershipTypeId, BuildingTypeId parameters are required, the other parameters are optional.</span></span>
  
### <a name="import-subnets"></a><span data-ttu-id="a39a6-334">Importar subredes</span><span class="sxs-lookup"><span data-stu-id="a39a6-334">Import Subnets</span></span>

<span data-ttu-id="a39a6-335">La importación de edificios te ofrece la posibilidad de obtener información específica sobre la creación (llamadas deficientes por edificio en WiFi/Cable, etc.).</span><span class="sxs-lookup"><span data-stu-id="a39a6-335">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a39a6-336">Este paso es opcional, pero se recomienda.</span><span class="sxs-lookup"><span data-stu-id="a39a6-336">This step is optional, but recommended.</span></span>
  
<span data-ttu-id="a39a6-337">Importar subredes y asignarlas a los edificios importados en el último paso.</span><span class="sxs-lookup"><span data-stu-id="a39a6-337">Import Subnets and map them to the Buildings imported in the last step.</span></span> <span data-ttu-id="a39a6-338">Si decide no rellenar NetworkName, asegúrese de que cada entrada de esta tabla usa un NetworkNameID de 0.</span><span class="sxs-lookup"><span data-stu-id="a39a6-338">If you decided not to populate NetworkName, ensure each entry in this table uses a NetworkNameID of 0.</span></span> <span data-ttu-id="a39a6-339">Para obtener más información SQL sintaxis y parámetros para el Panel de calidad de llamadas, vea Usar el panel de calidad de llamadas [para Skype Empresarial Server.](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/use)</span><span class="sxs-lookup"><span data-stu-id="a39a6-339">For more information on SQL syntax and parameters for the Call Quality Dashboard, see [Use Call Quality Dashboard for Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/use).</span></span>
  
 <span data-ttu-id="a39a6-340">**Sintaxis de SQL ejemplo**</span><span class="sxs-lookup"><span data-stu-id="a39a6-340">**Sample SQL Syntax**</span></span>
  
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

<span data-ttu-id="a39a6-341">Los parámetros Network y UpdatedDate son obligatorios, los demás parámetros son opcionales.</span><span class="sxs-lookup"><span data-stu-id="a39a6-341">The Network, and UpdatedDate parameters are required, the other parameters are optional.</span></span>
  
### <a name="optional-bssid"></a><span data-ttu-id="a39a6-342">Opcional: BSSID</span><span class="sxs-lookup"><span data-stu-id="a39a6-342">Optional: BSSID</span></span>

<span data-ttu-id="a39a6-343">Rellenar la información BSSID te ofrece una correlación de secuencias WiFi adicional por controlador o radio.</span><span class="sxs-lookup"><span data-stu-id="a39a6-343">Populating BSSID information gives you additional WiFi stream correlation by controller or radio.</span></span> <span data-ttu-id="a39a6-344">Esto se suma al filtrado por creación o subred.</span><span class="sxs-lookup"><span data-stu-id="a39a6-344">This is in addition to filtering by building or subnet.</span></span> 
  
 <span data-ttu-id="a39a6-345">**Sintaxis de SQL ejemplo**</span><span class="sxs-lookup"><span data-stu-id="a39a6-345">**Sample SQL Syntax**</span></span>
  
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

<span data-ttu-id="a39a6-346">**Detalles de CqdBssidTable**</span><span class="sxs-lookup"><span data-stu-id="a39a6-346">**CqdBssidTable Details**</span></span>

|<span data-ttu-id="a39a6-347">**Como se muestra en el CQD**</span><span class="sxs-lookup"><span data-stu-id="a39a6-347">**As shown in CQD**</span></span>|<span data-ttu-id="a39a6-348">**Tabla CQDBssid**</span><span class="sxs-lookup"><span data-stu-id="a39a6-348">**CQDBssid Table**</span></span>|<span data-ttu-id="a39a6-349">**Entradas de ejemplo**</span><span class="sxs-lookup"><span data-stu-id="a39a6-349">**Example inputs**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a39a6-350">Ap NName</span><span class="sxs-lookup"><span data-stu-id="a39a6-350">Ap NName</span></span>  <br/> |<span data-ttu-id="a39a6-351">AP</span><span class="sxs-lookup"><span data-stu-id="a39a6-351">AP</span></span>  <br/> |<span data-ttu-id="a39a6-352">AP1</span><span class="sxs-lookup"><span data-stu-id="a39a6-352">AP1</span></span>  <br/> |
|<span data-ttu-id="a39a6-353">BBssid</span><span class="sxs-lookup"><span data-stu-id="a39a6-353">BBssid</span></span>  <br/> |<span data-ttu-id="a39a6-354">BSS</span><span class="sxs-lookup"><span data-stu-id="a39a6-354">BSS</span></span>  <br/> |<span data-ttu-id="a39a6-355">00-00-00-00-00-00 (debe usar el formato fformat delimitado)</span><span class="sxs-lookup"><span data-stu-id="a39a6-355">00-00-00-00-00-00 (you must use the delimited fformat)</span></span>  <br/> |
|<span data-ttu-id="a39a6-356">Controlador</span><span class="sxs-lookup"><span data-stu-id="a39a6-356">Controller</span></span>  <br/> |<span data-ttu-id="a39a6-357">Building</span><span class="sxs-lookup"><span data-stu-id="a39a6-357">Building</span></span>  <br/> |<span data-ttu-id="a39a6-358">Ap 7 de Aruba</span><span class="sxs-lookup"><span data-stu-id="a39a6-358">Aruba AP 7</span></span>  <br/> |
|<span data-ttu-id="a39a6-359">Dispositivo</span><span class="sxs-lookup"><span data-stu-id="a39a6-359">Device</span></span>  <br/> |<span data-ttu-id="a39a6-360">ess</span><span class="sxs-lookup"><span data-stu-id="a39a6-360">ess</span></span>  <br/> |<span data-ttu-id="a39a6-361">Controller1</span><span class="sxs-lookup"><span data-stu-id="a39a6-361">Controller1</span></span>  <br/> |
|<span data-ttu-id="a39a6-362">Radio</span><span class="sxs-lookup"><span data-stu-id="a39a6-362">Radio</span></span>  <br/> |<span data-ttu-id="a39a6-363">phy</span><span class="sxs-lookup"><span data-stu-id="a39a6-363">phy</span></span>  <br/> |<span data-ttu-id="a39a6-364">bgn</span><span class="sxs-lookup"><span data-stu-id="a39a6-364">bgn</span></span>  <br/> |
   
### <a name="processing-the-imported-data"></a><span data-ttu-id="a39a6-365">Procesamiento de los datos importados</span><span class="sxs-lookup"><span data-stu-id="a39a6-365">Processing the imported data</span></span>

<span data-ttu-id="a39a6-366">De forma predeterminada, después de importar los datos de creación o red, solo se aplicará a los registros generados después de ese momento.</span><span class="sxs-lookup"><span data-stu-id="a39a6-366">By default, after you import building/network data it will only apply to records generated after that point in time.</span></span> 
  
<span data-ttu-id="a39a6-367">Para etiquetar todos los registros anteriores con estos nuevos datos, deberá ejecutar el procedimiento almacenado CqdUpdateBuilding como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="a39a6-367">To tag all the previous records with this new data, you will need to run the CqdUpdateBuilding stored procedure as shown below:</span></span> 
  
<span data-ttu-id="a39a6-368">Pónle la fecha del primer registro (identifique que con el comando Select MIN(StartTime) FROM CqdPartitionedStreamView SQL ), un EndDate de mañana y, a continuación, NULL para los dos últimos valores.</span><span class="sxs-lookup"><span data-stu-id="a39a6-368">Give it the date of your first record (identify that using the Select MIN(StartTime) FROM CqdPartitionedStreamView SQL command ), an EndDate of tomorrow, then NULL for the last two values.</span></span>
  
<span data-ttu-id="a39a6-369">Una vez que los datos están asociados a datos de secuencia, el cubo SSIS debe volver a procesar todos los registros.</span><span class="sxs-lookup"><span data-stu-id="a39a6-369">Once the data is associated with stream data, the SSIS Cube needs to reprocess all records.</span></span> <span data-ttu-id="a39a6-370">Esto también se aplica cuando se agregan datos BSSID/ISP en masa.</span><span class="sxs-lookup"><span data-stu-id="a39a6-370">This also applies when bulk adding BSSID/ISP data.</span></span> <span data-ttu-id="a39a6-371">Asegúrese de que esté seleccionado "Proceso completo".</span><span class="sxs-lookup"><span data-stu-id="a39a6-371">Ensure that "Process Full" is selected.</span></span>
  

