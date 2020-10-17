---
title: 'Lync Server 2013: crear o modificar una directiva de conferencia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a conferencing policy
ms:assetid: e2974030-2c0a-4634-91e8-93f4e2d674d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721910(v=OCS.15)
ms:contentKeyID: 49733844
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dc01c8bed503f06806c873431ef201e03c31811
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516897"
---
# <a name="create-or-modify-a-conferencing-policy-in-lync-server-2013"></a><span data-ttu-id="555ab-102">Crear o modificar una directiva de conferencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="555ab-102">Create or modify a conferencing policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="555ab-103">_**Última modificación del tema:** 2013-02-07_</span><span class="sxs-lookup"><span data-stu-id="555ab-103">_**Topic Last Modified:** 2013-02-07_</span></span>

<span data-ttu-id="555ab-104">Siga estos pasos para crear una directiva de conferencia de nivel de usuario o de nivel de sitio.</span><span class="sxs-lookup"><span data-stu-id="555ab-104">Follow these steps to create a user-level or a site-level conferencing policy.</span></span> <span data-ttu-id="555ab-105">Para obtener más información sobre cómo asignar una directiva de nivel de usuario a un usuario, consulte [asignar una directiva de conferencia por usuario en Lync Server 2013](lync-server-2013-assign-a-per-user-conferencing-policy.md).</span><span class="sxs-lookup"><span data-stu-id="555ab-105">For details about how to assign a user-level policy to a user, see [Assign a per-user conferencing policy in Lync Server 2013](lync-server-2013-assign-a-per-user-conferencing-policy.md).</span></span> <span data-ttu-id="555ab-106">Para obtener una lista de todas las opciones de configuración de directivas de conferencia disponibles, consulte [referencia de configuración de directivas de conferencia para Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span><span class="sxs-lookup"><span data-stu-id="555ab-106">For a list of all available conferencing policy settings, see [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<div>

## <a name="to-create-a-new-user-or-site-policy"></a><span data-ttu-id="555ab-107">Para crear una directiva de sitio o de usuario nueva</span><span class="sxs-lookup"><span data-stu-id="555ab-107">To create a new user or site policy</span></span>

1.  <span data-ttu-id="555ab-108">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="555ab-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="555ab-109">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="555ab-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="555ab-110">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="555ab-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="555ab-111">En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Directiva de Conferencia**.</span><span class="sxs-lookup"><span data-stu-id="555ab-111">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="555ab-112">Haga clic en **Nuevo** y luego siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="555ab-112">Click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="555ab-p103">Para crear una directiva de nivel de usuario, haga clic en **Directiva de usuario**. En **Directiva de conferencia nueva**, en **Nombre**, escriba un nombre descriptivo para la directiva.</span><span class="sxs-lookup"><span data-stu-id="555ab-p103">To create a user-level policy, click **User policy**. In **New Conferencing Policy**, in **Name**, type a descriptive name for the policy.</span></span>
    
      - <span data-ttu-id="555ab-p104">Para crear una directiva de nivel de sitio, haga clic en **Directiva de sitio**. En el campo de búsqueda **Seleccionar un sitio**, escriba todo o parte del nombre del sitio para el que desea crear una directiva. En la lista de sitios, haga clic en el sitio que desee y después en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="555ab-p104">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the list of sites, click the site that you want, and then click **OK**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="555ab-118">El nombre del sitio pasa a ser el nombre de la directiva de conferencia y no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="555ab-118">The site name becomes the conferencing policy name, and it cannot be changed.</span></span>

        
        </div>

5.  <span data-ttu-id="555ab-119">En **Descripción**, escriba una descripción para la directiva.</span><span class="sxs-lookup"><span data-stu-id="555ab-119">In **Description**, type a description for the policy.</span></span>

6.  <span data-ttu-id="555ab-p105">En **Directiva de organizadores**, en **Tamaño máximo de la reunión**, escriba el número máximo de usuarios que desea que participen en una reunión. De manera predeterminada, el tamaño máximo de la reunión se establece en 250.</span><span class="sxs-lookup"><span data-stu-id="555ab-p105">Under **Organizer policy**, in **Maximum meeting size**, type the maximum number of users that you want to allow at a meeting. By default, the maximum meeting size is 250.</span></span>

7.  <span data-ttu-id="555ab-122">Para impedir que los usuarios inviten a usuarios anónimos a las reuniones, desactive la casilla **Permitir a los participantes invitar a usuarios anónimos**.</span><span class="sxs-lookup"><span data-stu-id="555ab-122">To prevent users from inviting anonymous users to meetings, clear the **Allow participants to invite anonymous users** check box.</span></span> <span data-ttu-id="555ab-123">Los usuarios anónimos son usuarios que no tienen credenciales en los servicios de dominio de Active Directory de la organización y que, por lo tanto, no están autenticados.</span><span class="sxs-lookup"><span data-stu-id="555ab-123">Anonymous users are users who do not have credentials in your organization’s Active Directory Domain Services and who, therefore, are not authenticated.</span></span> <span data-ttu-id="555ab-124">Normalmente, los participantes pueden invitar a usuarios anónimos a las reuniones.</span><span class="sxs-lookup"><span data-stu-id="555ab-124">By default, users can invite anonymous users to meetings.</span></span>

8.  <span data-ttu-id="555ab-125">En **Grabación**, lleve a cabo uno de los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="555ab-125">In **Recording**, do one of the following:</span></span>
    
      - <span data-ttu-id="555ab-p107">Para impedir que los participantes graben reuniones, haga clic en **Ninguna**. Esta es la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="555ab-p107">To prevent participants from recording meetings, click **None**. This is the default setting.</span></span>
    
      - <span data-ttu-id="555ab-128">Para permitir que los participantes graben reuniones, haga clic en **Habilitar grabación**.</span><span class="sxs-lookup"><span data-stu-id="555ab-128">To allow participants to record meetings, click **Enable recording**.</span></span>

9.  <span data-ttu-id="555ab-p108">Para permitir que los participantes externos graben reuniones, active la casilla **Permitir a los participantes federados y anónimos grabar**. Generalmente, los participantes externos no pueden grabar las reuniones.</span><span class="sxs-lookup"><span data-stu-id="555ab-p108">To allow external participants to record meetings, select the **Allow federated and anonymous participants to record** check box. The default is to prevent external participants from recording meetings.</span></span>

10. <span data-ttu-id="555ab-131">En **Audio/vídeo**, lleve a cabo uno de los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="555ab-131">In **Audio/video**, do one of the following:</span></span>
    
      - <span data-ttu-id="555ab-132">Para impedir el uso de audio y vídeo, haga clic en **Ninguno**.</span><span class="sxs-lookup"><span data-stu-id="555ab-132">To prevent the use of audio and video, click **None**.</span></span>
    
      - <span data-ttu-id="555ab-133">Para permitir el uso de audio pero no de vídeo, haga clic en **Habilitar audio IP**.</span><span class="sxs-lookup"><span data-stu-id="555ab-133">To allow the use of audio but not video, click **Enable IP audio**.</span></span>
    
      - <span data-ttu-id="555ab-p109">Para permitir el uso de audio y de vídeo, haga clic en **Habilitar audio y vídeo IP**. Esta es la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="555ab-p109">To allow the use of audio and video, click **Enable IP audio/video**. This is the default setting.</span></span>

11. <span data-ttu-id="555ab-136">Si opta por permitir el uso de audio en **Audio/vídeo**, realice uno de los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="555ab-136">If you chose to allow the use of audio in **Audio/video**, do the following:</span></span>
    
      - <span data-ttu-id="555ab-p110">Para impedir que los usuarios participen en la reunión mediante acceso telefónico, desactive la casilla **Habilitar conferencia de acceso telefónico local RTC**. Normalmente, los usuarios pueden acceder telefónicamente a las reuniones a través de la red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="555ab-p110">To prevent users from joining the meeting by dialing in, clear the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
      - <span data-ttu-id="555ab-p111">Si permite que los usuarios accedan telefónicamente a las reuniones y desea permitir que usuarios no autenticados (anónimos) se unan a una reunión con llamadas salientes, active la casilla **Permitir acceso telefónico a los participantes anónimos**. Con las llamadas salientes, el servidor de conferencia llama al usuario y este contesta el teléfono para participar en la reunión. Normalmente, los usuarios anónimos no pueden participar en una reunión con llamadas salientes.</span><span class="sxs-lookup"><span data-stu-id="555ab-p111">If you allow users to dial in to meetings and you want to allow unauthenticated (anonymous) users to join a meeting by using dial out phoning, select the **Allow anonymous participants to dial out** check box. With dial-out phoning, the conference server calls the user, and the user answers the phone to join the meeting. By default, anonymous users cannot join a meeting by using dial-out phoning.</span></span>

12. <span data-ttu-id="555ab-142">Si opta por permitir el uso de vídeo en **Audio/vídeo**, active **Permitir varias secuencias de vídeo**.</span><span class="sxs-lookup"><span data-stu-id="555ab-142">If you chose to allow the use of video in **Audio/video**, check **Allow multiple video streams** .</span></span>

13. <span data-ttu-id="555ab-143">En **Colaboración de datos**, lleve a cabo uno de los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="555ab-143">In **Data collaboration**, do one of the following:</span></span>
    
      - <span data-ttu-id="555ab-144">Para impedir la colaboración de datos, haga clic en **Ninguna**.</span><span class="sxs-lookup"><span data-stu-id="555ab-144">To prevent data collaboration, click **None**.</span></span>
    
      - <span data-ttu-id="555ab-p112">Para permitir la colaboración de datos, haga clic en **Habilitar colaboración de datos**. Esta es la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="555ab-p112">To allow data collaboration, click **Enable data collaboration**. This is the default setting.</span></span>

14. <span data-ttu-id="555ab-147">Si opta por permitir la colaboración de datos en **Colaboración de datos**, realice uno de los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="555ab-147">If you chose to allow data collaboration in **Data collaboration**, do the following:</span></span>
    
      - <span data-ttu-id="555ab-p113">Para impedir descargas externas, desactive la casilla **Permitir a los participantes federados y anónimos descargar contenido**. Normalmente, los usuarios externos pueden descargar contenido.</span><span class="sxs-lookup"><span data-stu-id="555ab-p113">To prevent external downloads, clear the **Allow federated and anonymous participants to download content** check box. By default, external users can download content.</span></span>
    
      - <span data-ttu-id="555ab-p114">Para impedir la transferencia de archivos, desactive la casilla **Permitir a los participantes transferir archivos**. Normalmente, los usuarios pueden transferir archivos.</span><span class="sxs-lookup"><span data-stu-id="555ab-p114">To prevent file transfers, clear the **Allow participants to transfer files** check box. By default, users can transfer files.</span></span>
    
      - <span data-ttu-id="555ab-p115">Para impedir el uso de anotaciones, desactive la casilla **Habilitar anotaciones**. Para usar anotaciones en las presentaciones de PowerPoint compartidas, desactive la casilla **Habilitar anotaciones de PowerPoint**. Normalmente, las anotaciones se permiten.</span><span class="sxs-lookup"><span data-stu-id="555ab-p115">To prevent the use of annotations, clear the **Enable annotations** check box. To the use of annotations in shard PowerPoint presentations, clear the **Enable PowerPoint annotations**. By default, annotations are allowed.</span></span>
    
      - <span data-ttu-id="555ab-p116">Para impedir el uso de sondeos, desactive la casilla **Habilitar sondeos**. Normalmente, se permiten los sondeos.</span><span class="sxs-lookup"><span data-stu-id="555ab-p116">To prevent the use of polls, clear the **Enable polls** check box. By default, polls are allowed.</span></span>

15. <span data-ttu-id="555ab-157">En **Uso compartido de aplicaciones**, lleve a cabo uno de los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="555ab-157">In **Application sharing**, do one of the following:</span></span>
    
      - <span data-ttu-id="555ab-158">Para impedir el uso compartido de aplicaciones, haga clic en **Deshabilitar el uso compartido de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="555ab-158">To prevent the use of application sharing, click **Disable application sharing**.</span></span>
    
      - <span data-ttu-id="555ab-p117">Para permitir el uso compartido de aplicaciones, haga clic en **Habilitar el uso compartido de aplicaciones**. Esta es la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="555ab-p117">To allow the use of application sharing, click **Enable application sharing**. This is the default setting.</span></span>

16. <span data-ttu-id="555ab-161">Si opta por permitir el uso compartido de aplicaciones en **Compartit aplicaciones**, realice uno de los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="555ab-161">If you chose to allow application sharing in **Application sharing**, do the following:</span></span>
    
      - <span data-ttu-id="555ab-p118">Para impedir que los participantes en una reunión controlen el uso compartido de aplicaciones, desactive la casilla **Permitir a los participantes asumir el control**. Normalmente, los participantes pueden controlar el uso compartido de las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="555ab-p118">To prevent meeting participants from taking control of application sharing, clear the **Allow participants to take control** check box. By default, participants can take control of application sharing.</span></span>
    
      - <span data-ttu-id="555ab-p119">Si opta por permitir que los participantes de las reuniones controlen el uso compartido de aplicaciones, seleccione la casilla **Permitir a los participantes federados y anónimos asumir el control** para permitir que los usuarios externos controlen el uso compartido de aplicaciones. Normalmente, los usuarios externos no pueden controlar el uso compartido de las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="555ab-p119">If you chose to allow meeting participants to take control of application sharing, select the **Allow federated and anonymous participants to take control** check box to allow external users to take control of application sharing. By default, external users cannot take control of application sharing.</span></span>

17. <span data-ttu-id="555ab-166">En **Directiva de participantes**, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="555ab-166">Under **Participant policy**, do one of the following:</span></span>
    
      - <span data-ttu-id="555ab-167">Para impedir el uso compartido de las aplicaciones y del escritorio, haga clic en **Deshabilitar el uso compartido de aplicaciones y escritorio**.</span><span class="sxs-lookup"><span data-stu-id="555ab-167">To prevent both application sharing and desktop sharing, click **Disable application and desktop sharing**.</span></span>
    
      - <span data-ttu-id="555ab-168">Para permitir el uso compartido de las aplicaciones pero no el uso compartido del escritorio, haga clic en **Habilitar el uso compartido de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="555ab-168">To allow application sharing but not desktop sharing, click **Enable application sharing**.</span></span>
    
      - <span data-ttu-id="555ab-p120">Para permitir el uso compartido de las aplicaciones y del escritorio, haga clic en **Habilitar el uso compartido de aplicaciones y escritorio**. Esta es la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="555ab-p120">To allow both application sharing and desktop sharing, click **Enable application and desktop sharing**. This is the default setting.</span></span>

18. <span data-ttu-id="555ab-p121">Para impedir la transferencia de archivos punto a punto, desactive la casilla **Habilitar la transferencia de archivos punto a punto**. Normalmente, se permite la transferencia de archivos punto a punto.</span><span class="sxs-lookup"><span data-stu-id="555ab-p121">To prevent peer-to-peer file transfers, clear the **Enable peer-to-peer file transfer** check box. By default, peer-to-peer file transfers are allowed.</span></span>

19. <span data-ttu-id="555ab-p122">Para permitir la grabación punto a punto, active la casilla **Habilitar grabación punto a punto**. Normalmente, no se permite la grabación punto a punto.</span><span class="sxs-lookup"><span data-stu-id="555ab-p122">To allow peer-to-peer recording, select the **Enable peer-to-peer recording** check box. By default, peer-to-peer recording is not allowed.</span></span>

20. <span data-ttu-id="555ab-p123">Para permitir que los participantes se unan con varias secuencias de vídeo, active la casilla **Permitir que los participantes se unan con varias secuencias de vídeo**. Normalmente, se permiten varias secuencias de vídeo.</span><span class="sxs-lookup"><span data-stu-id="555ab-p123">To allow participants to join with multiple video streams, select the **Enable participants to join with multiple video streams** check box. By default, multiple video streams are allowed.</span></span>

21. <span data-ttu-id="555ab-177">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="555ab-177">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-user-or-site-policy"></a><span data-ttu-id="555ab-178">Para modificar una directiva de usuario o de sitio existente</span><span class="sxs-lookup"><span data-stu-id="555ab-178">To modify an existing user or site policy</span></span>

1.  <span data-ttu-id="555ab-179">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="555ab-179">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="555ab-180">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="555ab-180">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="555ab-181">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="555ab-181">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="555ab-182">En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Directiva de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="555ab-182">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="555ab-183">En la lista de directivas de conferencia, haga clic en la directiva que desee cambiar y luego haga clic en **Editar** y en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="555ab-183">In the list of conferencing policies, click the policy that you want to change, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="555ab-184">En **Editar directiva de conferencia**, modifique cualquier configuración de directivas, salvo el nombre de la directiva, que no se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="555ab-184">In **Edit Conferencing Policy**, modify any of the policy settings, except for the policy name, which cannot be modified.</span></span>

6.  <span data-ttu-id="555ab-185">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="555ab-185">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

