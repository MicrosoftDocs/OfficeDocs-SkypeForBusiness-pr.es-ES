---
title: Bloquear el acceso a SharePoint para usuarios específicos
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: Nigolc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Obtener información sobre cómo bloquear el acceso a SharePoint para usuarios específicos
ms.openlocfilehash: 959de8c06e26d2d12c3a3698375b11d373392447
ms.sourcegitcommit: b37632ffa22e3a6045b476c95d46889e9193a15b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "47956041"
---
# <a name="block-access-to-sharepoint-for-specific-users"></a><span data-ttu-id="66674-103">Bloquear el acceso a SharePoint para usuarios específicos</span><span class="sxs-lookup"><span data-stu-id="66674-103">Block access to SharePoint for specific users</span></span>

<span data-ttu-id="66674-104">Aplicar cualquier directiva de acceso condicional en SharePoint Online (SPO) también se aplica a teams.</span><span class="sxs-lookup"><span data-stu-id="66674-104">Applying any Conditional Access (CA) policy on SharePoint Online (SPO) is also applied to Teams.</span></span> <span data-ttu-id="66674-105">Sin embargo, algunas organizaciones desean bloquear el acceso a los archivos de SharePoint (cargar, descargar, ver, editar, crear) y permitir que sus empleados usen equipos de escritorio, dispositivos móviles y clientes Web en dispositivos no administrados.</span><span class="sxs-lookup"><span data-stu-id="66674-105">However, some organizations want to block access to SharePoint files (upload, download, view, edit, create) yet allow their employees to use Teams desktop, mobile, and web clients on unmanaged devices.</span></span> <span data-ttu-id="66674-106">En las reglas de directiva de la entidad emisora, el bloqueo de SPO también provocaría el bloqueo de Teams.</span><span class="sxs-lookup"><span data-stu-id="66674-106">Under the CA policy rules, blocking SPO would lead to blocking Teams as well.</span></span> <span data-ttu-id="66674-107">En este artículo se explica cómo puede eludir esta limitación y permitir que los empleados sigan usando Teams mientras bloquean completamente el acceso a los archivos almacenados en SPO.</span><span class="sxs-lookup"><span data-stu-id="66674-107">This article explains how you can work around this limitation and allow your employees to continue using Teams while completely blocking access to files stored in SPO.</span></span>

