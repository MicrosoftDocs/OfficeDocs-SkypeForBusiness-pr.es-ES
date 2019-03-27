---
title: Asignar directivas de conferencia para admitir usuarios anónimos
ms.reviewer: ''
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Puede controlar quién puede invitar a usuarios anónimos mediante la configuración de una directiva de conferencia para admitir usuarios anónimos y aplicar esa directiva de conferencia a usuarios específicos.
ms.openlocfilehash: 62ff84b19fadbeaf0f26fa3e5869026254d28d1f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881130"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-skype-for-business-server"></a><span data-ttu-id="9559e-103">Asignar directivas de conferencia para admitir usuarios anónimos en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="9559e-103">Assign conferencing policies to support anonymous users in Skype for Business Server</span></span> 


<span data-ttu-id="9559e-104">De forma predeterminada, todos los usuarios no podrán invitar a usuarios anónimos a participar en una reunión.</span><span class="sxs-lookup"><span data-stu-id="9559e-104">By default, all users are prevented from inviting anonymous users to participate in a meeting.</span></span> <span data-ttu-id="9559e-105">Puede controlar quién puede invitar a usuarios anónimos mediante la configuración de una directiva de conferencia para admitir usuarios anónimos y aplicar esa directiva de conferencia a usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="9559e-105">You control who can invite anonymous users by configuring a conferencing policy to support anonymous users, and applying that conferencing policy to specific users.</span></span> <span data-ttu-id="9559e-106">Para obtener información detallada sobre cómo configurar las directivas de una conferencia para admitir usuarios anónimos, vea [crear directivas de conferencia en Skype para Business Server](../../conferencing/create-policies.md) y [Managing federación y el acceso externo a Skype para Business Server](../managing-federation-and-external-access.md).</span><span class="sxs-lookup"><span data-stu-id="9559e-106">For details about how to configure a conferencing policies to support anonymous users, see [Create conferencing policies in Skype for Business Server](../../conferencing/create-policies.md) and [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span>

<span data-ttu-id="9559e-107">Use el procedimiento de esta sección para aplicar una directiva de conferencia que ya haya creado a uno o más usuarios o grupos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="9559e-107">Use the procedure in this section to apply a conferencing policy that you have already created to one or more users or user groups.</span></span>

> [!NOTE]  
> <span data-ttu-id="9559e-108">Además de configurar y aplicar una directiva para permitir que los usuarios invitar a usuarios anónimos, también debe habilitar la compatibilidad para los usuarios anónimos para su organización.</span><span class="sxs-lookup"><span data-stu-id="9559e-108">In addition to configuring and applying a policy to enable users to invite anonymous users, you must also enable support for anonymous users for your organization.</span></span> <span data-ttu-id="9559e-109">Para obtener información detallada, vea [Configurar directivas para controlar el acceso de usuarios públicos en Skype para Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="9559e-109">For details, see [Configure policies to control public user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>


## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a><span data-ttu-id="9559e-110">Para configurar una directiva de usuario para la participación anónima en las reuniones</span><span class="sxs-lookup"><span data-stu-id="9559e-110">To configure a user policy for anonymous participation in meetings</span></span>

1.  <span data-ttu-id="9559e-111">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="9559e-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9559e-112">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="9559e-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="9559e-113">En la barra de navegación izquierda, haga clic en **conferencia**y, a continuación, realice una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="9559e-113">In the left navigation bar, click **Conferencing**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="9559e-114">Para crear una nueva directiva de usuario, haga clic en **nuevo**y, a continuación, haga clic en **Directiva de usuario**.</span><span class="sxs-lookup"><span data-stu-id="9559e-114">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="9559e-115">Cree un nombre único en el campo **nombre** que indica lo que abarca la directiva de usuario (por ejemplo, **EnableAnonymous** para una directiva de usuario que habilita la comunicación con los usuarios anónimos).</span><span class="sxs-lookup"><span data-stu-id="9559e-115">Create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableAnonymous** for a user policy that enables communications with anonymous users).</span></span>
    
    2.  <span data-ttu-id="9559e-116">Para configurar una directiva de usuario existente, haga clic en la directiva correspondiente que aparece en la tabla, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="9559e-116">To configure an existing user policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

4.  <span data-ttu-id="9559e-117">En el cuadro de diálogo de **Las directivas de conferencia** , active la casilla de verificación **Permitir que los participantes invitar a usuarios anónimos** .</span><span class="sxs-lookup"><span data-stu-id="9559e-117">In the **Conferencing Policies** dialog box, select the **Allow participants to invite anonymous users** check box.</span></span>

5.  <span data-ttu-id="9559e-118">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="9559e-118">Click **Commit**.</span></span>

6.  <span data-ttu-id="9559e-119">En la barra de navegación izquierda, haga clic en **usuarios**, busque en la cuenta de usuario que desea configurar.</span><span class="sxs-lookup"><span data-stu-id="9559e-119">In the left navigation bar, click **Users**, search on the user account that you want to configure.</span></span>

7.  <span data-ttu-id="9559e-120">En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, luego, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="9559e-120">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

8.  <span data-ttu-id="9559e-121">En **Editar Skype para usuarios de empresa Server** en **Directiva de conferencia**, seleccione la directiva de usuario con la configuración de acceso de usuario anónimo que desee aplicar a este usuario.</span><span class="sxs-lookup"><span data-stu-id="9559e-121">In **Edit Skype for Business Server User** under **Conferencing policy**, select the user policy with the anonymous user access configuration that you want to apply to this user.</span></span>  

    > [!NOTE]  
    > <span data-ttu-id="9559e-122">La <STRONG> &lt;automática&gt; </STRONG> configuración aplicar la configuración predeterminada de la instalación de servidor y se aplican automáticamente por el servidor.</span><span class="sxs-lookup"><span data-stu-id="9559e-122">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings and are applied automatically by the server.</span></span>


<span data-ttu-id="9559e-123">Para permitir que los usuarios invitar a usuarios anónimos a las conferencias, también debe habilitar la compatibilidad con usuarios anónimos en su organización.</span><span class="sxs-lookup"><span data-stu-id="9559e-123">To enable users to invite anonymous users to conferences, you must also enable support for anonymous users in your organization.</span></span> <span data-ttu-id="9559e-124">Para obtener información detallada, vea [Configurar directivas para controlar el acceso de usuarios públicos en Skype para Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="9559e-124">For details, see [Configure policies to control public user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>

