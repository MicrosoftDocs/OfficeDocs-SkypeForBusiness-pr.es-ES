---
title: Habilitar la integración de Exchange 2013 Outlook Web App y mensajería instantánea
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Exchange 2013 Outlook Web App and IM integration
ms:assetid: 44d08cf0-b17d-46e1-a4f0-fcc2fe96a958
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204857(v=OCS.15)
ms:contentKeyID: 48184027
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a67dd3c18525d7a39678b5871d087ea79c502fce
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006406"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-exchange-2013-outlook-web-app-and-im-integration"></a><span data-ttu-id="8fe2c-102">Habilitar la integración de Exchange 2013 Outlook Web App y mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="8fe2c-102">Enable Exchange 2013 Outlook Web App and IM integration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8fe2c-103">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="8fe2c-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="8fe2c-104">Para habilitar la integración de Exchange 2013 Outlook Web Access (OWA) y la mensajería instantánea (mi) con Lync Server 2013, debe agregar el servidor de servidor de acceso de cliente (CAS) de Exchange 2013 a la topología de Lync Server 2013 como un servidor de aplicaciones de confianza.</span><span class="sxs-lookup"><span data-stu-id="8fe2c-104">To enable Exchange 2013 Outlook Web Access (OWA) and instant messaging (IM) integration with Lync Server 2013, you must add the Exchange 2013 Client Access Server (CAS) server to the Lync Server 2013 topology as a trusted application server.</span></span>

<div>

## <a name="to-create-a-trusted-application-pool"></a><span data-ttu-id="8fe2c-105">Para crear un grupo de aplicaciones de confianza</span><span class="sxs-lookup"><span data-stu-id="8fe2c-105">To create a trusted application pool</span></span>

1.  <span data-ttu-id="8fe2c-106">Inicie el shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8fe2c-106">Start the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="8fe2c-107">Ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="8fe2c-107">Run the following cmdlet:</span></span>
    
        Get-CsSite
    
    <span data-ttu-id="8fe2c-108">Esto devuelve el siteID para el siteName en el que está creando el grupo.</span><span class="sxs-lookup"><span data-stu-id="8fe2c-108">This returns the siteID for the siteName in which you are creating the pool.</span></span> <span data-ttu-id="8fe2c-109">Para obtener más información, consulte [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) en la documentación del shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8fe2c-109">For details, see [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) in the Lync Server 2013 Management Shell documentation.</span></span>

3.  <span data-ttu-id="8fe2c-110">Ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="8fe2c-110">Run the following cmdlet:</span></span>
    
        New-CsTrustedApplicationPool -Identity <E14 CAS FQDN> -ThrottleAsServer $true -TreatAsAuthenticated $true -ComputerFQDN <E14 CAS FQDN> -Site <Site> -Registrar <Pool FQDN in the site> -RequiresReplication $false
    
    <span data-ttu-id="8fe2c-111">Para obtener más información, consulte [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) en la documentación del shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8fe2c-111">For details, see [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) in the Lync Server 2013 Management Shell documentation.</span></span>
    
    <span data-ttu-id="8fe2c-112">El FQDN de Exchange Server debe configurarse como el nombre alternativo del sujeto (SAN) o el nombre de sujeto (SN) del certificado de Exchange OWA.</span><span class="sxs-lookup"><span data-stu-id="8fe2c-112">The Exchange Server FQDN should be configured as the Exchange OWA certificate Subject Name (SN), or the Subject Alternate Name (SAN).</span></span>
    
    <span data-ttu-id="8fe2c-113">En Exchange OWA, compruebe que el FQDN del grupo también es de confianza.</span><span class="sxs-lookup"><span data-stu-id="8fe2c-113">In Exchange OWA, verify that the pool’s FQDN is trusted as well.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="8fe2c-114">Si el servidor CAS <EM>no</EM> se encuentra en el mismo servidor que ejecuta la mensajería unificada (MU) de Exchange 2013, omita los pasos restantes de este procedimiento y realice el procedimiento "crear una aplicación de confianza para el servidor Exchange 2013 CAS" más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="8fe2c-114">If your CAS server is <EM>not</EM> collocated on the same server that is running Exchange 2013 Unified Messaging (UM), skip the remaining steps in this procedure and perform the “Create a trusted application for the Exchange 2013 CAS server” procedure later in this topic.</span></span> <span data-ttu-id="8fe2c-115">Si el servidor CAS está combinado en el mismo servidor que ejecuta la mensajería unificada (MU) de Exchange 2013, complete los pasos de este procedimiento y no realice el procedimiento "crear una aplicación de confianza para el servidor de Exchange 2013 CAS" más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="8fe2c-115">If your CAS server is collocated on the same server that is running Exchange 2013 Unified Messaging (UM), complete the steps in this procedure and do not perform the “Create a trusted application for the Exchange 2013 CAS server” procedure later in this topic.</span></span>

    
    </div>

