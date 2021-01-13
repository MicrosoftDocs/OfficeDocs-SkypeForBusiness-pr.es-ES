---
title: Crear directivas de conferencia en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8c685326-8356-4075-bf95-32324b16ef81
description: 'Resumen: obtenga información sobre cómo crear directivas de conferencia en Skype Empresarial Server.'
ms.openlocfilehash: 8e707e6da1a56fa1818d436714327936369b06fe
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828240"
---
# <a name="create-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="18673-103">Crear directivas de conferencia en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="18673-103">Create conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="18673-104">**Resumen:** Obtenga información sobre cómo crear directivas de conferencia en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="18673-104">**Summary:** Learn how to create conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="18673-105">Puede crear directivas de conferencia con el Panel de control de Skype Empresarial Server o con el Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="18673-105">You can create conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="create-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="18673-106">Crear directivas de conferencia con el Panel de control de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="18673-106">Create conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="18673-107">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="18673-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="18673-108">Abra el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="18673-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="18673-109">En la barra de navegación izquierda, haga clic **en Conferencia** y, a continuación, haga clic en Directiva **de conferencia.**</span><span class="sxs-lookup"><span data-stu-id="18673-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="18673-110">Haga clic en **Nuevo** y luego siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="18673-110">Click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="18673-p101">Para crear una directiva de nivel de usuario, haga clic en **Directiva de usuario**. En **Directiva de conferencia nueva**, en **Nombre**, escriba un nombre descriptivo para la directiva.</span><span class="sxs-lookup"><span data-stu-id="18673-p101">To create a user-level policy, click **User policy**. In **New Conferencing Policy**, in **Name**, type a descriptive name for the policy.</span></span>
    
   - <span data-ttu-id="18673-p102">Para crear una directiva de nivel de sitio, haga clic en **Directiva de sitio**. En el campo de búsqueda **Seleccionar un sitio**, escriba todo o parte del nombre del sitio para el que desea crear una directiva. En la lista de sitios, haga clic en el sitio que desee y después en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="18673-p102">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the list of sites, click the site that you want, and then click **OK**.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="18673-116">El nombre del sitio se convierte en el nombre de la directiva de conferencia; no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="18673-116">The site name becomes the conferencing policy name; it cannot be changed.</span></span> 
  
5. <span data-ttu-id="18673-117">En **Descripción**, escriba una descripción para la directiva.</span><span class="sxs-lookup"><span data-stu-id="18673-117">In **Description**, type a description for the policy.</span></span>
    
6. <span data-ttu-id="18673-p103">En **Directiva de organizadores**, en **Tamaño máximo de la reunión**, escriba el número máximo de usuarios que desea que participen en una reunión. De manera predeterminada, el tamaño máximo de la reunión se establece en 250.</span><span class="sxs-lookup"><span data-stu-id="18673-p103">Under **Organizer policy**, in **Maximum meeting size**, type the maximum number of users that you want to allow at a meeting. By default, the maximum meeting size is 250.</span></span>
    
7. <span data-ttu-id="18673-120">Para impedir que los usuarios inviten a usuarios anónimos a las reuniones, desactive la casilla **Permitir a los participantes invitar a usuarios anónimos**.</span><span class="sxs-lookup"><span data-stu-id="18673-120">To prevent users from inviting anonymous users to meetings, clear the **Allow participants to invite anonymous users** check box.</span></span> <span data-ttu-id="18673-121">Los usuarios anónimos son usuarios que no tienen credenciales en los Servicios de dominio de Active Directory de su organización y que, por lo tanto, no están autenticados.</span><span class="sxs-lookup"><span data-stu-id="18673-121">Anonymous users are users who do not have credentials in your organization's Active Directory Domain Services and who, therefore, are not authenticated.</span></span> <span data-ttu-id="18673-122">Normalmente, los participantes pueden invitar a usuarios anónimos a las reuniones.</span><span class="sxs-lookup"><span data-stu-id="18673-122">By default, users can invite anonymous users to meetings.</span></span>
    
