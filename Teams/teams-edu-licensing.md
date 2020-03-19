---
title: Recursos de Microsoft Teams para administradores de educación
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Tutorial de licencias de Microsoft Teams para EDU.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
appliesto:
- Microsoft Teams
ms.openlocfilehash: b7d5ebd0552aafffe2eb2330e6945f99dd788b2f
ms.sourcegitcommit: 86366b66b15870fe83cbb76e1ae7aa1ce9b3bfe1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2020
ms.locfileid: "42858635"
---
# <a name="assign-microsoft-teams-licenses-for-edu"></a><span data-ttu-id="a0c7a-103">Asignar licencias de Microsoft Teams para EDU</span><span class="sxs-lookup"><span data-stu-id="a0c7a-103">Assign Microsoft Teams licenses for EDU</span></span>

<span data-ttu-id="a0c7a-104">Microsoft Teams es un centro digital que reúne conversaciones, contenido y aplicaciones en un solo lugar.</span><span class="sxs-lookup"><span data-stu-id="a0c7a-104">Microsoft Teams is a digital hub that brings conversations, content, and apps together in one place.</span></span> <span data-ttu-id="a0c7a-105">Dado que se basa en Office 365, las escuelas se benefician de la integración con aplicaciones y los servicios de Office universalmente conocidos.</span><span class="sxs-lookup"><span data-stu-id="a0c7a-105">Because it's built on Office 365, schools benefit from integration with their familiar Office apps and services.</span></span> <span data-ttu-id="a0c7a-106">Su institución puede usar Microsoft Teams para crear clases colaborativas, ponerse en contacto los unos con los otros en comunidades de aprendizaje profesional y comunicarse con el personal del centro educativo. Y todo ello a través de una sola experiencia de Office 365 para el ámbito educativo.</span><span class="sxs-lookup"><span data-stu-id="a0c7a-106">Your institution can use Microsoft Teams to create collaborative classrooms, connect in professional learning communities, and communicate with school staff all from a single experience in Office 365 for Education.</span></span>

