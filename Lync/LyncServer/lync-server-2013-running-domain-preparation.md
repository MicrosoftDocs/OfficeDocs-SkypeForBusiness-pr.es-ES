---
title: 'Lync Server 2013: ejecución de la preparación del dominio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running domain preparation
ms:assetid: 95dab800-1f2c-4506-b36c-99986643b149
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398761(v=OCS.15)
ms:contentKeyID: 48184847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 960a3664bb7b629a9d66b375d072f826ed9e2738
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050772"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-domain-preparation-for-lync-server-2013"></a><span data-ttu-id="58486-102">Ejecutar la preparación del dominio para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58486-102">Running domain preparation for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58486-103">_**Última modificación del tema:** 2013-04-16_</span><span class="sxs-lookup"><span data-stu-id="58486-103">_**Topic Last Modified:** 2013-04-16_</span></span>

<span data-ttu-id="58486-104">Puede usar los cmdlets del shell de administración de Lync Server o de instalación para preparar los dominios.</span><span class="sxs-lookup"><span data-stu-id="58486-104">You can use Setup or Lync Server Management Shell cmdlets to prepare domains.</span></span> <span data-ttu-id="58486-105">El cmdlet que prepara un dominio es **Enable-CsAdDomain**.</span><span class="sxs-lookup"><span data-stu-id="58486-105">The cmdlet that prepares a domain is **Enable-CsAdDomain**.</span></span>

<span data-ttu-id="58486-106">La preparación del dominio es el último paso en la preparación de los servicios de dominio de Active Directory para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="58486-106">Domain preparation is the final step in preparing Active Directory Domain Services for Lync Server 2013.</span></span>

<div>

## <a name="to-use-setup-to-prepare-domains"></a><span data-ttu-id="58486-107">Para preparar dominios durante la instalación</span><span class="sxs-lookup"><span data-stu-id="58486-107">To use Setup to prepare domains</span></span>

1.  <span data-ttu-id="58486-108">Inicie sesión en cualquier servidor del dominio como miembro del grupo Admins. del dominio.</span><span class="sxs-lookup"><span data-stu-id="58486-108">Log on to any server in the domain as a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="58486-109">Desde el medio o la carpeta de instalación de Lync Server 2013, ejecute setup. exe para iniciar el Asistente para la implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="58486-109">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>

3.  <span data-ttu-id="58486-110">Haga clic en **Preparar Active Directory** y espere a que se determine el estado de implementación.</span><span class="sxs-lookup"><span data-stu-id="58486-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

4.  <span data-ttu-id="58486-111">En **Paso 5: Preparar dominio actual**, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="58486-111">At **Step 5: Prepare Current Domain**, click **Run**.</span></span>

5.  <span data-ttu-id="58486-112">En la página **Preparar el dominio**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="58486-112">On the **Prepare Domain** page, click **Next**.</span></span>

6.  <span data-ttu-id="58486-113">En la página **Ejecución de comandos**, busque **Estado de la tarea: completado** y, a continuación, haga clic en **Ver registro**.</span><span class="sxs-lookup"><span data-stu-id="58486-113">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

7.  <span data-ttu-id="58486-114">En la columna **acción** , expanda **preparación del dominio**, busque un \*\* \<\> \*\* resultado de ejecución correcta al final de cada tarea para comprobar que la preparación del dominio se completó correctamente, cierre el registro y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="58486-114">Under the **Action** column, expand **Domain Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that domain preparation completed successfully, close the log, and then click **Finish**.</span></span>

8.  <span data-ttu-id="58486-115">Espere a que se complete la replicación de Active Directory o fuerce la replicación en todos los controladores de dominio indicados en el complemento Sitios y servicios de Active Directory para el controlador de dominio raíz del bosque.</span><span class="sxs-lookup"><span data-stu-id="58486-115">Wait for Active Directory replication to complete or force replication to all the domain controllers listed in the Active Directory Sites and Services snap-in for the forest root domain controller.</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-domain"></a><span data-ttu-id="58486-116">Para usar cmdlets para preparar el dominio</span><span class="sxs-lookup"><span data-stu-id="58486-116">To use cmdlets to prepare the domain</span></span>

