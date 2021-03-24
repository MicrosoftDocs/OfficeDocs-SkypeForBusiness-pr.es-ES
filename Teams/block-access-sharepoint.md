---
title: Bloquear el acceso a SharePoint para determinados usuarios
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
description: Obtenga más información sobre cómo bloquear el acceso a SharePoint para determinados usuarios
ms.openlocfilehash: dce6581abe4fee70a6622817be7aefb0e3379e2f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092898"
---
# <a name="block-access-to-sharepoint-for-specific-users"></a><span data-ttu-id="f4682-103">Bloquear el acceso a SharePoint para determinados usuarios</span><span class="sxs-lookup"><span data-stu-id="f4682-103">Block access to SharePoint for specific users</span></span>

<span data-ttu-id="f4682-104">Aplicar cualquier directiva de acceso condicional (CA) en SharePoint en Microsoft 365 también se aplica a Teams.</span><span class="sxs-lookup"><span data-stu-id="f4682-104">Applying any Conditional Access (CA) policy on SharePoint in Microsoft 365 is also applied to Teams.</span></span> <span data-ttu-id="f4682-105">Sin embargo, algunas organizaciones desean bloquear el acceso a los archivos de SharePoint (cargar, descargar, ver, editar, crear), pero permiten a sus empleados utilizar los clientes de escritorio, móviles y web de Teams en dispositivos no administrados.</span><span class="sxs-lookup"><span data-stu-id="f4682-105">However, some organizations want to block access to SharePoint files (upload, download, view, edit, create) yet allow their employees to use Teams desktop, mobile, and web clients on unmanaged devices.</span></span> <span data-ttu-id="f4682-106">Bajo las reglas de la directiva de la CA, bloquear a SharePoint implicaría bloquear también a Teams.</span><span class="sxs-lookup"><span data-stu-id="f4682-106">Under the CA policy rules, blocking SharePoint would lead to blocking Teams as well.</span></span> <span data-ttu-id="f4682-107">Este artículo explica cómo puede solucionar esta limitación y permitir que sus empleados sigan utilizando Teams mientras bloquean completamente el acceso a los archivos almacenados en SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f4682-107">This article explains how you can work around this limitation and allow your employees to continue using Teams while completely blocking access to files stored in SharePoint.</span></span>

> [!Note]
> <span data-ttu-id="f4682-108">Bloquear o limitar el acceso a dispositivos no administrados se basa en directivas de acceso condicional de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f4682-108">Blocking or limiting access on unmanaged devices relies on Azure AD conditional access policies.</span></span> <span data-ttu-id="f4682-109">Obtenga información acerca de la [licencia Azure AD](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="f4682-109">Learn about [Azure AD licensing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span> <span data-ttu-id="f4682-110">Para una visión general del acceso condicional en Azure AD, vea [Acceso condicional en Azure Active Directory](/azure/active-directory/conditional-access/overview).</span><span class="sxs-lookup"><span data-stu-id="f4682-110">For an overview of conditional access in Azure AD, see [Conditional access in Azure Active Directory](/azure/active-directory/conditional-access/overview).</span></span> <span data-ttu-id="f4682-111">Para obtener información sobre las directivas de acceso de SharePoint Online recomendadas, vea [recomendaciones de directiva para proteger los archivos y los sitios de SharePoint](/microsoft-365/enterprise/sharepoint-file-access-policies).</span><span class="sxs-lookup"><span data-stu-id="f4682-111">For info about recommended SharePoint Online access policies, see [Policy recommendations for securing SharePoint sites and files](/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span> <span data-ttu-id="f4682-112">Si limita el acceso a dispositivos no administrados, los usuarios de los dispositivos administrados deben usar uno de las [combinaciones compatibles de SO y navegadores](/azure/active-directory/conditional-access/technical-reference#client-apps-condition) o bien también tendrán acceso limitado.</span><span class="sxs-lookup"><span data-stu-id="f4682-112">If you limit access on unmanaged devices, users on managed devices must use one of the [supported OS and browser combinations](/azure/active-directory/conditional-access/technical-reference#client-apps-condition), or they will also have limited access.</span></span>

<span data-ttu-id="f4682-113">Puede bloquear o limitar el acceso para:</span><span class="sxs-lookup"><span data-stu-id="f4682-113">You can block or limit access for:</span></span>

- <span data-ttu-id="f4682-114">Usuarios de la organización o solo algunos usuarios o grupos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f4682-114">Users in the organization or only some users or security groups.</span></span>

- <span data-ttu-id="f4682-115">Todos los sitios de la organización o solo algunos.</span><span class="sxs-lookup"><span data-stu-id="f4682-115">All sites in the organization or only some sites.</span></span>

<span data-ttu-id="f4682-116">Cuando se bloquea el acceso, los usuarios verán un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="f4682-116">When access is blocked, users will see an error message.</span></span> <span data-ttu-id="f4682-117">Bloquear el acceso ayuda a proporcionar seguridad y protege los datos seguros.</span><span class="sxs-lookup"><span data-stu-id="f4682-117">Blocking access helps provide security and protects secure data.</span></span> <span data-ttu-id="f4682-118">Cuando se bloquea el acceso, los usuarios verán un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="f4682-118">When access is blocked, users will see an error message.</span></span>

