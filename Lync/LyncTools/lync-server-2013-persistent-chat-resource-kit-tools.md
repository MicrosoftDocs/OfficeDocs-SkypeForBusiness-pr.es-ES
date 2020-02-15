---
title: Herramientas del kit de recursos de chat persistente de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Persistent Chat Resource Kit Tools
ms:assetid: 7a34d2ba-eb25-4e22-92d1-b9baf81b102c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945599(v=OCS.15)
ms:contentKeyID: 51541423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7895a1ebb2c0ce45cebf3514839b7ab3405e1c9f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "41983035"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-persistent-chat-resource-kit-tools"></a><span data-ttu-id="2af80-102">Herramientas del kit de recursos de chat persistente de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2af80-102">Lync Server 2013 Persistent Chat Resource Kit Tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2af80-103">_**Última modificación del tema:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="2af80-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="2af80-104">Las herramientas del kit de recursos de chat persistente de Lync Server 2013 ayudan a simplificar las tareas rutinarias para los administradores de ti que implementan y administran el servidor de chat persistente de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2af80-104">The Lync Server 2013 Persistent Chat Resource Kit tools help to make routine tasks easier for IT administrators who deploy and manage Lync Server 2013 Persistent Chat Server.</span></span> <span data-ttu-id="2af80-105">Además de las instrucciones de instalación, en este tema se describe el propósito de cada herramienta y ejemplos de uso.</span><span class="sxs-lookup"><span data-stu-id="2af80-105">In addition to installation instructions, this topic describes the purpose of each tool, and examples of its use.</span></span>

<div>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="2af80-106">Instalación de las herramientas del kit de recursos</span><span class="sxs-lookup"><span data-stu-id="2af80-106">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="2af80-107">Para instalar las herramientas del kit de recursos de Lync Server 2013, descargue **PersistentChatReskit. msi**.</span><span class="sxs-lookup"><span data-stu-id="2af80-107">To install the Lync Server 2013, Resource Kit Tools, download **PersistentChatReskit.msi**.</span></span> <span data-ttu-id="2af80-108">Ejecute **PersistentChatReskit. msi** para realizar una instalación sencilla.</span><span class="sxs-lookup"><span data-stu-id="2af80-108">Run **PersistentChatReskit.msi** to do a simple installation.</span></span> <span data-ttu-id="2af80-109">El archivo. msi instala todas las herramientas en la siguiente ruta de \\acceso: **archivos\\ de programa Kit\\de recursos del servidor de chat persistente de Microsoft Lync Server 2013**.</span><span class="sxs-lookup"><span data-stu-id="2af80-109">The .msi installs all the tools in the following path: \\**Program Files\\ Microsoft Lync Server 2013\\Persistent Chat Server Resource Kit**.</span></span> <span data-ttu-id="2af80-110">Las herramientas que son ejecutables independientes se encuentran en esta carpeta.</span><span class="sxs-lookup"><span data-stu-id="2af80-110">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="2af80-111">Las herramientas que también tienen archivos se encuentran en sus propias subcarpetas.</span><span class="sxs-lookup"><span data-stu-id="2af80-111">Tools that also have files are in their own subfolders.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2af80-112">Después de instalar las herramientas del kit de recursos de Lync Server 2013, debe instalar <STRONG>PsExec. exe</STRONG> y copiar <STRONG>PsExec. exe</STRONG> en la siguiente \\ruta de acceso: <STRONG>archivos de programa \ Microsoft Lync Server 2013 \ opciones de recursos del servidor de chat persistente Kit\ChatStressTool</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="2af80-112">After installing the Lync Server 2013, Resource Kit Tools, you must install <STRONG>PsExec.exe</STRONG> and copy <STRONG>PsExec.exe</STRONG> to the following path: \\<STRONG>Program Files\ Microsoft Lync Server 2013\Persistent Chat Server Resource Kit\ChatStressTool</STRONG>.</span></span> <span data-ttu-id="2af80-113">Si no copia <STRONG>PsExec. exe</STRONG>, la herramienta de estrés de chat persistente generará una excepción de error y no se realizará correctamente.</span><span class="sxs-lookup"><span data-stu-id="2af80-113">If you do not copy <STRONG>PsExec.exe</STRONG>, the Persistent Chat Stress Tool will throw an error exception, and not perform correctly.</span></span> <span data-ttu-id="2af80-114">Asegúrese de que cumple estos requisitos previos antes de ejecutar la herramienta.</span><span class="sxs-lookup"><span data-stu-id="2af80-114">Make sure that you meet this prerequisite requirement prior to running the tool.</span></span> <span data-ttu-id="2af80-115">Para obtener más información sobre cómo instalar <STRONG>PsExec. exe</STRONG>, consulte <A href="http://go.microsoft.com/fwlink/p/?linkid=282246">http://go.microsoft.com/fwlink/p/?LinkId=282246</A>.</span><span class="sxs-lookup"><span data-stu-id="2af80-115">For details about installing <STRONG>PsExec.exe</STRONG>, see <A href="http://go.microsoft.com/fwlink/p/?linkid=282246">http://go.microsoft.com/fwlink/p/?LinkId=282246</A>.</span></span>



</div>

</div>

<div>

## <a name="supported-environments"></a><span data-ttu-id="2af80-116">Entornos compatibles</span><span class="sxs-lookup"><span data-stu-id="2af80-116">Supported Environments</span></span>

<span data-ttu-id="2af80-117">Para obtener un rendimiento óptimo, debe instalar las herramientas del kit de recursos de Lync Server 2013 en el mismo entorno y con las mismas especificaciones necesarias para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2af80-117">For optimal performance, the Lync Server 2013, Resource Kit Tools should be installed in the same environment and with the same specifications that are required for Lync Server 2013.</span></span>

</div>

<div>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="2af80-118">Introducción a las herramientas del kit de recursos</span><span class="sxs-lookup"><span data-stu-id="2af80-118">Resource Kit Tools Overview</span></span>

