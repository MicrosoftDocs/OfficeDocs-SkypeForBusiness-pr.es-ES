---
title: 'Lync Server 2013: uso de Microsoft SQL Server 2008 R2 como base de datos de System Center Operations Manager'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database
ms:assetid: 0efe76da-8854-499e-bdc7-3623244a8e85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687969(v=OCS.15)
ms:contentKeyID: 49733555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ad7854043eb85db7b5d260d57beed26746160f5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044312"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database-for-lync-server-2013"></a><span data-ttu-id="d999a-102">Uso de Microsoft SQL Server 2008 R2 como base de datos de System Center Operations Manager para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d999a-102">Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d999a-103">_**Última modificación del tema:** 2013-07-29_</span><span class="sxs-lookup"><span data-stu-id="d999a-103">_**Topic Last Modified:** 2013-07-29_</span></span>

<span data-ttu-id="d999a-104">Para usar SQL Server 2008 R2 como base de datos back-end, complete los pasos que se detallan en este tema.</span><span class="sxs-lookup"><span data-stu-id="d999a-104">To use SQL Server 2008 R2 as your back-end database, complete the steps detailed in this topic.</span></span>

<div>

## <a name="configuring-sql-server-2008-r2-and-sql-server-reporting-services"></a><span data-ttu-id="d999a-105">Configuración de SQL Server 2008 R2 y SQL Server Reporting Services</span><span class="sxs-lookup"><span data-stu-id="d999a-105">Configuring SQL Server 2008 R2 and SQL Server Reporting Services</span></span>

<span data-ttu-id="d999a-106">Antes de empezar a instalar System Center Operations Manager, debe realizar dos cambios en su SQL Server 2008 R2 y en la configuración de SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="d999a-106">Before you begin installing System Center Operations Manager you must make two changes to your SQL Server 2008 R2 and your SQL Server Reporting Services configuration.</span></span> <span data-ttu-id="d999a-107">(Estos cambios solo son necesarios si usa SQL Server 2008 R2 como su base de datos de Operations Manager). En primer lugar, haga lo siguiente en el equipo donde se va a hospedar la base de datos de Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="d999a-107">(These changes are required only if you are using SQL Server 2008 R2 as your Operations Manager database.) First, do the following on the computer that will host your Operations Manager database:</span></span>

1.  <span data-ttu-id="d999a-108">Haga clic en **Inicio** y, a continuación, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="d999a-108">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="d999a-109">En el cuadro de diálogo **Ejecutar** , **escriba C\\: archivos\\de programa Microsoft\\ SQL\_Server MSRS10 50\\. ARCHINST\\Reporting Services ReportServer** y, a continuación, presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="d999a-109">In the **Run** dialog box, type **C:\\Program Files\\Microsoft SQL Server\\ MSRS10\_50.ARCHINST\\Reporting Services\\ReportServer** and then press ENTER.</span></span>

3.  <span data-ttu-id="d999a-110">En la carpeta **ReportServer**, abra el archivo **rsreportserver.config** en Notepad o cualquier otro editor de texto.</span><span class="sxs-lookup"><span data-stu-id="d999a-110">In the **ReportServer** folder, open the file **rsreportserver.config** in Notepad or any other text editor.</span></span>

4.  <span data-ttu-id="d999a-111">Cerca del comienzo del archivo verá una serie de nodos "Add Key".</span><span class="sxs-lookup"><span data-stu-id="d999a-111">Near the beginning of the file you will see a series of "Add Key" nodes.</span></span> <span data-ttu-id="d999a-112">Busque la entrada que comienza \*\* \<con Add key = "SecureConnectionLevel"\*\* y establezca el valor en **0**:</span><span class="sxs-lookup"><span data-stu-id="d999a-112">Find the entry that begins **\<Add Key="SecureConnectionLevel"** and set the value to **0**:</span></span>
    
        <Add Key="SecureConnectionLevel" Value="0"/>

5.  <span data-ttu-id="d999a-113">Guarde el archivo **rsreportserver.config** y luego cierre el editor de texto.</span><span class="sxs-lookup"><span data-stu-id="d999a-113">Save the file **rsreportserver.config** and then close your text editor.</span></span>

<span data-ttu-id="d999a-p103">Después de actualizar el archivo de configuración del servidor de informes debe asignar el certificado correcto a SQL Server Reporting Services. Para ello:</span><span class="sxs-lookup"><span data-stu-id="d999a-p103">After updating the Report Server configuration file you must then assign the correct certificate to SQL Server Reporting Services. To do that:</span></span>

