---
title: Definir y configurar un grupo de servidores front-end o un servidor Standard Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define and configure a Front End pool or Standard Edition server
ms:assetid: 713fc263-23dd-414a-b001-82932e4fe966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398538(v=OCS.15)
ms:contentKeyID: 48184457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f35c49ab232bd69184191ab841431e6c80eca20a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036480"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-and-configure-a-front-end-pool-or-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="7ee15-102">Definir y configurar un grupo de servidores front-end o un servidor Standard Edition en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ee15-102">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ee15-103">_**Última modificación del tema:** 2013-03-08_</span><span class="sxs-lookup"><span data-stu-id="7ee15-103">_**Topic Last Modified:** 2013-03-08_</span></span>

<span data-ttu-id="7ee15-p101">Este procedimiento no requiere pertenencia al grupo de dominio con privilegios o de administrador local. Deberá iniciar sesión en un equipo como usuario estándar.</span><span class="sxs-lookup"><span data-stu-id="7ee15-p101">This procedure does not require membership in a local administrator or privileged domain group. You should log on to a computer as a standard user.</span></span>

<span data-ttu-id="7ee15-106">Si va a implementar un servidor de empresa, debe ejecutarse en todo momento un número mínimo de servidores front-end en un grupo.</span><span class="sxs-lookup"><span data-stu-id="7ee15-106">If you are deploying an Enterprise server, a minimum number of Front End Servers in a pool must be running at all times.</span></span> <span data-ttu-id="7ee15-107">En la tabla siguiente, se resumen estos requisitos.</span><span class="sxs-lookup"><span data-stu-id="7ee15-107">The following table summarizes these requirements.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7ee15-108">Número total de servidores front-end en el grupo</span><span class="sxs-lookup"><span data-stu-id="7ee15-108">Total number of Front End Servers in the pool</span></span></th>
<th><span data-ttu-id="7ee15-109">Número necesario de servidores en ejecución para que el grupo sea funcional</span><span class="sxs-lookup"><span data-stu-id="7ee15-109">Number of servers that must be running for pool to be functional</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7ee15-110">1-2</span><span class="sxs-lookup"><span data-stu-id="7ee15-110">1-2</span></span></p></td>
<td><p><span data-ttu-id="7ee15-111">1 </span><span class="sxs-lookup"><span data-stu-id="7ee15-111">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ee15-112">3-4</span><span class="sxs-lookup"><span data-stu-id="7ee15-112">3-4</span></span></p></td>
<td><p><span data-ttu-id="7ee15-113">2 </span><span class="sxs-lookup"><span data-stu-id="7ee15-113">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ee15-114">5-6</span><span class="sxs-lookup"><span data-stu-id="7ee15-114">5-6</span></span></p></td>
<td><p><span data-ttu-id="7ee15-115">3 </span><span class="sxs-lookup"><span data-stu-id="7ee15-115">3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ee15-116">7-8</span><span class="sxs-lookup"><span data-stu-id="7ee15-116">7-8</span></span></p></td>
<td><p><span data-ttu-id="7ee15-117">4 </span><span class="sxs-lookup"><span data-stu-id="7ee15-117">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ee15-118">9-10</span><span class="sxs-lookup"><span data-stu-id="7ee15-118">9-10</span></span></p></td>
<td><p><span data-ttu-id="7ee15-119">5 </span><span class="sxs-lookup"><span data-stu-id="7ee15-119">5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ee15-120">11-12</span><span class="sxs-lookup"><span data-stu-id="7ee15-120">11-12</span></span></p></td>
<td><p><span data-ttu-id="7ee15-121">6 </span><span class="sxs-lookup"><span data-stu-id="7ee15-121">6</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> <span data-ttu-id="7ee15-122">Para Lync Server 2013, siempre que agregue o quite un servidor front-end del grupo de servidores, debe reiniciar los servicios.</span><span class="sxs-lookup"><span data-stu-id="7ee15-122">For Lync Server 2013, any time you add or remove a Front End Server from the pool, you must restart services.</span></span> <span data-ttu-id="7ee15-123">La eliminación y la adición de servidores se deben realizar como operaciones independientes.</span><span class="sxs-lookup"><span data-stu-id="7ee15-123">Removing and adding servers should be done as separate operations.</span></span> <span data-ttu-id="7ee15-124">Por ejemplo, si va a agregar dos servidores front-end y quitar dos servidores front-end, use el siguiente proceso:</span><span class="sxs-lookup"><span data-stu-id="7ee15-124">For example, if you are going to add two Front End Servers and remove two Front End Servers, use the following process:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="7ee15-125">Elimine los dos servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="7ee15-125">Remove the two Front End Servers.</span></span></P>
> <LI>
> <P><span data-ttu-id="7ee15-126">Publique y reactive la topología.</span><span class="sxs-lookup"><span data-stu-id="7ee15-126">Publish and re-activate the topology.</span></span></P>
> <LI>
> <P><span data-ttu-id="7ee15-127">Reinicie los servicios</span><span class="sxs-lookup"><span data-stu-id="7ee15-127">Restart the services</span></span></P>
> <LI>
> <P><span data-ttu-id="7ee15-128">Añada los dos servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="7ee15-128">Add the two Front End Servers.</span></span></P>
> <LI>
> <P><span data-ttu-id="7ee15-129">Publique y reactive a topología.</span><span class="sxs-lookup"><span data-stu-id="7ee15-129">Publish and re-activate the topology.</span></span></P>
> <LI>
> <P><span data-ttu-id="7ee15-130">Reinicie los servicios.</span><span class="sxs-lookup"><span data-stu-id="7ee15-130">Restart the services.</span></span></P></LI></OL>



