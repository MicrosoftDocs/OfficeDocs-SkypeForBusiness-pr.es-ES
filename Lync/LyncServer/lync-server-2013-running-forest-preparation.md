---
title: 'Lync Server 2013: ejecución de la preparación del bosque'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running forest preparation
ms:assetid: 9d62f7be-bcfe-421d-8d8a-225567102a35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412732(v=OCS.15)
ms:contentKeyID: 48184991
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e9cb09b04ca42c032f042ed7970452f70982e016
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051684"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-forest-preparation-for-lync-server-2013"></a><span data-ttu-id="742c1-102">Ejecutar la preparación del bosque para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="742c1-102">Running forest preparation for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="742c1-103">_**Última modificación del tema:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="742c1-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="742c1-104">Puede usar los cmdlets del shell de administración de Lync Server o de instalación para preparar el bosque.</span><span class="sxs-lookup"><span data-stu-id="742c1-104">You can use Setup or Lync Server Management Shell cmdlets to prepare the forest.</span></span> <span data-ttu-id="742c1-105">El cmdlet que prepara el bosque es **Enable-CsAdForest**.</span><span class="sxs-lookup"><span data-stu-id="742c1-105">The cmdlet that prepares the forest is **Enable-CsAdForest**.</span></span>

<span data-ttu-id="742c1-106">Después de preparar el bosque, debe comprobar que la configuración global se haya replicado antes de llevar a cabo la preparación del dominio.</span><span class="sxs-lookup"><span data-stu-id="742c1-106">After you prepare the forest, you must verify that global settings have been replicated before running domain preparation.</span></span>

<div>

## <a name="to-use-setup-to-prepare-the-forest"></a><span data-ttu-id="742c1-107">Para preparar el bosque durante la instalación</span><span class="sxs-lookup"><span data-stu-id="742c1-107">To use Setup to prepare the forest</span></span>

1.  <span data-ttu-id="742c1-108">Inicie sesión en un equipo que se haya unido a un dominio como miembro del grupo de administradores de la empresa para el dominio raíz del bosque.</span><span class="sxs-lookup"><span data-stu-id="742c1-108">Log on to a computer that is joined to a domain as a member of the Enterprise Admins group for the forest root domain.</span></span>

2.  <span data-ttu-id="742c1-109">Desde el medio o la carpeta de instalación 2013 de Lync Server, ejecute setup. exe para iniciar el Asistente para la implementación.</span><span class="sxs-lookup"><span data-stu-id="742c1-109">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Deployment Wizard.</span></span>

3.  <span data-ttu-id="742c1-110">Haga clic en **Preparar Active Directory** y espere hasta que se determine el estado de implementación.</span><span class="sxs-lookup"><span data-stu-id="742c1-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

4.  <span data-ttu-id="742c1-111">En **Paso 3: Preparar bosque actual**, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="742c1-111">At **Step 3: Prepare Current Forest**, click **Run**.</span></span>

5.  <span data-ttu-id="742c1-112">En la página **Preparar el bosque**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="742c1-112">On the **Prepare Forest** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="742c1-113">La preparación del bosque le permite elegir dónde desea situar los grupos universales para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="742c1-113">Forest Preparation allows you to choose where to place the Universal Groups for Lync Server 2013.</span></span> <span data-ttu-id="742c1-114">Elija una ubicación que respete los requisitos de su organización.</span><span class="sxs-lookup"><span data-stu-id="742c1-114">Choose a location that is consistent with the requirements of your organization.</span></span>

    
    </div>

6.  <span data-ttu-id="742c1-115">En la página **Ejecución de comandos**, busque **Estado de la tarea: completado** y, a continuación, haga clic en **Ver registro**.</span><span class="sxs-lookup"><span data-stu-id="742c1-115">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

7.  <span data-ttu-id="742c1-116">En la columna **acción** , expanda **preparación del bosque**, busque un \*\* \<\> \*\* resultado de ejecución correcta al final de cada tarea para comprobar que la preparación del bosque se completó correctamente, cierre el registro y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="742c1-116">Under the **Action** column, expand **Forest Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that forest preparation completed successfully, close the log, and then click **Finish**.</span></span>