1.  <span data-ttu-id="d999a-116">Haga clic en **Inicio**, en **todos los programas**, en **Microsoft SQL Server 2008 R2**, en **herramientas de configuración**y, a continuación, en Administrador de **configuración de Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="d999a-116">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>

2.  <span data-ttu-id="d999a-117">En el cuadro de diálogo **Conexión de configuración de Reporting Services**, asegúrese de que el nombre de su servidor aparece en el cuadro **Nombre del servidor**.</span><span class="sxs-lookup"><span data-stu-id="d999a-117">In the **Reporting Services Configuration Connection** dialog box, make sure that the name of your server appears in the **Server Name** box.</span></span> <span data-ttu-id="d999a-118">Seleccione la instancia de SQL Server que va a hospedar la base de datos de Operations Manager (por ejemplo, **ARCHINST**) en la lista desplegable **instancia del servidor de informes** y, a continuación, haga clic en **conectar**.</span><span class="sxs-lookup"><span data-stu-id="d999a-118">Select the SQL Server instance that will host your Operations Manager database (for example, **ARCHINST**) from the **Report Server Instance** drop-down list and then click **Connect**.</span></span>

3.  <span data-ttu-id="d999a-119">En el Administrador de configuración de Reporting Services, haga clic en **Dirección URL del servicio web**.</span><span class="sxs-lookup"><span data-stu-id="d999a-119">In Reporting Services Configuration Manager, click **Web Service URL**.</span></span>

4.  <span data-ttu-id="d999a-p105">En la página **Dirección URL del servicio web**, seleccione el certificado que se usará para Reporting Services de la lista desplegable **Certificado SSL** y luego haga clic en **Aplicar**. Después de unos segundos, verá un par de direcciones URL debajo de **Direcciones URL del servicio web del servidor de informes**.</span><span class="sxs-lookup"><span data-stu-id="d999a-p105">On the **Web Service URL** page, select the certificate to be used for your Reporting Services from the **SSL Certificate** dropdown list and then click **Apply**. After a few seconds, you will see a pair of URLs listed under **Report Server Web Service URLs**.</span></span>

5.  <span data-ttu-id="d999a-122">Haga clic en ambas direcciones URL para verificar que puede acceder a SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="d999a-122">Click both of the URLs to verify that you can access SQL Server Reporting Services.</span></span>

6.  <span data-ttu-id="d999a-123">Cierre el Administrador de configuración de Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="d999a-123">Close Reporting Services Configuration Manager.</span></span>

</div>

<div>

## <a name="creating-a-system-center-operations-manager-database-for-use-with-sql-server-2008-r2"></a><span data-ttu-id="d999a-124">Creación de una base de datos de System Center Operations Manager para usarla con SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="d999a-124">Creating a System Center Operations Manager database for use with SQL Server 2008 R2</span></span>

<span data-ttu-id="d999a-125">Si desea configurar System Center Operations Manager para usar una base de datos de SQL Server 2008 R2, deberá "crear manualmente" la base de datos de Operations Manager en el equipo que ejecuta SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="d999a-125">If you want to configure System Center Operations Manager to use a SQL Server 2008 R2 database, you will need to "manually" create the Operations Manager database on the computer running SQL Server 2008 R2.</span></span> <span data-ttu-id="d999a-126">(De nuevo, estos pasos no son necesarios si utiliza SQL Server 2005 o SQL Server 2008 como base de datos back-end.)</span><span class="sxs-lookup"><span data-stu-id="d999a-126">(Again, these steps are not required if you are using SQL Server 2005 or SQL Server 2008 as your back-end database.)</span></span>

<span data-ttu-id="d999a-127">Para crear manualmente una base de datos de Operations Manager, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d999a-127">To manually create an Operations Manager database do the following:</span></span>

1.  <span data-ttu-id="d999a-128">En el medio de instalación de System Center Operations Manager 2007 R2,\\en la carpeta SupportTools AMD64, haga doble clic en **DBCreateWizard. exe**.</span><span class="sxs-lookup"><span data-stu-id="d999a-128">On the System Center Operations Manager 2007 R2 setup media, in the SupportTools\\AMD64 folder, double-click **DBCreateWizard.exe**.</span></span>