8. <span data-ttu-id="18673-123">En **Grabación**, lleve a cabo uno de los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="18673-123">In **Recording**, do one of the following:</span></span>
    
   - <span data-ttu-id="18673-p105">Para impedir que los participantes graben reuniones, haga clic en **Ninguna**. Esta es la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="18673-p105">To prevent participants from recording meetings, click **None**. This is the default setting.</span></span>
    
   - <span data-ttu-id="18673-126">Para permitir que los participantes graben reuniones, haga clic en **Habilitar grabación**.</span><span class="sxs-lookup"><span data-stu-id="18673-126">To allow participants to record meetings, click **Enable recording**.</span></span>
    
9. <span data-ttu-id="18673-p106">Para permitir que los participantes externos graben reuniones, active la casilla **Permitir a los participantes federados y anónimos grabar**. Generalmente, los participantes externos no pueden grabar las reuniones.</span><span class="sxs-lookup"><span data-stu-id="18673-p106">To allow external participants to record meetings, select the **Allow federated and anonymous participants to record** check box. The default is to prevent external participants from recording meetings.</span></span>
    
10. <span data-ttu-id="18673-129">En **Audio/vídeo**, lleve a cabo uno de los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="18673-129">In **Audio/video**, do one of the following:</span></span>
    
    - <span data-ttu-id="18673-130">Para impedir el uso de audio y vídeo, haga clic en **Ninguno**.</span><span class="sxs-lookup"><span data-stu-id="18673-130">To prevent the use of audio and video, click **None**.</span></span>
    
    - <span data-ttu-id="18673-131">Para permitir el uso de audio pero no de vídeo, haga clic en **Habilitar audio IP**.</span><span class="sxs-lookup"><span data-stu-id="18673-131">To allow the use of audio but not video, click **Enable IP audio**.</span></span>
    
    - <span data-ttu-id="18673-p107">Para permitir el uso de audio y de vídeo, haga clic en **Habilitar audio y vídeo IP**. Esta es la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="18673-p107">To allow the use of audio and video, click **Enable IP audio/video**. This is the default setting.</span></span>
    
11. <span data-ttu-id="18673-134">Si opta por permitir el uso de audio en **Audio/vídeo**, realice uno de los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="18673-134">If you chose to allow the use of audio in **Audio/video**, do the following:</span></span>
    
    - <span data-ttu-id="18673-p108">Para impedir que los usuarios participen en la reunión mediante acceso telefónico, desactive la casilla **Habilitar conferencia de acceso telefónico local RTC**. Normalmente, los usuarios pueden acceder telefónicamente a las reuniones a través de la red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="18673-p108">To prevent users from joining the meeting by dialing in, clear the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
    - <span data-ttu-id="18673-p109">Si permite que los usuarios accedan telefónicamente a las reuniones y desea permitir que usuarios no autenticados (anónimos) se unan a una reunión con llamadas salientes, active la casilla **Permitir acceso telefónico a los participantes anónimos**. Con las llamadas salientes, el servidor de conferencia llama al usuario y este contesta el teléfono para participar en la reunión. Normalmente, los usuarios anónimos no pueden participar en una reunión con llamadas salientes.</span><span class="sxs-lookup"><span data-stu-id="18673-p109">If you allow users to dial in to meetings and you want to allow unauthenticated (anonymous) users to join a meeting by using dial out phoning, select the **Allow anonymous participants to dial out** check box. With dial-out phoning, the conference server calls the user, and the user answers the phone to join the meeting. By default, anonymous users cannot join a meeting by using dial-out phoning.</span></span>
    
12. <span data-ttu-id="18673-140">Si decidió permitir el uso de vídeo en **audio y vídeo,** active **Permitir varias secuencias de vídeo.**</span><span class="sxs-lookup"><span data-stu-id="18673-140">If you chose to allow the use of video in **Audio/video**, check **Allow multiple video streams**.</span></span>
    
13. <span data-ttu-id="18673-141">En **Colaboración de datos**, lleve a cabo uno de los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="18673-141">In **Data collaboration**, do one of the following:</span></span>
    
    - <span data-ttu-id="18673-142">Para impedir la colaboración de datos, haga clic en **Ninguna**.</span><span class="sxs-lookup"><span data-stu-id="18673-142">To prevent data collaboration, click **None**.</span></span>
    
    - <span data-ttu-id="18673-p110">Para permitir la colaboración de datos, haga clic en **Habilitar colaboración de datos**. Esta es la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="18673-p110">To allow data collaboration, click **Enable data collaboration**. This is the default setting.</span></span>
    
