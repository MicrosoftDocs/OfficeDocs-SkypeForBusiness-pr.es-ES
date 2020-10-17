---
title: 'Lync Server 2013: instalar SQL Server Reporting Services'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing SQL Server Reporting Services
ms:assetid: 638a1d0c-1ac7-4735-83f2-4df3d03c7cf9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204957(v=OCS.15)
ms:contentKeyID: 48184345
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9044f90146b604f0277b0a5b815c6540849d58b7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534937"
---
# <a name="installing-sql-server-reporting-services-in-lync-server-2013"></a><span data-ttu-id="0153e-102">Instalar SQL Server Reporting Services en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0153e-102">Installing SQL Server Reporting Services in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0153e-103">_**Última modificación del tema:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="0153e-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="0153e-104">Si tiene previsto usar los informes de supervisión de Microsoft Lync Server 2013 (consulte la siguiente sección de esta documentación para obtener más información), debe instalar primero SQL Server Reporting Services; Reporting Services se puede instalar al mismo tiempo que se instala Microsoft SQL Server o en cualquier momento después de instalar SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0153e-104">If you intend to use Microsoft Lync Server 2013 Monitoring Reports (see the next section of this documentation for more information) you must first install SQL Server Reporting Services; Reporting Services can be installed at the same time you install Microsoft SQL Server or any time after SQL Server has been installed.</span></span> <span data-ttu-id="0153e-105">Esto puede realizarse al mismo tiempo que instala Microsoft SQL Server o con posterioridad.</span><span class="sxs-lookup"><span data-stu-id="0153e-105">If you have not installed SQL Server, then follow the instructions provided earlier in this documentation.</span></span> <span data-ttu-id="0153e-106">Si no ha instalado SQL Server, siga las instrucciones suministradas anteriormente en esta documentación.</span><span class="sxs-lookup"><span data-stu-id="0153e-106">When installing SQL Server, make sure that, on the Feature Selection page, you select Reporting Services.</span></span> <span data-ttu-id="0153e-107">Al instalar SQL Server, asegúrese de que selecciona Reporting Services en la página Selección de características, ya que de este modo se instalará SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="0153e-107">That will install SQL Server Reporting Services.</span></span>

<span data-ttu-id="0153e-108">Si ya tiene instalado SQL Server pero no SQL Server Reporting Services, puede agregar esta característica siguiendo las instrucciones pertinentes de SQL Server 2008 R2 o SQL Server 2012, según proceda.</span><span class="sxs-lookup"><span data-stu-id="0153e-108">If you have already installed SQL Server but did not install SQL Server Reporting Services you can add that feature by following the appropriate set of instructions for SQL Server 2008 R2 or SQL Server 2012, as appropriate.</span></span>

<span data-ttu-id="0153e-109">Siga estos pasos para confirmar que Reporting Services se ha instalado correctamente:</span><span class="sxs-lookup"><span data-stu-id="0153e-109">To verify that the reporting Services have been successfully installed, complete the following steps:</span></span>

1.  <span data-ttu-id="0153e-110">Si ejecuta Microsoft SQL Server 2008 R2, haga clic sucesivamente en **Inicio**, **Todos los programas**, **Microsoft SQL Server 2008 R2**, **Herramientas de configuración** y **Administrador de configuración de Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="0153e-110">If you are running Microsoft SQL Server 2008 R2, then click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>
    
    <span data-ttu-id="0153e-111">Si ejecuta Microsoft SQL Server 2012, haga clic sucesivamente en **Inicio**, **Todos los programas**, **Microsoft SQL Server 2012**, **Herramientas de configuración** y **Administrador de configuración de Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="0153e-111">If you are running Microsoft SQL Server 2012, then click **Start**, click **All Programs**, click **Microsoft SQL Server 2012**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>

2.  <span data-ttu-id="0153e-p102">En el cuadro de diálogo **Conexión de configuración de Reporting Services**, compruebe que el cuadro **Nombre del servidor** refleja el nombre del servidor y, asimismo, que el cuadro **Instancia del servidor de informes** refleja el nombre de la instancia de SQL Server en la que están los datos de supervisión. Haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="0153e-p102">In the **Reporting Services Configuration Connection** dialog box, verify that the name of your server appears in the **Server Name** box and that the name of the SQL Server instance that stores your monitoring data appears in the **Report Server Instance** box. Click **Connect**.</span></span>

