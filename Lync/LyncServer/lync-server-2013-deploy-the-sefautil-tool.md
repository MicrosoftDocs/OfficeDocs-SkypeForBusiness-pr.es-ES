---
title: 'Lync Server 2013: implementar la herramienta SEFAUtil'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy the SEFAUtil tool
ms:assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945659(v=OCS.15)
ms:contentKeyID: 51541534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91392470d47cc4d59130e7c304656f9eee48ae5e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531377"
---
# <a name="deploy-the-sefautil-tool-in-lync-server-2013"></a><span data-ttu-id="35005-102">Implementar la herramienta SEFAUtil en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35005-102">Deploy the SEFAUtil tool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35005-103">_**Última modificación del tema:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="35005-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="35005-104">Para implementar y administrar la recogida de llamadas de grupo, debe usar la herramienta del kit de recursos de SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="35005-104">To deploy and manage Group Call Pickup, you need to use the SEFAUtil resource kit tool.</span></span> <span data-ttu-id="35005-105">La herramienta forma parte de las herramientas del kit de recursos de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="35005-105">The tool is part of the Lync Server 2013 resource kit tools.</span></span> <span data-ttu-id="35005-106">Para poder instalar SEFAUtil, debe tener un grupo de aplicaciones de confianza en la topología, especificar SEFAUtil como aplicación de confianza y habilitar la topología.</span><span class="sxs-lookup"><span data-stu-id="35005-106">Before you can install SEFAUtil, you must have a trusted application pool in your topology, specify SEFAUtil as a trusted application, and enable the topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="35005-107">El SDK de la API administrada de comunicaciones unificadas (UCMA) 3,0 de Microsoft debe estar instalado en cualquier equipo en el que tenga previsto ejecutar la herramienta SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="35005-107">Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK must be installed on any computer where you plan to run the SEFAUtil tool.</span></span>



</div>

<span data-ttu-id="35005-108">Puede ejecutar el SEFAUtil en cualquier grupo de servidores front-end en su implementación de.</span><span class="sxs-lookup"><span data-stu-id="35005-108">You can run the SEFAUtil in any Front End pool in your deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="35005-109">Para obtener más información sobre cómo ejecutar SEFAUtil, vea el artículo del blog de TechNet sobre cómo obtener SEFAutil en ejecución.</span><span class="sxs-lookup"><span data-stu-id="35005-109">For more details about running SEFAUtil, see the Technet blog article, "How to get SEFAutil running?"</span></span> <span data-ttu-id="35005-110">en <A href="https://go.microsoft.com/fwlink/?linkid=278940">https://go.microsoft.com/fwlink/?LinkId=278940</A> .</span><span class="sxs-lookup"><span data-stu-id="35005-110">at <A href="https://go.microsoft.com/fwlink/?linkid=278940">https://go.microsoft.com/fwlink/?LinkId=278940</A>.</span></span>



</div>

<div>

## <a name="to-deploy-sefautil"></a><span data-ttu-id="35005-111">Para implementar SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="35005-111">To deploy SEFAUtil</span></span>

1.  <span data-ttu-id="35005-112">Inicie sesión en el equipo donde esté instalado el shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal y como se describe en [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="35005-112">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="35005-113">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="35005-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="35005-114">La herramienta SEFAUtil solo puede ejecutarse en un equipo que forme parte de un grupo de aplicaciones de confianza.</span><span class="sxs-lookup"><span data-stu-id="35005-114">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="35005-115">Si es necesario, defina un grupo de aplicaciones de confianza para el grupo de servidores front-end en el que planea ejecutar SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="35005-115">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="35005-116">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="35005-116">At the command line, run:</span></span>
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>

4.  <span data-ttu-id="35005-117">Defina la herramienta SEFAUtil como una aplicación de confianza.</span><span class="sxs-lookup"><span data-stu-id="35005-117">Define the SEFAUtil tool as a trusted application.</span></span> <span data-ttu-id="35005-118">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="35005-118">At the command line, run:</span></span>
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="35005-119">Puede usar un puerto diferente si es necesario.</span><span class="sxs-lookup"><span data-stu-id="35005-119">You can use a different port if needed.</span></span>

    
    </div>

5.  <span data-ttu-id="35005-120">Habilite la topología con los cambios.</span><span class="sxs-lookup"><span data-stu-id="35005-120">Enable the topology with your changes.</span></span> <span data-ttu-id="35005-121">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="35005-121">At the command line, run:</span></span>
    
        Enable-CsTopology

6.  <span data-ttu-id="35005-122">Instale las herramientas del kit de recursos de Lync Server 2013 en un servidor front-end que se encuentra en el grupo de aplicaciones de confianza que creó en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="35005-122">Install the Lync Server 2013 resource kit tools on a Front End Server that is in the trusted application pool that you created in step 3.</span></span>

7.  <span data-ttu-id="35005-123">Compruebe que la herramienta SEFAUtil se está ejecutando correctamente, de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="35005-123">Verify that the SEFAUtil tool is running correctly, as follows:</span></span>
    
    1.  <span data-ttu-id="35005-124">Ejecute la herramienta desde el símbolo del sistema de Windows con privilegios de administrador para mostrar la configuración de desvío de llamadas de un usuario en la implementación.</span><span class="sxs-lookup"><span data-stu-id="35005-124">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="35005-125">La herramienta se encuentra en \Archivos de Programa\microsoft Lync Server 2013 \ reskit.</span><span class="sxs-lookup"><span data-stu-id="35005-125">The tool is located at \Program Files\Microsoft Lync Server 2013\Reskit.</span></span>

        
        </div>
    
    2.  <span data-ttu-id="35005-126">Muestra la configuración de desvío de llamadas de un usuario.</span><span class="sxs-lookup"><span data-stu-id="35005-126">Display the call forwarding settings of a user.</span></span> <span data-ttu-id="35005-127">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="35005-127">At the command line, run:</span></span>
        
            SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
        
        <span data-ttu-id="35005-128">Se mostrará la configuración de desvío de llamadas para el usuario.</span><span class="sxs-lookup"><span data-stu-id="35005-128">The call forwarding settings for the user will be displayed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

