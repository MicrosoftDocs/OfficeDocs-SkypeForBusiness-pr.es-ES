---
title: 'Lync Server 2013: implementar la herramienta SEFAUtil'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploy the SEFAUtil tool
ms:assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945659(v=OCS.15)
ms:contentKeyID: 51541534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0783ab251359582d232d558da2161a149dea5117
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835571"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-the-sefautil-tool-in-lync-server-2013"></a><span data-ttu-id="d7b59-102">Deploy the SEFAUtil tool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7b59-102">Deploy the SEFAUtil tool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d7b59-103">_**Última modificación del tema:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="d7b59-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="d7b59-104">Para implementar y administrar la recopilación de llamadas de grupo, necesita usar la herramienta del kit de recursos de SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="d7b59-104">To deploy and manage Group Call Pickup, you need to use the SEFAUtil resource kit tool.</span></span> <span data-ttu-id="d7b59-105">La herramienta forma parte de las herramientas del kit de recursos de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d7b59-105">The tool is part of the Lync Server 2013 resource kit tools.</span></span> <span data-ttu-id="d7b59-106">Para poder instalar SEFAUtil, debe disponer de un grupo de aplicaciones de confianza en su topología, especificar SEFAUtil como una aplicación de confianza y habilitar la topología.</span><span class="sxs-lookup"><span data-stu-id="d7b59-106">Before you can install SEFAUtil, you must have a trusted application pool in your topology, specify SEFAUtil as a trusted application, and enable the topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d7b59-107">Instale el SDK de la API administrada de comunicaciones unificadas (UCMA) de Microsoft 3.0 Core en los equipos donde planee ejecutar la herramienta SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="d7b59-107">Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK must be installed on any computer where you plan to run the SEFAUtil tool.</span></span>



</div>

<span data-ttu-id="d7b59-108">Puede ejecutar el SEFAUtil en cualquier grupo de servidores front-end de su implementación.</span><span class="sxs-lookup"><span data-stu-id="d7b59-108">You can run the SEFAUtil in any Front End pool in your deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d7b59-109">Para obtener más información sobre cómo ejecutar SEFAUtil, consulte el artículo del blog de TechNet, "Cómo obtener SEFAutil en ejecución".</span><span class="sxs-lookup"><span data-stu-id="d7b59-109">For more details about running SEFAUtil, see the Technet blog article, "How to get SEFAutil running?"</span></span> <span data-ttu-id="d7b59-110">en <A href="http://go.microsoft.com/fwlink/?linkid=278940">http://go.microsoft.com/fwlink/?LinkId=278940</A>.</span><span class="sxs-lookup"><span data-stu-id="d7b59-110">at <A href="http://go.microsoft.com/fwlink/?linkid=278940">http://go.microsoft.com/fwlink/?LinkId=278940</A>.</span></span>



</div>

<div>

## <a name="to-deploy-sefautil"></a><span data-ttu-id="d7b59-111">Para implementar SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="d7b59-111">To deploy SEFAUtil</span></span>

1.  <span data-ttu-id="d7b59-112">Inicie sesión en el equipo donde está instalado el shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal y como se describe en [permisos de configuración de delegado en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="d7b59-112">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="d7b59-113">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="d7b59-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d7b59-114">La herramienta SEFAUtil solo se puede ejecutar en un equipo que forme parte de un grupo de aplicaciones de confianza.</span><span class="sxs-lookup"><span data-stu-id="d7b59-114">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="d7b59-115">Si es necesario, defina un grupo de aplicaciones de confianza para el grupo de servidores front-end en el que tiene previsto ejecutar SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="d7b59-115">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="d7b59-116">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="d7b59-116">At the command line, run:</span></span>
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>

4.  <span data-ttu-id="d7b59-p104">Defina la herramienta SEFAUtil como aplicación de confianza. En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="d7b59-p104">Define the SEFAUtil tool as a trusted application. At the command line, run:</span></span>
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d7b59-119">Si es preciso, puede usar otro puerto.</span><span class="sxs-lookup"><span data-stu-id="d7b59-119">You can use a different port if needed.</span></span>

    
    </div>

5.  <span data-ttu-id="d7b59-p105">Habilite la topología con los cambios. En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="d7b59-p105">Enable the topology with your changes. At the command line, run:</span></span>
    
        Enable-CsTopology

6.  <span data-ttu-id="d7b59-122">Instale las herramientas del kit de recursos de Lync Server 2013 en un servidor front-end que se encuentra en el grupo de aplicaciones de confianza que creó en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="d7b59-122">Install the Lync Server 2013 resource kit tools on a Front End Server that is in the trusted application pool that you created in step 3.</span></span>

7.  <span data-ttu-id="d7b59-123">Compruebe que la herramienta SEFAUtil funcione correctamente, tal como se indica:</span><span class="sxs-lookup"><span data-stu-id="d7b59-123">Verify that the SEFAUtil tool is running correctly, as follows:</span></span>
    
    1.  <span data-ttu-id="d7b59-124">Ejecute la herramienta desde el símbolo del sistema de Windows con privilegios de administrador para que aparezca la configuración de reenvío de llamadas de un usuario en la implementación.</span><span class="sxs-lookup"><span data-stu-id="d7b59-124">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="d7b59-125">La herramienta se encuentra en \Archivos de Programa\microsoft Lync Server 2013 \ reskit.</span><span class="sxs-lookup"><span data-stu-id="d7b59-125">The tool is located at \Program Files\Microsoft Lync Server 2013\Reskit.</span></span>

        
        </div>
    
    2.  <span data-ttu-id="d7b59-p106">Muestre la configuración de reenvío de llamadas de un usuario. En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="d7b59-p106">Display the call forwarding settings of a user. At the command line, run:</span></span>
        
            SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
        
        <span data-ttu-id="d7b59-128">Aparecerá la configuración de reenvío de llamadas del usuario.</span><span class="sxs-lookup"><span data-stu-id="d7b59-128">The call forwarding settings for the user will be displayed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

