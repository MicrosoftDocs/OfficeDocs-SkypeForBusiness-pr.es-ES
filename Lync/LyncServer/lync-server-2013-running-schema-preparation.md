---
title: 'Lync Server 2013: Ejecutar la preparación del esquema'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Running schema preparation
ms:assetid: 9d02bdb1-ff29-417a-bcce-b068b31207d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412729(v=OCS.15)
ms:contentKeyID: 48184911
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b743e5ef93b14279f5f2f16cb70241617a0c8f0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822541"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-active-directory-schema-preparation-in-lync-server-2013"></a><span data-ttu-id="ceee0-102">Ejecutar la preparación del esquema de Active Directory en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ceee0-102">Running Active Directory schema preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ceee0-103">_**Última modificación del tema:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="ceee0-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="ceee0-104">Puede usar el programa de instalación o los cmdlets del shell de administración de Lync Server para preparar el esquema de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ceee0-104">You can use Setup or Lync Server Management Shell cmdlets to prepare the Active Directory schema.</span></span> <span data-ttu-id="ceee0-105">El cmdlet que extiende el esquema de Active Directory es **install-CsAdServerSchema**.</span><span class="sxs-lookup"><span data-stu-id="ceee0-105">The cmdlet that extends the Active Directory schema is **Install-CsAdServerSchema**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ceee0-106">El cmdlet de preparación del esquema (<STRONG>install-CsAdServerSchema</STRONG>) debe tener acceso al maestro de esquema, que requiere que el servicio de registro remoto se esté ejecutando y que la clave del registro remoto esté habilitada.</span><span class="sxs-lookup"><span data-stu-id="ceee0-106">The schema preparation cmdlet (<STRONG>Install-CsAdServerSchema</STRONG>) must access the schema master, which requires that the remote registry service is running and that the remote registry key is enabled.</span></span> <span data-ttu-id="ceee0-107">Si el servicio de registro remoto no se puede habilitar en el maestro de esquema, puede ejecutar el cmdlet localmente en el maestro de esquema.</span><span class="sxs-lookup"><span data-stu-id="ceee0-107">If the remote registry service cannot be enabled on the schema master, you can run the cmdlet locally on the schema master.</span></span> <span data-ttu-id="ceee0-108">Para obtener más información sobre el acceso remoto al registro, consulte el artículo 314837 de Microsoft Knowledge base, "cómo administrar el acceso remoto <A href="http://go.microsoft.com/fwlink/p/?linkid=125769">http://go.microsoft.com/fwlink/p/?linkId=125769</A>al registro" en.</span><span class="sxs-lookup"><span data-stu-id="ceee0-108">For details about registry remote access, see Microsoft Knowledge Base article 314837, "How to Manage Remote Access to the Registry," at <A href="http://go.microsoft.com/fwlink/p/?linkid=125769">http://go.microsoft.com/fwlink/p/?linkId=125769</A>.</span></span>



</div>