> [!Note]
> <span data-ttu-id="66674-108">Bloquear o limitar el acceso a dispositivos no administrados depende de las directivas de acceso condicional de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="66674-108">Blocking or limiting access on unmanaged devices relies on Azure AD conditional access policies.</span></span> <span data-ttu-id="66674-109">Más información sobre las [licencias de Azure ad](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="66674-109">Learn about [Azure AD licensing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span> <span data-ttu-id="66674-110">Para obtener información general sobre el acceso condicional en Azure AD, consulte [acceso condicional en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span><span class="sxs-lookup"><span data-stu-id="66674-110">For an overview of conditional access in Azure AD, see [Conditional access in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span> <span data-ttu-id="66674-111">Para obtener información sobre las directivas de acceso de SharePoint recomendadas, consulte [recomendaciones de directiva para proteger los sitios y archivos de SharePoint](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span><span class="sxs-lookup"><span data-stu-id="66674-111">For info about recommended SharePoint access policies, see [Policy recommendations for securing SharePoint sites and files](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span> <span data-ttu-id="66674-112">Si limita el acceso a los dispositivos no administrados, los usuarios de los dispositivos administrados deben usar una de las [combinaciones de sistema operativo y explorador compatibles](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#client-apps-condition), o bien también tendrán acceso limitado.</span><span class="sxs-lookup"><span data-stu-id="66674-112">If you limit access on unmanaged devices, users on managed devices must use one of the [supported OS and browser combinations](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#client-apps-condition), or they will also have limited access.</span></span>

<span data-ttu-id="66674-113">Puede bloquear o limitar el acceso a:</span><span class="sxs-lookup"><span data-stu-id="66674-113">You can block or limit access for:</span></span>

- <span data-ttu-id="66674-114">Usuarios de la organización o solo algunos usuarios o grupos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="66674-114">Users in the organization or only some users or security groups.</span></span>

- <span data-ttu-id="66674-115">Todos los sitios de la organización o solo algunos sitios.</span><span class="sxs-lookup"><span data-stu-id="66674-115">All sites in the organization or only some sites.</span></span>

<span data-ttu-id="66674-116">Cuando se bloquea el acceso, los usuarios verán un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="66674-116">When access is blocked, users will see an error message.</span></span> <span data-ttu-id="66674-117">Bloquear el acceso ayuda a proporcionar seguridad y protege los datos seguros.</span><span class="sxs-lookup"><span data-stu-id="66674-117">Blocking access helps provide security and protects secure data.</span></span> <span data-ttu-id="66674-118">Cuando se bloquea el acceso, los usuarios verán un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="66674-118">When access is blocked, users will see an error message.</span></span>

1. <span data-ttu-id="66674-119">Abra el [centro de administración](https://admin.microsoft.com/sharepoint?page=accessControl&modern=true)de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="66674-119">Open the SharePoint [Admin Center](https://admin.microsoft.com/sharepoint?page=accessControl&modern=true).</span></span>

2. <span data-ttu-id="66674-120">Expanda directivas de acceso de **directivas**  >  **Access Policies**.</span><span class="sxs-lookup"><span data-stu-id="66674-120">Expand **Policies** > **Access Policies**.</span></span>

3. <span data-ttu-id="66674-121">En la sección **dispositivos no gestionados** , seleccione **Bloquear acceso** y seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="66674-121">In the **Unmanaged Devices** section,  select **Block Access** and select **Save**.</span></span>

   ![la sección de dispositivos no administrados para las directivas](media/no-sharepoint-access1.png)

4. <span data-ttu-id="66674-123">Abra el portal de [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) y vaya a **directivas de acceso condicional**.</span><span class="sxs-lookup"><span data-stu-id="66674-123">Open the [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) portal and navigate to **Conditional Access Policies**.</span></span>

    <span data-ttu-id="66674-124">Verá que SharePoint ha creado una nueva Directiva similar a este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="66674-124">You'll see a new policy has been created by SharePoint that's similar to this example:</span></span>

    ![una nueva directiva que se denomina usar restricciones de aplicación de acceso para el explorador](media/no-sharepoint-access2.png)

5. <span data-ttu-id="66674-126">Actualice la Directiva para destinar solo a usuarios específicos o a un grupo.</span><span class="sxs-lookup"><span data-stu-id="66674-126">Update the policy to target only specific users or a group.</span></span>

    ![el centro de administración de SharePoint con la sección seleccionar usuario resaltada.](media/no-sharepoint-access2b.png)

  > [!Note]
> <span data-ttu-id="66674-128">Al configurar esta Directiva, se cortará el acceso al portal de administración de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="66674-128">Setting this policy will cut your access to the SharePoint admin portal.</span></span> <span data-ttu-id="66674-129">Le recomendamos que configure la Directiva de exclusión y seleccione los administradores globales y de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="66674-129">We recommended that you configure the exclusion policy and select the Global and SharePoint admins.</span></span>

6. <span data-ttu-id="66674-130">Comprobar que solo se selecciona SharePoint Online como aplicación de nube de destino</span><span class="sxs-lookup"><span data-stu-id="66674-130">Verify that only SharePoint Online is selected as targeted Cloud App</span></span>

    ![SharePoint Online está seleccionado como la aplicación de destino.](media/no-sharepoint-access3.png)

7. <span data-ttu-id="66674-132">Actualice **las condiciones** para incluir también los clientes de escritorio.</span><span class="sxs-lookup"><span data-stu-id="66674-132">Update **Conditions** to include desktop clients, as well.</span></span>

    ![aplicaciones móviles y de escritorio resaltadas.](media/no-sharepoint-access4.png)

8. <span data-ttu-id="66674-134">Asegurarse de que **conceder acceso** está habilitado</span><span class="sxs-lookup"><span data-stu-id="66674-134">Make sure that **Grant access** is enabled</span></span>

    ![conceder acceso está habilitado.](media/no-sharepoint-access5.png)

9. <span data-ttu-id="66674-136">Asegúrese de que está habilitada la opción **usar restricciones de aplicación** .</span><span class="sxs-lookup"><span data-stu-id="66674-136">Make sure **Use app enforced restrictions** is enabled.</span></span>

10. <span data-ttu-id="66674-137">Habilite la Directiva y seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="66674-137">Enable your policy and select **Save**.</span></span>

    ![Está habilitada la aplicación de restricciones obligatorias.](media/no-sharepoint-access6.png)

<span data-ttu-id="66674-139">Para probar su Directiva, debe cerrar sesión en cualquier cliente, como la aplicación de escritorio de Teams o el cliente de sincronización de OneDrive, e iniciar sesión de nuevo para ver cómo funciona la Directiva.</span><span class="sxs-lookup"><span data-stu-id="66674-139">To test your policy, you need to sign out from any client such as the Teams desktop app or the OneDrive sync client and sign in again to see the policy working.</span></span> <span data-ttu-id="66674-140">Si su acceso ha sido bloqueado, verá un mensaje en teams que indica que el elemento podría no existir.</span><span class="sxs-lookup"><span data-stu-id="66674-140">If your access has been blocked, you'll see a message in Teams that states the item might not exist.</span></span>

 ![El mensaje de elemento no encontrado.](media/access-denied-sharepoint.png)

<span data-ttu-id="66674-142">En SharePoint, recibirá un mensaje de acceso denegado.</span><span class="sxs-lookup"><span data-stu-id="66674-142">In Sharepoint, you'll receive an access denied message.</span></span> 

![El mensaje de acceso denegado.](media/blocked-access-warning.png)

## <a name="related-topics"></a><span data-ttu-id="66674-144">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="66674-144">Related topics</span></span>

[<span data-ttu-id="66674-145">Controlar el acceso a los dispositivos no administrados en SharePoint</span><span class="sxs-lookup"><span data-stu-id="66674-145">Control access for unmanaged devices in SharePoint</span></span>](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)
