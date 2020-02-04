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
ms.openlocfilehash: 6342743486e3a3261e297d602ceb994d421dc13c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726010"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-sql-server-reporting-services-in-lync-server-2013"></a><span data-ttu-id="beb3d-102">Instalar SQL Server Reporting Services en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="beb3d-102">Installing SQL Server Reporting Services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="beb3d-103">_**Última modificación del tema:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="beb3d-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="beb3d-104">Si tiene previsto usar los informes de supervisión de Microsoft Lync Server 2013 (consulte la siguiente sección de esta documentación para obtener más información) primero debe instalar SQL Server Reporting Services. Reporting Services puede instalarse al mismo tiempo que instala Microsoft SQL Server o en cualquier momento después de instalar SQL Server.</span><span class="sxs-lookup"><span data-stu-id="beb3d-104">If you intend to use Microsoft Lync Server 2013 Monitoring Reports (see the next section of this documentation for more information) you must first install SQL Server Reporting Services; Reporting Services can be installed at the same time you install Microsoft SQL Server or any time after SQL Server has been installed.</span></span> <span data-ttu-id="beb3d-105">Esto puede realizarse al mismo tiempo que instala Microsoft SQL Server o después de instalar SQL Server.</span><span class="sxs-lookup"><span data-stu-id="beb3d-105">If you have not installed SQL Server, then follow the instructions provided earlier in this documentation.</span></span> <span data-ttu-id="beb3d-106">Si no ha instalado SQL Server, siga las instrucciones suministradas anteriormente en esta documentación.</span><span class="sxs-lookup"><span data-stu-id="beb3d-106">When installing SQL Server, make sure that, on the Feature Selection page, you select Reporting Services.</span></span> <span data-ttu-id="beb3d-107">Al instalar SQL Server, asegúrese de que selecciona Reporting Services en la página Selección de características, ya que de este modo se instalará SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="beb3d-107">That will install SQL Server Reporting Services.</span></span>

<span data-ttu-id="beb3d-108">Si ya ha instalado SQL Server pero no ha instalado SQL Server Reporting Services, puede agregar esa característica siguiendo el conjunto adecuado de instrucciones para SQL Server 2008 R2 o SQL Server 2012, según corresponda.</span><span class="sxs-lookup"><span data-stu-id="beb3d-108">If you have already installed SQL Server but did not install SQL Server Reporting Services you can add that feature by following the appropriate set of instructions for SQL Server 2008 R2 or SQL Server 2012, as appropriate.</span></span>

<span data-ttu-id="beb3d-109">Siga los pasos que se indican a continuación para comprobar que Reporting Services se ha instalado correctamente:</span><span class="sxs-lookup"><span data-stu-id="beb3d-109">To verify that the reporting Services have been successfully installed, complete the following steps:</span></span>

1.  <span data-ttu-id="beb3d-110">Si está ejecutando Microsoft SQL Server 2008 R2, haga clic en **Inicio**, haga clic en **todos los programas**, **Microsoft SQL Server 2008 R2**, **herramientas de configuración**y, a continuación, haga clic en **Administrador de configuración de Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="beb3d-110">If you are running Microsoft SQL Server 2008 R2, then click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>
    
    <span data-ttu-id="beb3d-111">Si está ejecutando Microsoft SQL Server 2012, haga clic en **Inicio**, haga clic en **todos los programas**, en **Microsoft SQL Server 2012**, en **herramientas de configuración**y, por último, en **Administrador de configuración de Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="beb3d-111">If you are running Microsoft SQL Server 2012, then click **Start**, click **All Programs**, click **Microsoft SQL Server 2012**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>

2.  <span data-ttu-id="beb3d-112">En el cuadro de diálogo **conexión de configuración de Reporting Services** , compruebe que el nombre del servidor aparece en el cuadro **nombre del servidor** y que el nombre de la instancia de SQL Server que almacena los datos de supervisión aparece en el cuadro instancia del **servidor de informes** .</span><span class="sxs-lookup"><span data-stu-id="beb3d-112">In the **Reporting Services Configuration Connection** dialog box, verify that the name of your server appears in the **Server Name** box and that the name of the SQL Server instance that stores your monitoring data appears in the **Report Server Instance** box.</span></span> <span data-ttu-id="beb3d-113">Haga clic en **conectar**.</span><span class="sxs-lookup"><span data-stu-id="beb3d-113">Click **Connect**.</span></span>

