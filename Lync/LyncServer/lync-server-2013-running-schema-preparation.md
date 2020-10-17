---
title: 'Lync Server 2013: ejecución de la preparación del esquema'
description: 'Lync Server 2013: ejecución de la preparación del esquema.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running schema preparation
ms:assetid: 9d02bdb1-ff29-417a-bcce-b068b31207d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412729(v=OCS.15)
ms:contentKeyID: 48184911
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0991bbff7f54f8b8b9eb01fc87f752e00f3dcbfd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569366"
---
# <a name="running-active-directory-schema-preparation-in-lync-server-2013"></a><span data-ttu-id="95f3c-103">Ejecución de la preparación del esquema de Active Directory en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="95f3c-103">Running Active Directory schema preparation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95f3c-104">_**Última modificación del tema:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="95f3c-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="95f3c-105">Puede usar los cmdlets del shell de administración de Lync Server o de instalación para preparar el esquema de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="95f3c-105">You can use Setup or Lync Server Management Shell cmdlets to prepare the Active Directory schema.</span></span> <span data-ttu-id="95f3c-106">El cmdlet que permite extender el esquema de Active Directory es **Install-CsAdServerSchema**.</span><span class="sxs-lookup"><span data-stu-id="95f3c-106">The cmdlet that extends the Active Directory schema is **Install-CsAdServerSchema**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="95f3c-107">El cmdlet de preparación del esquema (<STRONG>Install-CsAdServerSchema</STRONG>) debe tener acceso al maestro de esquema, que requiere que el servicio del Registro remoto esté en ejecución y que la clave del Registro remoto esté habilitada.</span><span class="sxs-lookup"><span data-stu-id="95f3c-107">The schema preparation cmdlet (<STRONG>Install-CsAdServerSchema</STRONG>) must access the schema master, which requires that the remote registry service is running and that the remote registry key is enabled.</span></span> <span data-ttu-id="95f3c-108">Si el servicio del Registro remoto no se puede habilitar en el maestro de esquema, puede ejecutar el cmdlet de forma local en el maestro de esquema.</span><span class="sxs-lookup"><span data-stu-id="95f3c-108">If the remote registry service cannot be enabled on the schema master, you can run the cmdlet locally on the schema master.</span></span> <span data-ttu-id="95f3c-109">Para obtener más información acerca del acceso remoto al registro, consulte el artículo 314837 de Microsoft Knowledge base, "How to Manage Remote Access to the Registry", en <A href="https://go.microsoft.com/fwlink/p/?linkid=125769">https://go.microsoft.com/fwlink/p/?linkId=125769</A> .</span><span class="sxs-lookup"><span data-stu-id="95f3c-109">For details about registry remote access, see Microsoft Knowledge Base article 314837, "How to Manage Remote Access to the Registry," at <A href="https://go.microsoft.com/fwlink/p/?linkid=125769">https://go.microsoft.com/fwlink/p/?linkId=125769</A>.</span></span>



</div>

