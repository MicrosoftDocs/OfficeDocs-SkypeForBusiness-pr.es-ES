---
title: Administración de la directiva de acceso externo a la organización
ms.reviewer: ''
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Después de implementar uno o varios servidores Edge, debe habilitar los tipos de acceso externo que se permitirán en la organización.
ms.openlocfilehash: 71797e865860107d23095659461c1b02e6d47cd7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817260"
---
# <a name="manage-external-access-policy-for-your-organization"></a><span data-ttu-id="8236c-103">Administración de la directiva de acceso externo a la organización</span><span class="sxs-lookup"><span data-stu-id="8236c-103">Manage external access policy for your organization</span></span>

<span data-ttu-id="8236c-104">Después de implementar uno o varios servidores Edge, debe habilitar los tipos de acceso externo que se permitirán en la organización.</span><span class="sxs-lookup"><span data-stu-id="8236c-104">After deploying one or more Edge Servers, you must enable the types of external access that will be supported for your organization.</span></span>

<span data-ttu-id="8236c-p101">De forma predeterminada, no hay ninguna directiva configurada para admitir el acceso de usuarios externos, incluido el acceso de usuarios remotos, el acceso de usuarios federados, incluso si ya ha habilitado la compatibilidad con el acceso de usuarios externos para su organización. Para controlar el uso del acceso de usuarios externos, debe configurar una o más directivas, especificando el tipo de acceso de usuarios externos que es compatible con cada directiva. Para la creación y configuración están disponibles los siguientes ámbitos de directivas. De forma predeterminada, se crea la directiva global, pero no se puede eliminar.</span><span class="sxs-lookup"><span data-stu-id="8236c-p101">By default, there are no policies configured to support external user access, including remote user access, federated user access, even if you have already enabled external user access support for your organization. To control the use of external user access, you must configure one or more policies, specifying the type of external user access supported for each policy. The following policy scopes are available for creation and configuration. By default, the Global policy is created, but cannot be deleted.</span></span>

  - <span data-ttu-id="8236c-109">**Directiva global**   La directiva global se crea al implementar los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="8236c-109">**Global policy**   The global policy is created when you deploy your Edge Servers.</span></span> <span data-ttu-id="8236c-110">De forma predeterminada, no hay habilitadas opciones de acceso de usuarios externos en la directiva global.</span><span class="sxs-lookup"><span data-stu-id="8236c-110">By default, no external user access options are enabled in the global policy.</span></span> <span data-ttu-id="8236c-111">Para admitir el acceso de usuarios externos en el nivel global, debe configurar la directiva global para que admita uno o más tipos de opciones de acceso de usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="8236c-111">To support external user access at the global level, you configure the global policy to support one or more types of external user access options.</span></span> <span data-ttu-id="8236c-112">La directiva global se aplica a todos los usuarios de su organización, pero las directivas de sitio y usuario invalidan la directiva global.</span><span class="sxs-lookup"><span data-stu-id="8236c-112">The global policy applies to all users in your organization, but site policies and user policies override the global policy.</span></span> <span data-ttu-id="8236c-113">Eliminar la directiva global no hará que desaparezca.</span><span class="sxs-lookup"><span data-stu-id="8236c-113">If you delete the global policy, you do not remove it.</span></span> <span data-ttu-id="8236c-114">En lugar de eso, se restablece la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="8236c-114">Instead, you reset it to the default setting.</span></span>

  - <span data-ttu-id="8236c-115">**Directiva de sitio**   Puede crear y configurar una o más directivas de sitio para limitar la compatibilidad con el acceso de usuarios externos a sitios específicos.</span><span class="sxs-lookup"><span data-stu-id="8236c-115">**Site policy**   You can create and configure one or more site policies to limit support for external user access to specific sites.</span></span> <span data-ttu-id="8236c-116">La configuración de la directiva de sitio invalida la directiva global, pero solo en el caso del sitio específico que determina la directiva.</span><span class="sxs-lookup"><span data-stu-id="8236c-116">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="8236c-117">Por ejemplo, si activa el acceso de usuarios remotos en la directiva global, puede especificar una directiva de sitio que deshabilite el acceso de usuarios remotos para un sitio específico.</span><span class="sxs-lookup"><span data-stu-id="8236c-117">For example, if you enable remote user access in the global policy, you might specify a site policy that disables remote user access for a specific site.</span></span> <span data-ttu-id="8236c-118">De forma predeterminada, una directiva de sitio se aplica a todos los usuarios de dicho sitio, aunque puede asignar una directiva de usuario a un usuario determinado para invalidar dicho parámetro de la directiva de sitio.</span><span class="sxs-lookup"><span data-stu-id="8236c-118">By default, a site policy is applied to all users of that site, but you can assign a user policy to a user to override the site policy setting.</span></span>

  - <span data-ttu-id="8236c-119">**Directiva de usuario**   Puede crear y configurar una o más directivas de usuario para limitar la compatibilidad con el acceso de usuarios remotos a usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="8236c-119">**User policy**   You can create and configure one or more user policies to limit support for remote user access to specific users.</span></span> <span data-ttu-id="8236c-120">La configuración de la directiva de usuario invalida la directiva global y la directiva de sitio, pero solo para los usuarios concretos a los que se ha asignado la directiva de usuario.</span><span class="sxs-lookup"><span data-stu-id="8236c-120">The configuration in the user policy overrides the global and site policy, but only for the specific users to whom the user policy is assigned.</span></span> <span data-ttu-id="8236c-121">Por ejemplo, si deshabilita el acceso de usuarios remotos en la directiva global y a la directiva de sitio, puede especificar una directiva de usuario para deshabilitar el acceso de usuarios remotos y, a continuación, asignar dicha directiva de usuario a usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="8236c-121">For example, if you enable remote user access in the global policy and site policy, you might specify a user policy that disables remote user access and then assign that user policy to specific users.</span></span> <span data-ttu-id="8236c-122">Si crea una directiva de sitio, debe aplicarla a uno o más usuarios antes de que se haga efectiva.</span><span class="sxs-lookup"><span data-stu-id="8236c-122">If you create a user policy, you must apply it to one or more users before it takes effect.</span></span>


