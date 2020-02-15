---
title: Combinar mediante el Asistente de combinación del generador de topologías
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Merge using Topology Builder Merge wizard
ms:assetid: c3f3c425-dab6-4dcd-bf0e-d7fde05f2ebf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205243(v=OCS.15)
ms:contentKeyID: 48185343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8889f55ecddae8f338a8fdb14809ec1c9fc7dad1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051242"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="merge-using-topology-builder-merge-wizard"></a><span data-ttu-id="93765-102">Combinar mediante el Asistente de combinación del generador de topologías</span><span class="sxs-lookup"><span data-stu-id="93765-102">Merge using Topology Builder Merge wizard</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93765-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="93765-103">_**Topic Last Modified:** 2012-10-02_</span></span>

1.  <span data-ttu-id="93765-104">Descargue la implementación actual con el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="93765-104">Download the existing deployment using Topology Builder.</span></span>

2.  <span data-ttu-id="93765-105">En el menú **Acción**, seleccione **Combinar Office Communications Server 2007 R2**.</span><span class="sxs-lookup"><span data-stu-id="93765-105">From the **Action** menu, select **Merge Office Communications Server 2007 R2**.</span></span>

3.  <span data-ttu-id="93765-106">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="93765-106">Click **Next**.</span></span>

4.  <span data-ttu-id="93765-107">En **Especificar configuración perimetral**, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="93765-107">In **Specify Edge Setup**, click **Add**.</span></span>
    
    <span data-ttu-id="93765-108">![Asistente para combinar topología, especificar página de configuración perimetral](images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "Asistente para combinar topología, especificar página de configuración perimetral")</span><span class="sxs-lookup"><span data-stu-id="93765-108">![Merge Topology Wizard, Specify Edge Setup page](images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "Merge Topology Wizard, Specify Edge Setup page")</span></span>  

5.  <span data-ttu-id="93765-p101">En **Especificar tipo de servidor perimetral**, escriba el tipo de configuración del servidor perimetral y haga clic en **Siguiente**. En este ejemplo, se usa la opción **Servidor perimetral único**.</span><span class="sxs-lookup"><span data-stu-id="93765-p101">In **Specify Edge Type**, enter the type of Edge Server configuration, and then click **Next**. This example uses the **Single Edge Server** option.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="93765-p102">No se admite la configuración de <STRONG>servidor perimetral expandido</STRONG>. Un <STRONG>servidor perimetral expandido</STRONG> debe convertirse primero en <STRONG>servidor perimetral único</STRONG> o en <STRONG>servidor perimetral consolidado con equilibrio de carga</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="93765-p102"><STRONG>Expanded Edge deployment</STRONG> is not a supported configuration. An <STRONG>Expanded Edge Server</STRONG> must first be converted to a <STRONG>Single Edge Server</STRONG> or a <STRONG>Load-balanced consolidated Edge</STRONG> Server.</span></span>

    
    </div>

6.  <span data-ttu-id="93765-113">En **especificar configuración perimetral interna** , escriba la información relevante del FQDN y los puertos internos del grupo de servidores perimetrales según sea necesario y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="93765-113">In **Specify Internal Edge Settings** , enter the relevant information for your Edge pool’s internal FQDN and ports as needed, and then click **Next**.</span></span>
    
    <span data-ttu-id="93765-114">![Cuadro de diálogo especificar configuración perimetral interna](images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "Cuadro de diálogo especificar configuración perimetral interna")</span><span class="sxs-lookup"><span data-stu-id="93765-114">![Specify Internal Edge Settings dialog](images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "Specify Internal Edge Settings dialog")</span></span>  

7.  <span data-ttu-id="93765-115">En **	Especificar perímetro externo**, escriba la información del FQDN de conferencia web del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="93765-115">In **Specify External Edge**, enter the web conferencing FQDN information for your Edge Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="93765-p103">Antes de hacer clic en <STRONG>Siguiente</STRONG>, realice el próximo paso de este procedimiento. Es muy importante que no omita este paso.</span><span class="sxs-lookup"><span data-stu-id="93765-p103">Before you click <STRONG>Next</STRONG>, do the next step in this procedure. It is very important that you do not miss this step.</span></span>

    
    </div>