</div>

<span data-ttu-id="7ee15-131">Una vez que haya definido la topología, use el siguiente procedimiento para definir un grupo de servidores front-end para el sitio.</span><span class="sxs-lookup"><span data-stu-id="7ee15-131">After you have defined your topology, use the following procedure to define a Front End pool for your site.</span></span> <span data-ttu-id="7ee15-132">Para obtener más información sobre cómo definir la topología, consulte [definir y configurar una topología en Topology Builder para Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md).</span><span class="sxs-lookup"><span data-stu-id="7ee15-132">For details about defining the topology, see [Define and configure a topology in Topology Builder for Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md).</span></span>

<div>

## <a name="to-define-a-front-end-pool"></a><span data-ttu-id="7ee15-133">Para definir un grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="7ee15-133">To define a Front End pool</span></span>

1.  <span data-ttu-id="7ee15-134">En el Asistente para definir nuevo grupo de servidores front-end, en la página **Definir nuevo grupo de servidores front-end**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7ee15-134">In the Define New Front End Pool Wizard, on the **Define the New Front End pool** page, click **Next**.</span></span>

2.  <span data-ttu-id="7ee15-135">En la página **definir el FQDN del grupo de servidores front-end** , escriba un nombre de dominio completo (FQDN) para el grupo que va a crear, haga clic en **grupo de servidores front-end Enterprise Edition**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7ee15-135">On the **Define the Front End pool FQDN** page, enter a fully qualified domain name (FQDN) for the pool you are creating, click **Enterprise Edition Front End pool**, and then click **Next**.</span></span>

3.  <span data-ttu-id="7ee15-136">En la página **definir los equipos de este grupo** , escriba un FQDN de equipo para el primer servidor front-end del grupo y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="7ee15-136">On the **Define the computers in this pool** page, enter a computer FQDN for the first Front End Server in the pool, and then click **Add**.</span></span> <span data-ttu-id="7ee15-137">Repita este paso para todos los equipos adicionales (hasta un máximo de doce) que desee agregar al grupo de servidores y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7ee15-137">Repeat this step for any additional computers (up to twelve) that you want to add to the pool, and then click **Next**.</span></span>