2.  <span data-ttu-id="d999a-129">En el Asistente de configuración de la base de datos, en la página **Bienvenido al Asistente de configuración de la base de datos**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d999a-129">In the Database Configuration Wizard, on the **Welcome to the Database Configuration Wizard** page, click **Next**.</span></span>

3.  <span data-ttu-id="d999a-130">En la página **Información de base de datos** deje todas las opciones de configuración como se encuentran y luego haga clic en **Siguiente**</span><span class="sxs-lookup"><span data-stu-id="d999a-130">On the **Database Information** page leave all the settings as-is and then click **Next**</span></span>

4.  <span data-ttu-id="d999a-131">En la **página Configuración del grupo de administración** , escriba un nombre para el grupo de administración (por ejemplo, supervisión de **Lync Server**) en el cuadro **nombre del grupo de administración** y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d999a-131">On the **Management Group Configuration** page type a name for your Management Group (for example, **Lync Server Monitoring**) in the **Management Group name** box and then click **Next**.</span></span>

5.  <span data-ttu-id="d999a-132">En la página **Informes de error de Operations Manager** haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d999a-132">On the **Operations Manager Error Reports** page click **Next**.</span></span>

6.  <span data-ttu-id="d999a-133">En la página **Resumen** haga clic en \*\*Finalizar \*\*.</span><span class="sxs-lookup"><span data-stu-id="d999a-133">On the **Summary** page click **Finish**.</span></span>

</div>

<div>

## <a name="creating-a-system-center-operations-manager-data-warehouse-for-use-with-sql-server-2008-r2"></a><span data-ttu-id="d999a-134">Creación de un almacén de datos de System Center Operations Manager para usarlo con SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="d999a-134">Creating a System Center Operations Manager data warehouse for use with SQL Server 2008 R2</span></span>

<span data-ttu-id="d999a-135">Microsoft Lync Server 2013 incluye tres nuevos informes de System Center Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="d999a-135">Microsoft Lync Server 2013 ships with three new System Center Operations Manager reports:</span></span>

  - <span data-ttu-id="d999a-136">**Informe de disponibilidad de escenario de principio a fin**   este informe detalla la disponibilidad o el tiempo activo para los servicios clave de Lync Server, como el registro o la presencia.</span><span class="sxs-lookup"><span data-stu-id="d999a-136">**End to End Scenario Availability Report**   This report details the availability/uptime for key Lync Server services such as registration or presence.</span></span>

  - <span data-ttu-id="d999a-137">**Informe de capacidad**   con información de contador de rendimiento, este informe muestra las tendencias de los componentes del sistema, como la disponibilidad de la memoria y el uso del procesador.</span><span class="sxs-lookup"><span data-stu-id="d999a-137">**Capacity Report**   Using performance counter information, this report shows trends for system components such as memory availability and processor usage.</span></span>

  - <span data-ttu-id="d999a-138">**Informe de componentes**   este informe enumera los principales generadores de alertas agrupados por el componente de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d999a-138">**Component Report**   This report lists the top alert generators grouped by Lync Server component.</span></span>

<span data-ttu-id="d999a-139">Para poder usar estos nuevos informes, debe instalar un almacén de datos de System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="d999a-139">In order to use these new reports you must install a System Center Operations Manager data warehouse.</span></span> <span data-ttu-id="d999a-140">(Un almacén de datos proporciona almacenamiento a largo plazo de datos de operaciones). Para usar un almacén de datos con SQL Server 2008 R2, debe llevar a cabo los siguientes pasos en el equipo que hospeda la base de datos de SQL Server:</span><span class="sxs-lookup"><span data-stu-id="d999a-140">(A data warehouse provides for long-term storage of operations data.) To use a data warehouse with SQL Server 2008 R2 you must carry out the following steps on the computer that hosts your SQL Server database:</span></span>

1.  <span data-ttu-id="d999a-141">En el medio de instalación de System Center Operations Manager,\\en\\la carpeta SETUP SupportTools AMD64, haga doble clic en **DBCreateWizard. exe**.</span><span class="sxs-lookup"><span data-stu-id="d999a-141">On the System Center Operations Manager setup media, in the Setup\\SupportTools\\AMD64 folder, double-click **DBCreateWizard.exe**.</span></span>

2.  <span data-ttu-id="d999a-142">En el Asistente de configuración de la base de datos, en la página **Bienvenido al Asistente de configuración de la base de datos**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d999a-142">In the Database Configuration Wizard, on the **Welcome to the Database Configuration Wizard** page, click **Next**.</span></span>