<span data-ttu-id="2af80-119">Estas son las herramientas que se proporcionan en el kit de recursos de chat persistente de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2af80-119">Here are the tools that are provided in the Lync Server 2013 Persistent Chat Resource Kit.</span></span> <span data-ttu-id="2af80-120">En la siguiente sección se proporciona una descripción de cada herramienta, incluidos los requisitos y el uso de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="2af80-120">The following section provides a description of each tool, including requirements and example usage.</span></span>

  - <span data-ttu-id="2af80-121">AffCheck</span><span class="sxs-lookup"><span data-stu-id="2af80-121">AffCheck</span></span>

  - <span data-ttu-id="2af80-122">ChatMonitoringSummary</span><span class="sxs-lookup"><span data-stu-id="2af80-122">ChatMonitoringSummary</span></span>

  - <span data-ttu-id="2af80-123">Herramienta ChatStress</span><span class="sxs-lookup"><span data-stu-id="2af80-123">ChatStress Tool</span></span>

  - <span data-ttu-id="2af80-124">ChatUpgradeVerifier</span><span class="sxs-lookup"><span data-stu-id="2af80-124">ChatUpgradeVerifier</span></span>

  - <span data-ttu-id="2af80-125">ChatUsageReport</span><span class="sxs-lookup"><span data-stu-id="2af80-125">ChatUsageReport</span></span>

  - <span data-ttu-id="2af80-126">ScheduleADSyncforPrincipal</span><span class="sxs-lookup"><span data-stu-id="2af80-126">ScheduleADSyncforPrincipal</span></span>

</div>

<div>

## <a name="affcheck"></a><span data-ttu-id="2af80-127">AffCheck</span><span class="sxs-lookup"><span data-stu-id="2af80-127">AffCheck</span></span>

<div>

## <a name="description"></a><span data-ttu-id="2af80-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="2af80-128">Description</span></span>

<span data-ttu-id="2af80-129">La herramienta AffCheck confirma que los registros de afiliación de grupo y usuario de base de datos de servidor back-end persistente coinciden con los de servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2af80-129">The AffCheck tool confirms that the Persistent Chat back-end database user and group affiliation records match that of Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="2af80-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2af80-130">Requirements</span></span>

<span data-ttu-id="2af80-131">La herramienta se instala con el instalador de PersistentChatResKit en un equipo unido a un dominio.</span><span class="sxs-lookup"><span data-stu-id="2af80-131">The tool is installed with the PersistentChatResKit installer on a domain joined machine.</span></span>

<span data-ttu-id="2af80-132">La cuenta de usuario con la que se ejecuta la herramienta debe tener acceso de lectura a la base de datos back-end de chat persistente y servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2af80-132">The user account under which the tool is run must have Read access to the Persistent Chat back-end database and Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="2af80-133">Uso</span><span class="sxs-lookup"><span data-stu-id="2af80-133">Usage</span></span>

<span data-ttu-id="2af80-134">Configure el archivo AffCheck. exe. config de acuerdo con las instrucciones del archivo de configuración y ejecute la herramienta AffCheck sin parámetros de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="2af80-134">Configure the AffCheck.exe.config file according to the instructions in the config file and run the AffCheck tool without command-line parameters.</span></span> <span data-ttu-id="2af80-135">A continuación se muestran los contenidos de la AffCheck. exe. config predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2af80-135">Following are the contents of the default AffCheck.exe.config.</span></span>

<span data-ttu-id="2af80-136">**AffCheck. exe. config:**</span><span class="sxs-lookup"><span data-stu-id="2af80-136">**AffCheck.exe.config:**</span></span>

```XML
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <appSettings>
        <!--Domain Controller IP Address-->
        <add key="LDAP" value="LDAP://0.0.0.0/"/>
        
        <!-- Domain DN  This is case sensitive, it must match exactly-->
        <add key="DomainComponent" value ="DC=DOMAIN,DC=COM"/>
        
        <!--Domain Administrator Login and Password-->
        <add key="DomainLogin" value="DOMAIN\Administrator"/>
        <add key="DomainPassword" value ="password"/>
        
        <!-- Connection string to Group Chat Database-->
        <add key="ConnectionString" value="data source=SQL_SERVER\INSTANCE;initial catalog=DATABASE_NAME;integrated security=SSPI"/>
        
        <!--Check group affiliations-->
        <add key="CheckGroups" value="true"/>
        
        <!--Check user affilations-->
        <add key="CheckUsers" value="true"/>
        
        <!--List all affiliations if there is a mismatch between database and active directory-->
        <add key="ListAffiliations" value="true"/>
    
        <!--If you need to offset the results of the number of affilations in AD(can be negative to add to AD parent count)-->
        <add key="Offset" value ="0"/>
    
        <!--If you need to ignore certain parents, provide a semi colon delimitted list.-->
        <add key="Ignore" value ="DC=uatest,DC=test,DC=contoso,DC=com;DC=test,DC=contoso,DC=com"/>
      </appSettings>
    </configuration>
  ```
</div>

</div>

<div>

## <a name="chatmonitoringsummary"></a><span data-ttu-id="2af80-137">ChatMonitoringSummary</span><span class="sxs-lookup"><span data-stu-id="2af80-137">ChatMonitoringSummary</span></span>

<div>

## <a name="description"></a><span data-ttu-id="2af80-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="2af80-138">Description</span></span>

<span data-ttu-id="2af80-139">La herramienta PersistentChatMonitoringSummary mueve la información de supervisión de chat persistente desde la base de datos de supervisión a un archivo de registro CSV especificado.</span><span class="sxs-lookup"><span data-stu-id="2af80-139">The PersistentChatMonitoringSummary tool moves Persistent Chat monitoring information from the monitoring database into a specified CSV log file.</span></span>