4.  <span data-ttu-id="7ee15-138">En la página **Seleccionar características**, active las casillas de las características que desee en este grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="7ee15-138">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="7ee15-139">Por ejemplo, si va a implementar sólo las características de mensajería instantánea (mi) y presencia, active la casilla de verificación **Conferencia** para permitir la mensajería instantánea de varios participantes pero no activar las casillas **Conferencia de acceso telefónico local (RTC)**, **telefonía IP empresarial**o **control de admisión de llamadas** , ya que representan características de conferencia de voz, vídeo y colaboración.</span><span class="sxs-lookup"><span data-stu-id="7ee15-139">For example, if you are deploying only instant messaging (IM) and presence features, you would select the **Conferencing** check box to allow multiparty IM but would not select the **Dial-in (PSTN) conferencing**, **Enterprise Voice**, or **Call Admission Control** check boxes, because they represent voice, video, and collaborative conferencing features.</span></span>
    
      - <span data-ttu-id="7ee15-140">**Conferencia**   : esta selección permite un amplio conjunto de características, entre las que se incluyen:</span><span class="sxs-lookup"><span data-stu-id="7ee15-140">**Conferencing**   This selection enables a rich set of features including:</span></span>
        
          - <span data-ttu-id="7ee15-141">Mensajería instantánea con más de dos interlocutores en una sesión de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="7ee15-141">IM with more than two parties in an IM session.</span></span>
        
          - <span data-ttu-id="7ee15-142">Conferencias, lo que incluye colaboración en documentos, uso compartido de aplicaciones y uso compartido de escritorio</span><span class="sxs-lookup"><span data-stu-id="7ee15-142">Conferencing, which includes document collaboration, application sharing, and desktop sharing.</span></span>
        
          - <span data-ttu-id="7ee15-143">Conferencia a/V, que permite a los usuarios tener conferencias de audio y vídeo (A/V) en tiempo real sin necesidad de servicios externos, como el servicio de Live Meeting o un puente de audio de terceros.</span><span class="sxs-lookup"><span data-stu-id="7ee15-143">A/V conferencing, which enables users to have real-time audio/video (A/V) conferences without the need for external services such as the Live Meeting service or a third-party audio bridge.</span></span>
    
      - <span data-ttu-id="7ee15-144">**Las conferencias**   de acceso telefónico local (RTC) permiten a los usuarios unirse a la parte de audio de una conferencia de Lync Server 2013 mediante un teléfono de red telefónica conmutada (RTC) sin necesidad de un proveedor de servicios de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="7ee15-144">**Dial-in (PSTN) conferencing**   Allows users to join the audio portion of a Lync Server 2013 conference by using a public switched telephone network (PSTN) phone without requiring an audio conferencing provider.</span></span>
    
      - <span data-ttu-id="7ee15-145">**Enterprise Voice**   Enterprise Voice es la solución de voz sobre IP (VoIP) de Lync Server 2013 que permite a los usuarios realizar y recibir llamadas telefónicas.</span><span class="sxs-lookup"><span data-stu-id="7ee15-145">**Enterprise Voice**   Enterprise Voice is the Voice over IP (VoIP) solution in Lync Server 2013 that allows users to make and receive phone calls.</span></span> <span data-ttu-id="7ee15-146">Implementaría esta característica si planea usar Lync Server 2013 para llamadas de voz, correo de voz y otras funciones que usan un dispositivo de hardware o un cliente de software.</span><span class="sxs-lookup"><span data-stu-id="7ee15-146">You would deploy this feature if you plan to use Lync Server 2013 for voice calls, voice mail, and other functions that use a hardware device or a software client.</span></span>
    
      - <span data-ttu-id="7ee15-147">**El CAC de control de admisión de llamadas (CAC)**   determina, en función del ancho de banda de red disponible, si se permite que se establezcan sesiones de comunicaciones en tiempo real, como las llamadas de voz o vídeo.</span><span class="sxs-lookup"><span data-stu-id="7ee15-147">**Call admission control (CAC)**   CAC determines, based on available network bandwidth, whether to allow real-time communications sessions such as voice or video calls to be established.</span></span> <span data-ttu-id="7ee15-148">Si solo ha implementado mensajería instantánea y presencia, no necesita el CAC, ya que ninguna de estas características lo usa.</span><span class="sxs-lookup"><span data-stu-id="7ee15-148">If you have deployed only IM and presence, CAC is not needed because neither of these two features uses CAC.</span></span>
    
      - <span data-ttu-id="7ee15-149">\*\*\*\* El archivado de archivado proporciona una forma de archivar contenido de mensajería instantánea, contenido de conferencias (reuniones) o ambos que se envían a través de Lync Server 2013.   </span><span class="sxs-lookup"><span data-stu-id="7ee15-149">**Archiving**   Archiving provides a way for you to archive IM content, conferencing (meeting) content, or both that is sent through Lync Server 2013.</span></span>
    
      - <span data-ttu-id="7ee15-150">\*\*\*\*   El servidor de supervisión de supervisión permite recopilar datos numéricos que describen la calidad de los medios en la red y los puntos de conexión, la información de uso relacionada con llamadas VoIP, mensajes de mensajería instantánea, conversaciones a/V, reuniones, uso compartido de aplicaciones y transferencias de archivos, así como la información de errores y solución de problemas de llamadas erróneas.</span><span class="sxs-lookup"><span data-stu-id="7ee15-150">**Monitoring**   Monitoring Server enables you to collect numerical data that describes the media quality on your network and endpoints, usage information related to VoIP calls, IM messages, A/V conversations, meetings, application sharing, and file transfers, and call error and troubleshooting information for failed calls.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="7ee15-p109">Si desea habilitar el CAC en la implementación, es preciso habilitarlo exactamente en un grupo de servidores por sitio central. El CAC se recomienda si está implementando características de voz o conferencia A/V.</span><span class="sxs-lookup"><span data-stu-id="7ee15-p109">If you would like to enable CAC in your deployment, it is required that you enable CAC in exactly one pool per central site. CAC is recommended if you are deploying voice features or A/V conferencing.</span></span>

    
    </div>
    
    <span data-ttu-id="7ee15-p110">En la tabla siguiente se muestran las características disponibles (arriba) y las funciones que se ofrecen a los usuarios (izquierda). Las selecciones de la tabla son las opciones que debe seleccionar para habilitar dichas características para su organización.</span><span class="sxs-lookup"><span data-stu-id="7ee15-p110">The following table shows the available features (top) and the functions offered to users (left). The selections in the table are what you should select to enable those features for your organization.</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th></th>
    <th><span data-ttu-id="7ee15-155">Conferencia</span><span class="sxs-lookup"><span data-stu-id="7ee15-155">Conferencing</span></span></th>
    <th><span data-ttu-id="7ee15-156">Conferencia de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="7ee15-156">Dial-In Conferencing</span></span></th>
    <th><span data-ttu-id="7ee15-157">Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="7ee15-157">Enterprise Voice</span></span></th>
    <th><span data-ttu-id="7ee15-158">Control de admisión de llamadas</span><span class="sxs-lookup"><span data-stu-id="7ee15-158">Call Admission Control</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="7ee15-159">Mensajería instantánea y presencia</span><span class="sxs-lookup"><span data-stu-id="7ee15-159">Instant messaging and presence</span></span></p></td>
    <td><p><span data-ttu-id="7ee15-160">X</span><span class="sxs-lookup"><span data-stu-id="7ee15-160">X</span></span></p></td>
    <td></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="7ee15-161">Conferencia</span><span class="sxs-lookup"><span data-stu-id="7ee15-161">Conferencing</span></span></p></td>
    <td><p><span data-ttu-id="7ee15-162">X</span><span class="sxs-lookup"><span data-stu-id="7ee15-162">X</span></span></p></td>
    <td><p><span data-ttu-id="7ee15-163">X</span><span class="sxs-lookup"><span data-stu-id="7ee15-163">X</span></span></p></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="7ee15-164">Conferencia A/V</span><span class="sxs-lookup"><span data-stu-id="7ee15-164">A/V conferencing</span></span></p></td>
    <td><p><span data-ttu-id="7ee15-165">X</span><span class="sxs-lookup"><span data-stu-id="7ee15-165">X</span></span></p></td>
    <td><p><span data-ttu-id="7ee15-166">X</span><span class="sxs-lookup"><span data-stu-id="7ee15-166">X</span></span></p></td>
    <td></td>
    <td><p><span data-ttu-id="7ee15-167">X</span><span class="sxs-lookup"><span data-stu-id="7ee15-167">X</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="7ee15-168">Telefonía IP empresarial</span><span class="sxs-lookup"><span data-stu-id="7ee15-168">Enterprise Voice</span></span></p></td>
    <td></td>
    <td></td>
    <td><p><span data-ttu-id="7ee15-169">X</span><span class="sxs-lookup"><span data-stu-id="7ee15-169">X</span></span></p></td>
    <td><p><span data-ttu-id="7ee15-170">X</span><span class="sxs-lookup"><span data-stu-id="7ee15-170">X</span></span></p></td>
    </tr>
    </tbody>
    </table>