<span data-ttu-id="beb3d-114">En el administrador de configuración del servicio de informes, el panel estado del servidor de informes debe mostrar que SQL Server Reporting Services se ha instalado y que los servicios de creación de informes se están ejecutando: el estado del servidor de informes debe mostrarse como **iniciado** y el botón **Inicio** debe estar atenuado y no disponible.</span><span class="sxs-lookup"><span data-stu-id="beb3d-114">In the Reporting Service Configuration Manager, the Report Server Status pane should show that SQL Server Reporting Services has been installed and that the Reporting Services are currently running: the Report Server Status should be shown as **Started** and the **Start** button should be grayed-out and unavailable.</span></span> <span data-ttu-id="beb3d-115">Si el servicio de informes no se está ejecutando, haga clic en **iniciar** para iniciar el servicio.</span><span class="sxs-lookup"><span data-stu-id="beb3d-115">If the Reporting Service is not running, click **Start** in order to start the service.</span></span>

<span data-ttu-id="beb3d-116">Si no aparece ninguna base de datos junto a la etiqueta nombre de base de datos del servidor de informes, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="beb3d-116">If no database is listed next to the Report Server Database Name label then do the following:</span></span>

1.  <span data-ttu-id="beb3d-117">En el administrador de configuración de Reporting Services, haga clic en **base de datos**.</span><span class="sxs-lookup"><span data-stu-id="beb3d-117">In the Reporting Services Configuration Manager click **Database**.</span></span>

2.  <span data-ttu-id="beb3d-118">En el panel base de datos del servidor de informes, haga clic en **Cambiar base de datos**.</span><span class="sxs-lookup"><span data-stu-id="beb3d-118">In the Report Server Database pane click **Change Database**.</span></span>

3.  <span data-ttu-id="beb3d-119">En el Asistente para la configuración de base de datos del servidor de informes, en el panel de acciones, seleccione **crear una nueva base de datos del servidor de informes** y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="beb3d-119">In the Report Server Database Configuration wizard, in the Action pane, select **Create a new report server database** and then click **Next**.</span></span>

4.  <span data-ttu-id="beb3d-120">En el Asistente para la configuración de base de datos del servidor de informes, en el panel servidor de base de datos, compruebe que la información que aparece en los cuadros **nombre del servidor**, **tipo de autenticación**y nombre de **usuario** es correcta.</span><span class="sxs-lookup"><span data-stu-id="beb3d-120">In the Report Server Database Configuration wizard, in the Database Server pane, verify that the information listed in the **Server Name**, **Authentication Type**, and **Username** boxes is correct.</span></span> <span data-ttu-id="beb3d-121">Haga clic en **probar conexión** para comprobar que se puede establecer una conexión con el servidor de base de datos y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="beb3d-121">Click **Test Connection** to verify that a connection can be made to the database server and then click **Next**.</span></span>

5.  <span data-ttu-id="beb3d-122">En el Asistente para la configuración de base de datos del servidor de informes, en el panel base de datos, acepte los valores predeterminados para nombre de la **base de datos**, **idioma**y **servidor de informes** y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="beb3d-122">In the Report Server Database Configuration wizard, in the Database pane, accept the default values for **Database Name**, **Language**, and **Report Server Mode** and then click **Next**.</span></span>

6.  <span data-ttu-id="beb3d-123">En el Asistente para la configuración de base de datos del servidor de informes, en el panel credenciales, compruebe que la información correcta aparece en la lista desplegable **tipo de autenticación** y los cuadros **nombre de usuario** y **contraseña** y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="beb3d-123">In the Report Server Database Configuration wizard, in the Credentials pane, verify that the correct information is listed in the **Authentication Type** dropdown list and the **User name** and **Password** boxes, and then click **Next**.</span></span>

7.  <span data-ttu-id="beb3d-124">En el Asistente para la configuración de base de datos del servidor de informes, en el panel Resumen, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="beb3d-124">In the Report Server Database Configuration wizard, in the Summary pane, click **Next**.</span></span>

8.  <span data-ttu-id="beb3d-125">En el Asistente para la configuración de base de datos del servidor de informes, en el panel progreso y finalizar, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="beb3d-125">In the Report Server Database Configuration wizard, in the Progress and Finish pane, click **Finish**.</span></span>

<span data-ttu-id="beb3d-126">Para comprobar que las direcciones URL de Reporting Services se han configurado, haga clic en **URL de servicio Web**.</span><span class="sxs-lookup"><span data-stu-id="beb3d-126">To verify that the Reporting Service URLs have been configured, click **Web Service URL**.</span></span> <span data-ttu-id="beb3d-127">Debería ver una o más direcciones URL en las **direcciones URL del servicio Web del servidor de informes**de encabezado.</span><span class="sxs-lookup"><span data-stu-id="beb3d-127">You should see one or more URLs listed under the heading **Report Server Web Service URLs**.</span></span> <span data-ttu-id="beb3d-128">Haga clic en cada una de estas direcciones URL para comprobar que puede ponerse en contacto con la Página principal de la instalación local de SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="beb3d-128">Click each of these URLs to verify that you can reach the home page for the local installation of SQL Server Reporting Services.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