<span data-ttu-id="2af80-140">El archivo CSV contendrá un desglose de las sesiones de chat persistentes por número de sesiones totales, sesiones correctas, errores inesperados, errores esperados y un desglose de los errores inesperados por identificador de diagnóstico, número de errores y descripción del error.</span><span class="sxs-lookup"><span data-stu-id="2af80-140">The CSV file will contain a breakdown of Persistent Chat sessions by number of total sessions, successful sessions, unexpected failures, expected failures, and a breakdown of the unexpected failures by diagnostic ID, number of failures, and failure description.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="2af80-141">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2af80-141">Requirements</span></span>

<span data-ttu-id="2af80-142">Instale las herramientas del kit de recursos de chat persistente en un equipo unido a un dominio que tenga acceso a la base de datos de supervisión.</span><span class="sxs-lookup"><span data-stu-id="2af80-142">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Monitoring database.</span></span>

<span data-ttu-id="2af80-143">La cuenta de usuario con la que se ejecuta la herramienta debe tener acceso de lectura a la base de datos de supervisión.</span><span class="sxs-lookup"><span data-stu-id="2af80-143">The user account under which the tool runs must have Read access to the Monitoring database.</span></span>

<span data-ttu-id="2af80-144">El archivo PersistentChatMonitoringSummary. exe. config debe contener una \<\> sección connectionStrings que defina la cadena de conexión a la base de datos de supervisión.</span><span class="sxs-lookup"><span data-stu-id="2af80-144">The file, PersistentChatMonitoringSummary.exe.config, must contain a \<connectionStrings\> section that defines the connection string to the Monitoring database.</span></span> <span data-ttu-id="2af80-145">También debe contener una clave para el PersistentChatEndpointUri en el que se recopilarán los datos de supervisión y una ruta de acceso de archivo a una ubicación para el archivo CSV que se generará.</span><span class="sxs-lookup"><span data-stu-id="2af80-145">It must also contain a key for the PersistentChatEndpointUri that the monitoring data will be gathered for, and a file path to a location for the CSV file that will be generated.</span></span> <span data-ttu-id="2af80-146">Consulte el archivo config instalado para obtener ejemplos.</span><span class="sxs-lookup"><span data-stu-id="2af80-146">Refer to the installed config file for examples.</span></span> <span data-ttu-id="2af80-147">El archivo debe estar ubicado en el mismo directorio que la herramienta.</span><span class="sxs-lookup"><span data-stu-id="2af80-147">The file must be located in the same directory as the tool.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="2af80-148">Uso</span><span class="sxs-lookup"><span data-stu-id="2af80-148">Usage</span></span>

```Batch
    PersistentChatMonitoringSummary [-StartDateTime <date>] [-EndDateTime <date>]
```

<span data-ttu-id="2af80-149">Estos parámetros definen la selección de datos:</span><span class="sxs-lookup"><span data-stu-id="2af80-149">These parameters define the selection of data:</span></span>

<span data-ttu-id="2af80-150">**StartDateTime:** Opcionalmente, especifica la fecha de inicio del período de selección.</span><span class="sxs-lookup"><span data-stu-id="2af80-150">**StartDateTime:** Optionally specifies the start date of the selection period.</span></span> <span data-ttu-id="2af80-151">Valor predeterminado: 1/1/1753 12:00:00 A.M.</span><span class="sxs-lookup"><span data-stu-id="2af80-151">Default: 1/1/1753 12:00:00 AM</span></span>

<span data-ttu-id="2af80-152">**EndDateTime:** Opcionalmente, especifica la última fecha del período de selección.</span><span class="sxs-lookup"><span data-stu-id="2af80-152">**EndDateTime:** Optionally specifies the last date of the selection period.</span></span> <span data-ttu-id="2af80-153">Valor predeterminado: ahora</span><span class="sxs-lookup"><span data-stu-id="2af80-153">Default: Now</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="2af80-154">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2af80-154">Example</span></span>

```Batch
    C:\Users\Administrator.VDOMAIN>Desktop\PersistentChatMonitoringSummary.exe
    Reading database connection information, Persistent Chat endpoint uri, and csv output path information from the application config file...
    Connecting to Monitoring database with connection string specified in the application config file...
    Gathering Persistent Chat Session Summary information between "1/1/1753 12:00:00 AM" and "11/19/2012 10:11:25 AM" for Persistent Chat Endpoint Uri "persistentChatEndpointUri@domain.com"...
    Press enter to continue or hit ctr-c if these settings are incorrect...
    
    The summary information about Persistent Chat sessions from the Monitoring database has been output to C:\PersistentChatMonitoring_dd4ace24-4c8a-4a3d-8fd4-591bdfacf47b.csv
    Press enter to exit...
```

</div>

</div>

<div>

## <a name="persistent-chat-stress-tool"></a><span data-ttu-id="2af80-155">Herramienta de estrés de chat persistente</span><span class="sxs-lookup"><span data-stu-id="2af80-155">Persistent Chat Stress Tool</span></span>

<div>

## <a name="description"></a><span data-ttu-id="2af80-156">Descripción</span><span class="sxs-lookup"><span data-stu-id="2af80-156">Description</span></span>

<span data-ttu-id="2af80-157">La herramienta de estrés de chat persistente ofrece una forma sencilla de simular el uso del chat persistente para probar el rendimiento real, incluidos los diversos modelos de usuario para ajustarse mejor a los escenarios de uso esperados.</span><span class="sxs-lookup"><span data-stu-id="2af80-157">The Persistent Chat Stress tool provides an easy way to simulate usage of Persistent Chat to test real-world performance, including varied user models to better fit your expected usage scenarios.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="2af80-158">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2af80-158">Requirements</span></span>