5.  <span data-ttu-id="7ee15-171">En la página **Seleccionar roles de servidor combinados** , puede combinar el servidor de mediación en el servidor front-end o para implementarlo como un servidor independiente.</span><span class="sxs-lookup"><span data-stu-id="7ee15-171">On the **Select collocated server roles** page, you can to collocate the Mediation Server on the Front End Server or to deploy it as a stand-alone server.</span></span>
    
    <span data-ttu-id="7ee15-172">Puede combinar el servidor de mediación en el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="7ee15-172">You can collocate the Mediation Server on the Front End pool.</span></span>
    
      - <span data-ttu-id="7ee15-173">Si va a combinar el servidor de mediación en el grupo de servidores front-end Enterprise Edition, asegúrese de que la casilla está activada.</span><span class="sxs-lookup"><span data-stu-id="7ee15-173">If you intend to collocate the Mediation Server on the Enterprise Edition Front End pool, ensure the check box is selected.</span></span> <span data-ttu-id="7ee15-174">Los roles de servidor se implementarán en los servidores del grupo.</span><span class="sxs-lookup"><span data-stu-id="7ee15-174">The server role will be deployed on the pool servers.</span></span>
    
      - <span data-ttu-id="7ee15-175">Si tiene previsto implementar el servidor de mediación como un servidor independiente, desactive la casilla correspondiente.</span><span class="sxs-lookup"><span data-stu-id="7ee15-175">If you intend to deploy the Mediation Server as a stand-alone server, clear the appropriate check box.</span></span> <span data-ttu-id="7ee15-176">Implementará el servidor de mediación en un paso de implementación independiente después de implementar completamente el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="7ee15-176">You will deploy Mediation Server in a separate deployment step after you completely deploy the Front End Server.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="7ee15-177">Se recomienda combinar el servidor de mediación si fuera posible.</span><span class="sxs-lookup"><span data-stu-id="7ee15-177">We recommend that you collocate the Mediation Server if possible.</span></span> <span data-ttu-id="7ee15-178">Para obtener más información sobre la compatibilidad de los servidores de mediación combinados o independientes, consulte <A href="lync-server-2013-components-and-topologies-for-mediation-server.md">Components and topologs for Mediation Server in Lync Server 2013</A> en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="7ee15-178">For details about support for collocated or stand-alone Mediation Servers, see <A href="lync-server-2013-components-and-topologies-for-mediation-server.md">Components and topologies for Mediation Server in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

