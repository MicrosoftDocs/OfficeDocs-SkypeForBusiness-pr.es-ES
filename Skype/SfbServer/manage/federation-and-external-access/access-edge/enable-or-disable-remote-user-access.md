---
title: Habilitar y deshabilitar el acceso de usuarios remotos
ms.reviewer: ''
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
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
description: Si habilita el acceso de usuarios remotos para usuarios remotos, los usuarios remotos admitidos se conectan a través de Internet y no tienen que conectarse con una VPN para colaborar con usuarios internos con Skype Empresarial Server.
ms.openlocfilehash: 9e5ba5828e129c6fed5dd892b1a7bb8e6bd64707
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817400"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a><span data-ttu-id="39490-103">Habilitar o deshabilitar el acceso de usuarios remotos en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="39490-103">Enable or disable remote user access in Skype for Business Server</span></span>

<span data-ttu-id="39490-104">Los usuarios remotos son usuarios de la organización que tienen una identidad persistente de Active Directory en la organización.</span><span class="sxs-lookup"><span data-stu-id="39490-104">Remote users are users in your organization who have a persistent Active Directory identity within the organization.</span></span> <span data-ttu-id="39490-105">Los usuarios remotos suelen iniciar sesión en Skype Empresarial Server desde fuera de la red mediante una red privada virtual (VPN) cuando no están conectados a la red de su organización.</span><span class="sxs-lookup"><span data-stu-id="39490-105">Remote users often sign in to Skype for Business Server from outside your network by using a virtual private network (VPN) when they are not connected to your organization’s network.</span></span> <span data-ttu-id="39490-106">Entre los usuarios se encuentran los empleados que trabajan en casa o fuera de la oficina, así como otros trabajadores remotos, como los proveedores de confianza, a los que se conceden credenciales corporativas.</span><span class="sxs-lookup"><span data-stu-id="39490-106">Remote users include employees working at home or on the road and other remote workers, such as trusted vendors, who have been granted enterprise credentials.</span></span> <span data-ttu-id="39490-107">Si habilita el acceso de usuarios remotos para usuarios remotos, los usuarios remotos admitidos se conectan a través de Internet y no tienen que conectarse con una VPN para colaborar con usuarios internos con Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="39490-107">If you enable remote user access for remote users, supported remote users connect over the Internet and do not have to connect using a VPN in order to collaborate with internal users using Skype for Business Server.</span></span>

<span data-ttu-id="39490-p102">Si más adelante desea impedir de forma provisional o definitiva el acceso a usuarios de dominios federados, deshabilite la federación para la organización. Para habilitar o deshabilitar el acceso de usuarios federados en su organización, siga el procedimiento de esta sección, que también incluye las opciones de federación adecuadas que debe admitir la organización.</span><span class="sxs-lookup"><span data-stu-id="39490-p102">To support remote user access, you must enable remote user access. When you enable remote user access, you enable it for your entire organization. If you later want to temporarily or permanently prevent remote user access, you can disable it for your organization. Use the procedure in this section to enable or disable remote user access for your organization.</span></span>


> [!NOTE]  
> <span data-ttu-id="39490-112">Al habilitar el acceso de usuarios remotos solo se especifica que los servidores que ejecuten el servicio perimetral de acceso permitan la comunicación con usuarios remotos, pero dichos usuarios no pueden participar en mensajes instantáneos ni en conferencias de la organización hasta que también se configure una directiva para administrar el uso del acceso de usuarios remotos.</span><span class="sxs-lookup"><span data-stu-id="39490-112">Enabling remote user access only specifies that your servers running the Access Edge service support communications with remote users, but remote users cannot participate in instant messaging (IM) or conferences in your organization until you also configure at least one policy to manage the use of remote user access.</span></span> <span data-ttu-id="39490-113">La configuración de directiva de Skype Empresarial Server que se aplica en un nivel de directiva puede invalidar la configuración que se aplica en otro nivel de directiva.</span><span class="sxs-lookup"><span data-stu-id="39490-113">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="39490-114">La prioridad de las directivas de Skype Empresarial Server es: la directiva de usuario (mayor influencia) invalida una directiva de sitio y una directiva de sitio invalida una directiva global (menor influencia).</span><span class="sxs-lookup"><span data-stu-id="39490-114">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="39490-115">Esto significa que cuanto más se aproxime la configuración de la directiva al objeto al que afecta la directiva, más influencia tendrá en el objeto.</span><span class="sxs-lookup"><span data-stu-id="39490-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> <span data-ttu-id="39490-116">Para obtener más información sobre cómo configurar directivas para el uso del acceso de usuarios remotos, consulte Configurar directivas para controlar el acceso de usuarios remotos [en Skype Empresarial Server.](../external-access-policies/configure-policies-to-control-remote-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="39490-116">For details about configuring policies for the use of remote user access, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a><span data-ttu-id="39490-117">Para habilitar o deshabilitar el acceso de usuarios remotos en la organización</span><span class="sxs-lookup"><span data-stu-id="39490-117">To enable or disable remote user access for your organization</span></span>