1. <span data-ttu-id="f4682-119">Abra el centro de administración de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f4682-119">Open the SharePoint Admin Center.</span></span>

2. <span data-ttu-id="f4682-120">Expanda **Directivas** > **Directivas de acceso**.</span><span class="sxs-lookup"><span data-stu-id="f4682-120">Expand **Policies** > **Access Policies**.</span></span>

3. <span data-ttu-id="f4682-121">En la sección **Dispositivos sin administrar**, seleccione **Bloquear el acceso** y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f4682-121">In the **Unmanaged Devices** section,  select **Block Access** and select **Save**.</span></span>

   ![la sección de dispositivos sin administrar para directivas](media/no-sharepoint-access1.png)

4. <span data-ttu-id="f4682-123">Abra el portal de [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) y vaya a **Directivas de acceso condicional**.</span><span class="sxs-lookup"><span data-stu-id="f4682-123">Open the [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) portal and navigate to **Conditional Access Policies**.</span></span>

    <span data-ttu-id="f4682-124">Verá que se ha creado una nueva directiva en SharePoint que es similar a la de este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f4682-124">You'll see a new policy has been created by SharePoint that's similar to this example:</span></span>

    ![una nueva directiva que se denomina usar las restricciones de acceso de la aplicación para el explorador](media/no-sharepoint-access2.png)

5. <span data-ttu-id="f4682-126">Actualizar la directiva para que se destine unicamente a usuarios específicos o a un grupo.</span><span class="sxs-lookup"><span data-stu-id="f4682-126">Update the policy to target only specific users or a group.</span></span>

    ![el centro de administración de SharePoint con la sección de selección de usuario resaltada.](media/no-sharepoint-access2b.png)

  > [!Note]
> <span data-ttu-id="f4682-128">Establecer esta directiva cortará su acceso al portal de administración de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f4682-128">Setting this policy will cut your access to the SharePoint admin portal.</span></span> <span data-ttu-id="f4682-129">Recomendamos que configure la directiva de exclusión y seleccione los administradores globales y de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f4682-129">We recommended that you configure the exclusion policy and select the Global and SharePoint admins.</span></span>

6. <span data-ttu-id="f4682-130">Comprobar que solo SharePoint está seleccionado como aplicación de nube de destino</span><span class="sxs-lookup"><span data-stu-id="f4682-130">Verify that only SharePoint is selected as targeted Cloud App</span></span>

    ![SharePoint se ha seleccionado como aplicación de destino.](media/no-sharepoint-access3.png)

7. <span data-ttu-id="f4682-132">Actualice las **Condiciones** para incluir también los clientes de escritorio.</span><span class="sxs-lookup"><span data-stu-id="f4682-132">Update **Conditions** to include desktop clients, as well.</span></span>

    ![aplicaciones móviles y de escritorio resaltadas.](media/no-sharepoint-access4.png)

8. <span data-ttu-id="f4682-134">Asegúrese de que **Conceder acceso** está habilitado</span><span class="sxs-lookup"><span data-stu-id="f4682-134">Make sure that **Grant access** is enabled</span></span>

    ![conceder acceso está habilitado.](media/no-sharepoint-access5.png)

9. <span data-ttu-id="f4682-136">Asegúrese de **Usar las restricciones que exige la aplicación** está habilitada.</span><span class="sxs-lookup"><span data-stu-id="f4682-136">Make sure **Use app enforced restrictions** is enabled.</span></span>

10. <span data-ttu-id="f4682-137">Habilite la directiva y seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f4682-137">Enable your policy and select **Save**.</span></span>

    ![Restricciones que exige la aplicación está habilitado.](media/no-sharepoint-access6.png)

<span data-ttu-id="f4682-139">Para probar su directiva, debe cerrar la sesión de cualquier cliente, como la aplicación de escritorio de Teams o el cliente de sincronización de OneDrive para la empresa e iniciar sesión de nuevo para ver cómo funciona la directiva.</span><span class="sxs-lookup"><span data-stu-id="f4682-139">To test your policy, you need to sign out from any client such as the Teams desktop app or the OneDrive for Business sync client and sign in again to see the policy working.</span></span> <span data-ttu-id="f4682-140">Si su acceso ha sido bloqueado, verá un mensaje en Teams que dice que el artículo podría no existir.</span><span class="sxs-lookup"><span data-stu-id="f4682-140">If your access has been blocked, you'll see a message in Teams that states the item might not exist.</span></span>

 ![Mensaje de articulo no encontrado.](media/access-denied-sharepoint.png)

<span data-ttu-id="f4682-142">En SharePoint, recibirá un mensaje de acceso denegado.</span><span class="sxs-lookup"><span data-stu-id="f4682-142">In SharePoint, you'll receive an access denied message.</span></span>

![Mensaje de error de acceso denegado](media/blocked-access-warning.png)

## <a name="related-topics"></a><span data-ttu-id="f4682-144">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="f4682-144">Related topics</span></span>

[<span data-ttu-id="f4682-145">Controlar el acceso de los dispositivos no administrados en SharePoint</span><span class="sxs-lookup"><span data-stu-id="f4682-145">Control access for unmanaged devices in SharePoint</span></span>](/sharepoint/control-access-from-unmanaged-devices)