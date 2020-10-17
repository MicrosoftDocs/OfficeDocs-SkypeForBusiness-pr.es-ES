---
title: 'Lync Server 2013: configuración de la mensajería unificada en Microsoft Exchange Server para trabajar con Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Unified Messaging on Microsoft Exchange Server to work with Lync Server 2013
ms:assetid: 058da9c4-23af-4ddb-9f63-70133a8aafc6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398106(v=OCS.15)
ms:contentKeyID: 48183289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 462252b1826802ec424c6684e3a6347754095508
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517057"
---
# <a name="configuring-unified-messaging-on-microsoft-exchange-server-to-work-with-lync-server-2013"></a><span data-ttu-id="204e1-102">Configuración de la mensajería unificada en Microsoft Exchange Server para trabajar con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="204e1-102">Configuring Unified Messaging on Microsoft Exchange Server to work with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="204e1-103">_**Última modificación del tema:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="204e1-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="204e1-104">Si desea usar la mensajería unificada (UM) de Exchange para proporcionar servicios de contestador automático, Outlook Voice Access o operador automático para los usuarios de Enterprise Voice, consulte <A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">Planning for Exchange Unified Messaging Integration in Lync Server 2013</A> en la documentación referente a la planeación y, a continuación, siga las instrucciones de esta sección.</span><span class="sxs-lookup"><span data-stu-id="204e1-104">If you want to use Exchange Unified Messaging (UM) to provide call answering, Outlook Voice Access, or auto-attendant services for Enterprise Voice users, read <A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">Planning for Exchange Unified Messaging integration in Lync Server 2013</A> in the Planning documentation, and then follow the instructions in this section.</span></span>



</div>

<span data-ttu-id="204e1-105">Para configurar la mensajería unificada (MU) de Exchange para que funcione con la telefonía IP empresarial, deberá realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="204e1-105">To configure Exchange Unified Messaging (UM) to work with Enterprise Voice, you’ll need to perform the following tasks:</span></span>

  - <span data-ttu-id="204e1-106">Configurar certificados en el servidor que ejecuta los servicios de mensajería unificada (MU) de Exchange</span><span class="sxs-lookup"><span data-stu-id="204e1-106">Configure certificates on the server running Exchange Unified Messaging (UM) services</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="204e1-107">Agregue todos los servidores de acceso de cliente y de buzones de correo a todos los planes de marcado URI de SIP de MU.</span><span class="sxs-lookup"><span data-stu-id="204e1-107">Add all Client Access and Mailbox servers to all UM SIP URI dial plans.</span></span> <span data-ttu-id="204e1-108">Si no es así, el enrutamiento de llamadas salientes no funciona según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="204e1-108">If not, outbound call routing won’t work as expected.</span></span>

    
    </div>

  - <span data-ttu-id="204e1-109">Cree uno o varios planes de marcado URI de SIP de mensajería unificada, junto con los números de teléfono de acceso de suscriptor, según sea necesario y, a continuación, cree los planes de marcado de Lync Server correspondientes.</span><span class="sxs-lookup"><span data-stu-id="204e1-109">Create one or more UM SIP URI dial plans, along with the subscriber access phone numbers, as needed, and then create corresponding Lync Server dial plans.</span></span>

  - <span data-ttu-id="204e1-110">Use el script **exchucutil.ps1** para:</span><span class="sxs-lookup"><span data-stu-id="204e1-110">Use the **exchucutil.ps1** script to:</span></span>
    
      - <span data-ttu-id="204e1-111">Crear puertas de enlace IP de Mensajería unificada.</span><span class="sxs-lookup"><span data-stu-id="204e1-111">Create UM IP gateways.</span></span>
    
      - <span data-ttu-id="204e1-112">Crear grupos de extensiones de Mensajería unificada.</span><span class="sxs-lookup"><span data-stu-id="204e1-112">Create UM hunt groups.</span></span>
    
      - <span data-ttu-id="204e1-113">Conceda a Lync Server 2013 permiso para leer objetos de servicios de dominio de Active Directory de mensajería unificada.</span><span class="sxs-lookup"><span data-stu-id="204e1-113">Grant Lync Server 2013 permission to read UM Active Directory Domain Services objects.</span></span>

  - <span data-ttu-id="204e1-114">Cree un objeto de operador automático de mensajería unificada.</span><span class="sxs-lookup"><span data-stu-id="204e1-114">Create a UM auto-attendant object.</span></span>

  - <span data-ttu-id="204e1-115">Cree un objeto de acceso de suscriptor.</span><span class="sxs-lookup"><span data-stu-id="204e1-115">Create a subscriber access object.</span></span>

  - <span data-ttu-id="204e1-116">Cree un URI de SIP para cada usuario y asocie a los usuarios con un plan de marcado URI de SIP de mensajería unificada.</span><span class="sxs-lookup"><span data-stu-id="204e1-116">Create a SIP URI for each user and associating users with a UM SIP URI dial plan.</span></span>

<div>

## <a name="requirements-and-recommendations"></a><span data-ttu-id="204e1-117">Requisitos y recomendaciones</span><span class="sxs-lookup"><span data-stu-id="204e1-117">Requirements and Recommendations</span></span>

