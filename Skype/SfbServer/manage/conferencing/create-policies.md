---
title: Crear directivas de conferencia en Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8c685326-8356-4075-bf95-32324b16ef81
description: 'Resumen: Obtenga información sobre cómo crear directivas de conferencia en Skype para Business Server.'
ms.openlocfilehash: 718eacad71ca0264785b9bb42d113c1d54679b50
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222838"
---
# <a name="create-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="0e9c6-103">Crear directivas de conferencia en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="0e9c6-103">Create conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="0e9c6-104">**Resumen:** Obtenga información sobre cómo crear directivas de conferencia en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-104">**Summary:** Learn how to create conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="0e9c6-105">Puede crear directivas de conferencia mediante el uso de Skype para el Panel de Control de servidor empresarial o mediante el uso de Skype para Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-105">You can create conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="create-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="0e9c6-106">Crear directivas de conferencia mediante el uso de Skype para el Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="0e9c6-106">Create conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="0e9c6-107">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="0e9c6-108">Abra Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="0e9c6-109">En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Directiva de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="0e9c6-110">Haga clic en **Nuevo** y, luego, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="0e9c6-110">Click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="0e9c6-p101">Para crear una directiva de nivel de usuario, haga clic en **Directiva de usuario**. En **Directiva de conferencia nueva**, en **Nombre**, escriba un nombre descriptivo para la directiva.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-p101">To create a user-level policy, click **User policy**. In **New Conferencing Policy**, in **Name**, type a descriptive name for the policy.</span></span>
    
   - <span data-ttu-id="0e9c6-p102">Para crear una directiva de nivel de sitio, haga clic en **Directiva de sitio**. En el campo de búsqueda **Seleccionar un sitio**, escriba todo o parte del nombre del sitio para el que desea crear una directiva. En la lista de sitios, haga clic en el sitio que desee y después en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-p102">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the list of sites, click the site that you want, and then click **OK**.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="0e9c6-116">El nombre del sitio pasa a ser el nombre de la directiva de conferencia y no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-116">The site name becomes the conferencing policy name; it cannot be changed.</span></span> 
  
5. <span data-ttu-id="0e9c6-117">En **Descripción**, escriba una descripción para la directiva.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-117">In **Description**, type a description for the policy.</span></span>
    
6. <span data-ttu-id="0e9c6-p103">En **Directiva de organizadores**, en **Tamaño máximo de la reunión**, escriba el número máximo de usuarios que desea que participen en una reunión. De manera predeterminada, el tamaño máximo de la reunión se establece en 250.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-p103">Under **Organizer policy**, in **Maximum meeting size**, type the maximum number of users that you want to allow at a meeting. By default, the maximum meeting size is 250.</span></span>
    
7. <span data-ttu-id="0e9c6-120">Para impedir que los usuarios inviten a usuarios anónimos a las reuniones, desactive la casilla **Permitir a los participantes invitar a usuarios anónimos**.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-120">To prevent users from inviting anonymous users to meetings, clear the **Allow participants to invite anonymous users** check box.</span></span> <span data-ttu-id="0e9c6-121">Los usuarios anónimos son usuarios que no tienen credenciales en los servicios de dominio de Active Directory de su organización y que, por lo tanto, no se autentican.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-121">Anonymous users are users who do not have credentials in your organization's Active Directory Domain Services and who, therefore, are not authenticated.</span></span> <span data-ttu-id="0e9c6-122">De manera predeterminada, los participantes pueden invitar a usuarios anónimos a las reuniones.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-122">By default, users can invite anonymous users to meetings.</span></span>
    
8. <span data-ttu-id="0e9c6-123">En **Grabación**, lleve a cabo uno de los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="0e9c6-123">In **Recording**, do one of the following:</span></span>
    
   - <span data-ttu-id="0e9c6-p105">Para impedir que los participantes graben reuniones, haga clic en **Ninguna**. Esta es la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-p105">To prevent participants from recording meetings, click **None**. This is the default setting.</span></span>
    
   - <span data-ttu-id="0e9c6-126">Para permitir que los participantes graben reuniones, haga clic en **Habilitar grabación**.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-126">To allow participants to record meetings, click **Enable recording**.</span></span>
    