> [!IMPORTANT]  
> <span data-ttu-id="8236c-123">Las opciones de configuración de directiva que se aplican en un nivel de directiva pueden sobrescribir la configuración que se aplica en otro nivel de directiva.</span><span class="sxs-lookup"><span data-stu-id="8236c-123">Policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="8236c-124">La prioridad de las directivas de Skype Empresarial Server es: la directiva de usuario (mayor influencia) invalida una directiva de sitio y una directiva de sitio invalida una directiva global (menor influencia).</span><span class="sxs-lookup"><span data-stu-id="8236c-124">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="8236c-125">Esto significa que cuanto más se aproxime la configuración de la directiva al objeto al que afecta la directiva, más influencia tendrá en el objeto.</span><span class="sxs-lookup"><span data-stu-id="8236c-125">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>


<span data-ttu-id="8236c-126">Entre estas opciones se incluyen los siguientes tipos de acceso externo:</span><span class="sxs-lookup"><span data-stu-id="8236c-126">These options include the following types of external access:</span></span>

  - <span data-ttu-id="8236c-127">**Habilitar las comunicaciones con usuarios federados**   Habilite esta opción si desea admitir el acceso de usuarios a dominios de socios federados.</span><span class="sxs-lookup"><span data-stu-id="8236c-127">**Enable communications with federated users**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="8236c-128">Esta configuración configura la capacidad para que los usuarios se comuniquen con otros dominios federados SIP, así como con proveedores hospedados como Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="8236c-128">This setting configures the ability for users to communicate with other SIP federated domains, as well as Hosted providers like Microsoft 365 or Office 365.</span></span> 


  - <span data-ttu-id="8236c-129">**Habilitar las comunicaciones con usuarios remotos**   Habilite esta opción si desea que los usuarios de su organización que están fuera del firewall, como los teletrabadores y los usuarios que están de viaje, puedan conectarse a Skype Empresarial Server a través de Internet.</span><span class="sxs-lookup"><span data-stu-id="8236c-129">**Enable communications with remote users**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Skype for Business Server over the Internet.</span></span>

  - <span data-ttu-id="8236c-130">**Habilitar las comunicaciones con usuarios públicos**   Habilite esta opción si desea que los usuarios internos puedan comunicarse con los contactos del proveedor de mensajería instantánea pública.</span><span class="sxs-lookup"><span data-stu-id="8236c-130">**Enable communications with public users**   Enable this option if you want internal users to be able to communicate with public IM provider contacts.</span></span>
   

> [!NOTE]  
> <span data-ttu-id="8236c-131">Además de habilitar la compatibilidad de acceso de usuarios externos, también debe configurar directivas para controlar el uso del acceso de usuarios externos en su organización antes de que los usuarios obtengan cualquier tipo de acceso para usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="8236c-131">In addition to enabling external user access support, you must also configure policies to control the use of external user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="8236c-132">Para detalles sobre cómo crear, configurar y aplicar directivas para acceso de usuarios externos, vea [Habilitar y deshabilitar el acceso de usuarios remotos](../access-edge/enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="8236c-132">For details about creating, configuring, and applying policies for external user access see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>



<span data-ttu-id="8236c-133">**Para ver directivas de acceso externo con cmdlets de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="8236c-133">**To view external access policies by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="8236c-134">Las directivas de acceso externas se pueden ver con el shell de administración de Skype Empresarial Server y el cmdlet **Get-CsExternalAccessPolicy**.</span><span class="sxs-lookup"><span data-stu-id="8236c-134">You can view external access policies by using Skype for Business Server Management Shell and the **Get-CsExternalAccessPolicy** cmdlet.</span></span> <span data-ttu-id="8236c-135">Puede ejecutar este cmdlet desde el shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8236c-135">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 
    
    <span data-ttu-id="8236c-136">Para ver información sobre todas las directivas de acceso externo escriba el comando siguiente en el shell de administración de Lync Server y presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="8236c-136">To view information about all your external access policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
    `Get-CsExternalAccessPolicy`
    
    <span data-ttu-id="8236c-137">Este comando devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="8236c-137">This command returns information similar to the following:</span></span>
    
    ```console
    Identity                          : Global
    Description                       :
    EnableFederationAccess            : False
    EnableXmppAccess                  : False
    EnablePublicCloudAccess           : False
    EnablePublicCloudAudioVideoAccess : False
    EnableOutsideAccess               : False
    ```
