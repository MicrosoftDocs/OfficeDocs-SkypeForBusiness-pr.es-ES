---
title: Configurar la supervisión SCOM
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Configure SCOM monitoring
ms:assetid: 4003d225-2a33-448c-abd9-571750661140
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688033(v=OCS.15)
ms:contentKeyID: 49733624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d48e08854b3c7aa66ca0f40224131b2785533e5
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233242"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-scom-monitoring"></a><span data-ttu-id="cdf94-102">Configurar la supervisión SCOM</span><span class="sxs-lookup"><span data-stu-id="cdf94-102">Configure SCOM monitoring</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cdf94-103">_**Última modificación del tema:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="cdf94-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="cdf94-104">Después de migrar a Microsoft Lync Server 2013, debe completar algunas tareas para configurar Lync Server 2013 para que funcione con System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="cdf94-104">After migrating to Microsoft Lync Server 2013, you must complete a few tasks to configure Lync Server 2013 to work with System Center Operations Manager.</span></span>

  - <span data-ttu-id="cdf94-105">Aplique actualizaciones de Lync Server 2010 a un servidor elegido para administrar la lógica de descubrimiento central.</span><span class="sxs-lookup"><span data-stu-id="cdf94-105">Apply Lync Server 2010 updates to a server elected to manage the central discovery logic.</span></span>

  - <span data-ttu-id="cdf94-106">Actualice la clave del registro del candidato de detección central.</span><span class="sxs-lookup"><span data-stu-id="cdf94-106">Update the central discovery candidate server registry key.</span></span>

  - <span data-ttu-id="cdf94-107">Configure el servidor de administración principal de System Center Operations Manager para que invalide el nodo de detección central candidato.</span><span class="sxs-lookup"><span data-stu-id="cdf94-107">Configure your primary System Center Operations Manager management server to override the candidate central discovery node.</span></span>

<span data-ttu-id="cdf94-108">A continuación se proporcionan instrucciones para llevar a cabo estas tareas.</span><span class="sxs-lookup"><span data-stu-id="cdf94-108">Instructions for carrying out each of these tasks are provided below.</span></span>

<span data-ttu-id="cdf94-109">**Aplique actualizaciones de Lync Server 2010 a un servidor elegido para administrar la lógica de descubrimiento central.**</span><span class="sxs-lookup"><span data-stu-id="cdf94-109">**Apply Lync Server 2010 updates to a server elected to manage the central discovery logic.**</span></span>

1.  <span data-ttu-id="cdf94-110">Elija un servidor que tenga instalados los archivos del agente System Center Operations Manager y esté configurado como un nodo de detección candidato.</span><span class="sxs-lookup"><span data-stu-id="cdf94-110">Elect a server that has the System Center Operations Manager agent files installed and is configured as a candidate discovery node.</span></span>

2.  <span data-ttu-id="cdf94-111">Aplique las actualizaciones de Lync Server 2010 a este servidor.</span><span class="sxs-lookup"><span data-stu-id="cdf94-111">Apply Lync Server 2010 updates to this server.</span></span> <span data-ttu-id="cdf94-112">Vea el tema sobre cómo [aplicar actualizaciones de Lync Server 2010](apply-lync-server-2010-updates.md).</span><span class="sxs-lookup"><span data-stu-id="cdf94-112">See the topic [Apply Lync Server 2010 updates](apply-lync-server-2010-updates.md).</span></span>

<span data-ttu-id="cdf94-113">**Actualice la clave del registro del candidato de detección central.**</span><span class="sxs-lookup"><span data-stu-id="cdf94-113">**Update the central discovery candidate server registry key.**</span></span>

1.  <span data-ttu-id="cdf94-114">En el servidor elegido para administrar la lógica de detección central, abra una ventana de comandos de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cdf94-114">On the server elected to manage the central discovery logic, open a Windows PowerShell command window.</span></span>

2.  <span data-ttu-id="cdf94-115">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="cdf94-115">At the command line, type the following:</span></span>
    
       ```
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
       ```
    
       ```
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
       ```
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="cdf94-116">Siempre que edite el registro, es posible que se produzca un error en el comando si la clave del registro ya existe.</span><span class="sxs-lookup"><span data-stu-id="cdf94-116">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists.</span></span> <span data-ttu-id="cdf94-117">Si tiene esto, puede ignorar el error sin riesgos.</span><span class="sxs-lookup"><span data-stu-id="cdf94-117">If you experience this, you can safely ignore the error.</span></span>

    
    </div>

<span data-ttu-id="cdf94-118">**Configure su servidor de administración principal de System Center Operations Manager para invalidar el nodo de supervisor de detección central candidato.**</span><span class="sxs-lookup"><span data-stu-id="cdf94-118">**Configure your primary System Center Operations Manager management server to override the candidate central discovery watcher node.**</span></span>

1.  <span data-ttu-id="cdf94-119">En un equipo en el que se haya instalado la consola de System Center Operations Manager, expanda los **objetos del módulo de administración** y seleccione descubrimientos de **objetos**.</span><span class="sxs-lookup"><span data-stu-id="cdf94-119">On a computer where the System Center Operations Manager console has been installed, expand **Management Pack Objects** and then select **Object Discoveries**.</span></span>

2.  <span data-ttu-id="cdf94-120">Haga clic en **cambiar ámbito...**</span><span class="sxs-lookup"><span data-stu-id="cdf94-120">Click **Change Scope...**</span></span>

3.  <span data-ttu-id="cdf94-121">En la página **objetos del módulo de administración del ámbito** , seleccione candidato de detección de **LS**.</span><span class="sxs-lookup"><span data-stu-id="cdf94-121">From the **Scope Management Pack Objects** page, select **LS Discovery Candidate**.</span></span>

4.  <span data-ttu-id="cdf94-122">Invalide el **valor efectivo candidato** a la detección de LS al nombre del servidor candidato elegido en el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="cdf94-122">Override the **LS Discovery Candidate Effective Value** to the name of the candidate server elected in the earlier procedure.</span></span>

<span data-ttu-id="cdf94-123">Por último, para finalizar los cambios, reinicie el servicio de mantenimiento en el servidor de administración de raíz de System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="cdf94-123">Lastly, to finalize your changes, restart the health service on the System Center Operations Manager Root Management Server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

