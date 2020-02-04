---
title: 'Lync Server 2013: Definición de requisitos para conferencias'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for conferencing
ms:assetid: 5c83e268-22bf-42b2-bac3-3237b5e02e03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204935(v=OCS.15)
ms:contentKeyID: 48184255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c19269ef06fc2aa7ec19e2ede53f406b345536b3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739960"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="6de9b-102">Definición de requisitos para conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6de9b-102">Defining your requirements for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6de9b-103">_**Última modificación del tema:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="6de9b-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="6de9b-104">Al determinar qué funciones de conferencia se van a implementar, es necesario tener en cuenta las características que quiere poner a disposición de los usuarios, así como la capacidad de ancho de banda de la red.</span><span class="sxs-lookup"><span data-stu-id="6de9b-104">When you are determining which conferencing capabilities to deploy, you need to consider the features that you want available to your users and your network bandwidth capabilities.</span></span> <span data-ttu-id="6de9b-105">La siguiente lista de preguntas le guiará a través del proceso de planeación de conferencias para determinar qué características de las conferencias debe implementar, en función de los requisitos de la organización.</span><span class="sxs-lookup"><span data-stu-id="6de9b-105">The following list of questions guides you through the conferencing planning process to determine what features of conferencing you should deploy, based on your organization’s requirements.</span></span>

  - <span data-ttu-id="6de9b-106">**¿Desea habilitar la conferencia web, que incluye la colaboración con documentos y el uso compartido de aplicaciones?**</span><span class="sxs-lookup"><span data-stu-id="6de9b-106">**Do you want to enable web conferencing, which includes document collaboration and application sharing?**</span></span>
    
    <span data-ttu-id="6de9b-107">Si es así, debe habilitar las conferencias para el grupo de servidores front-end en Microsoft Lync Server 2013, la herramienta de planeación o el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="6de9b-107">If so, you must enable conferencing for your Front End pool in the Microsoft Lync Server 2013, Planning Tool or in Topology Builder.</span></span> <span data-ttu-id="6de9b-108">Cuando se habilita la Conferencia, se habilitan las conferencias web y A/V.</span><span class="sxs-lookup"><span data-stu-id="6de9b-108">When you enable conferencing, you enable both web conferencing and A/V conferencing.</span></span>
    
    <span data-ttu-id="6de9b-109">El uso compartido de aplicaciones requiere y utiliza más ancho de banda de red que la colaboración en documentos.</span><span class="sxs-lookup"><span data-stu-id="6de9b-109">Application sharing requires and uses more network bandwidth than document collaboration.</span></span> <span data-ttu-id="6de9b-110">Lync Server 2013 proporciona un mecanismo de limitación para controlar cada sesión de uso compartido de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="6de9b-110">Lync Server 2013 provides a throttling mechanism to control each application sharing session.</span></span> <span data-ttu-id="6de9b-111">De forma predeterminada, esto se establece en 1,5 KB por segundo para cada sesión.</span><span class="sxs-lookup"><span data-stu-id="6de9b-111">By default, this is set to 1.5 KB/second for each session.</span></span>
    
    <span data-ttu-id="6de9b-112">Si no desea habilitar el uso compartido de aplicaciones pero desea la colaboración de documentos, puede habilitar la Conferencia y usar las directivas de reunión para deshabilitar el uso compartido de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="6de9b-112">If you do not want to enable application sharing but you do want document collaboration, you can enable conferencing and use meeting policies to disable application sharing.</span></span> <span data-ttu-id="6de9b-113">Para obtener más información sobre cómo configurar directivas de reunión, consulte [directivas de conferencia en Lync Server 2013](lync-server-2013-conferencing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="6de9b-113">For details about configuring meeting policies, see [Conferencing policies in Lync Server 2013](lync-server-2013-conferencing-policies.md).</span></span>
    
    <span data-ttu-id="6de9b-114">Para que los usuarios puedan compartir presentaciones de PowerPoint, necesita configurar Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="6de9b-114">To enable users to share PowerPoint presentations, you need to configure Office Web Apps Server.</span></span> <span data-ttu-id="6de9b-115">Para obtener más información sobre cómo configurar Office Web Apps Server, vea [configurar la integración con Office Web Apps Server y Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="6de9b-115">For details about configuring Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

  - <span data-ttu-id="6de9b-116">**¿Desea habilitar las conferencias A/V?**</span><span class="sxs-lookup"><span data-stu-id="6de9b-116">**Do you want to enable A/V conferencing?**</span></span>
    
    <span data-ttu-id="6de9b-117">Si es así, debe habilitar las conferencias para el grupo de servidores front-end en Lync Server 2013, la herramienta de planeación o en el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="6de9b-117">If so, you must enable conferencing for your Front End pool in the Lync Server 2013, Planning Tool or in Topology Builder.</span></span> <span data-ttu-id="6de9b-118">Cuando se habilita la Conferencia, se habilitan las conferencias web y A/V.</span><span class="sxs-lookup"><span data-stu-id="6de9b-118">When you enable conferencing, you enable both web conferencing and A/V conferencing.</span></span>
    
    <span data-ttu-id="6de9b-119">Las conferencias A/V requieren y usan más ancho de banda de la red que las conferencias web (que incluyen colaboración de documentos y uso compartido de aplicaciones).</span><span class="sxs-lookup"><span data-stu-id="6de9b-119">A/V conferencing requires and uses more network bandwidth than web conferencing (which includes document collaboration and application sharing).</span></span> <span data-ttu-id="6de9b-120">Si no desea habilitar una conferencia a/V pero desea habilitar las conferencias web, puede habilitar la Conferencia y usar las directivas de reunión para deshabilitar las conferencias de A/V.</span><span class="sxs-lookup"><span data-stu-id="6de9b-120">If you do not want to enable A/V conferencing but you do want to enable web conferencing, you can enable conferencing and use meeting policies to disable A/V conferences.</span></span>
    
    <span data-ttu-id="6de9b-121">Si desea habilitar conferencias de audio pero no videoconferencias, puede habilitar conferencias A/V y usar directivas de reunión para evitar las videoconferencias.</span><span class="sxs-lookup"><span data-stu-id="6de9b-121">If you do want to enable audio conferences but not video conferences, you can enable A/V conferencing and use meeting policies to prevent video conferences.</span></span> <span data-ttu-id="6de9b-122">Como alternativa, puede habilitar la conferencia A/V y habilitar únicamente determinados usuarios para que inicien o participen en conferencias A/V.</span><span class="sxs-lookup"><span data-stu-id="6de9b-122">Alternatively, you can enable A/V conferencing and enable only certain users to start or participate in A/V conferences.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6de9b-p109">No se necesita la telefonía IP empresarial para usar las conferencias A/V. Si habilita las conferencias A/V, los usuarios que dispongan de dispositivos de audio podrán agregar audio a las conferencias, aun cuando se use una PBX como solución de telefonía.</span><span class="sxs-lookup"><span data-stu-id="6de9b-p109">Enterprise Voice is not required for you to use A/V conferencing. If you enable A/V conferencing, your users can add audio to their conferences if they have audio devices, even if you use a PBX for your telephone solution.</span></span>

    
    </div>

  - <span data-ttu-id="6de9b-125">**¿Desea permitir que los usuarios se unan a la parte de audio de las conferencias al usar un teléfono PSTN?**</span><span class="sxs-lookup"><span data-stu-id="6de9b-125">**Do you want to enable users to join the audio portion of conferences when using a PSTN phone?**</span></span>
    
    <span data-ttu-id="6de9b-p110">Si es así, implemente y habilite la conferencia de acceso telefónico. Los usuarios invitados, tanto dentro como fuera de su organización, puede unirse entonces a la parte de audio de las conferencias por medio de un teléfono RTC.</span><span class="sxs-lookup"><span data-stu-id="6de9b-p110">If so, deploy and enable dial-in conferencing. Invited users, both inside and outside your organization, can then join the audio portion of conferences by using a PSTN phone.</span></span>

  - <span data-ttu-id="6de9b-128">**¿Desea permitir que los usuarios externos con clientes de Lync Server 2013 se unan a los tipos de conferencias que haya habilitado?**</span><span class="sxs-lookup"><span data-stu-id="6de9b-128">**Do you want to enable external users with Lync Server 2013 clients to join the types of conferences that you have enabled?**</span></span>
    
    <span data-ttu-id="6de9b-129">Si es así, debe implementar servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="6de9b-129">If so, you should deploy Edge Servers.</span></span> <span data-ttu-id="6de9b-130">Al permitir la participación externa en las reuniones, podrá maximizar su inversión en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6de9b-130">By allowing external participation in meetings, you maximize your investment in Lync Server 2013.</span></span> <span data-ttu-id="6de9b-131">Por ejemplo, los usuarios con equipos portátiles con Lync Server 2013 pueden unirse a las conferencias desde cualquier lugar: en casa, en el aeropuerto o en los sitios de los clientes.</span><span class="sxs-lookup"><span data-stu-id="6de9b-131">For example, users with laptops with Lync Server 2013 can join conferences from wherever they are—at home, in the airport, or at customer sites.</span></span>
    
    <span data-ttu-id="6de9b-132">Además, con los servidores perimetrales implementados, puede crear relaciones federadas con otras organizaciones, como los clientes o los proveedores, y los usuarios de esas organizaciones pueden colaborar más fácilmente con los usuarios.</span><span class="sxs-lookup"><span data-stu-id="6de9b-132">Additionally, with Edge Servers deployed you can create federated relationships with other organizations-such as your customers or vendors-and users from those organizations can more easily collaborate with your users.</span></span>
    
    <span data-ttu-id="6de9b-133">Para obtener más información sobre la implementación de servidores perimetrales, vea [planear el acceso de usuarios externos en Lync server 2013](lync-server-2013-planning-for-external-user-access.md) e [implementar el acceso de usuarios externos en Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="6de9b-133">For details about deploying Edge Servers, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span> <span data-ttu-id="6de9b-134">Para obtener detalles sobre cómo habilitar el acceso externo para Office Web Apps Server, consulte [publicación de Office Web Apps Server en Lync Server 2013 con un servidor proxy inverso](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md).</span><span class="sxs-lookup"><span data-stu-id="6de9b-134">For details about enabling external access for Office Web Apps Server, see [Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md).</span></span>

  - <span data-ttu-id="6de9b-135">**¿Desea controlar los clientes que pueden unirse a reuniones de Lync Server 2013?**</span><span class="sxs-lookup"><span data-stu-id="6de9b-135">**Do you want to control the clients that can join Lync Server 2013 meetings?**</span></span>
    
    <span data-ttu-id="6de9b-136">En caso afirmativo, necesitará configurar una página de participación en la reunión para que solo estén disponibles las opciones de cliente que quiera permitir.</span><span class="sxs-lookup"><span data-stu-id="6de9b-136">If so, you should configure the meeting join page so that only the client options that you want to support are available.</span></span> <span data-ttu-id="6de9b-137">Cada vez que un usuario hace clic en un vínculo para unirse a una reunión programada, Lync Server 2013 detecta si un cliente ya está instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="6de9b-137">Each time a user clicks a link to join a scheduled meeting, Lync Server 2013 detects whether a client is already installed on the computer.</span></span> <span data-ttu-id="6de9b-138">Luego inicia el cliente predeterminado y abre la página de participación en la reunión, que contiene vínculos para clientes alternativos.</span><span class="sxs-lookup"><span data-stu-id="6de9b-138">It then starts the default client and opens the meeting join page, which contains links for alternate clients.</span></span> <span data-ttu-id="6de9b-139">La página de la combinación de reuniones siempre contiene la opción de usar Microsoft Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="6de9b-139">The meeting join page always contains the option to use Microsoft Lync Web App.</span></span> <span data-ttu-id="6de9b-140">Además de esta opción, puede decidir si desea incluir vínculos para asistentes y para versiones anteriores de Communicator.</span><span class="sxs-lookup"><span data-stu-id="6de9b-140">In addition to this option, you can decide whether to include links for Attendee and previous versions of Communicator.</span></span> <span data-ttu-id="6de9b-141">Para obtener más información, vea [configurar la página de combinación de reuniones en Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md).</span><span class="sxs-lookup"><span data-stu-id="6de9b-141">For details, see [Configuring the meeting join page in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6de9b-142">En esta sección</span><span class="sxs-lookup"><span data-stu-id="6de9b-142">In This Section</span></span>

  - [<span data-ttu-id="6de9b-143">Requisitos de conferencia web en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6de9b-143">Web conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-web-conferencing-requirements.md)

  - [<span data-ttu-id="6de9b-144">Requisitos de conferencia A/V en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6de9b-144">A/V conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-a-v-conferencing-requirements.md)

  - [<span data-ttu-id="6de9b-145">Requisitos de las conferencias de acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6de9b-145">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6de9b-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="6de9b-146">See Also</span></span>


[<span data-ttu-id="6de9b-147">Planificar conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6de9b-147">Planning for conferencing in Lync Server 2013</span></span>](lync-server-2013-planning-for-conferencing.md)  
[<span data-ttu-id="6de9b-148">Lista de comprobación para la implementación de conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6de9b-148">Deployment checklist for conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

