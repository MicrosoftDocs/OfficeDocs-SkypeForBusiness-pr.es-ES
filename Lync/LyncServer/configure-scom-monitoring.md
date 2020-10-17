---
title: Configurar la supervisión SCOM
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure SCOM monitoring
ms:assetid: 4003d225-2a33-448c-abd9-571750661140
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688033(v=OCS.15)
ms:contentKeyID: 49733624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de0ca4d569c8a67eb134c5a1bd018ed143041046
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503367"
---
# <a name="configure-scom-monitoring"></a><span data-ttu-id="d7760-102">Configurar la supervisión SCOM</span><span class="sxs-lookup"><span data-stu-id="d7760-102">Configure SCOM monitoring</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d7760-103">_**Última modificación del tema:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="d7760-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="d7760-104">Después de migrar a Microsoft Lync Server 2013, debe realizar algunas tareas para configurar Lync Server 2013 para que funcione con System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="d7760-104">After migrating to Microsoft Lync Server 2013, you must complete a few tasks to configure Lync Server 2013 to work with System Center Operations Manager.</span></span>

  - <span data-ttu-id="d7760-105">Aplique las actualizaciones de Lync Server 2010 a un servidor elegido para administrar la lógica de detección central.</span><span class="sxs-lookup"><span data-stu-id="d7760-105">Apply Lync Server 2010 updates to a server elected to manage the central discovery logic.</span></span>

  - <span data-ttu-id="d7760-106">Actualice la clave de registro del servidor candidato de detección central.</span><span class="sxs-lookup"><span data-stu-id="d7760-106">Update the central discovery candidate server registry key.</span></span>

  - <span data-ttu-id="d7760-107">Configure el servidor de administración principal de System Center Operations Manager para invalidar el nodo de detección central candidato.</span><span class="sxs-lookup"><span data-stu-id="d7760-107">Configure your primary System Center Operations Manager management server to override the candidate central discovery node.</span></span>

<span data-ttu-id="d7760-108">A continuación se proporcionan instrucciones para realizar cada una de estas tareas.</span><span class="sxs-lookup"><span data-stu-id="d7760-108">Instructions for carrying out each of these tasks are provided below.</span></span>

<span data-ttu-id="d7760-109">**Aplique las actualizaciones de Lync Server 2010 a un servidor elegido para administrar la lógica de detección central.**</span><span class="sxs-lookup"><span data-stu-id="d7760-109">**Apply Lync Server 2010 updates to a server elected to manage the central discovery logic.**</span></span>

1.  <span data-ttu-id="d7760-110">Elija un servidor que tenga los archivos del agente System Center Operations Manager instalados y esté configurado como un nodo de detección candidato.</span><span class="sxs-lookup"><span data-stu-id="d7760-110">Elect a server that has the System Center Operations Manager agent files installed and is configured as a candidate discovery node.</span></span>

2.  <span data-ttu-id="d7760-111">Aplique las actualizaciones de Lync Server 2010 a este servidor.</span><span class="sxs-lookup"><span data-stu-id="d7760-111">Apply Lync Server 2010 updates to this server.</span></span> <span data-ttu-id="d7760-112">Consulte el tema [Apply Lync Server 2010 updates](apply-lync-server-2010-updates.md).</span><span class="sxs-lookup"><span data-stu-id="d7760-112">See the topic [Apply Lync Server 2010 updates](apply-lync-server-2010-updates.md).</span></span>

<span data-ttu-id="d7760-113">**Actualice la clave de registro del servidor candidato de detección central.**</span><span class="sxs-lookup"><span data-stu-id="d7760-113">**Update the central discovery candidate server registry key.**</span></span>

1.  <span data-ttu-id="d7760-114">En el servidor decidió administrar la lógica de detección central, abra una ventana de comandos de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d7760-114">On the server elected to manage the central discovery logic, open a Windows PowerShell command window.</span></span>

2.  <span data-ttu-id="d7760-115">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d7760-115">At the command line, type the following:</span></span>
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
       ```
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
       ```
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="d7760-p102">Al cambiar el registro, puede recibir un error que indica que el comando ha fallado si la clave de registro ya existe. Si le pasa esto, puede ignorar el error de forma segura.</span><span class="sxs-lookup"><span data-stu-id="d7760-p102">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists. If you experience this, you can safely ignore the error.</span></span>

    
    </div>

<span data-ttu-id="d7760-118">**Configure el servidor de administración principal de System Center Operations Manager para invalidar el nodo de monitor de detección central candidato.**</span><span class="sxs-lookup"><span data-stu-id="d7760-118">**Configure your primary System Center Operations Manager management server to override the candidate central discovery watcher node.**</span></span>

1.  <span data-ttu-id="d7760-119">En un PC donde se haya instalado la consola de System Center Operations Manager, expanda **Objetos del módulo de administración** y luego seleccione **Detecciones de objetos**.</span><span class="sxs-lookup"><span data-stu-id="d7760-119">On a computer where the System Center Operations Manager console has been installed, expand **Management Pack Objects** and then select **Object Discoveries**.</span></span>

2.  <span data-ttu-id="d7760-120">Haga clic en **Cambiar ámbito...**</span><span class="sxs-lookup"><span data-stu-id="d7760-120">Click **Change Scope...**</span></span>

3.  <span data-ttu-id="d7760-121">En la página **Objetos de módulo de administración de ámbito**, seleccione **Candidato de detección de LS**.</span><span class="sxs-lookup"><span data-stu-id="d7760-121">From the **Scope Management Pack Objects** page, select **LS Discovery Candidate**.</span></span>

4.  <span data-ttu-id="d7760-122">Reemplace el **Valor efectivo de Candidato de detección de LS** con el nombre del servidor candidato elegido en el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="d7760-122">Override the **LS Discovery Candidate Effective Value** to the name of the candidate server elected in the earlier procedure.</span></span>

<span data-ttu-id="d7760-123">Por último, para finalizar los cambios, reinicie el servicio de estado en el Servidor de administración raíz de System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="d7760-123">Lastly, to finalize your changes, restart the health service on the System Center Operations Manager Root Management Server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

