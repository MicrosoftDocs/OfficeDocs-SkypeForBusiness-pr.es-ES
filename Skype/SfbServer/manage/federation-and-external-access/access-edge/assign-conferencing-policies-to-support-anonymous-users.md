---
title: Asignar directivas de conferencia para admitir usuarios anónimos
ms.reviewer: ''
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
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
description: Para controlar quién puede invitar a usuarios anónimos, se debe configurar una directiva de conferencias que admita la participación de usuarios anónimos, y aplicar dicha directiva a usuarios específicos.
ms.openlocfilehash: 57d100569722cbe89811d15eb9fbe04e5d375711
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817460"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-skype-for-business-server"></a><span data-ttu-id="b8eae-103">Asignar directivas de conferencia para admitir usuarios anónimos en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="b8eae-103">Assign conferencing policies to support anonymous users in Skype for Business Server</span></span> 


<span data-ttu-id="b8eae-104">De forma predeterminada, ningún usuario tiene permitido invitar a usuarios anónimos a participar en una reunión.</span><span class="sxs-lookup"><span data-stu-id="b8eae-104">By default, all users are prevented from inviting anonymous users to participate in a meeting.</span></span> <span data-ttu-id="b8eae-105">Para controlar quién puede invitar a usuarios anónimos, se debe configurar una directiva de conferencias que admita la participación de usuarios anónimos, y aplicar dicha directiva a usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="b8eae-105">You control who can invite anonymous users by configuring a conferencing policy to support anonymous users, and applying that conferencing policy to specific users.</span></span> <span data-ttu-id="b8eae-106">Para obtener más información sobre cómo configurar directivas de conferencia para admitir usuarios anónimos, consulte Crear directivas de conferencia en Skype Empresarial [Server](../../conferencing/create-policies.md) y administrar la federación y el acceso externo a [Skype Empresarial Server.](../managing-federation-and-external-access.md)</span><span class="sxs-lookup"><span data-stu-id="b8eae-106">For details about how to configure a conferencing policies to support anonymous users, see [Create conferencing policies in Skype for Business Server](../../conferencing/create-policies.md) and [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span>

<span data-ttu-id="b8eae-107">Use el procedimiento descrito en esta sección para aplicar una directiva de conferencia que ya ha creado a uno o varios usuarios o grupos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="b8eae-107">Use the procedure in this section to apply a conferencing policy that you have already created to one or more users or user groups.</span></span>

> [!NOTE]  
> <span data-ttu-id="b8eae-108">Además de configurar y aplicar una directiva para permitir a los usuarios invitar a usuarios anónimos, también debe habilitar la compatibilidad con usuarios anónimos para su organización.</span><span class="sxs-lookup"><span data-stu-id="b8eae-108">In addition to configuring and applying a policy to enable users to invite anonymous users, you must also enable support for anonymous users for your organization.</span></span> <span data-ttu-id="b8eae-109">Para obtener más información, [consulte Configurar directivas para controlar el acceso de usuarios públicos en Skype Empresarial Server.](../external-access-policies/configure-policies-to-control-public-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="b8eae-109">For details, see [Configure policies to control public user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>


## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a><span data-ttu-id="b8eae-110">Para configurar una directiva de usuario para la participación anónima en reuniones</span><span class="sxs-lookup"><span data-stu-id="b8eae-110">To configure a user policy for anonymous participation in meetings</span></span>

1.  <span data-ttu-id="b8eae-111">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="b8eae-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b8eae-112">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="b8eae-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="b8eae-113">En la barra de navegación izquierda, haga clic en **Conferencia** y, a continuación, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="b8eae-113">In the left navigation bar, click **Conferencing**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="b8eae-114">Para crear una directiva de usuario nueva, haga clic en **Nuevo** y, a continuación, en **Directiva de usuario**.</span><span class="sxs-lookup"><span data-stu-id="b8eae-114">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="b8eae-115">Cree un nombre  único en el campo Nombre que indique lo que cubre la directiva de usuario (por ejemplo, **EnableAnonymous** para una directiva de usuario que permite las comunicaciones con usuarios anónimos).</span><span class="sxs-lookup"><span data-stu-id="b8eae-115">Create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableAnonymous** for a user policy that enables communications with anonymous users).</span></span>
    
    2.  <span data-ttu-id="b8eae-116">Para configurar una directiva de usuario existente, haga clic en la directiva correspondiente que aparece en la tabla, haga clic en Editar **y,** a continuación, haga clic **en Mostrar detalles.**</span><span class="sxs-lookup"><span data-stu-id="b8eae-116">To configure an existing user policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

4.  <span data-ttu-id="b8eae-117">En el **cuadro de diálogo Directivas de** conferencia, active la casilla Permitir a los **participantes invitar a usuarios anónimos.**</span><span class="sxs-lookup"><span data-stu-id="b8eae-117">In the **Conferencing Policies** dialog box, select the **Allow participants to invite anonymous users** check box.</span></span>

5.  <span data-ttu-id="b8eae-118">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="b8eae-118">Click **Commit**.</span></span>

6.  <span data-ttu-id="b8eae-119">En la barra de navegación izquierda, haga clic en **Usuarios** y busque la cuenta de usuario que desee configurar.</span><span class="sxs-lookup"><span data-stu-id="b8eae-119">In the left navigation bar, click **Users**, search on the user account that you want to configure.</span></span>

7.  <span data-ttu-id="b8eae-120">En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en  **Editar** y, a continuación, en  **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="b8eae-120">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

8.  <span data-ttu-id="b8eae-121">En **Editar usuario de Skype Empresarial Server** en la directiva de conferencia, seleccione la directiva de usuario con la configuración de acceso de usuario anónimo que desea aplicar a este usuario. </span><span class="sxs-lookup"><span data-stu-id="b8eae-121">In **Edit Skype for Business Server User** under **Conferencing policy**, select the user policy with the anonymous user access configuration that you want to apply to this user.</span></span>  

    > [!NOTE]  
    > <span data-ttu-id="b8eae-122">La <STRONG> &lt; configuración &gt; </STRONG> automática aplica la configuración predeterminada de instalación del servidor y el servidor la aplica automáticamente.</span><span class="sxs-lookup"><span data-stu-id="b8eae-122">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings and are applied automatically by the server.</span></span>


<span data-ttu-id="b8eae-123">Para permitir a los usuarios invitar a usuarios anónimos a conferencias, también tiene que habilitar la compatibilidad con usuarios anónimos en la organización.</span><span class="sxs-lookup"><span data-stu-id="b8eae-123">To enable users to invite anonymous users to conferences, you must also enable support for anonymous users in your organization.</span></span> <span data-ttu-id="b8eae-124">Para obtener más información, [consulte Configurar directivas para controlar el acceso de usuarios públicos en Skype Empresarial Server.](../external-access-policies/configure-policies-to-control-public-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="b8eae-124">For details, see [Configure policies to control public user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>