6.  <span data-ttu-id="7ee15-179">La página **asociar roles de servidor con este grupo de servidores front-end** permite definir y asociar roles de servidor con el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="7ee15-179">The **Associate server roles with this Front End pool** page lets you define and associate server roles with the Front End pool.</span></span> <span data-ttu-id="7ee15-180">Los tres roles disponibles son:</span><span class="sxs-lookup"><span data-stu-id="7ee15-180">The following role is available:</span></span>
    
    <span data-ttu-id="7ee15-181">**La habilitación**   de un grupo de servidores perimetrales define y asocia un solo servidor perimetral o un grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="7ee15-181">**Enable an Edge pool**   Defines and associates a single Edge Server or a pool of Edge Servers.</span></span> <span data-ttu-id="7ee15-182">Un servidor perimetral facilita la comunicación y la colaboración entre usuarios dentro de la organización y personas fuera de la organización, incluidos los usuarios federados.</span><span class="sxs-lookup"><span data-stu-id="7ee15-182">An Edge Server facilitates communication and collaboration between users inside the organization and people outside the organization, including federated users.</span></span>
    
    <span data-ttu-id="7ee15-183">Existen dos escenarios posibles que pueden usarse para implementar y asociar roles de servidor:</span><span class="sxs-lookup"><span data-stu-id="7ee15-183">There are two possible scenarios that you can use to deploy and associate the server roles:</span></span>
    
    <span data-ttu-id="7ee15-p116">Para el escenario uno, se define una nueva topología para una nueva instalación. Puede acometer la instalación de dos formas:</span><span class="sxs-lookup"><span data-stu-id="7ee15-p116">For scenario one, you are defining a new topology for a new installation. You can approach the installation in one of two ways:</span></span>
    
      - <span data-ttu-id="7ee15-186">Dejar todas las casillas sin activar y proceder con la definición de la topología.</span><span class="sxs-lookup"><span data-stu-id="7ee15-186">Leave the check box clear and proceed with defining the topology.</span></span> <span data-ttu-id="7ee15-187">Una vez que haya publicado, configurado y probado los roles de servidor front-end y back-end, puede volver a ejecutar el generador de topologías para agregar los servidores de roles a la topología.</span><span class="sxs-lookup"><span data-stu-id="7ee15-187">After you have published, configured, and tested the Front End and Back End Server roles, you can run Topology Builder again to add the role servers to the topology.</span></span> <span data-ttu-id="7ee15-188">Esta estrategia le permitirá probar el grupo de servidores front-end y el servidor que ejecuta SQL Server sin complicaciones adicionales de roles adicionales.</span><span class="sxs-lookup"><span data-stu-id="7ee15-188">This strategy will enable you to test the Front End pool and the server running SQL Server without additional complications from additional roles.</span></span> <span data-ttu-id="7ee15-189">Una vez completadas las pruebas iniciales, puede volver a ejecutar el generador de topologías para seleccionar los roles que necesita implementar.</span><span class="sxs-lookup"><span data-stu-id="7ee15-189">After you have completed your initial testing, you can run Topology Builder again to select the roles you need to deploy.</span></span>
    
      - <span data-ttu-id="7ee15-190">Seleccione los roles que necesita instalar y, a continuación, configure le hardware para hospedar los roles seleccionados.</span><span class="sxs-lookup"><span data-stu-id="7ee15-190">Select roles that you need to install, and then set up the hardware to accommodate the selected roles.</span></span>
    
    <span data-ttu-id="7ee15-191">Para el escenario dos, tiene una implementación existente y la infraestructura está preparada para nuevos roles o debe asociar roles existentes con un nuevo servidor front-end:</span><span class="sxs-lookup"><span data-stu-id="7ee15-191">For scenario two, you have an existing deployment and your infrastructure is ready for new roles or you need to associate existing roles with a new Front End Server:</span></span>
    
      - <span data-ttu-id="7ee15-192">En este caso, se seleccionan los roles que se van a implementar o asociar con el nuevo servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="7ee15-192">In this case, you will select the roles that you intend to deploy or associate with the new Front End Server.</span></span> <span data-ttu-id="7ee15-193">En cualquier caso, continuará con la definición de los roles, la configuración de cualquier hardware necesario y procederá con la instalación.</span><span class="sxs-lookup"><span data-stu-id="7ee15-193">In either case, you will proceed with the definition of the roles, set up any needed hardware, and proceed with the installation.</span></span>

