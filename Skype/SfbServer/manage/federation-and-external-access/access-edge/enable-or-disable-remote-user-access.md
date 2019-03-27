---
title: Habilitar y deshabilitar el acceso de usuarios remotos
ms.reviewer: ''
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Si habilita el acceso de usuarios remotos para los usuarios remotos, los usuarios remotos compatibles conectan a través de Internet y no tienen conexión con una red privada virtual para colaborar con los usuarios internos con Skype para Business Server.
ms.openlocfilehash: aea136e6c8758fd646a20b8bc7a64a393d45a3e7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898919"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a><span data-ttu-id="f0290-103">Habilitar o deshabilitar el acceso de usuarios remotos en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="f0290-103">Enable or disable remote user access in Skype for Business Server</span></span>

<span data-ttu-id="f0290-104">Los usuarios remotos son los usuarios de la organización que tienen una identidad de Active Directory persistente dentro de la organización.</span><span class="sxs-lookup"><span data-stu-id="f0290-104">Remote users are users in your organization who have a persistent Active Directory identity within the organization.</span></span> <span data-ttu-id="f0290-105">Los usuarios remotos a menudo inicie sesión en Skype para Business Server desde fuera de la red mediante el uso de una red privada virtual (VPN) cuando no están conectados a la red de su organización.</span><span class="sxs-lookup"><span data-stu-id="f0290-105">Remote users often sign in to Skype for Business Server from outside your network by using a virtual private network (VPN) when they are not connected to your organization’s network.</span></span> <span data-ttu-id="f0290-106">Los usuarios remotos incluyen a los empleados que trabajan en casa o de viaje y otros trabajadores remotos, como proveedores de confianza, que se hayan concedido credenciales de empresa.</span><span class="sxs-lookup"><span data-stu-id="f0290-106">Remote users include employees working at home or on the road and other remote workers, such as trusted vendors, who have been granted enterprise credentials.</span></span> <span data-ttu-id="f0290-107">Si habilita el acceso de usuarios remotos para los usuarios remotos, los usuarios remotos compatibles conectan a través de Internet y no tienen conexión con una red privada virtual para colaborar con los usuarios internos con Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="f0290-107">If you enable remote user access for remote users, supported remote users connect over the Internet and do not have to connect using a VPN in order to collaborate with internal users using Skype for Business Server.</span></span>

<span data-ttu-id="f0290-108">Para permitir el acceso de usuarios remotos, debe habilitar el acceso de usuarios remotos.</span><span class="sxs-lookup"><span data-stu-id="f0290-108">To support remote user access, you must enable remote user access.</span></span> <span data-ttu-id="f0290-109">Cuando se habilita el acceso de usuarios remotos, habilitarla para toda la organización.</span><span class="sxs-lookup"><span data-stu-id="f0290-109">When you enable remote user access, you enable it for your entire organization.</span></span> <span data-ttu-id="f0290-110">Si más adelante desea temporal o permanente impedir el acceso de usuarios remotos, se puede deshabilitar para su organización.</span><span class="sxs-lookup"><span data-stu-id="f0290-110">If you later want to temporarily or permanently prevent remote user access, you can disable it for your organization.</span></span> <span data-ttu-id="f0290-111">Use el procedimiento de esta sección para habilitar o deshabilitar el acceso de usuarios remotos para su organización.</span><span class="sxs-lookup"><span data-stu-id="f0290-111">Use the procedure in this section to enable or disable remote user access for your organization.</span></span>