14. <span data-ttu-id="18673-145">Si opta por permitir la colaboración de datos en **Colaboración de datos**, realice uno de los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="18673-145">If you chose to allow data collaboration in **Data collaboration**, do the following:</span></span>
    
    - <span data-ttu-id="18673-p111">Para impedir descargas externas, desactive la casilla **Permitir a los participantes federados y anónimos descargar contenido**. Normalmente, los usuarios externos pueden descargar contenido.</span><span class="sxs-lookup"><span data-stu-id="18673-p111">To prevent external downloads, clear the **Allow federated and anonymous participants to download content** check box. By default, external users can download content.</span></span>
    
    - <span data-ttu-id="18673-p112">Para impedir la transferencia de archivos, desactive la casilla **Permitir a los participantes transferir archivos**. Normalmente, los usuarios pueden transferir archivos.</span><span class="sxs-lookup"><span data-stu-id="18673-p112">To prevent file transfers, clear the **Allow participants to transfer files** check box. By default, users can transfer files.</span></span>
    
    - <span data-ttu-id="18673-150">Para impedir el uso de anotaciones, desactive la casilla **Habilitar anotaciones**.</span><span class="sxs-lookup"><span data-stu-id="18673-150">To prevent the use of annotations, clear the **Enable annotations** check box.</span></span> <span data-ttu-id="18673-151">Para usar anotaciones en presentaciones compartidas de PowerPoint, desactive **habilitar anotaciones de PowerPoint.**</span><span class="sxs-lookup"><span data-stu-id="18673-151">To the use of annotations in shared PowerPoint presentations, clear the **Enable PowerPoint annotations**.</span></span> <span data-ttu-id="18673-152">Normalmente, las anotaciones se permiten.</span><span class="sxs-lookup"><span data-stu-id="18673-152">By default, annotations are allowed.</span></span>
    
    - <span data-ttu-id="18673-p114">Para impedir el uso de sondeos, desactive la casilla **Habilitar sondeos**. Normalmente, se permiten los sondeos.</span><span class="sxs-lookup"><span data-stu-id="18673-p114">To prevent the use of polls, clear the **Enable polls** check box. By default, polls are allowed.</span></span>
    
15. <span data-ttu-id="18673-155">En **Uso compartido de aplicaciones**, lleve a cabo uno de los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="18673-155">In **Application sharing**, do one of the following:</span></span>
    
    - <span data-ttu-id="18673-156">Para impedir el uso compartido de aplicaciones, haga clic en **Deshabilitar el uso compartido de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="18673-156">To prevent the use of application sharing, click **Disable application sharing**.</span></span>
    
    - <span data-ttu-id="18673-p115">Para permitir el uso compartido de aplicaciones, haga clic en **Habilitar el uso compartido de aplicaciones**. Esta es la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="18673-p115">To allow the use of application sharing, click **Enable application sharing**. This is the default setting.</span></span>
    
16. <span data-ttu-id="18673-159">Si opta por permitir el uso compartido de aplicaciones en **Compartit aplicaciones**, realice uno de los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="18673-159">If you chose to allow application sharing in **Application sharing**, do the following:</span></span>
    
    - <span data-ttu-id="18673-p116">Para impedir que los participantes en una reunión controlen el uso compartido de aplicaciones, desactive la casilla **Permitir a los participantes asumir el control**. Normalmente, los participantes pueden controlar el uso compartido de las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="18673-p116">To prevent meeting participants from taking control of application sharing, clear the **Allow participants to take control** check box. By default, participants can take control of application sharing.</span></span>
    
    - <span data-ttu-id="18673-p117">Si opta por permitir que los participantes de las reuniones controlen el uso compartido de aplicaciones, seleccione la casilla **Permitir a los participantes federados y anónimos asumir el control** para permitir que los usuarios externos controlen el uso compartido de aplicaciones. Normalmente, los usuarios externos no pueden controlar el uso compartido de las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="18673-p117">If you chose to allow meeting participants to take control of application sharing, select the **Allow federated and anonymous participants to take control** check box to allow external users to take control of application sharing. By default, external users cannot take control of application sharing.</span></span>
    