8.  <span data-ttu-id="742c1-p103">Espere a que se complete la replicación de Active Directory o fuércela en todos los controladores de dominio que se enumeran en el complemento **Sitios y servicios de Active Directory** del controlador del dominio raíz del bosque antes de ejecutar la preparación del dominio. Fuerce la replicación entre los controladores de dominio en todos los sitios de Active Directory para que la replicación en los sitios se produzca en cuestión de minutos.</span><span class="sxs-lookup"><span data-stu-id="742c1-p103">Wait for Active Directory replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation. Force replication between the domain controllers in all Active Directory sites to cause replication within the sites to occur within minutes.</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-forest"></a><span data-ttu-id="742c1-119">Para usar cmdlets en la preparación del bosque</span><span class="sxs-lookup"><span data-stu-id="742c1-119">To use cmdlets to prepare the forest</span></span>

1.  <span data-ttu-id="742c1-120">Inicie sesión en un equipo que se haya unido a un dominio como miembro del grupo Admins. del dominio en el dominio raíz del bosque.</span><span class="sxs-lookup"><span data-stu-id="742c1-120">Log on to a computer that is joined to a domain as a member of the Domain Admins group in the forest root domain.</span></span>

2.  <span data-ttu-id="742c1-121">Instale los componentes principales de Lync Server de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="742c1-121">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="742c1-122">Desde el medio o la carpeta de instalación de Lync Server 2013, ejecute setup. exe para iniciar el Asistente para la implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="742c1-122">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="742c1-123">Si se le pide que instale el Paquete redistribuible de Microsoft Visual C++, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="742c1-123">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="742c1-124">El cuadro de diálogo del programa de instalación de Lync Server 2013 le pedirá que indique una ubicación para instalar los archivos de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="742c1-124">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="742c1-125">Elija la ubicación predeterminada o haga clic en **Examinar** para buscar la ubicación que prefiera y, a continuación, en **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="742c1-125">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="742c1-126">En la página Contrato de licencia, active **Acepto los términos del contrato de licencia** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="742c1-126">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="742c1-127">El instalador instala los componentes principales de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="742c1-127">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="742c1-128">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="742c1-128">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="742c1-129">Realizar</span><span class="sxs-lookup"><span data-stu-id="742c1-129">Run:</span></span>
    
        Enable-CsAdForest [-GroupDomain <FQDN of the domain in which to create the universal groups>]
    
    <span data-ttu-id="742c1-130">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="742c1-130">For example:</span></span>
    
        Enable-CsAdForest -GroupDomain domain1.contoso.com 
    
    <span data-ttu-id="742c1-p106">Si no especifica el parámetro GroupDomain, el valor predeterminado es el dominio local. Si se crearon grupos universales previamente en un dominio que no es el dominio predeterminado, debe especificar el parámetro GroupDomain explícitamente.</span><span class="sxs-lookup"><span data-stu-id="742c1-p106">If you do not specify the GroupDomain parameter, the default value is the local domain. If universal groups were created previously in a domain that is not the default domain, you must specify the GroupDomain parameter explicitly.</span></span>

5.  <span data-ttu-id="742c1-133">Espere a que se complete la replicación de Active Directory o fuércela en todos los controladores de dominio que se enumeran en el complemento \*\*Sitios y servicios de Active Directory \*\* del controlador del dominio raíz del bosque antes de ejecutar la preparación del dominio.</span><span class="sxs-lookup"><span data-stu-id="742c1-133">Wait for Active Directory replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation.</span></span>

6.  <span data-ttu-id="742c1-p107">Compruebe que la preparación del bosque se ha realizado correctamente. Ejecute:</span><span class="sxs-lookup"><span data-stu-id="742c1-p107">Verify that forest preparation was successful. Run:</span></span>
    
        Get-CsAdForest 
    
    <span data-ttu-id="742c1-136">Este cmdlet devuelve un valor de **LC\_FORESTSETTINGS\_estado\_listo** si la preparación del bosque se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="742c1-136">This cmdlet returns a value of **LC\_FORESTSETTINGS\_STATE\_READY** if forest preparation was successful.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="742c1-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="742c1-137">See Also</span></span>


[<span data-ttu-id="742c1-138">Uso de cmdlets para invertir la preparación del bosque para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="742c1-138">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)  


[<span data-ttu-id="742c1-139">Preparar el bosque para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="742c1-139">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

