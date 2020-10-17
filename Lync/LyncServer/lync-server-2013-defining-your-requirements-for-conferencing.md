---
title: 'Lync Server 2013: definición de los requisitos para las conferencias'
description: 'Lync Server 2013: definición de los requisitos para las conferencias.'
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
ms.openlocfilehash: 009a80d2fd48341723743bb6a06ad2ee05289a6c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545416"
---
# <a name="defining-your-requirements-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="c6851-103">Definición de los requisitos para las conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6851-103">Defining your requirements for conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6851-104">_**Última modificación del tema:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="c6851-104">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="c6851-105">Al determinar qué capacidades de conferencia se van a implementar, debe tener en cuenta las características que desea que estén disponibles para los usuarios y las capacidades de ancho de banda de la red.</span><span class="sxs-lookup"><span data-stu-id="c6851-105">When you are determining which conferencing capabilities to deploy, you need to consider the features that you want available to your users and your network bandwidth capabilities.</span></span> <span data-ttu-id="c6851-106">La lista de preguntas que aparece a continuación le orienta a través del proceso de planeación de conferencia para determinar qué características de conferencia deberá implementar en función de los requisitos de su organización.</span><span class="sxs-lookup"><span data-stu-id="c6851-106">The following list of questions guides you through the conferencing planning process to determine what features of conferencing you should deploy, based on your organization’s requirements.</span></span>

  - <span data-ttu-id="c6851-107">**¿Desea habilitar la conferencia web, lo que incluye colaboración en documentos y uso compartido de aplicaciones?**</span><span class="sxs-lookup"><span data-stu-id="c6851-107">**Do you want to enable web conferencing, which includes document collaboration and application sharing?**</span></span>
    
    <span data-ttu-id="c6851-108">Si es así, debe habilitar las conferencias para el grupo de servidores front-end en la herramienta de planeación de Microsoft Lync Server 2013, o en el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="c6851-108">If so, you must enable conferencing for your Front End pool in the Microsoft Lync Server 2013, Planning Tool or in Topology Builder.</span></span> <span data-ttu-id="c6851-109">Al habilitar las conferencias, se habilitan las conferencias web y A/V.</span><span class="sxs-lookup"><span data-stu-id="c6851-109">When you enable conferencing, you enable both web conferencing and A/V conferencing.</span></span>
    
    <span data-ttu-id="c6851-110">El uso compartido de aplicaciones requiere y usa un mayor ancho de banda que la colaboración en documentos.</span><span class="sxs-lookup"><span data-stu-id="c6851-110">Application sharing requires and uses more network bandwidth than document collaboration.</span></span> <span data-ttu-id="c6851-111">Lync Server 2013 proporciona un mecanismo de limitación para controlar cada sesión de uso compartido de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="c6851-111">Lync Server 2013 provides a throttling mechanism to control each application sharing session.</span></span> <span data-ttu-id="c6851-112">De forma predeterminada, este está establecido en 1,5 KB/segundo para cada sesión.</span><span class="sxs-lookup"><span data-stu-id="c6851-112">By default, this is set to 1.5 KB/second for each session.</span></span>
    
    <span data-ttu-id="c6851-113">Si no desea habilitar el uso compartido de aplicaciones pero desea permitir la colaboración en documentos, puede habilitar la conferencia y usar directivas de reunión para deshabilitar el uso compartido de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="c6851-113">If you do not want to enable application sharing but you do want document collaboration, you can enable conferencing and use meeting policies to disable application sharing.</span></span> <span data-ttu-id="c6851-114">Para más información sobre cómo configurar las directivas de reuniones, consulte [directivas de conferencia en Lync Server 2013](lync-server-2013-conferencing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="c6851-114">For details about configuring meeting policies, see [Conferencing policies in Lync Server 2013](lync-server-2013-conferencing-policies.md).</span></span>
    
    <span data-ttu-id="c6851-115">Para permitir que los usuarios compartan presentaciones de PowerPoint, debe configurar Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="c6851-115">To enable users to share PowerPoint presentations, you need to configure Office Web Apps Server.</span></span> <span data-ttu-id="c6851-116">Para más información sobre la configuración de Office Web Apps Server, vea [Configuring Integration with Office Web Apps Server y Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="c6851-116">For details about configuring Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

  - <span data-ttu-id="c6851-117">**¿Desea habilitar la conferencia A/V?**</span><span class="sxs-lookup"><span data-stu-id="c6851-117">**Do you want to enable A/V conferencing?**</span></span>
    
    <span data-ttu-id="c6851-118">Si es así, debe habilitar las conferencias para el grupo de servidores front-end en la herramienta de planeación de Lync Server 2013 o en el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="c6851-118">If so, you must enable conferencing for your Front End pool in the Lync Server 2013, Planning Tool or in Topology Builder.</span></span> <span data-ttu-id="c6851-119">Al habilitar las conferencias, se habilitan las conferencias web y A/V.</span><span class="sxs-lookup"><span data-stu-id="c6851-119">When you enable conferencing, you enable both web conferencing and A/V conferencing.</span></span>
    
    <span data-ttu-id="c6851-120">La conferencia A/V requiere y usa un mayor ancho de banda que la conferencia web (lo que incluye la colaboración en documentos y los recursos compartidos de aplicaciones).</span><span class="sxs-lookup"><span data-stu-id="c6851-120">A/V conferencing requires and uses more network bandwidth than web conferencing (which includes document collaboration and application sharing).</span></span> <span data-ttu-id="c6851-121">Si no desea habilitar la conferencia A/V pero desea habilitar la conferencia Web, puede habilitar la Conferencia y usar las directivas de reunión para deshabilitar las conferencias de A/V.</span><span class="sxs-lookup"><span data-stu-id="c6851-121">If you do not want to enable A/V conferencing but you do want to enable web conferencing, you can enable conferencing and use meeting policies to disable A/V conferences.</span></span>
    
    <span data-ttu-id="c6851-p108">Si desea habilitar las conferencias de audio, pero no las conferencias de vídeo, puede habilitar la conferencia A/V y usar directivas de reunión para evitar las conferencias de vídeo. Como alternativa, puede habilitar la conferencia A/V y habilitar solo a determinados usuarios para que inicien conferencias A/V o participen en ellas.</span><span class="sxs-lookup"><span data-stu-id="c6851-p108">If you do want to enable audio conferences but not video conferences, you can enable A/V conferencing and use meeting policies to prevent video conferences. Alternatively, you can enable A/V conferencing and enable only certain users to start or participate in A/V conferences.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c6851-124">La telefonía IP empresarial no es necesaria para usar la conferencia A/V.</span><span class="sxs-lookup"><span data-stu-id="c6851-124">Enterprise Voice is not required for you to use A/V conferencing.</span></span> <span data-ttu-id="c6851-125">Si habilita las conferencias A/V, los usuarios pueden agregar audio a sus conferencias si tienen dispositivos de audio, incluso si usa una PBX para la solución telefónica.</span><span class="sxs-lookup"><span data-stu-id="c6851-125">If you enable A/V conferencing, your users can add audio to their conferences if they have audio devices, even if you use a PBX for your telephone solution.</span></span>

    
    </div>

  - <span data-ttu-id="c6851-126">**¿Desea permitir que los usuarios se unan a secciones de audio de conferencias al usar un teléfono RTC?**</span><span class="sxs-lookup"><span data-stu-id="c6851-126">**Do you want to enable users to join the audio portion of conferences when using a PSTN phone?**</span></span>
    
    <span data-ttu-id="c6851-p110">Si es así, implemente y habilite las conferencias de acceso telefónico local. De este modo, los usuarios invitados, tanto de dentro como de fuera de la organización, podrán unirse a la sección de audio de las conferencias a través de un teléfono RTC.</span><span class="sxs-lookup"><span data-stu-id="c6851-p110">If so, deploy and enable dial-in conferencing. Invited users, both inside and outside your organization, can then join the audio portion of conferences by using a PSTN phone.</span></span>

  - <span data-ttu-id="c6851-129">**¿Desea habilitar a los usuarios externos con clientes de Lync Server 2013 para que se unan a los tipos de conferencias que ha habilitado?**</span><span class="sxs-lookup"><span data-stu-id="c6851-129">**Do you want to enable external users with Lync Server 2013 clients to join the types of conferences that you have enabled?**</span></span>
    
    <span data-ttu-id="c6851-130">De ser así, deberá implementar servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="c6851-130">If so, you should deploy Edge Servers.</span></span> <span data-ttu-id="c6851-131">Al permitir la participación externa en las reuniones, se maximiza la inversión en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c6851-131">By allowing external participation in meetings, you maximize your investment in Lync Server 2013.</span></span> <span data-ttu-id="c6851-132">Por ejemplo, los usuarios con equipos portátiles con Lync Server 2013 pueden unirse a conferencias desde cualquier lugar: en el domicilio, en el aeropuerto o en los sitios de los clientes.</span><span class="sxs-lookup"><span data-stu-id="c6851-132">For example, users with laptops with Lync Server 2013 can join conferences from wherever they are—at home, in the airport, or at customer sites.</span></span>
    
    <span data-ttu-id="c6851-133">Asimismo, la implementación de servidores perimetrales permite crear relaciones federadas con otras organizaciones, por ejemplo, sus clientes o proveedores. Así los usuarios de dichas organizaciones pueden colaborar con mayor facilidad con sus usuarios.</span><span class="sxs-lookup"><span data-stu-id="c6851-133">Additionally, with Edge Servers deployed you can create federated relationships with other organizations-such as your customers or vendors-and users from those organizations can more easily collaborate with your users.</span></span>
    
    <span data-ttu-id="c6851-134">Para obtener más información sobre la implementación de servidores perimetrales, consulte [Planning for external User Access in Lync server 2013](lync-server-2013-planning-for-external-user-access.md) e [Deploying external User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="c6851-134">For details about deploying Edge Servers, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span> <span data-ttu-id="c6851-135">Para obtener más información sobre cómo habilitar el acceso externo para Office Web Apps Server, consulte [Publishing Office Web Apps Server in Lync Server 2013 Using a inverso Proxy Server](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md).</span><span class="sxs-lookup"><span data-stu-id="c6851-135">For details about enabling external access for Office Web Apps Server, see [Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md).</span></span>

  - <span data-ttu-id="c6851-136">**¿Desea controlar los clientes que pueden unirse a reuniones de Lync Server 2013?**</span><span class="sxs-lookup"><span data-stu-id="c6851-136">**Do you want to control the clients that can join Lync Server 2013 meetings?**</span></span>
    
    <span data-ttu-id="c6851-137">Si es así, debe configurar la página de participación en la reunión para que solo estén disponibles las opciones de cliente que desea admitir.</span><span class="sxs-lookup"><span data-stu-id="c6851-137">If so, you should configure the meeting join page so that only the client options that you want to support are available.</span></span> <span data-ttu-id="c6851-138">Cada vez que un usuario hace clic en un vínculo para unirse a una reunión programada, Lync Server 2013 detecta si un cliente ya está instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="c6851-138">Each time a user clicks a link to join a scheduled meeting, Lync Server 2013 detects whether a client is already installed on the computer.</span></span> <span data-ttu-id="c6851-139">A continuación, inicia el cliente predeterminado y abre la página de participación en la reunión, que contiene vínculos para clientes alternativos.</span><span class="sxs-lookup"><span data-stu-id="c6851-139">It then starts the default client and opens the meeting join page, which contains links for alternate clients.</span></span> <span data-ttu-id="c6851-140">La página para participar en reuniones contiene siempre la opción de usar Microsoft Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="c6851-140">The meeting join page always contains the option to use Microsoft Lync Web App.</span></span> <span data-ttu-id="c6851-141">Además de esta opción, puede decidir si desea incluir vínculos para asistentes y versiones anteriores de Communicator.</span><span class="sxs-lookup"><span data-stu-id="c6851-141">In addition to this option, you can decide whether to include links for Attendee and previous versions of Communicator.</span></span> <span data-ttu-id="c6851-142">Para obtener más información, consulte [configurar la página de participación en la reunión en Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md).</span><span class="sxs-lookup"><span data-stu-id="c6851-142">For details, see [Configuring the meeting join page in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c6851-143">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c6851-143">In This Section</span></span>

  - [<span data-ttu-id="c6851-144">Requisitos de conferencia web en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6851-144">Web conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-web-conferencing-requirements.md)

  - [<span data-ttu-id="c6851-145">Requisitos de conferencia A/V en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6851-145">A/V conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-a-v-conferencing-requirements.md)

  - [<span data-ttu-id="c6851-146">Requisitos de conferencia de acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6851-146">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c6851-147">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c6851-147">See Also</span></span>


[<span data-ttu-id="c6851-148">Planeación de conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6851-148">Planning for conferencing in Lync Server 2013</span></span>](lync-server-2013-planning-for-conferencing.md)  
[<span data-ttu-id="c6851-149">Lista de comprobación para la implementación de conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6851-149">Deployment checklist for conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