<span data-ttu-id="2af80-159">Instale las herramientas del kit de recursos de chat persistente en un equipo unido a un dominio que tenga acceso a la base de datos back-end de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="2af80-159">Install the Persistent Chat Resource Kit tools onto a domain-joined machine that has access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="2af80-160">Además de esta máquina del *controlador* , necesitará varias máquinas *del cargador* .</span><span class="sxs-lookup"><span data-stu-id="2af80-160">In addition to this *controller* machine, you will need several *loader* machines.</span></span> <span data-ttu-id="2af80-161">Para cada 10.000 usuarios del modelo de usuario, necesitará al menos 4 GB de RAM disponible en un equipo del cargador.</span><span class="sxs-lookup"><span data-stu-id="2af80-161">For every 10K users in your user model, you will need at least 4GB of free RAM on a loader machine.</span></span> <span data-ttu-id="2af80-162">Por ejemplo, una ejecución con usuarios de 80K necesitará aproximadamente 32 GB de RAM distribuida en todas las máquinas del cargador.</span><span class="sxs-lookup"><span data-stu-id="2af80-162">For example, a run with 80K users will require about 32GB of RAM spread across all loader machines.</span></span> <span data-ttu-id="2af80-163">Se recomienda tener al menos tres equipos de cargador, independientemente de la carga prevista.</span><span class="sxs-lookup"><span data-stu-id="2af80-163">We recommend that you have at least three loader machines, regardless of expected load.</span></span>

<span data-ttu-id="2af80-164">Los equipos del cargador deben tener instalado .NET 4,5 Framework, así como el paquete redistribuible de Visual C++ 2012.</span><span class="sxs-lookup"><span data-stu-id="2af80-164">Loader machines must have the .NET 4.5 Framework as well as the Visual C++ 2012 Redistributable installed.</span></span>

</div>

<div>

## <a name="configuration"></a><span data-ttu-id="2af80-165">Configuración</span><span class="sxs-lookup"><span data-stu-id="2af80-165">Configuration</span></span>

<span data-ttu-id="2af80-166">Copie los archivos de ChatStressTool en una carpeta compartida accesible desde todos los equipos del cargador.</span><span class="sxs-lookup"><span data-stu-id="2af80-166">Copy ChatStressTool files into a shared folder accessible from all loader machines.</span></span>

<span data-ttu-id="2af80-167">Crear usuarios y canales para usarlos en el segmento de esfuerzo:</span><span class="sxs-lookup"><span data-stu-id="2af80-167">Create users and channels for use in the stress run:</span></span>

  - <span data-ttu-id="2af80-168">Cree tantos usuarios como el modelo de usuario llame a, habilítelo para Lync y establezca su Directiva de chat persistente en habilitada.</span><span class="sxs-lookup"><span data-stu-id="2af80-168">Create as many users as your user model calls for, enable them for Lync, and set their Persistent Chat policy to Enabled.</span></span>

  - <span data-ttu-id="2af80-169">Cree una categoría para los canales de estrés y, a continuación, cree tantas salas como sean necesarias en esa categoría.</span><span class="sxs-lookup"><span data-stu-id="2af80-169">Create a category for your stress channels, and then create as many rooms as are needed under that category.</span></span> <span data-ttu-id="2af80-170">La categoría debe tener todos los usuarios de esfuerzo en su lista de **permitidos** (mediante la adición de su uo) y las salas de estrés deben tener una configuración de privacidad de **abierta**.</span><span class="sxs-lookup"><span data-stu-id="2af80-170">The category should have all stress users in its **Allowed** list (by way of adding their OU), and stress rooms should have a privacy setting of **Open**.</span></span>

  - <span data-ttu-id="2af80-171">Le recomendamos que cree salas de estrés adicionales.</span><span class="sxs-lookup"><span data-stu-id="2af80-171">We recommend creating extra stress rooms.</span></span> <span data-ttu-id="2af80-172">Puede crear salas de 50.000 con el siguiente comando de la interfaz de línea de comandos de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2af80-172">You can create 50,000 rooms with the following Windows PowerShell command-line interface command:</span></span>
    ```Powershell
        for ($i = 0; $i -le 50000; $i++) { New-CsPersistentChatRoom -Category <parent category> -Name "StressChan_$i" -Privacy Open }
    ```    

<span data-ttu-id="2af80-173">Edite los archivos de configuración para que se ajusten a su topología:</span><span class="sxs-lookup"><span data-stu-id="2af80-173">Edit the configuration files to fit your topology:</span></span>

<span data-ttu-id="2af80-174">En **LoaderProcess. exe. config**, cambie "Controller.contoso.com" por el nombre de dominio completo (FQDN) del equipo del controlador.</span><span class="sxs-lookup"><span data-stu-id="2af80-174">In **LoaderProcess.exe.config**, change “controller.contoso.com” to the controller machine’s fully qualified domain name (FQDN).</span></span>

<span data-ttu-id="2af80-175">En **StressLauncher. exe. config:**</span><span class="sxs-lookup"><span data-stu-id="2af80-175">In **StressLauncher.exe.config:**</span></span>

1.  <span data-ttu-id="2af80-176">Cambie el valor de configuración "LoaderBinary" a la ruta de acceso de la carpeta compartida.</span><span class="sxs-lookup"><span data-stu-id="2af80-176">Change the “LoaderBinary” setting value to the shared folder’s path.</span></span>

2.  <span data-ttu-id="2af80-177">Cambie "AdminUser"/"AdminPassword" por las credenciales que tienen acceso de administrador a los equipos del cargador.</span><span class="sxs-lookup"><span data-stu-id="2af80-177">Change “AdminUser”/”AdminPassword” to credentials that have admin access to loader machines.</span></span>

3.  <span data-ttu-id="2af80-178">Cambie "ChannelCategory" por el nombre de la categoría en la que se crearon los canales de estrés.</span><span class="sxs-lookup"><span data-stu-id="2af80-178">Change “ChannelCategory” to the name of the category that stress channels have been created under.</span></span>