<span data-ttu-id="95f3c-110">Una vez preparado el esquema, compruebe manualmente que la división del esquema se haya replicado antes de continuar con la preparación del bosque.</span><span class="sxs-lookup"><span data-stu-id="95f3c-110">After you complete schema preparation, manually verify that the schema partition has been replicated before proceeding to forest preparation.</span></span> <span data-ttu-id="95f3c-111">Para obtener información detallada, consulte [Verifying Active Directory Schema Replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span><span class="sxs-lookup"><span data-stu-id="95f3c-111">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

<div>

## <a name="to-use-setup-to-prepare-the-schema-of-the-current-forest"></a><span data-ttu-id="95f3c-112">Para preparar el esquema del bosque actual durante la instalación</span><span class="sxs-lookup"><span data-stu-id="95f3c-112">To use Setup to prepare the schema of the current forest</span></span>

1.  <span data-ttu-id="95f3c-113">Inicie sesión en un servidor del bosque como miembro del grupo Administradores de esquema y con derechos de administrador en el maestro de esquema.</span><span class="sxs-lookup"><span data-stu-id="95f3c-113">Log on to a server in your forest as a member of the Schema Admins group and with administrator rights on the schema master.</span></span>

2.  <span data-ttu-id="95f3c-114">Desde la carpeta o los medios de instalación de Lync Server 2013, ejecute Setup.exe para iniciar el Asistente para la implementación.</span><span class="sxs-lookup"><span data-stu-id="95f3c-114">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Deployment Wizard.</span></span>

3.  <span data-ttu-id="95f3c-115">Si se le pide que instale el Paquete redistribuible de Microsoft Visual C++, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="95f3c-115">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>

4.  <span data-ttu-id="95f3c-116">El cuadro de diálogo del programa de instalación de Lync Server 2013 le pedirá que indique una ubicación para instalar los archivos de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="95f3c-116">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="95f3c-117">Elija la ubicación predeterminada o haga clic en **Examinar** para buscar la ubicación que prefiera y, a continuación, en **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="95f3c-117">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>

5.  <span data-ttu-id="95f3c-118">En la página Contrato de licencia, active **Acepto los términos del contrato de licencia** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="95f3c-118">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span>

6.  <span data-ttu-id="95f3c-119">El instalador instala los componentes principales de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="95f3c-119">The installer installs the Lync Server Core Components.</span></span>

7.  <span data-ttu-id="95f3c-120">Cuando el Asistente para la implementación esté listo, haga clic en **Preparar Active Directory** y espere hasta que se determine el estado de implementación.</span><span class="sxs-lookup"><span data-stu-id="95f3c-120">When the Deployment Wizard is ready, click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

8.  <span data-ttu-id="95f3c-121">En **Paso 1: Preparar el esquema**, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="95f3c-121">At **Step 1: Prepare Schema**, click **Run**.</span></span>

9.  <span data-ttu-id="95f3c-122">En la página **Preparar el esquema**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="95f3c-122">On the **Prepare Schema** page, click **Next**.</span></span>

10. <span data-ttu-id="95f3c-123">En la página **Ejecución de comandos**, busque **Estado de la tarea: completado** y, a continuación, haga clic en **Ver registro**.</span><span class="sxs-lookup"><span data-stu-id="95f3c-123">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

11. <span data-ttu-id="95f3c-124">En la columna **acción** , expanda **preparación del esquema**, busque el **\<Success\>** resultado de ejecución al final de cada tarea para comprobar que la preparación del esquema se completó correctamente, cierre el registro y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="95f3c-124">Under the **Action** column, expand **Schema Prep**, look for the **\<Success\>** Execution Result at the end of each task to verify that schema preparation completed successfully, close the log, and then click **Finish**.</span></span>

12. <span data-ttu-id="95f3c-125">Espere a que la replicación de Active Directory finalice o fuerce la replicación.</span><span class="sxs-lookup"><span data-stu-id="95f3c-125">Wait for Active Directory replication to complete or force replication.</span></span>

13. <span data-ttu-id="95f3c-126">Compruebe manualmente que los cambios realizados en el esquema se hayan replicado al resto de controladores de dominio.</span><span class="sxs-lookup"><span data-stu-id="95f3c-126">Manually verify that the schema changes replicated to all other domain controllers.</span></span> <span data-ttu-id="95f3c-127">Para obtener información detallada, consulte [Verifying Active Directory Schema Replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span><span class="sxs-lookup"><span data-stu-id="95f3c-127">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-schema-of-the-current-forest"></a><span data-ttu-id="95f3c-128">Para usar cmdlets para preparar el esquema del bosque actual</span><span class="sxs-lookup"><span data-stu-id="95f3c-128">To use cmdlets to prepare the schema of the current forest</span></span>

1.  <span data-ttu-id="95f3c-129">Inicie sesión en un equipo del bosque como miembro del grupo Administradores de esquema y con derechos de administrador en el maestro de esquema.</span><span class="sxs-lookup"><span data-stu-id="95f3c-129">Log on to a computer in the forest as a member of the Schema Admins group and with administrator rights on the schema master.</span></span>

2.  <span data-ttu-id="95f3c-130">Instale los componentes principales de Lync Server de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="95f3c-130">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="95f3c-131">Desde la carpeta o los medios de instalación de Lync Server 2013, ejecute Setup.exe para iniciar el Asistente para la implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="95f3c-131">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="95f3c-132">Si se le pide que instale el Paquete redistribuible de Microsoft Visual C++, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="95f3c-132">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="95f3c-133">El cuadro de diálogo del programa de instalación de Lync Server 2013 le pedirá que indique una ubicación para instalar los archivos de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="95f3c-133">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="95f3c-134">Elija la ubicación predeterminada o haga clic en **Examinar** para buscar la ubicación que prefiera y, a continuación, en **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="95f3c-134">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="95f3c-135">En la página Contrato de licencia, active **Acepto los términos del contrato de licencia** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="95f3c-135">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="95f3c-136">El instalador instala los componentes principales de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="95f3c-136">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="95f3c-137">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="95f3c-137">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="95f3c-138">Realizar</span><span class="sxs-lookup"><span data-stu-id="95f3c-138">Run:</span></span>
    
        Install-CsAdServerSchema [-Ldf <directory where the .ldf file is located>] 
    
    <span data-ttu-id="95f3c-139">Si no especifica el parámetro ldf, el valor predeterminado es la ruta de instalación de Lync Server 2013 que se lee en el registro.</span><span class="sxs-lookup"><span data-stu-id="95f3c-139">If you do not specify the Ldf parameter, the default value is the Lync Server 2013 installation path that is read from the registry.</span></span>
    
    <span data-ttu-id="95f3c-140">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="95f3c-140">For example:</span></span>
    
        Install-CsAdServerSchema -Ldf "C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup"

5.  <span data-ttu-id="95f3c-141">Use el siguiente cmdlet para comprobar que la preparación del esquema ha finalizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="95f3c-141">Use the following cmdlet to verify that schema preparation ran to completion.</span></span>
    
        Get-CsAdServerSchema 
    
    <span data-ttu-id="95f3c-142">Este cmdlet devuelve un valor de **Estado de versión de esquema \_ \_ \_ actual** si la preparación del esquema se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="95f3c-142">This cmdlet returns a value of **SCHEMA\_VERSION\_STATE\_CURRENT** if schema preparation was successful.</span></span>

6.  <span data-ttu-id="95f3c-143">Espere a que la replicación de Active Directory finalice o fuerce la replicación.</span><span class="sxs-lookup"><span data-stu-id="95f3c-143">Wait for Active Directory replication to complete or force replication.</span></span>

7.  <span data-ttu-id="95f3c-144">Compruebe manualmente que los cambios realizados en el esquema se hayan replicado al resto de controladores de dominio.</span><span class="sxs-lookup"><span data-stu-id="95f3c-144">Manually verify that the schema changes replicated to all other domain controllers.</span></span> <span data-ttu-id="95f3c-145">Para obtener información detallada, consulte [Verifying Active Directory Schema Replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span><span class="sxs-lookup"><span data-stu-id="95f3c-145">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="95f3c-146">Consulte también</span><span class="sxs-lookup"><span data-stu-id="95f3c-146">See Also</span></span>


[<span data-ttu-id="95f3c-147">Comprobar la replicación de esquemas de Active Directory en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="95f3c-147">Verifying Active Directory schema replication in Lync Server 2013</span></span>](lync-server-2013-verifying-schema-replication.md)  


[<span data-ttu-id="95f3c-148">Preparar el esquema de Active Directory en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="95f3c-148">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