<span data-ttu-id="a0c7a-107">Para empezar, los administradores de TI tienen que usar el Centro de administración de Microsoft 365 para [habilitar Microsoft Teams en su escuela](https://docs.microsoft.com/microsoft-365/education/intune-edu-trial/enable-microsoft-teams).</span><span class="sxs-lookup"><span data-stu-id="a0c7a-107">To get started, IT administrators need to use the Microsoft 365 Admin Center to [enable Microsoft Teams for your school](https://docs.microsoft.com/microsoft-365/education/intune-edu-trial/enable-microsoft-teams).</span></span>
<span data-ttu-id="a0c7a-108">Cuando termine, debe asignar las licencias a las cuentas de usuario para que el profesor, el personal y los alumnos puedan acceder a los servicios de Office 365, como Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a0c7a-108">Once complete, you must assign licenses to user accounts so your faculty, staff, and students can access Office 365 services, such as Microsoft Teams.</span></span>

<span data-ttu-id="a0c7a-109">Puede asignar licencias a las cuentas de usuario, ya sea de forma individual o automáticamente mediante la pertenencia a grupos.</span><span class="sxs-lookup"><span data-stu-id="a0c7a-109">You can assign licenses to user accounts either individually or automatically through group membership.</span></span> <span data-ttu-id="a0c7a-110">Este artículo le guiará por los pasos para asignar licencias de Office 365 a una persona o a un conjunto reducido de cuentas de usuario en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a0c7a-110">This article will walk you through how to assign Office 365 licenses to an individual or a small set of user accounts via the Microsoft 365 admin center.</span></span> <span data-ttu-id="a0c7a-111">Para asignar licencias automáticamente mediante la pertenencia a grupos, consulte uno de nuestros artículos de soporte técnico:</span><span class="sxs-lookup"><span data-stu-id="a0c7a-111">To assign licenses automatically through group membership, see one of our supporting articles:</span></span>

- [<span data-ttu-id="a0c7a-112">PowerShell de Office 365</span><span class="sxs-lookup"><span data-stu-id="a0c7a-112">Office 365 Powershell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)
- [<span data-ttu-id="a0c7a-113">Concesión de licencias basada en grupo en Active Directory</span><span class="sxs-lookup"><span data-stu-id="a0c7a-113">Group-based Licensing in Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)

<span data-ttu-id="a0c7a-114">Puede asignar licencias a los usuarios en la página **Licencias** o en la página **Usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="a0c7a-114">You can assign licenses to users on either the **Licenses** page, or on the **Active Users** page.</span></span> <span data-ttu-id="a0c7a-115">El método que use dependerá de si desea asignar licencias de producto a usuarios específicos o si quiere asignar licencias de usuarios a productos específicos.</span><span class="sxs-lookup"><span data-stu-id="a0c7a-115">Which method you use depends on whether you want to assign product licenses to specific users, or assign users licenses to specific products.</span></span>

> [!NOTE]
> <span data-ttu-id="a0c7a-116">Si no usa el nuevo Centro de administración de Microsoft 365, puede activarlo seleccionando **Probar el nuevo centro de administración** ubicado en la parte superior de la página de inicio.</span><span class="sxs-lookup"><span data-stu-id="a0c7a-116">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

## <a name="assign-licenses-to-users-on-the-licenses-page"></a><span data-ttu-id="a0c7a-117">Asignar licencias a los usuarios en la página licencias</span><span class="sxs-lookup"><span data-stu-id="a0c7a-117">Assign licenses to users on the Licenses page</span></span>

> [!NOTE]
> <span data-ttu-id="a0c7a-118">Debe ser un administrador global, administrador de facturación, administrador de licencias o administrador de administración de usuarios. Para obtener más información, consulte [Información sobre los roles de administrador de Office 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="a0c7a-118">You must be a Global admin, Billing admin, License admin, or User management admin. For more information, see [About Office 365 admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="a0c7a-119">Al usar la página de **Licencias** para asignar licencias, asigna licencias para un producto específico a un máximo de 20 usuarios.</span><span class="sxs-lookup"><span data-stu-id="a0c7a-119">When you use the **Licenses** page to assign licenses, you assign licenses for a specific product for up to 20 users.</span></span> <span data-ttu-id="a0c7a-120">En la página **Licencias**, verá una lista de todos los productos para los que tiene suscripciones, junto con el número total de licencias de cada producto, cuántas licencias están asignadas y cuántas están disponibles.</span><span class="sxs-lookup"><span data-stu-id="a0c7a-120">On the **Licenses** page, you see a list of all the products you have subscriptions for, together with the total number of licenses for each product, how many licenses are assigned, and how many are available.</span></span>

1. <span data-ttu-id="a0c7a-121">En el Centro de administración, vaya a la página **Facturación** > [Licencias](https://go.microsoft.com/fwlink/p/?linkid=842264).</span><span class="sxs-lookup"><span data-stu-id="a0c7a-121">In the admin center, go to the **Billing** > [Licenses](https://go.microsoft.com/fwlink/p/?linkid=842264) page.</span></span>

   ![Captura de pantalla de la ventana facturación y las opciones de menú.](media/EDU-Lic-Billing-License.png)
2. <span data-ttu-id="a0c7a-123">Seleccione un producto para el que quiera asignar licencias.</span><span class="sxs-lookup"><span data-stu-id="a0c7a-123">Select a product for which you want to assign licenses.</span></span> <span data-ttu-id="a0c7a-124">Microsoft Teams forma parte del SKU para estudiantes gratuito de Office 365 A1.</span><span class="sxs-lookup"><span data-stu-id="a0c7a-124">Microsoft Teams is part of the free Office 365 A1 for Students SKU.</span></span>

   ![Captura de pantalla de la página Licencias con productos disponibles para asignar licencias.](media/EDU-Lic-Licenses-Products.png)
3. <span data-ttu-id="a0c7a-126">Seleccione **Asignar licencias**.</span><span class="sxs-lookup"><span data-stu-id="a0c7a-126">Select **Assign licenses**.</span></span>

   ![Captura de pantalla de la sección Usuarios de la página y la opción Asignar licencias con el signo más delante.](media/EDU-Lic-Assign-Licenses.png)
4. <span data-ttu-id="a0c7a-128">En el panel **Asignar licencias a los usuarios**, empiece a escribir un nombre, lo que generará una lista de nombres.</span><span class="sxs-lookup"><span data-stu-id="a0c7a-128">In the **Assign licenses to users** pane, begin typing a name, which should generate a list of names.</span></span> <span data-ttu-id="a0c7a-129">Elija en los resultados el nombre que busca para agregarlo a la lista.</span><span class="sxs-lookup"><span data-stu-id="a0c7a-129">Choose the name you're looking for from the results to add it to the list.</span></span> <span data-ttu-id="a0c7a-130">Puede agregar hasta 20 usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="a0c7a-130">You can add up to 20 users at a time.</span></span>

   ![Captura de pantalla de la página de Asignar licencias a los usuarios con un nombre parcial escrito, donde se muestran los resultados de la búsqueda para ese nombre parcial.](media/EDU-Lic-Assign-Licenses-Users.png)
5. <span data-ttu-id="a0c7a-132">Seleccione **Activar o desactivar aplicaciones y servicios** para asignar o quitar el acceso a elementos específicos, como Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a0c7a-132">Select **Turn apps and services on or off** to assign or remove access to specific items, such as Microsoft Teams.</span></span> <span data-ttu-id="a0c7a-133">Asegúrese de que **Microsoft Teams** y **Office para la web (Educación)** estén seleccionados.</span><span class="sxs-lookup"><span data-stu-id="a0c7a-133">Ensure **Microsoft Teams** and **Office for the web (Education)** are selected.</span></span>
6. <span data-ttu-id="a0c7a-134">Cuando termine, seleccione **Asignar** y haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="a0c7a-134">When you're finished, select **Assign**, then select **Close**.</span></span>

<span data-ttu-id="a0c7a-135">Para cambiar las aplicaciones y los servicios a los que tiene acceso un usuario:</span><span class="sxs-lookup"><span data-stu-id="a0c7a-135">To change the apps and services a user has access to:</span></span>

1. <span data-ttu-id="a0c7a-136">Seleccione la fila que contiene el usuario.</span><span class="sxs-lookup"><span data-stu-id="a0c7a-136">Select the row that contains the user.</span></span>
1. <span data-ttu-id="a0c7a-137">En el panel derecho, active o desactive las aplicaciones y servicios a los que quiere dar o quitar acceso.</span><span class="sxs-lookup"><span data-stu-id="a0c7a-137">In the right pane, select or deselect the apps and services that you want to give access to, or remove access from.</span></span>
1. <span data-ttu-id="a0c7a-138">Cuando haya terminado, seleccione **Guardar** y haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="a0c7a-138">When you're finished, select **Save**, then select **Close**.</span></span>

## <a name="assign-licenses-to-an-individual-or-multiple-users-on-the-active-users-page"></a><span data-ttu-id="a0c7a-139">Asignar licencias a un usuario individual o a varios usuarios en la página Usuarios activos</span><span class="sxs-lookup"><span data-stu-id="a0c7a-139">Assign licenses to an individual or multiple users on the Active users page</span></span>

1. <span data-ttu-id="a0c7a-140">En el Centro de administración, vaya a la página **Usuarios**  >  [Usuarios activos](https://go.microsoft.com/fwlink/p/?linkid=834822).</span><span class="sxs-lookup"><span data-stu-id="a0c7a-140">In the admin center, go to the **Users** > [Active users](https://go.microsoft.com/fwlink/p/?linkid=834822) page.</span></span>

   ![Captura de pantalla de la opción de menú Usuarios activos en el Centro de administración de Microsoft O365.](media/EDU-Lic-Active-Users.png)
2. <span data-ttu-id="a0c7a-142">Seleccione los círculos junto al (a los) nombre(s) del (de los) usuario(s) al (a los) que quiere asignar licencias.</span><span class="sxs-lookup"><span data-stu-id="a0c7a-142">Select the circles next to the name(s) of the user(s) you want to assign license(s) to.</span></span>

   ![Captura de pantalla de la página Usuarios activos y una lista de los usuarios activos de la página, con algunos usuarios seleccionados, ya que se ha rellenado un círculo junto a sus nombres.](media/EDU-Lic-Active-Users-List.png)
3. <span data-ttu-id="a0c7a-144">En la parte superior, seleccione **Administrar licencias de producto**.</span><span class="sxs-lookup"><span data-stu-id="a0c7a-144">At the top select **Manage product licenses**.</span></span>

   ![Captura de pantalla de la pestaña Administrar licencias de producto y un usuario que aparece sin licencia.](media/EDU-Lic-Manage-Product-Licenses.png)
4. <span data-ttu-id="a0c7a-146">En el panel **Administrar licencias de producto**, seleccione **Agregar a las asignaciones de licencias de producto existentes**  >  **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a0c7a-146">In the **Manage product licenses** pane, select **Add to existing product license assignments** > **Next**.</span></span>

   ![Captura de pantalla de la ventana Administrar licencias de producto, con el botón de radio Agregar a las asignaciones de licencias de producto existentes activado.](media/EDU-Lic-Add-Existing-Product.png)
5. <span data-ttu-id="a0c7a-148">En el panel **Agregar a los productos existentes**, cambie el botón de alternancia a la posición de **Activado** para la licencia que quiere que tengan los usuarios seleccionados.</span><span class="sxs-lookup"><span data-stu-id="a0c7a-148">In the **Add to existing products** pane, switch the toggle to the **On** position for the license that you want the selected users to have.</span></span> <span data-ttu-id="a0c7a-149">Asegúrese de que **Microsoft Teams** y **Office para la web (Educación)** estén seleccionados.</span><span class="sxs-lookup"><span data-stu-id="a0c7a-149">Ensure **Microsoft Teams** and **Office for the web (Education)** are selected.</span></span>

   ![Captura de pantalla de la pestaña Agregar a los productos existentes en la que se ha seleccionado Microsoft Teams y Office para la web, Educación.](media/EDU-Lic-Add-Existing-Products.png)

   <span data-ttu-id="a0c7a-151">De forma predeterminada, todos los servicios asociados con esas licencias se asignan automáticamente al usuario o los usuarios.</span><span class="sxs-lookup"><span data-stu-id="a0c7a-151">By default, all services associated with those license(s) are automatically assigned to the user(s).</span></span> <span data-ttu-id="a0c7a-152">Puede limitar los servicios que están disponibles para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="a0c7a-152">You can limit which services are available to the users.</span></span> <span data-ttu-id="a0c7a-153">Cambie el botón de alternancia a la posición de **Desactivado** para los servicios que no quiere que tengan los usuarios.</span><span class="sxs-lookup"><span data-stu-id="a0c7a-153">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="a0c7a-154">En la parte inferior del panel, seleccione Agregar > Cerrar.</span><span class="sxs-lookup"><span data-stu-id="a0c7a-154">At the bottom of the pane, select Add > Close.</span></span>