8.  <span data-ttu-id="93765-118">Active la casilla **este grupo de servidores perimetrales se usa para la Federación y la conectividad de mensajería instantánea pública** si tiene previsto usar el servidor perimetral de Office Communications Server 2007 R2 heredado para la Federación.</span><span class="sxs-lookup"><span data-stu-id="93765-118">Check the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use the legacy Office Communications Server 2007 R2 Edge Server for federation.</span></span> <span data-ttu-id="93765-119">Si tiene varios servidores perimetrales implementados, solamente uno de ellos estará habilitado para la federación.</span><span class="sxs-lookup"><span data-stu-id="93765-119">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="93765-120">Si no activa esta casilla y decide más adelante que desea habilitar la federación, deberá ejecutar de nuevo el asistente para combinar del Generador de topologías y volver a publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="93765-120">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard and publish your topology again.</span></span>
    
    <span data-ttu-id="93765-121">![Cuadro de diálogo servidor perimetral, especificar página perimetral externa](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "Cuadro de diálogo servidor perimetral, especificar página perimetral externa")</span><span class="sxs-lookup"><span data-stu-id="93765-121">![Edge Server dialog, Specify External Edge page](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "Edge Server dialog, Specify External Edge page")</span></span>  

9.  <span data-ttu-id="93765-122">En **Especificar próximo salto**, escriba el nombre de dominio completo de la ubicación del próximo salto en el entorno.</span><span class="sxs-lookup"><span data-stu-id="93765-122">In **Specify Next Hop**, enter the fully qualified domain name (FQDN) of the next hop location in your environment.</span></span> <span data-ttu-id="93765-123">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="93765-123">Click **Finish**.</span></span>
    
    <span data-ttu-id="93765-124">![Cuadro de diálogo servidor perimetral, especificar página de salto siguiente](images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "Cuadro de diálogo servidor perimetral, especificar página de salto siguiente")</span><span class="sxs-lookup"><span data-stu-id="93765-124">![Edge Server dialog, Specify Next Hop page](images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "Edge Server dialog, Specify Next Hop page")</span></span>  

10. <span data-ttu-id="93765-125">En **especificar configuración perimetral**, si se han agregado todos los servidores perimetrales de Office Communications Server 2007 R2, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="93765-125">In **Specify Edge Setup**, if all your Office Communications Server 2007 R2 Edge Servers have been added, click **Next**.</span></span> <span data-ttu-id="93765-126">Si tiene más servidores perimetrales de Office Communications Server 2007 R2 para agregar, repita este procedimiento desde el paso 4.</span><span class="sxs-lookup"><span data-stu-id="93765-126">If you have more Office Communications Server 2007 R2 Edge Servers to add, repeat this procedure starting at step 4.</span></span>

11. <span data-ttu-id="93765-127">En **especificar puerto SIP interno** , seleccione la opción predeterminada (es decir, si no modificó el puerto SIP predeterminado).</span><span class="sxs-lookup"><span data-stu-id="93765-127">In **Specify Internal SIP port** , select the default setting (that is, if you did not modify the default SIP port).</span></span> <span data-ttu-id="93765-128">Cambie esta opción como sea necesario si no usa el puerto predeterminado 5061 y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="93765-128">Change as appropriate if you are not using a default port of 5061, and then click **Next**.</span></span>

12. <span data-ttu-id="93765-129">En **Resumen**, haga clic en **Siguiente** para comenzar a combinar las topologías.</span><span class="sxs-lookup"><span data-stu-id="93765-129">In **Summary**, click **Next** to begin merging the topologies.</span></span>

13. <span data-ttu-id="93765-130">La página del asistente comprueba que la combinación de topologías se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="93765-130">The wizard page verifies that the merging of the topologies was successful.</span></span>

14. <span data-ttu-id="93765-131">En la columna **Estado**, verifique que el valor es **Correcto** y haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="93765-131">In the **Status** column, verify that the value is **Success**, and then click **Finish**.</span></span>

15. <span data-ttu-id="93765-132">En el panel izquierdo del generador de topologías, ahora debería ver el **BackCompatSite**, que indica que el entorno de Office Communications Server 2007 R2 se ha combinado con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="93765-132">In the left pane of Topology Builder, you should now see the **BackCompatSite**, which indicates that your Office Communications Server 2007 R2 environment has been merged with Lync Server 2013.</span></span>
    
    <span data-ttu-id="93765-133">![Generador de topologías que muestra una topología combinada](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Generador de topologías que muestra una topología combinada")</span><span class="sxs-lookup"><span data-stu-id="93765-133">![Topology Builder showing a merged topology](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Topology Builder showing a merged topology")</span></span>  

16. <span data-ttu-id="93765-134">En el menú **Acción**, haga clic en **Publicar topología** y en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="93765-134">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

17. <span data-ttu-id="93765-135">Cuando el **Asistente para publicación** haya finalizado, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="93765-135">When the **Publishing wizard** completes, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="93765-136">Es importante que complete el siguiente tema, <A href="import-policies-and-settings.md">Import policies and Settings</A>, para asegurarse de que la configuración de directivas heredada se importa en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="93765-136">It’s important that you complete the next topic, <A href="import-policies-and-settings.md">Import policies and settings</A>, to ensure that the legacy policy settings are imported into Lync Server 2013.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

