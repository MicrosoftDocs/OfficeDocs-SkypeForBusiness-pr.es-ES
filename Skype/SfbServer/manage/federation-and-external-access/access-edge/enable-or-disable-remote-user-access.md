---
title: Habilitar y deshabilitar el acceso de usuarios remotos
ms.reviewer: ''
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Si habilita el acceso de usuarios remotos para usuarios remotos, los usuarios remotos compatibles se conectan a través de Internet y no tienen que conectarse usando una VPN para colaborar con usuarios internos que usen Skype empresarial Server.
ms.openlocfilehash: b562dbe7a849ca4266a45303008ff9081903658d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818381"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a><span data-ttu-id="724e4-103">Habilitar o deshabilitar el acceso de usuarios remotos en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="724e4-103">Enable or disable remote user access in Skype for Business Server</span></span>

<span data-ttu-id="724e4-104">Los usuarios remotos son usuarios de su organización que tienen una identidad de Active Directory persistente dentro de la organización.</span><span class="sxs-lookup"><span data-stu-id="724e4-104">Remote users are users in your organization who have a persistent Active Directory identity within the organization.</span></span> <span data-ttu-id="724e4-105">Los usuarios remotos a menudo inician sesión en Skype empresarial Server desde fuera de la red mediante una red privada virtual (VPN) cuando no están conectados a la red de su organización.</span><span class="sxs-lookup"><span data-stu-id="724e4-105">Remote users often sign in to Skype for Business Server from outside your network by using a virtual private network (VPN) when they are not connected to your organization’s network.</span></span> <span data-ttu-id="724e4-106">Los usuarios remotos incluyen empleados que trabajan en casa o que están de viaje y otros trabajadores remotos, como proveedores de confianza, a los que se les han concedido credenciales empresariales.</span><span class="sxs-lookup"><span data-stu-id="724e4-106">Remote users include employees working at home or on the road and other remote workers, such as trusted vendors, who have been granted enterprise credentials.</span></span> <span data-ttu-id="724e4-107">Si habilita el acceso de usuarios remotos para usuarios remotos, los usuarios remotos compatibles se conectan a través de Internet y no tienen que conectarse usando una VPN para colaborar con usuarios internos que usen Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="724e4-107">If you enable remote user access for remote users, supported remote users connect over the Internet and do not have to connect using a VPN in order to collaborate with internal users using Skype for Business Server.</span></span>

<span data-ttu-id="724e4-108">Para admitir el acceso de usuarios remotos, debe habilitar el acceso de usuarios remotos.</span><span class="sxs-lookup"><span data-stu-id="724e4-108">To support remote user access, you must enable remote user access.</span></span> <span data-ttu-id="724e4-109">Cuando se habilita el acceso de usuarios remotos, se habilita para toda la organización.</span><span class="sxs-lookup"><span data-stu-id="724e4-109">When you enable remote user access, you enable it for your entire organization.</span></span> <span data-ttu-id="724e4-110">Si posteriormente desea evitar el acceso de usuarios remotos de forma temporal o permanente, puede deshabilitarlo para su organización.</span><span class="sxs-lookup"><span data-stu-id="724e4-110">If you later want to temporarily or permanently prevent remote user access, you can disable it for your organization.</span></span> <span data-ttu-id="724e4-111">Use el procedimiento de esta sección para habilitar o deshabilitar el acceso de usuarios remotos a su organización.</span><span class="sxs-lookup"><span data-stu-id="724e4-111">Use the procedure in this section to enable or disable remote user access for your organization.</span></span>