7.  <span data-ttu-id="7ee15-194">En la página **Definir el almacén de SQL**, realice una de las operaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="7ee15-194">On the **Define the SQL store** page, do one of the following:</span></span>
    
      - <span data-ttu-id="7ee15-195">Para usar el almacén de SQL Server existente que ya se ha definido en la topología, seleccione **Usar un almacén de SQL definido previamente**.</span><span class="sxs-lookup"><span data-stu-id="7ee15-195">To use an existing SQL Server store that has already been defined in your topology, select an instance from **SQL store**.</span></span>
    
      - <span data-ttu-id="7ee15-196">Para definir una nueva instancia de SQL Server para almacenar la información del grupo de servidores, haga clic en **nuevo** y, a continuación, especifique el **FQDN de SQL Server**en el cuadro de diálogo **definir nuevo almacén de SQL** .</span><span class="sxs-lookup"><span data-stu-id="7ee15-196">To define a new SQL Server instance to store pool information, click **New** and then specify the **SQL Server FQDN**in the **Define New SQL Store** dialog box.</span></span>
    
      - <span data-ttu-id="7ee15-197">Para especificar el nombre de una instancia de SQL Server, seleccione **Instancia con nombre** y, a continuación, especifique el nombre de la instancia.</span><span class="sxs-lookup"><span data-stu-id="7ee15-197">To specify the name of a SQL Server instance, select **Named Instance**, and then specify the name of the instance.</span></span>
    
      - <span data-ttu-id="7ee15-198">Para usar la instancia predeterminada, haga clic en **Instancia predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="7ee15-198">To use the default instance, click **Default instance**.</span></span>
    
      - <span data-ttu-id="7ee15-199">Para utilizar la creación de reflejos de SQL, seleccione **Habilitar creación de reflejos de SQL** y seleccione una instancia existente o cree una nueva instancia.</span><span class="sxs-lookup"><span data-stu-id="7ee15-199">To use SQL Mirroring, select **Enable SQL mirroring** and select an existing instance or create a new instance.</span></span>

8.  <span data-ttu-id="7ee15-200">En la página **Definir el uso compartido de archivos**, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="7ee15-200">On the **Define the file share** page, do one of the following:</span></span>
    
      - <span data-ttu-id="7ee15-201">Para usar un uso compartido de archivos ya definido en la topología, seleccione **Usar un uso compartido de archivos ya definido**.</span><span class="sxs-lookup"><span data-stu-id="7ee15-201">To use a file share that has already been defined in your topology, select **Use a previously defined file share**.</span></span>
    
      - <span data-ttu-id="7ee15-202">Para definir un nuevo recurso compartido de archivos, seleccione **Definir un nuevo recurso compartido de archivos**, en el cuadro **FQDN de servidor de archivos**, escriba el FQDN del servidor de archivos existente donde se ubicará el recurso compartido de archivos y, a continuación, escriba un nombre para el recurso compartido de archivos en el cuadro **Recurso compartido de archivos**.</span><span class="sxs-lookup"><span data-stu-id="7ee15-202">To define a new file share, select **Define a new file share**, in the **File Server FQDN** box, enter the FQDN of the existing file server where the file share is to reside, and then enter a name for the file share in the **File Share** box.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="7ee15-203">El recurso compartido de archivos para Lync Server 2013 no se encuentra en el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="7ee15-203">The file share for Lync Server 2013 cannot be located on the Front End Server.</span></span> <span data-ttu-id="7ee15-204">Tenga en cuenta que, en este ejemplo, el recurso compartido de archivos se ha colocado en el servidor back-end basado en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7ee15-204">Note that in this example, the file share has been located on the SQL Server-based Back End Server.</span></span> <span data-ttu-id="7ee15-205">Esta podría no ser una ubicación óptima para los requisitos de su organización y es posible que un servidor de archivos fuera una opción mejor.</span><span class="sxs-lookup"><span data-stu-id="7ee15-205">This might not be an optimal location for your organization’s requirements, and a file server might be a better choice.</span></span> <span data-ttu-id="7ee15-206">Puede definir el uso compartido de archivos sin que este se haya creado.</span><span class="sxs-lookup"><span data-stu-id="7ee15-206">You can define the file share without the file share having been created.</span></span> <span data-ttu-id="7ee15-207">Tendrá que crear el uso compartido de archivos en la ubicación que defina antes de publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="7ee15-207">You will need to create the file share in the location you define before you publish the topology.</span></span>

    
    </div>