4.  <span data-ttu-id="2af80-179">Cambie "UserNamePattern" y "UserPasswordPattern" por una plantilla que coincida con las credenciales de usuario de carga.</span><span class="sxs-lookup"><span data-stu-id="2af80-179">Change “UserNamePattern” and “UserPasswordPattern” to a template that matches your stress user credentials.</span></span> <span data-ttu-id="2af80-180">{0}se reemplaza por el número de índice del usuario.</span><span class="sxs-lookup"><span data-stu-id="2af80-180">{0} is replaced with the user’s index number.</span></span>

5.  <span data-ttu-id="2af80-181">Cambie "dominio" al dominio SIP de su topología de prueba.</span><span class="sxs-lookup"><span data-stu-id="2af80-181">Change “Domain” to the SIP domain of your test topology.</span></span>

6.  <span data-ttu-id="2af80-182">Cambie "ConnectionString" por una cadena de conexión para la base de datos back-end de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="2af80-182">Change “ConnectionString” to a connection string for your Persistent Chat back-end database.</span></span>

7.  <span data-ttu-id="2af80-183">Cambie "UserIndexStart" al índice del primer usuario de esfuerzo.</span><span class="sxs-lookup"><span data-stu-id="2af80-183">Change “UserIndexStart” to the index of the first stress user.</span></span>

8.  <span data-ttu-id="2af80-184">Cambie "LyncFQDN" por el FQDN de su grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="2af80-184">Change “LyncFQDN” to the FQDN of your Front End pool.</span></span>

9.  <span data-ttu-id="2af80-185">Modifique la lista "máquinas" para incluir nombres de máquina para todos los equipos del cargador.</span><span class="sxs-lookup"><span data-stu-id="2af80-185">Modify the “Machines” list to include machine names for all of your loader machines.</span></span>

10. <span data-ttu-id="2af80-186">Cambiar baseAddress del extremo de servicio (el valor predeterminado es "controller.contoso.com") al FQDN de su equipo de controlador.</span><span class="sxs-lookup"><span data-stu-id="2af80-186">Change the baseAddress of the service endpoint (default is “controller.contoso.com”) to the FQDN of your controller machine.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="2af80-187">Uso</span><span class="sxs-lookup"><span data-stu-id="2af80-187">Usage</span></span>

<span data-ttu-id="2af80-188">Una vez completada la configuración, abra StressLauncher. exe en el equipo del controlador.</span><span class="sxs-lookup"><span data-stu-id="2af80-188">After configuration is complete, open StressLauncher.exe on the controller machine.</span></span> <span data-ttu-id="2af80-189">Puede iniciar StressLauncher como cualquier usuario.</span><span class="sxs-lookup"><span data-stu-id="2af80-189">You can launch StressLauncher as any user.</span></span> <span data-ttu-id="2af80-190">Las credenciales con las que se inician los procesos del cargador en los equipos del cargador deben especificarse en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="2af80-190">The credentials under which the loader processes start on the loader machines must be specified in the config file.</span></span> <span data-ttu-id="2af80-191">También debe proporcionar una cadena de conexión que tenga acceso de lectura a la base de datos back-end de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="2af80-191">You also must give a connection string that has Read access to the Persistent Chat back-end database.</span></span> <span data-ttu-id="2af80-192">Si esta cadena de conexión usa la autenticación de Windows integrada, debe iniciar StressLauncher como un usuario con este acceso.</span><span class="sxs-lookup"><span data-stu-id="2af80-192">If this connection string uses integrated Windows authentication, you must launch StressLauncher as a user that has this access.</span></span>

<span data-ttu-id="2af80-193">Modifique la configuración del modelo de usuario según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="2af80-193">Alter the user model settings as needed.</span></span> <span data-ttu-id="2af80-194">Haga clic en **Iniciar carga** para iniciar una ejecución.</span><span class="sxs-lookup"><span data-stu-id="2af80-194">Click **Start Load** to initiate a run.</span></span> <span data-ttu-id="2af80-195">Después de un minuto, los usuarios empezarán a iniciar sesión y la barra de progreso empezará a rellenarse.</span><span class="sxs-lookup"><span data-stu-id="2af80-195">After a minute or so, users will start being signed in, and the progress bar will begin to fill.</span></span> <span data-ttu-id="2af80-196">En este punto, puede que el equipo controlador funcione y realice medidas de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="2af80-196">At this point, you may can the controller machine working and take performance measurements.</span></span>

</div>

</div>

<div>

## <a name="chatupgradeverifier"></a><span data-ttu-id="2af80-197">ChatUpgradeVerifier</span><span class="sxs-lookup"><span data-stu-id="2af80-197">ChatUpgradeVerifier</span></span>

<div>

## <a name="description"></a><span data-ttu-id="2af80-198">Descripción</span><span class="sxs-lookup"><span data-stu-id="2af80-198">Description</span></span>

<span data-ttu-id="2af80-199">ChatUpgradeVerifier es una herramienta de comparación de bases de datos específica de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="2af80-199">ChatUpgradeVerifier is a Persistent Chat specific database comparison tool.</span></span> <span data-ttu-id="2af80-200">La herramienta compara la base de datos de chat en grupo 2007 R2 o el chat de grupo 2010 (2007/2010Db) en la base de datos del chat persistente 2013 (2013Db).</span><span class="sxs-lookup"><span data-stu-id="2af80-200">The tool compares either the Group Chat 2007 R2 or Group Chat 2010 Database (2007/2010Db) to the Persistent Chat 2013 Database (2013Db).</span></span>