3.  <span data-ttu-id="d999a-143">En la página **Información de base de datos**, seleccione **Base de datos del almacén de datos de Operations Manager** de la lista desplegable **Tipo de base de datos** y luego haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d999a-143">On the **Database Information** page, select **Operations Manager Data Warehouse Database** from the **Database Type** dropdown list and then click **Next**.</span></span>

4.  <span data-ttu-id="d999a-144">En la página **Resumen** haga clic en \*\*Finalizar \*\*.</span><span class="sxs-lookup"><span data-stu-id="d999a-144">On the **Summary** page click **Finish**.</span></span>

</div>

<div>

## <a name="installing-the-system-center-operations-manager-console"></a><span data-ttu-id="d999a-145">Instalación de la consola de System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="d999a-145">Installing the System Center Operations Manager console</span></span>

<span data-ttu-id="d999a-146">La consola de Operations Manager es la principal herramienta que se usa para administrar System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="d999a-146">The Operations Manager console is the primary tool used to manage System Center Operations Manager.</span></span> <span data-ttu-id="d999a-147">Antes de instalar la consola de Operations Manager, asegúrese de que ha instalado una versión compatible de SQL Server junto con el servicio de informes de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d999a-147">Before you install the Operations Manager console, make sure that you have installed a supported version of SQL Server along with the SQL Server Reporting Service.</span></span> <span data-ttu-id="d999a-148">También se recomienda que ejecute el Administrador de configuración de SQL Server's Reporting Services para verificar que Reporting Service se ha instalado y configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="d999a-148">It is also recommended that you run SQL Server's Reporting Services Configuration Manager to verify that the Reporting Service has been correctly installed and configured.</span></span>

<span data-ttu-id="d999a-149">Para instalar la consola de System Center Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="d999a-149">To install the System Center Operations Manager console:</span></span>

1.  <span data-ttu-id="d999a-150">En el medio de instalación de System Center Operations Manager, haga doble clic en **SetupOM. exe**.</span><span class="sxs-lookup"><span data-stu-id="d999a-150">On the System Center Operations Manager setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="d999a-151">En System Center Operations Manager 2007 R2 Setup, haga clic en **comprobar requisitos previos**.</span><span class="sxs-lookup"><span data-stu-id="d999a-151">In System Center Operations Manager 2007 R2 Setup, click **Check Prerequisites**.</span></span>

3.  <span data-ttu-id="d999a-152">En el visor de requisitos previos de System Center Operations Manager, seleccione los componentes de System Center que se van a instalar: (**servidor**; **Consola**; y **PowerShell**) y, a continuación, haga clic en **comprobar**.</span><span class="sxs-lookup"><span data-stu-id="d999a-152">In the System Center Operations Manager Prerequisite Viewer, select the System Center components to be installed: (**Server**; **Console**; and **PowerShell**) and then click **Check**.</span></span> <span data-ttu-id="d999a-153">Verifique que no se haya informado ningún problema de bloqueo y luego haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="d999a-153">Verify that no blocking issues have been reported and then click **Close**.</span></span> <span data-ttu-id="d999a-154">Si se ha informado algún problema de bloqueo, corrija el problema y luego haga clic en **Comprobar** para volver a ejecutar la comprobación de requisitos.</span><span class="sxs-lookup"><span data-stu-id="d999a-154">If a blocking issue has been reported, correct the problem and then click **Check** to re-run the prerequisite testing.</span></span>

4.  <span data-ttu-id="d999a-155">En el programa de instalación de System Center Operations Manager, haga clic en **instalar Operations Manager**.</span><span class="sxs-lookup"><span data-stu-id="d999a-155">In System Center Operations Manager Setup, click **Install Operations Manager**.</span></span>

5.  <span data-ttu-id="d999a-156">En el Asistente para la instalación de System Center Operations Manager, en la página **éste es el Asistente para la instalación de System Center Operations Manager** , haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d999a-156">In the System Center Operations Manager Setup wizard, on the **Welcome to the System Center Operations Manager Setup Wizard** page, click **Next**.</span></span>

6.  <span data-ttu-id="d999a-157">En la página **Contrato de licencia de usuario final**, seleccione **Acepto los términos del contrato de licencia** y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d999a-157">On the **End-User License Agreement** page, select **I accept the terms in the license agreement** and then click **Next**.</span></span>