9.  <span data-ttu-id="7ee15-208">En la página **Especificar la dirección URL de servicios web**, siga uno o varios de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="7ee15-208">On the **Specify the Web Services URL** page, do one or both of the following:</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="7ee15-209">La dirección URL base es la identidad de servicios web de la dirección URL, menos https://.</span><span class="sxs-lookup"><span data-stu-id="7ee15-209">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="7ee15-210">Por ejemplo, si la dirección URL completa de los servicios web del grupo es https://pool01.contoso.net, la dirección URL base es pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="7ee15-210">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]
    > <span data-ttu-id="7ee15-211">Si tiene más de un grupo front-end o servidor front-end, el FQDN de servicios web externos debe ser único.</span><span class="sxs-lookup"><span data-stu-id="7ee15-211">If you have more than one Front End pool or Front End Server, the external Web services FQDN must be unique.</span></span> <span data-ttu-id="7ee15-212">Por ejemplo, si define el FQDN de servicios web externos de un servidor front-end como <STRONG>pool01.contoso.com</STRONG>, no puede usar <STRONG>pool01.contoso.com</STRONG> para otro grupo de servidores front-end o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="7ee15-212">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span>

    
    </div>
    
    1.  <span data-ttu-id="7ee15-213">Si está configurando el equilibrio de carga de DNS, active la casilla **invalidar el FQDN del grupo de servicios Web interno** , escriba la dirección URL base interna (que debe ser diferente del FQDN del grupo de\<servidores y podría\>ser, por ejemplo, Internal-la dirección URL base) en la **dirección URL base interna**.</span><span class="sxs-lookup"><span data-stu-id="7ee15-213">If you are configuring DNS load balancing, select the **Override internal Web Services pool FQDN** check box, enter the internal base URL (which must be different from the pool FQDN and could be, for example, internal-\<your base URL\>) in **Internal Base URL**.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="7ee15-214">Si decide reemplazar los servicios Web internos con un FQDN autodefinido, cada FQDN debe ser único en cualquier otro grupo de servidores front-end, director o grupo de directores.</span><span class="sxs-lookup"><span data-stu-id="7ee15-214">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span> <span data-ttu-id="7ee15-215"><STRONG>Use solo caracteres estándar</STRONG> (incluidos A – z, a – z, 0 – 9 y guiones) al definir direcciones URL o nombres de dominio completos.</span><span class="sxs-lookup"><span data-stu-id="7ee15-215"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when defining URLs or fully qualified domain names.</span></span> <span data-ttu-id="7ee15-216">No use caracteres Unicode ni de subrayado.</span><span class="sxs-lookup"><span data-stu-id="7ee15-216">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="7ee15-217">Los caracteres no estándar de una dirección URL o un FQDN no suelen ser compatibles con las CA públicas y DNS externas (es decir, cuando la dirección URL o el FQDN deben asignarse al nombre del sujeto o al nombre alternativo del sujeto del certificado).</span><span class="sxs-lookup"><span data-stu-id="7ee15-217">Nonstandard characters in a URL or FQDN are often not supported by external DNS and public CAs (that is, when the URL or FQDN must be assigned to the subject name or subject alternative name in the certificate).</span></span>

        
        </div>
    
    2.  <span data-ttu-id="7ee15-218">Opcionalmente, escriba la dirección URL base externa en **Dirección URL base externa**.</span><span class="sxs-lookup"><span data-stu-id="7ee15-218">Optionally enter the external base URL in **External Base URL**.</span></span> <span data-ttu-id="7ee15-219">Deberá introducir la dirección URL base externa con el fin de diferenciar la asignación de nombres de dominio interna.</span><span class="sxs-lookup"><span data-stu-id="7ee15-219">You would enter the external base URL to differentiate it from your internal domain naming.</span></span> <span data-ttu-id="7ee15-220">Por ejemplo, el dominio interno es contoso.net, pero el nombre del dominio externo es contoso.com.</span><span class="sxs-lookup"><span data-stu-id="7ee15-220">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="7ee15-221">La dirección URL se define mediante el nombre de dominio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="7ee15-221">You would define the URL using the contoso.com domain name.</span></span> <span data-ttu-id="7ee15-222">También es importante en el caso de un proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="7ee15-222">This is also important in the case of a reverse proxy.</span></span> <span data-ttu-id="7ee15-223">El nombre de dominio de la dirección URL base externa será el mismo que el nombre de dominio del FQDN del servidor proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="7ee15-223">The external base URL domain name would be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="7ee15-224">La mensajería instantánea y la presencia requieren acceso HTTP al grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="7ee15-224">Instant messaging and presence does require HTTP access to the Front End pool.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="7ee15-225">Para usar el equilibrio de carga de DNS, debe crear los registros DNS correspondientes.</span><span class="sxs-lookup"><span data-stu-id="7ee15-225">To use DNS load balancing, you must create the appropriate DNS records.</span></span> <span data-ttu-id="7ee15-226">Para obtener más información, consulte <A href="lync-server-2013-configure-dns-for-load-balancing.md">configure DNS for Load Balancing in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7ee15-226">For details, see <A href="lync-server-2013-configure-dns-for-load-balancing.md">Configure DNS for load balancing in Lync Server 2013</A>.</span></span>

    
    </div>

