---
title: Habilitar o deshabilitar el acceso de usuarios anónimos
ms.reviewer: ''
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
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
description: ''
ms.openlocfilehash: cc0d779e2728fd2a82547b52bda57c05c7a983a3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006005"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a><span data-ttu-id="0c2e1-102">Habilitar o deshabilitar el acceso de usuarios anónimos en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="0c2e1-102">Enable or disable anonymous user access in Skype for Business Server</span></span>

<span data-ttu-id="0c2e1-103">Los usuarios anónimos son usuarios que no tienen una cuenta de usuario en los servicios de dominio de Active Directory de la organización o en un dominio federado admitido, pero que pueden ser invitados a participar remotamente en una conferencia local.</span><span class="sxs-lookup"><span data-stu-id="0c2e1-103">Anonymous users are users who do not have a user account in your organization's Active Directory Domain Services or in a supported federated domain, but can be invited to participate remotely in an on-premises conference.</span></span> <span data-ttu-id="0c2e1-104">Al permitir la participación anónima en las reuniones, se habilitan los usuarios anónimos (es decir, los usuarios cuya identidad se comprueba sólo a través de la reunión o la clave de conferencia) para unirse a las reuniones.</span><span class="sxs-lookup"><span data-stu-id="0c2e1-104">By allowing anonymous participation in meetings you enable anonymous users (that is, users whose identity is verified through the meeting or conference key only) to join meetings.</span></span> <span data-ttu-id="0c2e1-105">Para permitir la participación anónima, es necesario habilitarla para su organización.</span><span class="sxs-lookup"><span data-stu-id="0c2e1-105">Allowing anonymous participation requires enabling it for your organization.</span></span>

<span data-ttu-id="0c2e1-106">Si más adelante desea evitar temporalmente o permanentemente el acceso de usuarios anónimos, puede deshabilitarlo para su organización.</span><span class="sxs-lookup"><span data-stu-id="0c2e1-106">If you later want to temporarily or permanently prevent access by anonymous users, you can disable it for your organization.</span></span> <span data-ttu-id="0c2e1-107">Use el procedimiento descrito en esta sección para habilitar o deshabilitar el acceso de usuarios anónimos para su organización.</span><span class="sxs-lookup"><span data-stu-id="0c2e1-107">Use the procedure in this section to enable or disable anonymous user access for your organization.</span></span>

> [!NOTE]  
> <span data-ttu-id="0c2e1-108">Al habilitar el acceso de usuarios anónimos para su organización, solo está especificando que los servidores que ejecutan el servicio perimetral de acceso admitan el acceso por parte de usuarios anónimos.</span><span class="sxs-lookup"><span data-stu-id="0c2e1-108">By enabling anonymous user access for your organization you are only specifying that your servers running the Access Edge service support access by anonymous users.</span></span> <span data-ttu-id="0c2e1-109">Los usuarios anónimos no pueden participar en ninguna reunión de su organización hasta que también configure al menos una directiva de conferencia y la aplique a uno o varios usuarios o grupos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="0c2e1-109">Anonymous users cannot participate in any meetings in your organization until you also configure at least one conferencing policy and apply it to one or more users or user groups.</span></span> <span data-ttu-id="0c2e1-110">Los únicos usuarios que pueden invitar a usuarios anónimos a las reuniones son aquellos a los que se les asigna una directiva de conferencia configurada para admitir usuarios anónimos.</span><span class="sxs-lookup"><span data-stu-id="0c2e1-110">The only users that can invite anonymous users to meetings are those users that are assigned a conferencing policy that is configured to support anonymous users.</span></span> <span data-ttu-id="0c2e1-111">Para obtener más información sobre cómo configurar directivas de conferencia para admitir la invitación a usuarios anónimos, consulte [Manage Conferencing Policies](../../conferencing/conferencing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="0c2e1-111">For details about configuring conferencing policies to support inviting anonymous users, see [Manage conferencing policies](../../conferencing/conferencing-policies.md).</span></span>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a><span data-ttu-id="0c2e1-112">Para habilitar o deshabilitar el acceso de usuarios anónimos para la organización</span><span class="sxs-lookup"><span data-stu-id="0c2e1-112">To enable or disable anonymous user access for your organization</span></span>

1.  <span data-ttu-id="0c2e1-113">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="0c2e1-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0c2e1-114">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="0c2e1-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="0c2e1-115">En el barra de navegación izquierda, haga clic en **Acceso para usuarios externos** y, a continuación, en **Configuración perimetral de acceso**.</span><span class="sxs-lookup"><span data-stu-id="0c2e1-115">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="0c2e1-116">En la página **Configuración perimetral de acceso**, haga clic en **Global**, en **Editar** y, a continuación en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="0c2e1-116">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="0c2e1-117">En **Editar configuración perimetral de acceso**, lleve a cabo uno de los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="0c2e1-117">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="0c2e1-118">Para habilitar el acceso de usuarios anónimos para su organización, active la casilla de verificación **Habilitar comunicaciones con usuarios anónimos** .</span><span class="sxs-lookup"><span data-stu-id="0c2e1-118">To enable anonymous user access for your organization, select the **Enable communications with anonymous users** check box.</span></span>
    
      - <span data-ttu-id="0c2e1-119">Para deshabilitar el acceso de usuarios anónimos para la organización, desactive la casilla de verificación **Habilitar comunicaciones con usuarios anónimos** .</span><span class="sxs-lookup"><span data-stu-id="0c2e1-119">To disable anonymous user access for your organization, clear the **Enable communications with anonymous users** check box.</span></span>

6.  <span data-ttu-id="0c2e1-120">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="0c2e1-120">Click **Commit**.</span></span>


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="0c2e1-121">Habilitación o deshabilitación del acceso de usuarios anónimos mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c2e1-121">Enabling or disabling anonymous user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="0c2e1-122">Puede administrar el acceso de usuarios anónimos mediante Windows PowerShell y el cmdlet **set-CsAccessEdgeConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="0c2e1-122">You can manage anonymous user access by using Windows PowerShell and the **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="0c2e1-123">Puede ejecutar este cmdlet desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c2e1-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-anonymous-user-access"></a><span data-ttu-id="0c2e1-124">Para habilitar el acceso de usuarios anónimos</span><span class="sxs-lookup"><span data-stu-id="0c2e1-124">To enable anonymous user access</span></span>

  - <span data-ttu-id="0c2e1-125">Para habilitar el acceso de usuarios anónimos, establezca el valor de la propiedad **AllowAnonymousUsers** en True ($true):</span><span class="sxs-lookup"><span data-stu-id="0c2e1-125">To enable anonymous user access, set the value of the **AllowAnonymousUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a><span data-ttu-id="0c2e1-126">Para deshabilitar el acceso de usuarios anónimos</span><span class="sxs-lookup"><span data-stu-id="0c2e1-126">To disable anonymous user access</span></span>

  - <span data-ttu-id="0c2e1-127">Para deshabilitar el acceso de usuarios anónimos, establezca el valor de la propiedad **AllowAnonymousUsers** en False ($false):</span><span class="sxs-lookup"><span data-stu-id="0c2e1-127">To disable anonymous user access, set the value of the **AllowAnonymousUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a><span data-ttu-id="0c2e1-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c2e1-128">See Also</span></span>

[<span data-ttu-id="0c2e1-129">Set-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="0c2e1-129">Set-CsClientPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy?view=skype-ps)  
  