7.  <span data-ttu-id="d999a-158">En la página **Registro del producto**, escriba su nombre en el cuadro **Nombre de usuario** y el nombre de su organización en el cuadro **Organización**.</span><span class="sxs-lookup"><span data-stu-id="d999a-158">On the **Product Registration** page, type your name in the **User Name** box and name of your organization in the **Organization** box.</span></span> <span data-ttu-id="d999a-159">Escriba la clave del producto System Center Operations Manager en el cuadro **Escriba la clave del CD de 25 dígitos** y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d999a-159">Type your System Center Operations Manager product key in the **Enter your 25 digit CD Key** box and then click **Next**.</span></span>

8.  <span data-ttu-id="d999a-p111">En la página **Instalación personalizada** seleccione las opciones de System Center que desea instalar y luego haga clic en **Siguiente**. Debe seleccionar **Servidor de administración**, **Interfaces de usuario** y **Consola web** para su instalación. **Base de datos** no debería seleccionarse ni instalarse.</span><span class="sxs-lookup"><span data-stu-id="d999a-p111">On the **Custom Setup** page select the System Center options to be installed and then click **Next**. You should select **Management Server**, **User Interfaces**, and **Web Console** to be installed. **Database** should not be selected and should not be installed.</span></span>

9.  <span data-ttu-id="d999a-163">En la página **instancia de servidor de base de datos de SC** , compruebe que el nombre del equipo en el que están instaladas las bases de datos de Operations Manager aparece en el cuadro servidor de base de datos de **System Center** .</span><span class="sxs-lookup"><span data-stu-id="d999a-163">On the **SC Database Server Instance** page, verify that the name of the computer where the Operations Manager databases are installed appears in the **System Center Database Server** box.</span></span> <span data-ttu-id="d999a-164">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d999a-164">Click **Next**.</span></span>

10. <span data-ttu-id="d999a-p113">En la página **Cuenta de acción de los servidores de administración**, seleccione **Cuenta de equipo local o del dominio** y luego introduzca los valores apropiados en los cuadros **Cuenta de usuario**, **Contraseña** y **Equipo local o del dominio**. Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d999a-p113">On the **Management Server Action Account** page, select **Domain or Local Computer Account** and then enter the appropriate values in the **User Account**, **Password**, and **Domain or local computer** boxes. Click **Next**.</span></span>

11. <span data-ttu-id="d999a-p114">En la página **Cuenta de servicio de configuración y SDK**, seleccione **Cuenta de equipo local o del dominio** y luego introduzca los valores apropiados en los cuadros **Cuenta de usuario**, **Contraseña** y **Equipo local o del dominio**. Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d999a-p114">On the **SDK and Config Service Account** page, select **Domain or Local Computer Account** and then enter the appropriate values in the **User Account**, **Password**, and **Domain or local computer** boxes. Click **Next**.</span></span>

12. <span data-ttu-id="d999a-169">En la página **Informes de error de Operations Manager** haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d999a-169">On the **Operations Manager Error Reports** page click **Next**.</span></span>

13. <span data-ttu-id="d999a-170">En la página **Programa para la mejora de la experiencia del usuario** haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d999a-170">On the **Customer Experience Improvement Program** page click **Next**.</span></span>

14. <span data-ttu-id="d999a-171">En la página **Listo para instalar el programa**, haga clic en **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="d999a-171">On the **Ready to Install the Program** page, click **Install**.</span></span>

15. <span data-ttu-id="d999a-172">En la página **Completar la instalación de System Center Operations Manager**, desactive las casillas **Clave de cifrado de copias de seguridad** y **Iniciar la consola** y luego haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="d999a-172">On the **Completing the System Center Operations Manager Setup** page, clear the **Backup Encryption Key** and **Start the console checkboxes** and then click **Finish**.</span></span>

16. <span data-ttu-id="d999a-173">En el programa de instalación de System Center Operations Manager, haga clic en **salir**.</span><span class="sxs-lookup"><span data-stu-id="d999a-173">In System Center Operations Manager Setup click **Exit**.</span></span>

</div>

<div>

## <a name="installing-system-center-reporting-services"></a><span data-ttu-id="d999a-174">Instalación de System Center Reporting Services</span><span class="sxs-lookup"><span data-stu-id="d999a-174">Installing System Center Reporting Services</span></span>

