---
title: Mover objetos de contacto de mensajería unificada de Exchange
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move Exchange Unified Messaging Contact objects
ms:assetid: 35c7e987-41b5-4798-b617-3303f20e52e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688022(v=OCS.15)
ms:contentKeyID: 49733612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3b3091a342b46b5c1aad1d456aa9159d951a4ba
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756619"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-exchange-unified-messaging-contact-objects"></a><span data-ttu-id="b6a4a-102">Mover objetos de contacto de mensajería unificada de Exchange</span><span class="sxs-lookup"><span data-stu-id="b6a4a-102">Move Exchange Unified Messaging Contact objects</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6a4a-103">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="b6a4a-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="b6a4a-104">Para migrar los objetos de contacto de operador automático (AA) y acceso de suscriptor (SA) a la nueva implementación de Lync Server 2013, primero debe mover los objetos de la implementación heredada de Office Communications Server 2007 R2 a la nueva implementación de Lync Server 2013 con los cmdlets **Get-CsExUmContact** y **Move-CsExUmContact** .</span><span class="sxs-lookup"><span data-stu-id="b6a4a-104">To migrate Auto Attendant (AA) and Subscriber Access (SA) contact objects to the new Lync Server 2013 deployment, you first move the objects from the legacy Office Communications Server 2007 R2 deployment to the new the Lync Server 2013 deployment using the **Get-CsExUmContact** and **Move-CsExUmContact** cmdlets.</span></span> <span data-ttu-id="b6a4a-105">En el servidor de Exchange, ejecute el script de Windows PowerShell **script ExchUCUtil** para hacer lo siguiente para el grupo de Lync recién implementado:</span><span class="sxs-lookup"><span data-stu-id="b6a4a-105">On the Exchange Server, you then run the **ExchUCUtil** Windows PowerShell script to do the following for the newly deployed Lync pool:</span></span>

  - <span data-ttu-id="b6a4a-106">Agregarlo a las puertas de enlace de IP de mensajería unificada.</span><span class="sxs-lookup"><span data-stu-id="b6a4a-106">Add it to the Unified Messaging IP gateways.</span></span>

  - <span data-ttu-id="b6a4a-107">Agregarlo a los grupos de búsqueda de Mensajería unificada.</span><span class="sxs-lookup"><span data-stu-id="b6a4a-107">Add it to the Unified Messaging hunt groups.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b6a4a-108">In order to use the <STRONG>Get-CsExUmContact</STRONG> and <STRONG>Move-CsExUmContact</STRONG> cmdlets, you must be a member of the RTCUniversalUserAdmins group and have organizational unit (OU) permission to the OU where the contacts objects are stored.</span><span class="sxs-lookup"><span data-stu-id="b6a4a-108">In order to use the <STRONG>Get-CsExUmContact</STRONG> and <STRONG>Move-CsExUmContact</STRONG> cmdlets, you must be a member of the RTCUniversalUserAdmins group and have organizational unit (OU) permission to the OU where the contacts objects are stored.</span></span> <span data-ttu-id="b6a4a-109">OU permission can be granted using the <STRONG>Grant-OUPermission</STRONG> cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b6a4a-109">OU permission can be granted using the <STRONG>Grant-OUPermission</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="to-move-contact-objects-by-using-the-lync-server-management-shell"></a><span data-ttu-id="b6a4a-110">Para mover objetos de contacto mediante el Shell de administración de Lync Server</span><span class="sxs-lookup"><span data-stu-id="b6a4a-110">To move contact objects by using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="b6a4a-111">Abra el Shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b6a4a-111">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="b6a4a-112">Para cada grupo registrado con mensajería unificada de Exchange (donde pool1.contoso.net es un grupo de servidores de la implementación de Office Communications Server 2007 R2 y pool2.contoso.net es el grupo de servidores de la implementación de Lync Server 2013) en la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b6a4a-112">For each pool registered with Exchange UM (where pool1.contoso.net is a pool from the Office Communications Server 2007 R2 deployment and pool2.contoso.net is the pool from the Lync Server 2013 deployment) at the command line, type the following:</span></span>
    
        Get-CsExUmContact -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsExUmContact -Target pool02.contoso.net
    
    <span data-ttu-id="b6a4a-113">Para comprobar que se mueven los objetos de contacto, ejecute el cmdlet **Get-CsExumContact**  y confirme que **RegistrarPool** está señalando ahora al nuevo grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="b6a4a-113">To verify that the contact objects are moved, run the **Get-CsExumContact** cmdlet and confirm that **RegistrarPool** is now pointing to the new pool.</span></span>