<span data-ttu-id="0153e-114">En el administrador de configuración del servicio de informes, el panel de estado del servidor de informes debe mostrar que SQL Server Reporting Services se ha instalado y que los servicios de informes se están ejecutando actualmente: el estado del servidor de informes debe mostrarse como **iniciado** y el botón **iniciar** debe estar atenuado y no disponible.</span><span class="sxs-lookup"><span data-stu-id="0153e-114">In the Reporting Service Configuration Manager, the Report Server Status pane should show that SQL Server Reporting Services has been installed and that the Reporting Services are currently running: the Report Server Status should be shown as **Started** and the **Start** button should be grayed-out and unavailable.</span></span> <span data-ttu-id="0153e-115">Si Reporting Services no estás ejecutándose, haga clic en **Iniciar** para iniciar el servicio.</span><span class="sxs-lookup"><span data-stu-id="0153e-115">If the Reporting Service is not running, click **Start** in order to start the service.</span></span>

<span data-ttu-id="0153e-116">Haga lo siguiente si no aparece ninguna base de datos al lado de la etiqueta Nombre de la base de datos del servidor de informes:</span><span class="sxs-lookup"><span data-stu-id="0153e-116">If no database is listed next to the Report Server Database Name label then do the following:</span></span>

1.  <span data-ttu-id="0153e-117">Haga clic en **Base de datos** en el Administrador de configuración de Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="0153e-117">In the Reporting Services Configuration Manager click **Database**.</span></span>

2.  <span data-ttu-id="0153e-118">Haga clic en **Cambiar base de datos** en el panel Base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="0153e-118">In the Report Server Database pane click **Change Database**.</span></span>

3.  <span data-ttu-id="0153e-119">En el panel Acción del Asistente para configuración de bases de datos del servidor de informes, seleccione **Crear una nueva base de datos del servidor de informes** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0153e-119">In the Report Server Database Configuration wizard, in the Action pane, select **Create a new report server database** and then click **Next**.</span></span>

4.  <span data-ttu-id="0153e-p104">En el panel Servidor de bases de datos del mismo asistente, confirme que la información de los cuadros **Nombre del servidor**, **Tipo de autenticación** y **Nombre de usuario** es correcta. Haga clic en **Probar conexión** para comprobar que se puede establecer una conexión con el servidor de base de datos y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0153e-p104">In the Report Server Database Configuration wizard, in the Database Server pane, verify that the information listed in the **Server Name**, **Authentication Type**, and **Username** boxes is correct. Click **Test Connection** to verify that a connection can be made to the database server and then click **Next**.</span></span>

5.  <span data-ttu-id="0153e-122">En el panel Base de datos del asistente, acepte los valores predeterminados en **Nombre de la base de datos**, **Idioma** y **Modo del servidor de informes** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0153e-122">In the Report Server Database Configuration wizard, in the Database pane, accept the default values for **Database Name**, **Language**, and **Report Server Mode** and then click **Next**.</span></span>

6.  <span data-ttu-id="0153e-123">En el panel Credenciales del asistente, confirme que la información de la lista desplegable **Tipo de autenticación** y de los cuadros **Nombre de usuario** y **Contraseña** es correcta y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0153e-123">In the Report Server Database Configuration wizard, in the Credentials pane, verify that the correct information is listed in the **Authentication Type** dropdown list and the **User name** and **Password** boxes, and then click **Next**.</span></span>

7.  <span data-ttu-id="0153e-124">En el panel Resumen del asistente, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0153e-124">In the Report Server Database Configuration wizard, in the Summary pane, click **Next**.</span></span>

8.  <span data-ttu-id="0153e-125">En el panel Avanzar y finalizar del asistente, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="0153e-125">In the Report Server Database Configuration wizard, in the Progress and Finish pane, click **Finish**.</span></span>

<span data-ttu-id="0153e-p105">Para comprobar que se han configurado las direcciones URL de Reporting Services, haga clic en **Dirección URL del servicio web**. Deberán aparecer una o más direcciones URL bajo el encabezado **Direcciones URL del servicio web del servidor de informes**. Haga clic en cada una de ellas para constatar que accede a la página principal de la instalación local de SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="0153e-p105">To verify that the Reporting Service URLs have been configured, click **Web Service URL**. You should see one or more URLs listed under the heading **Report Server Web Service URLs**. Click each of these URLs to verify that you can reach the home page for the local installation of SQL Server Reporting Services.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