<span data-ttu-id="d999a-175">Después de instalar y configurar la consola de System Center Operations Manager, debe instalar System Center Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="d999a-175">After installing and configuring the System Center Operations Manager console you must then install System Center Reporting Services.</span></span> <span data-ttu-id="d999a-176">Si usa SQL Server 2008 R2 como base de datos back-end de Operations Manager, significa que primero debe realizar un cambio temporal en el grupo de seguridad asociado con SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="d999a-176">If you are using SQL Server 2008 R2 as your Operations Manager back-end database, that means that you must first make a temporary change to the security group associated with SQL Server Reporting Services.</span></span> <span data-ttu-id="d999a-177">Si usa SQL Server 2008 R2, debe hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d999a-177">If you are using SQL Server 2008 R2, you must do the following:</span></span>

1.  <span data-ttu-id="d999a-178">Haga clic en **Inicio**, elija **Herramientas administrativas** y, a continuación, haga clic en **Administrador de servidores**.</span><span class="sxs-lookup"><span data-stu-id="d999a-178">Click **Start**, point to **Administrative Tools**, and then click **Server Manager**.</span></span>

2.  <span data-ttu-id="d999a-179">En Administrador de servidores, expanda **Configuración**, expanda **Usuarios y grupos locales** y, a continuación, haga clic en **Grupos**.</span><span class="sxs-lookup"><span data-stu-id="d999a-179">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="d999a-180">Busque el siguiente grupo, donde ATL-SC-001 representa el nombre de su equipo y ARCHINST representa la instancia de SQL Server para la base de datos de System Center: **SQLServerReportServerUser $ ATL-SC\_-001 $ MSRS10 50. ARCHINST**.</span><span class="sxs-lookup"><span data-stu-id="d999a-180">Locate the following group, where atl-sc-001 represents the name of your computer and ARCHINST represents the SQL Server instance for the System Center database: **SQLServerReportServerUser$atl-sc-001$MSRS10\_50.ARCHINST**.</span></span>

4.  <span data-ttu-id="d999a-181">Haga clic con el botón secundario en el grupo y, a continuación, haga clic en **Cambiar nombre**.</span><span class="sxs-lookup"><span data-stu-id="d999a-181">Right-click the group and then click **Rename**.</span></span> <span data-ttu-id="d999a-182">Cambie el nombre del grupo eliminando \*\* \_50\*\* del nombre del grupo.</span><span class="sxs-lookup"><span data-stu-id="d999a-182">Rename the group by deleting **\_50** from the group name.</span></span> <span data-ttu-id="d999a-183">Por ejemplo: **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10. ARCHINST**.</span><span class="sxs-lookup"><span data-stu-id="d999a-183">For example: **SQLServerReportServerUser$atl-sc-001$MSRS10.ARCHINST**.</span></span>

5.  <span data-ttu-id="d999a-184">Cierre el Administrador de servidores.</span><span class="sxs-lookup"><span data-stu-id="d999a-184">Close Server Manager.</span></span>

<span data-ttu-id="d999a-p117">Ahora está listo para instalar System Center Reporting Services. Para ello:</span><span class="sxs-lookup"><span data-stu-id="d999a-p117">At this point you are ready to install System Center Reporting Services. To do this:</span></span>

1.  <span data-ttu-id="d999a-187">En el medio de instalación de System Center Operations Manager 2007 R2, haga doble clic en **SetupOM. exe**.</span><span class="sxs-lookup"><span data-stu-id="d999a-187">On the System Center Operations Manager 2007 R2 Setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="d999a-188">En el programa de instalación de System Center Operations Manager 2007 R2, haga clic en **instalar informes de Operations Manager**.</span><span class="sxs-lookup"><span data-stu-id="d999a-188">In System Center Operations Manager 2007 R2 Setup, click **Install Operations Manager Reporting**.</span></span>

3.  <span data-ttu-id="d999a-189">En el Asistente para la instalación de informes de System Center Operations Manager 2007 R2, en la página de **bienvenida a configuración de informes de Operations Manager** , haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d999a-189">In the System Center Operations Manager 2007 R2 Reporting Setup wizard, on the **Welcome to Operations Manager Reporting Setup** page, click **Next**.</span></span>

4.  <span data-ttu-id="d999a-190">En la página **Contrato de licencia de usuario final**, seleccione **Acepto los términos del contrato de licencia** y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d999a-190">On the **End-user License Agreement** page select **I accept the terms of the license agreement** and then click **Next**.</span></span>

