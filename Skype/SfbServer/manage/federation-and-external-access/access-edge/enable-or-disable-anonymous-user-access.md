---
title: Habilitar y deshabilitar el acceso anónimo de usuarios
ms.reviewer: ''
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: 6bc424dc0b26f794d45c5a601b468bbb78c92ef6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919454"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a><span data-ttu-id="12a52-102">Habilitar o deshabilitar el acceso de usuarios anónimos en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="12a52-102">Enable or disable anonymous user access in Skype for Business Server</span></span>

<span data-ttu-id="12a52-103">Los usuarios anónimos son usuarios que no tienen una cuenta de usuario en los servicios de dominio de Active Directory de su organización o en un dominio federado compatible, pero pueden ser invitados a participar de forma remota en una conferencia local.</span><span class="sxs-lookup"><span data-stu-id="12a52-103">Anonymous users are users who do not have a user account in your organization's Active Directory Domain Services or in a supported federated domain, but can be invited to participate remotely in an on-premises conference.</span></span> <span data-ttu-id="12a52-104">Permitiendo la participación remota en reuniones permite a los usuarios anónimos (es decir, los usuarios cuya identidad se comprobará mediante la clave de conferencia o reunión sólo) para participar en reuniones.</span><span class="sxs-lookup"><span data-stu-id="12a52-104">By allowing anonymous participation in meetings you enable anonymous users (that is, users whose identity is verified through the meeting or conference key only) to join meetings.</span></span> <span data-ttu-id="12a52-105">Lo que permite la participación anónima requiere habilitar para la organización.</span><span class="sxs-lookup"><span data-stu-id="12a52-105">Allowing anonymous participation requires enabling it for your organization.</span></span>

<span data-ttu-id="12a52-106">Si más adelante desea impedir el acceso a los usuarios anónimos temporal o permanente, se puede deshabilitar para su organización.</span><span class="sxs-lookup"><span data-stu-id="12a52-106">If you later want to temporarily or permanently prevent access by anonymous users, you can disable it for your organization.</span></span> <span data-ttu-id="12a52-107">Use el procedimiento de esta sección para habilitar o deshabilitar el acceso de usuario anónimo para la organización.</span><span class="sxs-lookup"><span data-stu-id="12a52-107">Use the procedure in this section to enable or disable anonymous user access for your organization.</span></span>

> [!NOTE]  
> <span data-ttu-id="12a52-108">Al habilitar el acceso de usuarios anónimos para la organización sólo se especifica que los servidores que ejecutan el servicio de servidor perimetral de acceso admitan el acceso de los usuarios anónimos.</span><span class="sxs-lookup"><span data-stu-id="12a52-108">By enabling anonymous user access for your organization you are only specifying that your servers running the Access Edge service support access by anonymous users.</span></span> <span data-ttu-id="12a52-109">Los usuarios anónimos no pueden participar en las reuniones de la organización hasta que también configura al menos una directiva de conferencia y aplica a uno o varios usuarios o grupos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="12a52-109">Anonymous users cannot participate in any meetings in your organization until you also configure at least one conferencing policy and apply it to one or more users or user groups.</span></span> <span data-ttu-id="12a52-110">Los únicos usuarios que pueden invitar a los usuarios anónimos a las reuniones son aquellos usuarios que están asignados a una directiva de conferencia que está configurada para admitir usuarios anónimos.</span><span class="sxs-lookup"><span data-stu-id="12a52-110">The only users that can invite anonymous users to meetings are those users that are assigned a conferencing policy that is configured to support anonymous users.</span></span> <span data-ttu-id="12a52-111">Para obtener información detallada acerca de cómo configurar las directivas de conferencia para admitir inviten a usuarios anónimos, vea [administrar las directivas de conferencia](../../conferencing/conferencing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="12a52-111">For details about configuring conferencing policies to support inviting anonymous users, see [Manage conferencing policies](../../conferencing/conferencing-policies.md).</span></span>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a><span data-ttu-id="12a52-112">Para habilitar o deshabilitar el acceso de usuarios anónimos para la organización</span><span class="sxs-lookup"><span data-stu-id="12a52-112">To enable or disable anonymous user access for your organization</span></span>

1.  <span data-ttu-id="12a52-113">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="12a52-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="12a52-114">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="12a52-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="12a52-115">En la barra de navegación izquierda, haga clic en **Acceso de usuarios externos**y, a continuación, haga clic en **Configuración perimetral de acceso**.</span><span class="sxs-lookup"><span data-stu-id="12a52-115">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="12a52-116">En la página **Configuración perimetral de acceso** , haga clic en **Global**, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="12a52-116">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="12a52-117">En **Editar configuración perimetral de acceso**, realice una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="12a52-117">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="12a52-118">Para habilitar el acceso de usuario anónimo para la organización, active la casilla de verificación **Habilitar las comunicaciones con los usuarios anónimos** .</span><span class="sxs-lookup"><span data-stu-id="12a52-118">To enable anonymous user access for your organization, select the **Enable communications with anonymous users** check box.</span></span>
    
      - <span data-ttu-id="12a52-119">Para deshabilitar el acceso de usuarios anónimos para su organización, desactive la casilla de verificación **Habilitar las comunicaciones con los usuarios anónimos** .</span><span class="sxs-lookup"><span data-stu-id="12a52-119">To disable anonymous user access for your organization, clear the **Enable communications with anonymous users** check box.</span></span>

6.  <span data-ttu-id="12a52-120">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="12a52-120">Click **Commit**.</span></span>


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="12a52-121">Habilitar o deshabilitar el acceso de usuarios anónimos mediante el uso de cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="12a52-121">Enabling or disabling anonymous user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="12a52-122">Puede administrar el acceso de usuarios anónimos mediante el uso de Windows PowerShell y el cmdlet **Set-CsAccessEdgeConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="12a52-122">You can manage anonymous user access by using Windows PowerShell and the **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="12a52-123">Se puede ejecutar este cmdlet, ya sea desde el Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="12a52-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-anonymous-user-access"></a><span data-ttu-id="12a52-124">Para habilitar el acceso de usuarios anónimos</span><span class="sxs-lookup"><span data-stu-id="12a52-124">To enable anonymous user access</span></span>

  - <span data-ttu-id="12a52-125">Para habilitar el acceso de usuarios anónimos, establezca el valor de la propiedad **AllowAnonymousUsers** en True ($True):</span><span class="sxs-lookup"><span data-stu-id="12a52-125">To enable anonymous user access, set the value of the **AllowAnonymousUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a><span data-ttu-id="12a52-126">Para deshabilitar el acceso de usuarios anónimos</span><span class="sxs-lookup"><span data-stu-id="12a52-126">To disable anonymous user access</span></span>

  - <span data-ttu-id="12a52-127">Para deshabilitar el acceso de usuarios anónimos, establezca el valor de la propiedad **AllowAnonymousUsers** en False ($False):</span><span class="sxs-lookup"><span data-stu-id="12a52-127">To disable anonymous user access, set the value of the **AllowAnonymousUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a><span data-ttu-id="12a52-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="12a52-128">See Also</span></span>

[<span data-ttu-id="12a52-129">Set-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="12a52-129">Set-CsClientPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy?view=skype-ps)  
  