17. <span data-ttu-id="18673-164">En **Directiva de participantes**, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="18673-164">Under **Participant policy**, do one of the following:</span></span>
    
    - <span data-ttu-id="18673-165">Para impedir el uso compartido de las aplicaciones y del escritorio, haga clic en **Deshabilitar el uso compartido de aplicaciones y escritorio**.</span><span class="sxs-lookup"><span data-stu-id="18673-165">To prevent both application sharing and desktop sharing, click **Disable application and desktop sharing**.</span></span>
    
    - <span data-ttu-id="18673-166">Para permitir el uso compartido de las aplicaciones pero no el uso compartido del escritorio, haga clic en **Habilitar el uso compartido de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="18673-166">To allow application sharing but not desktop sharing, click **Enable application sharing**.</span></span>
    
    - <span data-ttu-id="18673-p118">Para permitir el uso compartido de las aplicaciones y del escritorio, haga clic en **Habilitar el uso compartido de aplicaciones y escritorio**. Esta es la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="18673-p118">To allow both application sharing and desktop sharing, click **Enable application and desktop sharing**. This is the default setting.</span></span>
    
18. <span data-ttu-id="18673-p119">Para impedir la transferencia de archivos punto a punto, desactive la casilla **Habilitar la transferencia de archivos punto a punto**. Normalmente, se permite la transferencia de archivos punto a punto.</span><span class="sxs-lookup"><span data-stu-id="18673-p119">To prevent peer-to-peer file transfers, clear the **Enable peer-to-peer file transfer** check box. By default, peer-to-peer file transfers are allowed.</span></span>
    
19. <span data-ttu-id="18673-p120">Para permitir la grabación punto a punto, active la casilla **Habilitar grabación punto a punto**. Normalmente, no se permite la grabación punto a punto.</span><span class="sxs-lookup"><span data-stu-id="18673-p120">To allow peer-to-peer recording, select the **Enable peer-to-peer recording** check box. By default, peer-to-peer recording is not allowed.</span></span>
    
20. <span data-ttu-id="18673-p121">Para permitir que los participantes se unan con varias secuencias de vídeo, active la casilla **Permitir que los participantes se unan con varias secuencias de vídeo**. Normalmente, se permiten varias secuencias de vídeo.</span><span class="sxs-lookup"><span data-stu-id="18673-p121">To allow participants to join with multiple video streams, select the **Enable participants to join with multiple video streams** check box. By default, multiple video streams are allowed.</span></span>
    
21. <span data-ttu-id="18673-175">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="18673-175">Click **Commit**.</span></span>
    
## <a name="create-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="18673-176">Crear directivas de conferencia con el Shell de administración de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="18673-176">Create conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="18673-177">Para crear directivas de conferencia, use el cmdlet **New-CsConferencingPolicy.**</span><span class="sxs-lookup"><span data-stu-id="18673-177">To create conferencing policies, use the **New-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="18673-178">En el siguiente ejemplo se crea una nueva directiva de conferencia con la identidad SalesConferencingPolicy.</span><span class="sxs-lookup"><span data-stu-id="18673-178">The following example creates a new conferencing policy with the Identity SalesConferencingPolicy.</span></span> <span data-ttu-id="18673-179">Esta directiva usará todos los valores predeterminados para una directiva de conferencia excepto uno: MaxMeetingSize.</span><span class="sxs-lookup"><span data-stu-id="18673-179">This policy will use all the default values for a conferencing policy except one: MaxMeetingSize.</span></span> <span data-ttu-id="18673-180">En este ejemplo, el tamaño máximo de una reunión se establecerá en 50 en lugar del valor predeterminado de 250:</span><span class="sxs-lookup"><span data-stu-id="18673-180">In this example, the maximum size for a meeting will be set to 50 instead of the default value of 250:</span></span>
  
```PowerShell
New-CsConferencingPolicy -Identity SalesConferencingPolicy -MaxMeetingSize 50
```

<span data-ttu-id="18673-181">Para obtener más información, incluida una descripción de sintaxis completa y una lista de parámetros, [vea New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="18673-181">For more information, including a complete syntax description and list of parameters, see [New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps).</span></span>
  