9. <span data-ttu-id="0e9c6-p106">Para permitir que los participantes externos graben reuniones, active la casilla **Permitir a los participantes federados y anónimos grabar**. Generalmente, los participantes externos no pueden grabar las reuniones.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-p106">To allow external participants to record meetings, select the **Allow federated and anonymous participants to record** check box. The default is to prevent external participants from recording meetings.</span></span>
    
10. <span data-ttu-id="0e9c6-129">En **Audio/vídeo**, lleve a cabo uno de los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="0e9c6-129">In **Audio/video**, do one of the following:</span></span>
    
    - <span data-ttu-id="0e9c6-130">Para impedir el uso de audio y vídeo, haga clic en **Ninguno**.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-130">To prevent the use of audio and video, click **None**.</span></span>
    
    - <span data-ttu-id="0e9c6-131">Para permitir el uso de audio pero no de vídeo, haga clic en **Habilitar audio IP**.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-131">To allow the use of audio but not video, click **Enable IP audio**.</span></span>
    
    - <span data-ttu-id="0e9c6-p107">Para permitir el uso de audio y de vídeo, haga clic en **Habilitar audio y vídeo IP**. Esta es la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-p107">To allow the use of audio and video, click **Enable IP audio/video**. This is the default setting.</span></span>
    
11. <span data-ttu-id="0e9c6-134">Si opta por permitir el uso de audio en **Audio/vídeo**, realice uno de los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="0e9c6-134">If you chose to allow the use of audio in **Audio/video**, do the following:</span></span>
    
    - <span data-ttu-id="0e9c6-p108">Para impedir que los usuarios participen en la reunión mediante acceso telefónico, desactive la casilla **Habilitar conferencia de acceso telefónico local RTC**. De manera predeterminada, los usuarios pueden acceder telefónicamente a las reuniones a través de la red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="0e9c6-p108">To prevent users from joining the meeting by dialing in, clear the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
    - <span data-ttu-id="0e9c6-p109">Si permite que los usuarios accedan telefónicamente a las reuniones y desea permitir que usuarios no autenticados (anónimos) se unan a una reunión por aceptación de llamada, active la casilla **Permitir acceso telefónico a los participantes anónimos**. Con la aceptación de llamadas, el servidor de conferencia llama al usuario y este contesta el teléfono para participar en la reunión. De manera predeterminada, los usuarios anónimos no pueden participar en una reunión por aceptación de llamada.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-p109">If you allow users to dial in to meetings and you want to allow unauthenticated (anonymous) users to join a meeting by using dial out phoning, select the **Allow anonymous participants to dial out** check box. With dial-out phoning, the conference server calls the user, and the user answers the phone to join the meeting. By default, anonymous users cannot join a meeting by using dial-out phoning.</span></span>
    
12. <span data-ttu-id="0e9c6-140">Si opta por permitir el uso de vídeo en **Audio/vídeo**, active **Permitir varias secuencias de vídeo**.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-140">If you chose to allow the use of video in **Audio/video**, check **Allow multiple video streams**.</span></span>
    
13. <span data-ttu-id="0e9c6-141">En **Colaboración de datos**, lleve a cabo uno de los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="0e9c6-141">In **Data collaboration**, do one of the following:</span></span>
    
    - <span data-ttu-id="0e9c6-142">Para impedir la colaboración de datos, haga clic en **Ninguna**.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-142">To prevent data collaboration, click **None**.</span></span>
    
    - <span data-ttu-id="0e9c6-p110">Para permitir la colaboración de datos, haga clic en **Habilitar colaboración de datos**. Esta es la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-p110">To allow data collaboration, click **Enable data collaboration**. This is the default setting.</span></span>
    