1.  <span data-ttu-id="39490-118">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="39490-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="39490-119">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="39490-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="39490-120">En el barra de navegación izquierda, haga clic en **Federación y acceso externo** y luego en **Configuración perimetral de acceso**.</span><span class="sxs-lookup"><span data-stu-id="39490-120">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="39490-121">En la página **Configuración perimetral de acceso**, haga clic en **Global**, en **Editar** y, a continuación en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="39490-121">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="39490-122">En **Editar configuración perimetral de acceso**, lleve a cabo uno de los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="39490-122">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="39490-123">Para habilitar el acceso de usuarios remotos en la organización, active la casilla **Habilitar el acceso remoto de usuarios**.</span><span class="sxs-lookup"><span data-stu-id="39490-123">To enable remote user access for your organization, select the **Enable remote user access** check box.</span></span>
    
      - <span data-ttu-id="39490-124">Para deshabilitar el acceso remoto de usuarios en la organización, desactive la casilla **Habilitar el acceso remoto de usuarios**.</span><span class="sxs-lookup"><span data-stu-id="39490-124">To disable remote user access for your organization, clear the **Enable remote user access** check box.</span></span>

6.  <span data-ttu-id="39490-125">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="39490-125">Click **Commit**.</span></span>

<span data-ttu-id="39490-126">Para permitir que los usuarios remotos inicien sesión en los servidores que ejecutan Skype Empresarial Server, también debe configurar al menos una directiva de acceso externo para admitir el acceso de usuarios remotos.</span><span class="sxs-lookup"><span data-stu-id="39490-126">To enable remote users to sign in to your servers running Skype for Business Server, you must also configure at least one external access policy to support remote user access.</span></span> <span data-ttu-id="39490-127">Para obtener más información, consulte [Configurar directivas para controlar el acceso de usuarios remotos en Skype Empresarial Server.](../external-access-policies/configure-policies-to-control-remote-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="39490-127">For details, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="39490-128">Habilitar o deshabilitar el acceso de usuarios remotos mediante cmdlets Windows PowerShell remoto</span><span class="sxs-lookup"><span data-stu-id="39490-128">Enabling or disabling remote user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="39490-129">El acceso de usuarios remotos se puede administrar mediante Windows PowerShell y el cmdlet Set-CsAccessEdgeConfiguration usuario.</span><span class="sxs-lookup"><span data-stu-id="39490-129">Remote user access can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="39490-130">Este cmdlet se puede ejecutar desde el Shell de administración de Skype Empresarial Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="39490-130">This cmdlet can be run either from the Skype for Business Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-remote-user-access"></a><span data-ttu-id="39490-131">Para habilitar el acceso de usuarios remotos</span><span class="sxs-lookup"><span data-stu-id="39490-131">To enable remote user access</span></span>

  - <span data-ttu-id="39490-132">Para habilitar el acceso de usuarios remotos, defina el valor de la propiedad **AllowOutsideUsers** en True ($True):</span><span class="sxs-lookup"><span data-stu-id="39490-132">To enable remote user access, set the value of the **AllowOutsideUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## <a name="to-disable-remote-user-access"></a><span data-ttu-id="39490-133">Para deshabilitar el acceso de usuarios remotos</span><span class="sxs-lookup"><span data-stu-id="39490-133">To disable remote user access</span></span>

  - <span data-ttu-id="39490-134">Para inhabilitar el acceso de usuarios remotos, defina el valor de la propiedad **AllowOutsideUsers** en False ($False):</span><span class="sxs-lookup"><span data-stu-id="39490-134">To disable remote user access, set the value of the **AllowOutsideUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False