<span data-ttu-id="2af80-201">La herramienta comprobará, una por una, cada categoría, un salón de chat persistente y un complemento en 2007/2010Db para ver si aparece en el 2013Db.</span><span class="sxs-lookup"><span data-stu-id="2af80-201">The tool will check, one by one, each category, Persistent Chat room, and add-in in 2007/2010Db to see if it appears in the 2013Db.</span></span> <span data-ttu-id="2af80-202">La comparación incluye la comprobación de todas las opciones de configuración de la categoría, el salón de chat o el complemento, todas las entidades de identidad del ámbito de la categoría y cualquier entidad de identidad de un rol en la categoría o en el salón de chat.</span><span class="sxs-lookup"><span data-stu-id="2af80-202">The comparison includes checking all settings on the category, chat room, or add-in, any principals in scope on the category, and any principal in a role on either the category or the chat room.</span></span> <span data-ttu-id="2af80-203">Si una categoría o un salón de chat no aparece correctamente en 2013Db, las diferencias se generarán en un archivo de conflictos.</span><span class="sxs-lookup"><span data-stu-id="2af80-203">If a category or a chat room does not appear correctly in the 2013Db, the differences will be output to a conflicts file.</span></span> <span data-ttu-id="2af80-204">Si, una vez que se ha realizado la actualización, se cambia 2007/2010Db y, a continuación, se ejecuta esta herramienta, se producirá un resultado de diferencias en el archivo de conflictos.</span><span class="sxs-lookup"><span data-stu-id="2af80-204">If, after the upgrade has occurred, the 2007/2010Db is changed and then this tool is run, there will be a differences output to the conflicts file.</span></span> <span data-ttu-id="2af80-205">Tenga en cuenta que esta aplicación es solo una herramienta de comparación de bases de datos y no valida el proceso de actualización.</span><span class="sxs-lookup"><span data-stu-id="2af80-205">Note that this application is a database comparison tool only and does not validate the upgrade process.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="2af80-206">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2af80-206">Requirements</span></span>

<span data-ttu-id="2af80-207">Instale las herramientas del kit de recursos de chat persistente en un equipo unido a un dominio que tenga acceso a las bases de datos de back-end de chat persistente (versiones anteriores y actuales para el chat persistente).</span><span class="sxs-lookup"><span data-stu-id="2af80-207">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Persistent Chat back-end databases (previous and current versions for Persistent Chat).</span></span>

<span data-ttu-id="2af80-208">La cuenta de usuario con la que se ejecuta la herramienta debe tener acceso de lectura a las bases de datos de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="2af80-208">The user account under which the tool runs must have Read access to the Persistent Chat databases.</span></span>

<span data-ttu-id="2af80-209">El archivo ChatUpgradeVerifier. exe. config debe contener el parámetro GroupChat2007R2Db o el parámetro GroupChat2010Db, con una cadena de conexión a la base de datos de chat de grupo adecuada (Groupchat 2007R2 o 2010).</span><span class="sxs-lookup"><span data-stu-id="2af80-209">The ChatUpgradeVerifier.exe.config file must contain either the GroupChat2007R2Db parameter or the GroupChat2010Db parameter, with a connection string to the appropriate Group Chat database (either Groupchat 2007R2 or 2010).</span></span> <span data-ttu-id="2af80-210">También debe contener un parámetro PersistentChat2013Db, con una cadena de conexión a la base de datos de chat persistente 2013.</span><span class="sxs-lookup"><span data-stu-id="2af80-210">It must also contain a PersistentChat2013Db parameter, with a connection string to the Persistent Chat 2013 database.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="2af80-211">Uso</span><span class="sxs-lookup"><span data-stu-id="2af80-211">Usage</span></span>

<span data-ttu-id="2af80-212">Ejecute **ChatUpgradeVerifier** sin ningún parámetro.</span><span class="sxs-lookup"><span data-stu-id="2af80-212">Run **ChatUpgradeVerifier** without any parameters.</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="2af80-213">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2af80-213">Example</span></span>

<span data-ttu-id="2af80-214">![Ejecutar ChatUpgradeVerifier. exe.](images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "Ejecutar ChatUpgradeVerifier. exe.")</span><span class="sxs-lookup"><span data-stu-id="2af80-214">![Running ChatUpgradeVerifier.exe.](images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "Running ChatUpgradeVerifier.exe.")</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-usage-report"></a><span data-ttu-id="2af80-215">Informe de uso de chat persistente</span><span class="sxs-lookup"><span data-stu-id="2af80-215">Persistent Chat Usage Report</span></span>

<div>

## <a name="description"></a><span data-ttu-id="2af80-216">Descripción</span><span class="sxs-lookup"><span data-stu-id="2af80-216">Description</span></span>

<span data-ttu-id="2af80-217">La herramienta ChatUsageReport genera un informe HTML del uso del servicio de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="2af80-217">The ChatUsageReport tool generates an HTML report of Persistent Chat service usage.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="2af80-218">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2af80-218">Requirements</span></span>

<span data-ttu-id="2af80-219">Instale las herramientas del kit de recursos de chat persistente en un equipo unido a un dominio que tenga acceso a la base de datos back-end de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="2af80-219">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="2af80-220">La cuenta de usuario con la que se ejecuta la herramienta debe tener acceso de lectura a la base de datos back-end de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="2af80-220">The user account under which the tool is run must have Read access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="2af80-221">El archivo ChatUsageReport. exe. config debe contener una \<\> sección connectionStrings que defina la cadena de conexión a la base de datos back-end de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="2af80-221">The file, ChatUsageReport.exe.config, must contain a \<connectionStrings\> section defining the connection string to the Persistent Chat back-end database.</span></span> <span data-ttu-id="2af80-222">El contenido del archivo de configuración predeterminado se incluye aquí, para su referencia.</span><span class="sxs-lookup"><span data-stu-id="2af80-222">The contents of the default config file are included here, for your reference.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="2af80-223">Uso</span><span class="sxs-lookup"><span data-stu-id="2af80-223">Usage</span></span>

```Powershell
    ChatUsageReport [-StartDate {date}] [-EndDate {date}] [-TopActiveUsers {n}] [-TopActiveRooms {n}] [-LeastActiveRooms {n}] [-RoomsInactiveSince {Date}] [-OutputFolder {path}]
```
<span data-ttu-id="2af80-224">Estos parámetros definen la selección de datos:</span><span class="sxs-lookup"><span data-stu-id="2af80-224">These parameters define the selection of data:</span></span>