> [!NOTE]  
> <span data-ttu-id="f0290-112">Habilitación del acceso de usuarios remotos sólo se especifica que los servidores que ejecutan el servicio de servidor perimetral de acceso admiten comunicaciones con usuarios remotos, pero los usuarios remotos no pueden participar en conferencias en su organización o de mensajería instantánea (mi) hasta que configure también en menos de una directiva para administrar el uso de acceso de usuarios remotos.</span><span class="sxs-lookup"><span data-stu-id="f0290-112">Enabling remote user access only specifies that your servers running the Access Edge service support communications with remote users, but remote users cannot participate in instant messaging (IM) or conferences in your organization until you also configure at least one policy to manage the use of remote user access.</span></span> <span data-ttu-id="f0290-113">Skype para la configuración de directiva de Business Server que se aplican en un nivel de directiva puede invalidar la configuración que se aplica en el nivel de directiva de otra.</span><span class="sxs-lookup"><span data-stu-id="f0290-113">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="f0290-114">Skype para la prioridad de la directiva de Business Server es: directiva de usuario (más influencia) reemplaza una directiva de sitio y, a continuación, una directiva de sitio invalida una directiva Global (menos influencia).</span><span class="sxs-lookup"><span data-stu-id="f0290-114">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="f0290-115">Esto significa que, cuanto más cercana es la configuración de directiva al objeto al que la directiva afecta, mayor es la influencia que ejerce sobre el objeto.</span><span class="sxs-lookup"><span data-stu-id="f0290-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> <span data-ttu-id="f0290-116">Para obtener información detallada acerca de cómo configurar las directivas para el uso de acceso de usuarios remotos, vea [Configurar directivas para controlar el acceso de usuarios remotos en Skype para Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="f0290-116">For details about configuring policies for the use of remote user access, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a><span data-ttu-id="f0290-117">Para habilitar o deshabilitar el acceso de usuarios remotos para su organización</span><span class="sxs-lookup"><span data-stu-id="f0290-117">To enable or disable remote user access for your organization</span></span>

1.  <span data-ttu-id="f0290-118">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="f0290-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f0290-119">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="f0290-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f0290-120">En la barra de navegación izquierda, haga clic en **Federación y acceso externo** y, luego, en **Configuración perimetral de acceso**.</span><span class="sxs-lookup"><span data-stu-id="f0290-120">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="f0290-121">En la página **Configuración perimetral de acceso** , haga clic en **Global**, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="f0290-121">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="f0290-122">En **Editar configuración perimetral de acceso**, realice una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="f0290-122">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="f0290-123">Para habilitar el acceso de usuarios remotos para su organización, active la casilla de verificación **Habilitar el acceso de usuarios remotos** .</span><span class="sxs-lookup"><span data-stu-id="f0290-123">To enable remote user access for your organization, select the **Enable remote user access** check box.</span></span>
    
      - <span data-ttu-id="f0290-124">Para deshabilitar el acceso de usuarios remotos para su organización, desactive la casilla de verificación **Habilitar el acceso de usuarios remotos** .</span><span class="sxs-lookup"><span data-stu-id="f0290-124">To disable remote user access for your organization, clear the **Enable remote user access** check box.</span></span>

6.  <span data-ttu-id="f0290-125">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="f0290-125">Click **Commit**.</span></span>

<span data-ttu-id="f0290-126">Para habilitar los usuarios remotos iniciar sesión en los servidores que ejecutan Skype para Business Server, también debe configurar al menos una directiva de acceso externo para admitir el acceso de usuarios remotos.</span><span class="sxs-lookup"><span data-stu-id="f0290-126">To enable remote users to sign in to your servers running Skype for Business Server, you must also configure at least one external access policy to support remote user access.</span></span> <span data-ttu-id="f0290-127">Para obtener información detallada, vea [Configurar directivas para controlar el acceso de usuarios remotos en Skype para Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="f0290-127">For details, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f0290-128">Habilitar o deshabilitar el acceso de usuarios remotos mediante el uso de cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f0290-128">Enabling or disabling remote user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="f0290-129">Acceso de usuarios remotos puede administrarse mediante el uso de Windows PowerShell y el cmdlet Set-CsAccessEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="f0290-129">Remote user access can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="f0290-130">Este cmdlet se puede ejecutar desde la Skype para Shell de administración de Business Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0290-130">This cmdlet can be run either from the Skype for Business Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-remote-user-access"></a><span data-ttu-id="f0290-131">Para habilitar el acceso de usuarios remotos</span><span class="sxs-lookup"><span data-stu-id="f0290-131">To enable remote user access</span></span>

  - <span data-ttu-id="f0290-132">Para habilitar el acceso de usuarios remotos, establezca el valor de la propiedad **AllowOutsideUsers** en True ($True):</span><span class="sxs-lookup"><span data-stu-id="f0290-132">To enable remote user access, set the value of the **AllowOutsideUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## <a name="to-disable-remote-user-access"></a><span data-ttu-id="f0290-133">Para deshabilitar el acceso de usuarios remotos</span><span class="sxs-lookup"><span data-stu-id="f0290-133">To disable remote user access</span></span>

  - <span data-ttu-id="f0290-134">Para deshabilitar el acceso de usuarios remotos, establezca el valor de la propiedad **AllowOutsideUsers** en False ($False):</span><span class="sxs-lookup"><span data-stu-id="f0290-134">To disable remote user access, set the value of the **AllowOutsideUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False