14. <span data-ttu-id="0e9c6-145">Si opta por permitir la colaboración de datos en **Colaboración de datos**, realice uno de los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="0e9c6-145">If you chose to allow data collaboration in **Data collaboration**, do the following:</span></span>
    
    - <span data-ttu-id="0e9c6-p111">Para impedir descargas externas, desactive la casilla **Permitir a los participantes federados y anónimos descargar contenido**. De manera predeterminada, los usuarios externos pueden descargar contenido.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-p111">To prevent external downloads, clear the **Allow federated and anonymous participants to download content** check box. By default, external users can download content.</span></span>
    
    - <span data-ttu-id="0e9c6-p112">Para impedir la transferencia de archivos, desactive la casilla **Permitir a los participantes transferir archivos**. De manera predeterminada, los usuarios pueden transferir archivos.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-p112">To prevent file transfers, clear the **Allow participants to transfer files** check box. By default, users can transfer files.</span></span>
    
    - <span data-ttu-id="0e9c6-p113">Para impedir el uso de anotaciones, desactive la casilla **Habilitar anotaciones**. Para usar anotaciones en las presentaciones de PowerPoint compartidas, desactive la casilla **Habilitar anotaciones de PowerPoint**. Normalmente, las anotaciones se permiten.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-p113">To prevent the use of annotations, clear the **Enable annotations** check box. To the use of annotations in shared PowerPoint presentations, clear the **Enable PowerPoint annotations**. By default, annotations are allowed.</span></span>
    
    - <span data-ttu-id="0e9c6-p114">Para impedir el uso de sondeos, desactive la casilla **Habilitar sondeos**. De manera predeterminada, se permiten los sondeos.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-p114">To prevent the use of polls, clear the **Enable polls** check box. By default, polls are allowed.</span></span>
    
15. <span data-ttu-id="0e9c6-155">En **Uso compartido de aplicaciones**, lleve a cabo uno de los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="0e9c6-155">In **Application sharing**, do one of the following:</span></span>
    
    - <span data-ttu-id="0e9c6-156">Para impedir el uso compartido de aplicaciones, haga clic en **Deshabilitar el uso compartido de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-156">To prevent the use of application sharing, click **Disable application sharing**.</span></span>
    
    - <span data-ttu-id="0e9c6-p115">Para permitir el uso compartido de aplicaciones, haga clic en **Habilitar el uso compartido de aplicaciones**. Esta es la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-p115">To allow the use of application sharing, click **Enable application sharing**. This is the default setting.</span></span>
    
16. <span data-ttu-id="0e9c6-159">Si opta por permitir el uso compartido de aplicaciones en **Uso compartido de aplicaciones**, realice uno de los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="0e9c6-159">If you chose to allow application sharing in **Application sharing**, do the following:</span></span>
    
    - <span data-ttu-id="0e9c6-p116">Para impedir que los participantes en una reunión controlen el uso compartido de aplicaciones, desactive la casilla **Permitir a los participantes asumir el control**. De manera predeterminada, los participantes pueden controlar el uso compartido de las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-p116">To prevent meeting participants from taking control of application sharing, clear the **Allow participants to take control** check box. By default, participants can take control of application sharing.</span></span>
    
    - <span data-ttu-id="0e9c6-p117">Si opta por permitir que los participantes de las reuniones controlen el uso compartido de aplicaciones, seleccione la casilla **Permitir a los participantes federados y anónimos asumir el control** para permitir que los usuarios externos controlen el uso compartido de aplicaciones. De manera predeterminada, los usuarios externos no pueden controlar el uso compartido de las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-p117">If you chose to allow meeting participants to take control of application sharing, select the **Allow federated and anonymous participants to take control** check box to allow external users to take control of application sharing. By default, external users cannot take control of application sharing.</span></span>
    