> [!NOTE]  
> <span data-ttu-id="724e4-112">Habilitar el acceso de usuarios remotos solo especifica que los servidores que ejecutan el servicio perimetral de acceso admiten comunicaciones con usuarios remotos, pero los usuarios remotos no pueden participar en la mensajería instantánea (mi) ni en conferencias de su organización hasta que también configure en menos una directiva para administrar el uso del acceso de usuarios remotos.</span><span class="sxs-lookup"><span data-stu-id="724e4-112">Enabling remote user access only specifies that your servers running the Access Edge service support communications with remote users, but remote users cannot participate in instant messaging (IM) or conferences in your organization until you also configure at least one policy to manage the use of remote user access.</span></span> <span data-ttu-id="724e4-113">La configuración de directiva de Skype empresarial Server que se aplica a un nivel de Directiva puede invalidar la configuración que se aplica a otro nivel de directiva.</span><span class="sxs-lookup"><span data-stu-id="724e4-113">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="724e4-114">La prioridad de la Directiva de servidor de Skype empresarial es: la Directiva de usuario (más influencia) reemplaza a una directiva de sitio y, después, una directiva de sitio invalida una directiva global (menor influencia).</span><span class="sxs-lookup"><span data-stu-id="724e4-114">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="724e4-115">Esto significa que, cuanto más cercana es la configuración de directiva al objeto al que la directiva afecta, mayor es la influencia que ejerce sobre el objeto.</span><span class="sxs-lookup"><span data-stu-id="724e4-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> <span data-ttu-id="724e4-116">Para obtener más información sobre cómo configurar directivas para el uso de acceso de usuarios remotos, vea [configurar directivas para controlar el acceso de usuarios remotos en Skype empresarial Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="724e4-116">For details about configuring policies for the use of remote user access, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a><span data-ttu-id="724e4-117">Para habilitar o deshabilitar el acceso de usuarios remotos a su organización</span><span class="sxs-lookup"><span data-stu-id="724e4-117">To enable or disable remote user access for your organization</span></span>

1.  <span data-ttu-id="724e4-118">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="724e4-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="724e4-119">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="724e4-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="724e4-120">En la barra de navegación izquierda, haga clic en **Federación y acceso externo** y, luego, en **Configuración perimetral de acceso**.</span><span class="sxs-lookup"><span data-stu-id="724e4-120">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="724e4-121">En la página **configuración de perímetro de Access** , haga clic en **global**, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="724e4-121">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="724e4-122">En **Editar configuración del límite de acceso**, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="724e4-122">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="724e4-123">Para habilitar el acceso de usuarios remotos a su organización, seleccione la casilla de verificación **Habilitar el acceso de usuarios remotos** .</span><span class="sxs-lookup"><span data-stu-id="724e4-123">To enable remote user access for your organization, select the **Enable remote user access** check box.</span></span>
    
      - <span data-ttu-id="724e4-124">Para deshabilitar el acceso de usuarios remotos a su organización, desactive la casilla **Habilitar el acceso de usuarios remotos** .</span><span class="sxs-lookup"><span data-stu-id="724e4-124">To disable remote user access for your organization, clear the **Enable remote user access** check box.</span></span>

6.  <span data-ttu-id="724e4-125">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="724e4-125">Click **Commit**.</span></span>

<span data-ttu-id="724e4-126">Para permitir que los usuarios remotos inicien sesión en sus servidores con Skype empresarial Server, también debe configurar al menos una directiva de acceso externo para que admita el acceso de usuarios remotos.</span><span class="sxs-lookup"><span data-stu-id="724e4-126">To enable remote users to sign in to your servers running Skype for Business Server, you must also configure at least one external access policy to support remote user access.</span></span> <span data-ttu-id="724e4-127">Para obtener más información, consulte [configurar directivas para controlar el acceso de usuarios remotos en Skype empresarial Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="724e4-127">For details, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="724e4-128">Habilitar o deshabilitar el acceso de usuarios remotos mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="724e4-128">Enabling or disabling remote user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="724e4-129">El acceso de usuarios remotos se puede administrar mediante Windows PowerShell y el cmdlet Set-CsAccessEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="724e4-129">Remote user access can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="724e4-130">Este cmdlet se puede ejecutar desde el shell de administración de Skype empresarial Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="724e4-130">This cmdlet can be run either from the Skype for Business Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-remote-user-access"></a><span data-ttu-id="724e4-131">Para habilitar el acceso de usuarios remotos</span><span class="sxs-lookup"><span data-stu-id="724e4-131">To enable remote user access</span></span>

  - <span data-ttu-id="724e4-132">Para habilitar el acceso de usuarios remotos, establezca el valor de la propiedad **AllowOutsideUsers** en True ($true):</span><span class="sxs-lookup"><span data-stu-id="724e4-132">To enable remote user access, set the value of the **AllowOutsideUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## <a name="to-disable-remote-user-access"></a><span data-ttu-id="724e4-133">Para deshabilitar el acceso de usuarios remotos</span><span class="sxs-lookup"><span data-stu-id="724e4-133">To disable remote user access</span></span>

  - <span data-ttu-id="724e4-134">Para deshabilitar el acceso de usuarios remotos, establezca el valor de la propiedad **AllowOutsideUsers** en False ($false):</span><span class="sxs-lookup"><span data-stu-id="724e4-134">To disable remote user access, set the value of the **AllowOutsideUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False