<span data-ttu-id="ceee0-109">Una vez completada la preparación del esquema, compruebe manualmente que la partición de esquema se ha replicado antes de continuar con la preparación del bosque.</span><span class="sxs-lookup"><span data-stu-id="ceee0-109">After you complete schema preparation, manually verify that the schema partition has been replicated before proceeding to forest preparation.</span></span> <span data-ttu-id="ceee0-110">Para obtener más información, vea [comprobar la replicación de esquema de Active Directory en Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span><span class="sxs-lookup"><span data-stu-id="ceee0-110">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

<div>

## <a name="to-use-setup-to-prepare-the-schema-of-the-current-forest"></a><span data-ttu-id="ceee0-111">Para usar el programa de instalación para preparar el esquema del bosque actual</span><span class="sxs-lookup"><span data-stu-id="ceee0-111">To use Setup to prepare the schema of the current forest</span></span>

1.  <span data-ttu-id="ceee0-112">Inicie sesión en un servidor del bosque como miembro del grupo administradores de esquema y con derechos de administrador en el maestro de esquema.</span><span class="sxs-lookup"><span data-stu-id="ceee0-112">Log on to a server in your forest as a member of the Schema Admins group and with administrator rights on the schema master.</span></span>

2.  <span data-ttu-id="ceee0-113">Desde la carpeta o los medios de instalación de Lync Server 2013, ejecute setup. exe para iniciar el Asistente para la implementación.</span><span class="sxs-lookup"><span data-stu-id="ceee0-113">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Deployment Wizard.</span></span>

3.  <span data-ttu-id="ceee0-114">Si se le pide que instale el redistribuible de Microsoft Visual C++, haga clic en **sí**.</span><span class="sxs-lookup"><span data-stu-id="ceee0-114">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>

4.  <span data-ttu-id="ceee0-115">En el cuadro de diálogo instalación de Lync Server 2013 se le pide una ubicación para instalar los archivos de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ceee0-115">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="ceee0-116">Elija la ubicación predeterminada o **Desplácese** hasta la ubicación que desee y, a continuación, haga clic en **instalar**.</span><span class="sxs-lookup"><span data-stu-id="ceee0-116">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>

5.  <span data-ttu-id="ceee0-117">En la página contrato de licencia, seleccione **acepto los términos del contrato de licencia**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ceee0-117">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span>

6.  <span data-ttu-id="ceee0-118">El instalador instala los componentes principales de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ceee0-118">The installer installs the Lync Server Core Components.</span></span>

7.  <span data-ttu-id="ceee0-119">Cuando el Asistente para la implementación esté listo, haga clic en **preparar Active**Directory y, a continuación, espere a que se determine el estado de implementación.</span><span class="sxs-lookup"><span data-stu-id="ceee0-119">When the Deployment Wizard is ready, click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

8.  <span data-ttu-id="ceee0-120">En el **paso 1: preparar el esquema**, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="ceee0-120">At **Step 1: Prepare Schema**, click **Run**.</span></span>

9.  <span data-ttu-id="ceee0-121">En la página **preparar esquema** , haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ceee0-121">On the **Prepare Schema** page, click **Next**.</span></span>

10. <span data-ttu-id="ceee0-122">En la página **Ejecución de comandos**, busque **Estado de la tarea: completado** y, a continuación, haga clic en **Ver registro**.</span><span class="sxs-lookup"><span data-stu-id="ceee0-122">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

11. <span data-ttu-id="ceee0-123">En la columna **acción** , expanda **preparar el esquema**, busque el resultado de ejecución \*\* \<correcta\> \*\* al final de cada tarea para comprobar que la preparación del esquema se completó correctamente, cierre el registro y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="ceee0-123">Under the **Action** column, expand **Schema Prep**, look for the **\<Success\>** Execution Result at the end of each task to verify that schema preparation completed successfully, close the log, and then click **Finish**.</span></span>

12. <span data-ttu-id="ceee0-124">Espere a que se complete la replicación de Active Directory o fuerce la replicación.</span><span class="sxs-lookup"><span data-stu-id="ceee0-124">Wait for Active Directory replication to complete or force replication.</span></span>

13. <span data-ttu-id="ceee0-125">Compruebe manualmente que los cambios de esquema se han replicado en el resto de los controladores de dominio.</span><span class="sxs-lookup"><span data-stu-id="ceee0-125">Manually verify that the schema changes replicated to all other domain controllers.</span></span> <span data-ttu-id="ceee0-126">Para obtener más información, vea [comprobar la replicación de esquema de Active Directory en Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span><span class="sxs-lookup"><span data-stu-id="ceee0-126">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-schema-of-the-current-forest"></a><span data-ttu-id="ceee0-127">Para usar los cmdlets para preparar el esquema del bosque actual</span><span class="sxs-lookup"><span data-stu-id="ceee0-127">To use cmdlets to prepare the schema of the current forest</span></span>

1.  <span data-ttu-id="ceee0-128">Inicie sesión en un equipo del bosque como miembro del grupo administradores de esquema y con derechos de administrador en el maestro de esquema.</span><span class="sxs-lookup"><span data-stu-id="ceee0-128">Log on to a computer in the forest as a member of the Schema Admins group and with administrator rights on the schema master.</span></span>

2.  <span data-ttu-id="ceee0-129">Instale los componentes básicos de Lync Server de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="ceee0-129">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="ceee0-130">Desde la carpeta o los medios de instalación de Lync Server 2013, ejecute setup. exe para iniciar el Asistente para la implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ceee0-130">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="ceee0-131">Si se le pide que instale el redistribuible de Microsoft Visual C++, haga clic en **sí**.</span><span class="sxs-lookup"><span data-stu-id="ceee0-131">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="ceee0-132">En el cuadro de diálogo instalación de Lync Server 2013 se le pide una ubicación para instalar los archivos de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ceee0-132">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="ceee0-133">Elija la ubicación predeterminada o **Desplácese** hasta la ubicación que desee y, a continuación, haga clic en **instalar**.</span><span class="sxs-lookup"><span data-stu-id="ceee0-133">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="ceee0-134">En la página contrato de licencia, seleccione **acepto los términos del contrato de licencia**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ceee0-134">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="ceee0-135">El instalador instala los componentes principales de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ceee0-135">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="ceee0-136">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="ceee0-136">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="ceee0-137">Ejecute:</span><span class="sxs-lookup"><span data-stu-id="ceee0-137">Run:</span></span>
    
        Install-CsAdServerSchema [-Ldf <directory where the .ldf file is located>] 
    
    <span data-ttu-id="ceee0-138">Si no especifica el parámetro ldf, el valor predeterminado es la ruta de instalación de Lync Server 2013 que se lee en el registro.</span><span class="sxs-lookup"><span data-stu-id="ceee0-138">If you do not specify the Ldf parameter, the default value is the Lync Server 2013 installation path that is read from the registry.</span></span>
    
    <span data-ttu-id="ceee0-139">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ceee0-139">For example:</span></span>
    
        Install-CsAdServerSchema -Ldf "C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup"

5.  <span data-ttu-id="ceee0-140">Use el siguiente cmdlet para comprobar que la preparación del esquema se ejecutó completamente.</span><span class="sxs-lookup"><span data-stu-id="ceee0-140">Use the following cmdlet to verify that schema preparation ran to completion.</span></span>
    
        Get-CsAdServerSchema 
    
    <span data-ttu-id="ceee0-141">Este cmdlet devuelve un valor de **estado\_\_de\_versión de esquema actual** si la preparación del esquema se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="ceee0-141">This cmdlet returns a value of **SCHEMA\_VERSION\_STATE\_CURRENT** if schema preparation was successful.</span></span>

6.  <span data-ttu-id="ceee0-142">Espere a que se complete la replicación de Active Directory o fuerce la replicación.</span><span class="sxs-lookup"><span data-stu-id="ceee0-142">Wait for Active Directory replication to complete or force replication.</span></span>

7.  <span data-ttu-id="ceee0-143">Compruebe manualmente que los cambios de esquema se han replicado en el resto de los controladores de dominio.</span><span class="sxs-lookup"><span data-stu-id="ceee0-143">Manually verify that the schema changes replicated to all other domain controllers.</span></span> <span data-ttu-id="ceee0-144">Para obtener más información, vea [comprobar la replicación de esquema de Active Directory en Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span><span class="sxs-lookup"><span data-stu-id="ceee0-144">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ceee0-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="ceee0-145">See Also</span></span>


[<span data-ttu-id="ceee0-146">Comprobar la replicación de esquemas de Active Directory en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ceee0-146">Verifying Active Directory schema replication in Lync Server 2013</span></span>](lync-server-2013-verifying-schema-replication.md)  


[<span data-ttu-id="ceee0-147">Preparación del esquema de Active Directory en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ceee0-147">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