4.  <span data-ttu-id="8fe2c-116">Ejecute \*\*Enable-CsTopology  \*\*.</span><span class="sxs-lookup"><span data-stu-id="8fe2c-116">Run **Enable-CsTopology**.</span></span>

5.  <span data-ttu-id="8fe2c-117">Abra el Generador de topologías y descargue la topología existente.</span><span class="sxs-lookup"><span data-stu-id="8fe2c-117">Open Topology Builder and download the existing topology.</span></span>

6.  <span data-ttu-id="8fe2c-118">En el panel izquierdo, expanda el árbol hasta llegar a **Servidores de aplicaciones de confianza**.</span><span class="sxs-lookup"><span data-stu-id="8fe2c-118">In the left pane, expand the tree until you reach **Trusted application servers**.</span></span>

7.  <span data-ttu-id="8fe2c-119">Expanda el nodo \*\*Servidores de aplicaciones de confianza \*\*.</span><span class="sxs-lookup"><span data-stu-id="8fe2c-119">Expand the **Trusted application servers** node.</span></span>

8.  <span data-ttu-id="8fe2c-120">Ahora debería ver el servidor CAS de Exchange 2013 como un servidor de aplicaciones de confianza.</span><span class="sxs-lookup"><span data-stu-id="8fe2c-120">You should now see the Exchange 2013 CAS server listed as a trusted application server.</span></span>

</div>

<div>

## <a name="to-create-a-trusted-application-for-the-exchange-2013-cas-server"></a><span data-ttu-id="8fe2c-121">Para crear una aplicación de confianza para el servidor CAS de Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="8fe2c-121">To create a trusted application for the Exchange 2013 CAS server</span></span>

1.  <span data-ttu-id="8fe2c-122">Inicie el shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8fe2c-122">Start the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="8fe2c-123">Si el servidor CAS *no* se encuentra en el mismo servidor que ejecuta la mensajería unificada (UM) de Exchange 2013, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="8fe2c-123">If your CAS server is *not* collocated on the same server that is running Exchange 2013 Unified Messaging (UM), run the following cmdlet:</span></span>
    
        New-CsTrustedApplication -ApplicationId <AppID String> -TrustedApplicationPoolFqdn <E14 CAS FQDN> -Port <available port number>
    
    <span data-ttu-id="8fe2c-124">Para obtener más información, consulte el tema [New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) en la documentación del shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8fe2c-124">For details, see the topic [New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) in the Lync Server 2013 Management Shell documentation.</span></span>

3.  <span data-ttu-id="8fe2c-125">Ejecute **Enable-CsTopology**.</span><span class="sxs-lookup"><span data-stu-id="8fe2c-125">Run **Enable-CsTopology**.</span></span>

4.  <span data-ttu-id="8fe2c-126">En el panel izquierdo del Generador de topologías, expanda el árbol hasta llegar a **Servidores de aplicaciones de confianza**.</span><span class="sxs-lookup"><span data-stu-id="8fe2c-126">From Topology Builder, in the left pane, expand the tree until you reach **Trusted application servers**.</span></span>

5.  <span data-ttu-id="8fe2c-127">Expanda el nodo **Servidores de aplicaciones de confianza**.</span><span class="sxs-lookup"><span data-stu-id="8fe2c-127">Expand the **Trusted application servers** node.</span></span>

6.  <span data-ttu-id="8fe2c-128">Ahora debería ver el servidor CAS de Exchange 2013 como un servidor de aplicaciones de confianza.</span><span class="sxs-lookup"><span data-stu-id="8fe2c-128">You should now see the Exchange 2013 CAS server listed as a trusted application server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