1.  <span data-ttu-id="58486-117">Inicie sesión en cualquier servidor del dominio como miembro del grupo Admins. del dominio.</span><span class="sxs-lookup"><span data-stu-id="58486-117">Log on to any server in the domain as a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="58486-118">Instale los componentes principales de Lync Server de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="58486-118">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="58486-119">Desde el medio o la carpeta de instalación de Lync Server 2013, ejecute setup. exe para iniciar el Asistente para la implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="58486-119">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="58486-120">Si se le pide que instale el Paquete redistribuible de Microsoft Visual C++, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="58486-120">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="58486-121">El cuadro de diálogo del programa de instalación de Lync Server 2013 le pedirá que indique una ubicación para instalar los archivos de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="58486-121">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="58486-122">Elija la ubicación predeterminada o haga clic en **Examinar** para buscar la ubicación que prefiera y, a continuación, en **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="58486-122">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="58486-123">En la página Contrato de licencia, active **Acepto los términos del contrato de licencia** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="58486-123">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="58486-124">El instalador instala los componentes principales de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="58486-124">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="58486-125">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="58486-125">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="58486-126">Realizar</span><span class="sxs-lookup"><span data-stu-id="58486-126">Run:</span></span>
    
        Enable-CsAdDomain [-Domain <DomainFQDN>] 
    
    <span data-ttu-id="58486-127">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="58486-127">For example:</span></span>
    
        Enable-CsAdDomain -Domain domain1.contoso.net 
    
    <span data-ttu-id="58486-128">Si no especifica el parámetro de dominio, el valor predeterminado es el dominio local.</span><span class="sxs-lookup"><span data-stu-id="58486-128">If you do not specify the Domain parameter, the default is the local domain.</span></span>

5.  <span data-ttu-id="58486-p104">Compruebe que la preparación del dominio se ha realizado correctamente. Ejecute:</span><span class="sxs-lookup"><span data-stu-id="58486-p104">Verify that domain preparation was successful. Run:</span></span>
    
        Get-CsAdDomain [-Domain <Domain FQDN>] [-DomainController <Domain controller FQDN>] [-GlobalCatalog <Global catalog server FQDN>] [-GlobalSettingsDomainController <Domain controller FQDN where global settings are stored>] 
    
    <span data-ttu-id="58486-131">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="58486-131">For example:</span></span>
    
        Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="58486-132">El parámetro GlobalSettingsDomainController permite indicar dónde se guarda la configuración global.</span><span class="sxs-lookup"><span data-stu-id="58486-132">The parameter GlobalSettingsDomainController allows you to indicate where global settings are stored.</span></span> <span data-ttu-id="58486-133">Si la configuración se guarda en el contenedor del sistema (habitual en implementaciones de actualización cuyas opciones de configuración globales no se han migrado al contenedor de configuración), deberá definir un controlador de dominio en la raíz del bosque de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="58486-133">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global settings migrated to the Configuration container), you define a domain controller in the root of your Active Directory forest.</span></span> <span data-ttu-id="58486-134">Si la configuración global se encuentra en el contenedor de configuración (habitual en implementaciones nuevas o de actualización en las que la configuración se ha migrado al contenedor de configuración), deberá definir cualquier controlador de dominio en el bosque.</span><span class="sxs-lookup"><span data-stu-id="58486-134">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="58486-135">Si no especifica este parámetro, el cmdlet presupone que la configuración se almacena en el contenedor de configuración y hace referencia a cualquier controlador de dominio de&nbsp;AD DS.</span><span class="sxs-lookup"><span data-stu-id="58486-135">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in AD&nbsp;DS.</span></span>

    
    </div>
    
    <span data-ttu-id="58486-136">Si no especifica el parámetro **Domain** , el valor predeterminado es el dominio local.</span><span class="sxs-lookup"><span data-stu-id="58486-136">If you do not specify the **Domain** parameter, the default is the local domain.</span></span>
    
    <span data-ttu-id="58486-137">Este cmdlet devuelve un valor de **LC\_DOMAINSETTINGS\_estado\_Ready** si la preparación del dominio se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="58486-137">This cmdlet returns a value of **LC\_DOMAINSETTINGS\_STATE\_READY** if domain preparation was successful.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="58486-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="58486-138">See Also</span></span>


[<span data-ttu-id="58486-139">Uso de cmdlets para invertir la preparación del dominio para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58486-139">Using cmdlets to reverse domain preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)  


[<span data-ttu-id="58486-140">Preparar dominios para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58486-140">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