17. <span data-ttu-id="0e9c6-164">En **Directiva de participantes**, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="0e9c6-164">Under **Participant policy**, do one of the following:</span></span>
    
    - <span data-ttu-id="0e9c6-165">Para impedir el uso compartido de las aplicaciones y del escritorio, haga clic en **Deshabilitar el uso compartido de aplicaciones y escritorio**.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-165">To prevent both application sharing and desktop sharing, click **Disable application and desktop sharing**.</span></span>
    
    - <span data-ttu-id="0e9c6-166">Para permitir el uso compartido de las aplicaciones pero no el uso compartido del escritorio, haga clic en **Habilitar el uso compartido de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-166">To allow application sharing but not desktop sharing, click **Enable application sharing**.</span></span>
    
    - <span data-ttu-id="0e9c6-p118">Para permitir el uso compartido de las aplicaciones y del escritorio, haga clic en **Habilitar el uso compartido de aplicaciones y escritorio**. Esta es la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-p118">To allow both application sharing and desktop sharing, click **Enable application and desktop sharing**. This is the default setting.</span></span>
    
18. <span data-ttu-id="0e9c6-p119">Para impedir la transferencia de archivos punto a punto, desactive la casilla **Habilitar la transferencia de archivos punto a punto**. De manera predeterminada, se permite la transferencia de archivos punto a punto.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-p119">To prevent peer-to-peer file transfers, clear the **Enable peer-to-peer file transfer** check box. By default, peer-to-peer file transfers are allowed.</span></span>
    
19. <span data-ttu-id="0e9c6-p120">Para permitir la grabación punto a punto, active la casilla **Habilitar grabación punto a punto**. De manera predeterminada, no se permite la grabación punto a punto.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-p120">To allow peer-to-peer recording, select the **Enable peer-to-peer recording** check box. By default, peer-to-peer recording is not allowed.</span></span>
    
20. <span data-ttu-id="0e9c6-p121">Para permitir que los participantes se unan con varias secuencias de vídeo, active la casilla **Permitir que los participantes se unan con varias secuencias de vídeo**. De manera predeterminada, se permiten varias secuencias de vídeo.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-p121">To allow participants to join with multiple video streams, select the **Enable participants to join with multiple video streams** check box. By default, multiple video streams are allowed.</span></span>
    
21. <span data-ttu-id="0e9c6-175">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-175">Click **Commit**.</span></span>
    
## <a name="create-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="0e9c6-176">Crear directivas de conferencia mediante el uso de Skype para Shell de administración de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="0e9c6-176">Create conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="0e9c6-177">Para crear directivas de conferencia, use el cmdlet **New-CsConferencingPolicy**.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-177">To create conferencing policies, use the **New-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="0e9c6-178">En el ejemplo siguiente se crea una nueva directiva de conferencias con Identity SalesConferencingPolicy.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-178">The following example creates a new conferencing policy with the Identity SalesConferencingPolicy.</span></span> <span data-ttu-id="0e9c6-179">Esta directiva usará todos los valores predeterminados de una directiva de conferencia, excepto uno: MaxMeetingSize.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-179">This policy will use all the default values for a conferencing policy except one: MaxMeetingSize.</span></span> <span data-ttu-id="0e9c6-180">En este ejemplo, el tamaño máximo para una reunión se establecerá en 50, en lugar del valor predeterminado 250:</span><span class="sxs-lookup"><span data-stu-id="0e9c6-180">In this example, the maximum size for a meeting will be set to 50 instead of the default value of 250:</span></span>
  
```
New-CsConferencingPolicy -Identity SalesConferencingPolicy -MaxMeetingSize 50
```

<span data-ttu-id="0e9c6-181">Para obtener más información, incluida una descripción de la sintaxis completa y una lista de parámetros, vea [New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="0e9c6-181">For more information, including a complete syntax description and list of parameters, see [New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps).</span></span>
  