</div>

<div>

## <a name="to-run-the-exchucutil-windows-powershell-script"></a><span data-ttu-id="b6a4a-114">Para ejecutar el script ExchUCUtil de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b6a4a-114">To run the ExchUCUtil Windows PowerShell script</span></span>

1.  <span data-ttu-id="b6a4a-115">Inicie sesión en el servidor de Mensajería unificada de Exchange como usuario con privilegios de administrador de organización de Exchange.</span><span class="sxs-lookup"><span data-stu-id="b6a4a-115">Log on to the Exchange UM Server as a user with Exchange Organization Administrator privileges.</span></span>

2.  <span data-ttu-id="b6a4a-116">Navegue al script de Windows PowerShell script ExchUCUtil.</span><span class="sxs-lookup"><span data-stu-id="b6a4a-116">Navigate to the ExchUCUtil Windows PowerShell script.</span></span>
    
    <span data-ttu-id="b6a4a-117">En Exchange 2007, ExchUCUtil.ps1 se encuentra en: **% archivos de programa% archivos de \\ secuencias de comandos de Microsoft \\ Exchange Server \\ \\ExchUCUtil.ps1**</span><span class="sxs-lookup"><span data-stu-id="b6a4a-117">In Exchange 2007, ExchUCUtil.ps1 is located at: **%Program Files%\\Microsoft\\Exchange Server\\Scripts\\ExchUCUtil.ps1**</span></span>
    
    <span data-ttu-id="b6a4a-118">En Exchange 2010, ExchUCUtil.ps1 se encuentra en: **% archivos de programa% \\ Microsoft \\ Exchange Server \\ V14 \\ scripts \\ de MicrosoftExchUCUtil.ps1**</span><span class="sxs-lookup"><span data-stu-id="b6a4a-118">In Exchange 2010, ExchUCUtil.ps1 is located at: **%Program Files%\\Microsoft\\Exchange Server\\V14\\Scripts\\ExchUCUtil.ps1**</span></span>

3.  <span data-ttu-id="b6a4a-119">Si Exchange se implementa en un solo bosque, escriba:</span><span class="sxs-lookup"><span data-stu-id="b6a4a-119">If Exchange is deployed in a single forest, type:</span></span>
    
        exchucutil.ps1
    
    <span data-ttu-id="b6a4a-120">Si Exchange se implementa en varios bosques, escriba:</span><span class="sxs-lookup"><span data-stu-id="b6a4a-120">Or, if Exchange is deployed in multiple forests, type:</span></span>
    
        exchucutil.ps1 -Forest:" <forest FQDN>"
    
    <span data-ttu-id="b6a4a-121">donde FQDN del bosque especifica el bosque en el que se implementa Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6a4a-121">where forest FQDN specifies the forest in which Lync Server 2013 is deployed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b6a4a-122">Asegúrese de reiniciar el servicio <STRONG>Front-end de Lync Server</STRONG> (rtcsrv.exe) <EM>después</EM> de ejecutar exchucutil.ps1.</span><span class="sxs-lookup"><span data-stu-id="b6a4a-122">Be sure to restart the <STRONG>Lync Server Front-End</STRONG> service (rtcsrv.exe) <EM>after</EM> you run exchucutil.ps1.</span></span> <span data-ttu-id="b6a4a-123">De lo contrario, Lync Server 2013 no detectará la mensajería unificada en la topología.</span><span class="sxs-lookup"><span data-stu-id="b6a4a-123">Otherwise, Lync Server 2013 will not detect Unified Messaging in the topology.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