<span data-ttu-id="2af80-225">**StartDate:** Opcionalmente, especifica la fecha de inicio UTC del período de selección.</span><span class="sxs-lookup"><span data-stu-id="2af80-225">**StartDate:** Optionally specifies the UTC start date of the selection period.</span></span> <span data-ttu-id="2af80-226">Valor predeterminado: fecha más temprana</span><span class="sxs-lookup"><span data-stu-id="2af80-226">Default: Earliest Date</span></span>

<span data-ttu-id="2af80-227">**EndDate:** Opcionalmente, especifica la fecha de finalización UTC del período de selección.</span><span class="sxs-lookup"><span data-stu-id="2af80-227">**EndDate:** Optionally specifies the UTC end date of the selection period.</span></span> <span data-ttu-id="2af80-228">Valor predeterminado: ahora</span><span class="sxs-lookup"><span data-stu-id="2af80-228">Default: Now</span></span>

<span data-ttu-id="2af80-229">Estos parámetros definen cómo y qué datos se muestran:</span><span class="sxs-lookup"><span data-stu-id="2af80-229">These parameters define how and what data is displayed:</span></span>

<span data-ttu-id="2af80-230">**TopActiveUsers:** Si se especifica esto, el informe incluirá a los usuarios más activos en función del número de mensajes que el usuario haya publicado en el salón de chat durante el período seleccionado.</span><span class="sxs-lookup"><span data-stu-id="2af80-230">**TopActiveUsers:** If this is specified, the report will include the n most active users in terms of the number of messages the user has posted in the chat room for the selected period.</span></span> <span data-ttu-id="2af80-231">Valor predeterminado: 10</span><span class="sxs-lookup"><span data-stu-id="2af80-231">Default: 10</span></span>

<span data-ttu-id="2af80-232">**TopActiveRooms:** Si se especifica, el informe incluirá los n salones de chat más activos en función del número de mensajes publicados en el salón durante el período seleccionado.</span><span class="sxs-lookup"><span data-stu-id="2af80-232">**TopActiveRooms:** If this is specified, the report will include the n most active chat rooms in terms of the number of messages posted in the room for the selected period.</span></span> <span data-ttu-id="2af80-233">Valor predeterminado: 10</span><span class="sxs-lookup"><span data-stu-id="2af80-233">Default: 10</span></span>

<span data-ttu-id="2af80-234">**LeastActiveRooms:** Si se especifica esto, el informe incluirá los salones de chat activos menos activos en relación con el número de mensajes publicados en el salón de chat durante el período seleccionado.</span><span class="sxs-lookup"><span data-stu-id="2af80-234">**LeastActiveRooms:** If this is specified, the report will include the n least active chat rooms in terms of the number of messages posted in the chat room for the selected period.</span></span> <span data-ttu-id="2af80-235">Las salas tendrán al menos un mensaje expuesto.</span><span class="sxs-lookup"><span data-stu-id="2af80-235">Rooms will have at least one message posted.</span></span> <span data-ttu-id="2af80-236">Valor predeterminado: 10</span><span class="sxs-lookup"><span data-stu-id="2af80-236">Default: 10</span></span>

<span data-ttu-id="2af80-237">**RoomsInactiveSince:** Si se especifica esto, el informe incluirá una lista de salones de chat que han estado inactivos desde la fecha especificada.</span><span class="sxs-lookup"><span data-stu-id="2af80-237">**RoomsInactiveSince:** If this is specified, the report will include a list of chat rooms that have been inactive since the specified date.</span></span> <span data-ttu-id="2af80-238">Valor predeterminado: tiempo completo</span><span class="sxs-lookup"><span data-stu-id="2af80-238">Default: Entire Time</span></span>

<span data-ttu-id="2af80-239">**OutputFolder:** La carpeta en la que se colocarán las imágenes de ChatUsageReport. html y del gráfico.</span><span class="sxs-lookup"><span data-stu-id="2af80-239">**OutputFolder:** The folder where the ChatUsageReport.html and the graph images will be placed.</span></span> <span data-ttu-id="2af80-240">Debe definirse en el archivo de configuración o en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="2af80-240">This must be defined in the config file or on the command line.</span></span>

<span data-ttu-id="2af80-241">Todos los valores de parámetros de la línea de comandos también se pueden especificar en el archivo ChatUsageReport. exe. config que se encuentra en el mismo directorio que la herramienta.</span><span class="sxs-lookup"><span data-stu-id="2af80-241">All of the command line parameter values can also be specified in the ChatUsageReport.exe.config file that is located in the same directory as the tool.</span></span> <span data-ttu-id="2af80-242">Si se especifica un valor en el archivo de configuración y en la línea de comandos, el valor de la línea de comandos invalidará el valor del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="2af80-242">If any value is specified in both the config file and the command line, the command line value will override the config file value.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="2af80-243">Output</span><span class="sxs-lookup"><span data-stu-id="2af80-243">Output</span></span>