10. <span data-ttu-id="7ee15-227">Si seleccionó **conferencias** en la **página seleccionar características** , en la página **seleccionar un servidor de Office Web Apps** , seleccione **asociar grupo con un servidor de Office Web Apps** y, a continuación, haga clic en **nuevo** (o seleccione un servidor de Office Web Apps existente en la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="7ee15-227">If you selected **Conferencing** on the **Select Features** page, on the **Select an Office Web Apps Server** page select **Associate pool with an Office Web Apps Server** and then click **New** (or select an existing Office Web Apps Server from the drop-down list).</span></span>

11. <span data-ttu-id="7ee15-228">En el cuadro de diálogo **Definir nuevo Office Web Apps Server**, escriba el nombre de dominio completo (FQDN) del equipo de Office Web Apps Server en el cuadro **FQDN de Office Web Apps Server**; al hacerlo, la dirección URL de descubrimiento de Office Web Apps Server deberá aparecer automáticamente en el cuadro **Dirección URL de descubrimiento de Office Web Apps Server**.</span><span class="sxs-lookup"><span data-stu-id="7ee15-228">In the **Define New Office Web Apps Server** dialog box, type the fully qualified domain name (FQDN) of your Office Web Apps Server computer in the **Office Web Apps Server FQDN** box; when you do this, your Office Web Apps Server discovery URL should automatically be entered into the **Office Web Apps Server discovery URL** box.</span></span>
    
    <span data-ttu-id="7ee15-229">Si Office Web Apps Server está instalado en local y en la misma zona de red que Lync Server 2013, la opción **Office Web Apps Server se implementa en una red externa (es decir, perimetral/Internet)** no debe seleccionarse.</span><span class="sxs-lookup"><span data-stu-id="7ee15-229">If the Office Web Apps Server is installed on-premises and in the same network zone as Lync Server 2013 then the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** should not be selected.</span></span>
    
    <span data-ttu-id="7ee15-230">Si Office Web Apps Server está implementado fuera del firewall interno, seleccione la opción **Office Web Apps Server se implementa en una red externa (esto es, perimetral/Internet)**.</span><span class="sxs-lookup"><span data-stu-id="7ee15-230">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="7ee15-231">Para obtener más información, consulte <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring Integration with Office Web Apps Server y Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7ee15-231">For details, see <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring integration with Office Web Apps Server and Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="7ee15-232">En la página **Definir el almacén de SQL para el archivado**, seleccione una instancia existente o un servidor SQL Server, o bien defina una nueva instancia para almacenar los datos asociados con los datos de archivado.</span><span class="sxs-lookup"><span data-stu-id="7ee15-232">On the **Define the Archiving SQL store** page, select an existing instance or SQL Server, or define a new instance to store the data associated with archiving data.</span></span>

13. <span data-ttu-id="7ee15-233">En la página **Definir el almacén SQL para la supervisión**, seleccione una instancia existente o un servidor SQL Server, o bien defina una nueva instancia para almacenar los datos asociados con los datos de supervisión.</span><span class="sxs-lookup"><span data-stu-id="7ee15-233">On the **Define the Monitoring SQL store** page, select an existing instance or SQL Server, or define a new instance to store the data associated with monitoring data.</span></span>

14. <span data-ttu-id="7ee15-234">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7ee15-234">Click **Next**.</span></span> <span data-ttu-id="7ee15-235">Si ha definido otros servidores de roles en la página **asociar roles de servidor con este grupo de servidores front-end** , se abrirán las páginas del Asistente para configuración de roles independiente para que pueda configurar los roles de servidor.</span><span class="sxs-lookup"><span data-stu-id="7ee15-235">If you defined other role servers on the **Associate server roles with this Front End pool** page, separate role configuration wizard pages will open to let you configure the server roles.</span></span> <span data-ttu-id="7ee15-236">Para obtener más información, consulte lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7ee15-236">For details, see the following:</span></span>
    
    [<span data-ttu-id="7ee15-237">Implementar el acceso de usuarios externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ee15-237">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)

15. <span data-ttu-id="7ee15-238">Si no ha seleccionado roles de servidor adicionales para configurarlos e implementarlos, o una vez finalizada la configuración de los roles de servidor adicionales, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="7ee15-238">If you did not select additional server roles to configure and deploy, or when you have finished the configuration of the additional role servers, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