<span data-ttu-id="204e1-118">Antes de empezar, en la documentación de esta sección se supone que ha implementado los siguientes roles de Exchange 2013: acceso de cliente y buzón de correo.</span><span class="sxs-lookup"><span data-stu-id="204e1-118">Before you begin, the documentation in this section assumes that you have deployed the following Exchange 2013 roles: Client Access and Mailbox.</span></span> <span data-ttu-id="204e1-119">En Microsoft Exchange Server 2013, la mensajería unificada de Exchange se ejecuta como un servicio en estos servidores.</span><span class="sxs-lookup"><span data-stu-id="204e1-119">In Microsoft Exchange Server 2013, Exchange UM runs as a service on these servers.</span></span>

<span data-ttu-id="204e1-120">Para obtener más información sobre la implementación de Exchange 2013, consulte la biblioteca de TechNet de Exchange 2013 en [https://go.microsoft.com/fwlink/p/?LinkId=266637](https://go.microsoft.com/fwlink/p/?linkid=266637)</span><span class="sxs-lookup"><span data-stu-id="204e1-120">For details about deploying Exchange 2013, see the Exchange 2013 TechNet Library at [https://go.microsoft.com/fwlink/p/?LinkId=266637](https://go.microsoft.com/fwlink/p/?linkid=266637)</span></span>

<span data-ttu-id="204e1-121">También debe tener en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="204e1-121">Also note the following:</span></span>

  - <span data-ttu-id="204e1-122">Si la mensajería unificada de Exchange está instalada en varios bosques, los pasos de integración del servidor de Exchange deben realizarse para cada bosque de mensajería unificada.</span><span class="sxs-lookup"><span data-stu-id="204e1-122">If Exchange UM is installed in multiple forests, the Exchange Server integration steps must be performed for each UM forest.</span></span> <span data-ttu-id="204e1-123">Además, cada bosque de MU debe configurarse para confiar en el bosque en el que se implementa Lync Server 2013 y el bosque en el que se implementa Lync Server 2013 debe estar configurado para confiar en cada bosque de MU.</span><span class="sxs-lookup"><span data-stu-id="204e1-123">In addition, each UM forest must be configured to trust the forest in which Lync Server 2013 is deployed, and the forest in which Lync Server 2013 is deployed must be configured to trust each UM forest.</span></span>

  - <span data-ttu-id="204e1-124">Los pasos de integración se realizan en los roles de servidor de Exchange donde se ejecutan los servicios de mensajería unificada y en el servidor que ejecuta Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="204e1-124">Integration steps are performed on both the Exchange Server roles where Unified Messaging services are running, and on the server running Lync Server 2013.</span></span> <span data-ttu-id="204e1-125">Debe realizar los pasos de integración de mensajería unificada de Exchange Server antes de realizar los pasos de integración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="204e1-125">You should perform the Exchange Server Unified Messaging integration steps before you perform the Lync Server 2013 integration steps.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="204e1-126">Para ver qué pasos de integración se realizan en qué servidores y por qué roles de administrador, vea <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">proceso de implementación para la integración de la mensajería unificada local y Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="204e1-126">To see which integration steps are performed on which servers and by which administrator roles, see <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</A>.</span></span>

    
    </div>

<span data-ttu-id="204e1-127">Las siguientes herramientas deben estar disponibles en cada servidor que ejecuta la mensajería unificada de Exchange:</span><span class="sxs-lookup"><span data-stu-id="204e1-127">The following tools must be available on each server running Exchange UM:</span></span>

  - <span data-ttu-id="204e1-128">Shell de administración de Exchange</span><span class="sxs-lookup"><span data-stu-id="204e1-128">Exchange Management Shell</span></span>

  - <span data-ttu-id="204e1-129">El script **exchucutil.ps1**, que realiza las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="204e1-129">The script **exchucutil.ps1**, which performs the following tasks:</span></span>
    
      - <span data-ttu-id="204e1-130">Crea una puerta de enlace IP de mensajería unificada para cada Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="204e1-130">Creates a UM IP gateway for each Lync Server 2013.</span></span>
    
      - <span data-ttu-id="204e1-131">Crea un grupo de búsqueda para cada puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="204e1-131">Creates a hunt group for each gateway.</span></span> <span data-ttu-id="204e1-132">El identificador piloto de cada grupo de extensiones especifica el plan de marcado URI del SIP de mensajería unificada usado por el grupo de servidores front-end o el servidor Standard Edition asociado a la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="204e1-132">The pilot identifier of each hunt group specifies the UM SIP URI dial plan used by the Front End pool or Standard Edition server that is associated with the gateway.</span></span>
    
      - <span data-ttu-id="204e1-133">Concede el permiso Lync Server 2013 para leer objetos de mensajería unificada de Exchange en servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="204e1-133">Grants Lync Server 2013 permission to read Exchange UM objects in Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="204e1-134">En esta sección</span><span class="sxs-lookup"><span data-stu-id="204e1-134">In This Section</span></span>

  - [<span data-ttu-id="204e1-135">Configurar certificados en el servidor que ejecuta la mensajería unificada de Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="204e1-135">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</span></span>](lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md)

  - [<span data-ttu-id="204e1-136">Configurar la mensajería unificada en Microsoft Exchange para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="204e1-136">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</span></span>](lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