<span data-ttu-id="2af80-244">El informe siempre incluirá el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="2af80-244">The report will always include the following output:</span></span>

  - <span data-ttu-id="2af80-245">Principales n salones de chat activos por número de publicaciones de mensajes durante el período seleccionado.</span><span class="sxs-lookup"><span data-stu-id="2af80-245">Top n most active chat rooms by number of message posts for selected period.</span></span>

  - <span data-ttu-id="2af80-246">Principales n usuarios activos por número de publicaciones de mensajes durante el período seleccionado.</span><span class="sxs-lookup"><span data-stu-id="2af80-246">Top n most active users by number of message posts for selected period.</span></span>

  - <span data-ttu-id="2af80-247">Principales n salones de chat activos como mínimo por número de publicaciones de mensajes para el período seleccionado.</span><span class="sxs-lookup"><span data-stu-id="2af80-247">Top n least active chat rooms by number of message posts for selected period.</span></span>

  - <span data-ttu-id="2af80-248">Salones de chat que están inactivos durante toda la vida de la base de datos o desde la fecha especificada.</span><span class="sxs-lookup"><span data-stu-id="2af80-248">Chat rooms that are inactive for the entire life of the database, or since the specified date.</span></span>

  - <span data-ttu-id="2af80-249">Tendencia diaria de exposición de mensajes para el período seleccionado.</span><span class="sxs-lookup"><span data-stu-id="2af80-249">Daily message post trend for selected period.</span></span>

  - <span data-ttu-id="2af80-250">Tendencia semanal de exposición de mensajes para el período seleccionado.</span><span class="sxs-lookup"><span data-stu-id="2af80-250">Weekly message post trend for selected period.</span></span>

  - <span data-ttu-id="2af80-251">Tendencia mensual de post de mensaje para el período seleccionado.</span><span class="sxs-lookup"><span data-stu-id="2af80-251">Monthly message post trend for selected period.</span></span>

  - <span data-ttu-id="2af80-252">Total de publicaciones de mensajes para el período seleccionado.</span><span class="sxs-lookup"><span data-stu-id="2af80-252">Total message posts for selected period.</span></span>

  - <span data-ttu-id="2af80-253">Número total de salones habilitados.</span><span class="sxs-lookup"><span data-stu-id="2af80-253">Total number of enabled rooms.</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="2af80-254">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2af80-254">Example</span></span>

<span data-ttu-id="2af80-255">En el siguiente ejemplo se genera un informe de uso para todo el año 2001 y se coloca el informe en el OutputFolder especificado en ChatUsageReport. exe. config.</span><span class="sxs-lookup"><span data-stu-id="2af80-255">The following example generates a usage report for the entire year 2001 and places the report in the OutputFolder specified in the ChatUsageReport.exe.config.</span></span>

```Powershell
    ChatUsageReport -RoomsInactiveSince 06-20-2010
```
<span data-ttu-id="2af80-256">ChatUsageReport. exe. config:</span><span class="sxs-lookup"><span data-stu-id="2af80-256">ChatUsageReport.exe.config:</span></span>

```XML
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <connectionStrings>
        <!-- The PersistentChat connection string must be defined in this file. -->
        <add name="PersistentChat" connectionString="Data Source=contoso.com\RTC;Initial Catalog=mgc;Integrated Security=SSPI"/>
      </connectionStrings>
      <appSettings>
        <!-- The OutputFolder must be defined here or on the command line. -->
        <add key="OutputFolder" value="."/>
        <!-- The values below are the same as the application defaults. -->
        <add key="StartDate" value="01/01/0001"/>
        <add key="EndDate" value="12/31/9999"/>
        <add key="TopActiveUsers" value="10"/>
        <add key="TopActiveRooms" value="10"/>
        <add key="LeastActiveRooms" value="10"/>
        <add key="RoomsInactiveSince" value="01/01/0001"/>
      </appSettings>
    </configuration></configuration>
```
</div>

</div>

<div>

## <a name="scheduleadsyncforprincipal"></a><span data-ttu-id="2af80-257">ScheduleADSyncForPrincipal</span><span class="sxs-lookup"><span data-stu-id="2af80-257">ScheduleADSyncForPrincipal</span></span>

<div>

## <a name="description"></a><span data-ttu-id="2af80-258">Descripción</span><span class="sxs-lookup"><span data-stu-id="2af80-258">Description</span></span>

<span data-ttu-id="2af80-259">ScheduleADSyncForPrincipal es un script de Microsoft SQL Server 2012 que debe ejecutarse directamente desde dentro de SQL Server Management Studio cuando se conecta a la base de datos back-end de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="2af80-259">ScheduleADSyncForPrincipal is a Microsoft SQL Server 2012 script that must be run directly from within SQL Server Management Studio when connected to the Persistent Chat back-end database.</span></span> <span data-ttu-id="2af80-260">Esta secuencia de comandos permite forzar el chat persistente para que sincronice sus registros de un usuario con los de servicios de dominio de Active Directory, en lugar de esperar el tiempo de sincronización programado.</span><span class="sxs-lookup"><span data-stu-id="2af80-260">This script enables you to force Persistent Chat to synchronize its records of a user with those of Active Directory Domain Services, rather than waiting for the scheduled synchronization time.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="2af80-261">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2af80-261">Requirements</span></span>

<span data-ttu-id="2af80-262">La cuenta de usuario con la que se ejecuta el script debe tener acceso de propietario a la base de datos back-end de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="2af80-262">The user account under which the script is run must have owner access to the Persistent Chat back-end database.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="2af80-263">Uso</span><span class="sxs-lookup"><span data-stu-id="2af80-263">Usage</span></span>

<span data-ttu-id="2af80-264">A continuación se muestran los contenidos de la secuencia de comandos predeterminada:</span><span class="sxs-lookup"><span data-stu-id="2af80-264">Following are the contents of the default script:</span></span>

```Powershell
    /*
    This script will schedule a principal for a forced AD synchronization cycle
    
    If you're using Sql Server Management Studio, pressing Ctrl+Shift+M will 
    allow you to specify values for the template parameter.
    */
    
        insert into
          tblPrincipalMeta
          (
           prinID
          ,prinAffiliationsDirty
          ,prinAttributesDirty
          ,prinDeleted
          )
          select
            prinID
           ,1
           ,1
           ,0
          from
            tblPrincipal
          where
            prinID not in (select prinID from tblPrincipalMeta) and
            prinID = <PrinID,int,0>
     
        update
          tblPrincipalMeta
        set
          prinAffiliationsDirty = 1
         ,prinAttributesDirty = 1
         ,tryCount = 0
         ,nextTry = null
        where
         prinID = <PrinID,int,0>
```

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