5.  <span data-ttu-id="d999a-191">En la página **Registro del producto**, asegúrese de que su nombre y el nombre de la organización aparecen en los cuadros **Nombre de usuario** y **Organización** y luego haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d999a-191">On the **Product Registration** page, ensure that your name and the name of your organization appear in the **User Name** and **Organization** boxes and then click **Next**.</span></span>

6.  <span data-ttu-id="d999a-p118">En la página **Instalación personalizada**, haga clic en **Reporting Server** y seleccione **Este componente y todos los componentes que dependan de él se instalarán en el disco duro local**. Haga clic en **Almacén de datos** y seleccione **Este componente no estará disponible** y luego haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d999a-p118">On the **Custom Setup** page, click **Reporting Server** and select **This component, and all dependent components, will be installed on local disk drive**. Click **Data Warehouse** and select **This component will not be available**, and then click **Next**.</span></span>

7.  <span data-ttu-id="d999a-194">En la página **Conectarse con el servidor de administración raíz**, escriba el nombre de su servidor de administración raíz Operations Manager en el cuadro **Servidor de administración raíz** y luego haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d999a-194">On the **Connect to the Root Management Server** page, type the name of your Operations Manager root management server in the **Root Management Server** box and then click **Next**.</span></span>

8.  <span data-ttu-id="d999a-p119">En la página **Conectarse con el almacén de datos de Operations Manager**, escriba la instancia de SQL Server en la que se encuentra su almacén de datos en el cuadro **Instancia de SQL Server**. (Si su almacén de datos se encuentra en la instancia Predeterminado escriba simplemente el nombre del servidor; por ejemplo: atl-sql-001). Verifique que el nombre de la base de datos **OperationsManagerDW** aparezca en el cuadro **Nombre** y que el puerto **1433** aparezca en el cuadro **puerto de SQL Server**. Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d999a-p119">On the **Connect to the Operations Manager Data Warehouse** page, type the SQL Server instance where your data warehouse is located in the **SQL Server Instance** box. (If your data warehouse is located in the Default instance then simply type the server name; for example: atl-sql-001.) Verify that the database name **OperationsManagerDW** appears in the **Name** box, and that port **1433** appears in the **SQL Server port** box. Click **Next**.</span></span>

9.  <span data-ttu-id="d999a-198">En la página **Instancia de SQL Server Reporting**, seleccione su servidor de SQL Server Reporting de la lista desplegable**Introduzca el servidor de SQL Server Reporting Services** y luego haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d999a-198">On the **SQL Server Reporting Instance** page, select your SQL Server reporting server from the **Enter the SQL Server Reporting Services Server** dropdown list and then click **Next**.</span></span>

10. <span data-ttu-id="d999a-p120">En la página **Cuenta de escritura de almacén de datos**, introduzca el nombre y la contraseña del usuario al que se le asignarán inicialmente permisos de escritura en el almacén de datos en los cuadros **Cuenta de usuario** y **Contraseña**. Seleccione el dominio del usuario de la lista desplegable **Dominio** y luego haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d999a-p120">On the **Data Warehouse Write Account** page, enter the name and password of the user to be initially assigned write permissions to the data warehouse in the **User Account** and **Password** boxes. Select the user's domain from the **Domain** dropdown list and then click **Next**.</span></span>

11. <span data-ttu-id="d999a-p121">En la página **Cuenta de lectura de datos**, introduzca el nombre y la contraseña de la cuenta de usuario que se utilizará cuando SQL Reporting Services realice consultas en el almacén de datos en los cuadros **Cuenta de usuario** y **Contraseña**. Seleccione el dominio de la cuenta de la lista desplegable **Dominio** y luego haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d999a-p121">On the **Data Reader Account** page, enter the name and password of the user account to be used when SQL Reporting Services queries the data warehouse in the **User Account** and **Password** boxes. Select the account domain from the **Domain** dropdown list and then click **Next**.</span></span>

12. <span data-ttu-id="d999a-203">En la página **Informes de datos operativos**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d999a-203">On the **Operational Data Reports** page, click **Next**.</span></span>

13. <span data-ttu-id="d999a-204">En la página **Actualización de Microsoft**, haga clic en \*\*Siguiente \*\*.</span><span class="sxs-lookup"><span data-stu-id="d999a-204">On the **Microsoft Update** page, click **Next**.</span></span>

14. <span data-ttu-id="d999a-205">En la página **Listo para instalar el programa**, haga clic en **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="d999a-205">On the **Ready to Install the Program** page, click **Install**.</span></span>

15. <span data-ttu-id="d999a-206">En la página **Finalización del Asistente de instalación de los componentes de Operations Manager Reporting**, haga clic en \*\*Finalizar \*\*.</span><span class="sxs-lookup"><span data-stu-id="d999a-206">On the **Completing the Operations Manager Reporting Components Setup Wizard** page, click **Finish**.</span></span>

16. <span data-ttu-id="d999a-207">En System Center Operations Manager 2007 R2 Setup, haga clic en **salir**.</span><span class="sxs-lookup"><span data-stu-id="d999a-207">In System Center Operations Manager 2007 R2 Setup, click **Exit**.</span></span>

<span data-ttu-id="d999a-208">Después de instalar los informes de System Center, use el siguiente procedimiento para restablecer el nombre del grupo de seguridad asociado con los informes de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d999a-208">After System Center reporting has been installed you then use the following procedure to reset the name of the security group associated with SQL Server reporting.</span></span> <span data-ttu-id="d999a-209">De nuevo, este procedimiento solo es necesario si usa SQL Server:</span><span class="sxs-lookup"><span data-stu-id="d999a-209">Again, this procedure is only required if you are using SQL Server:</span></span>

1.  <span data-ttu-id="d999a-210">Haga clic en **Inicio**, elija **Herramientas administrativas** y, a continuación, haga clic en **Administrador de servidores**.</span><span class="sxs-lookup"><span data-stu-id="d999a-210">Click **Start**, point to **Administrative Tools**, and then click **Server Manager**.</span></span>

2.  <span data-ttu-id="d999a-211">En Administrador de servidores, expanda **Configuración**, expanda **Usuarios y grupos locales** y, a continuación, haga clic en **Grupos**.</span><span class="sxs-lookup"><span data-stu-id="d999a-211">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="d999a-212">Busque el siguiente grupo, donde ATL-SC-001 representa el nombre de su equipo y ARCHINST representa la instancia de SQL Server para las bases de datos de archivado y supervisión: **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10. ARCHINST**.</span><span class="sxs-lookup"><span data-stu-id="d999a-212">Locate the following group, where atl-sc-001 represents the name of your computer and ARCHINST represents the SQL Server instance for the archiving and monitoring databases: **SQLServerReportServerUser$atl-sc-001$MSRS10.ARCHINST**.</span></span>

4.  <span data-ttu-id="d999a-213">Haga clic con el botón secundario en el grupo y, a continuación, haga clic en **Cambiar nombre**.</span><span class="sxs-lookup"><span data-stu-id="d999a-213">Right-click the group and then click **Rename**.</span></span> <span data-ttu-id="d999a-214">Cambie el nombre del grupo agregando \*\* \_50\*\* al final del nombre del grupo, justo antes del nombre de la instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d999a-214">Rename the group by adding **\_50** to the end of the group name, right before the SQL Server instance name.</span></span> <span data-ttu-id="d999a-215">Por ejemplo: **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10\_50. ARCHINST**.</span><span class="sxs-lookup"><span data-stu-id="d999a-215">For example: **SQLServerReportServerUser$atl-sc-001$MSRS10\_50.ARCHINST**.</span></span>

5.  <span data-ttu-id="d999a-216">Cierre el Administrador de servidores.</span><span class="sxs-lookup"><span data-stu-id="d999a-216">Close Server Manager.</span></span>

<span data-ttu-id="d999a-p124">Si la Consola de operaciones de System Center está abierta, necesitará cerrar la aplicación y volver a abrirla; si no hace esto, la pestaña **Elaboración de informes** no aparecerá en la interfaz de usuario de la Consola de operaciones. Tenga en cuenta que, después de reiniciar la Consola de operaciones por primera vez, podría tomar varios minutos antes de que todos los Informes de supervisión aparezcan en la pestaña **Elaboración de informes**.</span><span class="sxs-lookup"><span data-stu-id="d999a-p124">If the System Center Operations Console is open you will need to close the application and then restart it; if you do not do this the **Reporting** tab will not appear in the Operations Console user interface. Note that, after restarting the Operations Console the first time, it could take several minutes before all the Monitoring Reports appear on the **Reporting** tab.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

